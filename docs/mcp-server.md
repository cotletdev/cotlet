# Cotlet MCP server

[← Back to README](../README.md) · Full docs: [cotlet.dev/docs/mcp](https://cotlet.dev/docs/mcp) (Markdown: [cotlet.dev/docs/mcp.md](https://cotlet.dev/docs/mcp.md))

One remote MCP server gives your agent every app on your account as tools. Add it once; new apps show up as you get access.

## Server

| Setting | Value |
|---|---|
| URL | `https://cotlet.dev/mcp/v1` |
| Transport | Streamable HTTP |
| Auth | `Authorization: Bearer COTLET_API_KEY` |
| URL for OAuth sign-in | `https://cotlet.dev/mcp/v1/connect` (Claude.ai, Claude Desktop, ChatGPT, Claude Code without a key) |
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

### Cline

```json
// cline_mcp_settings.json
{
  "mcpServers": {
    "cotlet": {
      "type": "streamableHttp",
      "url": "https://cotlet.dev/mcp/v1",
      "headers": { "Authorization": "Bearer <your key>" }
    }
  }
}
```

### Claude Desktop

```text
Settings > Connectors > Add custom connector
Name: Cotlet
URL:  https://cotlet.dev/mcp/v1/connect

Then Connect and sign in to Cotlet.
```

### ChatGPT

```text
Settings > Apps & Connectors > Create
MCP server URL: https://cotlet.dev/mcp/v1/connect
Authentication: OAuth
```

### n8n

```text
Node: MCP Client (MCP Client Tool inside an AI Agent)
Server Transport: HTTP Streamable
MCP Endpoint URL: https://cotlet.dev/mcp/v1
Authentication: Bearer Auth
  Token: <your key>
Tool: skool
Input (JSON): {"tool": "list_groups", "arguments": {}}
```

### Make

```text
App: MCP Client > Call a tool
MCP Server: + New MCP Server
  URL: https://cotlet.dev/mcp/v1
  API Key / Access token: <your key>
Tool Name: skool
Arguments: {"tool": "list_groups", "arguments": {}}
```

### Zapier

```text
Action: MCP Client by Zapier > Run Tool
Server URL: https://cotlet.dev/mcp/v1
Transport: Streamable HTTP
OAuth: No
Bearer Token: <your key>
Tool: skool
  tool: list_groups
  arguments: {}
```

n8n, Make, Zapier and Cline were tested on 21.10.2026 with an API key.

Product names are trademarks of their owners. Cotlet is not affiliated with them.

## Tools

- Each app is one tool named like the app, with dashes as underscores: `skool`, `pirate_ship`. Its endpoints are the operations of that tool.
- `{"tool": "list_members", "arguments": {...}}` runs an operation. Its arguments are the same JSON Schema as the REST endpoint.
- `{"tool": "list_members"}` alone returns that operation's description and input schema; `{}` lists every operation. Both are free.
- `tools/list` needs no key: without one it returns a tool for every app; with a key or sign-in, only the apps and operations that credential may call.
- An app whose operations all read carries `readOnlyHint: true`, so clients can run it without asking.
- Each app is also a resource, `cotlet://apps/{app}`, with its description and endpoints.
- Want fewer operations in front of your agent? Create a key for only the apps (or operations) you use.

## Calling a tool

Agents call tools for you; this is what goes over the wire:

```bash
curl -X POST https://cotlet.dev/mcp/v1 \
  -H "Authorization: Bearer $COTLET_API_KEY" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/call",
       "params": {"name": "skool", "arguments": {"tool": "list_members", "arguments": {"group": "yourgroup"}}}}'
```

The result carries the output twice: as `structuredContent` for code and as JSON text for the model.

## Errors

A failed tool call returns a result with `isError: true` and a message your agent can act on, with the same codes as the [REST API](rest-api.md#errors):

```json
{
  "content": [{ "type": "text", "text": "AUTH_EXPIRED: Skool signed the user out. Ask the user to sign in to the app again in their Cloud Browser at browser_url, then call again. browser_url: https://cotlet.dev/app/browser" }],
  "isError": true
}
```

## MCP or REST?

Use MCP when an agent decides what to call. Use [REST](rest-api.md) at `https://cotlet.dev/api/v1` when your own code does: same key, same inputs, same outputs.
