<img src="assets/chatacademia-icon.png" alt="ChatAcademia logo" width="72" height="72">

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

## Try it

- “Use research-questions to develop three feasible questions about sleep and academic performance among university students.”
- “Use research-gaps to investigate: Does improving sleep duration improve academic performance among university students? Keep the original question and compare overlapping studies.”
- “Use literature-overview for the topic sleep and academic performance, asking: What associations are reported among university students? Keep the review bounded and link sources.”

The literature-overview workflow requires both a topic and a research question. The gap workflow requires an existing question. If inputs are missing, the skill asks before research. Workflow retrieval supplies instructions; it does not itself produce research results.

## Troubleshooting

If tools are unavailable, complete connector authorization and start a new Claude session or reload the plugin. Inspect `/mcp` in Claude Code for connection status. Do not replace OAuth with tokens in this repository.

If a workflow reports invalid arguments, inspect its current discovery schema. Omit absent optional values rather than sending empty strings. Research calls must respect tool limits and the user's budget. On credit or permission errors, stop and resolve the account issue; do not retry indefinitely.

## Credits and scope

Workflow discovery and retrieval cost zero ChatAcademia credits. Research tools consume ChatAcademia credits. OAuth consent determines the available server tools; this plugin does not restrict server permissions. The skills do not request purchases, plan upgrades or feedback unless the user asks.

Research results can be incomplete. Skills distinguish paper metadata, abstracts and supplied full text, preserve original questions and do not infer novelty from empty searches. They do not promise exhaustive reviews, persistent projects or private library integrations.

## Privacy, security and rights

The plugin sends research inputs through the ChatAcademia connector when tools are called. The ChatAcademia service is governed by its [privacy policy](https://chatacademia.com/privacy) and [terms](https://chatacademia.com/terms). Claude's own data handling is governed by Anthropic's policies. No separate telemetry or credential store is bundled here.

See [SECURITY.md](SECURITY.md) for reporting vulnerabilities. Contact: [team@chatacademia.com](mailto:team@chatacademia.com).

No open-source license is granted by this repository. Rights in this plugin are reserved by their respective holders. Public availability does not grant rights in the private ChatAcademia application or service.

## Validation

The manifest and archive are checked against [Claude's plugin reference](https://code.claude.com/docs/en/plugins-reference). Structural validation is separate from live Claude import, OAuth authorization and research execution. See [CONTRIBUTING.md](CONTRIBUTING.md) for validation and maintenance instructions. Structural checks do not assert successful OAuth or research execution.

## Branding

The [PNG](assets/chatacademia-icon.png) and [SVG](assets/chatacademia-icon.svg) are existing ChatAcademia app icons, copied unchanged. They preserve the established blue background and white mark. Their inclusion displays the logo in this README and supplies assets for directory review.

Claude's documented plugin manifest has no supported logo or icon field. No such field is added here. A logo in this repository does not guarantee an icon on a Claude catalog card; that requires a supported directory branding mechanism or Anthropic review. See [BRANDING.md](BRANDING.md) for asset provenance and review links.
