# Cotlet MCP server

[← Back to README](../README.md) · Full docs: [cotlet.dev/docs/mcp](https://cotlet.dev/docs/mcp) (Markdown: [cotlet.dev/docs/mcp.md](https://cotlet.dev/docs/mcp.md))

One remote MCP server gives your agent every app on your account as tools. Add it once; new apps show up as you get access.

## Server

| Setting | Value |
|---|---|
| URL | `https://cotlet.dev/mcp/v1` |
| Transport | Streamable HTTP |
| Auth | `Authorization: Bearer COTLET_API_KEY`, or OAuth sign-in in clients that support it |
| Protocol versions | `2025-11-25`, `2025-06-18`, `2025-03-26`, `2024-11-05` |

## Connect a client

### Claude Code

```bash
claude mcp add --transport http cotlet https://cotlet.dev/mcp/v1 \
  --header "Authorization: Bearer $COTLET_API_KEY"
```

### Cursor

```json
// ~/.cursor/mcp.json
{
  "mcpServers": {
    "cotlet": {
      "url": "https://cotlet.dev/mcp/v1",
      "headers": { "Authorization": "Bearer ${env:COTLET_API_KEY}" }
    }
  }
}
```

### Codex

```toml
# ~/.codex/config.toml
[mcp_servers.cotlet]
url = "https://cotlet.dev/mcp/v1"
bearer_token_env_var = "COTLET_API_KEY"
```

### Claude Desktop

```text
Settings > Connectors > Add custom connector
Name: Cotlet
URL:  https://cotlet.dev/mcp/v1
```

### ChatGPT

```text
Settings > Apps & Connectors > Create
MCP server URL: https://cotlet.dev/mcp/v1
Authentication: OAuth
```

### n8n

```text
Node: MCP Client Tool
Endpoint: https://cotlet.dev/mcp/v1
Authentication: Header Auth
  Name:  Authorization
  Value: Bearer <your key>
```

Product names are trademarks of their owners. Cotlet is not affiliated with them.

## Tools

- Each endpoint is one tool named `{app}_{endpoint}`, such as `skool_list_members`. Its input schema is the same JSON Schema as the REST endpoint.
- `tools/list` returns the tools of every app; it needs no key.
- Read endpoints carry `readOnlyHint: true`, so clients can run them without asking.
- Each app is also a resource, `cotlet://apps/{app}`, with its description and endpoints.
- Too many tools for your agent? Keep only the apps you use: add `?apps=skool,booksy` to the server URL.

## Calling a tool

Agents call tools for you; this is what goes over the wire:

```bash
curl -X POST https://cotlet.dev/mcp/v1 \
  -H "Authorization: Bearer $COTLET_API_KEY" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/call",
       "params": {"name": "skool_list_members", "arguments": {"group": "yourgroup"}}}'
```

The result carries the output twice: as `structuredContent` for code and as JSON text for the model.

## Errors

A failed tool call returns a result with `isError: true` and a message your agent can act on, with the same codes as the [REST API](rest-api.md#errors):

```json
{
  "content": [{ "type": "text", "text": "AUTH_EXPIRED: your Skool session expired. Ask the user to sign in again: https://cotlet.dev/app/connect/skool" }],
  "isError": true
}
```

## MCP or REST?

Use MCP when an agent decides what to call. Use [REST](rest-api.md) at `https://cotlet.dev/api/v1` when your own code does: same key, same inputs, same outputs.
