# Applied Results: Mathematics

Papers where LLM+evolution methods produced new mathematical discoveries or improved known bounds.

---

## Cap Set Problem (Extremal Combinatorics)

**Problem:** Find the largest subset of Z_3^n containing no three elements that sum to zero.

| Result | Previous Best | New Result | Method | Reference |
|---|---|---|---|---|
| Cap set in Z_3^8 | 496 | **512** | FunSearch | Nature 2024 |
| Asymptotic lower bound (gamma) | ~2.2184 | **>= 2.2202** | FunSearch | Nature 2024 |

**Significance:** First improvement to the asymptotic lower bound in 20 years. FunSearch discovered a previously unrecognized symmetry in cap set constructions.

**Paper:** Romera-Paredes et al., "Mathematical discoveries from program search with large language models," Nature 625, pp. 468-475, 2024. [DOI](https://doi.org/10.1038/s41586-023-06924-6)

---

## 4x4 Matrix Multiplication

**Problem:** Multiply two 4x4 complex-valued matrices using the fewest scalar multiplications.

| Previous Best | New Result | Method | Reference |
|---|---|---|---|
| 49 (Strassen, 1969) | **48** | AlphaEvolve | arXiv:2506.13131 |

**Significance:** First improvement over Strassen's algorithm in 56 years. Works with non-commutative rings, enabling recursive application (48^k vs 49^k). AlphaEvolve improved SOTA on 14 different matrix multiplication benchmarks.

**Paper:** Novikov et al., "AlphaEvolve: A coding agent for scientific and algorithmic discovery," arXiv:2506.13131, 2025.

---

## Kissing Number (Dimension 11)

**Problem:** Maximum number of non-overlapping unit spheres that can simultaneously touch a central unit sphere in d dimensions.

| Dimension | Previous Lower Bound | New Lower Bound | Method | Reference |
|---|---|---|---|---|
| d=11 | 592 | **593** | AlphaEvolve | arXiv:2506.13131 |

**Significance:** Problem dating back 300+ years. Finding even a single additional sphere is extremely difficult.

---

## Circle Packing (26 circles in unit square)

**Problem:** Pack 26 circles in a unit square to maximize the sum of their radii.

Progressive improvement timeline:

| Date | Method | Score | Evaluations | Reference |
|---|---|---|---|---|
| Pre-2025 | Best known | ~2.634 | -- | -- |
| May 2025 | AlphaEvolve | 2.63586275 | Thousands+ | arXiv:2506.13131 |
| Jun 2025 | EoH | **2.63594** | Hundreds | github.com/FeiLiu36/EoH |
| Sep 2025 | ShinkaEvolve | **2.63597771** | ~150 | arXiv:2509.19349 |
| Nov 2025 | ThetaEvolve | **2.63598570** | Low | arXiv:2511.23473 |

**Key insight:** ShinkaEvolve surpassed AlphaEvolve with orders of magnitude fewer evaluations, demonstrating sample efficiency.

---

## Erdos Minimum Overlap Problem

**Problem:** Split integers {1,...,2n} into two equal sets to minimize the maximum frequency of any difference. Determine the asymptotic minimum overlap constant.

| Date | Method | Upper Bound | Reference |
|---|---|---|---|
| 2016 | Best human | ~0.380927 | -- |
| May 2025 | AlphaEvolve | ~0.380924 | arXiv:2506.13131 |
| Jan 2026 | TTT-Discover | **0.380876** | arXiv:2601.16175 |

---

## Autocorrelation Inequalities

**Problem:** Determine optimal constants C1 (upper) and C2 (lower) for autocorrelation inequalities of step functions.

### First Autocorrelation (C1 upper bound)

| Method | Bound | Reference |
|---|---|---|
| Best human | 1.50973 | -- |
| AlphaEvolve | <= 1.5032 | arXiv:2506.13131 |
| TTT-Discover | **1.50287** | arXiv:2601.16175 |

### Second Autocorrelation (C2 lower bound)

| Method | Bound | Reference |
|---|---|---|
| Best human | 0.8892 | -- |
| AlphaEvolve v1 | >= 0.8962 | arXiv:2506.13131 |
| CodeEvolve | **0.93768** | arXiv:2510.14150 |

---

## Finite Field Kakeya Sets

**Problem:** Construct Kakeya sets (containing a line in every direction) in F_q^d.

| Dimension | Result | Method | Reference |
|---|---|---|---|
| d=2 | Rediscovered known optimal | AlphaEvolve | arXiv:2511.02864 |
| d=3 | O(q) improvement in error term | AlphaEvolve | arXiv:2511.02864 |
| d=4 | O(q^3) improvement via algebraic construction | AlphaEvolve | arXiv:2511.02864 |

**Paper:** Georgiev, Gomez-Serrano, Tao, Wagner, "Mathematical exploration and discovery at scale," arXiv:2511.02864, 2025.

---

## Nikodym Sets (Inspired New Human Proof)

**Problem:** Construct Nikodym sets in F_q^d.

AlphaEvolve discovered a construction based on removing 8 low-degree algebraic surfaces. This was sufficiently novel that it **directly inspired a new theoretical paper by Terence Tao**:

**Follow-up Paper:** Tao, "New Nikodym set constructions over finite fields," arXiv:2511.07721, 2025.

| Dimension | Previous Best (random) | New Result (human proof, inspired by AlphaEvolve) |
|---|---|---|
| d >= 3 | q^d - (d-1+o(1))q^{d-1} log q | **q^d - ((d-2)/log 2 + 1 + o(1))q^{d-1} log q** |

---

## Hexagon Packing (11 hexagons)

**Problem:** Pack 11 unit regular hexagons into the smallest bounding hexagon.

| Previous Best (Morandi 2015) | AlphaEvolve | Method |
|---|---|---|
| Larger side length | **3.931** (~0.3% edge, ~0.6% area reduction) | AlphaEvolve |

**Insight:** Tilting inner hexagons at varying angles (not uniform alignment) yields denser packings.

---

## Cube Packing (11 cubes)

**Problem:** Pack 11 unit cubes into the smallest bounding box.

| Previous Best | AlphaEvolve |
|---|---|
| ~2.912 | **2.895** |

---

## 3D Moving Sofa Problem

**Problem:** Largest volume "sofa" that can navigate a snake-shaped 3D corridor.

| Result | Method |
|---|---|
| Rediscovered optimal 2D Gerver sofa | AlphaEvolve |
| **New 3D sofa with volume >= 1.81** | AlphaEvolve |

---

## Isosceles Triangle-Free Grid Points

**Problem:** Maximum points in 64x64 grid with no three forming an isosceles triangle.

| Result | Method |
|---|---|
| **112 points** | AlphaEvolve |

---

## Pairwise Touching Cylinders

**Problem:** Find configuration of 7 mutually touching infinite unit cylinders.

| Previous | AlphaEvolve |
|---|---|
| Months of CPU time | **~2 hours**, numerical loss O(10^{-23}) |

---

## IMO 2025 Problem 6 Variant

**Problem:** Minimum tiles C(n) to tile n x n grid where every row/column has exactly one uncovered square.

| Result | Method |
|---|---|
| Discovered formula: ceil(n + 2*sqrt(n) - 3) | AlphaEvolve |

---

## Shannon Capacity of Cycle Graphs

**Problem:** Shannon capacity of odd cycle graphs C_m.

| Graph | Result | Method |
|---|---|---|
| C_9, C_11 | Independent sets larger than previously known | FunSearch |

**Note:** Did not lead to improved Shannon capacity estimates.

---

## Corners Problem

**Problem:** Largest subset of [n]^2 with no axis-aligned right-angle corners.

| Case | Previous | FunSearch |
|---|---|---|
| n=2 | 3.391 | **3.421** |
| n=3 | 7 | **7.280** |

---

## Generative Modeling for Mathematical Discovery

A practical adaptation of FunSearch designed for working mathematicians (no ML expertise or HPC required).

**Paper:** Ellenberg, Fraser-Taliente, Harvey, Srivastava, Sutherland, "Generative Modeling for Mathematical Discovery," arXiv:2503.11061, 2025.

Demonstrated that FunSearch generalizes across combinatorial and number-theoretic settings.

---

## Ramsey Numbers (Improved Lower Bounds)

**Problem:** Determine the minimum number of vertices needed to guarantee a monochromatic clique under any 2-edge-coloring.

| Number | Previous Best | New Lower Bound | Method | Reference |
|---|---|---|---|---|
| R(3, 13) | 60 | **61** | AlphaEvolve | arXiv:2603.09172 |
| R(3, 18) | 99 | **100** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 13) | 138 | **139** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 14) | 147 | **148** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 15) | 158 | **159** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 16) | 170 | **174** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 18) | 205 | **209** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 19) | 213 | **219** | AlphaEvolve | arXiv:2603.09172 |
| R(4, 20) | 234 | **237** | AlphaEvolve | arXiv:2603.09172 |

**Significance:** Virtually all known Ramsey lower bounds are derived computationally with bespoke search algorithms, each producing a handful of results. AlphaEvolve is a **single meta-algorithm** that yields a search algorithm for all of these results -- and recovers known optimal lower bounds across many other cases.

**Paper:** Nagda, Raghavan, Thakurta, "Reinforced Generation of Combinatorial Structures: Ramsey Numbers," arXiv:[2603.09172](https://arxiv.org/abs/2603.09172), 2026.

---

## Zarankiewicz Numbers (Bipartite Extremal Graph Theory)

**Problem:** Z(m, n, s, t) is the maximum number of edges in a bipartite graph G_{m,n} with no complete K_{s,t} bipartite subgraph.

| Parameter | Previous | New Result | Method | Reference |
|---|---|---|---|---|
| Z(11, 21, 3, 3) | -- | **= 116** (exact) | OpenEvolve | arXiv:2605.01120 |
| Z(11, 22, 3, 3) | -- | **= 121** (exact) | OpenEvolve | arXiv:2605.01120 |
| Z(12, 22, 3, 3) | -- | **= 132** (exact) | OpenEvolve | arXiv:2605.01120 |
| Plus 41 additional lower bounds | -- | improved | OpenEvolve | arXiv:2605.01120 |

**Cost:** Less than **$30 per parameter combination** -- demonstrating that LLM-guided evolutionary search can be inexpensive and reproducible for combinatorial discovery.

**Paper:** Bhan, Nobili, Langer, "New Bounds for Zarankiewicz Numbers via Reinforced LLM Evolutionary Search," arXiv:[2605.01120](https://arxiv.org/abs/2605.01120), 2026.

---

## Random Offerer Mechanism (Bilateral Trade, Game Theory)

**Problem:** Determine the worst-case ratio of first-best gains-from-trade to those of the Random-Offerer mechanism in bilateral trade.

| Source | Lower Bound on Ratio | Reference |
|---|---|---|
| Original conjecture | <= 2 | -- |
| Cai et al. | > 2 | -- |
| Babaioff et al. | ~ 2.02 | -- |
| AlphaEvolve | **>= 2.0749** | arXiv:2603.08679 |

**Significance:** AI-guided evolutionary search over the space of value distributions identified a new worst-case instance, widening the known efficiency gap.

**Paper:** Cai, Gupta, Li, Mehta, "A New Lower Bound for the Random Offerer Mechanism in Bilateral Trade using AI-Guided Evolutionary Search," arXiv:[2603.08679](https://arxiv.org/abs/2603.08679), 2026.

---

## R-Equivalence on Cubic Surfaces (AI-Assisted Proof)

**Problem:** Determine R-equivalence on smooth cubic surfaces over p-adic fields with all-Eckardt reductions.

| Setting | Result | AI Role |
|---|---|---|
| 2-adic surfaces, all-Eckardt reductions | R-equivalence is trivial or exponent 2 | AlphaEvolve + Gemini 3 Deep Think |
| Diagonal cubic X^3+Y^3+Z^3+\zeta_3 T^3=0 over Q_2(\zeta_3) | Triviality confirmed (answers long-standing Manin question, 1972) | AI-assisted |

**Paper:** Kanevsky, Salazar, Harvey, "R-equivalence on Cubic Surfaces I: Existing Cases with Non-Trivial Universal Equivalence," arXiv:[2603.19215](https://arxiv.org/abs/2603.19215), 2026.

**Note:** The authors document the timeline and nature of AI use, describing this as the first in a series of works derived from a year of interactions with generative AI models. AlphaEvolve assisted exploration; Gemini 3 Deep Think proved many of the supporting lemmas.

---

## 67 Open Problems (Comprehensive Study)

AlphaEvolve was tested on 67 open problems spanning analysis, combinatorics, geometry, and number theory in collaboration with Terence Tao and Javier Gomez-Serrano.

**Overall Results:**
- ~75% matched state-of-the-art
- ~20% improved upon best-known solutions
- Tested on Sidorenko's, Sendov's, Crouzeix's, and Smale's conjectures -- found only known extremizers, no counterexamples

**Paper:** arXiv:2511.02864

---

## Summary

| Domain | Discoveries | Key Method |
|---|---|---|
| Combinatorics | Cap sets, Erdos overlap, kissing number, Ramsey, Zarankiewicz | FunSearch, AlphaEvolve, OpenEvolve |
| Geometry/Packing | Circle, hexagon, cube, sofa | AlphaEvolve, ShinkaEvolve, EoH |
| Algebra | Matrix multiplication, Kakeya/Nikodym sets | AlphaEvolve |
| Analysis | Autocorrelation inequalities | AlphaEvolve, CodeEvolve, TTT-Discover |
| Graph Theory | Shannon capacity, corners, bipartite extremal | FunSearch, OpenEvolve |
| Game Theory / Econ | Bilateral trade lower bound | AlphaEvolve |
| Algebraic Geometry | R-equivalence on cubic surfaces | AlphaEvolve + Gemini Deep Think |
