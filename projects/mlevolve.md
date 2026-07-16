# MLEvolve

**Organization:** Shanghai Artificial Intelligence Laboratory / East China Normal University
**Year:** 2026
**Status:** Open-sourced ([InternScience/MLEvolve](https://github.com/InternScience/MLEvolve))
**Venue:** arXiv

## Overview

MLEvolve is an LLM-based self-evolving multi-agent framework for end-to-end machine learning engineering (MLE) and algorithm discovery. It targets three failure modes of prior MLE agents on long-horizon tasks: inter-branch information isolation, memoryless search, and lack of hierarchical control. On MLE-Bench it sets a new state of the art while running in half the standard time budget, and it generalizes to outperform AlphaEvolve on mathematical optimization tasks.

## Architecture

```
┌───────────────────────────────────────────────────────────────┐
│                          MLEvolve                              │
│                                                                │
│   ┌──────────────────────────────────────────────────────┐    │
│   │  Progressive MCGS (graph-structured search)          │    │
│   │   • primary edges (parent→child, credit assignment)  │    │
│   │   • reference edges (cross-branch information flow)  │    │
│   │   • entropy-inspired schedule: explore → exploit     │    │
│   │   • UCT ⇄ Elite-guided soft switch                   │    │
│   └──────────────────────────────────────────────────────┘    │
│                    ▲                       │                    │
│   ┌────────────────┴─────────┐   ┌─────────▼───────────────┐   │
│   │  Retrospective Memory    │   │  Hierarchical Planning  │   │
│   │   • domain knowledge base│   │   Planner (what/why)    │   │
│   │     (cold-start)         │   │   Coder (how)           │   │
│   │   • dynamic global memory│   │   Adaptive modes:       │   │
│   │     (RRF hybrid retrieval)│  │   base / stepwise / diff│   │
│   └──────────────────────────┘   └─────────────────────────┘   │
└───────────────────────────────────────────────────────────────┘
```

## Key Innovations

### 1. Progressive Monte Carlo Graph Search (MCGS)
Extends MCTS with a directed graph. **Primary edges** preserve parent–child order and carry credit assignment (backpropagation); **reference edges** connect nodes across branches and non-adjacent levels, enabling cross-branch knowledge flow, trajectory reuse, and multi-branch aggregation. Four expansion types (primary, intra-branch evolution, cross-branch reference, multi-branch aggregation) are triggered by branch- and global-level stagnation detection. When there are no reference edges, the search reduces to standard MCTS.

### 2. Entropy-Inspired Progressive Exploration Schedule
A time-dependent soft switch between UCT-based exploration (high entropy) and Elite-guided exploitation (low entropy) gradually concentrates compute on promising branches as the run progresses — critical under a fixed wall-clock budget.

### 3. Retrospective Memory
Pairs a curated **domain knowledge base** (cold-start priors per task type) with a **dynamic global memory** that automatically accumulates structured records (plan, outcome, analysis, feedback) and retrieves them via Reciprocal Rank Fusion over lexical + FAISS semantic search — no extra LLM calls for reflection. Stage-aware retrieval serves the planning and debugging stages differently.

### 4. Hierarchical Planning with Adaptive Code Generation
Decouples a module-level **Planner** (*what* to modify and *why*) from a **Coder** (*how* to implement it), which selects among **base** (full rewrite), **stepwise** (module-by-module), and **diff** (targeted edits) modes based on the current search state.

## Results

- **MLE-Bench (75 Kaggle tasks):** 65.3% average medal rate under a 12-hour budget (half the standard 24h), state of the art across all reported methods. 100% valid-submission rate, 76.0% above-median rate, 34.7% gold-medal rate. Backbone: Gemini-3.1-Pro-preview.
- **Cross-domain generalization:** Outperforms specialized algorithm-discovery methods including [AlphaEvolve](alphaevolve.md) and AlphaEvolve-v2 on 15 open-ended mathematical optimization tasks drawn from the AlphaEvolve suite.

## Paper

**"MLEvolve: A Self-Evolving Framework for Automated Machine Learning Algorithm Discovery"**
Shangheng Du, Xiangchao Yan, Jinxin Shi, Zongsheng Cao, Shiyang Feng, Zichen Liang, Boyuan Sun, Tianshuo Peng, Yifan Zhou, Xin Li, Jie Zhou, Liang He, Bo Zhang, Lei Bai
arXiv: [2606.06473](https://arxiv.org/abs/2606.06473) (June 2026)

## Repository

[InternScience/MLEvolve](https://github.com/InternScience/MLEvolve)

## Key People

- **Lei Bai**, **Bo Zhang**, **Xiangchao Yan** — Shanghai AI Laboratory (corresponding authors)

## See Also

- [AlphaEvolve](alphaevolve.md) — Beaten on the mathematical optimization subset; source of those tasks
- [ShinkaEvolve](shinkaevolve.md) — Sample-efficient program evolution with adaptive sampling
- [Darwin Godel Machine](darwin-godel-machine.md) — Self-improving agent code via MAP-Elites
- [Neural Architecture Search](../applications/neural-architecture-search.md) — Related MLE / model-design applications
