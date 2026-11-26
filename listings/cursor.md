# Cursor Marketplace and cursor.directory

Endpoint: `https://api.chatacademia.com/mcp/cursor`

Files (outside the Claude plugin folder so each keeps its own URL):
- `/.cursor-plugin/marketplace.json` → plugin `chatacademia`, source `cursor/chatacademia`
- `/cursor/chatacademia/.cursor-plugin/plugin.json` (name, displayName, version, description, author, publisher, logo,
  category `integrations`, `mcpServers: ./mcp.json`), `/cursor/chatacademia/mcp.json` (`type: http`, /mcp/cursor),
  `/cursor/chatacademia/assets/logo.png` (512×512), `/cursor/chatacademia/README.md`.
- Validated with Cursor's own CI script (`cursor/plugins` `scripts/validate-plugins.mjs` + schemas, run against this repo):
  `All plugins validated successfully.` (it also checks our `.claude-plugin/marketplace.json`).

## Cursor Marketplace

Submit at https://cursor.com/marketplace/publish with the repo URL
`https://github.com/khanhduyvt0101/chatacademia-claude-plugin`. Every plugin and update is reviewed by hand.
Fields: use `COPY.md` (name, one-liner, long description, logo 512 PNG, category Integrations, tags).

## cursor.directory (https://cursor.directory/plugins/new)

Paste only `https://github.com/khanhduyvt0101/chatacademia-claude-plugin` (subfolder URLs are ignored). Its scanner
reads the root `.cursor-plugin/marketplace.json` and finds `cursor/chatacademia/.cursor-plugin/plugin.json` +
`mcp.json`. It takes the logo only from a root manifest `logo`, which Cursor's marketplace schema does not allow, so
cursor.directory may show the GitHub owner avatar; fix the image in its edit form after it is listed.

## Add to Cursor links

- Web (works from READMEs): `https://cursor.com/install-mcp?name=chatacademia&config=eyJ1cmwiOiJodHRwczovL2FwaS5jaGF0YWNhZGVtaWEuY29tL21jcC9jdXJzb3IifQ%3D%3D`
- Deeplink: `cursor://anysphere.cursor-deeplink/mcp/install?name=chatacademia&config=eyJ1cmwiOiJodHRwczovL2FwaS5jaGF0YWNhZGVtaWEuY29tL21jcC9jdXJzb3IifQ%3D%3D`
  (`config` = base64 of `{"url":"https://api.chatacademia.com/mcp/cursor"}`)
- Badge: `[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](<web link>)`
