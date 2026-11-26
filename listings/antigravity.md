# Google Antigravity Marketplace

Endpoint: `https://api.chatacademia.com/mcp/antigravity`

- Files: `/antigravity/chatacademia/plugin.json` (name, displayName, version, description 133 chars, logo, author,
  suggestedPrompts ×3), `/antigravity/chatacademia/mcp_config.json` (`serverUrl`, Streamable HTTP; OAuth via CIMD/DCR is
  automatic), `/antigravity/chatacademia/assets/logo.png` (512×512).
- Validated: `agy plugin validate --strict ./antigravity/chatacademia` → `✔ Validation passed` (mcpServers 1).
- Submit: interest form https://forms.gle/2EX5RFYPoJe1UgxR9 (fields not visible without opening it). Answers: plugin
  repo `https://github.com/orchestero/chatacademia-claude-plugin`, path `antigravity/chatacademia`, contact
  team@chatacademia.com, descriptions and logo from `COPY.md`.
- Open question: installing a plugin from a repo subfolder is not documented. If reviewers need a repo root, publish
  the folder as its own small repo.
- Users without the marketplace: add to `mcp_config.json`:
  `{"mcpServers":{"chatacademia":{"serverUrl":"https://api.chatacademia.com/mcp/antigravity"}}}`
