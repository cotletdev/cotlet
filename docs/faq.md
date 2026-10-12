# Cotlet FAQ

[← Back to README](../README.md) · Help center: [cotlet.dev/help](https://cotlet.dev/help)

## Getting started

**What is Cotlet?**
Hosted integrations for apps that have no API. Your AI agent signs in as you and does the work, over one MCP server or a REST API.

**How do I get access?**
[Request access](https://cotlet.dev/signup) and pick your apps. Each request is reviewed and you get your API key by email.

**Which agents does it work with?**
Any MCP client: Claude Code, Claude Desktop, ChatGPT, Cursor, Codex, GitHub Copilot, Gemini, Windsurf, n8n and more. Scripts use the REST API.

**My app is not in the catalog.**
Search for it on the [integrations page](https://cotlet.dev/integrations) and press Request. No account needed. Sign up to count it toward what gets built next.

**Why not a script from GitHub?**
Scripts break when the app changes, and you fix them yourself. Cotlet tests every integration daily, fixes it for you, and refunds credits for failed calls.

## Connecting apps

**How do I connect an app?**
You sign in to the app yourself, once, in a browser on the Cotlet connect page. Only the session is kept.

**Do you store my password?**
No. Your password goes to the app, never to Cotlet's database. Only the session is kept, encrypted with AES-256.

**What about 2FA and CAPTCHAs?**
You pass them yourself when you sign in. Cotlet never solves CAPTCHAs or bypasses MFA.

**What happens when my session expires?**
The call returns `AUTH_EXPIRED` with a link. Your agent asks you to sign in again; Cotlet never logs in for you.

**What can the agent do in my account?**
Only what you allow when you connect: read only, read and edit, or full with your confirmation on every send.

**How do I revoke access?**
Disconnect the app in your dashboard. The session is deleted and access ends at once.

## Pricing and credits

**Is there a free trial?**
Yes. Every account starts with a free 7-day trial and 5,000 credits, no card needed. The trial starts when your access is active.

**Do I pay anything now?**
No. Nothing is charged until your access is active.

**How are credits counted?**
Cotlet meters the work each successful API or MCP call takes. Same rate for every app.

**Do failed calls cost credits?**
No. Only successful calls are charged, and credits for failed calls come back.

**Do unused credits expire?**
After 3 months. Each month's credits stay valid for 3 months and add up; the oldest are used first and you get an email a week before any expire.

**Can I cancel anytime?**
Yes. Plans are billed monthly, with no long-term contract.

## Security and trust

**Do you keep my data?**
No. Data passes through a call to your agent. No payloads are kept after the call ends.

**Can the AI model see my login?**
No. The agent calls tools; the session stays in the vault and never reaches the model.

**Will my account get banned?**
Requests stay human-paced, with one isolated session per user. Cotlet cannot promise, but minimises the risk.

**Is this legal?**
You automate your own account with your own login. Cotlet is unofficial, not affiliated with the apps, and refuses apps that forbid automation.

**Which apps will you never automate?**
Banks without a licence, LinkedIn, Instagram, and any app that sent a cease-and-desist.

**What if an app owner objects?**
The integration is paused within 24 hours for everyone and the affected credits are refunded.

**Where are the servers?**
In the European Union, in a data centre in Finland.

## Troubleshooting

**My agent says `AUTH_REQUIRED`.**
The app is not connected yet. Open the link in the error and sign in to the app.

**My agent says `CAPTCHA_REQUIRED` or `MFA_REQUIRED`.**
The app asked for a check. Open the link in the error and finish it yourself.

**My agent says `SCOPE_DENIED`.**
The action is outside what you allowed. Change the permission level for that app in your dashboard.

**A tool is missing from my agent.**
Check the app is connected, then ask your agent to list tools again. Each connected app adds its tools.

**An integration is paused.**
The daily test found a problem. Cotlet pauses it, fixes it, and refunds credits for failed calls.
