# ChatAcademia for Cursor

Adds ChatAcademia's remote MCP server to Cursor: search scholarly databases, verify citations, find grants, plan
studies, find research gaps, extract study data and get mock peer review, without leaving the editor.

## Install

- From the Cursor Marketplace: search for **ChatAcademia** and select Install.
- One click: [Add to Cursor](https://cursor.com/install-mcp?name=chatacademia&config=eyJ1cmwiOiJodHRwczovL2FwaS5jaGF0YWNhZGVtaWEuY29tL21jcC9jdXJzb3IifQ%3D%3D)
- By hand, in `~/.cursor/mcp.json` or `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "chatacademia": { "url": "https://api.chatacademia.com/mcp/cursor" }
  }
}
```

Then open **Settings → MCP**, select **Connect** next to ChatAcademia and sign in with your ChatAcademia account in the
browser (OAuth; no API key). You need an account with a verified email and an active plan; a 7-day free trial is
available at [app.chatacademia.com](https://app.chatacademia.com).

## Try it

- "Use ChatAcademia to find recent peer-reviewed papers on formative feedback in higher education."
- "Check these five references with ChatAcademia and tell me which ones you could not find."
- "Find grant opportunities for a two-year study on adolescent sleep and school performance."

## Data and credits

Research tools use the credits of your ChatAcademia plan; account, balance and workflow tools are free. ChatAcademia
only receives what Cursor sends to a tool (your query or the text you ask it to analyse). The activity log keeps the
tool name, time, status and credits, not inputs or outputs. Docs: https://www.chatacademia.com/claude ·
Privacy: https://www.chatacademia.com/privacy · Terms: https://www.chatacademia.com/terms · Support:
team@chatacademia.com.

License: MIT (plugin files). The ChatAcademia name and logo are not covered, see BRANDING.md in the repository root.
