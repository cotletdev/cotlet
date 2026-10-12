# Cotlet REST API

[← Back to README](../README.md) · Full docs: [cotlet.dev/docs/api](https://cotlet.dev/docs/api) (Markdown: [cotlet.dev/docs/api.md](https://cotlet.dev/docs/api.md))

The same actions your agent calls over MCP, as a REST API for your scripts, cron jobs and automation platforms. One key for both.

## Endpoint pattern

```text
POST https://cotlet.dev/api/v1/{app}/{endpoint}
```

## Authentication

```text
Authorization: Bearer COTLET_API_KEY
Content-Type: application/json
```

Every endpoint, its parameters and an example response are readable without an account on the app's Markdown page, for example [cotlet.dev/docs/api/skool.md](https://cotlet.dev/docs/api/skool.md). Calling an endpoint needs an API key and returns `403` without one.

## Making a call

```bash
curl -X POST https://cotlet.dev/api/v1/skool/list_members \
  -H "Authorization: Bearer $COTLET_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"group": "yourgroup", "role": "admin"}'
```

- Inputs are validated against the endpoint JSON Schema before anything runs.
- Unknown fields are rejected, so a typo never runs silently.
- `GET` with the inputs as query parameters works for read endpoints.

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

## Confirmation

Endpoints marked **Confirm** reach other people: they publish, message or email. By default each call waits for your OK before it runs:

```json
{
  "status": "awaiting_confirmation",
  "call_id": "call_7f2a91",
  "confirm_url": "https://cotlet.dev/app/confirm/call_7f2a91"
}
```

Open the `confirm_url`, approve, and read the result with `GET /api/v1/calls/{call_id}`. To run on a schedule without you, switch confirmation off for that endpoint in your dashboard.

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
| 400 | `invalid_input` | The body does not match the endpoint schema. | Fix the fields named in `details`. |
| 402 | `insufficient_credits` | Your credits ran out. | Wait for your next monthly credits or move to a bigger size in the dashboard. |
| 403 | `api_key_required` | No API key on the call. | Send `Authorization: Bearer`. |
| 403 | `access_not_granted` | The key has no access to this app. | Request access with the link in the error. |
| 404 | `unknown_app`, `unknown_endpoint` | No such app or endpoint. | The error lists the valid names. |
| 409 | `AUTH_REQUIRED` | The app is not connected yet. | Open the `connect_url` and sign in. |
| 409 | `AUTH_EXPIRED` | The app session expired or was revoked. | Open the `connect_url` and sign in again. |
| 409 | `CAPTCHA_REQUIRED`, `MFA_REQUIRED` | The app asked for a check only you can pass. | Finish it on the connect page. |
| 403 | `SCOPE_DENIED` | The action is outside what you allowed. | Widen access in the dashboard. |
| 429 | `rate_limited` | Too many requests. | Wait for `Retry-After` seconds. |
| 503 | `TARGET_BLOCKED` | The app blocked access; the endpoint is paused. | Try later. Credits are refunded. |

## Rate limits

Over the limit you get `429` with a `Retry-After` header. Apps have limits of their own; Cotlet paces calls so your account stays within them.

## Discovery

```bash
curl https://cotlet.dev/api/v1/apps
```

Lists every app with its endpoints. See also [for-ai-agents.md](for-ai-agents.md).
