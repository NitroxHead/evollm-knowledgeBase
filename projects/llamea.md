# LLaMEA

**Organization:** Leiden University (XAI-LIACS group)
**Year:** 2024
**Status:** Open-sourced (MIT)
**Venue:** IEEE Transactions on Evolutionary Computation

## Overview

LLaMEA (Large Language Model Evolutionary Algorithm) automates the design of metaheuristic optimization algorithms. The LLM generates, mutates, and refines entire optimization algorithms as code, evaluated on standard benchmarks.

## Approach

- **(1+1) evolutionary strategy**: Single parent, single offspring per generation
- **LLM as mutation operator**: GPT-4 generates and modifies algorithm implementations
- **Feedback loop**: Error traces + performance metrics fed back to LLM
- **Full algorithm evolution**: Entire metaheuristic algorithms (not just parameters)

## Results

- Generated novel metaheuristics that **outperformed CMA-ES and Differential Evolution** on BBOB benchmark suite (5D)
- Won the **Silver Humies Award at GECCO 2025** for human-competitive results
- Demonstrated that LLMs can design optimization algorithms from scratch

## Paper

**"LLaMEA: A Large Language Model Evolutionary Algorithm for Automatically Generating Metaheuristics"**
Leiden University / XAI-LIACS group
arXiv: [2405.20132](https://arxiv.org/abs/2405.20132)
IEEE TEVC 2024

## Repository

[XAI-liacs/LLaMEA](https://github.com/XAI-liacs/LLaMEA) -- MIT License

## See Also

- [EoH](eoh.md) -- Heuristic evolution with dual representation
- [ReEvo](reevo.md) -- Reflective heuristic evolution
- [AlphaEvolve](alphaevolve.md) -- Full-scale algorithm evolution at Google
