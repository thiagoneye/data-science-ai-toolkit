---
name: reproducibility-audit
description: Audit a data science project for repeatable results, dependencies and provenance.
---

# Reproducibility Audit

## When to use

Use for audit a data science project for repeatable results, dependencies and provenance.

## Workflow

1. Inventory source code, configs, environments and inputs.
2. Check dataset hashes, random seeds and data splits.
3. Inspect tests, tracking, evaluation isolation and leaked credentials.
4. Attempt minimal reproducibility checks only when authorized.
5. Rank findings by impact and propose precise remediations.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Audit report, reproduction instructions, prioritized fixes.
