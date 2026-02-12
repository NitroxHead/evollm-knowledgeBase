# ShinkaEvolve

**Organization:** Sakana AI
**Year:** 2025
**Status:** Open-sourced (Apache 2.0)

## Overview

ShinkaEvolve is a sample-efficient LLM-driven program evolution framework. While FunSearch and AlphaEvolve achieve results through massive compute, ShinkaEvolve focuses on achieving comparable or superior results with orders of magnitude fewer evaluations.

## Key Innovations

### 1. Adaptive Parent Sampling
Balances exploration vs exploitation when selecting parent programs. Dynamically adjusts the selection pressure based on the current state of the evolutionary search.

### 2. Novelty-Based Rejection
Avoids redundant evaluations by filtering out candidate programs that are too similar to previously evaluated solutions. This dramatically reduces wasted compute.

### 3. Bandit-Based LLM Selector
Uses a multi-armed bandit algorithm to route mutation tasks to the most effective LLM in an ensemble. Different LLMs may be better at different types of mutations; the bandit learns which to use when.

## Results

- **Circle packing**: Discovered new SOTA solution in only ~150 evaluations (orders of magnitude fewer than FunSearch/AlphaEvolve)
- **ALE-Bench**: Improved competitive programming solutions
- **ICFP 2025**: Helped win the 2025 ICFP Programming Contest

## Paper

**"ShinkaEvolve: Towards Open-Ended And Sample-Efficient Program Evolution"**
Robert Tjarko Lange, Yuki Imajuku, Edoardo Cetin, Aaditya Prasad, Qi Sun, Maxence Faldor, Yujin Tang, David Ha
arXiv: [2509.19349](https://arxiv.org/abs/2509.19349) (September 2025)

## Repository

[SakanaAI/ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) -- Apache 2.0 license

## Comparison with AlphaEvolve

| Aspect | AlphaEvolve | ShinkaEvolve |
|---|---|---|
| Focus | Raw performance | Sample efficiency |
| Evaluations needed | Thousands+ | ~150 for SOTA |
| Open source | No (results only) | Yes (full framework) |
| LLM selection | Fixed ensemble | Bandit-based adaptive |
| Novelty filtering | No | Yes |
| Organization | Google DeepMind | Sakana AI |

## Key People

- **Robert Tjarko Lange** -- Also involved in Darwin Godel Machine
- **David Ha** -- Sakana AI founder, former Google Brain

## See Also

- [AlphaEvolve](alphaevolve.md) -- Higher-compute alternative
- [FunSearch](funsearch.md) -- Earlier approach with similar goals
- [Darwin Godel Machine](darwin-godel-machine.md) -- Another Sakana AI project
