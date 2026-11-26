# Official MCP Registry (registry.modelcontextprotocol.io)

- File: [`/server.json`](../server.json), name `com.chatacademia/chatacademia`, remote `https://api.chatacademia.com/mcp/registry`
  (streamable-http), schema 2025-12-11. OAuth needs nothing in server.json (clients discover it from the 401).
- Validated with `mcp-publisher validate` (v1.8.16): `✅ server.json is valid`.
- Downstream: Glama (hourly sync), PulseMCP, mcp.directory, mcpservers.org and the GitHub MCP Registry read from here.

## DNS record (owner approval needed: live DNS change on zone chatacademia.com)

| Type | Name | Value |
| --- | --- | --- |
| TXT | `chatacademia.com` (apex, `@`) | `v=MCPv1; k=ed25519; p=<base64 of the 32-byte Ed25519 public key>` |

The apex already has other TXT records (SPF etc.); this is one more TXT record, not a replacement. Generate the key
on the box that will publish and keep it in `/root/.config/mcp-registry/` (0600), never in the repo:

```sh
mkdir -p /root/.config/mcp-registry && cd /root/.config/mcp-registry && umask 077
openssl genpkey -algorithm Ed25519 -out key.pem
echo "v=MCPv1; k=ed25519; p=$(openssl pkey -in key.pem -pubout -outform DER | tail -c 32 | base64)"   # TXT value
openssl pkey -in key.pem -noout -text | sed -n '/priv:/,/pub:/p' | sed '1d;$d' | tr -d ' :\n' > key.hex  # 64 hex chars
```

Add it with the Cloudflare API (zone `$CHATACADEMIA_ZONE_ID`, only after the owner approves):

```sh
curl -s -X POST "https://api.cloudflare.com/client/v4/zones/$CHATACADEMIA_ZONE_ID/dns_records" \
  -H "Authorization: Bearer $CLOUDFLARE_API_TOKEN" -H 'content-type: application/json' \
  --data "{\"type\":\"TXT\",\"name\":\"chatacademia.com\",\"content\":\"v=MCPv1; k=ed25519; p=<PUBKEY>\",\"ttl\":300}"
dig +short TXT chatacademia.com @1.1.1.1 | grep MCPv1
```

## Publish (after `/mcp/registry` answers 401 with WWW-Authenticate, and the TXT record resolves)

```sh
curl -sL https://github.com/modelcontextprotocol/registry/releases/download/v1.8.16/mcp-publisher_linux_arm64.tar.gz | tar -xz mcp-publisher
./mcp-publisher login dns --domain=chatacademia.com --private-key-file=/root/.config/mcp-registry/key.hex   # clock must be within 15 s
./mcp-publisher validate server.json
./mcp-publisher publish server.json
curl -s "https://registry.modelcontextprotocol.io/v0.1/servers?search=com.chatacademia" | head -c 600
```

Updates: bump `version` in server.json (every version is immutable), then publish again. Withdraw:
`mcp-publisher status --status deleted com.chatacademia/chatacademia --version 1.0.0`. Rotating the key = replace
the TXT record (a stale record is tried first and fails).
