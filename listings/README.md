# Listing kit

Files used to list ChatAcademia in MCP directories and agent marketplaces. Nothing here is loaded by the Claude
plugin. Copy and per-form field mapping: [COPY.md](COPY.md). Each target uses its own endpoint URL (table in COPY.md).

| Target | File | Repo files it relies on |
| --- | --- | --- |
| Official MCP Registry | [mcp-registry.md](mcp-registry.md) (DNS record + publish commands) | `/server.json` |
| GitHub MCP Registry / VS Code | [github-vscode.md](github-vscode.md), [emails/github-partnerships.md](emails/github-partnerships.md) | README links |
| Cursor Marketplace, cursor.directory | [cursor.md](cursor.md) | `/.cursor-plugin/marketplace.json`, `/cursor/chatacademia/` |
| Gemini CLI | [gemini-cli.md](gemini-cli.md) | `/gemini-extension.json`, `/GEMINI.md` |
| Antigravity | [antigravity.md](antigravity.md) | `/antigravity/chatacademia/` |
| Kiro | [kiro.md](kiro.md) | `/kiro/chatacademia/` |
| Docker MCP Catalog | [docker.md](docker.md) | [docker/servers/chatacademia/](docker/servers/chatacademia) |
| Cline | [cline.md](cline.md) | `/llms-install.md`, `/assets/chatacademia-icon-400.png` |
| Raycast | [raycast.md](raycast.md) | |
| Kilo | [kilo.md](kilo.md) | [kilo/mcps/chatacademia/MCP.yaml](kilo/mcps/chatacademia/MCP.yaml) |
| Goose | [goose.md](goose.md) (directory closed; registry only) | |
| Awesome lists | [awesome-lists.md](awesome-lists.md) | |
| Community Claude Code marketplaces | [claude-code-community.md](claude-code-community.md) | [claude-code-templates/chatacademia.json](claude-code-templates/chatacademia.json) |
| OpenAI plugin directory (ChatGPT, Codex) | [openai.md](openai.md) | `/openai-plugin/`, `scripts/build-openai-plugin.mjs` |
| Web forms, emails | [COPY.md](COPY.md), [emails/](emails) | |

Assets: `/assets/chatacademia-icon.svg`, `-512.png`, `-400.png`, `/assets/screenshots/*.png` (1440×900).
