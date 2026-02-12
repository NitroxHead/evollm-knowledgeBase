# Evolutionary Frameworks Used in LLM+Evolution

## 1. MAP-Elites (Quality-Diversity)

**Most commonly used framework** in the field. Maintains a grid of solutions indexed by behavioral descriptors, keeping the best solution in each cell.

```
         Feature 1 →
    ┌────┬────┬────┬────┐
    │ A  │    │ C  │    │  Feature 2
    ├────┼────┼────┼────┤    ↓
    │    │ B  │    │ D  │
    ├────┼────┼────┼────┤
    │ E  │    │ F  │    │
    └────┴────┴────┴────┘
    Each cell: best solution with those features
```

**Why it's popular for LLM+evolution:**
- Maintains diversity (prevents LLM from converging on one type of solution)
- Provides diverse parent selection (LLM gets varied examples)
- Naturally supports multi-objective problems

**Used by:** AlphaEvolve, FunSearch, ELM/OpenELM, Darwin Godel Machine, LLMatic, QDAIF

## 2. Island Model

Multiple independent populations evolve in parallel with periodic migration of solutions between islands.

```
  ┌─────────┐     ┌─────────┐     ┌─────────┐
  │ Island 1│────>│ Island 2│────>│ Island 3│
  │ (Pop A) │<────│ (Pop B) │<────│ (Pop C) │
  └─────────┘     └─────────┘     └─────────┘
       Migration of best solutions periodically
```

**Why it's useful:**
- Prevents premature convergence
- Enables different prompting strategies per island
- Natural parallelism

**Used by:** FunSearch, AlphaEvolve (combined with MAP-Elites)

## 3. (1+1) Evolutionary Strategy

Simplest possible evolutionary algorithm: one parent, one offspring, keep the better one.

```
Parent → Mutate → Offspring → Compare → Keep better
```

**Why it works for LLM+evolution:**
- Minimal infrastructure needed
- LLM mutation is expensive, so fewer candidates per generation makes sense
- Works well when the LLM produces high-quality mutations

**Used by:** LLaMEA, OPRO (conceptually)

## 4. Genetic Algorithm (GA)

Traditional population-based approach with selection, crossover, and mutation.

```
Population → Selection → Crossover → Mutation → New Population
```

**LLM adaptation:** The LLM replaces both crossover and mutation operators. Selection remains fitness-proportionate or tournament-based.

**Used by:** EvoPrompt (GA variant)

## 5. Differential Evolution (DE)

Uses differences between population members to guide mutation direction.

```
Target + F * (Donor1 - Donor2) → Trial → Selection
```

**LLM adaptation:** Instead of arithmetic difference, the LLM is prompted to capture the "conceptual difference" between solutions and apply it.

**Used by:** EvoPrompt (DE variant)

## 6. Novelty Search

Rewards solutions for being different from existing solutions, rather than for fitness.

**Adaptation:** ShinkaEvolve uses novelty-based rejection to avoid evaluating redundant solutions.

**Used by:** ShinkaEvolve (novelty filtering), ELM/OpenELM (MAP-Elites inherently includes novelty)

## 7. CMA-ES (Covariance Matrix Adaptation)

Continuous optimization algorithm that adapts a multivariate Gaussian distribution over the search space.

**Used for:** Evolving continuous parameters (merge weights, hyperparameters) rather than code.

**Used by:** Evolutionary Model Merging

## Framework Comparison

| Framework | Population Size | Diversity Mechanism | Best For |
|---|---|---|---|
| MAP-Elites | Grid-based | Feature-space partitioning | Code/program evolution |
| Island Model | Multiple small pops | Geographic isolation | Parallel exploration |
| (1+1) ES | 1 | None (relies on LLM) | Simple problems, expensive eval |
| GA | Fixed population | Crossover + selection | Prompt optimization |
| DE | Fixed population | Difference-based mutation | Prompt optimization |
| Novelty Search | Variable | Novelty metric | Avoiding local optima |
| CMA-ES | Continuous | Covariance adaptation | Parameter optimization |

## Common Combinations

- **MAP-Elites + Island Model**: AlphaEvolve, FunSearch -- diversity at two levels
- **MAP-Elites + Novelty**: ShinkaEvolve -- QD with explicit novelty filtering
- **GA + LLM operators**: EvoPrompt -- classic EA structure, modern operators
