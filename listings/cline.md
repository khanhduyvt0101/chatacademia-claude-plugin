# Cline MCP Marketplace

Endpoint: `https://api.chatacademia.com/mcp/cline`

Files: `/llms-install.md` (repo root, agent-driven install), README section "Install in Cline",
`/assets/chatacademia-icon-400.png` (400×400 PNG).

**Before submitting:** (1) confirm `/mcp/cline` answers 401 with `WWW-Authenticate`; (2) Cline's OAuth callback is
`http://127.0.0.1:{1456..1461}/mcp/oauth/callback`, so our dynamic client registration must accept loopback redirect
URIs on those ports; (3) do one real install in Cline from `llms-install.md` (the template makes you tick that
you tested it).

Open an issue with template https://github.com/cline/mcp-marketplace/issues/new?template=mcp-server-submission.yml

- Title: `[Server Submission]: ChatAcademia (remote, OAuth)`
- GitHub Repository URL: `https://github.com/khanhduyvt0101/chatacademia-claude-plugin`
- Logo Image: `https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/chatacademia-icon-400.png`
- Installation Testing: [x] tested with README.md / llms-install.md · [x] stable and ready for public use
- Additional Information:

```
ChatAcademia is an AI research assistant for academics. This is our official hosted MCP server.

- Endpoint: https://api.chatacademia.com/mcp/cline (Streamable HTTP)
- Auth: OAuth 2.1 with PKCE and dynamic client registration. No API key and nothing to run locally;
  the repository holds configuration and docs only.
- Official MCP Registry: com.chatacademia/chatacademia
- Tools: scholarly paper search across major academic databases, citation verification, grant search,
  research questions and study design, research-gap analysis, data extraction with supporting passages,
  mock peer review, academic editing. 8 guided workflows as prompts.
- Requires a ChatAcademia account (7-day free trial, then paid plans with monthly credits).
- Tested with Cline <version> on <date>.
- Docs: https://www.chatacademia.com/claude · Privacy: https://www.chatacademia.com/privacy
```

Review is slow and selective (about 4,100 issues, many open).
