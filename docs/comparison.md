# Cotlet compared with other ways to automate an app with no API

[← Back to README](../README.md)

When an app has no usable API, there are a few ways to get an AI agent or a script to work in it. This page compares them honestly, including where Cotlet is not the right choice.

| | Click by hand | Script from GitHub | RPA tool | General browser agent | Official API (if any) | **Cotlet** |
|---|---|---|---|---|---|---|
| Works without a vendor API | Yes | Yes | Yes | Yes | No | **Yes** |
| Stable tool names and JSON Schema | No | Depends | No | No | Yes | **Yes** |
| Works over MCP with your agent | No | Build it yourself | Rarely | Yes | Sometimes | **Yes, one server for all apps** |
| REST API for scripts | No | Build it yourself | Sometimes | No | Yes | **Yes, same key** |
| Who fixes it when the site changes | Nobody needs to | You | You | Nobody, it retries | The vendor | **Cotlet, tested every 6 hours** |
| Failed runs cost you | Time | Time | Licence + time | Tokens | Depends | **Nothing, credits refunded** |
| Where your password lives | In your head | Often in a `.env` file | In the RPA vault | Often in the prompt or browser | OAuth | **Nowhere: you sign in in your own Cloud Browser, password saving off** |
| Setup | None | Install, configure, host | Build flows | Prompting each time | Apply, get approved, code | **Sign in once in your Cloud Browser, paste one URL** |

## When to use what

- **Use the official API** when it exists and covers your job. It is the most stable option.
- **Use a script from GitHub** when you enjoy maintaining it and the app rarely changes.
- **Use a general browser agent** for one-off tasks in sites nobody has integrated.
- **Use Cotlet** when you want your agent to do the same job in an app with no usable API, reliably, every day or every week, without maintaining anything and without giving your password to anyone.

## Why not a script from GitHub?

Scripts break when the app changes, and you fix them yourself. Cotlet tests every integration every 6 hours, pauses calls when a site changes, ships the fix and refunds credits for failed calls. How Cotlet reaches each app is its job; you just call the tools.

## Per-app comparisons

Each integration page on cotlet.dev compares, for that specific app, what the vendor offers itself (API, Zapier and similar connectors) and what community MCP servers on GitHub do, next to Cotlet, with sources. Example: [Skool API and MCP server](https://cotlet.dev/integrations/skool-api-mcp-server).
