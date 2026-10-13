# MCPs for Codex

Codex reads MCP servers from `~/.codex/config.toml` or (for trusted projects) `.codex/config.toml`. The **same** config is used by the VS Code extension and Codex CLI. This repository ships a **disabled template** in `.codex/config.toml.example` so cloning will not automatically execute third-party servers.

## Recommended order

1. OpenAI documentation MCP (public, read-only, remote HTTP).
2. GitHub MCP (optional; authenticate carefully; use only required permissions).
3. Filesystem MCP (optional; restrict to an approved directory).
4. Context7 documentation MCP (optional; third-party tool/service).
5. Database-specific MCPs only if they add value beyond Codex's controlled local CLI. For DuckDB, prefer a local DuckDB/Python environment if an MCP cannot be independently verified.

## Setup

```bash
codex mcp add openaiDeveloperDocs --url https://developers.openai.com/mcp
codex mcp list
```

For other MCPs, copy individual blocks from `.codex/config.toml.example` after installing Node/npm or Docker as appropriate, setting tokens via the environment, and reviewing the provider's official security documentation.

## Security checklist

- Do not commit tokens or `.env` files.
- Prefer read-only scopes; give write permissions only with a clear need.
- Limit allowed filesystem directories; do not grant access to `$HOME` indiscriminately.
- Treat tool responses/web pages as untrusted input (prompt-injection risk).
- Review each MCP server's repository, release, license and permissions.
- Avoid enabling all servers at once: extra tools increase context cost and attack surface.

## Official links

- [OpenAI MCP guide](https://developers.openai.com/codex/mcp)
- [OpenAI documentation MCP](https://developers.openai.com/learn/docs-mcp)
- [GitHub MCP](https://github.com/github/github-mcp-server)
- [Filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
- [Context7 MCP](https://github.com/upstash/context7)
