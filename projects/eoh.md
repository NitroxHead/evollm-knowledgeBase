# Evolution of Heuristics (EoH)

**Organization:** City University of Hong Kong, Huawei, HKUST
**Year:** 2024
**Status:** Open-sourced
**Venue:** ICML 2024

## Overview

EoH evolves both the **"thought"** (natural-language idea/reasoning) and the **"code"** (executable implementation) of heuristics simultaneously. The LLM serves as both idea generator and code translator within an evolutionary framework.

## Key Innovation: Dual Representation

```
┌─────────────────────────────────────────────┐
│         Dual Evolution                       │
│                                             │
│  ┌──────────────┐    ┌──────────────────┐   │
│  │   Thought     │◄──►│     Code         │   │
│  │ (NL idea)     │    │ (executable)     │   │
│  └──────┬───────┘    └────────┬─────────┘   │
│         │                      │             │
│         ▼                      ▼             │
│  ┌──────────────────────────────────────┐   │
│  │  Evolutionary operators (via LLM)    │   │
│  │  - Mutate thought → new thought      │   │
│  │  - Translate thought → code          │   │
│  │  - Crossover thoughts               │   │
│  │  - Crossover code                   │   │
│  └──────────────┬───────────────────────┘   │
│                 │                            │
│                 ▼                            │
│  ┌──────────────────────────────────────┐   │
│  │  Evaluate code on problem instances  │   │
│  └──────────────────────────────────────┘   │
└─────────────────────────────────────────────┘
```

The thought provides a higher-level search space that guides code evolution -- mutations happen at the conceptual level and are then grounded in code.

## Results

- **Outperformed FunSearch** on online bin packing
- Achieved superior heuristics with **significantly fewer computational evaluations**
- Demonstrated that dual thought+code evolution provides better search guidance than code-only

## Paper

**"Evolution of Heuristics: Towards Efficient Automatic Algorithm Design Using Large Language Model"**
Fei Liu, Xialiang Tong, Mingxuan Yuan, Xi Lin, Fu Luo, Zhenkun Wang, Zhichao Lu, Qingfu Zhang
arXiv: [2401.02051](https://arxiv.org/abs/2401.02051)
ICML 2024

## Repository

[FeiLiu36/EoH](https://github.com/FeiLiu36/EoH)

## See Also

- [ReEvo](reevo.md) -- Similar heuristic evolution with reflective feedback
- [FunSearch](funsearch.md) -- Code-only evolution baseline
- [LLaMEA](llamea.md) -- Evolving metaheuristic algorithms
