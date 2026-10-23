# Glossary

[← Back to README](../README.md)

**Agent (AI agent)**
A program driven by a language model that acts through tools: ChatGPT, Claude, Cursor, n8n workflows and others.

**API (application programming interface)**
A documented way for code to talk to an app. Cotlet exists for apps where the official API is missing, limited, partners-only or a paid add-on.

**Canary test**
A test Cotlet runs every 6 hours against each integration. If it fails, calls to that integration pause until the fix ships.

**Background activity**
The list in the Cotlet console of every request Cotlet sends from the user's Cloud Browser, and every visit that keeps the user signed in: time, app, tool, method, address and status, without the content.

**Cloud Browser**
The user's own Chrome in the cloud, one per app they sign in to, opened from the console at `cotlet.dev/app/browser`. The user signs in to apps there and enables them for agents. It has a fixed IP, sleeps when idle and wakes in seconds; password saving is off.

**Approval**
A step where an action that reaches other people (publish, message, email) waits for the user's OK before it runs. The call returns `status: pending` with a `call_id`. On by default; "Run without approval" switches it off per tool.

**Enable for agents**
The step after signing in to an app in the Cloud Browser: only enabled apps can be used by the user's agents, read only or read and write. "Disable for agents" cuts them off and keeps the user signed in.

**Credits**
The only billing unit at Cotlet, bought in one-time packs valid 12 months. A successful call uses 10 credits; the Cloud Browser uses 50 credits a day while it has an app enabled for agents; an agent driving the browser itself uses 5 credits a minute.

**Gated API**
An official API available only to approved partners, after an application, a contract or a review.

**Integration**
One app in the Cotlet catalog, exposed as MCP tools and REST endpoints. Its page lives at `cotlet.dev/integrations/{slug}-api-mcp-server`.

**MCP (Model Context Protocol)**
An open protocol that lets AI agents discover and call tools on a server. Cotlet runs one remote MCP server at `https://cotlet.dev/mcp/v1` over Streamable HTTP.

**Request access**
How a user adds an app to their account: sign-up is open, and each app is requested in the console. The user creates API keys there too.

**REST API**
The same actions as the MCP tools, callable over HTTP at `https://cotlet.dev/api/v1/{app}/{endpoint}` with the same key.

**Scope**
What the user allowed for an app when enabling it for agents: read only or read and write; an API key can be narrowed further to chosen apps and tools. A call outside it returns `SCOPE_DENIED`.

**Session**
The signed-in state an app gives the user after login. At Cotlet it lives in the user's Cloud Browser, as cookies in a profile stored encrypted with AES-256-GCM. The password is never saved.

**Tool**
One action an agent can call. Over MCP each app has a read tool and a write tool, such as `skool_read` and `skool_write`, and its endpoints are operations such as `list_members`, each with a JSON Schema for its inputs and outputs.

**Unofficial integration**
An integration built without the app vendor's involvement. Cotlet is unofficial and not affiliated with any app in its catalog.

**Use case**
One job a user hands to their agent in a specific app, such as "approve Skool membership requests". Cotlet documents 784 of them; see [cotlet.dev/use-cases](https://cotlet.dev/use-cases).
