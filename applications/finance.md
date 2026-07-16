# Applied Results: Finance & Quantitative Trading

Papers where LLM+evolution methods designed, optimized, or repaired financial strategies.

---

## Quantitative Trading Strategy Optimization (EVOQUANT)

**Problem:** Quantitative strategy optimization is largely manual -- experts identify weak signals, tune risk-control rules, and repeatedly validate revisions. Naively letting an LLM rewrite strategies introduces hallucinated edits, strategy drift, and backtest overfitting.

**Approach:** EVOQUANT is a self-**Ev**olving **V**erifier-guided framework for strategy **O**ptimization in **Quant**itative trading. The LLM diagnoses performance bottlenecks, generates *semantically controlled* candidate edits, selects the best strategy through a multi-stage verification pipeline (guarding against drift and overfitting), and distills optimization experience into reusable knowledge for continual self-improvement.

| Metric | Result |
|---|---|
| Strategies evaluated | 7 (4 A-share market, 3 Crypto market) |
| Average test Sharpe ratio | **-0.298 → 0.538** |
| Best-performing strategy | **199% relative improvement** |
| Robustness | Confirmed by ablation studies and stress tests under stricter conditions |

**Significance:** Reframes quantitative strategy optimization from costly manual trial-and-error into an automated, verifiable iterative loop. The verifier-guided selection stage is the key defense against the failure modes (hallucinated edits, drift, backtest overfitting) that make naive LLM rewriting unreliable in finance.

**Paper:** Mao, Li, Li, Duan, Yuan, Liu, Luo, Tang, Chu, Tang, "EVOQUANT: Self-Evolving Verifier-Guided Strategy Optimization for Robust Quantitative Trading," arXiv:[2607.12455](https://arxiv.org/abs/2607.12455), 2026.

**Method:** LLM code/strategy evolution + multi-stage verification + experience distillation. Related in spirit to verifier-guided evolutionary coding agents such as [OpenEvolve](../projects/openevolve.md) and to reflective/experience-accumulating designs like [ReEvo](../projects/reevo.md).

---

## Algorithmic Trading Program Evolution (AlgoEvolve)

**Problem:** Extend LLM-as-semantic-mutation-operator program evolution from static coding benchmarks to algorithmic trading -- a domain that is noisy, non-stationary, and highly discontinuous.

**Approach:** AlgoEvolve generates, evaluates, and iteratively improves executable Python trading strategies under a rigorous testing protocol. A **meta-evolutionary outer loop** evolves the prompts guiding program synthesis in the inner loop, discovering improved search heuristics.

| Observation | Result |
|---|---|
| Strategy logic | Emergent **regime-adaptive** behavior, including autonomous shifts in trading rules |
| Meta-evolved prompts | Consistently outperform initial human-designed instructions; balance exploration/exploitation and reduce zero-trade failures |

**Paper:** Sharma, Shroff, "AlgoEvolve: LLM-driven Meta-evolution of Algorithmic Trading Programs," arXiv:[2606.26173](https://arxiv.org/abs/2606.26173), 2026.

**Method:** LLM semantic program evolution with a prompt-evolving meta-loop, in the spirit of [AlphaEvolve](../projects/alphaevolve.md). See also [ReEvo](../projects/reevo.md) for reflective heuristic evolution.

---

## Bitcoin Trading System Evolution (MadEvolve)

**Problem:** Apply LLM-driven algorithm optimization to core quantitative-finance tasks -- feature/signal generation, strategy-component tuning, and end-to-end pipeline design -- on Bitcoin trading.

**Approach:** MadEvolve is a general-purpose AlphaEvolve-inspired optimization framework (originally built for computational cosmology) applied here to algorithmic trading and alpha generation.

| Task | Result |
|---|---|
| Evolving feature sets for signal generation | Significant backtest improvement |
| Optimizing separate trading-strategy components | Significant improvement |
| Jointly evolving feature pipeline + execution strategy | Significant improvement |
| Rigor | Compared against agentic search (Claude Code); explicitly evaluates p-hacking probability on the simulation setup |

**Paper:** Kvasiuk, Li, Colegrove, Münchmeyer, "MadEvolve: Evolutionary Optimization of Trading Systems with Large Language Models," arXiv:[2605.23007](https://arxiv.org/abs/2605.23007), 2026.

**Method:** AlphaEvolve-inspired general-purpose algorithm evolution.

---

## Summary

| Problem | Method | Key Achievement |
|---|---|---|
| Quant trading (A-share + Crypto) | EVOQUANT | Avg Sharpe -0.298 → 0.538; verifier guards against drift/overfitting |
| Algorithmic trading programs | AlgoEvolve | Emergent regime-adaptive strategies; prompt-evolving meta-loop |
| Bitcoin trading systems | MadEvolve | Improves feature/signal/execution pipelines; audits p-hacking |
