# OPRO (Optimization by PROmpting)

**Organization:** Google DeepMind
**Year:** 2023
**Status:** Open-sourced

## Overview

OPRO uses LLMs directly as optimizers by describing optimization problems in natural language. The LLM iteratively proposes new solutions based on a history of prior solutions and their scores. While not explicitly evolutionary, it follows an iterative improvement pattern analogous to evolution.

## Approach

```
┌─────────────────────────────────────────┐
│           OPRO Optimization Loop         │
│                                         │
│  ┌──────────────────────────────────┐   │
│  │         Meta-Prompt               │   │
│  │  ┌────────────────────────────┐  │   │
│  │  │ Problem description        │  │   │
│  │  │ Previous solutions + scores│  │   │
│  │  │ "Generate a better one"    │  │   │
│  │  └────────────────────────────┘  │   │
│  └──────────────┬───────────────────┘   │
│                 │                        │
│                 ▼                        │
│  ┌──────────────────────────────────┐   │
│  │    LLM generates new solution    │   │
│  └──────────────┬───────────────────┘   │
│                 │                        │
│                 ▼                        │
│  ┌──────────────────────────────────┐   │
│  │    Evaluate + add to history     │   │
│  └──────────────────────────────────┘   │
└─────────────────────────────────────────┘
```

### Key Insight

The LLM sees a trajectory of (solution, score) pairs and learns to propose improvements. This is analogous to a (1+1) evolutionary strategy but with semantic understanding.

## Results

- Outperformed human-designed prompts by up to **8% on GSM8K**
- Up to **50% improvement on Big-Bench Hard** tasks
- Demonstrated that LLMs can serve as general-purpose optimizers

## Paper

**"Large Language Models as Optimizers"**
Chengrun Yang, Xuezhi Wang, Yifeng Lu, Hanxiao Liu, Quoc V. Le, Denny Zhou, Xinyun Chen
arXiv: [2309.03409](https://arxiv.org/abs/2309.03409)

## Repository

[google-deepmind/opro](https://github.com/google-deepmind/opro)

## See Also

- [EvoPrompt](evoprompt.md) -- Explicitly evolutionary prompt optimization
- [Promptbreeder](promptbreeder.md) -- Meta-evolutionary prompt optimization
