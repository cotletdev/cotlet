# Installing the Cotlet MCP server (for AI agents such as Cline)

Cotlet is a hosted, remote MCP server. There is nothing to clone, build or run locally.

## 1. Get an API key

The user signs up at https://cotlet.dev/signup, turns on or requests the apps they need, signs in to each app once in their Cloud Browser, and creates an API key in the console at https://cotlet.dev/app (API keys). Ask the user for the key; never guess one.

## 2. Add the server

Add this entry to the MCP settings (for Cline: `cline_mcp_settings.json`), replacing `<your key>`:

```json
{
  "mcpServers": {
    "cotlet": {
      "type": "streamableHttp",
      "url": "https://cotlet.dev/mcp/v1",
      "headers": { "Authorization": "Bearer <your key>" },
      "disabled": false
    }
  }
}
```

Clients with OAuth sign-in can use `https://cotlet.dev/mcp/v1/connect` without a key instead.

## 3. Check it works

1. Call `cotlet_whoami`: it returns the signed-in account and the apps it may use.
2. Each app is one tool, such as `skool`. Call it with `{}` to list its operations, with `{"tool": "list_groups"}` to get one operation's input schema, and with `{"tool": "list_groups", "arguments": {}}` to run it.

If a call returns `access_not_granted`, the user must turn the app on or request it at the `integrations_url` in the response. Actions that reach other people (publish, message, email) return `status: pending` with an `approval_url` and run only after the user approves them.

Docs: https://cotlet.dev/docs/mcp
