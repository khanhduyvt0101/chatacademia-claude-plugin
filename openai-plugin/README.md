# ChatAcademia plugin for ChatGPT and Codex (OpenAI plugin directory)

Source of the `chatacademia-research` package listed at platform.openai.com/plugins. This README is not part of the
upload. MCP endpoint (reviewed surface, never change it): `https://api.chatacademia.com/mcp/chatgpt`.

- `.codex-plugin/plugin.json`: manifest (Codex layout; name must stay `chatacademia-research`, bump `version` per upload)
- `.mcp.json`: the remote MCP server
- `assets/`: `logo.png` 512×512, `composer-icon.png` 256×256
- `skills/`: **generated** from `plugins/chatacademia/skills` by `scripts/build-openai-plugin.mjs` (tools limited to the
  `/mcp/chatgpt` route, no checkout or upgrade wording). Do not edit by hand.

```sh
node scripts/build-openai-plugin.mjs                       # regenerate skills + validate
node scripts/build-openai-plugin.mjs --check               # CI-style: fail if skills are stale
node scripts/build-openai-plugin.mjs --zip chatacademia-openai-1.1.0.zip
```

There is no official validator CLI; the script checks the rules in
https://developers.openai.com/plugins/deploy/submission-errors and the portal upload is the final check.
