# EvoX

**Organization:** UC Berkeley (Sky Lab) / UT Austin
**Year:** 2026 (February)
**Status:** Research preprint

## Overview

EvoX is a meta-evolutionary framework that **jointly evolves candidate solutions and the search strategy used to generate them**. Where AlphaEvolve, OpenEvolve, ShinkaEvolve, and GEPA all rely on a fixed search strategy with predefined knobs (explore/exploit ratios, parent-selection rules, mutation operators), EvoX continuously adapts those knobs based on observed progress. Across nearly 200 real-world optimization tasks, EvoX outperforms AlphaEvolve, OpenEvolve, GEPA, and ShinkaEvolve on the majority of tasks.

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    EvoX Meta-Loop                         │
│                                                          │
│   ┌─────────────────┐     ┌─────────────────┐           │
│   │  Solution         │     │  Strategy        │           │
│   │  Population       │<───>│  Population      │           │
│   │  (candidate code, │     │  (selection +    │           │
│   │   prompts, etc.)  │     │   variation      │           │
│   │                   │     │   policies)      │           │
│   └─────────┬─────────┘     └──────┬──────────┘           │
│             │                       │                       │
│             ▼                       ▼                       │
│   ┌──────────────────────────────────────────┐           │
│   │  Joint evaluation: which strategy        │           │
│   │  generated improvement on which kind     │           │
│   │  of subproblem?                          │           │
│   └──────────────────────────────────────────┘           │
│             │                                              │
│             └──> Update both populations                  │
└─────────────────────────────────────────────────────────┘
```

### Components

1. **Solution population** -- Candidate programs/prompts/algorithms under evolution.

2. **Strategy population** -- Search strategies (how to select parents, how to vary them, exploration weights) that are themselves evolved.

3. **Joint update** -- Each generation, the credit for improvements is attributed to the strategy that produced them; successful strategies are reinforced while poor ones are replaced.

4. **Dynamic shifting** -- The system can shift between qualitatively different search modes within a single run as the search landscape changes.

## Key Innovation

Existing LLM-evolution frameworks use **static search hyperparameters**. EvoX treats those hyperparameters as a second, smaller evolved population, letting the system self-tune as the search progresses. This addresses the well-documented failure mode where a single fixed strategy is effective in some regimes but fails as the problem changes (e.g. early diversity-seeking vs late exploitation, or shifts in fitness-landscape ruggedness).

## Results

- **~200 real-world optimization tasks evaluated**
- **Outperforms AlphaEvolve, OpenEvolve, GEPA, and ShinkaEvolve on the majority of tasks**
- Domains span code optimization, prompt optimization, and algorithm design

## Paper

**"EvoX: Meta-Evolution for Automated Discovery"**
Shu Liu, Shubham Agarwal, Monishwaran Maheswaran, Mert Cemri, Zhifei Li, Qiuyang Mang, Ashwin Naren, Ethan Boneh, Audrey Cheng, Melissa Z. Pan, Alexander Du, Kurt Keutzer, Alvin Cheung, Alexandros G. Dimakis, Koushik Sen, Matei Zaharia, Ion Stoica
arXiv: [2602.23413](https://arxiv.org/abs/2602.23413) (February 2026)

## Key People

- UC Berkeley Sky Lab (Matei Zaharia, Ion Stoica, Alvin Cheung, Koushik Sen, Kurt Keutzer)
- UT Austin (Alexandros G. Dimakis)
- Same Berkeley group behind GEPA and the "Barbarians at the Gate" systems research

## See Also

- [AlphaEvolve](alphaevolve.md) -- One of the systems EvoX dominates
- [OpenEvolve](openevolve.md) -- Another baseline EvoX dominates
- [ShinkaEvolve](shinkaevolve.md) -- Sample-efficient baseline EvoX dominates
- [GEPA](gepa.md) -- Prompt-optimization baseline EvoX dominates
- [LEVI](levi.md) -- Concurrent sample-efficient framework with overlapping goals
- [Promptbreeder](promptbreeder.md) -- Earlier work on evolving evolutionary operators
