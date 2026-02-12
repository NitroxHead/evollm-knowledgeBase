# The AI Scientist

**Organization:** Sakana AI, University of Oxford, University of British Columbia
**Year:** 2024
**Status:** Open-sourced

## Overview

The AI Scientist is a fully autonomous system for open-ended scientific discovery. While not purely evolutionary, it uses iterative self-improvement loops akin to evolution -- generating research ideas, running experiments, analyzing results, and writing papers in a loop.

## Pipeline

```
Idea Generation → Experiment Design → Code Writing → Execution →
Analysis → Paper Writing → Self-Review → Iterate
```

### v2 Improvements

AI Scientist v2 uses **agentic tree search** for more autonomous exploration:
- Branching exploration of research directions
- Self-evaluation and pruning of unproductive paths
- More sophisticated experiment management

## Results

- v1: Generated papers rated **"Weak Accept"** quality by automated reviewers
- v2: Produced the **first entirely AI-generated peer-review-accepted workshop paper**

## Repositories

- [SakanaAI/AI-Scientist](https://github.com/SakanaAI/AI-Scientist) (v1)
- [SakanaAI/AI-Scientist-v2](https://github.com/SakanaAI/AI-Scientist-v2) (v2)

## Key People

- **Chris Lu** -- Lead researcher
- **David Ha** -- Sakana AI founder

## Relevance to LLM+Evolution

While the AI Scientist doesn't use explicit evolutionary algorithms, its iterative research loop mirrors evolutionary principles:
- **Variation**: Generating diverse research ideas
- **Selection**: Self-review and filtering
- **Iteration**: Refining based on experimental feedback

It also represents a potential **application** of LLM+evolution systems -- using evolved algorithms within autonomous scientific discovery.

## See Also

- [Darwin Godel Machine](darwin-godel-machine.md) -- Self-improving agent (more explicitly evolutionary)
- [ShinkaEvolve](shinkaevolve.md) -- Explicit evolutionary framework by same org
