# Docker MCP Catalog (docker/mcp-registry)

Endpoint: `https://api.chatacademia.com/mcp/docker`

- PR content: copy `listings/docker/servers/chatacademia/` to `servers/chatacademia/` in a fork of docker/mcp-registry
  (`server.yaml` type remote + `oauth` + `dynamic.tools: true`, `tools.json` = `[]`, `readme.md` = docs link). Same shape
  as the existing granola-remote / notion-remote entries.
- Validated locally with their tool on a fresh clone (`go run ./cmd/validate --name chatacademia`): every check ✅
  (name, directory, title, prettier YAML, secrets, icon, dynamic tools, remote, OAuth); `go run ./cmd/catalog
  chatacademia` writes the catalog entry.
- PR title: `Add ChatAcademia remote server`. Body: one-liner + docs URL + "OAuth 2.1 with DCR; test credentials via
  the Docker form https://forms.gle/6Lw3nsvu2d6nFg8e6".
- Before submitting: owner should read Docker's terms (a submitter withdrew over an indemnification clause, PR #7597).
  Backlog is large (~3.6k open PRs, few merges), expect a long wait.
- Test (needs Docker Desktop MCP Toolkit, not on this box): `docker mcp catalog import ...`,
  `docker mcp oauth authorize chatacademia`, `docker mcp gateway run`.
