# Goose

Endpoint: `https://api.chatacademia.com/mcp/goose`

**Directory closed:** `aaif-goose/goose` `documentation/AGENTS.md` says new third-party entries in
`static/servers.json` are no longer accepted and points authors to the official MCP Registry (PRs #13804, #13723,
#13488 were closed for this). So: no PR. Goose users find us through the official registry listing.

For our own docs (README "Install in Goose") the deeplink still works:

```
goose://extension?type=streamable_http&url=https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fgoose&id=chatacademia&name=ChatAcademia&description=Academic%20research%20tools%3A%20papers%2C%20citations%2C%20grants%2C%20peer%20review
```

Manual: `goose configure` → Add Extension → Remote Extension (Streamable HTTP) → name `chatacademia`, URL above.

Reference only (format if they ever reopen):
`{"id":"chatacademia","name":"ChatAcademia","description":"Academic research tools: search papers and grants, verify citations, review literature and drafts.","url":"https://api.chatacademia.com/mcp/goose","link":"https://www.chatacademia.com/claude","installation_notes":"Hosted remote server. Sign in with your ChatAcademia account via OAuth on first connect.","is_builtin":false,"endorsed":false,"environmentVariables":[],"type":"streamable-http"}`
