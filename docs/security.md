# Security at Cotlet

[← Back to README](../README.md) · On the website: [cotlet.dev/security](https://cotlet.dev/security) · Policy: [cotlet.dev/acceptable-use](https://cotlet.dev/acceptable-use)

Your login stays yours. You sign in yourself; Cotlet keeps only the session, scoped to the actions you allow.

## How Cotlet holds your access

Your password never reaches Cotlet. Only the session goes into the vault.

```text
You (sign in once) ──▶ Encrypted vault (AES-256-GCM) ──▶ Isolated session (per user and app) ──▶ The app (human-paced calls)

AI model ──tool calls──▶ Cotlet        (the model never sees a login or a password)
```

- **No stored passwords.** Only the session, encrypted with AES-256-GCM, the same cipher 1Password uses for its vaults and Apple for iCloud Keychain.
- **One isolated session per user and app.** Never shared between users.
- **The model never sees a login.** Agents call tools, not sessions.
- **No payload retention.** Data passes through. Nothing is kept after the call.

## Checked by independent scanners

Free public tests anyone can rerun on cotlet.dev:

- **A+ on [Qualys SSL Labs](https://www.ssllabs.com/ssltest/analyze.html?d=cotlet.dev)**: encryption in transit, TLS setup and certificates.
- **A+ on [securityheaders.com](https://securityheaders.com/?q=cotlet.dev&followRedirects=on)**: browser protections sent with every page.
- **A+ on [Mozilla Observatory](https://developer.mozilla.org/en-US/observatory/analyze?host=cotlet.dev)**: Mozilla's web security baseline.

## Scoped consent, action by action

Agents can only do what you ticked.

- **You pick the actions:** read only, read and edit, or full with your confirmation on every send.
- **You pass MFA yourself.** Cotlet never bypasses it or asks for codes.
- **Revoke in one click.** Disconnect an app in your dashboard; the session is deleted and access ends at once.
- **Actions that reach other people** (publish, message, email) wait for your OK unless you switch that off per tool.

## What Cotlet never does

- Break CAPTCHAs
- Bypass MFA
- Automate banks without a licence
- Touch LinkedIn or Instagram
- Keep going after a cease-and-desist
- Store your data longer than the call

## If a site objects

1. **A cease-and-desist arrives.** The app owner asks Cotlet to stop.
2. **Paused within 24 hours.** The integration stops for everyone.
3. **Your credits refunded.** Affected credits come back to you.

## Uptime

An independent monitor, Better Stack, checks the website, console and API every 3 minutes from Europe, North America, Asia and Australia. Live status and every outage are public at [status.cotlet.dev](https://status.cotlet.dev).

## Where the servers are

In the European Union: the console, API, database and session vault run in a data centre in Finland. A CDN serves the public website worldwide.

## On the roadmap

Planned, not done yet. Cotlet will say when they ship.

- **Service accounts**: add a Cotlet user to your team app instead of your own login.

## Your responsibility

You use your own account in each app and stay responsible for following that app's terms. Cotlet is independent and not affiliated with any app in its catalog. Cotlet refuses apps that forbid automation.

## Reporting a vulnerability

See [SECURITY.md](../SECURITY.md).
