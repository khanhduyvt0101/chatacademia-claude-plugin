# Community Claude Code marketplaces (non-Anthropic)

MCP endpoint for these listings: `https://api.chatacademia.com/mcp/claudecode`. The Claude plugin itself
(`plugins/chatacademia`, URL `/mcp/claude`) is unchanged: these sites list the **repo/plugin**, so where a site lists
the plugin it will show `/mcp/claude`; only stand-alone MCP entries use `/mcp/claudecode`.

## davila7/claude-code-templates (aitmpl.com)

PR adding `cli-tool/components/mcps/research/chatacademia.json` = `listings/claude-code-templates/chatacademia.json`
(same shape as `devtools/gitranks-contribute.json`, #1582). One component per PR; do not commit
`docs/components.json` or `dashboard/public/`. Title: `Add ChatAcademia MCP (academic research)`.

## claudemarketplaces.com/submit

Sign in with GitHub (khanhduyvt0101). Submit two things:
- Plugin marketplace repo: `https://github.com/khanhduyvt0101/chatacademia-claude-plugin` (marketplace `chatacademia`,
  install `/plugin marketplace add khanhduyvt0101/chatacademia-claude-plugin`).
- MCP server (if the form asks for a URL): `https://api.chatacademia.com/mcp/claudecode`, transport HTTP, OAuth.
Texts from `COPY.md`. Free; $9 priority review is the owner's call.

## claudepluginhub.com

Auto-indexes repos with `.claude-plugin/plugin.json`; if not indexed yet, use "Submit your plugin" with the repo URL
`https://github.com/khanhduyvt0101/chatacademia-claude-plugin`. Site blocks headless browsers (Cloudflare), so use a
real browser profile.
