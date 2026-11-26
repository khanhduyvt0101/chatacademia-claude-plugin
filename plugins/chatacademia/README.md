<img src="assets/chatacademia-icon.png" alt="ChatAcademia logo" width="72" height="72">

# ChatAcademia for Claude

ChatAcademia connects Claude to real academic databases and to eight research workflows, so literature work stays tied to sources you can open. The plugin bundles the ChatAcademia connector (a remote MCP server) and one skill per workflow. It contains no application server, no executable hooks or scripts that run for you, and no credentials.

## Skills

| Skill | Use it to |
| --- | --- |
| `literature-overview` | Search, screen and synthesize a bounded, source-linked literature overview. |
| `research-gap` | Compare related studies around an existing question and decide whether a gap is worth pursuing. No defensible gap is a valid result. |
| `brainstorm-research-questions` | Turn a topic into feasible research questions and subquestions grounded in the literature. |
| `mock-peer-review` | Get reviewer-style feedback on a manuscript, abstract or proposal before submission. |
| `hallucination-checker` | Check whether references and quoted claims exist and say what they are cited for. |
| `find-research-grants` | Find funding calls and funded projects, and assess fit with your proposal. |
| `extract-data` | Pull design, sample, measures and results out of study text, with exact supporting passages. |
| `plan-academic-seminar` | Plan a seminar, journal club or talk: paper selection, timing and discussion questions. |

Skills are namespaced by the plugin, for example `/chatacademia:research-gap`. Claude also loads them automatically when your request matches. The skill text is generated from ChatAcademia's own server definitions (see [CONTRIBUTING.md](CONTRIBUTING.md)), so it matches the tools the connector offers.

## Setup

**Claude (claude.ai and Cowork):** install ChatAcademia from the plugin directory, open the plugin's **Connectors** tab, connect ChatAcademia and sign in.

**Claude Code:**

```sh
/plugin marketplace add khanhduyvt0101/chatacademia-claude-plugin
/plugin install chatacademia@chatacademia
```

Then run `/mcp`, select ChatAcademia and complete the sign-in in your browser. To try a local copy instead: `claude --plugin-dir ./chatacademia-claude-plugin`.

You need a ChatAcademia account with a verified email and an active plan (sign up at [app.chatacademia.com](https://app.chatacademia.com)). Sign-in uses OAuth in your browser; nothing is pasted into configuration files, and you can revoke the connection from your ChatAcademia account at any time.

If you already added ChatAcademia as a standalone connector, use the same URL (`https://api.chatacademia.com/mcp/claude`); Claude then shows one set of tools, not two. Full documentation: [chatacademia.com/claude](https://www.chatacademia.com/claude). Using another AI app? See [install ChatAcademia in other agents](https://github.com/khanhduyvt0101/chatacademia-claude-plugin#install-chatacademia-in-your-agent).

## Try it

- "Use research-gap on: Does improving sleep duration improve academic performance among university students?"
- "Give me a literature overview of sleep and academic performance, question: what associations are reported among university students? Keep it bounded and link every source."
- "Check these five references for hallucinated entries: ..."

## What this plugin sends and fetches

- **Connector endpoint:** `https://api.chatacademia.com/mcp/claude`, operated by ChatAcademia. It is the only network destination the plugin uses (declared in `.mcp.json`).
- **What is sent:** only when a ChatAcademia tool runs, Claude sends the tool arguments: search queries, reference titles, and any manuscript, abstract or study text you ask it to analyze. ChatAcademia also receives your OAuth identity (name, email, verification status) and the tool name and timing.
- **What ChatAcademia fetches for you:** paper metadata and abstracts from public databases (PubMed, OpenAlex, Crossref, Semantic Scholar, arXiv, Europe PMC, ERIC, Google Scholar), grant listings (Grants.gov, NIH RePORTER, CORDIS, UKRI) and Crossref reference checks. It does not retrieve paywalled full text.
- **What is stored:** ChatAcademia records the tool name, calling app, status, timing and credits used so you can review your usage; it does not store tool inputs or outputs in that log. The optional memory tools (`get_my_memory`, `remember_about_me`) read and write ChatAcademia's own profile for you, only when you ask. They never access Claude's memory or your Claude chats.
- **Credits:** research tools use credits from your ChatAcademia plan. Reading skills, balance and plan information costs nothing. Skills never buy, upgrade or send feedback unless you explicitly ask.
- **Not in this plugin:** no telemetry, no local scripts that run on your machine, no credential store.

Your data is handled under ChatAcademia's [privacy policy](https://www.chatacademia.com/privacy) and [terms](https://www.chatacademia.com/terms). ChatAcademia does not use your content to train AI models. Claude's own data handling is governed by Anthropic's policies. ChatAcademia is for people aged 18 and over.

## Limits you should know

Results can be incomplete. Abstracts and metadata are not full text, an empty search is not evidence of absence, and a matched reference only shows the paper exists, not that it supports the claim. The skills label what they actually read and do not promise exhaustive reviews, saved projects or access to your private libraries (Zotero, Mendeley, Drive, Dropbox) through Claude.

## Troubleshooting

- *Tools not available:* connect and authorize ChatAcademia, then start a new session or run `/reload-plugins`. Check `/mcp` in Claude Code for status.
- *Credit or permission errors:* stop and check your balance and plan in ChatAcademia; the skills do not retry in a loop.
- *Need help:* email [team@chatacademia.com](mailto:team@chatacademia.com) or open an [issue](https://github.com/khanhduyvt0101/chatacademia-claude-plugin/issues). Report vulnerabilities as described in [SECURITY.md](SECURITY.md).

## License

The plugin files are MIT licensed (see [LICENSE](LICENSE)). The ChatAcademia name and logo are not covered, see BRANDING.md in the repository root. The ChatAcademia service itself is separate and governed by its terms.
