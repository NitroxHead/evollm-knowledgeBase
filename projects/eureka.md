# Eureka

**Organization:** NVIDIA, UPenn, Caltech, UT Austin
**Year:** 2023
**Status:** Open-sourced
**Venue:** ICLR 2024

## Overview

Eureka is an LLM-powered evolutionary system for automatically designing reward functions for reinforcement learning in robotics. It uses GPT-4 to iteratively generate, evaluate, and improve reward code -- applying evolutionary principles to the reward design problem.

## Architecture

```
┌─────────────────────────────────────────────────┐
│              Eureka Loop                         │
│                                                 │
│  Phase 1: Generation                            │
│  ┌────────────────────────────────────────────┐ │
│  │ GPT-4 generates batch of reward functions  │ │
│  │ (zero-shot, from environment source code)  │ │
│  └──────────────────┬─────────────────────────┘ │
│                     │                            │
│  Phase 2: Evaluation                            │
│  ┌──────────────────▼─────────────────────────┐ │
│  │ Train RL policies with each reward function│ │
│  │ (GPU-accelerated, NVIDIA Isaac Gym)        │ │
│  └──────────────────┬─────────────────────────┘ │
│                     │                            │
│  Phase 3: Reflection                            │
│  ┌──────────────────▼─────────────────────────┐ │
│  │ Feed performance statistics back to GPT-4  │ │
│  │ "Reward reflection" → improved candidates  │ │
│  └────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────┘
```

## Results

- Outperformed **expert human-engineered rewards on 83%** of 29 tasks
- Average **52% normalized improvement** across 10 robot morphologies
- Enabled a simulated Shadow Hand to perform **pen spinning** for the first time

## Paper

**"Eureka: Human-Level Reward Design via Coding Large Language Models"**
Yecheng Jason Ma, William Liang, Guanzhi Wang, De-An Huang, Osbert Bastani, Dinesh Jayaraman, Yuke Zhu, Linxi "Jim" Fan, Anima Anandkumar
arXiv: [2310.12931](https://arxiv.org/abs/2310.12931)
ICLR 2024

## Repository

[eureka-research/Eureka](https://github.com/eureka-research/Eureka)

## See Also

- [ELM](elm.md) -- Evolving robot programs via LLMs
- [ReEvo](reevo.md) -- Similar iterative improvement with LLM reflection
