# Applied Results: Competitive Programming

Papers where LLM+evolution methods achieved results in programming contests and benchmarks.

---

## ICFP 2025 Programming Contest -- 1st Place

**Problem:** Maze navigation/mapping with ambiguous hints.

| Metric | Result |
|---|---|
| Placement | **1st place** |
| Team | Team Unagi (including Sakana AI's Takuya Akiba) |
| Role of evolution | Evolved efficient auxiliary variables for SAT solver encoding |
| Speedup (mid-scale) | From 2.86s to 0.44s (~6.5x) |
| Speedup (large-scale) | From 127s to 13s (~10x) |

ShinkaEvolve optimized the Rust code of their SAT encoding, enabling solutions to large-scale problems that were previously intractable.

**Method:** ShinkaEvolve
**Reference:** [Sakana AI blog](https://sakana.ai/icfp-2025/), arXiv:2509.19349

---

## Google Hash Code -- Surpassed Top Human Score

**Problem:** Data center optimization challenge from Google Hash Code competition.

| Metric | Result |
|---|---|
| EvoTune score | **418** |
| Top human score | 407 |

**Method:** EvoTune (evolutionary search + RL fine-tuning of LLM)

**Paper:** "Algorithm Discovery With LLMs: Evolutionary Search Meets Reinforcement Learning," arXiv:2504.05108, COLM 2025.

---

## AtCoder Heuristic Contest (ALE-Bench)

**Problem:** AtCoder competitive programming problems.

| Metric | Result |
|---|---|
| Average improvement | **2.3%** on public scores |
| AHC015 specifically | Score improved from 762,641 to **817,371** |
| Ranking impact | Would have achieved **2nd place** in actual competition for one task |

**Method:** ShinkaEvolve
**Reference:** arXiv:2509.19349

---

## AIME Math Reasoning

**Problem:** AIME (American Invitational Mathematics Examination) 2024 problems.

| Metric | Result |
|---|---|
| Architecture evolved | Three-stage system (diverse expert personas, critical peer review, synthesis) |
| Generations | 75 |
| Generalization | Works on unseen problems |

**Method:** ShinkaEvolve
**Reference:** arXiv:2509.19349

---

## SWE-bench (Self-Improving Agents)

**Problem:** Solve real-world software engineering tasks from GitHub issues.

| Metric | Before | After |
|---|---|---|
| Success rate | 20.0% | **50.0%** |

**Method:** Darwin Godel Machine (self-modification of agent code)
**Reference:** arXiv:2505.22954

---

## Polyglot Benchmark (Self-Improving Agents)

**Problem:** Multi-language programming tasks.

| Metric | Before | After |
|---|---|---|
| Success rate | 14.2% | **30.7%** |

**Method:** Darwin Godel Machine
**Reference:** arXiv:2505.22954

---

## AlphaEvolve Benchmarks (CodeEvolve)

**Problem:** Reproduce and surpass AlphaEvolve results using open-source methods.

| Problem | AlphaEvolve | CodeEvolve | Winner |
|---|---|---|---|
| Second autocorrelation (P1) | 0.89627 | **0.93768** | CodeEvolve |
| Distance minimization (P2.A) | -- | **Improved** | CodeEvolve |
| Distance minimization (P2.B) | -- | **Improved** | CodeEvolve |
| Circle packing (P3.A) | -- | **Improved** | CodeEvolve |
| Circle packing (P3.B) | -- | **Improved** | CodeEvolve |
| Circle packing in rectangle (P4) | Matched | Matched | Tie |

**Result:** CodeEvolve surpassed AlphaEvolve on **5 of 6 benchmarks** using open-weight models at a fraction of the compute cost.

**Paper:** Assumpcao et al., "CodeEvolve: an open source evolutionary coding agent," arXiv:2510.14150, 2025.

---

## AAMAS 2026 MCTF Competition -- 1st Place (Hardware)

**Problem:** 3v3 maritime capture-the-flag (MCTF), an adversarial multi-agent game with a shifting evaluation landscape.

| Metric | Result |
|---|---|
| Hardware round-robin | **1st place** |
| Simulation round | 3rd place |
| Combined score (MCTF 2026 benchmark) | **0.526** (best of all methods) |
| Generalization to unseen opponents | **61.7% win rate** |
| Emergent tactics | Lookahead search, adaptive interception (absent from seed strategies) |

FAMOU adds evaluator co-evolution, hierarchical deep evaluation, and weakness pressure to the OpenEvolve/ShinkaEvolve code-evolution paradigm, outperforming both as baselines.

**Method:** [FAMOU](../projects/famou.md)
**Paper:** Li et al., "Beyond Static Evaluation: Co-Evolutionary Mechanisms for LLM-Driven Strategy Evolution in Adversarial Games," arXiv:[2606.10389](https://arxiv.org/abs/2606.10389), 2026.

---

## Summary

| Contest/Benchmark | Method | Achievement |
|---|---|---|
| ICFP 2025 | ShinkaEvolve | 1st place, 10x speedup |
| AAMAS 2026 MCTF | FAMOU | 1st place (hardware), adversarial-game code evolution |
| Google Hash Code | EvoTune | Beat top human score (418 vs 407) |
| AtCoder (ALE-Bench) | ShinkaEvolve | Would achieve 2nd place |
| AIME 2024 | ShinkaEvolve | Evolved effective reasoning architecture |
| SWE-bench | Darwin Godel Machine | 20% → 50% success rate |
| Polyglot | Darwin Godel Machine | 14.2% → 30.7% |
| AlphaEvolve benchmarks | CodeEvolve | Beat AlphaEvolve on 5/6 tasks |
