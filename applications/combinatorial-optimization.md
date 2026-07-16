# Applied Results: Combinatorial Optimization

Papers where LLM+evolution methods designed heuristics for NP-hard optimization problems.

---

## Online Bin Packing

**Problem:** Items arrive one at a time with sizes in (0,1]; assign irrevocably to bins of capacity 1 to minimize bins used.

| Method | Result | Reference |
|---|---|---|
| FunSearch | Outperforms First Fit and Best Fit on OR1-OR5 benchmarks; generalizes across problem sizes | Nature 2024 |
| EoH | Surpasses FunSearch with fewer LLM queries | arXiv:2401.02051 |
| EvoTune | Outperforms FunSearch baseline consistently | arXiv:2504.05108 |

**FunSearch insight:** Instead of always packing into the bin with least remaining capacity (Best Fit), only do so when the fit is very tight; otherwise use bins with more remaining space. This counter-intuitive strategy was new.

**Benchmarking note:** Sim, Renau, Hart, "Beyond the Hype: Benchmarking LLM-Evolved Heuristics for Bin Packing" (arXiv:2501.11411, GECCO 2025) found that most LLM-generated heuristics don't generalize well across diverse bin packing instance distributions. Important calibration for the field.

---

## Traveling Salesman Problem (TSP)

| Method | Result | Reference |
|---|---|---|
| ReEvo | Improved POMO optimality gap from 52% to 29% on TSP1000 | arXiv:2402.01145 |
| ReEvo | Improved LEHD gap from 3.2% to 3.0% on TSP1000 | arXiv:2402.01145 |
| EoH | Generated SOTA heuristics | arXiv:2401.02051 |
| HeurAgenix | Matches or exceeds specialized solvers | arXiv:2506.15196 |
| EvoTune | Consistent improvement over baselines | arXiv:2504.05108 |

---

## Vehicle Routing (CVRP)

| Method | Result | Reference |
|---|---|---|
| ReEvo | Generated heuristics outperforming neural solvers in minutes | arXiv:2402.01145 |
| HeurAgenix | Matches or exceeds specialized solvers | arXiv:2506.15196 |

---

## Job Shop Scheduling

| Method | Result | Reference |
|---|---|---|
| HeurAgenix | Competitive with specialized JSSP solvers | arXiv:2506.15196 |
| LLM4EO | Outperforms tailored EAs on FJSP benchmarks; LLM replaces operators when EA stagnates | arXiv:2511.16485 |

**Paper:** "LLM4EO: Large Language Model for Evolutionary Optimization in Flexible Job Shop Scheduling," arXiv:2511.16485, 2025.

---

## Multiple Knapsack

| Method | Result | Reference |
|---|---|---|
| ReEvo | Competitive heuristics generated | arXiv:2402.01145 |
| HeurAgenix | Matches specialized solvers | arXiv:2506.15196 |

---

## MaxCut

| Method | Result | Reference |
|---|---|---|
| HeurAgenix | Competitive with specialized MaxCut solvers | arXiv:2506.15196 |

---

## Decap Placement (Electronic Design Automation)

| Method | Result | Reference |
|---|---|---|
| ReEvo | State-of-the-art heuristic | arXiv:2402.01145 |

---

## Google Hash Code Datacenter Optimization

| Method | Result | Reference |
|---|---|---|
| EvoTune | Score of 418, surpassing top human score of 407 | arXiv:2504.05108 |

**Paper:** "Algorithm Discovery With LLMs: Evolutionary Search Meets Reinforcement Learning," arXiv:2504.05108, COLM 2025.

**Method:** EvoTune (evolutionary search + RL fine-tuning of LLM)

---

## Black-Box Optimization (BBOB Benchmark)

| Method | Result | Reference |
|---|---|---|
| LLaMEA | Outperformed CMA-ES and DE on 5D BBOB | arXiv:2405.20132 |
| LLaMEA | Won Any-time Performance competition at GECCO 2025 | IEEE TEVC |
| LLaMEA | Silver Humies Award at GECCO 2025 | GECCO 2025 |

---

## Multi-Objective Bayesian Optimization (LLaMEA-MOBO)

**Problem:** Automatically design complete multi-objective Bayesian optimization (MOBO) algorithms -- a task where the many interdependent design choices normally demand deep expert tuning.

| Metric | Result | Reference |
|---|---|---|
| Synthetic suite (ZDT/DTLZ/WFG, 12 problems) | Best generated algorithm reaches **0.971** mean normalized hypervolume vs 0.869 for qParEGO, at ~**60x** less wall-clock time | arXiv:2607.08791 |
| Per-problem significance | Significantly better than qParEGO on 7/12; never worse | -- |
| Real-world engineering (3 unseen RE problems) | **0.985** vs 0.971 for qParEGO, at ~**3.4x** lower cost | -- |

Extends [LLaMEA](../projects/llamea.md) to MOBO, using the LLM as mutation/crossover operator within an evolutionary strategy, with SMAC hyperparameter optimization inside the loop (~900 algorithms generated across 9 runs).

**Paper:** Laskaris, Brasher, van Stein, Raponi, Bäck, Neukart, "LLM-Driven Evolutionary Generation of Multi-Objective Bayesian Optimization Algorithms," arXiv:[2607.08791](https://arxiv.org/abs/2607.08791), 2026.

---

## 2026 LLM-AHD Framework Wave

A large family of LLM-based Automated Heuristic Design (LLM-AHD) frameworks appeared in early 2026, each targeting a different limitation of the prior generation (EoH, ReEvo, FunSearch). Most evaluate on the same TSP / Online BPP / CVRP / FJSP / MIS substrate.

| Framework | Key idea | Reference |
|---|---|---|
| **HMACE** | Multi-agent (Proposer/Generator/Evaluator/Reflector) collaboration | arXiv:[2605.07214](https://arxiv.org/abs/2605.07214) |
| **BEAM** | Bi-level GA (high-level structure) + MCTS (low-level placeholders); beats KaMIS on MIS | arXiv:[2604.12898](https://arxiv.org/abs/2604.12898) |
| **A2DEPT** | Tree-structured evolution over full algorithms (not just code components) | arXiv:[2604.24043](https://arxiv.org/abs/2604.24043) |
| **AHD Agent** | Tool-using RL-trained agent that retrieves targeted runtime evidence | arXiv:[2605.08756](https://arxiv.org/abs/2605.08756) |
| **LaF-MCTS** | Three-tier hierarchical MCTS for large-scale CVRP (1000+ nodes) | arXiv:[2605.03339](https://arxiv.org/abs/2605.03339) |
| **ReVEL** | Multi-turn reflective evolution with performance-profile grouping | arXiv:[2604.04940](https://arxiv.org/abs/2604.04940) |
| **EvoStage** | Stagewise decomposition; beats human-expert designs for Adam scheduling and BO acquisition functions | arXiv:[2603.07970](https://arxiv.org/abs/2603.07970) |
| **DyACE** | Dynamic co-evolution with receding-horizon control for perturbative heuristics | arXiv:[2603.13344](https://arxiv.org/abs/2603.13344) |
| **DSevolve** | Quality-diverse rule portfolio for dynamic shop-floor scheduling | arXiv:[2603.27628](https://arxiv.org/abs/2603.27628) |
| **CoupleEvo** | Coupled-subproblem heuristic evolution | arXiv:[2605.06341](https://arxiv.org/abs/2605.06341) |
| **Teacher-Aware Evolution** | Uses RL-trained policy as behavioral teacher for heuristic search | arXiv:[2605.10634](https://arxiv.org/abs/2605.10634) |
| **QDEvo** | Multi-objective Quality-Diversity: unbounded archive keyed by code embeddings + hierarchical self-reflection; fights mode collapse | arXiv:[2607.11916](https://arxiv.org/abs/2607.11916) |
| **MeEvo** | Cyclically couples Natural Evolution (code crossover/mutation) with Metacognitive Evolution (reflection over reasoning traces); lower variance on constrained tasks | arXiv:[2606.14202](https://arxiv.org/abs/2606.14202) |
| **RAISE** | Robust AHD: an LLM-free inner loop searches worst-case adversarial instances so heuristics survive distribution shift (prior methods degrade up to 19x) | arXiv:[2606.31801](https://arxiv.org/abs/2606.31801) |
| **SeaEvo** | Strategy-space layer that turns natural-language strategy into persistent population-level state; +20.6% avg across four systems benchmarks | arXiv:[2604.24372](https://arxiv.org/abs/2604.24372) |

**Trend:** The field has converged on multi-agent / multi-stage / tool-using designs as the next step beyond single-loop FunSearch/EoH-style evolution. **BEAM** stands out for producing a heuristic that outperforms KaMIS, a long-standing SOTA Maximum Independent Set solver. **QDEvo** attacks a recurring pathology of LLM heuristic search -- mode collapse into homogeneous populations -- by pairing Quality-Diversity with pre-trained code embeddings, and reports gains in both Hypervolume and Inverted Generational Distance over prior SOTA. A second sub-trend targets **what the search preserves and how robust it is**: **SeaEvo** keeps natural-language strategy as first-class population state (beyond transient mutation context), while **RAISE** hardens evolved heuristics against distribution shift via adversarial instance search, and **MeEvo** fuses reflection-based and population-based evolution.

---

## Online Inventory Policies (InvEvolve)

**Problem:** Generate inventory-control policies for online settings with **non-stationary demand** -- a dynamic setting where AlphaEvolve-style evolution (strong on static, structured problems) is not directly suited.

**Approach:** InvEvolve is an end-to-end inventory-policy evolution and inference framework grounded in **confidence-interval-based certification**. Built on an LLM trained via RL, it processes demand data together with numerical and textual features and emits **white-box** policies carrying statistical safety guarantees.

| Aspect | Result |
|---|---|
| Theory | Lower bound on the probability of evolving a statistically safe *and* improved policy; characterizes the multi-period gap vs an oracle-safe benchmark |
| Synthetic + real retail data | Outperforms classical inventory policies and deep-learning methods |
| Canonical settings | New policies beat existing benchmarks |

**Paper:** Huang, Lin, Tang, Jiang, Jiang, Wang, Wei, "InvEvolve: Evolving White-Box Inventory Policies via Large Language Models with Performance Guarantees," arXiv:[2605.00369](https://arxiv.org/abs/2605.00369), 2026.

---

## Key Papers

| Paper | Year | Venue | Method | Problems Solved |
|---|---|---|---|---|
| ReEvo | 2024 | NeurIPS 2024 | ReEvo | TSP, CVRP, Orienteering, Knapsack, Bin Packing, Decap |
| EoH | 2024 | ICML 2024 (Oral) | EoH | Bin Packing, TSP |
| HeurAgenix | 2025 | arXiv | HeurAgenix | TSP, CVRP, MKP, JSSP, MaxCut |
| EvoTune | 2025 | COLM 2025 | EvoTune | Bin Packing, TSP, Hash Code |
| LLM4EO | 2025 | arXiv | LLM4EO | Flexible Job Shop Scheduling |
| Beyond the Hype | 2025 | GECCO 2025 | Various | Bin Packing (benchmarking study) |
| LLaMEA | 2024 | IEEE TEVC | LLaMEA | BBOB (general black-box optimization) |

---

## Summary

| Problem Domain | Best Method | Key Achievement |
|---|---|---|
| Bin Packing | FunSearch/EoH | Novel counter-intuitive heuristic |
| TSP | ReEvo | 44% improvement in optimality gap (TSP1000) |
| CVRP | ReEvo | Outperforms neural solvers |
| Job Shop | LLM4EO | Meta-evolution of operators |
| Hash Code | EvoTune | Surpassed top human score |
| BBOB | LLaMEA | Beat CMA-ES and DE; Silver Humies Award |
| Multi-objective BO | LLaMEA-MOBO | Beats qParEGO at ~60x lower cost (synthetic) |
