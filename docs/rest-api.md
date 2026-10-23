# Cotlet REST API

[← Back to README](../README.md) · Full docs: [cotlet.dev/docs/api](https://cotlet.dev/docs/api) (Markdown: [cotlet.dev/docs/api.md](https://cotlet.dev/docs/api.md))

The same actions your agent calls over MCP, as a REST API for your scripts, cron jobs and automation platforms. One key for both.

## Endpoint pattern

```text
{METHOD} https://cotlet.dev/api/v1/{app}/{path}
```

Each operation has its own method and path, for example `GET /api/v1/skool/groups/{group}/members`. Routes of any app: `GET https://cotlet.dev/api/v1/apps/{slug}`, no key needed.

## Authentication

```text
Authorization: Bearer COTLET_API_KEY
Content-Type: application/json
```

Every endpoint, its parameters and an example response are readable without an account on the app's Markdown page, for example [cotlet.dev/docs/api/skool.md](https://cotlet.dev/docs/api/skool.md). Calling an endpoint needs an API key and returns `401` without one.

## Making a call

```bash
curl "https://cotlet.dev/api/v1/skool/groups/yourgroup/members?role=admin" \
  -H "Authorization: Bearer $COTLET_API_KEY"
```

- Inputs are validated against the endpoint JSON Schema before anything runs.
- Unknown fields are rejected, so a typo never runs silently.
- Path parameters such as `{group}` go in the URL. Other inputs go in the query for `GET` and `DELETE`, in a JSON body for `POST`, `PUT` and `PATCH`.
- A known path with the wrong method returns `405` with an `Allow` header.

## Responses

A successful call returns `200` and the endpoint output as JSON:

```json
{
  "members": [
    {
      "member_id": "m_8c41d2",
      "name": "Ana Lopez",
      "role": "member",
      "joined_at": "2026-10-01T18:21:00Z"
    }
  ],
  "next_cursor": "eyJvZmZzZXQiOjUwfQ"
}
```

| Header | Meaning |
|---|---|
| `X-Request-Id` | ID of the call. Quote it when you contact support. |
| `X-Credits-Used` | Credits this call used. Failed calls use none. |
| `Link` | Docs of the app, as `rel="describedby"`. |

## Pagination

List endpoints return up to `limit` items and a `next_cursor`. Pass it as `cursor` to get the next page; `null` means you have everything.

```json
{"group": "yourgroup", "cursor": "eyJvZmZzZXQiOjUwfQ"}
```

## Approval

Endpoints marked **Confirm** reach other people: they publish, message or email. By default each call waits for your approval and returns `202`:

```json
{
  "call_id": "0f3c2a91-6b7e-4d1a-9c55-2e8f1b7d4a60",
  "status": "pending",
  "app": "skool",
  "tool": "send_message",
  "approval_url": "https://cotlet.dev/app/activity?tab=approvals",
  "status_url": "https://cotlet.dev/api/v1/calls/0f3c2a91-6b7e-4d1a-9c55-2e8f1b7d4a60",
  "expires_at": "2026-10-18T09:12:00+00:00"
}
```

Approve it at the `approval_url`, then `GET` the `status_url` for the outcome. Without a decision the call lapses at `expires_at` and nothing is sent. To run on a schedule without you, set the endpoint to "Run without approval" in Activity, Approval rules.

## Errors

Errors return JSON with an `error` code, a `message` written for your agent, and a link when you need to act:

```json
{
  "error": "access_not_granted",
  "message": "This API key has no access to Skool.",
  "request_access_url": "https://cotlet.dev/signup?app=skool",
  "docs_url": "https://cotlet.dev/integrations/skool-api-mcp-server"
}
```

| Status | Code | What happened | What to do |
|---|---|---|---|
| 400 | `invalid_input` | The inputs do not match the endpoint schema. | Fix the fields named in `details`. |
| 402 | `insufficient_credits` | Your credits ran out. | Buy a credit pack in the dashboard; calls and your Cloud Browser resume after the purchase. |
| 401 | `api_key_required` | No API key on the call. | Send `Authorization: Bearer`. |
| 401 | `invalid_api_key` | The key is unknown, expired or revoked. | Create a new key in the dashboard. |
| 403 | `access_not_granted` | The key has no access to this app. | Request the app with the link in the error. |
| 404 | `unknown_app`, `unknown_endpoint` | No such app, or no endpoint at this path. | The error lists the valid routes. |
| 405 | `method_not_allowed` | The path is an endpoint, but not with this method. | Use a method from the `Allow` header. |
| 403 | `AUTH_REQUIRED` | The app is not signed in to in your Cloud Browser, or not enabled for agents. | Open the `browser_url`, sign in and press Enable for agents. |
| 403 | `AUTH_EXPIRED` | The app signed you out. | Open the `browser_url` and sign in again. |
| 403 | `CAPTCHA_REQUIRED`, `MFA_REQUIRED` | The app asked for a check only you can pass. | Finish it in your Cloud Browser at the `browser_url`. |
| 403 | `SCOPE_DENIED` | The action is outside what you allowed. | Switch the app to read and write at the `browser_url`, or widen the key in the dashboard. |
| 403 | `APP_PERMISSION_DENIED` | Your account in the app lacks the role for this, e.g. it is not a group admin. | Use a group or item your account manages. Nothing was charged. |
| 403 | `BROWSER_SUSPENDED` | We suspended your Cloud Browser. | Contact us at the `support_url`. |
| 429 | `rate_limited` | Too many requests. | Wait for `Retry-After` seconds. |
| 403 | `TARGET_BLOCKED` | The app refused the account. | Nothing was charged; tell the user. |

## Drive your Cloud Browser

Scripts can drive your Cloud Browser over Chrome DevTools, one browser per app, signed in to that app only:

```text
POST https://cotlet.dev/api/v1/browser/cdp-sessions
Authorization: Bearer COTLET_API_KEY
Content-Type: application/json

{"app": "skool"}
```

The answer is `201` with `cdp_url`, `expires_at` and `credits_per_minute`. Connect Playwright, Puppeteer or any CDP client to `cdp_url`. Every started minute of an open connection is charged; `402` means no credits left.

## Rate limits

| What | Limit |
|---|---|
| Calls to endpoints | 60 a minute per key |
| Listing apps, endpoints and schemas | 120 a minute per IP |
| MCP messages | 120 a minute per key |

Over the limit you get `429` with a `Retry-After` header. Apps have limits of their own; Cotlet paces calls so your account stays within them.

## Discovery

```bash
curl https://cotlet.dev/api/v1/apps
```

| Endpoint (no key) | Returns |
|---|---|
| `GET /api/v1/apps` | Every app with its endpoint count and links |
| `GET /api/v1/apps/{app}` | One app: what it is, how it connects, its endpoints with method and path |
| `GET /api/v1/apps/{app}/endpoints/{endpoint}` | One endpoint: full input JSON Schema and an example response |

See also [for-ai-agents.md](for-ai-agents.md).
