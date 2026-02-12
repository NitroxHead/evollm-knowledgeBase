# Applied Results: Neural Architecture Search & ML

Papers where LLM+evolution methods discovered neural architectures or ML algorithms.

---

## Algorithmic Reasoning GNNs (EvoPrompting)

**Problem:** Design GNN architectures for the CLRS Algorithmic Reasoning Benchmark.

| Metric | Result |
|---|---|
| SOTA tasks | **21 out of 30** tasks outperformed existing architectures |
| Model size | Similar to hand-designed baselines |

**Method:** EvoPrompting -- LLM generates architecture code, evaluated by training.

**Paper:** Chen, Dohan, So, "EvoPrompting: Language Models for Code-Level Neural Architecture Search," arXiv:2302.14838, NeurIPS 2023.

---

## MNIST-1D CNNs (EvoPrompting)

**Problem:** Design CNN architectures for MNIST-1D benchmark.

| Metric | Result |
|---|---|
| Performance | Outperforms both human-designed and few-shot-prompted architectures |
| Efficiency | Better accuracy with similar or smaller model size |

**Method:** EvoPrompting
**Reference:** Same NeurIPS 2023 paper as above.

---

## CIFAR-10 / NAS-bench-201 (LLMatic)

**Problem:** Discover competitive architectures with minimal evaluations.

| Metric | Result |
|---|---|
| Evaluations | Only **2,000** candidates |
| Domain knowledge | None required -- no exposure to top-performing models |
| Performance | Competitive with established NAS methods |

**Method:** LLMatic -- CodeGen LLM + 2-archive MAP-Elites

**Paper:** Nasir, Earle, Togelius, James, Cleghorn, "LLMatic: Neural Architecture Search via Large Language Models and Quality Diversity Optimization," arXiv:2306.01102, GECCO 2024.

**Repository:** [umair-nasir14/LLMatic](https://github.com/umair-nasir14/LLMatic)

---

## Preference Optimization Algorithms (DiscoPOP)

**Problem:** Discover new loss functions for LLM alignment.

| Metric | Result |
|---|---|
| AlpacaEval 2.0 win rate vs GPT-4 | **13.21%** (vs DPO baseline: 11.23%) |
| Tasks | Summarization, controlled generation |

**Method:** LLM-driven evolutionary search over loss functions.

**Paper:** Lu et al., "Discovering Preference Optimization Algorithms with and for LLMs," NeurIPS 2024.

---

## Evolved Model Merging

**Problem:** Find optimal recipes for combining pretrained LLMs without retraining.

| Metric | Result |
|---|---|
| Japanese Math LLM | SOTA on Japanese benchmarks (not explicitly trained for math) |
| Japanese VLM | Culturally-aware vision-language model via cross-domain merging |

**Method:** CMA-ES optimizing merge weights and layer connections.

**Paper:** Akiba, Shing, Tang, Sun, Ha, "Evolutionary Optimization of Model Merging Recipes," arXiv:2403.13187, Nature Machine Intelligence, 2024.

---

## Summary

| Application | Method | Key Achievement |
|---|---|---|
| GNN architecture (algorithmic reasoning) | EvoPrompting | SOTA on 21/30 CLRS tasks |
| CNN architecture (MNIST-1D) | EvoPrompting | Beat human-designed architectures |
| General NAS (CIFAR-10) | LLMatic | Competitive in 2,000 evaluations |
| LLM alignment loss functions | DiscoPOP | Novel loss outperforming DPO |
| Model merging recipes | Evo Model Merge | SOTA Japanese Math LLM |
