---
name: cfd-data-processing
description: Inspect and extract OpenFOAM meshes, fields and solver outputs for analytics.
---

# Cfd Data Processing

## When to use

Use for inspect and extract OpenFOAM meshes, fields and solver outputs for analytics.

## Workflow

1. Identify case layout, solver, version and file formats.
2. Inspect mesh geometry, cell/point fields, boundaries and write times.
3. Extract coefficients and fields without modifying source cases.
4. Validate physical units, indexing, coordinate frames and temporal alignment.
5. Export structured datasets with case IDs and source provenance.

## Guardrails

- Do not modify raw data or access unauthorized files.
- Never invent measurements, citations, metrics, or test results.
- Honor the repository `AGENTS.md` and relevant `rules/` guidance.
- Use English identifiers/docstrings and Portuguese explanatory code comments.

## Expected outputs

Extraction plan/script, schema, validation diagnostics.
