# OpenELM

**Organization:** CarperAI (LAION affiliate)
**Year:** 2023
**Status:** Open-sourced

## Overview

OpenELM is an open-source Python library implementing the ideas from the ELM paper. It provides a framework for evolutionary search with language models, making it easy to run MAP-Elites and other quality-diversity algorithms with LLM-powered variation operators.

## Features

- Built on **LangChain** for LLM integration
- **MAP-Elites** as default quality-diversity algorithm
- Generic environments for evolving:
  - Text prompts
  - Code/programs
  - Other text-based genotypes
- Supports any LLM API via LangChain (OpenAI, HuggingFace, local models)
- Modular design: swap LLMs, environments, and QD algorithms

## Paper

**"The OpenELM Library: Leveraging Progress in Language Models for Novel Evolutionary Algorithms"**
Workshop paper, OpenReview

## Repository

[CarperAI/OpenELM](https://github.com/CarperAI/OpenELM)

## See Also

- [ELM](elm.md) -- The foundational paper OpenELM implements
- [OpenEvolve](openevolve.md) -- AlphaEvolve-focused reimplementation
