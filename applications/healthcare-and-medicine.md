# Applied Results: Healthcare & Medicine

Papers where LLM+evolution methods designed or optimized clinical decision pipelines and medical workflows.

---

## Medical Decision Pipelines (LLM-Guided Evolution)

**Problem:** Adapting LLMs to clinical workflows usually requires costly fine-tuning or manual prompt/pipeline engineering. Can inference-time evolution discover effective medical decision strategies instead?

**Approach:** LLM-guided **MAP-Elites** evolution over executable artifacts (programs, prompts, pipelines), optimized by task-specific fitness functions. Three clinical tasks are cast as evolutionary searches: urgency triage, interactive consultation, and medical image classification.

| Task | Result |
|---|---|
| Urgency triage | Semigran accuracy **77.3% → 87.1%**; emergency recall **0.60 → 0.97**; improved safety-weighted held-out MIMIC-ESI performance |
| Interactive consultation | Improves the accuracy–cost frontier across Llama-3, Qwen-3.5, Gemma-4; transfers to held-out iCRAFTMD |
| Medical image classification (PneumoniaMNIST) | Prompt-only evolution improves frozen MedGemma VLMs while preserving strict JSON output |

**Key insight:** Gains come from **interpretable program-level mechanisms** -- calibrated triage boundaries, targeted evidence acquisition, selective commitment, finding-oriented visual decision rules -- rather than superficial prompt rewording alone.

**Paper:** Sviridov, Oskin, Panin, Bespalov, Dylov, Oseledets, Nesterov, "LLM-Guided Evolution for Medical Decision Pipelines," arXiv:[2606.07342](https://arxiv.org/abs/2606.07342), 2026. Repository: [univanxx/llm_guided_evo_medical](https://github.com/univanxx/llm_guided_evo_medical).

**Method:** MAP-Elites over executable decision artifacts (see [Evolutionary Frameworks](../taxonomy/evolutionary-frameworks.md)); inference-time alternative to fine-tuning.

---

## Summary

| Task | Method | Key Achievement |
|---|---|---|
| Clinical triage / consultation / imaging | LLM-guided MAP-Elites | Triage accuracy 77.3% → 87.1%, emergency recall 0.60 → 0.97; interpretable decision rules |
