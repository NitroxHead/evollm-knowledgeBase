# LLM Roles in Evolutionary Computation

## 1. LLM as Mutation Operator

The most common and impactful integration pattern. The LLM replaces random perturbation with semantically meaningful modifications.

**How it works:**
1. Select a parent solution (code/text) from the population
2. Construct a prompt with the parent + problem context + performance feedback
3. LLM generates a modified version
4. Evaluate the offspring

**Advantages over random mutation:**
- Understands code semantics -- won't produce syntactically invalid code
- Can make large, coordinated changes across multiple parts of a solution
- Can leverage knowledge from pretraining about algorithms, patterns, and best practices
- Can accept natural-language feedback to guide improvements

**Projects:** AlphaEvolve, FunSearch, ELM, ShinkaEvolve, LLaMEA, EoH, Eureka

## 2. LLM as Crossover Operator

The LLM combines ideas from multiple parent solutions, going beyond syntactic recombination.

**How it works:**
1. Select 2+ parent solutions from the population
2. Present all parents in the prompt (few-shot style)
3. LLM generates offspring that blends ideas from parents
4. This is "semantic crossover" -- the LLM understands what each parent does and combines at the conceptual level

**Key paper:** "Language Model Crossover: Variation through Few-Shot Prompting" (Meyerson et al., 2023)

**Projects:** EvoPrompt, Language Model Crossover, AlphaEvolve (implicit via inspiration programs)

## 3. LLM as Fitness Evaluator / Surrogate

The LLM approximates the fitness function, useful when automated evaluation is expensive or impossible.

**How it works:**
1. Present the candidate solution to the LLM
2. Ask the LLM to score it on relevant criteria
3. Use the LLM's assessment as a fitness signal

**Advantages:**
- Can evaluate subjective qualities (creativity, readability, beauty)
- Can provide multi-dimensional feedback
- Can explain why a solution is good or bad

**Limitations:**
- Less reliable than automated evaluation on objective metrics
- Can be manipulated by adversarial solutions

**Projects:** QDAIF (Quality-Diversity through AI Feedback)

## 4. LLM as Reflector / Feedback Provider

A distinctive role where the LLM analyzes performance differences between solutions and provides natural-language improvement guidance.

**How it works:**
1. Compare two or more solutions with different fitness scores
2. Ask the LLM to explain why one is better
3. Feed this "verbal gradient" back into the mutation process

**Projects:** ReEvo (explicit reflector LLM), Eureka (reward reflection)

## 5. Dual-Role: Thought + Code Generation

The LLM simultaneously evolves natural-language reasoning and executable code, using each to guide the other.

**How it works:**
1. Represent solutions as (thought, code) pairs
2. Evolve thoughts at the conceptual level
3. Translate thoughts to code
4. Evaluate code for fitness
5. Use fitness to select (thought, code) pairs

**Projects:** EoH (Evolution of Heuristics)

## Comparison Matrix

| Role | Replaces | Key Advantage | Key Limitation |
|---|---|---|---|
| Mutation Operator | Random perturbation | Semantic understanding | Compute cost per evaluation |
| Crossover Operator | Syntactic recombination | Conceptual blending | May lose parent diversity |
| Fitness Evaluator | Manual/automated scoring | Subjective quality assessment | Reliability on objective tasks |
| Reflector | N/A (new role) | Targeted improvement guidance | Requires good explanation ability |
| Thought+Code | N/A (new role) | Higher-level search space | Increased complexity |
