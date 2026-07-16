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

## Diverse LLM Alignment (EvoPref)

**Problem:** Gradient-based preference optimization (DPO/ORPO/…) suffers **preference collapse** -- converging to narrow behavioral modes and neglecting preference diversity.

**Approach:** EvoPref is a multi-objective evolutionary algorithm maintaining populations of **LoRA adapters** optimized across helpfulness, harmlessness, and honesty via **NSGA-II** selection with archive-based diversity preservation.

| Metric | Result |
|---|---|
| Preference coverage | **+18%** (median 82.5% vs 70.0% for ORPO, p<0.001) |
| Collapse rate | **−47%** (11.0% vs 20.6%, p<0.001) |
| Alignment quality | Competitive (median 75.5% RewardBench vs 75.0% ORPO) |

Compared against MOEA/D, SMS-EMOA, CMA-ES, and gradient baselines (DPO/IPO/KTO/ORPO) with rigorous statistical testing.

**Paper:** Guo, Wu, Yiu, "EvoPref: Multi-Objective Evolutionary Optimization Discovers Diverse LLM Alignments Beyond Gradient Descent," arXiv:[2605.09777](https://arxiv.org/abs/2605.09777), 2026. Complements [DiscoPOP](#preference-optimization-algorithms-discopop), which evolves the loss function rather than a population of adapters.

---

## Learning to Evolve Across Tasks (Evolution Fine-Tuning)

**Problem:** In LLM+evolution search, the *capability* to iteratively evolve a solution (which part to mutate, when to backtrack) lives in the external scaffold, not the model -- so every new problem starts from scratch and accumulated search experience is discarded.

**Approach:** Evolution Fine-Tuning (EFT) is a **mid-training paradigm** that converts evolutionary-search trajectories into supervision, teaching the LLM itself to evolve solutions. The authors build **Finch Collection** (156K trajectories, 10 domains, 371 optimization tasks) and fine-tune open models (2B–9B).

| Metric | Result |
|---|---|
| Cross-task generalization | **+10.22%** average over base models across 22 held-out tasks |
| With test-time RL | Matches SOTA on two circle-packing tasks; beats base model on the Erdős minimum-overlap problem |

**Paper:** Lee, Kim, Kang, Chuen, Chen, Han, Jung, Kang, "Evolution Fine-Tuning: Learning to Discover Across 371 Optimization Tasks," arXiv:[2606.29082](https://arxiv.org/abs/2606.29082), 2026.

**Significance:** Serves as a "practice phase" for general-purpose discovery agents -- pushing evolutionary competence from the scaffold into the model weights.

---

## Training-Free Evolutionary Model Merging (Darwin Family)

**Problem:** Improve frontier-level reasoning **without additional training**, by recombining capabilities already encoded in existing checkpoints.

**Approach:** Darwin Family performs gradient-free weight-space recombination via a **14-dimensional adaptive merge genome** (component/block-level), **MRI-Trust Fusion** (balances diagnostic layer-importance signals with evolutionary search through a learnable trust parameter), and an **Architecture Mapper** enabling cross-architecture breeding (e.g. Transformer + Mamba components).

| Metric | Result |
|---|---|
| Darwin-27B-Opus on GPQA Diamond | **86.9%**, ranking #6 of 1,252 models -- beating its fully trained foundation model with no gradient training |
| Scales 4B–35B | Consistently improve over parents; support recursive multi-generation evolution |

**Paper:** Kim, Hong, Kim, Choi, Jang, Shin, Kim, "Darwin Family: MRI-Trust-Weighted Evolutionary Merging for Training-Free Scaling of Language-Model Reasoning," arXiv:[2605.14386](https://arxiv.org/abs/2605.14386), 2026.

**See also:** [Evo Model Merge](../projects/evo-model-merge.md) (Sakana AI) -- the foundational CMA-ES model-merging work that Darwin Family extends with diagnostic guidance and cross-architecture breeding.

---

## Summary

| Application | Method | Key Achievement |
|---|---|---|
| GNN architecture (algorithmic reasoning) | EvoPrompting | SOTA on 21/30 CLRS tasks |
| CNN architecture (MNIST-1D) | EvoPrompting | Beat human-designed architectures |
| General NAS (CIFAR-10) | LLMatic | Competitive in 2,000 evaluations |
| LLM alignment loss functions | DiscoPOP | Novel loss outperforming DPO |
| Diverse LLM alignment | EvoPref | +18% preference coverage, −47% collapse vs ORPO |
| Learning to evolve (mid-training) | Evolution Fine-Tuning | +10.22% cross-task; internalizes search into weights |
| Model merging recipes | Evo Model Merge | SOTA Japanese Math LLM |
| Training-free model merging | Darwin Family | 86.9% GPQA Diamond (#6/1252), no gradient training |
