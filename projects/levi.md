# LEVI

**Organization:** Independent (Temoor Tanveer)
**Year:** 2026 (May)
**Status:** Open-sourced

## Overview

LEVI is a sample-efficient LLM-driven evolutionary search framework built on the explicit bet that **stronger search architectures can substitute for larger LLMs**. Where AlphaEvolve and similar systems compensate for poor diversity and uniform model use by spending more frontier-LLM dollars, LEVI redesigns the search loop around three components: a diversity-preserving solution database, a mutation router that mixes small and large LLMs, and a rank-preserving proxy benchmark for rollout-heavy settings.

## Architecture

```
┌────────────────────────────────────────────────────────┐
│                       LEVI Pipeline                      │
│                                                        │
│   ┌──────────────────┐                                 │
│   │  Solution         │                                 │
│   │  database with    │                                 │
│   │  baseline         │                                 │
│   │  diversity        │                                 │
│   │  (preserved       │                                 │
│   │   throughout      │                                 │
│   │   the run)        │                                 │
│   └────────┬─────────┘                                 │
│            │                                            │
│            ▼                                            │
│   ┌──────────────────────────────────┐                 │
│   │  Mutation router:                │                 │
│   │   - small LLM for local edits    │                 │
│   │   - large LLM for novel jumps    │                 │
│   └────────┬─────────────────────────┘                 │
│            │                                            │
│            ▼                                            │
│   ┌──────────────────────────────────┐                 │
│   │  Rank-preserving proxy           │                 │
│   │  benchmark (subset evaluation    │                 │
│   │  that preserves the ranking      │                 │
│   │  of the full benchmark)          │                 │
│   └──────────────────────────────────┘                 │
└────────────────────────────────────────────────────────┘
```

### Components

1. **Diversity-first database** -- Establishes diversity at initialization and maintains it throughout the run, rather than relying on stronger mutation models to compensate for archive collapse.

2. **Mutation router** -- Routes mutations to small vs large LLMs based on the kind of edit needed: small models handle local edits cheaply; frontier models are reserved for jumps requiring novel ideation.

3. **Rank-preserving proxy benchmarks** -- For rollout-heavy benchmarks (e.g. systems-research suites), LEVI evaluates on a proxy subset chosen to preserve ranking relative to the full benchmark, avoiding redundant rollouts on representative-but-correlated examples.

## Key Innovation

The paper argues that the cost of frontier-LLM-driven evolution is **largely an artifact of how existing frameworks allocate search**, not a fundamental requirement. By fixing diversity at the database level and routing edits by difficulty, LEVI achieves frontier-level scores with smaller models doing most of the work.

## Results

| Benchmark | LEVI vs. Frontier Baseline | Cost Reduction |
|---|---|---|
| Systems-research benchmarks | Highest score | **3.3-6.7x smaller budget** vs ShinkaEvolve, GEPA, AdaEvolve |
| One systems problem | Matches best | **35x lower cost** |
| Prompt optimization | Matches or exceeds GEPA | <50% rollout budget across 4 benchmarks |

## Paper

**"LEVI: Stronger Search Architectures Can Substitute for Larger LLMs in Evolutionary Search"**
Temoor Tanveer
arXiv: [2605.09764](https://arxiv.org/abs/2605.09764) (May 2026)

## Repository

[ttanv/levi](https://github.com/ttanv/levi)

## See Also

- [ShinkaEvolve](shinkaevolve.md) -- Concurrent sample-efficient framework (LEVI benchmarks against)
- [GEPA](gepa.md) -- Prompt-optimization baseline (LEVI matches at lower cost)
- [EvoX](evox.md) -- Concurrent meta-evolution approach with overlapping goals
- [AlphaEvolve](alphaevolve.md) -- Frontier-LLM baseline LEVI argues against
