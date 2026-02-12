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
