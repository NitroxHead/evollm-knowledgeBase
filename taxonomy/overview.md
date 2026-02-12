# Taxonomy Overview: LLMs + Evolution

## The Three Integration Directions

LLMs and evolutionary algorithms can be integrated in three fundamental ways:

```
                    LLM + Evolution Integration
                            │
            ┌───────────────┼───────────────┐
            │               │               │
     ┌──────▼──────┐ ┌─────▼──────┐ ┌──────▼──────┐
     │ LLM Enhances│ │EA Enhances │ │Co-Evolution │
     │     EA       │ │    LLM     │ │             │
     └──────┬──────┘ └─────┬──────┘ └──────┬──────┘
            │               │               │
    ┌───────┼───────┐      │        ┌──────┼──────┐
    │       │       │      │        │             │
 Variation Eval  Repr.  Prompts  Self-       Algorithm+
 Operators       & Init  & Arch.  Improving   Prompt
                         Search   Systems     Co-Evol.
```

### Direction 1: LLM Enhances EA

The LLM serves as a component within an evolutionary algorithm:

| Role | Description | Example Projects |
|---|---|---|
| **Mutation Operator** | LLM generates semantically meaningful code/text variations | AlphaEvolve, FunSearch, ELM, ShinkaEvolve |
| **Crossover Operator** | LLM combines elements from parent solutions | EvoPrompt, Language Model Crossover |
| **Fitness Evaluator** | LLM assesses quality as a surrogate fitness function | QDAIF |
| **Initialization** | LLM generates high-quality initial population | Most systems use this implicitly |

### Direction 2: EA Enhances LLM

Evolutionary algorithms optimize aspects of LLM systems:

| Target | Description | Example Projects |
|---|---|---|
| **Prompt Optimization** | EA evolves prompts for better LLM performance | EvoPrompt, OPRO, Promptbreeder |
| **Architecture Search** | EA discovers neural network architectures via LLM code | EvoPrompting, LLMatic |
| **Model Merging** | EA finds optimal recipes for combining pretrained models | Evo Model Merge |
| **Reward Design** | EA evolves reward functions for RL training | Eureka |

### Direction 3: Co-Evolution

LLMs and evolutionary processes improve each other simultaneously:

| Type | Description | Example Projects |
|---|---|---|
| **Self-Improving Systems** | Agent evolves its own code | Darwin Godel Machine |
| **LLM Fine-tuning Loop** | Evolved outputs fine-tune the LLM for better mutations | ELM (bootstrapping) |
| **Thought+Code Co-Evolution** | Natural language reasoning and code evolve together | EoH |

## What Gets Evolved

```
┌─────────────────────────────────────────────────────────┐
│                   What Gets Evolved                      │
│                                                         │
│  Programs/Code ──── AlphaEvolve, FunSearch, ShinkaEvolve│
│       │                                                 │
│  Heuristics ──────── ReEvo, EoH, LLaMEA                │
│       │                                                 │
│  Text Prompts ────── EvoPrompt, Promptbreeder, OPRO    │
│       │                                                 │
│  Neural Archs ────── EvoPrompting, LLMatic             │
│       │                                                 │
│  Reward Functions ── Eureka                            │
│       │                                                 │
│  Models ──────────── Evo Model Merge                   │
│       │                                                 │
│  Agents (Self) ───── Darwin Godel Machine              │
└─────────────────────────────────────────────────────────┘
```

## See Also

- [Approaches](approaches.md) -- Detailed breakdown of LLM roles
- [Evolutionary Frameworks](evolutionary-frameworks.md) -- GA, MAP-Elites, etc.
- [Application Domains](application-domains.md) -- Where these are applied
