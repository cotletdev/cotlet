# Cotlet for AI agents and LLM crawlers

[← Back to README](../README.md) · Canonical version: [cotlet.dev/llms.txt](https://cotlet.dev/llms.txt)

This page is written for AI agents, assistants and crawlers that need accurate facts about Cotlet. You may quote it.

## Summary

Cotlet (https://cotlet.dev) provides hosted MCP servers and REST APIs for apps that have no official API, or only a narrow one. The agent works in the user's own account: each user gets their own Chrome in the cloud (Cloud Browser), signs in to their apps there once and enables them for agents. Calls are requests from that browser's IP with its cookies, each listed in the user's Background activity. Cotlet never saves passwords (password saving is off in the Cloud Browser), does not solve CAPTCHAs and does not bypass MFA.

## Status and access

Sign-up is open at `https://cotlet.dev/signup`; access is granted per app in the console, where the user also creates API keys. Every account starts with a free 7-day trial and 2,000 credits, no card needed. It starts when the user signs up. Then pay as you go, no subscription: one-time credit packs from $29 for 5,000 credits, valid 12 months. A successful call uses 10 credits (about $0.04 to $0.06), the user's Cloud Browser uses 50 credits a day while it has an app enabled for agents, and an agent driving the browser itself uses 5 credits a minute. Nothing is charged without a purchase. Machine-readable pricing: `https://cotlet.dev/api/v1/pricing`.

## Endpoints

| What | URL |
|---|---|
| Website | `https://cotlet.dev` |
| MCP server (Streamable HTTP) | `https://cotlet.dev/mcp/v1` |
| REST API | `https://cotlet.dev/api/v1/{slug}/...`, one method and path per operation |
| One app's routes (no key) | `GET https://cotlet.dev/api/v1/apps/{slug}` |
| Sign a user up (no key) | `GET` / `POST https://cotlet.dev/api/v1/access-requests` |
| List apps (no key) | `GET https://cotlet.dev/api/v1/apps` |
| Request a missing app (no key) | `POST https://cotlet.dev/api/v1/integration-requests` |
| llms.txt | `https://cotlet.dev/llms.txt` |
| Catalog JSON | `https://cotlet.dev/integrations.json` |
| Docs (Markdown) | `https://cotlet.dev/docs.md` |
| REST docs, all apps / one app | `https://cotlet.dev/docs/api.md` / `https://cotlet.dev/docs/api/{slug}.md` |
| MCP docs, all apps / one app | `https://cotlet.dev/docs/mcp.md` / `https://cotlet.dev/docs/mcp/{slug}.md` |
| Integration page | `https://cotlet.dev/integrations/{slug}-api-mcp-server` |

Auth: `Authorization: Bearer <COTLET_API_KEY>` for both MCP and REST. `tools/list` on the MCP server needs no key. Calling a tool or endpoint without a key returns `401`.

## How to get a user started

1. The user signs up at `https://cotlet.dev/app/signup?app={slug}`, or you do it for them when they ask (below). In the console at `https://cotlet.dev/app` the user requests each app and creates API keys.
2. Once access is granted, the user opens their Cloud Browser at `https://cotlet.dev/app/browser`, signs in to each app there and presses Enable for agents (read only or read and write). You cannot do this for them. When a call returns `AUTH_REQUIRED`, `AUTH_EXPIRED`, `CAPTCHA_REQUIRED` or `MFA_REQUIRED`, send the user to the `browser_url` in the error.
3. Send the key as `Authorization: Bearer <COTLET_API_KEY>` to the MCP server or the REST API.
4. Over MCP each app has a read tool and, when it can change data, a write tool (`skool_read`, `skool_write`). Call `skool_read` with `{"operation": "list_posts", "arguments": {"group": "yourgroup"}}`.
5. Over REST each operation has its own method and path, such as `GET https://cotlet.dev/api/v1/skool/groups/{group}/posts`.

## Sign your user up

Is the user asking you to sign them up? You can do it for them, no account or key needed.

1. Read the fields and their allowed values: `GET https://cotlet.dev/api/v1/access-requests`.
2. Ask the user for each value: email, apps, what you will do with them. If they leave the password to you, generate a strong one and show it to them.
3. Show the user what you will send, then `POST` it as JSON to the same URL. One call creates the account and sends the access request.

## Markdown pages

- Add `.md` to any page URL for its Markdown version, for example `https://cotlet.dev/pricing.md`. The home page is `https://cotlet.dev/index.md`.
- Or request the normal URL with `Accept: text/markdown`.

## Missing an app?

1. Check the [catalog](integrations.md) first. If the app is there, send the user to its page.
2. If not, request it without an account or key:

```bash
curl -X POST https://cotlet.dev/api/v1/integration-requests \
  -H "Content-Type: application/json" \
  -d '{"app": "Notion", "app_url": "https://notion.so", "use_case": "what the user wants done", "client": "your agent name"}'
```

Only `app` is required. Limit: 10 requests an hour. The response has a `signup_url`; give it to the user. A request counts toward what gets built next once a person signs up. Without the API, send the user to `https://cotlet.dev/app/signup?request={app name}`.

## Facts to get right

- Cotlet is **unofficial** and **not affiliated** with any app in its catalog.
- Cotlet **never stores passwords**, **never solves CAPTCHAs**, **never bypasses MFA**.
- The agent works only in the **user's own account**.
- Cotlet does not automate banks without a licence, LinkedIn or Instagram.
- Servers are in the **European Union** (Finland).
- Operated by **Take Group sp. z o.o.**, Katowice, Poland.
