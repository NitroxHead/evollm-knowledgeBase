# Darwin Godel Machine (DGM)

**Organization:** Sakana AI, University of British Columbia
**Year:** 2025
**Status:** Open-sourced

## Overview

The Darwin Godel Machine is a self-improving coding agent that reads and modifies **its own source code** to improve its performance. It uses open-ended evolutionary search inspired by Darwinian evolution to autonomously discover improvements to its own codebase.

## Key Innovation: Self-Modification

Unlike other projects that evolve solutions to external problems, DGM evolves **itself**:

```
┌─────────────────────────────────────────────┐
│           Self-Improvement Loop              │
│                                             │
│  ┌──────────────────────────────────────┐   │
│  │  Agent reads its own source code     │   │
│  └──────────────┬───────────────────────┘   │
│                 │                            │
│                 ▼                            │
│  ┌──────────────────────────────────────┐   │
│  │  Foundation model proposes code      │   │
│  │  modifications (new tools, workflow  │   │
│  │  changes, strategy updates)          │   │
│  └──────────────┬───────────────────────┘   │
│                 │                            │
│                 ▼                            │
│  ┌──────────────────────────────────────┐   │
│  │  Evaluate modified agent variant     │   │
│  │  on benchmarks (sandboxed)           │   │
│  └──────────────┬───────────────────────┘   │
│                 │                            │
│                 ▼                            │
│  ┌──────────────────────────────────────┐   │
│  │  MAP-Elites maintains diverse        │   │
│  │  high-quality agent variants         │   │
│  └──────────────────────────────────────┘   │
└─────────────────────────────────────────────┘
```

## Results

- Improved coding agent performance on **SWE-bench** from 20.0% to **50.0%**
- Improved on **Polyglot** from 14.2% to **30.7%**
- All improvements discovered **autonomously** through self-modification

## Paper

**"Darwin Godel Machine: Open-Ended Evolution of Self-Improving Agents"**
Jenny Zhang, et al.
arXiv: [2505.22954](https://arxiv.org/abs/2505.22954) (May 2025)

## Repository

[jennyzzt/dgm](https://github.com/jennyzzt/dgm)

## Significance

DGM represents a step toward recursive self-improvement -- agents that can improve their own capabilities without human intervention. This connects to classical AI concepts like the Godel Machine (Jurgen Schmidhuber, 2003).

## See Also

- [ShinkaEvolve](shinkaevolve.md) -- Another Sakana AI evolution project
- [AI Scientist](ai-scientist.md) -- Autonomous scientific discovery by Sakana AI
- [ELM](elm.md) -- LLM fine-tuning on evolved outputs (related concept)
