---
name: data-pipeline-engineering
description: Design reliable ETL/ELT and Medallion pipelines for Parquet and analytical datasets.
---

# Data Pipeline Engineering

## When to use

Use for design reliable ETL/ELT and Medallion pipelines for Parquet and analytical datasets.

## Workflow

1. Map sources, destinations and allowed access.
2. Define schema, contracts, provenance and partition strategy.
3. Implement isolated extraction, validation, transform and storage steps.
4. Add idempotency, logging, retries and checkpoint behavior.
5. Test repeat execution and malformed inputs.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Pipeline code/plan, contracts, tests, operating guide.
