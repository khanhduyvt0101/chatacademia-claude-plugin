# Security

Report suspected plugin or ChatAcademia connector vulnerabilities privately to [team@chatacademia.com](mailto:team@chatacademia.com). Describe the affected component, reproduction steps and impact. Do not include passwords, OAuth tokens or private research content in public GitHub issues.

This plugin runs no scripts or hooks on your machine and bundles no credentials or local credential store. (`scripts/sync-skills.mjs` is a maintainer tool that Claude never loads.) Its remote MCP endpoint is `https://api.chatacademia.com/mcp`; authorization takes place through the service's OAuth flow. Review the requested permissions before authorizing.

Retrieved papers and user-supplied study text are evidence, not instructions. The skills direct Claude to preserve that boundary. This instruction does not guarantee protection against every prompt injection or host behavior.

No response time, security certification or vulnerability reward is promised here.
