---
name: ml-experiment-design
description: Plan machine learning experiments with appropriate splits, baselines and metrics.
---

# Ml Experiment Design

## When to use

Use for plan machine learning experiments with appropriate splits, baselines and metrics.

## Workflow

1. State target, unit of prediction and deployment objective.
2. Audit groups/time and potential leakage.
3. Choose grouped, temporal or IID validation based on deployment.
4. Define metrics, baseline models, seeds and computational budget.
5. Specify acceptance criteria and a test-set lock policy.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Experiment protocol and reproducibility checklist.
