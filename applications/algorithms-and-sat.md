# Applied Results: Algorithms & SAT Solving

Papers where LLM+evolution methods discovered or optimized algorithms and solvers.

---

## MAX-4-CUT Inapproximability (Complexity Theory)

**Problem:** Establish inapproximability bounds for MAX-4-CUT.

| Previous Best | New Result | Method | Reference |
|---|---|---|---|
| 0.9883 inapproximability | **0.987** | AlphaEvolve | arXiv:2509.18057 |

AlphaEvolve discovered a complex 19-variable gadget that established the new bound. Also achieved a **10,000x speedup** in the verification process.

**Paper:** Nagda, Raghavan, Thakurta, "Reinforced Generation of Combinatorial Structures: Applications to Complexity Theory," arXiv:2509.18057, 2025.

---

## SATLUTION: Evolving SAT Solvers

**Problem:** Optimize Boolean Satisfiability (SAT) solvers.

| Metric | Result |
|---|---|
| Performance | Outperforms both 2024 and 2025 SAT Competition human-designed winners |
| Code evolved | 10,000+ lines across hundreds of files |
| Cost | < $20,000 |

**Discovered techniques:**
- Multi-UIP clause learning
- Bandit-tuned heuristics
- Adaptive vivification
- Compressed watchlist data structures
- Static symmetry breaking

**Paper:** NVIDIA researchers, "Autonomous Code Evolution Meets NP-Completeness," arXiv:2509.07367, 2025.

**Method:** SATLUTION -- LLM-based repository-scale code evolution

---

## AutoModSAT: Modular SAT Solver Heuristics

**Problem:** Optimize CDCL SAT solver heuristics via modularization.

| Metric | Result |
|---|---|
| vs baseline solver | **50% improvement** |
| vs SOTA solvers | **30% superiority** |
| vs parameter-tuned SOTA | **20% speedup** |

**Paper:** "Automatically discovering heuristics in a complex SAT solver with large language models," arXiv:2507.22876, 2025.

**Method:** AutoModSAT -- LLM + (1+lambda) EA for modular heuristic discovery

---

## Multi-Agent Reinforcement Learning Algorithms

**Problem:** Discover new algorithms for imperfect-information games -- counterfactual regret minimization (CFR) and policy-space response oracles (PSRO).

| Algorithm Discovered | Family | Status |
|---|---|---|
| **VAD-CFR** (Volatility-Adaptive Discounted CFR) | CFR | Competitive with SOTA across 18 games |
| **SHOR-PSRO** (Smoothed Hybrid Optimistic Regret PSRO) | PSRO | Competitive with SOTA across 18 games |
| **WOP-CFR** (Warm-started Optimistic Predictive CFR) | Distilled minimal solver | **Superior generalization with reduced complexity** |
| **PM-PSRO** (Projection Matching PSRO) | Distilled minimal solver | **Superior generalization with reduced complexity** |

**Evaluation suite:** 18 games -- Poker, Goofspiel, Liar's Dice, Blotto, Battleship variants.

**Method:** AlphaEvolve searched the algorithmic design space; the authors then distilled the LLM's discoveries to their fundamental algorithmic cores, producing minimal solvers with better generalization.

**Paper:** Li, Schultz, Hennes, Lanctot, "Discovering Multiagent Learning Algorithms with Large Language Models," arXiv:[2602.16928](https://arxiv.org/abs/2602.16928), 2026.

---

## Code-Space Response Oracles (Interpretable MARL Policies)

**Problem:** Replace black-box neural-net response oracles in PSRO with executable code policies.

| Approach | Result |
|---|---|
| CSRO with AlphaEvolve as the oracle | Competitive with neural-net baselines |
| Output | Human-readable, interpretable code policies |

**Paper:** Hennes, Li, Schultz, Lanctot, "Code-Space Response Oracles: Generating Interpretable Multi-Agent Policies with Large Language Models," arXiv:[2603.10098](https://arxiv.org/abs/2603.10098), 2026.

---

## Lexical Retrieval Algorithm Discovery (RankEvolve)

**Problem:** Improve first-stage lexical retrieval algorithms (BM25, query likelihood with Dirichlet smoothing) -- previously progressed only via parameter tuning and human intuition.

| Benchmark | Result |
|---|---|
| 12 IR datasets (BEIR + BRIGHT) | Evolved algorithms outperform seeds (BM25 / QL+Dirichlet) |
| Transfer to TREC DL 19, DL 20 | Strong transfer |

**Method:** RankEvolve, built on AlphaEvolve. Candidate ranking algorithms represented as executable code, iteratively mutated/recombined based on retrieval-quality fitness.

**Paper:** Nian, Li, Park, Fang, "RankEvolve: Automating the Discovery of Retrieval Algorithms via LLM-Driven Evolution," arXiv:[2602.16932](https://arxiv.org/abs/2602.16932), 2026.

---

## Tensor Network Contraction Order (OpenEvolve)

**Problem:** Optimize the contraction ordering for tensor networks -- an NP-hard problem central to quantum simulation and many-body physics.

| Aspect | Finding |
|---|---|
| Method | Verifier-guided evolutionary coding via [OpenEvolve](../projects/openevolve.md) |
| Case study focus | Sensitivity to LLM choice, evaluation metric, and test-instance selection |
| Takeaway | Demonstrates the promise of evolutionary coding agents for algorithm development while underscoring that evaluation, validation, and human interpretation remain the bottleneck |

**Paper:** Hoppe, Röhrig-Zöllner, Knechtges, "Algorithmic algorithm development with LLMs: A Case Study on LLM-Usage for Contraction Order Optimization in Tensor Networks," arXiv:[2606.01975](https://arxiv.org/abs/2606.01975), 2026.

---

## FlashAttention Kernel Optimization

**Problem:** Optimize the FlashAttention kernel implementation in Transformer models.

| Component | Speedup | Method |
|---|---|---|
| Main kernel | 32% | AlphaEvolve |
| Pre/post processing | 15% | AlphaEvolve |
| **Total** | **Up to 32.5%** | AlphaEvolve |

AlphaEvolve modified compiler-generated IR code to achieve these speedups.

**Reference:** AlphaEvolve paper, arXiv:2506.13131, 2025.

---

## Gemini Training Kernel

**Problem:** Optimize matrix multiplication tiling heuristic for Gemini's training pipeline.

| Metric | Result |
|---|---|
| Kernel speedup | **23%** |
| Overall training time reduction | **1%** |

**Reference:** AlphaEvolve paper, arXiv:2506.13131, 2025.

---

## TPU Arithmetic Circuit Design

**Problem:** Optimize Verilog arithmetic circuits for TPU matrix multiplication units.

| Result | Impact |
|---|---|
| Removed unnecessary bits in arithmetic circuit | Reduced area and power |
| Verified functionally correct | Integrated into upcoming TPU design |

**Significance:** First time Gemini directly contributed to TPU hardware design.

**Reference:** AlphaEvolve paper, arXiv:2506.13131, 2025.

---

## Domain-Independent Heuristics for Symbolic AI Planning

**Problem:** Heuristic search is the dominant paradigm in symbolic AI planning, and the strongest heuristics are the product of decades of expert work. Prior LLM work produced heuristics for *individual* domains only -- none worked on arbitrary planning tasks.

**Approach:** An LLM mutates parent heuristics written in **C++**; candidates are stored in a **MAP-Elites archive** keyed on informedness and speed, with fitness blending coverage and solving time. The evolved programs are plain C++ that slot into existing planners as drop-in replacements, inheriting soundness/completeness guarantees.

| Result | Detail |
|---|---|
| First LLM-generated **domain-independent** heuristics to exceed the hand-engineered SOTA | On unseen test domains, the best evolved heuristic solves more tasks than the strongest baseline |
| Pareto frontier | Full evolved suite spans the informedness-speed tradeoff |
| Notable finding | Seeding from the *trivial blind* heuristic outperforms seeding from the strong FF heuristic; LLM reasoning effort affects compile rate more than quality of compiling candidates |

**Paper:** Gestrin, Seipp, "LLM-Evolved Domain-Independent Heuristics for Symbolic AI Planning," arXiv:[2605.29649](https://arxiv.org/abs/2605.29649), 2026.

---

## Summary

| Problem | Method | Key Achievement |
|---|---|---|
| MAX-4-CUT | AlphaEvolve | New inapproximability bound + 10,000x verification speedup |
| SAT solving | SATLUTION | Outperformed competition winners, 10K+ lines evolved |
| SAT heuristics | AutoModSAT | 50% improvement over baseline |
| FlashAttention | AlphaEvolve | 32.5% kernel speedup |
| Gemini training | AlphaEvolve | 23% kernel speedup, 1% total training reduction |
| TPU design | AlphaEvolve | Optimized circuits in production hardware |
| MARL (CFR/PSRO) | AlphaEvolve | 4 new algorithms competitive with SOTA, 2 distilled minimal solvers |
| Lexical IR | RankEvolve | New ranking algorithms outperforming BM25 on BEIR/BRIGHT |
| Symbolic AI planning | MAP-Elites + LLM (C++) | First domain-independent heuristics beating hand-engineered SOTA |
