# Evolution through Large Models (ELM)

**Organization:** OpenAI
**Year:** 2022 (June)
**Status:** Open-sourced via CarperAI

## Overview

ELM is the foundational paper that formally proposed using LLMs as intelligent mutation operators within evolutionary loops. Instead of random code mutations, an LLM generates meaningful code variations. This paper established the conceptual framework that FunSearch, AlphaEvolve, and subsequent systems built upon.

## Key Contributions

1. **LLMs as mutation operators**: Showed that LLMs can serve as semantically-aware genetic operators, replacing random perturbation with meaningful code modification
2. **Open-ended evolution**: Demonstrated evolution in domains the LLM never saw during pretraining (Sodarace virtual robots)
3. **Bootstrapping loop**: Evolved programs can be used to fine-tune the LLM itself, creating a virtuous cycle

## Architecture

```
┌─────────────────────────────────────────────┐
│              ELM Architecture                │
│                                             │
│  ┌──────────┐    ┌──────────────────────┐   │
│  │  MAP-     │───>│  LLM Mutation        │   │
│  │  Elites   │    │  (code generation)   │   │
│  │  Archive  │    └──────────┬───────────┘   │
│  └─────▲─────┘               │               │
│        │                     ▼               │
│  ┌─────┴─────┐    ┌──────────────────────┐  │
│  │ Simulation │<───│  Sodarace Environment│  │
│  │ Evaluation │    │  (walking robots)    │  │
│  └───────────┘    └──────────────────────┘  │
│                                             │
│  ┌──────────────────────────────────────┐   │
│  │  Fine-tuning: LLM ← best programs   │   │
│  └──────────────────────────────────────┘   │
└─────────────────────────────────────────────┘
```

### Three Components

1. **LLM-driven mutation operator**: The LLM receives parent program(s) and generates variations
2. **Evolutionary outer loop (MAP-Elites)**: Quality-diversity algorithm maintaining diverse, high-quality solutions
3. **LLM fine-tuning on evolved programs**: Successful outputs improve the LLM's future mutation capabilities

## Results

- Generated **hundreds of thousands** of functional virtual walking robots in Sodarace
- Robots evolved in a domain **entirely unseen** during LLM pretraining
- Demonstrated bootstrapping of domain-specific conditional language models from evolution

## Paper

**"Evolution through Large Models"**
Joel Lehman, Jonathan Gordon, Shawn Jain, Kamal Ndousse, Cathy Yeh, Kenneth O. Stanley
arXiv: [2206.08896](https://arxiv.org/abs/2206.08896) (June 2022)
Also published as Springer Handbook chapter (2023)

## Repository

[CarperAI/OpenELM](https://github.com/CarperAI/OpenELM)

## Key People

- **Joel Lehman** -- Pioneer of novelty search and quality-diversity, also co-author of Language Model Crossover
- **Kenneth O. Stanley** -- Co-inventor of NEAT, neuroevolution pioneer

## Significance

ELM is considered the **origin paper** for the LLM+evolution field. It established:
- The conceptual framework of "LLMs as genetic operators"
- That LLMs can enable evolution in novel domains
- The potential for self-improving evolutionary systems

## See Also

- [OpenELM](openelm.md) -- Open-source library implementing ELM concepts
- [FunSearch](funsearch.md) -- Applied similar ideas to mathematical discovery
- [AlphaEvolve](alphaevolve.md) -- Industrial-scale successor
