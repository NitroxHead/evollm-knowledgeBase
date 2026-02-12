# LLMatic

**Organization:** NYU, University of the Witwatersrand
**Year:** 2023
**Status:** Open-sourced
**Venue:** GECCO 2024

## Overview

LLMatic merges LLM code-generation with Quality-Diversity (QD) optimization for neural architecture search. It uses the CodeGen LLM to generate neural network architectures as code and a MAP-Elites variant to maintain diverse, high-performing architecture candidates.

## Approach

- Uses **CodeGen LLM** to generate architecture code
- **2-archive QD algorithm** (MAP-Elites variant)
- Prompts and architectures **co-evolve**
- No prior knowledge of target benchmark domain required

## Results

- Competitive architectures evaluating only **2,000 candidates** on CIFAR-10 and NAS-bench-201
- Achieved results **without exposure** to top-performing models
- Demonstrated that LLMs can effectively search architecture spaces

## Paper

**"LLMatic: Neural Architecture Search via Large Language Models and Quality Diversity Optimization"**
Muhammad U. Nasir, Sam Earle, Julian Togelius, Steven James, Christopher Cleghorn
arXiv: [2306.01102](https://arxiv.org/abs/2306.01102)
GECCO 2024

## Repository

[umair-nasir14/LLMatic](https://github.com/umair-nasir14/LLMatic)

## See Also

- [EvoPrompting](evoprompting.md) -- Another LLM-based NAS approach
- [OpenELM](openelm.md) -- General QD+LLM framework
