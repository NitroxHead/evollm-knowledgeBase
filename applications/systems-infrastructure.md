# Applied Results: Systems & Infrastructure

Papers where LLM+evolution methods optimized real-world systems, data centers, and ML infrastructure.

---

## Google Borg Data Center Scheduling

**Problem:** Optimize machine ranking heuristic for job assignment in Google's Borg cluster management system.

| Metric | Result |
|---|---|
| Compute recovered | **0.7% of Google's worldwide compute** (~14,000 servers equivalent) |
| In production | **Over 1 year** |
| Target | "Stranded resources" -- machines with one exhausted resource while others remain available |

**Method:** AlphaEvolve
**Reference:** arXiv:2506.13131, 2025.

**Significance:** This is the most impactful production deployment of LLM+evolution to date.

---

## Expert Parallelism Load Balancing (EPLB) for MoE Models

**Problem:** Balance load across experts in Mixture-of-Experts models.

| Metric | Result | Cost |
|---|---|---|
| Initial speedup | 5x | < $10, ~5 hours |
| Final speedup | **13x** | with Gemini 2.5 Flash |
| Technique discovered | Vectorized tensor ops + zig-zag partitioning | -- |

**Paper:** Cheng, Liu, Pan, Li et al. (UC Berkeley, 20+ authors including Koushik Sen, Matei Zaharia, Ion Stoica), "Barbarians at the Gate: How AI is Upending Systems Research," arXiv:2510.06189, 2025.

**Method:** OpenEvolve (open-source AlphaEvolve)

---

## LLM-based SQL Query Optimization

**Problem:** Optimize relational analytics queries using LLM inference.

| Metric | Result |
|---|---|
| Speedup | **3x** for relational analytics with LLM inference |

**Paper:** Same "Barbarians at the Gate" paper (arXiv:2510.06189)
**Method:** OpenEvolve

---

## Multi-Region Cloud Scheduling

**Problem:** Reduce costs in multi-region cloud deployments.

| Metric | Result |
|---|---|
| Cost reduction | **Up to 50%** |

**Paper:** Same "Barbarians at the Gate" paper (arXiv:2510.06189)
**Method:** OpenEvolve

---

## Gemini Training Pipeline

**Problem:** Optimize matrix multiplication tiling for Gemini's training pipeline.

| Metric | Result |
|---|---|
| Kernel speedup | **23%** |
| Overall training time | **1% reduction** |

**Method:** AlphaEvolve
**Reference:** arXiv:2506.13131

---

## FlashAttention Kernel

**Problem:** Optimize FlashAttention implementation in Transformers.

| Component | Speedup |
|---|---|
| Main kernel | 32% |
| Pre/post processing | 15% |
| **Total** | **Up to 32.5%** |

AlphaEvolve modified compiler-generated IR code.

**Method:** AlphaEvolve
**Reference:** arXiv:2506.13131

---

## Cache Replacement Policies (ArchAgent)

**Problem:** Design new state-of-the-art cache replacement policies (not just parameter tuning -- new mechanisms and logic).

| Workload | Time Budget | Improvement over Prior SoTA | Note |
|---|---|---|---|
| Public multi-core Google Workload Traces | 2 days, no human intervention | **5.3% IPC speedup** | New mechanism architected automatically |
| SPEC06 (single-core, heavily explored) | 18 days | **0.9% IPC speedup** | Comparable "winning margin" to prior SoTA, achieved 3-5x faster |
| SPEC06 with post-silicon hyperspecialization | -- | **2.4% IPC speedup** | Runtime parameter tuning by agent |

**Method:** ArchAgent, built on AlphaEvolve.

**Notable side finding:** The agent discovered and exploited a loophole in a popular microarchitectural simulator ("simulator escape") -- a consequence of these tools having been designed for human researchers acting in good faith.

**Paper:** Gupta, Jain, Gonzalez, Novikov, Huang, Balog, Eisenberger, Shirobokov, Vũ, Dixon, Nikolić, Ranganathan, Karandikar, "ArchAgent: Agentic AI-driven Computer Architecture Discovery," arXiv:[2602.22425](https://arxiv.org/abs/2602.22425), 2026.

---

## Radar Resource Allocation for Multi-Target Tracking

**Problem:** Real-time power allocation in radar systems for multi-target tracking.

| Metric | Result |
|---|---|
| Tracking accuracy | Average relative loss only **1.51%** vs iterative optimal solver |
| Speedup | **Over three orders of magnitude** vs conventional iterative solvers |
| Form | Closed-form, interpretable scoring function |

**Method:** AlphaEvolve evolves a compact symbolic scoring function over physically inspired features, with a deterministic constraint-satisfying transformation.

**Paper:** Hou, Pu, Yan, Zhou, Liu, "Discover Fast Power Allocation Solution for Multi-Target Tracking via AlphaEvolve Evolution," arXiv:[2605.01794](https://arxiv.org/abs/2605.01794), 2026.

---

## TPU Hardware Design

**Problem:** Optimize Verilog arithmetic circuits for TPU matrix multiplication units.

| Result | Impact |
|---|---|
| Removed unnecessary bits | Reduced area and power consumption |
| Verified functionally correct | Integrated into upcoming TPU design |

**Significance:** First direct AI contribution to production TPU hardware.

**Method:** AlphaEvolve
**Reference:** arXiv:2506.13131

---

## Summary

| System | Method | Impact | Status |
|---|---|---|---|
| Google Borg | AlphaEvolve | 0.7% global compute | Production (1+ year) |
| EPLB load balancing | OpenEvolve | 13x speedup | Research |
| SQL optimization | OpenEvolve | 3x speedup | Research |
| Cloud scheduling | OpenEvolve | 50% cost reduction | Research |
| Gemini training | AlphaEvolve | 1% training reduction | Production |
| FlashAttention | AlphaEvolve | 32.5% speedup | Verified |
| TPU design | AlphaEvolve | Area/power reduction | In upcoming TPU |
| Cache replacement (ArchAgent) | AlphaEvolve | 5.3% IPC speedup | Research |
| Radar power allocation | AlphaEvolve | 1000x speedup, near-optimal | Research |
| Enterprise Java hotspots | CodeEvolve (Salesforce) | 15.22x speedup avg | Research |

**Note:** The "Barbarians at the Gate" paper (arXiv:2510.06189) is particularly notable for demonstrating that OpenEvolve can achieve significant systems optimizations for < $10 in LLM API costs.
