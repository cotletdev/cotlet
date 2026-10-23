# Cotlet MCP server

[← Back to README](../README.md) · Full docs: [cotlet.dev/docs/mcp](https://cotlet.dev/docs/mcp) (Markdown: [cotlet.dev/docs/mcp.md](https://cotlet.dev/docs/mcp.md))

One remote MCP server gives your agent every app on your account, a read tool and a write tool per app. Add it once; new apps show up as you enable them for agents.

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
Tool: skool_read
Input (JSON): {"operation": "list_groups", "arguments": {}}
```

### Make

```text
App: MCP Client > Call a tool
MCP Server: + New MCP Server
  URL: https://cotlet.dev/mcp/v1
  API Key / Access token: <your key>
Tool Name: skool_read
Arguments: {"operation": "list_groups", "arguments": {}}
```

### Zapier

```text
Action: MCP Client by Zapier > Run Tool
Server URL: https://cotlet.dev/mcp/v1
Transport: Streamable HTTP
OAuth: No
Bearer Token: <your key>
Tool: skool_read
  operation: list_groups
  arguments: {}
```

In n8n, Make and Zapier pick the app's read or write tool, such as `skool_read`. Put the operation in `operation` and its inputs in `arguments`. An API key is enough there; OAuth is not needed.

No key in Claude Code? Add `https://cotlet.dev/mcp/v1/connect` without the header, run `/mcp` and sign in to Cotlet in the browser. The client gets its own credential, listed on the API keys page, where you can disconnect it like a key.

Product names are trademarks of their owners. Cotlet is not affiliated with them.

## Tools

Each app has two tools named like the app, with dashes as underscores: `skool_read` for the endpoints that read and `skool_write` for the ones that change data. An app that only reads has no write tool. So 70 endpoints cost your agent two tools, not 70.

- `{"operation": "list_members", "arguments": {...}}` runs an operation. Its arguments are the same JSON Schema as the REST endpoint.
- Each tool's input schema carries every operation's arguments, so your agent needs no extra call to learn them.
- Signed in, `tools/list` returns the apps you enabled for agents, within the key's scope; a read-only account or key gets no write tool. Without a key it returns every app's two tools with their operation counts, no schemas.
- Read tools carry `readOnlyHint: true`, so clients can run them without asking. Write tools carry `destructiveHint: true`, so clients ask before each call.
- Each app is also a resource, `cotlet://apps/{app}`, with its description and endpoints.
- Want fewer operations in front of your agent? Create a key for only the apps (or operations) you use.

Account tools, all free: `cotlet_whoami` (which account a connection uses), `cotlet_apps` (which apps work now and what the user still has to do), `cotlet_request_apps`, `cotlet_balance`, `cotlet_get_call` (outcome of a call waiting for approval), `cotlet_report_issue` (a bug or missing feature, straight to the Cotlet team) and `cotlet_upload_file` (a local file for tools that take one, up to 25 MB).

## Calling a tool

Agents call tools for you; this is what goes over the wire:

```bash
curl -X POST https://cotlet.dev/mcp/v1 \
  -H "Authorization: Bearer $COTLET_API_KEY" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/call",
       "params": {"name": "skool_read", "arguments": {"operation": "list_members", "arguments": {"group": "yourgroup"}}}}'
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

## Approval

Tools that reach other people (messages, posts, accepting members) wait for your approval by default. The call returns `status: pending` with a `call_id` instead of a result.

- Approve or reject it in the console under Activity, Approvals. Without a decision it lapses after 24 hours.
- Your agent checks the outcome with `cotlet_get_call` and the `call_id`.
- For automations, set a tool to "Run without approval" in Activity, Approval rules.

## Drive your Cloud Browser

When no Cotlet tool does the job, your agent can work in your Cloud Browser itself, billed per started minute of an open session.

- **Browser tools:** `cotlet_browser_open` opens the app's browser, then `cotlet_browser_navigate`, `_read`, `_screenshot`, `_scroll`, `_click`, `_type`, `_select`, `_press`, `_upload` and `_close`. No extra software on your side.
- **Chrome DevTools:** `cotlet_browser_connect` with `{"app": "skool"}` returns `cdp_url`, a DevTools WebSocket already signed in to the app. Connect Playwright (`chromium.connectOverCDP(cdp_url)`), Puppeteer or `npx chrome-devtools-mcp@latest --wsEndpoint=<cdp_url>`. The URL works for new connections for one hour.
- `cotlet_browser_sessions` lists open sessions with what they cost so far and closes them.

## MCP or REST?

Use MCP when an agent decides what to call. Use [REST](rest-api.md) at `https://cotlet.dev/api/v1` when your own code does: same key, same inputs, same outputs.
