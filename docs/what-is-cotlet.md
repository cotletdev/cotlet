# What is Cotlet?

[← Back to README](../README.md)

**Cotlet** ([cotlet.dev](https://cotlet.dev)) is a catalog of hosted integrations that let an AI agent work in web apps that have no official API, or only a narrow one. Each integration is available as tools in one remote **MCP server** and as a **REST API**. The user signs in to each app once, in a browser; Cotlet keeps only the session, and the agent then works in the user's own account.

## Definition

> Cotlet is a hosted MCP server and REST API for apps with no usable API. Your AI agent signs in as you and does the work.

## Key facts

| Attribute | Value |
|---|---|
| Name | Cotlet |
| Type | Software as a service (developer tool, AI agent infrastructure) |
| Category | Hosted MCP servers, unofficial APIs, AI agent integrations |
| Website | https://cotlet.dev |
| MCP server | `https://cotlet.dev/mcp/v1` (Streamable HTTP) |
| REST API | `https://cotlet.dev/api/v1/{app}/{endpoint}` |
| Auth | One API key (`Authorization: Bearer`) for MCP and REST; OAuth in MCP clients that support it |
| Catalog | 97 apps, 526 documented use cases |
| Clients | Claude Code, Claude Desktop, ChatGPT, Cursor, Codex, GitHub Copilot, Gemini, Windsurf, n8n, any MCP client |
| Pricing | Free 7-day trial with 2,000 credits; one-time credit packs from $29, no subscription |
| Access | Request access; each account is reviewed and gets its API key by email |
| Hosting | European Union (Finland) |
| Market | Worldwide, English |
| Operator | Take Group sp. z o.o., Katowice, Poland |
| Contact | contact@cotlet.dev |
| X | [@cotletdev](https://x.com/cotletdev) |
| GitHub | https://github.com/cotletdev |

## What Cotlet is

- **A catalog of integrations** for apps that never built an API: community platforms (Skool, Substack, Patreon), course platforms (Udemy, Teachable), travel (GetYourGuide, Klook), real estate (Idealista, Zoopla, DoorLoop), local services (Booksy, Fresha, Vagaro) and invoicing tools (Dubsado, Joist).
- **One MCP server** for all of them. Every app a user connects shows up as tools, named `{app}_{endpoint}`.
- **A REST API** with the same actions, for scripts, cron jobs and automation platforms.
- **Maintained access.** Cotlet tests every integration daily, pauses calls when a site changes, fixes it and refunds credits for failed calls.

## What Cotlet is not

- **Not a password manager.** Cotlet never saves passwords: the user signs in to each app themselves, in their own Cloud Browser, where password saving is off.
- **Not a CAPTCHA or MFA bypass.** The user passes those checks; Cotlet never solves or skips them.
- **Not a scraper of other people's data.** The agent works only in the user's own account, with the user's own login.
- **Not an official API.** Cotlet is unofficial and not affiliated with any app in its catalog.
- **Not a general browser agent.** Each integration exposes defined tools with JSON Schema inputs and outputs, not a free-form browser.

## Positioning

The outcome comes first: **your agent signs in and does the work**. MCP is how the agent reaches the apps. The REST API is there for developers: "Built for agents. Scriptable too."

## Who it is for

People and small teams who already work with AI agents and keep clicking through the same apps by hand: community owners, creators, course sellers, tour operators, real estate agents and landlords, salons and local service businesses, field-service trades, freelancers, agencies and developers. See [use-cases.md](use-cases.md).

## Related

- [The problem](problem.md)
- [How it works](how-it-works.md)
- [Comparison with other approaches](comparison.md)
- [Glossary](glossary.md)
