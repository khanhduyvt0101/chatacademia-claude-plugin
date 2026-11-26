# OpenAI plugin directory (ChatGPT apps + Codex plugins): v1.1.0 update

Upload the ZIP built by `node scripts/build-openai-plugin.mjs --zip <out>` (source `openai-plugin/`) via the existing
plugin → **Upload plugin to make changes** → review → submit → Publish. Name stays `chatacademia-research`; MCP URL
stays `https://api.chatacademia.com/mcp/chatgpt`.

Changes vs 1.0.0: 8 skills, `interface.capabilities` (8 entries), `composerIcon` + `logo`, brand colours,
3 default prompts, website `https://www.chatacademia.com`, release notes.

Decisions to confirm in the portal:
- **Category** `Education & Research`: the only research category the package validator accepts (`plugin_category_unknown`
  lists 13 values; "Scientific Research" is not one). If the dashboard keeps "Scientific Research", choose it there.
- **Support URL** `https://www.chatacademia.com/about`: support URLs must be HTTPS (no mailto), and the site has no
  /support page. A dedicated support/ChatGPT page on the website would be better; change it in the dashboard if one is added.
- **Test cases** are not in the ZIP (omitting `review.test_cases` keeps the saved ones). Skills get their own safety scan.
- Reviewer account must have credits (the first review failed on 0 credits).
