# AlphaEvolve

**Organization:** Google DeepMind
**Year:** 2025 (May)
**Status:** Production use at Google (not open-sourced)
**Predecessor:** [FunSearch](funsearch.md)

## Overview

AlphaEvolve is an evolutionary coding agent that combines Gemini LLMs with evolutionary search to discover and optimize algorithms. It is the successor to FunSearch, with key improvements: whole-program evolution (not just single functions), frontier LLM ensemble, and multi-objective optimization.

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    AlphaEvolve Pipeline                   │
│                                                         │
│  ┌──────────────┐    ┌─────────────────┐                │
│  │    Prompt     │───>│  LLM Ensemble   │                │
│  │   Sampler     │    │ ┌─────────────┐ │                │
│  │              │    │ │ Gemini Flash │ │  (breadth)     │
│  │ - parent     │    │ │ Gemini Pro   │ │  (depth)      │
│  │ - inspiration│    │ └─────────────┘ │                │
│  └──────────────┘    └────────┬────────┘                │
│         ▲                      │                         │
│         │                      ▼                         │
│  ┌──────┴───────┐    ┌─────────────────┐                │
│  │   Programs    │<───│   Evaluators    │                │
│  │   Database    │    │ (multi-metric)  │                │
│  │              │    └─────────────────┘                │
│  │ MAP-Elites + │                                       │
│  │ Island Model │                                       │
│  └──────────────┘                                       │
└─────────────────────────────────────────────────────────┘
```

### Components

1. **Prompt Sampler** -- Assembles context-rich prompts by selecting parent programs (direct basis for improvement) and inspiration programs (for diverse ideas) from the database.

2. **LLM Ensemble** -- Two-tier Gemini model strategy:
   - **Gemini Flash**: Lightweight, fast; maximizes breadth of exploration
   - **Gemini Pro**: Powerful; provides depth with higher-quality suggestions

3. **Evaluators** -- Automated evaluation on user-defined scalar metrics (performance, resource usage, correctness, LLM-assessed quality).

4. **Programs Database** -- Stores all programs + metrics. Implements:
   - **MAP-Elites**: Maintains diverse archive indexed by solution features
   - **Island Model**: Independent sub-populations with periodic migration

### Key Design Principles

- **Asynchronous pipeline** using Python asyncio for throughput
- **Whole-program evolution** (hundreds of lines, not just function stubs)
- **Diversity preservation** via MAP-Elites + island model
- **Human-readable outputs** for auditability

## Results

### Mathematics
- **4x4 matrix multiplication**: Found procedure using 48 scalar multiplications -- first improvement over Strassen's 1969 algorithm in 56 years
- **50+ open math problems**: Rediscovered SOTA in 75%, improved best-known in 20%
- **Kissing number**: Improved lower bound in 11 dimensions from 592 to 593
- **Collaboration with Terence Tao**: Applied to 67 open problems (Nov 2025)

### Google Production
- **Borg scheduling**: Recovers ~0.7% of Google's worldwide compute (in production >1 year)
- **Gemini training**: 23% kernel speedup, 1% overall training time reduction
- **FlashAttention**: Up to 32.5% kernel speedup
- **TPU design**: Optimized Verilog for arithmetic circuits, integrated into upcoming TPU

## Paper

**"AlphaEvolve: A coding agent for scientific and algorithmic discovery"**
Alexander Novikov, Ngan Vu, Marvin Eisenberger, Emilien Dupont, Po-Sen Huang, Adam Zsolt Wagner, et al.
arXiv: [2506.13131](https://arxiv.org/abs/2506.13131) (June 2025)

Follow-up: **"Mathematical exploration and discovery at scale"** (with Terence Tao)
arXiv: [2511.02864](https://arxiv.org/abs/2511.02864) (November 2025)

## Repositories

| Repository | Description |
|---|---|
| [google-deepmind/alphaevolve_results](https://github.com/google-deepmind/alphaevolve_results) | Mathematical discoveries + verification code |
| [google-deepmind/alphaevolve_repository_of_problems](https://github.com/google-deepmind/alphaevolve_repository_of_problems) | 67 mathematical problem definitions |

**Note:** The AlphaEvolve system itself is not open-sourced. See [OpenEvolve](openevolve.md) for a community reimplementation.

## Key People

- Alexander Novikov (lead author)
- Matej Balog (core researcher, also FunSearch)
- Pushmeet Kohli (AI for Science lead)
- Terence Tao (Fields Medalist, external collaborator)

## See Also

- [FunSearch](funsearch.md) -- Direct predecessor
- [OpenEvolve](openevolve.md) -- Open-source reimplementation
- [ShinkaEvolve](shinkaevolve.md) -- Alternative approach by Sakana AI
