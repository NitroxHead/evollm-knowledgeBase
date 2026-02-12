# EvoPrompt

**Organization:** Tsinghua University, Microsoft Research
**Year:** 2023
**Status:** Open-sourced
**Venue:** ICLR 2024

## Overview

EvoPrompt is a discrete prompt optimization framework that uses evolutionary algorithms (Genetic Algorithm and Differential Evolution) to evolve task prompts for LLMs. The LLM itself serves as the operator that generates new prompt candidates -- connecting evolutionary algorithms with LLMs for prompt optimization.

## Approach

Two evolutionary strategies adapted for prompt optimization:

### Genetic Algorithm (GA) Variant
- **Selection**: Tournament selection from prompt population
- **Crossover**: LLM combines two parent prompts into offspring
- **Mutation**: LLM modifies offspring prompts

### Differential Evolution (DE) Variant
- Adapts DE's difference-based mutation to text:
  - Select base prompt + two difference prompts
  - LLM generates new prompt capturing the "difference" between prompts
  - More structured exploration than GA

## Results

- Outperformed human-engineered prompts by up to **25% on BIG-Bench Hard**
- Tested on **31 datasets** with GPT-3.5 and Alpaca
- Consistent improvement across sentiment analysis, topic classification, and reasoning tasks

## Paper

**"Connecting Large Language Models with Evolutionary Algorithms Yields Powerful Prompt Optimizers"**
Qingyan Guo, Rui Wang, Junliang Guo, Bei Li, Kaitao Song, Xu Tan, Guoqing Liu, Jiang Bian, Yujiu Yang
arXiv: [2309.08532](https://arxiv.org/abs/2309.08532)
ICLR 2024

## Repository

[beeevita/EvoPrompt](https://github.com/beeevita/EvoPrompt)

## See Also

- [Promptbreeder](promptbreeder.md) -- Meta-evolutionary prompt optimization
- [OPRO](opro.md) -- LLM-as-optimizer for prompts
- [EvoPrompting](evoprompting.md) -- Different project: evolving neural architectures
