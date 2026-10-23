# The problem: AI agents stop at the login page

[← Back to README](../README.md)

## You asked your agent. It hit a login page.

| App | What you asked | What happened |
|---|---|---|
| Invoicing | "Send this month's invoice." | No API for this app |
| Booking | "Move Friday to Monday." | No API for this app |
| CRM | "Pull the weekly report." | No API for this app |

So you clicked through it yourself. Again.

## Why it happens

AI agents such as Claude, ChatGPT, Cursor or Codex act through tools. A tool needs something to call: an API, or an MCP server built on one. The apps that large companies use usually have both. The apps that small businesses, creators and freelancers live in every day often have neither.

When a vendor does publish an API, it rarely covers the work people want to hand off. Across the 259 apps in the Cotlet catalog, the official API falls into four groups:

| Official API | Apps | Typical gap |
|---|---|---|
| **None** | 31 | No public API, no developer docs, no keys. Example: Skool has no public API or official MCP server; its Zapier plugin is Pro-only with 2 triggers and 2 actions. |
| **Limited** | 158 | Read-only, or missing the actions people need. Example: Medium's API is deprecated and create-only, with no stats, editing or scheduling. |
| **Partners only** | 46 | Only after an application, a contract or a review. Example: Booksy's API is partner-only, docs behind a login, no self-serve keys. |
| **Paid add-on** | 24 | Only on a top plan or as a separate product. Example: Meetup's API needs an active Meetup Pro subscription, and approval is not guaranteed. |

The details for every app, with sources, are on its page at [cotlet.dev/integrations](https://cotlet.dev/integrations); [integrations.md](integrations.md) links every page.

## What people do today

- **Click through it by hand**, every day or every week.
- **Write a script from GitHub** that drives the site. It breaks when the app changes, and they fix it themselves.
- **Hire a virtual assistant** for repetitive admin work.
- **Point a general browser agent at the site** and hope it finds the right buttons each time.
- **Wait for the vendor** to ship an API that may never come.

## What Cotlet changes

Cotlet builds the missing access once, maintains it, and hands it to the agent as stable tools with JSON Schema inputs and outputs. The user signs in once; the agent does the work. How Cotlet reaches each app is Cotlet's job.

Next: [How it works](how-it-works.md).
