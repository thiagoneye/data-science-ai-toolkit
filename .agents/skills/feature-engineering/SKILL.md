---
name: feature-engineering
description: Engineer features and leakage-free preprocessing for prediction tasks.
---

# Feature Engineering

## When to use

Use for engineer features and leakage-free preprocessing for prediction tasks.

## Workflow

1. Specify prediction horizon and what is available at inference time.
2. Define split before fitting any transforms.
3. Select encodings/scaling appropriate to model and domain.
4. Fit transforms only within training fold; apply to validation/test.
5. Document feature lineage, ablations and drift risks.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Feature spec, transformation pipeline, tests.
