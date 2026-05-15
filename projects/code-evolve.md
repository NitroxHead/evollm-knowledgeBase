# CodeEvolve (Salesforce)

**Organization:** Salesforce AI Research
**Year:** 2026 (May)
**Status:** Research preprint

> **Disambiguation:** The name "CodeEvolve" has been used for at least two distinct systems. This page covers the Salesforce framework for multi-language enterprise code optimization (arXiv:2605.04677). A separate but unrelated CodeEvolve (arXiv:2510.14150) was used to set a new bound on the second autocorrelation inequality and is referenced in [applications/mathematics.md](../applications/mathematics.md).

## Overview

CodeEvolve is an LLM-driven evolutionary code-optimization framework that extends [OpenEvolve](openevolve.md) with runtime-profile-guided target selection, Monte Carlo Tree Search (MCTS) over candidate edits, and language-specific evaluation pipelines. It is designed for enterprise codebases in **Java** and **Salesforce Apex**, addressing two practical gaps in AlphaEvolve-style systems: identifying which functions are actually worth optimizing in a large codebase, and validating optimized code against domain-specific compilation, test, and review pipelines.

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│                  CodeEvolve Pipeline                       │
│                                                          │
│   ┌─────────────────────┐                                │
│   │  JFR profile of     │                                │
│   │  running app        │                                │
│   └─────────┬──────────┘                                │
│             │                                            │
│             ▼                                            │
│   ┌─────────────────────┐    ┌────────────────────┐     │
│   │  Weighted component │───>│  Target selection    │     │
│   │  graph (call &       │    │  (functions with    │     │
│   │   cost-weighted)    │    │   highest exec cost) │     │
│   └─────────────────────┘    └─────────┬──────────┘     │
│                                         │                 │
│                                         ▼                 │
│   ┌─────────────────────────────────────────────────┐   │
│   │  MCTS-augmented LLM mutation                      │   │
│   │  (extends OpenEvolve's evolutionary search)       │   │
│   └────────┬────────────────────────────────────────┘   │
│            │                                              │
│            ▼                                              │
│   ┌─────────────────────────────────────────────────┐   │
│   │  Validation gate:                                 │   │
│   │   - Build                                         │   │
│   │   - Unit tests                                    │   │
│   │   - Perf checks                                   │   │
│   │   - Static analysis                               │   │
│   │   - LLM-based review                              │   │
│   └─────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────┘
```

### Components

1. **Runtime-guided target selection** -- Builds a weighted component graph from Java Flight Recorder (JFR) profiles, then selects optimization targets that account for the majority of execution cost. Removes the manual bottleneck-identification step typical in AlphaEvolve-style systems.

2. **MCTS-augmented evolution** -- Extends OpenEvolve's evolutionary loop with Monte Carlo Tree Search to explore candidate edits more systematically.

3. **Language-specific evaluation pipelines** -- For each candidate, runs build validation, unit tests, performance checks, static analysis, and LLM-based review tailored to Java and Salesforce Apex.

4. **Correctness preservation** -- Only retains variants that pass all functional-correctness checks.

## Key Innovation

Most LLM+evolution code-optimization work targets carefully framed single-function problems (FunSearch, AlphaEvolve math/algorithms). CodeEvolve targets **large enterprise codebases** where the dominant practical difficulty is locating which functions are worth optimizing and verifying that changes preserve correctness across realistic test surfaces.

## Results

| Setting | Result |
|---|---|
| Enterprise Java codebase, 7 hotspot functions | **Average 15.22x speedup** |
| Single-pass LLM optimization comparison | Outperforms it on 5 of 7 hotspots |
| Apex optimization, MCTS-full configuration | **19.5 / 20 valid programs** on average |

The ablation confirms that all three additions on top of OpenEvolve (search, filtering, refinement) contribute to reliability.

## Paper

**"CodeEvolve: LLM-Driven Evolutionary Optimization with Runtime-Enriched Target Selection for Multi-Language Code Enhancement"**
Ajay Krishna Borra, Wenzhuo Yang, Samarth Arora, Akhilesh Deepak Gotmare, Gokulakrishnan Gopalakrishnan, Tharun Gali, Madhav Rathi, Doyen Sahoo, Manpreet Singh, Mayuresh Verma, Laksh Venka, Shuchita Singh
arXiv: [2605.04677](https://arxiv.org/abs/2605.04677) (May 2026)

## See Also

- [OpenEvolve](openevolve.md) -- Base framework that CodeEvolve extends
- [AlphaEvolve](alphaevolve.md) -- Higher-level inspiration
- [applications/systems-infrastructure.md](../applications/systems-infrastructure.md) -- Other applied code-optimization results
