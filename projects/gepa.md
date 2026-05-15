# GEPA (Genetic-Pareto)

**Organization:** UC Berkeley / Stanford / Notre Dame / Databricks
**Year:** 2025 (July)
**Status:** Open-sourced (Apache 2.0)

## Overview

GEPA is a reflective prompt optimizer that uses natural-language reflection plus a Pareto-frontier evolutionary loop to learn high-level rules from trial-and-error rollouts. It frames LLM adaptation as prompt evolution rather than weight updates, arguing that interpretable language is a richer learning medium than scalar policy-gradient signals. GEPA has become one of the most widely cited baselines for prompt evolution in 2026, with frameworks like LEVI, EvoX, ShinkaEvolve, and CANTANTE benchmarking against it.

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│                       GEPA Loop                            │
│                                                          │
│  ┌────────────┐    ┌──────────────────┐                 │
│  │  Sample     │───>│  Run system,     │                 │
│  │  prompt(s)  │    │  collect rollout │                 │
│  │  from       │    │  trajectories    │                 │
│  │  Pareto     │    │  (reasoning,     │                 │
│  │  frontier   │    │   tool calls,    │                 │
│  └────────────┘    │   outputs)        │                 │
│         ▲          └────────┬─────────┘                 │
│         │                    │                            │
│         │                    ▼                            │
│  ┌──────┴──────┐    ┌──────────────────┐                │
│  │  Pareto     │<───│  Reflective      │                 │
│  │  frontier   │    │  LLM diagnoses,  │                 │
│  │  of prompts │    │  proposes prompt │                 │
│  │  (multi-    │    │  updates, merges │                 │
│  │  objective) │    │  Pareto-optimal  │                 │
│  └─────────────┘    │  prompt pairs    │                 │
│                     └──────────────────┘                 │
└──────────────────────────────────────────────────────────┘
```

### Components

1. **Trajectory sampling** -- For each candidate prompt, samples full execution traces including reasoning, tool calls, and tool outputs.

2. **Reflective mutation** -- A reflection LLM reads trajectories in natural language to diagnose failure modes, then proposes targeted prompt updates.

3. **Pareto-frontier selection** -- Maintains a frontier of prompts on multiple objectives (accuracy across task subsets) rather than collapsing to one best prompt; this preserves complementary strategies for later merging.

4. **Complementary merging** -- Combines lessons from different Pareto-optimal prompts to produce hybrid candidates.

## Key Innovation

GEPA's central claim is that **language-space feedback** (natural-language reflection on trajectories) generalizes from far fewer rollouts than **scalar-reward feedback** (RL policy gradients). The Pareto frontier preserves diverse partial-credit prompts whose strengths can be merged, avoiding the diversity collapse common in standard genetic prompt optimization.

## Results

- **vs. GRPO (RL):** +6% average across six tasks, up to +20%, using **up to 35x fewer rollouts**
- **vs. MIPROv2 (prior SOTA prompt optimizer):** >10% improvement (e.g., +12% accuracy on AIME-2025)
- **Inference-time search:** Promising results as a code-optimization search strategy
- **Tasks:** Multi-step reasoning, tool use, code optimization

## Paper

**"GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning"**
Lakshya A Agrawal, Shangyin Tan, Dilara Soylu, Noah Ziems, Rishi Khare, Krista Opsahl-Ong, Arnav Singhvi, Herumb Shandilya, Michael J Ryan, Meng Jiang, Christopher Potts, Koushik Sen, Alexandros G. Dimakis, Ion Stoica, Dan Klein, Matei Zaharia, Omar Khattab
arXiv: [2507.19457](https://arxiv.org/abs/2507.19457) (July 2025)

## Repository

[gepa-ai/gepa](https://github.com/gepa-ai/gepa) -- Apache 2.0

Integrated as a module in **DSPy**: `dspy.GEPA`

## Adoption (as of May 2026)

GEPA appears as the primary baseline in numerous 2026 prompt-optimization papers:
- **LEVI** (2605.09764) -- matches/exceeds GEPA at <50% rollout budget
- **CANTANTE** (2605.13295) -- contrastive credit attribution, beats GEPA on MBPP/GSM8K
- **ContraPrompt** (2604.17937) -- outperforms GEPA on 4 reasoning benchmarks
- **p1** (2604.08801) -- prompt filtering on top of GEPA-style search
- **FlashEvolve** (2605.08520) -- 3.5-4.9x throughput on GEPA workloads
- **E-SPL** (2602.14697) -- joint RL + prompt evolution

GEPA-Optimized prompting has also been applied to OpenACC code generation (2601.08884) and clinical risk-of-bias assessment (2512.01452).

## Key People

- **Lakshya A Agrawal** -- Lead author
- **Omar Khattab** -- DSPy creator, senior author
- **Matei Zaharia, Ion Stoica** -- UC Berkeley, Databricks/Sky Lab

## See Also

- [OPRO](opro.md) -- Earlier prompt-as-optimization approach
- [Promptbreeder](promptbreeder.md) -- Earlier meta-prompt evolution
- [EvoPrompt](evoprompt.md) -- Earlier GA-style prompt evolution
- [LEVI](levi.md) -- Sample-efficient successor that benchmarks against GEPA
- [EvoX](evox.md) -- Meta-evolution framework that subsumes GEPA-style strategies
