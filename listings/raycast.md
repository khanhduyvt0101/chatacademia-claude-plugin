# Raycast: Model Context Protocol Registry extension

Endpoint: `https://api.chatacademia.com/mcp/raycast`

PR to `raycast/extensions`, 3 files under `extensions/model-context-protocol-registry/` (same shape as the Tolstoy
PR #33872, merged 2026-11-25). Title: `[MCP Registry] Add ChatAcademia MCP Server`.

## `src/registries/builtin/entries.ts`: add to `OFFICIAL_ENTRIES` (alphabetical by `name`)

```ts
  {
    name: "chatacademia",
    title: "ChatAcademia",
    description:
      "ChatAcademia, the AI research assistant for academics. Search papers and grants across scholarly databases, verify citations, find research gaps, extract study data and get mock peer review, with 8 guided research workflows. Hosted Streamable HTTP server with OAuth 2.1 sign-in (dynamic client registration and PKCE), a direct HTTP connection in Raycast and an `mcp-remote` fallback. A ChatAcademia account is required (7-day free trial).",
    icon: "https://raw.githubusercontent.com/khanhduyvt0101/chatacademia-claude-plugin/main/assets/chatacademia-icon-512.png",
    homepage: "https://www.chatacademia.com/claude",
    configuration: {
      command: "npx",
      args: ["-y", "mcp-remote@0.14.3", "https://api.chatacademia.com/mcp/raycast"],
    },
    remoteUrl: "https://api.chatacademia.com/mcp/raycast",
  },
```

Check the pinned `mcp-remote` version against the newest entries before opening the PR.

## `CHANGELOG.md`: new top entry (date = PR day)

```md
## [Add ChatAcademia MCP Server] - {PR_MERGE_DATE}

- Add ChatAcademia to the official MCP server registry entries
```

(Raycast replaces `{PR_MERGE_DATE}` on merge; use it if the file's other entries do.)

## `README.md`: table row in the official servers table (or run the extension's `update-readme.ts` with bun)

```md
| [ChatAcademia](https://www.chatacademia.com/claude) | Academic research tools: search papers and grants, verify citations, review literature and drafts. |
```
