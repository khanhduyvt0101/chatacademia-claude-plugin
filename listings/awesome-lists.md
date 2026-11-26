# Awesome lists

Endpoint for all awesome lists: `https://api.chatacademia.com/mcp/awesome`

## punkpeye/awesome-remote-mcp-servers (active, merges daily)

Prerequisites: (1) a Glama connector page for ChatAcademia (comes from the official registry sync, or "Add Server" on
glama.ai); CI checks the badge resolves; (2) the account opening the PR stars the repo; (3) `/mcp/awesome` answers
`initialize` with 401 + `WWW-Authenticate` (CI calls it and classes it 🔐).

Category `### 🔬 Science & Research`, alphabetical. Replace `NAMESPACE/NAME` with the Glama connector path:

```md
- [ChatAcademia](https://www.chatacademia.com/claude) `https://api.chatacademia.com/mcp/awesome`
  [![ChatAcademia MCP connector](https://glama.ai/mcp/connectors/NAMESPACE/NAME/badges/score.svg)](https://glama.ai/mcp/connectors/NAMESPACE/NAME)
  🔐 - Search papers and grants, verify citations, find research gaps and get mock peer review for academics.
```

(description 102 chars, ≤120, ends with a period.) PR title: `Add ChatAcademia`.

## jaw9c/awesome-remote-mcp-servers (1000+ open PRs, 3 merges since May: low odds)

Alphabetical table row ("OAuth2.1" without 🔐 = supports DCR, which we do):

```md
| ChatAcademia | Scientific Research | `https://api.chatacademia.com/mcp/awesome` | OAuth2.1 | [ChatAcademia](https://www.chatacademia.com) |
```

## wong2/awesome-mcp-servers

Takes no PRs; use the mcpservers.org form (see `COPY.md`).
