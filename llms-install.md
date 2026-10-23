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
2. Each app has a read tool and, when it can change data, a write tool: `skool_read`, `skool_write`. The tool's input schema lists every operation with its inputs. Run one with `{"operation": "list_groups", "arguments": {}}`.
3. `cotlet_apps` says which apps work now and what the user still has to do, such as sign in to the app in the Cloud Browser or enable it for agents.

If a call returns `access_not_granted`, the user must add the app or request it at the `integrations_url` in the response. Actions that reach other people (publish, message, email) return `status: pending` with a `call_id` and run only after the user approves them in the console; `cotlet_get_call` reports the outcome.

Docs: https://cotlet.dev/docs/mcp
