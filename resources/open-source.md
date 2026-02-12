# Open Source Implementations

## Full Frameworks

### OpenEvolve (AlphaEvolve Reimplementation)
- **Repo:** [codelion/openevolve](https://github.com/codelion/openevolve)
- **Install:** `pip install openevolve`
- **License:** Open source
- **LLM Support:** Any OpenAI-compatible API (Gemini, GPT, local models)
- **Description:** Faithful reimplementation of AlphaEvolve's architecture

### ShinkaEvolve
- **Repo:** [SakanaAI/ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve)
- **License:** Apache 2.0
- **Description:** Sample-efficient LLM-driven program evolution
- **Key Feature:** Novelty-based rejection + bandit-based LLM selection

### OpenELM
- **Repo:** [CarperAI/OpenELM](https://github.com/CarperAI/OpenELM)
- **License:** Open source
- **LLM Support:** Any via LangChain
- **Description:** General QD+LLM evolutionary search library

### FunSearch
- **Repo:** [google-deepmind/funsearch](https://github.com/google-deepmind/funsearch)
- **License:** Apache 2.0
- **Description:** Official DeepMind implementation

### LLaMEA
- **Repo:** [XAI-liacs/LLaMEA](https://github.com/XAI-liacs/LLaMEA)
- **License:** MIT
- **Description:** Automated metaheuristic algorithm design

## Domain-Specific Tools

### ReEvo (Combinatorial Optimization)
- **Repo:** [ai4co/reevo](https://github.com/ai4co/reevo)
- **Description:** Evolve heuristics for TSP, VRP, bin packing, etc.

### EvoPrompt (Prompt Optimization)
- **Repo:** [beeevita/EvoPrompt](https://github.com/beeevita/EvoPrompt)
- **Description:** GA/DE-based prompt evolution

### OPRO (Prompt Optimization)
- **Repo:** [google-deepmind/opro](https://github.com/google-deepmind/opro)
- **Description:** LLM-as-optimizer for prompts

### EoH (Heuristic Design)
- **Repo:** [FeiLiu36/EoH](https://github.com/FeiLiu36/EoH)
- **Description:** Dual thought+code heuristic evolution

### Eureka (Reward Design)
- **Repo:** [eureka-research/Eureka](https://github.com/eureka-research/Eureka)
- **Description:** Evolving reward functions for robotics RL

### Darwin Godel Machine (Self-Improving Agents)
- **Repo:** [jennyzzt/dgm](https://github.com/jennyzzt/dgm)
- **Description:** Agents that evolve their own source code

### AI Scientist (Scientific Discovery)
- **Repo:** [SakanaAI/AI-Scientist](https://github.com/SakanaAI/AI-Scientist)
- **Repo v2:** [SakanaAI/AI-Scientist-v2](https://github.com/SakanaAI/AI-Scientist-v2)
- **Description:** Autonomous research agent

## QD Algorithm Libraries

### pyribs
- **Repo:** [icaros-usc/pyribs](https://github.com/icaros-usc/pyribs)
- **Description:** Quality-Diversity optimization library (MAP-Elites, etc.)
- **Note:** Not LLM-specific but commonly used as a foundation

## Results-Only Repositories

### AlphaEvolve Results
- **Repo:** [google-deepmind/alphaevolve_results](https://github.com/google-deepmind/alphaevolve_results)
- **Description:** Mathematical discoveries + verification notebooks

### AlphaEvolve Problems
- **Repo:** [google-deepmind/alphaevolve_repository_of_problems](https://github.com/google-deepmind/alphaevolve_repository_of_problems)
- **Description:** 67 mathematical problem definitions used in experiments

## Getting Started Guide

**If you want to...**

| Goal | Recommended Tool |
|---|---|
| Evolve programs/algorithms | OpenEvolve or ShinkaEvolve |
| Optimize prompts | EvoPrompt or OPRO |
| Design heuristics for optimization | ReEvo or EoH |
| Search neural architectures | LLMatic |
| Design reward functions | Eureka |
| Explore general QD+LLM | OpenELM |
| Build from scratch | pyribs + your own LLM integration |
