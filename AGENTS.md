# Codex project instructions — Data Science Toolkit

## Communication and code
- Respond to the user in Brazilian Portuguese, unless the user requests another language.
- Use English for identifiers, filenames, functions, classes, type names, tests, and docstrings.
- Use Portuguese for explanatory comments inside source code.
- Prefer explicit assumptions and concise technical reporting.

## Operating discipline
- Inspect existing project structure before modifying it; make minimal, scoped changes.
- Treat raw datasets as immutable. Never overwrite source data.
- Never expose credentials or commit `.env`, secrets, raw private data, model weights, or large outputs.
- Ask for approval before destructive operations, installing new external tools, or accessing sensitive locations.
- Do not claim a command, test, query, or experiment succeeded without actual execution evidence.
- Favor `pyproject.toml`, isolated environments, pinned reproducible dependencies, and concise README instructions.

## Data science invariants
- Prevent train/validation/test leakage: fit transformations only on the training split.
- Choose data splits based on deployment goal (grouped cases, temporal windows, or IID as appropriate).
- Define representative baselines and evaluation metrics before complex modeling.
- Record data versions, seeds, environment, hyperparameters, and evaluation artifacts.
- Validate physical units, dimensions, coordinate frames and numerical tolerances for scientific datasets.
- Favor robust schema validation, stable IDs, and idempotent pipelines.
- Never invent empirical findings, scientific citations, or performance metrics.

## Domain rules
Read relevant documents before major work, using the task's domain:
- `rules/python-standards.md`
- `rules/data-engineering.md`
- `rules/data-quality.md`
- `rules/machine-learning.md`
- `rules/deep-learning.md`
- `rules/scientific-computing.md`
- `rules/testing-and-reproducibility.md`
- `rules/scientific-research.md`

## Skills
When a request matches a skill in `.agents/skills/`, read its `SKILL.md` and follow its workflow. Skills are guidance, not permission to access external services or modify unapproved resources.

## Deliverables
Summarize what changed, where it changed, tests performed, limitations, and next actionable steps. Include commands for reproduction when applicable.
