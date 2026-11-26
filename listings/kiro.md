# Kiro powers / Kiro registry

Endpoint: `https://api.chatacademia.com/mcp/kiro`

- Files (Agent Plugins 1.0.0, which Kiro powers support since 2026-08): `/kiro/chatacademia/plugin.json` and
  `/kiro/chatacademia/mcp.json` (`type: streamable-http`). Both validated against the agent-plugins.org 1.0.0 JSON
  schemas. Kiro installs powers from a repo subfolder URL:
  `https://github.com/orchestero/chatacademia-claude-plugin/tree/main/kiro/chatacademia`.
- Caveat: Kiro's own docs show `"url"` alone and its official powers use `"type": "http"`; the spec value
  `streamable-http` is what the schema requires. If a Kiro test install does not connect, change `type` to `http`.
- Submit form https://kiro.dev/powers/submit/:
  - Resource type: **MCP server** (or Power, pointing at the folder above)
  - First/last name: the owner's · Email: team@chatacademia.com · Organization: ChatAcademia
  - Use case (3–4 words): **Academic research and citations**
  - Public GitHub repository URL: `https://github.com/orchestero/chatacademia-claude-plugin`
  - Logo: `assets/chatacademia-icon.svg` (SVG recommended)
  - Domain/problem: the short description from `COPY.md`
  - Submitting accepts the Kiro Registry Publisher Terms (owner should be OK with that).
- Add to Kiro link (no listing needed):
  `https://kiro.dev/launch/mcp/add/?name=chatacademia&config=%7B%22url%22%3A%22https%3A%2F%2Fapi.chatacademia.com%2Fmcp%2Fkiro%22%7D`
  Badge: `https://kiro.dev/images/add-to-kiro.svg`

- Manifest metadata: the Agent Plugins 1.0.0 schema forbids extra keys (`additionalProperties: false`), so `displayName`/icon
  cannot go in `plugin.json`; give Kiro the logo URL `https://api.chatacademia.com/icon-512.png` in the submit form.
