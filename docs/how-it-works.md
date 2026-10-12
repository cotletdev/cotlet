# How Cotlet works

[← Back to README](../README.md) · On the website: [cotlet.dev/how-it-works](https://cotlet.dev/how-it-works)

Sign in once. Your agent does the clicking.

## Four steps from your app to a finished task

### 1. Find your app

Pick it from the [catalog](https://cotlet.dev/integrations). Its tools are ready to use. Not there? Request it; if enough people ask, it gets built.

### 2. Sign in with your account

[Request access](https://cotlet.dev/signup) and pick your apps. Each request is reviewed and the API key arrives by email. Then you sign in to each app yourself, once, in a browser on the Cotlet connect page. You pass any 2FA or CAPTCHA yourself. Cotlet never sees or stores your password; only the session is kept, encrypted with AES-256.

While connecting, you choose what the agent may do in that app: **read only**, **read and edit**, or **full**, with your confirmation on every send.

### 3. Add it to your agent over MCP

Paste one MCP URL into your agent:

```bash
claude mcp add --transport http cotlet https://cotlet.dev/mcp/v1 \
  --header "Authorization: Bearer $COTLET_API_KEY"
```

Each connected app shows up as tools, for example `booksy_reschedule_booking` or `skool_approve_membership_request`. Scripts use the same actions over REST. See [mcp-server.md](mcp-server.md) and [rest-api.md](rest-api.md).

### 4. Automate it and forget it

Your agent does the work on request or on a schedule:

> *"Move all of Friday's bookings to Monday and let the clients know."*
>
> Tool call over MCP → signed in with your session → bookings moved in the app.
>
> *"Done. 6 bookings moved to Monday, clients notified."*

## What happens on each call

```text
Your agent ──tools/call──▶ Cotlet MCP server ──▶ checks key, plan and consent
                                              ──▶ runs the action in your account with your session
                                              ◀── returns structured JSON
```

1. Cotlet checks your API key, your access to the app and the scope you allowed.
2. The action runs in an isolated session for you and that app, at a human pace.
3. The result comes back as JSON: `structuredContent` for code and text for the model.
4. Credits are used only if the call succeeds.

## Confirmations

Actions that reach other people (publish, message, email) wait for your OK by default. The call returns `awaiting_confirmation` with a link; you approve, and the agent reads the result. To run such a job on a schedule, switch confirmation off for that tool in your dashboard.

## When the session expires

The call returns `AUTH_EXPIRED` with a link. Your agent asks you to sign in again. Cotlet never logs in for you.

## When a site changes

Every integration has its own status.

| Stage | What happens |
|---|---|
| **Live** | The daily canary test passes. |
| **Paused** | The site changed and the test failed. Calls pause until the fix ships. |
| **Fixed** | The integration is live again. Credits for failed calls are refunded. |

## Your password and data stay yours

- **No password stored.** You sign in yourself; Cotlet keeps only an encrypted session you can revoke.
- **Cotlet does not read your data.** It goes from the app straight to your agent.
- **Nothing saved to disk.** Results live in memory for the call and are gone after it.

More in [security.md](security.md).
