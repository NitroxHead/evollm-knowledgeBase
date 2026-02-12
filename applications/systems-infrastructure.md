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

**Note:** The "Barbarians at the Gate" paper (arXiv:2510.06189) is particularly notable for demonstrating that OpenEvolve can achieve significant systems optimizations for < $10 in LLM API costs.
