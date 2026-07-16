# FAMOU

**Organization:** Baidu (and collaborators)
**Year:** 2026
**Status:** Open-sourced ([FAMOU-CoEvo](https://github.com/1xiangliu1/FAMOU-CoEvo))
**Venue:** arXiv

## Overview

FAMOU is a foundation-model code-evolution framework specialized for **adversarial multi-agent games**. It is built on the same paradigm as [OpenEvolve](openevolve.md) and [ShinkaEvolve](shinkaevolve.md) — an LLM iteratively mutates programs under a fitness signal — but adds three mechanisms to cope with a *shifting evaluation landscape*: in adversarial settings, as strategies improve, fixed evaluators become unreliable and evolution stagnates. FAMOU-evolved strategies won 1st place in the hardware round-robin of the AAMAS 2026 MCTF Competition.

## Key Innovation

The core problem FAMOU addresses is **non-stationary evaluation**: a strategy that scores well against a weak opponent pool may be poor against strong opponents, so a fixed fitness function misleads the search. FAMOU introduces three coupled mechanisms:

### 1. Evaluator Co-Evolution
Discovered champion strategies are folded back into the opponent pool, so the evaluation landscape tracks the improving population instead of a static baseline.

### 2. Hierarchical Deep Evaluation
Replaces noisy few-game score estimates with statistically reliable, multi-stage assessments — reducing the variance that otherwise stalls selection.

### 3. Weakness Pressure
Dynamically up-weights the hardest opponents a candidate faces, applying targeted selection pressure to break through performance plateaus.

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│                          FAMOU                            │
│                                                           │
│   ┌───────────┐    ┌───────────┐    ┌──────────────────┐  │
│   │  Program  │───>│    LLM    │───>│  Hierarchical    │  │
│   │  Sampler  │    │ (mutation)│    │  Deep Evaluation │  │
│   └───────────┘    └───────────┘    └────────┬─────────┘  │
│         ▲                                     │            │
│         │        ┌────────────────────┐       │            │
│         │        │  Opponent Pool     │<──────┘            │
│         │        │  + Weakness Pressure│  (co-evolved)     │
│         └────────│  + Champion inject  │                   │
│                  └────────────────────┘                   │
└──────────────────────────────────────────────────────────┘
```

## Results

- **MCTF 2026 3v3 maritime capture-the-flag:** Highest combined score (**0.526**) under two backbone LLMs, and best generalization to unseen opponents (**61.7% win rate**) — outperforming both OpenEvolve- and ShinkaEvolve-style baselines. Ablations confirm each of the three mechanisms contributes.
- **AAMAS 2026 MCTF Competition:** FAMOU-evolved strategy placed **1st in the hardware round-robin** and **3rd in simulation**, validating real-world transferability.
- **Emergent tactics:** The LLM mutation process produced tactical structures absent from the seed strategies — including lookahead search and adaptive interception — demonstrating that code-level evolution yields nontrivial algorithmic innovation in adversarial settings.

## Paper

**"Beyond Static Evaluation: Co-Evolutionary Mechanisms for LLM-Driven Strategy Evolution in Adversarial Games"**
Haoran Li, Zengle Ge, Ziyang Zhang, Xiaomin Yuan, Yui Lo, Qianhui Liu, Bocheng An, Dongke Rong, Jiaqun Liu, Annan Li, Jianmin Wu, Dawei Yin, Dou Shen
arXiv: [2606.10389](https://arxiv.org/abs/2606.10389) (June 2026)

## Repository

[1xiangliu1/FAMOU-CoEvo](https://github.com/1xiangliu1/FAMOU-CoEvo)

## See Also

- [OpenEvolve](openevolve.md) — Shared code-evolution foundation; a FAMOU baseline
- [ShinkaEvolve](shinkaevolve.md) — Shared paradigm; a FAMOU baseline (and ICFP 2025 competition winner)
- [Competitive Programming](../applications/competitive-programming.md) — Competition-winning evolved code, incl. FAMOU at AAMAS 2026
