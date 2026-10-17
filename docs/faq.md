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
Open your Cloud Browser in the console: your own Chrome in the cloud. Sign in to the app there yourself, then press **Enable for agents**, read only or read and write.

**What is the Cloud Browser?**
One Chrome per workspace that runs on Cotlet's servers in the EU, with a fixed IP shown in your console. It sleeps when nobody uses it and wakes in seconds, so your agents can work in your apps 24/7, even when your computer is off.

**Do you store my password?**
No. Password saving and autofill are off in your Cloud Browser, so Cotlet never saves your password. The signed-in profile is stored encrypted with AES-256-GCM.

**Why does my agent not click in my browser?**
To be fast, Cotlet doesn't click through pages. It sends the same requests your browser would, from your browser's IP with its cookies. Every request is listed in your Background activity.

**What about 2FA and CAPTCHAs?**
You pass them yourself when you sign in. Cotlet never solves CAPTCHAs or bypasses MFA.

**What happens when an app signs me out?**
The call returns `AUTH_EXPIRED` with a link to your Cloud Browser, and you get an email. Sign in to the app there again; Cotlet never logs in for you.

**What can the agent do in my account?**
Only the apps you enable for agents, each read only or read and write. Posts and messages wait for your OK by default.

**How do I revoke access?**
Press **Disable for agents** next to the app, or sign out of it in your Cloud Browser. **Reset browser** in Settings deletes the whole profile.

## Pricing and credits

**Is there a free trial?**
Yes. Every account starts with a free 7-day trial and 2,000 credits, no card needed. You start it in the dashboard once your access is active.

**Do I pay anything now?**
No. Nothing is charged unless you buy a credit pack.

**How are credits counted?**
Credit packs from $29 for 5,000 credits, one-time, no subscription. A successful call uses 20 to 30 credits (25 for most tools), and your Cloud Browser uses 50 credits a day while it has an app enabled for agents, however many apps that is.

**Do failed calls cost credits?**
No. Only successful calls are charged; a failed call costs nothing.

**Do unused credits expire?**
After 12 months. Packs stack, the credits that expire first are used first, and you get an email a week before any expire.

**Is it a subscription?**
No. Credit packs are one-time purchases and nothing renews, so there is nothing to cancel.

## Security and trust

**Do you keep my data?**
No. Data passes through a call to your agent. No payloads are kept after the call ends.

**Can the AI model see my login?**
No. The agent calls tools; logins and cookies stay in your Cloud Browser and never reach the model.

**Will my account get banned?**
Every call comes from the same browser and fixed IP you signed in with, at a human pace. Cotlet cannot promise, but minimises the risk.

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
The app is not signed in or not enabled for agents yet. Open the link in the error, sign in to the app in your Cloud Browser and press Enable for agents.

**My agent says `CAPTCHA_REQUIRED` or `MFA_REQUIRED`.**
The app asked for a check. Open the link in the error and finish it yourself in your Cloud Browser.

**My agent says `SCOPE_DENIED`.**
The action is outside what you allowed. Switch the app to read and write in your Cloud Browser, or widen the API key in your dashboard.

**A tool is missing from my agent.**
Check the app is enabled for agents, then ask your agent to list tools again. Each connected app adds its tools.

**An integration is paused.**
The daily test found a problem. Cotlet pauses it and fixes it; failed calls cost nothing.
