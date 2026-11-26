# Installing ChatAcademia (instructions for AI agents such as Cline)

ChatAcademia is a **hosted remote MCP server**. Do not clone this repository, install packages or run anything
locally. There is no API key: the user signs in with OAuth in the browser.

## Facts

- Server name: `chatacademia`
- Transport: Streamable HTTP
- URL for Cline: `https://api.chatacademia.com/mcp/cline`
- Auth: OAuth 2.1 (dynamic client registration, PKCE). No headers, no environment variables, no secrets.
- Requirement: a ChatAcademia account with a verified email and an active plan (7-day free trial at
  https://app.chatacademia.com).

## Steps for Cline

1. Open Cline's MCP settings file (`cline_mcp_settings.json`, via the MCP Servers icon → Configure).
2. Add this entry inside `mcpServers` (keep any existing servers):

```json
{
  "mcpServers": {
    "chatacademia": {
      "type": "streamableHttp",
      "url": "https://api.chatacademia.com/mcp/cline",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

3. Save. In the MCP Servers list, select **Authenticate** (or **Authorize OAuth**) next to `chatacademia` and ask
   the user to finish the ChatAcademia sign-in in the browser window that opens.

## Check that it works

Call the `get_credit_balance` tool (free). A balance means the connection works. Then try `search_papers` with a short
query, for example `{"query": "sleep and academic performance", "limit": 3}`.

## If it fails

- 401 / "unauthorized": the sign-in was not finished. Authenticate again.
- "no active plan" or "not enough credits": the user must start a trial or choose a plan at https://app.chatacademia.com.
  Do not retry in a loop.
- Do not call `remember_about_me` or `submit_feedback` unless the user asks.

## Remove

Delete the `chatacademia` entry from `cline_mcp_settings.json`, and revoke the connection under connected apps in the
ChatAcademia account.

Other clients: see the "Install" section of [README.md](README.md). Docs: https://www.chatacademia.com/claude
