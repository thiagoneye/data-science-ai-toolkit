---
name: data-quality-validation
description: Establish dataset contracts and automated quality assertions.
---

# Data Quality Validation

## When to use

Use for establish dataset contracts and automated quality assertions.

## Workflow

1. Inventory expected schema, nullability, valid ranges and identifiers.
2. Create representative positive and negative fixtures.
3. Check duplication, integrity, chronology and units.
4. Generate machine-readable failures and a concise summary.
5. Define handling for quarantined and missing records.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Quality checks, test fixtures, validation report.
