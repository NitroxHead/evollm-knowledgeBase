# ReEvo

**Organization:** Peking University, Southeast University, Singapore Management University, KAIST
**Year:** 2024
**Status:** Open-sourced
**Venue:** NeurIPS 2024

## Overview

ReEvo (Reflective Evolution) uses LLMs as "Language Hyper-Heuristics" to automatically design heuristics for combinatorial optimization problems. Its key innovation is a two-LLM pipeline with a Reflector that provides "verbal gradients" -- natural language feedback on why one solution outperforms another.

## Architecture

```
┌─────────────────────────────────────────────┐
│               ReEvo Pipeline                 │
│                                             │
│  ┌──────────────┐    ┌──────────────────┐   │
│  │  Generator    │───>│  Candidate       │   │
│  │  LLM         │    │  Heuristic Code  │   │
│  └──────────────┘    └────────┬─────────┘   │
│         ▲                      │             │
│         │                      ▼             │
│  ┌──────┴───────┐    ┌──────────────────┐   │
│  │  Reflector   │<───│  Evaluation on   │   │
│  │  LLM         │    │  Problem Instances│   │
│  │ ("verbal     │    └──────────────────┘   │
│  │  gradients") │                           │
│  └──────────────┘                           │
└─────────────────────────────────────────────┘
```

### Two-LLM Pipeline

1. **Generator LLM**: Produces heuristic code based on problem description + reflection feedback
2. **Reflector LLM**: Analyzes performance differences between heuristics, providing natural-language insights about what makes one better than another ("verbal gradients")

This separation allows the reflector to provide targeted improvement guidance rather than relying on the generator to infer improvements from raw scores alone.

## Results

- Heuristics generated in **minutes** outperformed SOTA human-designed heuristics and neural solvers
- Tested across **12 combinatorial optimization** problem settings:
  - Traveling Salesman Problem (TSP)
  - Capacitated Vehicle Routing Problem (CVRP)
  - Bin Packing
  - Flow Shop Scheduling
  - And more

## Paper

**"ReEvo: Large Language Models as Hyper-Heuristics with Reflective Evolution"**
Haoran Ye, Jiarui Wang, Zhiguang Cao, Federico Berto, Chuanbo Hua, Haeyeon Kim, Jinkyoo Park, Guojie Song
arXiv: [2402.01145](https://arxiv.org/abs/2402.01145)
NeurIPS 2024

## Repository

[ai4co/reevo](https://github.com/ai4co/reevo)

## See Also

- [EoH](eoh.md) -- Similar heuristic evolution with dual thought+code representation
- [LLaMEA](llamea.md) -- Evolving metaheuristic algorithms
- [FunSearch](funsearch.md) -- Broader program evolution
