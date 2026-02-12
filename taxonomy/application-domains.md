# Application Domains

## 1. Mathematical Discovery

The most high-profile application domain, with publications in Nature.

| Achievement | Project | Significance |
|---|---|---|
| Cap set constructions | FunSearch | First LLM-driven math discovery (Nature 2024) |
| 4x4 matrix multiplication (48 ops) | AlphaEvolve | First improvement over Strassen in 56 years |
| Kissing number (11D: 593) | AlphaEvolve | Improved decades-old bound |
| 67 open problems explored | AlphaEvolve + Tao | Improved 20% of best-known solutions |
| Circle packing SOTA | ShinkaEvolve | In only ~150 evaluations |

## 2. Code / Algorithm Optimization

Optimizing existing algorithms and infrastructure code.

| Achievement | Project | Impact |
|---|---|---|
| Data center scheduling (Borg) | AlphaEvolve | 0.7% of Google's worldwide compute recovered |
| Gemini training kernel | AlphaEvolve | 23% kernel speedup, 1% overall training reduction |
| FlashAttention | AlphaEvolve | Up to 32.5% kernel speedup |
| TPU Verilog design | AlphaEvolve | Reduced area/power in production TPU |

## 3. Combinatorial Optimization

Evolving heuristics for NP-hard problems.

| Problem Domain | Projects | Notes |
|---|---|---|
| Bin Packing | FunSearch, EoH | Both found improvements over human heuristics |
| TSP | ReEvo | Outperformed neural solvers |
| Vehicle Routing (CVRP) | ReEvo | Minutes to generate, outperforms SOTA |
| Flow Shop Scheduling | ReEvo | 12 problem settings tested |
| General metaheuristics | LLaMEA | Outperformed CMA-ES and DE |

## 4. Neural Architecture Search

Discovering neural network architectures.

| Benchmark | Project | Result |
|---|---|---|
| MNIST-1D | EvoPrompting | Outperformed human-designed CNNs |
| CLRS (algorithmic reasoning) | EvoPrompting | SOTA on 21/30 tasks |
| CIFAR-10 / NAS-bench-201 | LLMatic | Competitive in 2,000 evaluations |

## 5. Robotics

Evolving robot behaviors and controllers.

| Task | Project | Result |
|---|---|---|
| Virtual walking robots | ELM | Hundreds of thousands of functional robots |
| Dexterous manipulation | Eureka | Pen spinning with Shadow Hand |
| 29 RL tasks (10 morphologies) | Eureka | 83% outperformed expert rewards |

## 6. Prompt Engineering

Optimizing prompts for LLM performance.

| Benchmark | Project | Improvement |
|---|---|---|
| BIG-Bench Hard | EvoPrompt | Up to 25% over human prompts |
| BIG-Bench Hard | OPRO | Up to 50% over human prompts |
| GSM8K | OPRO | Up to 8% improvement |
| Arithmetic/commonsense | Promptbreeder | Outperformed CoT, Plan-and-Solve |

## 7. Self-Improving AI Systems

Agents that evolve themselves.

| Benchmark | Project | Before → After |
|---|---|---|
| SWE-bench | Darwin Godel Machine | 20.0% → 50.0% |
| Polyglot | Darwin Godel Machine | 14.2% → 30.7% |
| Competitive programming | ShinkaEvolve | ICFP 2025 contest winner |

## 8. Model Optimization

Evolving model configurations and merge recipes.

| Task | Project | Result |
|---|---|---|
| Japanese Math LLM | Evo Model Merge | SOTA on Japanese benchmarks |
| Cross-domain VLM | Evo Model Merge | Culturally-aware vision-language model |

## Domain Maturity Assessment

```
Most Mature ──────────────────────────────── Least Mature

Mathematical    Code         Prompt      Self-Improving
Discovery       Optimization Engineering Systems
  ████████       ██████       █████        ██
  (Nature        (Google      (Multiple    (Early
  papers,        production)  benchmarks)  results)
  verified
  results)
```
