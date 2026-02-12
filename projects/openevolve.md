# OpenEvolve

**Organization:** Community (Asankhaya Sharma / codelion)
**Year:** 2025
**Status:** Open-sourced, available on PyPI

## Overview

OpenEvolve is the most prominent open-source faithful reimplementation of Google DeepMind's AlphaEvolve system. It makes LLM-driven evolutionary code optimization accessible to the broader research community.

## Features

- Mirrors **AlphaEvolve architecture**: Prompt Sampler, LLM Ensemble, Evaluator Pool, Program Database
- Supports **multiple LLM backends** via OpenAI-compatible APIs:
  - Google Gemini
  - OpenAI GPT models
  - Local models (Ollama, vLLM, etc.)
- Available on **PyPI**: `pip install openevolve`
- Active development with multiple community forks

## Installation

```bash
pip install openevolve
```

## Repository

[codelion/openevolve](https://github.com/codelion/openevolve) (primary)

Also: `algorithmicsuperintelligence/openevolve`, `jamesahou/openevolve`

## Resources

- [HuggingFace blog post](https://huggingface.co/blog/codelion/openevolve) -- Detailed guide

## See Also

- [AlphaEvolve](alphaevolve.md) -- The system it reimplements
- [OpenELM](openelm.md) -- Older open-source framework based on ELM
