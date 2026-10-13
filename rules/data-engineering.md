# Data engineering standards

- Use immutable raw/Bronze inputs; create derived Silver/Gold artifacts separately.
- Define and version data contracts: schema, nullability, primary identifiers, units and timestamps.
- Favor Parquet with explicit types and partition keys supported by actual queries.
- Make ingestion idempotent and record source provenance, checksum and processing status.
- Avoid partition explosion and excessive small Parquet files.
- Never silently discard malformed records; emit validation reports.
