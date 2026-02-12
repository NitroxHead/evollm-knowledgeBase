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

## Summary

| Problem | Method | Key Achievement |
|---|---|---|
| MAX-4-CUT | AlphaEvolve | New inapproximability bound + 10,000x verification speedup |
| SAT solving | SATLUTION | Outperformed competition winners, 10K+ lines evolved |
| SAT heuristics | AutoModSAT | 50% improvement over baseline |
| FlashAttention | AlphaEvolve | 32.5% kernel speedup |
| Gemini training | AlphaEvolve | 23% kernel speedup, 1% total training reduction |
| TPU design | AlphaEvolve | Optimized circuits in production hardware |
