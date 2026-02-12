# EvoPrompting

**Organization:** Google Brain
**Year:** 2023
**Status:** No official repo
**Venue:** NeurIPS 2023

## Overview

EvoPrompting uses LLMs as adaptive mutation and crossover operators within an evolutionary neural architecture search (NAS) algorithm. The LLM generates code-level architecture modifications -- evolving actual architecture code rather than just hyperparameters.

**Note:** Not to be confused with [EvoPrompt](evoprompt.md), which evolves text prompts.

## Approach

1. Maintain a population of neural network architectures (as code)
2. Select parents based on fitness
3. Prompt the LLM with parent architecture code
4. LLM generates offspring architectures via:
   - **Mutation**: Modify a parent architecture
   - **Crossover**: Combine elements from multiple parents
5. Evaluate offspring architectures by training
6. Select survivors and repeat

## Results

- **MNIST-1D**: Produced CNNs outperforming human-designed and few-shot-prompted architectures
- **CLRS Algorithmic Reasoning Benchmark**: Outperformed SOTA on 21/30 tasks using evolved GNN architectures

## Paper

**"EvoPrompting: Language Models for Code-Level Neural Architecture Search"**
Angelica Chen, David M. Dohan, David R. So
arXiv: [2302.14838](https://arxiv.org/abs/2302.14838)
NeurIPS 2023

## Repository

No official repository. Unofficial: [algopapi/EvoPrompting_Reinforcement_learning](https://github.com/algopapi/EvoPrompting_Reinforcement_learning)

## See Also

- [LLMatic](llmatic.md) -- QD-based NAS with LLMs
- [EvoPrompt](evoprompt.md) -- Different project: evolving text prompts
