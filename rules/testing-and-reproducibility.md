# Testing and reproducibility

- Write unit tests for parsing and transformations; integration tests for pipelines.
- Use small synthetic fixtures without leaking production datasets.
- Pin tools or lock environment; provide commands and expected outputs.
- Track seeds, dataset hashes, code commit, experiment configs and software versions.
- Validate negative cases, schema drift and idempotent reruns.
- Avoid testing via live external services unless explicitly approved.
