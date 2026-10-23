# How Cotlet works

[← Back to README](../README.md) · On the website: [cotlet.dev/how-it-works](https://cotlet.dev/how-it-works)

Your own Chrome in the cloud. Sign in to your apps once, your agent works in them 24/7, even when your computer is off.

## Four steps from your app to a finished task

### 1. Find your app

Pick it from the [catalog](https://cotlet.dev/integrations). Its tools are ready to use. Not there? Request it; if enough people ask, it gets built.

### 2. Sign in, in your Cloud Browser

[Sign up free](https://cotlet.dev/signup) and add your apps in the console. The 7-day trial with 2,000 credits starts at once. Then:

1. **Open your Cloud Browser** in the console (`cotlet.dev/app/browser`). It is your own Chrome that runs on Cotlet's servers in the EU, with a fixed IP shown in the console. Each app gets its own window, sharp as the app's own site, locked to that app's pages.
2. **Sign in to the app yourself**, on the app's own page, also with Google if you like. You pass any 2FA or CAPTCHA yourself. Password saving and autofill are off in this browser, so Cotlet never saves your password.
3. **Enable it for your agents.** The console shows the apps you are signed in to ("Skool: signed in as Jake"). Signing in alone gives agents nothing; you press **Enable for agents** and pick **read only** or **read and write**.

The browser sleeps when nobody uses it and wakes in seconds; its profile is stored encrypted with AES-256-GCM.

### 3. Add it to your agent over MCP

Paste one MCP URL into your agent:

```bash
claude mcp add --transport http cotlet https://cotlet.dev/mcp/v1 \
  --header "Authorization: Bearer $COTLET_API_KEY"
```

Each app you enable shows up as a read tool and a write tool, for example `skool_read` and `skool_write`. The agent picks an operation, such as `approve_membership_request`, and passes its inputs. Scripts use the same actions over REST. See [mcp-server.md](mcp-server.md) and [rest-api.md](rest-api.md).

### 4. Automate it and forget it

Your agent does the work on request or on a schedule:

> *"Move all of Friday's bookings to Monday and let the clients know."*
>
> Tool call over MCP → signed in, in your Cloud Browser → bookings moved in the app.
>
> *"Done. 6 bookings moved to Monday, clients notified."*

## What happens on each call

```text
Your agent ──tools/call──▶ Cotlet MCP server ──▶ checks key, scope, credits and approval
                                              ──▶ sends the app's own request from your Cloud Browser's IP, with its cookies
                                              ◀── returns structured JSON
```

1. Cotlet checks your API key, your access to the app and the scope you allowed.
2. To be fast, Cotlet doesn't click through pages. It sends the same requests your browser would, from your browser's IP with its cookies, at a human pace. Every request is listed in your **Background activity** in the console.
3. The result comes back as JSON: `structuredContent` for code and text for the model.
4. Credits are used only if the call succeeds.

## Confirmations

Actions that reach other people (publish, message, email) wait for your OK by default. The call returns `status: pending` with a `call_id`. You approve or reject it in the console under Activity, Approvals, and the agent reads the outcome with `cotlet_get_call`. Without a decision it lapses after 24 hours. To run such a job on a schedule, set that tool to "Run without approval" in Activity, Approval rules.

## When an app signs you out

The call returns `AUTH_EXPIRED` with a `browser_url` to your Cloud Browser, and you get an email. Your agent asks you to sign in again there. Cotlet never logs in for you.

## How you cut access

- **Sign out** of the app in your Cloud Browser: calls stop from the next one.
- **Disable for agents** next to the app: agents lose access at once, you stay signed in.
- **Reset browser** in Settings: the whole profile is deleted.

## When a site changes

Every integration has its own status.

| Stage | What happens |
|---|---|
| **Live** | The canary test, run every 6 hours, passes. |
| **Paused** | The site changed and the test failed. Calls pause until the fix ships. |
| **Fixed** | The integration is live again. Credits for failed calls are refunded. |

## Your password and data stay yours

- **No password saved.** You sign in yourself, in your own browser, where password saving is off.
- **Cotlet does not read your data.** It goes from the app straight to your agent.
- **Nothing saved to disk.** Results live in memory for the call and are gone after it.

More in [security.md](security.md).
