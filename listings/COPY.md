# ChatAcademia listing copy kit

One source of truth for every directory, marketplace and web form. Each target gets its **own** endpoint URL (see the
table at the end) so installs can be traced per channel. Never reuse another channel's URL.

## Identity

| Field | Value |
| --- | --- |
| Name | ChatAcademia |
| Registry name | `com.chatacademia/chatacademia` |
| Slug / id | `chatacademia` |
| Publisher / author | ChatAcademia (official, run by the service's own company) |
| Website | https://www.chatacademia.com |
| Docs | https://www.chatacademia.com/claude |
| Pricing | https://www.chatacademia.com/#pricing (7-day free trial; plans from $15/month with monthly credits) |
| Privacy | https://www.chatacademia.com/privacy |
| Terms | https://www.chatacademia.com/terms |
| Support | team@chatacademia.com · https://github.com/khanhduyvt0101/chatacademia-claude-plugin/issues |
| Security | https://github.com/khanhduyvt0101/chatacademia-claude-plugin/blob/main/SECURITY.md |
| Repository | https://github.com/khanhduyvt0101/chatacademia-claude-plugin (MIT) |
| Transport | Remote, Streamable HTTP. No local install, no binary, no Docker image |
| Auth | OAuth 2.1 (dynamic client registration and client ID metadata documents, PKCE). No API key, no headers |
| Contact for reviewers | team@chatacademia.com |

## Logos and screenshots (raw GitHub URLs, live after push to `main`)

- SVG: https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/chatacademia-icon.svg
- PNG 512×512: https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/chatacademia-icon-512.png
- PNG 400×400 (Cline): https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/chatacademia-icon-400.png
- Screenshots (1440×900 PNG), base `https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/screenshots/`:
  `01-overview.png`, `02-tools.png`, `03-skills.png`, `04-connect.png`, `05-hallucination-checker.png`.
  They are public website pages. Screenshots of ChatAcademia running inside an agent (Cursor, VS Code) need a signed-in
  account with a plan and are not in this kit yet.

Brand colour: `#339AF0` (icon background), white mark.

## Descriptions

**One-liner (≤100 chars, 98):**
Academic research tools: search papers and grants, verify citations, review literature and drafts.

**Short (≤200 chars, 190):**
ChatAcademia brings real academic databases into your AI agent: search papers and grants, check references for
hallucinations, map research gaps, extract study data and get mock peer review.

**Long (≤2000 chars):**

> ChatAcademia is an AI research assistant for academics, now available as a remote MCP server for any agent that
> supports MCP. It connects your assistant to real scholarly databases (PubMed, OpenAlex, Crossref, Semantic Scholar,
> arXiv, Europe PMC, ERIC) and grant sources (Grants.gov, NIH RePORTER, CORDIS, UKRI), so literature work stays tied to
> sources you can open.
>
> Use it to search papers and fetch abstracts, verify up to five references at a time against Crossref and other
> databases, find funding calls and funded projects, turn a topic into feasible research questions, draft search
> strategies and review protocols, identify research gaps in the evidence you collected, extract study data with exact
> supporting passages, get reviewer-style feedback on a manuscript, and plan a seminar or journal club.
>
> More than 30 tools and 8 guided workflows (literature overview, research gap, research questions, hallucination checker, mock
> peer review, research grants, data extraction, seminar planning). Two tools write data (saving a fact to your profile,
> sending feedback) and are marked so your agent can ask first; everything else only reads or computes.
>
> Sign-in is OAuth in your browser: nothing to paste, no API keys, revocable from your ChatAcademia account at any time.
> Research tools use the credits of your ChatAcademia plan (7-day free trial, then plans with monthly credits); account,
> balance and workflow tools are free. Every result reports the credits used and failed requests are not charged.
>
> Privacy: ChatAcademia only receives what your agent sends to a tool. The activity log keeps tool name, time, status and
> credits, not your inputs or outputs, and your content is not used to train AI models. Results are metadata and
> abstracts, not paywalled full text.

(1,776 characters.)

## Categories and tags

- Primary category: **Research** / Education / Science. Secondary: Productivity, Search, Knowledge.
- Tags: `academic-research`, `literature-review`, `citations`, `hallucination-check`, `research-gap`, `peer-review`,
  `grants`, `pubmed`, `openalex`, `crossref`, `semantic-scholar`, `arxiv`, `scholarly-search`, `education`, `oauth`,
  `remote`, `streamable-http`.

## Feature bullets

- Search scholarly databases (PubMed, OpenAlex, Crossref, Semantic Scholar, arXiv, Europe PMC, ERIC) in one call.
- Verify citations: matched, possible match or not found, with the database that matched.
- Find grants and funded projects from US, EU and UK funders, and check proposal fit.
- Plan studies: research questions, sub-questions, Boolean search strategies, study design, review protocols.
- Analyse literature you supply: research gaps, synthesis, claim evaluation, data extraction with exact passages.
- Write and present: mock peer review, academic editing, poster outlines, seminar plans.
- 8 guided workflows exposed as MCP prompts/skills.
- OAuth sign-in, no API keys; read-only by default, two clearly marked write tools.

## Example prompts

1. "Use ChatAcademia to find recent peer-reviewed papers on formative feedback in higher education and summarize what they agree on."
2. "Check these five references with ChatAcademia and tell me which ones you could not find."
3. "Does improving sleep duration improve academic performance among university students? Look for a research gap."
4. "Find grant opportunities for a two-year study on adolescent sleep and school performance."
5. "I pasted my draft methods section. Ask ChatAcademia for a mock peer review and list the major issues."
6. "Draft a PubMed and Scopus-style Boolean search strategy for telehealth interventions in rural diabetes care."

## Auth and credits (for forms that ask "how does auth work?" / "pricing")

> ChatAcademia is a hosted remote MCP server (Streamable HTTP). Clients discover OAuth 2.1 from the 401
> `WWW-Authenticate` / protected-resource metadata; it supports dynamic client registration and client ID metadata
> documents, with PKCE. Users sign in with their ChatAcademia account in the browser; no API key or header is needed.
> Using research tools requires an account with a verified email and an active plan (7-day free trial available).
> Pricing: freemium/paid (trial, then subscription with monthly credits). Without a token `initialize` answers 401, so
> scanners that do not do OAuth show no tools.

## Per-channel endpoint URLs (owner rule: one URL per listing)

| Target | URL |
| --- | --- |
| Official MCP Registry (`server.json`) | https://api.chatacademia.com/mcp/registry |
| GitHub MCP Registry / VS Code | https://api.chatacademia.com/mcp/vscode |
| Cursor (Marketplace, cursor.directory, deeplink) | https://api.chatacademia.com/mcp/cursor |
| Cline | https://api.chatacademia.com/mcp/cline |
| Raycast | https://api.chatacademia.com/mcp/raycast |
| Docker MCP Catalog | https://api.chatacademia.com/mcp/docker |
| Goose | https://api.chatacademia.com/mcp/goose |
| Kilo | https://api.chatacademia.com/mcp/kilo |
| Kiro | https://api.chatacademia.com/mcp/kiro |
| Gemini CLI | https://api.chatacademia.com/mcp/gemini |
| Antigravity | https://api.chatacademia.com/mcp/antigravity |
| Mistral Le Chat | https://api.chatacademia.com/mcp/mistral |
| Perplexity | https://api.chatacademia.com/mcp/perplexity |
| Glama | https://api.chatacademia.com/mcp/glama |
| mcp.so | https://api.chatacademia.com/mcp/mcpso |
| MCP Market | https://api.chatacademia.com/mcp/mcpmarket |
| mcpservers.org | https://api.chatacademia.com/mcp/mcpservers |
| LobeHub | https://api.chatacademia.com/mcp/lobehub |
| mcp.directory | https://api.chatacademia.com/mcp/mcpdirectory |
| awesome lists (punkpeye, jaw9c) | https://api.chatacademia.com/mcp/awesome |
| Community Claude Code marketplaces | https://api.chatacademia.com/mcp/claudecode |
| Claude plugin / Claude directory | https://api.chatacademia.com/mcp/claude |
| MCP Server Finder, GitHub partnerships email | use the registry / vscode URL of the listing they pull from (see emails) |

## Web form field mapping

Use the copy above; each row lists only what differs. "One-liner", "Short", "Long" = the descriptions above.
Logo = 512 PNG unless stated. Contact email everywhere: team@chatacademia.com.

| Target | Where | Fields → values |
| --- | --- | --- |
| **mcp.so** | Free: comment on https://github.com/chatmcp/mcpso/issues/1 (paid $39 form at mcp.so/submit skips review) | Comment: `ChatAcademia: a remote MCP server for academic research.` + Short description + `- Site and setup: https://www.chatacademia.com/claude` + `- Endpoint: https://api.chatacademia.com/mcp/mcpso (Streamable HTTP, OAuth)` + `- Official MCP Registry: com.chatacademia/chatacademia` + `- Repo: https://github.com/khanhduyvt0101/chatacademia-claude-plugin`. On the form: tab **Remote Server**, Repository URL = repo, Name = ChatAcademia. |
| **MCP Market** | https://mcpmarket.com/submit | Tab "MCP Server": repo-url = repo URL, submitter-email, Try Now link = https://www.chatacademia.com/claude → "Submit to free queue" (4–6 weeks). The "Remote MCP" tab (endpoint /mcp/mcpmarket) is a separate **paid** listing (needs key features ≥ N, use cases, FAQs): owner's call; reuse Feature bullets, Example prompts and the FAQ below. |
| **mcpservers.org** | https://mcpservers.org/submit | Server Name = ChatAcademia · Category = **Search** (no Research option; "Other" is the alternative) · Short Description = One-liner · Repository/Website/Docs = https://www.chatacademia.com/claude · Official MCP Registry Name = `com.chatacademia/chatacademia` · [x] supports remote connections → Remote Server URL = https://api.chatacademia.com/mcp/mcpservers · Authentication = OAuth · Contact Email. Free (2 weeks) or $39 premium: owner's call. |
| **mcp.directory** | https://mcp.directory/submit (also auto-imports registry entries) | GitHub Repository URL = repo · npm/PyPI = empty · Short Description (≤100) = One-liner · Email. No endpoint field: after listing, email them to set the endpoint to https://api.chatacademia.com/mcp/mcpdirectory and claim the registry import. |
| **LobeHub** | https://lobehub.com/mcp → "Publish your server" (needs a LobeHub sign-in; fields not visible logged out) | Expected: name, repo/homepage, description (Short + Long), category Research/Education, connection type **HTTP / streamable** with URL https://api.chatacademia.com/mcp/lobehub, auth OAuth, icon = 512 PNG URL. |
| **Glama** | https://glama.ai/mcp/servers → "Add Server" → **Hosted endpoint** (or wait for the hourly registry sync) | Name = ChatAcademia · Endpoint URL = https://api.chatacademia.com/mcp/glama · Transport = Streamable HTTP · Auth = OAuth · Description = Short · Homepage = https://www.chatacademia.com/claude · Repo = repo URL. Then claim via DNS TXT `_glama-claim.chatacademia.com` or `/.well-known/glama.json` (owner approval: DNS/web change) and add a least-privilege OAuth test profile so the listing is not "unhealthy". Note: a registry-synced entry will carry /mcp/registry; a hosted-endpoint entry carries /mcp/glama. |
| **MCP Server Finder** | email, `emails/mcp-server-finder.md` | No dedicated route was assigned; the draft uses /mcp/registry. Ask the owner whether to add `/mcp/mcpserverfinder`. |
| **Mistral Le Chat** | email, `emails/mistral.md` | Endpoint /mcp/mistral. |
| **Perplexity** | email, `emails/perplexity.md` | Endpoint /mcp/perplexity. |
| **GitHub partnerships** | email, `emails/github-partnerships.md` | After the registry publish. Endpoint /mcp/vscode. |
| **claudemarketplaces.com / claudepluginhub.com** | see `claude-code-community.md` | Repo URL; MCP URL /mcp/claudecode. |
| **Kiro** | https://kiro.dev/powers/submit/, see `kiro.md` | Resource type, names, Use case = "Academic research and citations", repo URL, logo SVG. |
| **Antigravity** | https://forms.gle/2EX5RFYPoJe1UgxR9, see `antigravity.md` | Repo URL + path `antigravity/chatacademia`, Short/Long, logo. |
| **Cursor Marketplace** | https://cursor.com/marketplace/publish, see `cursor.md` | Repo URL; category Integrations. |
| **Docker / Raycast / Kilo / Cline / awesome lists / claude-code-templates** | PR or issue, see the matching file in `listings/` | Exact diffs there. |
| **Goose** | closed to new entries, see `goose.md` | Covered by the official registry. |

## FAQ (for forms that ask for FAQs)

- **Is it free?** There is a 7-day free trial. After that, research tools use the monthly credits of a paid plan;
  account, balance and workflow tools never use credits, and failed requests are not charged.
- **Do I need an API key?** No. You sign in with your ChatAcademia account through OAuth in the browser.
- **Which databases does it search?** PubMed, OpenAlex, Crossref, Semantic Scholar, arXiv, Europe PMC and ERIC for
  papers; Grants.gov, NIH RePORTER, CORDIS and UKRI for funding.
- **Does it read full text?** No. It returns metadata and available abstracts; analysis tools work on text you supply.
- **What data does ChatAcademia keep?** The tool name, time, status and credits, not your inputs or outputs. Your
  content is not used to train AI models.
- **Which clients work?** Any MCP client with Streamable HTTP and OAuth: Claude, Cursor, VS Code, Cline, Gemini CLI,
  Antigravity, Kiro, Goose, Raycast, Le Chat, Perplexity and others.
