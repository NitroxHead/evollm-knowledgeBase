# Promptbreeder

**Organization:** Google DeepMind
**Year:** 2023
**Status:** Research paper (no official repo)
**Venue:** ICML 2024

## Overview

Promptbreeder is a self-referential self-improvement system that evolves not only task-prompts but also the **mutation-prompts** that govern how task-prompts are mutated. This creates a two-level evolutionary hierarchy -- a meta-evolutionary approach.

## Key Innovation: Self-Referential Evolution

Traditional prompt evolution optimizes task prompts directly. Promptbreeder goes one level deeper:

```
Level 2: Mutation-prompts (HOW to mutate)
    │
    ▼ (applied to)
Level 1: Task-prompts (WHAT to say to the LLM)
    │
    ▼ (evaluated on)
Level 0: Task performance
```

Both levels evolve simultaneously, allowing the system to discover better mutation strategies as it goes.

## Mutation Strategies

1. **Direct Mutation**: Mutation-prompt applied to task-prompt
2. **Estimation of Distribution**: Generate new prompts from observed distribution
3. **Hypermutation**: Mutate the mutation-prompts themselves
4. **Lamarckian Mutation**: Use task performance feedback to guide mutations
5. **Prompt Crossover**: Combine elements from different prompts

## Results

- Outperformed **Chain-of-Thought**, **Plan-and-Solve**, and other SOTA prompting strategies
- Tested on arithmetic and commonsense reasoning benchmarks
- Achieved improvements **without any parameter updates** to the LLM

## Paper

**"Promptbreeder: Self-Referential Self-Improvement Via Prompt Evolution"**
Chrisantha Fernando, Dylan Banarse, Henryk Michalewski, Simon Osindero, Tim Rocktaschel
arXiv: [2309.16797](https://arxiv.org/abs/2309.16797)
ICML 2024

## See Also

- [EvoPrompt](evoprompt.md) -- GA/DE-based prompt evolution
- [OPRO](opro.md) -- LLM-as-optimizer for prompts
