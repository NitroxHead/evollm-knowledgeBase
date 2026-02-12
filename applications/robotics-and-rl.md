# Applied Results: Robotics & Reinforcement Learning

Papers where LLM+evolution methods designed reward functions, robot morphologies, or RL policies.

---

## Dexterous Manipulation -- Pen Spinning (Eureka)

**Problem:** Design reward functions for 29 RL environments across 10 robot morphologies, including dexterous manipulation with a Shadow Hand.

| Metric | Result |
|---|---|
| Tasks outperforming human experts | **83%** (24 out of 29) |
| Average normalized improvement | **52%** over human-designed rewards |
| Pen spinning | **First demonstration** of simulated Shadow Hand performing pen spinning tricks |

**Method:** Eureka (NVIDIA) -- GPT-4 generates reward functions, evaluated in NVIDIA Isaac Gym, improved via reward reflection.

**Paper:** Ma, Liang, Wang et al., "Eureka: Human-Level Reward Design via Coding Large Language Models," arXiv:2310.12931, ICLR 2024.

**Repository:** [eureka-research/Eureka](https://github.com/eureka-research/Eureka)

---

## Virtual Walking Robots -- Sodarace (ELM)

**Problem:** Design ambulating robots for various terrains in the Sodarace simulation domain.

| Metric | Result |
|---|---|
| Functional programs generated | **Hundreds of thousands** |
| Domain knowledge required | **None** -- domain was entirely unseen during LLM pretraining |
| Bootstrapping | Evolved programs used to fine-tune a conditional LLM for terrain-specific generation |

**Method:** ELM (Evolution through Large Models) + MAP-Elites

**Paper:** Lehman et al., "Evolution through Large Models," arXiv:2206.08896, 2022.

**Repository:** [CarperAI/OpenELM](https://github.com/CarperAI/OpenELM)

---

## Preference Optimization for LLM Alignment (DiscoPOP)

**Problem:** Discover new preference optimization algorithms for LLM alignment (RLHF alternative).

| Metric | Result |
|---|---|
| AlpacaEval 2.0 win rate vs GPT-4 | **13.21%** (DPO baseline: 11.23%) |
| Method discovered | DiscoPOP loss function |

**Method:** LLM-driven evolutionary search over preference optimization loss functions.

**Paper:** Lu, Holt, Fanconi, Chan, Foerster, van der Schaar, Lange (Sakana AI), "Discovering Preference Optimization Algorithms with and for LLMs," NeurIPS 2024.

---

## Summary

| Application | Method | Key Achievement |
|---|---|---|
| Reward function design (29 tasks) | Eureka | 83% beat human experts; pen spinning |
| Robot morphology design | ELM | Hundreds of thousands of functional robots |
| LLM alignment (RLHF) | DiscoPOP | New preference optimization loss function |
