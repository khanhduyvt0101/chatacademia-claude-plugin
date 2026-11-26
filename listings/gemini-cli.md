# Gemini CLI extensions gallery (geminicli.com/extensions)

Endpoint: `https://api.chatacademia.com/mcp/gemini`

- Files: `/gemini-extension.json` and `/GEMINI.md` at the **repo root**. The gallery only indexes a manifest "in the
  absolute root of the repository or the release archive", so a subfolder would not be picked up.
- MCP entry uses `url` + `"type": "http"` (current CLI flags `httpUrl` as deprecated). OAuth: none configured; the CLI
  discovers it from the 401 and uses dynamic client registration.
- Validated: `gemini extensions validate .` (Gemini CLI 0.71.1) → `successfully validated`, no warnings.
- No submission: a daily crawler indexes public repos with the topic. Hermes runs (needs owner OK, changes repo metadata):

```sh
gh repo edit khanhduyvt0101/chatacademia-claude-plugin --add-topic gemini-cli-extension
# after a day, check that GitHub code search indexed the manifest:
gh api 'search/code?q=repo:khanhduyvt0101/chatacademia-claude-plugin+filename:gemini-extension.json' --jq .total_count
```

User install: `gemini extensions install https://github.com/khanhduyvt0101/chatacademia-claude-plugin`
