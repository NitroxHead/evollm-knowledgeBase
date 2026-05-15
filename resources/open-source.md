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

### GEPA (Reflective Prompt Evolution)
- **Repo:** [gepa-ai/gepa](https://github.com/gepa-ai/gepa)
- **License:** Apache 2.0
- **Description:** Genetic-Pareto prompt evolution with natural-language reflection
- **Key Feature:** Outperforms GRPO with 35x fewer rollouts; integrated as `dspy.GEPA` in DSPy

### LEVI (Sample-Efficient Evolutionary Search)
- **Repo:** [ttanv/levi](https://github.com/ttanv/levi)
- **Description:** Diversity-first, mixed-model evolutionary framework
- **Key Feature:** 3-6x cost reduction vs frontier-LLM frameworks at matching quality

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

### MASPO (Joint Multi-Agent Prompt Optimization)
- **Repo:** [wangzx1219/MASPO](https://github.com/wangzx1219/MASPO)
- **Description:** Evolutionary beam search for joint prompt optimization across interacting agents in LLM multi-agent systems

### BehaveSim (Algorithmic Similarity for LLM-AAD)
- **Repo:** [RayZhhh/behavesim](https://github.com/RayZhhh/behavesim)
- **Description:** Measures algorithmic similarity via problem-solving trajectories (PSTrajs); integrates with FunSearch/EoH to promote behavioral diversity

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

## Benchmarks

### CreativeBench (Machine Creativity for Code)
- **Paper:** arXiv:[2603.11863](https://arxiv.org/abs/2603.11863)
- **Description:** Two subsets (Combo + Explore) targeting combinatorial vs exploratory creativity; uses executable code to distinguish creativity from hallucination via quality × novelty metric

### Metal-Sci (Apple Silicon Kernel Search)
- **Repo:** [vicgalle/metal-sci-kernels](https://github.com/vicgalle/metal-sci-kernels)
- **Description:** 10 scientific Apple Silicon Metal compute kernels (stencils, n-body, Boltzmann, MD, PDE, FFT) with roofline-anchored fitness; includes held-out generalization-size gate

### GAMBIT (Multi-Agent Adversarial Robustness)
- **Paper:** arXiv:[2605.09027](https://arxiv.org/abs/2605.09027)
- **Description:** Co-evolved imposter/detector benchmark for LLM multi-agent systems; 27,804 labeled instances spanning 240 imposter strategies

## Getting Started Guide

**If you want to...**

| Goal | Recommended Tool |
|---|---|
| Evolve programs/algorithms | OpenEvolve or ShinkaEvolve |
| Achieve frontier results at lower cost | LEVI or EvoX |
| Optimize prompts | GEPA (via DSPy), EvoPrompt, or OPRO |
| Design heuristics for optimization | ReEvo or EoH |
| Search neural architectures | LLMatic |
| Design reward functions | Eureka |
| Explore general QD+LLM | OpenELM |
| Build from scratch | pyribs + your own LLM integration |
