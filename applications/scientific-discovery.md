# Applied Results: Scientific Discovery

Papers where LLM+evolution methods contributed to materials science, chemistry, biology, and cross-disciplinary discovery.

---

## Macromolecular Sequence Design

**Problem:** Design monomer sequences to produce targeted self-assembly morphologies.

| Method | Result | Reference |
|---|---|---|
| Claude 3.5 as evolutionary optimizer | Outperforms traditional active learning with handcrafted surrogates and EAs | npj Comput. Mater. 2024 |

**Key insight:** The LLM effectively self-reflects and infers approximate task understanding without explicit context -- it recognized the task as analogous to a "protein folding problem."

**Paper:** Reinhart, Statt (Penn State), "Large language models design sequence-defined macromolecules via evolutionary optimization," npj Computational Materials, 2024. [DOI](https://www.nature.com/articles/s41524-024-01449-6)

---

## Materials Discovery (LLEMA)

**Problem:** Discover new materials across 14 tasks spanning electronics, energy, coatings, optics, and aerospace.

| Metric | Result |
|---|---|
| Tasks tested | 14 materials design tasks |
| Performance | Higher hit-rates and stronger Pareto fronts than generative and LLM-only baselines |
| Validity | Chemically plausible, thermodynamically stable, property-aligned |

**Paper:** "Accelerating Materials Design via LLM-Guided Evolutionary Search," arXiv:2510.22503, 2025.

**Method:** LLEMA (LLM-guided Evolution for Materials design)

---

## Molecular Optimization / Drug Discovery (Chemlactica)

**Problem:** Optimize drug-like molecules for target properties.

| Metric | Result | Reference |
|---|---|---|
| PMO benchmark | **8% improvement** over previous SOTA | arXiv:2407.18897 |
| Multi-property optimization | Competitive or exceeds SOTA in docking simulations | ICLR 2025 |
| Models | Chemlactica-125M, Chemlactica-1.3B, Chemma-2B | -- |

**Paper:** Guevorguian, Bedrosian et al., "Small Molecule Optimization with Large Language Models," arXiv:2407.18897, ICLR 2025.

**Method:** Chemlactica/Chemma -- LLMs + evolutionary algorithms + rejection sampling

---

## Cross-Disciplinary Discovery (DeepEvolve)

**Problem:** Nine benchmarks spanning chemistry, mathematics, biology, materials, and patents.

| Metric | Result |
|---|---|
| Improvement range | 0.39% to **666%** across 9 benchmarks |
| Best gain (circle packing) | 666% -- from fixed-configuration to variable-sized constructions |

**Paper:** Liu, Zhu, Chen, Jiang, "Scientific Algorithm Discovery by Augmenting AlphaEvolve with Deep Research," arXiv:2510.06056, 2025.

**Method:** DeepEvolve -- AlphaEvolve augmented with a deep research agent for domain context

---

## Photonic Structure Design

**Problem:** Design multilayer photonic structures -- Bragg mirrors, ellipsometry inverse analysis, solar cell antireflection coatings.

| Metric | Result | Reference |
|---|---|---|
| Performance | Matches or surpasses quasi-oppositional DE on large-scale instances | arXiv:2503.19742 |
| Application | Realistic optical inverse design tasks | GECCO 2025 Workshop |

**Paper:** Yin et al., "Optimizing Photonic Structures with Large Language Model Driven Algorithm Discovery," arXiv:2503.19742, GECCO 2025 Workshop.

**Method:** LLaMEA framework with domain-focused prompts

---

## Bayesian Optimization for Engineering (LLaMEA-BO)

**Problem:** Generate novel Bayesian Optimization algorithms for expensive optimization in automotive crash worthiness and car shape design.

| Metric | Result | Reference |
|---|---|---|
| BBOB performance | Outperforms SOTA BO baselines on 19/24 functions (5D) | arXiv:2505.21034 |
| Generalization | Strong generalization to higher dimensions and different tasks | -- |

**Paper:** "LLaMEA-BO: Automatically Generating Bayesian Optimization Algorithms," arXiv:2505.21034, 2025.

**Method:** LLaMEA-BO (extension of LLaMEA for Bayesian optimization)

---

## Autonomous CFD Discovery (AI CFD Scientist)

**Problem:** Span the full scientific-discovery loop for computational fluid dynamics -- ideation, validated execution, physics-aware verification, source-code modification, and figure-grounded writing -- with vision-language gates that catch silent physical failures.

| Result | Metric |
|---|---|
| Spalart-Allmaras runtime correction discovered autonomously | **7.89% reduction** in lower-wall Cf RMSE vs DNS on periodic hill (Re_h=5600) |
| Silent failures caught by vision-language gate | **14 of 16** missed by solver-level checks |

**Paper:** Somasekharan, Pathak, Dhanakoti, Zhang, Yue, Zhu, Pan, "AI CFD Scientist: Toward Open-Ended Computational Fluid Dynamics Discovery with Physics-Aware AI Agents," arXiv:[2605.06607](https://arxiv.org/abs/2605.06607), 2026.

---

## Cosmology (CMBEvolve / CosmoEvolve)

**Problem:** Autonomous scientific discovery in cosmology.

| System | Target | Result |
|---|---|---|
| **CMBEvolve** | Quantitative objectives via LLM-guided code evolution + tree search | Iteratively improves benchmark on weak-lensing OOD detection |
| **CosmoEvolve** | Open-ended workflows via a virtual multi-agent research lab | Identifies non-trivial pair- and scale-dependent behaviour in ACT DR6 data |

**Paper:** Xu, Borrett, "Beyond AI as Assistants: Toward Autonomous Discovery in Cosmology," arXiv:[2605.14791](https://arxiv.org/abs/2605.14791), 2026.

---

## Scientific Image Processing (CVEvolve)

**Problem:** Autonomous algorithm discovery for unstructured scientific imaging -- noisy, high-dynamic-range, sparsely-labeled data common in x-ray and microscopy experiments.

| Task | Result |
|---|---|
| X-ray fluorescence microscopy image registration | Improved baseline |
| Bragg peak detection | Improved baseline |
| High-energy diffraction microscopy segmentation | Improved baseline |

**Method:** CVEvolve -- multi-round LLM-driven search with lineage-aware stochastic sampling, holdout testing to identify candidates that generalize better than later over-optimized alternatives. Zero-code interface for domain scientists.

**Paper:** Du, Yin, Luo, Beniwal, Tang, Sharma, Cherukara (Argonne National Lab), "CVEvolve: Autonomous Algorithm Discovery for Unstructured Scientific Data Processing," arXiv:[2605.11359](https://arxiv.org/abs/2605.11359), 2026.

---

## Symbolic Regression via RL-Optimized Evolution (GAE)

**Problem:** Discover closed-form physical equations for complex nonlinear oscillator systems via LLM-guided evolutionary program search.

| Component | Contribution |
|---|---|
| Relational GNN | Parses programs into typed computation graphs → structure-aware embeddings |
| RL meta-controller | Replaces blind parent/mutation sampling with a directed policy trained on reward history |
| Online GRPO fine-tuning | Updates the LLM mutation operator at test time using group-normalized rewards |

**Result:** GAE (Graph-Augmented Evolution) consistently matches or outperforms static LLM-driven baselines and achieves **state-of-the-art out-of-distribution** performance on nonlinear-oscillator symbolic regression.

**Paper:** Chen, Cheng, "GAE: Graph-Augmented Evolution for Scientific Discovery via Reinforcement Optimization," arXiv:[2607.10127](https://arxiv.org/abs/2607.10127), 2026.

---

## Critical Finding: Does LLM Evolution Actually Compound? (PTB-Search)

**Problem:** Audit whether the generate → select → feed-back loop truly compounds discovery in **scientific equation discovery**, where finite samples make structure underdetermined.

| Observation | Result |
|---|---|
| Parent-conditioned evolution vs fresh independent sampling (matched call budget) | Statistically indistinguishable (median OOD NMSE 0.045 vs 0.049) |
| Instructed multi-parent crossover | *Worse* than independent sampling |
| Predictor of final success | Initial proposal quality, not iteration |
| Proposed fix (PTB-Search) | Sample once, extract a per-problem term dictionary, then **set-level sparse selection** |
| LLM-SRBench (239-problem split) | **73.2%** Acc₀.₁ (Llama-3.1-8B), **77.0%** (DeepSeek-V4 anchor) vs 49.2% best baseline, at ~1/10 the call budget |

**Takeaway:** In this setting, the LLM is best understood as a *supplier of candidate terms*; the discovery is carried by external set-level selection, not by the evolutionary loop itself. An important calibration on where LLM+evolution does and does not add value.

**Paper:** Li, "Dictionaries, Not Darwin: Set-Level Selection Beats LLM Evolution in Scientific Equation Discovery," arXiv:[2607.04108](https://arxiv.org/abs/2607.04108), 2026.

---

## Autonomous Scientific Discovery (AI Scientist)

**Problem:** Fully automated open-ended scientific research.

| Version | Result | Reference |
|---|---|---|
| v1 | Papers rated "Weak Accept" by automated reviewers | github.com/SakanaAI/AI-Scientist |
| v2 | First entirely AI-generated peer-review-accepted workshop paper | github.com/SakanaAI/AI-Scientist-v2 |

**Method:** AI Scientist (Sakana AI) -- iterative LLM-powered research cycles

---

## Summary

| Domain | Method | Key Achievement |
|---|---|---|
| Polymer/macromolecular design | Claude 3.5 evolutionary | Outperformed active learning |
| Materials discovery (14 domains) | LLEMA | Chemically valid, SOTA hit-rates |
| Drug discovery | Chemlactica | 8% PMO improvement |
| Cross-disciplinary (9 domains) | DeepEvolve | Up to 666% improvement |
| Photonics/optics | LLaMEA | Matches specialized methods |
| Automotive engineering | LLaMEA-BO | 19/24 BBOB functions |
| General science | AI Scientist v2 | First AI peer-reviewed paper |
| CFD turbulence modeling | AI CFD Scientist | 7.89% Cf RMSE reduction, vision-language gates |
| Cosmology | CMBEvolve / CosmoEvolve | Autonomous ACT DR6 data analysis |
| Scientific imaging | CVEvolve | Zero-code algorithm discovery for x-ray microscopy |
| Symbolic regression | GAE | SOTA OOD via GNN + RL-directed evolution |
| Equation discovery (audit) | PTB-Search | Shows evolution ≈ fresh sampling; set-level selection wins |
