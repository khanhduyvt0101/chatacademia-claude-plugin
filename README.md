# ChatAcademia plugin for Claude

This repository holds the ChatAcademia plugin for Claude in [`plugins/chatacademia`](plugins/chatacademia). The plugin
adds evidence-grounded academic research skills (literature overviews, research gaps, research questions, citation
checks, mock peer review, grants, data extraction and seminar planning) and connects Claude to ChatAcademia's MCP
server at `https://api.chatacademia.com/mcp/claude`.

- Plugin, setup and data disclosure: [plugins/chatacademia/README.md](plugins/chatacademia/README.md)
- Docs: https://www.chatacademia.com/claude
- Privacy: https://www.chatacademia.com/privacy · Terms: https://www.chatacademia.com/terms
- Support: team@chatacademia.com
- Maintainers: see [CONTRIBUTING.md](CONTRIBUTING.md). License: MIT ([LICENSE](LICENSE)); brand: [BRANDING.md](BRANDING.md).

## Install ChatAcademia in your agent

ChatAcademia is a hosted remote MCP server (Streamable HTTP). Sign-in is OAuth in your browser: no API key, nothing to
run locally. You need a ChatAcademia account with a verified email and an active plan (7-day free trial at
[app.chatacademia.com](https://app.chatacademia.com)). Each app has its own address below; use the one for your app.

| App | How |
| --- | --- |
| **Claude** (claude.ai, Cowork, Claude Code) | Plugin in [`plugins/chatacademia`](plugins/chatacademia/README.md), or custom connector `https://api.chatacademia.com/mcp/claude` |
| **ChatGPT / Codex** | Install ChatAcademia from the ChatGPT plugin directory (source in [`openai-plugin/`](openai-plugin/README.md); endpoint `https://api.chatacademia.com/mcp/chatgpt`) |
| **Cursor** | [![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=chatacademia&config=eyJ1cmwiOiJodHRwczovL2FwaS5jaGF0YWNhZGVtaWEuY29tL21jcC9jdXJzb3IifQ%3D%3D) or `https://api.chatacademia.com/mcp/cursor` ([Cursor plugin](cursor/chatacademia/README.md)) |
| **VS Code / GitHub Copilot** | [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_ChatAcademia-0098FF?logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=chatacademia&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fvscode%22%7D) or `https://api.chatacademia.com/mcp/vscode` |
| **Cline** | `https://api.chatacademia.com/mcp/cline`, type `streamableHttp` (agent guide: [llms-install.md](llms-install.md)) |
| **Gemini CLI** | `gemini extensions install https://github.com/khanhduyvt0101/chatacademia-claude-plugin` (uses `https://api.chatacademia.com/mcp/gemini`) |
| **Antigravity** | Plugin in [`antigravity/chatacademia`](antigravity/chatacademia), or `serverUrl` `https://api.chatacademia.com/mcp/antigravity` |
| **Kiro** | [![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add/?name=chatacademia&config=%7B%22url%22%3A%22https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fkiro%22%7D) or `https://api.chatacademia.com/mcp/kiro` |
| **Goose** | Add Extension → Remote Extension (Streamable HTTP) → `https://api.chatacademia.com/mcp/goose` (deeplink in [listings/goose.md](listings/goose.md)) |
| **Raycast** | Install from the MCP Registry extension, or add `https://api.chatacademia.com/mcp/raycast` |
| **Kilo Code** | `{"type": "streamable-http", "url": "https://api.chatacademia.com/mcp/kilo"}` |
| **Le Chat** | Connectors → Add custom connector → `https://api.chatacademia.com/mcp/mistral` |
| **Perplexity** | Settings → Connectors → custom remote connector → `https://api.chatacademia.com/mcp/perplexity` |
| **Any other MCP client** | `https://api.chatacademia.com/mcp/registry` (Streamable HTTP, OAuth; [server.json](server.json), MCP Registry name `com.chatacademia/chatacademia`) |

Manual config, for clients that use an `mcpServers` file (Cursor shown; Cline adds `"type": "streamableHttp"`):

```json
{
  "mcpServers": {
    "chatacademia": { "url": "https://api.chatacademia.com/mcp/cursor" }
  }
}
```

After adding it, connect or authenticate ChatAcademia in your app's MCP settings and finish the sign-in in the browser.
Then try: "Use ChatAcademia to check these five references and tell me which ones you could not find."

Listing files for directories and marketplaces are in [`listings/`](listings/README.md).
