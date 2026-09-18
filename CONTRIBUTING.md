# Maintaining this plugin

Keep this repository standalone. Do not add private ChatAcademia source, environment files, tokens, account exports or research transcripts.

## Layout

- `.claude-plugin/plugin.json`: documented plugin metadata only.
- `.mcp.json`: the public HTTP connector endpoint, without credentials.
- `skills/*/SKILL.md`: one focused skill per directory, with name and description frontmatter.
- `assets/`: existing product branding for documentation and directory review.

Skills use live `list_research_workflows` and `get_research_workflow` definitions. Preserve their exact names and check live schemas; do not duplicate server instructions or claim unavailable private project features.

## Validate

```sh
npx --yes @anthropic-ai/claude-code plugin validate . --strict
claude --plugin-dir . --init-only
```

The second command checks startup, not authenticated research. For a runtime test, authorize the connector on the intended Claude surface, invoke each skill with complete required inputs and a bounded budget, verify actual tool calls and source-linked outputs, and record actual credits charged. Never publish authentication logs or private research inputs.

Package only tracked product files in a ZIP, with `.claude-plugin/plugin.json`, `.mcp.json` and `skills/` at the archive root. Exclude `.git`, environment files, debug logs and local validation reports. Check archive integrity and contents before upload.

Bump the semantic plugin version for published changes so version-pinned installations can receive updates. Plugin versions are separate from the remote service version.

## Official references

- [Plugin reference and manifest](https://code.claude.com/docs/en/plugins-reference)
- [Create plugins](https://code.claude.com/docs/en/plugins)
- [Use plugins in Claude](https://support.claude.com/en/articles/13837440-use-plugins-in-claude)
- [Anthropic knowledge-work examples](https://github.com/anthropics/knowledge-work-plugins)
- [Public community distribution](https://github.com/anthropics/claude-plugins-community)

Public community submissions go through Anthropic's directory review pipeline. The community repository is a read-only mirror; do not send it a pull request or claim an Anthropic Verified badge.
