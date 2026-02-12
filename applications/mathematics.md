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
| Combinatorics | Cap sets, Erdos overlap, kissing number | FunSearch, AlphaEvolve |
| Geometry/Packing | Circle, hexagon, cube, sofa | AlphaEvolve, ShinkaEvolve, EoH |
| Algebra | Matrix multiplication, Kakeya/Nikodym sets | AlphaEvolve |
| Analysis | Autocorrelation inequalities | AlphaEvolve, CodeEvolve, TTT-Discover |
| Graph Theory | Shannon capacity, corners problem | FunSearch |
