# Evolutionary Model Merging

**Organization:** Sakana AI
**Year:** 2024
**Status:** Published
**Venue:** Nature Machine Intelligence

## Overview

Uses evolutionary algorithms to automatically discover optimal recipes for merging multiple pretrained LLMs. Instead of relying on human intuition to decide which models to merge and how, CMA-ES optimizes merge configurations to maximize performance on target benchmarks.

## Approach

Evolutionary search operates in two spaces simultaneously:

1. **Parameter space**: Optimizing merge weights (how much of each source model to use)
2. **Data flow space**: Optimizing layer connections and orderings (how layers from different models connect)

**Optimizer**: CMA-ES (Covariance Matrix Adaptation Evolution Strategy)

## Results

- Created a **Japanese Math LLM** achieving SOTA on Japanese benchmarks despite not being explicitly trained for math
- Created **culturally-aware Japanese VLMs** through cross-domain merging of language and vision models
- Demonstrated that evolution can find non-obvious model combinations humans would not try

## Paper

**"Evolutionary Optimization of Model Merging Recipes"**
Takuya Akiba, Makoto Shing, Yujin Tang, Qi Sun, David Ha
arXiv: [2403.13187](https://arxiv.org/abs/2403.13187)
Nature Machine Intelligence, 2024

## Significance

This project is unique in evolving **models** rather than programs or prompts. It shows that evolutionary principles apply at the model level too -- combining pretrained models through evolved recipes rather than expensive retraining.

## See Also

- [ShinkaEvolve](shinkaevolve.md) -- Same organization, evolving programs
- [Darwin Godel Machine](darwin-godel-machine.md) -- Same organization, self-improving agents
- [Darwin Family](../applications/neural-architecture-search.md#training-free-evolutionary-model-merging-darwin-family) (2026) -- Extends training-free evolutionary merging with a 14-dim merge genome, diagnostic MRI-Trust fusion, and cross-architecture (Transformer + Mamba) breeding
