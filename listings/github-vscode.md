# GitHub MCP Registry (github.com/mcp) and VS Code MCP gallery

Endpoint: `https://api.chatacademia.com/mcp/vscode`

1. Publish to the official MCP Registry first (see `mcp-registry.md`). GitHub's registry only carries servers that are
   in the official registry, and it is curated.
2. Send `emails/github-partnerships.md` to partnerships@github.com (still the documented path, GitHub blog 2025-10-24;
   no self-publish found as of 2026-11-26).

Note: an entry pulled from the official registry would carry the `/mcp/registry` URL from server.json. The
`/mcp/vscode` URL is used by our own install links below; ask GitHub in the email whether they can show it.

## Install links (README "Install in VS Code")

- Web (works in browsers and GitHub READMEs, 302s to the app; tested 2026-11-26):
  `https://vscode.dev/redirect/mcp/install?name=chatacademia&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fvscode%22%7D`
  (add `&quality=insiders` for VS Code Insiders)
- Direct: `vscode:mcp/install?%7B%22name%22%3A%22chatacademia%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fvscode%22%7D`
- After the registry listing: `vscode:mcp/by-name/com.chatacademia/chatacademia` (opens the gallery entry; uses the registry URL).
- Manual `.vscode/mcp.json`: `{"servers":{"chatacademia":{"type":"http","url":"https://api.chatacademia.com/mcp/vscode"}}}`
