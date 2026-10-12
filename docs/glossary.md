# Glossary

[← Back to README](../README.md)

**Agent (AI agent)**
A program driven by a language model that acts through tools: Claude Code, Claude Desktop, ChatGPT, Cursor, Codex, GitHub Copilot, Gemini, Windsurf, n8n workflows and others.

**API (application programming interface)**
A documented way for code to talk to an app. Cotlet exists for apps where the official API is missing, limited, partners-only or a paid add-on.

**Canary test**
A test Cotlet runs every day against each integration. If it fails, calls to that integration pause until the fix ships.

**Confirmation**
A step where an action that reaches other people (publish, message, email) waits for the user's OK before it runs. On by default; can be switched off per tool.

**Connect page**
The page at `cotlet.dev/app/connect/{app}` where the user signs in to an app themselves. Cotlet keeps only the resulting session.

**Credits**
The only billing unit at Cotlet. Each successful call uses credits for the work it takes, at one rate for every app. Each month's credits stay valid for 3 months.

**Gated API**
An official API available only to approved partners, after an application, a contract or a review.

**Integration**
One app in the Cotlet catalog, exposed as MCP tools and REST endpoints. Its page lives at `cotlet.dev/integrations/{slug}-api-mcp-server`.

**MCP (Model Context Protocol)**
An open protocol that lets AI agents discover and call tools on a server. Cotlet runs one remote MCP server at `https://cotlet.dev/mcp/v1` over Streamable HTTP.

**Request access**
How an account gets access to Cotlet: the user picks their apps, the request is reviewed and the API key arrives by email.

**REST API**
The same actions as the MCP tools, callable over HTTP at `https://cotlet.dev/api/v1/{app}/{endpoint}` with the same key.

**Scope**
What the user allowed for an app when connecting it: read only, read and edit, or full with confirmation on every send. A call outside it returns `SCOPE_DENIED`.

**Session**
The signed-in state an app gives the user after login. Cotlet stores only this, encrypted with AES-256, one isolated session per user and app. Never the password.

**Tool**
One action an agent can call, named `{app}_{endpoint}`, such as `skool_list_members`, with a JSON Schema for its inputs and outputs.

**Unofficial integration**
An integration built without the app vendor's involvement. Cotlet is unofficial and not affiliated with any app in its catalog.

**Use case**
One job a user hands to their agent in a specific app, such as "approve Skool membership requests". Cotlet documents 526 of them; see [use-cases.md](use-cases.md).
