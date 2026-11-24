# Seercraft MCP server

**Competitor Meta ad intelligence for AI assistants.** Connect [Seercraft](https://seercraft.io) to Claude, ChatGPT, Cursor or any MCP client and ask in plain words:

- *What did my competitors launch or stop on Meta this week?*
- *Which hooks have my competitors' longest-running ads used?*
- *Give me 3 ad tests for my brand based on what competitors are running.*
- *What offers is this brand running right now, and are any new this month?*

Seercraft reads your tracked competitors' Facebook and Instagram ads every day from Meta's public Ad Library, groups near-identical ads into ideas, and answers from your own workspace. Every result cites the ads behind it, with links. Counts come from Seercraft's data, not the model.

## Connect

| | |
|---|---|
| Server URL | `https://api.seercraft.io/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 (PKCE + dynamic client registration) |

- **Claude:** Settings → Connectors → Add custom connector → paste the URL → Connect.
- **ChatGPT / Cursor / others:** add a remote MCP server with the URL above; sign in when prompted.

You pick one workspace at sign-in. Read-only by default; tick **Allow changes** to let the assistant create boards and briefs. It never deletes, publishes or bills. Requires a paid Seercraft plan ([7-day free trial](https://seercraft.io/pricing)).

## Tools (13 read, 5 write)

| Tool | What it does |
|---|---|
| `what_changed` | New, stopped and relaunched ads per tracked brand in a window |
| `search_ads` | Find and count ads, grouped by idea; filter by copy, status, format, platform, run days, hook, angle, offer, persona |
| `get_ad` | One ad: facts, copy, landing page, version count, related ads |
| `breakdown` | An ad's stored AI breakdown (hook, angle, offer, proof, persona) |
| `longest_running` | A brand's longest-running ads, one row per idea |
| `creative_patterns` | How ideas use hooks, angles, offers, formats, personas or proof |
| `brand_profile` | A brand's ad mix over everything Seercraft has read |
| `my_brand` | Your own brand profile |
| `test_plan` | This week's "3 tests to run next" |
| `list_boards` / `get_board` | Your boards and their ads |
| `list_briefs` / `get_brief` | Your creative briefs |
| `create_board` / `add_ads_to_board` | Save ads into boards (write) |
| `create_brief_from_ads` | Propose a brief from ads, with its credit cost (write) |
| `propose_plan` / `run_plan` | Plan several changes, run only after you confirm (write) |

Prompts: Weekly competitor sweep · 3 tests for my brand · Offer scan · What changed at a brand.
Resources: `seercraft://brand-profile`, `seercraft://tracked-brands`.

## Links

[Docs](https://seercraft.io/docs/mcp) · [Privacy](https://seercraft.io/privacy) · [Terms](https://seercraft.io/terms) · [hello@seercraft.io](mailto:hello@seercraft.io)

Seercraft analyses public ad-library data; it doesn't serve, buy or promote ads. This repo holds the directory listing for the hosted server; the server itself is closed source.
