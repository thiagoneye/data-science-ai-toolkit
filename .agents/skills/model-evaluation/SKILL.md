---
name: model-evaluation
description: Evaluate regression/classification/surrogate models with robust error analysis.
---

# Model Evaluation

## When to use

Use for evaluate regression/classification/surrogate models with robust error analysis.

## Workflow

1. Confirm holdout criteria and metrics defined before training.
2. Compute baseline comparisons and stratified/group-level metrics.
3. Inspect error distribution, failures and extrapolation regions.
4. Quantify uncertainty when supported by experiment design.
5. Publish plots and conclusions with limitations.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Reproducible metrics, error plots, evaluation memo.
