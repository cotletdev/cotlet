# Security at Cotlet

[← Back to README](../README.md) · On the website: [cotlet.dev/security](https://cotlet.dev/security) · Policy: [cotlet.dev/acceptable-use](https://cotlet.dev/acceptable-use)

Your login stays yours. You sign in yourself, in your own Chrome in the cloud. Your agents only get the apps you enable, and every background request is listed.

## Your Cloud Browser

Every Cotlet workspace gets its own Chrome in the cloud, running in Cotlet's EU data centre, with one window per app you sign in to. You open it from the console and sign in the way you do in Chrome at home.

| Question | Chrome on your computer | Your Cloud Browser |
|---|---|---|
| Who signs in | You | You, on the app's own page, with the address bar in view |
| Your password | Often saved by the password manager | Never saved: password saving and autofill are off |
| Second factor and CAPTCHAs | You pass them | You pass them; Cotlet never solves or skips them |
| Network | Your home or office IP | One fixed IP, shown in your console |
| When your computer is off | Nothing runs | Your agents keep working in the apps you enabled |
| What agents can use | Whatever a script can reach | Only the apps you enable, read only or read and write |
| Cutting access | Sign out | Sign out, Disable for agents, or Reset browser |

The browser runs on Cotlet's side, so what you type in it passes through Cotlet's servers on its way to the app. That is why password saving is off and why the signed-in browser is limited as described below.

## How Cotlet holds your access

To be fast, Cotlet doesn't click through pages. It sends the same requests your browser would, from your browser's IP with its cookies. Every request is listed in your Background activity.

```text
You (sign in yourself) ──▶ Your Cloud Browser (one per app) ──▶ Encrypted profile (AES-256-GCM) ──▶ The app (same IP, human pace)

AI model ──tool calls──▶ Cotlet        (the model never sees a login or a cookie)
```

- **We never save your password.** Password saving is off; the profile sleeps encrypted with AES-256-GCM.
- **Every background request is listed:** time, app, tool, address and status, without the content.
- **The model never sees a login.** Agents call tools, not cookies.
- **No payload retention.** Data passes through. Nothing is kept after the call.

## Checked by independent scanners

Free public tests anyone can rerun on cotlet.dev:

- **A+ on [Qualys SSL Labs](https://www.ssllabs.com/ssltest/analyze.html?d=cotlet.dev)**: encryption in transit, TLS setup and certificates.
- **A+ on [securityheaders.com](https://securityheaders.com/?q=cotlet.dev&followRedirects=on)**: browser protections sent with every page.
- **A+ on [Mozilla Observatory](https://developer.mozilla.org/en-US/observatory/analyze?host=cotlet.dev)**: Mozilla's web security baseline.

## Your agents only get the apps you enable

- **Enable for agents, per app:** read only or read and write. Being signed in is not enough.
- **Scope each API key:** its apps, its tools, read only or read and write.
- **Actions that reach other people** (publish, message, email) wait for your OK unless you switch that off per tool.
- **You pass MFA yourself.** Cotlet never bypasses it or asks for codes.
- **Cut access in one click:** Disable for agents, sign out of the app in the browser, or Reset browser.

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
3. **Your credits stay.** Calls that fail cost nothing; your balance works for every other app.

## Uptime

An independent monitor, Better Stack, checks the website, console and API every 3 minutes from Europe, North America, Asia and Australia. Live status and every outage are public at [status.cotlet.dev](https://status.cotlet.dev).

## Where the servers are

In the European Union: the console, API, database and Cloud Browsers run in a data centre in Finland. Each Cloud Browser reaches apps through a fixed IP from Cotlet's proxy provider, listed on [cotlet.dev/subprocessors](https://cotlet.dev/subprocessors). A CDN serves the public website worldwide.

## Your responsibility

You use your own account in each app and stay responsible for following that app's terms. The Cloud Browser may only be used for accounts you are authorized to use ([acceptable use policy](https://cotlet.dev/acceptable-use)). Cotlet is independent and not affiliated with any app in its catalog. Cotlet refuses apps that forbid automation.

## Reporting a vulnerability

See [SECURITY.md](../SECURITY.md).
