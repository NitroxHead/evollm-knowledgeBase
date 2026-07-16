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

## Chip Macro Placement Ordering (OrderPlace)

**Problem:** Discover macro *placement-order* strategies for chip physical design -- the temporal sequencing of placement, previously governed by static hand-crafted heuristics (area- or connectivity-based), while ML has focused only on spatial coordinates.

| Metric | Result |
|---|---|
| Wirelength reduction vs WireMask-EA | **34.04%** |
| Wirelength reduction vs SOTA EGPlace | **14.08%** |
| Benchmark | ISPD 2005 |
| Efficiency trick | Lightweight deterministic greedy "proxy probe" filters candidate orderings cheaply |

**Method:** OrderPlace -- proxy-guided LLM evolution over code-level ordering policies (static scoring metrics through dynamic physics-inspired mechanisms).

**Paper:** Mo, Liu, Xu, Wu, "Order Matters: Unveiling the Hidden Impact of Macro Placement Sequences via Proxy-Guided LLM Evolution," arXiv:[2606.08904](https://arxiv.org/abs/2606.08904), 2026.

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

## GPU Kernel Optimization (Kernel Foundry)

**Problem:** Generate GPU kernels that are simultaneously **correct** and **hardware-efficient** -- LLMs alone often produce one or the other.

**Approach:** Kernel Foundry is a diagnosis-driven evolutionary framework combining expert-guided, retrieval-augmented initialization with **multi-island** evolutionary search. Candidate kernels are refined via structured diagnostic feedback; a centralized experience library accumulates reusable optimization knowledge, with explicit anti-cheating mechanisms that prevent bypassing kernel-level computation.

| Benchmark | Result |
|---|---|
| KernelBench | Consistently improves correctness and performance over strong baselines; **up to 100% correctness on Level 2** |

**Paper:** Huang, Chen, Huang, Yin, Li, Zhen, Yuan, Shao, "Kernel Foundry: A Diagnosis-driven Evolutionary Kernel Optimizer with Multi-Experts," arXiv:[2605.30359](https://arxiv.org/abs/2605.30359), 2026.

---

## Logic Synthesis Technology Mapping (MappingEvolve)

**Problem:** Technology mapping is a critical, difficult logic-synthesis stage. Prior LLM work generated optimization *scripts* but left the core mapping algorithm untouched.

**Approach:** MappingEvolve directly **evolves the technology-mapping code**, abstracting the process into optimization operators and using a hierarchical agent architecture (Planner / Evolver / Evaluator) to guide the search.

| Metric | Result |
|---|---|
| Area reduction vs ABC | **10.04%** |
| Area reduction vs mockturtle | **7.93%** |
| Overall improvement on EPFL benchmarks | **46.6%–96.0%** S_overall, while navigating the area–delay tradeoff |

**Paper:** Fu, Liu, Xu, Ho, "MappingEvolve: LLM-Driven Code Evolution for Technology Mapping," arXiv:[2604.26591](https://arxiv.org/abs/2604.26591), 2026. Repository: [Flians/MappingEvolve](https://github.com/Flians/MappingEvolve).

---

## Approximate Circuit Design (Prompt-Circuit Co-Evolution)

**Problem:** Design 8-bit **approximate multipliers** that trade accuracy for power/area/latency -- valuable for error-resilient workloads such as neural networks.

**Approach:** A co-evolutionary algorithm that simultaneously evolves a population of candidate circuits **and** a population of prompt templates steering the LLM's modifications, using an off-the-shelf LLM with no domain-specific training.

| Comparison | Result |
|---|---|
| vs highly optimized EvoApproxLib circuits | Improved error-area trade-offs across several target objectives |

**Paper:** Tomasovic, Sekanina, "Multi-Objective Coevolution of Prompts and Templates for Circuit Approximation," arXiv:[2606.13089](https://arxiv.org/abs/2606.13089), 2026.

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
| Chip macro placement order | OrderPlace | 14-34% wirelength reduction | Research |
| GPU kernels | Kernel Foundry | Up to 100% correctness on KernelBench L2 | Research |
| Technology mapping | MappingEvolve | 7.9-10% area reduction vs ABC/mockturtle | Research |
| Approximate multipliers | Prompt-circuit co-evolution | Better error-area trade-offs vs EvoApproxLib | Research |

**Note:** The "Barbarians at the Gate" paper (arXiv:2510.06189) is particularly notable for demonstrating that OpenEvolve can achieve significant systems optimizations for < $10 in LLM API costs.
