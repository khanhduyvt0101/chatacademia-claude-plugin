# Maintaining this plugin

Keep this repository standalone. Do not add private ChatAcademia source, environment files, tokens, account exports or research transcripts.

## Layout

- `.claude-plugin/plugin.json`: manifest and directory listing fields (icon, documentation, support, privacy, terms).
- `.claude-plugin/marketplace.json`: lets people install straight from this repository on Claude Code.
- `.mcp.json`: the public HTTP connector endpoint, without credentials.
- `skills/*/SKILL.md`: **generated**, one skill per ChatAcademia MCP workflow. Do not edit by hand.
- `scripts/sync-skills.mjs`: the generator and drift check (maintainer tool, never loaded by Claude).
- `assets/`: icon and brand source.

## Keeping skills in sync with the server

The ChatAcademia server defines the workflows once (`packages/server/lib/mcp/mcp-skill-definitions.ts` and the agent prompts) and serves them to MCP hosts as skills. This plugin ships the same text so it works offline from the server and in hosts that only load plugin skills. To avoid drift the files are generated, with the same skill names and descriptions as the server, plus a short plugin preamble and plugin rules (verified bibliography fields, evidence availability) that live in the script.

```sh
node scripts/sync-skills.mjs --ca /path/to/chatacademia           # regenerate skills/
node scripts/sync-skills.mjs --ca /path/to/chatacademia --check   # exit 1 when stale (run in release checks)
```

The script needs `bun` and a ChatAcademia checkout. It also fails if a skill names a tool the server does not expose. Run it whenever the server's skills or tools change, then bump `version` in `plugin.json`: new or renamed skills are a minor or major bump.

If a user has both this plugin and the standalone connector, Claude may see a workflow twice (plugin-namespaced and server-provided). The text is identical by construction, so either copy gives the same behavior.

## Validate

```sh
claude plugin validate . --strict
claude --plugin-dir . --init-only
```

The second command checks startup only, not authenticated research. For a runtime test, authorize the connector, run each skill with complete inputs and a small budget, and check the tool calls and source links. Never publish auth logs or private research inputs.

Bump the semantic version in `plugin.json` for every published change; the directory tracks this branch and uses `version`.
