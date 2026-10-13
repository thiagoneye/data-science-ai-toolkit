---
name: dataset-profiling
description: Profile structured datasets, schemas, missing values, duplicates, and distribution anomalies before modeling.
---

# Dataset Profiling

## When to use

Use for profile structured datasets, schemas, missing values, duplicates, and distribution anomalies before modeling.

## Workflow

1. Confirm authorized dataset location, size, format and target.
2. Sample when necessary; profile entire dataset with streaming SQL if practical.
3. Report row counts, types, missing values, uniqueness, duplicates and ranges.
4. Check group/time coverage and flag suspicious distributions.
5. Write a reproducible report with clearly labeled limitations.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Schema and quality profile, reproducible query/code, key warnings.
