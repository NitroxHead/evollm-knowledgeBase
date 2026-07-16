# EvoLLM Knowledge Base

A knowledge base for **LLM-based Evolution** -- projects that combine Large Language Models with evolutionary algorithms to solve problems, and the real-world results they have achieved.

## What is LLM-based Evolution?

LLM-based evolution replaces traditional genetic operators (random mutation, syntactic crossover) with LLM-powered semantic operators. Instead of randomly perturbing code or solutions, an LLM proposes meaningful variations based on its understanding of the problem domain. An evolutionary loop then selects, evaluates, and iterates on these candidates.

```
┌─────────────────────────────────────────────────────┐
│                 Evolutionary Loop                    │
│                                                     │
│  ┌──────────┐    ┌──────────┐    ┌──────────────┐  │
│  │  Prompt   │───>│   LLM    │───>│  Evaluator   │  │
│  │  Sampler  │    │ Ensemble │    │  (Fitness)   │  │
│  └──────────┘    └──────────┘    └──────────────┘  │
│       ▲                                │            │
│       │          ┌──────────┐          │            │
│       └──────────│ Programs │<─────────┘            │
│                  │ Database │                       │
│                  └──────────┘                       │
└─────────────────────────────────────────────────────┘
```

## Repository Structure

```
.
├── README.md
├── projects/                 # Methods & tools (24 profiles)
│   ├── alphaevolve.md        #   Google DeepMind
│   ├── funsearch.md          #   Google DeepMind
│   ├── elm.md                #   OpenAI (foundational)
│   ├── shinkaevolve.md       #   Sakana AI
│   ├── reevo.md              #   Peking U / KAIST
│   ├── evoprompt.md          #   Tsinghua / Microsoft
│   ├── evoprompting.md       #   Google Brain
│   ├── promptbreeder.md      #   Google DeepMind
│   ├── opro.md               #   Google DeepMind
│   ├── openelm.md            #   CarperAI
│   ├── openevolve.md         #   Community
│   ├── llmatic.md            #   NYU et al.
│   ├── eureka.md             #   NVIDIA
│   ├── eoh.md                #   CityU HK
│   ├── llamea.md             #   Leiden University
│   ├── darwin-godel-machine.md  # Sakana AI
│   ├── evo-model-merge.md    #   Sakana AI
│   ├── ai-scientist.md       #   Sakana AI
│   ├── gepa.md               #   UC Berkeley / Stanford (prompt evolution)
│   ├── evox.md               #   UC Berkeley (meta-evolution)
│   ├── levi.md               #   Independent (sample-efficient)
│   ├── code-evolve.md        #   Salesforce (multi-language code optimization)
│   ├── mlevolve.md           #   Shanghai AI Lab (self-evolving MLE / algorithm discovery)
│   └── famou.md              #   Baidu (adversarial-game strategy evolution)
│
├── applications/             # Applied results by domain (30+ papers)
│   ├── mathematics.md        #   Cap sets, matrix mult, kissing number, packing...
│   ├── algorithms-and-sat.md #   SAT solvers, complexity theory, kernel optimization
│   ├── combinatorial-optimization.md  # TSP, bin packing, VRP, scheduling
│   ├── systems-infrastructure.md      # Data centers, TPU design, ML training
│   ├── scientific-discovery.md        # Materials, drug discovery, photonics
│   ├── robotics-and-rl.md    #   Reward design, robot morphology
│   ├── neural-architecture-search.md  # NAS, model merging, alignment
│   ├── competitive-programming.md     # ICFP, Hash Code, AtCoder, SWE-bench
│   ├── finance.md              #   Quantitative trading strategy optimization
│   └── healthcare-and-medicine.md     # Clinical decision pipelines
│
├── taxonomy/                 # Classification and conceptual frameworks
│   ├── overview.md           #   Three integration directions
│   ├── approaches.md         #   LLM roles (mutation, crossover, evaluator...)
│   ├── evolutionary-frameworks.md  # MAP-Elites, island models, GA, DE, CMA-ES
│   └── application-domains.md     # Domain overview with key results
│
├── comparisons/              # Cross-project comparisons
│   ├── comparison-table.md   #   Side-by-side tables
│   └── mechanism-advantages.md  #   When each evolutionary mechanism gives an edge
│
└── resources/                # Surveys, tools, and open problems
    ├── surveys.md            #   Academic survey papers
    ├── open-source.md        #   Available implementations
    └── challenges.md         #   Unsolved problems and research directions
```

## Quick Navigation

### Applied Results (What problems have been solved?)

| Domain | Highlights | Link |
|---|---|---|
| Mathematics | Matrix multiplication (broke 56-year record), cap sets, kissing number, packing | [applications/mathematics.md](applications/mathematics.md) |
| Algorithms & SAT | SAT solvers beating competition winners, FlashAttention 32.5% speedup | [applications/algorithms-and-sat.md](applications/algorithms-and-sat.md) |
| Combinatorial Optimization | TSP, bin packing, VRP, scheduling -- outperforming human heuristics | [applications/combinatorial-optimization.md](applications/combinatorial-optimization.md) |
| Systems & Infrastructure | 0.7% of Google's compute recovered, TPU design, 13x load balancing | [applications/systems-infrastructure.md](applications/systems-infrastructure.md) |
| Scientific Discovery | Drug molecules, materials design, photonics, macromolecular design | [applications/scientific-discovery.md](applications/scientific-discovery.md) |
| Robotics & RL | Pen spinning, reward design (83% beat human experts), walking robots | [applications/robotics-and-rl.md](applications/robotics-and-rl.md) |
| Neural Architecture Search | SOTA on 21/30 algorithmic reasoning tasks, model merging | [applications/neural-architecture-search.md](applications/neural-architecture-search.md) |
| Competitive Programming | 1st place ICFP 2025, beat Hash Code top human score | [applications/competitive-programming.md](applications/competitive-programming.md) |
| Finance & Quant Trading | Verifier-guided strategy optimization (Sharpe -0.3 → 0.54), evolved trading programs | [applications/finance.md](applications/finance.md) |
| Healthcare & Medicine | Clinical triage accuracy 77% → 87%, interpretable decision pipelines | [applications/healthcare-and-medicine.md](applications/healthcare-and-medicine.md) |

### Methods & Tools (How do they work?)

#### By Organization

| Organization | Projects |
|---|---|
| Google DeepMind | [AlphaEvolve](projects/alphaevolve.md), [FunSearch](projects/funsearch.md), [Promptbreeder](projects/promptbreeder.md), [OPRO](projects/opro.md) |
| Sakana AI | [ShinkaEvolve](projects/shinkaevolve.md), [Darwin Godel Machine](projects/darwin-godel-machine.md), [Evo Model Merge](projects/evo-model-merge.md), [AI Scientist](projects/ai-scientist.md) |
| OpenAI / CarperAI | [ELM](projects/elm.md), [OpenELM](projects/openelm.md) |
| NVIDIA | [Eureka](projects/eureka.md) |
| UC Berkeley / Stanford | [GEPA](projects/gepa.md), [EvoX](projects/evox.md) |
| Salesforce | [CodeEvolve](projects/code-evolve.md) |
| Shanghai AI Lab | [MLEvolve](projects/mlevolve.md) |
| Baidu | [FAMOU](projects/famou.md) |
| Academia | [ReEvo](projects/reevo.md), [EvoPrompt](projects/evoprompt.md), [EoH](projects/eoh.md), [LLMatic](projects/llmatic.md), [LLaMEA](projects/llamea.md), [EvoPrompting](projects/evoprompting.md) |
| Community / Independent | [OpenEvolve](projects/openevolve.md), [LEVI](projects/levi.md) |

#### By What Is Being Evolved

| Category | Projects |
|---|---|
| Programs / Algorithms | [AlphaEvolve](projects/alphaevolve.md), [FunSearch](projects/funsearch.md), [ShinkaEvolve](projects/shinkaevolve.md), [ELM](projects/elm.md), [LLaMEA](projects/llamea.md), [EoH](projects/eoh.md), [CodeEvolve](projects/code-evolve.md), [LEVI](projects/levi.md), [MLEvolve](projects/mlevolve.md), [FAMOU](projects/famou.md) |
| Heuristics for Optimization | [ReEvo](projects/reevo.md), [EoH](projects/eoh.md) |
| Text Prompts | [EvoPrompt](projects/evoprompt.md), [Promptbreeder](projects/promptbreeder.md), [OPRO](projects/opro.md), [GEPA](projects/gepa.md) |
| Neural Architectures | [EvoPrompting](projects/evoprompting.md), [LLMatic](projects/llmatic.md) |
| Reward Functions | [Eureka](projects/eureka.md) |
| Models Themselves | [Evo Model Merge](projects/evo-model-merge.md) |
| Agent Source Code (Self) | [Darwin Godel Machine](projects/darwin-godel-machine.md) |
| Search Strategy Itself (Meta) | [EvoX](projects/evox.md) |

### Conceptual Resources

- [Taxonomy Overview](taxonomy/overview.md) -- How LLMs and evolution intersect
- [Approaches](taxonomy/approaches.md) -- LLM roles in evolutionary computation
- [Evolutionary Frameworks](taxonomy/evolutionary-frameworks.md) -- GA, MAP-Elites, island models, etc.
- [Application Domains](taxonomy/application-domains.md) -- Domain overview with key results
- [Comparison Table](comparisons/comparison-table.md) -- Side-by-side project comparison
- [Mechanism Advantages](comparisons/mechanism-advantages.md) -- Which evolutionary mechanism gives an edge and when
- [Survey Papers](resources/surveys.md) -- Academic surveys on the field
- [Open Source Tools](resources/open-source.md) -- Available implementations
- [Open Challenges](resources/challenges.md) -- Unsolved problems in the field

## Headline Results

| Achievement | Method | Year |
|---|---|---|
| Broke Strassen's 56-year matrix multiplication record | AlphaEvolve | 2025 |
| First LLM-driven mathematical discovery (Nature) | FunSearch | 2024 |
| 0.7% of Google's worldwide compute recovered | AlphaEvolve | 2025 |
| 1st place ICFP Programming Contest | ShinkaEvolve | 2025 |
| Beat SAT competition winners (evolved 10K+ lines) | SATLUTION | 2025 |
| 83% of RL tasks beat human expert rewards | Eureka | 2024 |
| Surpassed Hash Code top human score | EvoTune | 2025 |
| SWE-bench 20% → 50% via self-modification | Darwin Godel Machine | 2025 |
| Silver Humies Award (human-competitive results) | LLaMEA | 2025 |
| 8% drug molecule optimization improvement | Chemlactica | 2025 |
| New lower bounds for 9 classical Ramsey numbers | AlphaEvolve | 2026 |
| 3 new exact + 41 improved Zarankiewicz numbers (<$30 each) | OpenEvolve | 2026 |
| 5.3% IPC speedup on SOTA cache replacement policy | ArchAgent (AlphaEvolve) | 2026 |
| Outperforms AlphaEvolve/OpenEvolve/GEPA/ShinkaEvolve on majority of ~200 tasks | EvoX | 2026 |
| 35x cost reduction vs frontier-LLM frameworks | LEVI | 2026 |
| GEPA outperforms GRPO (RL) on 6 tasks with 35x fewer rollouts | GEPA | 2025 |
| SOTA on MLE-Bench in half the runtime; beats AlphaEvolve on math tasks | MLEvolve | 2026 |
| 1st place (hardware) at AAMAS 2026 MCTF adversarial-game competition | FAMOU | 2026 |

## Timeline

```
2022  ── ELM (OpenAI) ─── First formal proposal of LLMs as mutation operators
  │
2023  ── FunSearch (DeepMind) ─── First mathematical discoveries via LLM+evolution
  │   ── OPRO, Promptbreeder, EvoPrompt ─── Prompt evolution wave
  │   ── EvoPrompting ─── LLM-guided neural architecture search
  │   ── Eureka (NVIDIA) ─── Evolving reward functions for RL
  │
2024  ── FunSearch published in Nature ─── Field gains mainstream recognition
  │   ── ReEvo ─── Reflective evolution for heuristic design
  │   ── EoH ─── Dual thought+code evolution
  │   ── LLaMEA ─── Automated metaheuristic design
  │   ── Evo Model Merge (Sakana AI) ─── Evolving model merge recipes
  │   ── AI Scientist (Sakana AI) ─── Autonomous scientific discovery
  │   ── DiscoPOP ─── Evolving LLM alignment algorithms
  │
2025  ── AlphaEvolve (DeepMind) ─── Full-codebase evolution, production impact
  │   ── ShinkaEvolve (Sakana AI) ─── Sample-efficient, ICFP 1st place
  │   ── Darwin Godel Machine ─── Self-improving agents
  │   ── SATLUTION (NVIDIA) ─── Evolved SAT solvers beat competition
  │   ── OpenEvolve ─── Open-source AlphaEvolve reimplementation
  │   ── AlphaEvolve + Terence Tao ─── 67 open math problems
  │   ── Systems applications (UC Berkeley) ─── <$10 for 13x speedups
  │   ── Chemlactica ─── Drug discovery via LLM+evolution
  │   ── GEPA (UC Berkeley) ─── Prompt evolution beats RL with 35x fewer rollouts
  │
2026  ── TTT-Discover ─── New SOTA on Erdos overlap + autocorrelation
  │   ── EvoX (UC Berkeley) ─── Meta-evolution dominates prior frameworks
  │   ── LEVI ─── Sample-efficient: 3-6x cheaper than frontier baselines
  │   ── AlphaEvolve Ramsey numbers ─── 9 improved classical lower bounds
  │   ── OpenEvolve Zarankiewicz ─── 3 exact + 41 improved bounds at <$30 each
  │   ── ArchAgent ─── SOTA cache replacement policy in 2 days
  │   ── Salesforce CodeEvolve ─── 15x speedup on enterprise Java hotspots
  │   ── AI CFD Scientist / CMBEvolve / CVEvolve ─── New scientific-discovery domains
  │   ── MARL discovery ─── 4 new CFR/PSRO algorithms via AlphaEvolve
  │   ── MLEvolve (Shanghai AI Lab) ─── SOTA MLE-Bench via graph search; beats AlphaEvolve on math
  │   ── FAMOU (Baidu) ─── Co-evolution wins AAMAS 2026 adversarial-game competition
  │   ── LLaMEA-MOBO / QDEvo / GAE / MeEvo / RAISE / SeaEvo ─── Algorithm-design and heuristic-QD advances
  │   ── "Dictionaries, Not Darwin" ─── Critical audit: evolution ≈ fresh sampling in equation discovery
  │   ── Darwin Family / EvoPref / Evolution Fine-Tuning ─── Evolution turns on the LLM itself (merging, alignment, mid-training)
  │   ── AlgoEvolve / MadEvolve ─── Evolved trading programs; new EDA results (Kernel Foundry, MappingEvolve)
  │   ── LLM-Guided Evolution (medical) / SCE (quantum LDPC codes) ─── New healthcare and quantum-EC domains
```

## Contributing

This knowledge base is actively maintained. Contributions welcome via pull requests.

## License

This knowledge base is provided under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
