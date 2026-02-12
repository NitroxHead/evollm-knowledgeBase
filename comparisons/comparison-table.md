# Project Comparison Table

## Full Comparison

| Project | Org | Year | What Evolves | Evo Framework | LLM Used | Open Source | Venue |
|---|---|---|---|---|---|---|---|
| [ELM](../projects/elm.md) | OpenAI | 2022 | Code (programs) | MAP-Elites | GPT-series | Yes (CarperAI) | arXiv/Springer |
| [FunSearch](../projects/funsearch.md) | DeepMind | 2023 | Functions (code) | Island Model | Codey/PaLM 2 | Yes | Nature |
| [EvoPrompting](../projects/evoprompting.md) | Google Brain | 2023 | Neural architectures | GA-style | GPT-3.5/4 | No | NeurIPS 2023 |
| [EvoPrompt](../projects/evoprompt.md) | Tsinghua/MSFT | 2023 | Text prompts | GA + DE | GPT-3.5/Alpaca | Yes | ICLR 2024 |
| [Promptbreeder](../projects/promptbreeder.md) | DeepMind | 2023 | Prompts + meta-prompts | Custom meta-EA | PaLM 2 | No | ICML 2024 |
| [OPRO](../projects/opro.md) | DeepMind | 2023 | Prompts/solutions | (1+1)-like | GPT-4/PaLM 2 | Yes | ICLR 2024 |
| [Eureka](../projects/eureka.md) | NVIDIA | 2023 | Reward functions | Iterative refinement | GPT-4 | Yes | ICLR 2024 |
| [ReEvo](../projects/reevo.md) | Peking U/KAIST | 2024 | Heuristics (code) | EA + Reflection | GPT-4/Claude | Yes | NeurIPS 2024 |
| [EoH](../projects/eoh.md) | CityU HK | 2024 | Heuristics (thought+code) | EA | GPT-4 | Yes | ICML 2024 |
| [LLMatic](../projects/llmatic.md) | NYU et al. | 2023 | Neural architectures | MAP-Elites (2-arch) | CodeGen | Yes | GECCO 2024 |
| [LLaMEA](../projects/llamea.md) | Leiden U | 2024 | Metaheuristic algorithms | (1+1) ES | GPT-4 | Yes | IEEE TEVC |
| [Evo Model Merge](../projects/evo-model-merge.md) | Sakana AI | 2024 | Model merge recipes | CMA-ES | N/A (merging) | No | Nature MI |
| [AI Scientist](../projects/ai-scientist.md) | Sakana AI | 2024 | Research ideas | Iterative | Claude/GPT-4 | Yes | arXiv |
| [AlphaEvolve](../projects/alphaevolve.md) | DeepMind | 2025 | Full codebases | MAP-Elites + Islands | Gemini ensemble | No (results) | arXiv |
| [ShinkaEvolve](../projects/shinkaevolve.md) | Sakana AI | 2025 | Programs (code) | Adaptive sampling | Ensemble (bandit) | Yes | arXiv |
| [Darwin Godel Machine](../projects/darwin-godel-machine.md) | Sakana AI | 2025 | Agent source code | MAP-Elites | Foundation models | Yes | arXiv |
| [OpenEvolve](../projects/openevolve.md) | Community | 2025 | Code (AlphaEvolve clone) | MAP-Elites + Islands | Any (OpenAI API) | Yes | -- |
| [OpenELM](../projects/openelm.md) | CarperAI | 2023 | Code/prompts (library) | MAP-Elites | Any (LangChain) | Yes | Workshop |

## By Scale of Impact

### Production / Real-World Impact
1. **AlphaEvolve** -- Running in Google production (Borg, TPU, Gemini training)
2. **Eureka** -- Demonstrated human-level reward design for robotics
3. **Evo Model Merge** -- Produced SOTA models published on HuggingFace

### Academic Breakthroughs
1. **FunSearch** -- Published in Nature, first LLM-driven math discovery
2. **AlphaEvolve** -- Improved on Strassen's algorithm after 56 years
3. **ShinkaEvolve** -- Won ICFP 2025 Programming Contest

### Framework / Tool Impact
1. **OpenEvolve** -- Most accessible open implementation of AlphaEvolve
2. **OpenELM** -- General-purpose QD+LLM library
3. **ReEvo** -- Ready-to-use heuristic evolution for combinatorial optimization

## By Sample Efficiency

| Project | Evaluations to SOTA | Compute Cost |
|---|---|---|
| ShinkaEvolve | ~150 | Low |
| EoH | Hundreds | Low-Medium |
| LLaMEA | Hundreds | Low-Medium |
| ReEvo | Hundreds-Thousands | Medium |
| FunSearch | Thousands-Millions | High |
| AlphaEvolve | Thousands+ | Very High |

## By Openness

### Fully Open Source
ELM/OpenELM, FunSearch, EvoPrompt, OPRO, ReEvo, EoH, LLaMEA, Eureka, ShinkaEvolve, Darwin Godel Machine, AI Scientist, OpenEvolve

### Partially Open (Results/Problems Only)
AlphaEvolve

### Closed
Promptbreeder, EvoPrompting, Evo Model Merge (paper only)
