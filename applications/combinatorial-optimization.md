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
