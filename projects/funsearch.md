# FunSearch

**Organization:** Google DeepMind
**Year:** 2023 (December)
**Status:** Open-sourced
**Successor:** [AlphaEvolve](alphaevolve.md)

## Overview

FunSearch ("function search") is the first system to make genuine new mathematical discoveries using LLMs. It pairs a pretrained LLM with an automated evaluator in an evolutionary loop to discover novel programs solving open mathematical problems. Unlike chatbot-style LLM use, FunSearch produces verifiably correct, novel results.

## Architecture

```
┌─────────────────────────────────────────────┐
│               FunSearch Loop                 │
│                                             │
│  ┌────────────┐    ┌────────────────────┐   │
│  │  Programs   │───>│   Prompt Assembly  │   │
│  │  Database   │    │  (best-shot)       │   │
│  │ (island     │    └────────┬───────────┘   │
│  │  model)     │             │               │
│  └──────▲──────┘             ▼               │
│         │            ┌──────────────┐        │
│         │            │  LLM (Codey/ │        │
│         │            │  PaLM 2)     │        │
│  ┌──────┴──────┐     └──────┬───────┘        │
│  │  Evaluator  │<───────────┘                │
│  │ (automated) │                             │
│  └─────────────┘                             │
└─────────────────────────────────────────────┘
```

### Key Design Decisions

- **Function-level evolution**: Evolves short function bodies (10-20 lines) within a fixed template/skeleton
- **Island model**: Multiple independent populations prevent premature convergence
- **Frozen LLM**: No fine-tuning -- uses pretrained Codey (PaLM 2 for code) as-is
- **Best-shot prompting**: Selects high-scoring parent programs as few-shot examples

### Limitations vs AlphaEvolve

| Aspect | FunSearch | AlphaEvolve |
|---|---|---|
| Scope | Single function stubs | Whole programs |
| LLM | Small code-only model | Frontier Gemini ensemble |
| Diversity | Island model only | MAP-Elites + islands |
| Objectives | Single metric | Multi-objective |

## Results

- **Cap set problem**: Discovered constructions exceeding all previously known results in extremal combinatorics
- **Bin packing**: Found more efficient online bin-packing heuristics with practical applications
- Published in **Nature** (Vol. 625, January 2024) -- a landmark publication

## Paper

**"Mathematical discoveries from program search with large language models"**
Bernardino Romera-Paredes, Mohammadamin Barekatain, Alexander Novikov, Matej Balog, M. Pawan Kumar, Emilien Dupont, Francisco J. R. Ruiz, et al.
Nature, Vol. 625, pp. 468-475 (January 2024)
DOI: [10.1038/s41586-023-06924-6](https://doi.org/10.1038/s41586-023-06924-6)

## Repository

[google-deepmind/funsearch](https://github.com/google-deepmind/funsearch) -- Apache 2.0 license

## See Also

- [AlphaEvolve](alphaevolve.md) -- Successor with whole-program evolution
- [ShinkaEvolve](shinkaevolve.md) -- Alternative with better sample efficiency
- [EoH](eoh.md) -- Outperformed FunSearch on bin packing with fewer evaluations
