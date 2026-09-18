# ChatAcademia for Claude

Evidence-grounded research questions, gap analysis and literature overviews with ChatAcademia. This standalone plugin contains a remote MCP configuration and three research skills. It contains no application server, executable hooks or credentials.

## Skills

- `/chatacademia:research-questions`: develop feasible questions from a topic and check their evidence.
- `/chatacademia:research-gaps`: compare related studies around an existing question. No defensible gap is a valid result.
- `/chatacademia:literature-overview`: search, screen and synthesize a bounded, source-linked literature overview.

Each skill retrieves the current workflow instructions from ChatAcademia rather than bundling a copy of server prompts.

## Claude Code

Clone this repository and load it for a session:

```sh
git clone https://github.com/khanhduyvt0101/chatacademia-claude-plugin.git
claude --plugin-dir ./chatacademia-claude-plugin
```

Use `/mcp` to connect ChatAcademia and complete OAuth sign-in in your browser. You need an active, verified ChatAcademia account. Never paste passwords or bearer tokens into the configuration.

## Cowork

Use Claude's custom plugin upload option to import the release ZIP. Connect ChatAcademia when prompted. If the bundled connector is unavailable, add a custom connector with `https://api.chatacademia.com/mcp` and authorize it. The skills locate tools by base name.

Public directory availability depends on Anthropic review. This repository is not evidence that the plugin has been accepted or listed.

## Credits and scope

Workflow discovery and retrieval cost zero ChatAcademia credits. Research tools consume ChatAcademia credits. OAuth consent determines the available server tools; this plugin does not restrict server permissions. The skills do not request purchases, plan upgrades or feedback unless the user asks.

Research results can be incomplete. Skills distinguish paper metadata, abstracts and supplied full text, preserve original questions and do not infer novelty from empty searches. They do not promise exhaustive reviews, persistent projects or private library integrations.

## Privacy, security and rights

The plugin sends research inputs through the ChatAcademia connector when tools are called. The ChatAcademia service is governed by its [privacy policy](https://chatacademia.com/privacy) and [terms](https://chatacademia.com/terms). Claude's own data handling is governed by Anthropic's policies. No separate telemetry or credential store is bundled here.

See [SECURITY.md](SECURITY.md) for reporting vulnerabilities. Contact: [team@chatacademia.com](mailto:team@chatacademia.com).

No open-source license is granted by this repository. Rights in this plugin are reserved by their respective holders. Public availability does not grant rights in the private ChatAcademia application or service.

## Validation

The manifest and archive are checked against [Claude's plugin reference](https://code.claude.com/docs/en/plugins-reference). Structural validation is separate from live Claude import, OAuth authorization and research execution. See the release preparation report for the exact checks performed.
