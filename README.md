# Está no Ir — agents

Open, read-only data and call examples for [Está no Ir](https://estanoir.grok.me/), a Portuguese notebook of short trips (1–3 days) in Portugal and nearby Europe, by train, coach, boat, plane or on foot.

Schemas, examples and pointers to the live data, first assembled on 11 November 2026 (Europe/Lisbon).

## What this is

- A **travel notebook**, not a travel agency: no bookings, no invented prices, no payments.
- Two sites:
  - People: https://estanoir.grok.me/
  - Agents: https://estanoir-bots.pages.dev/
- Two kinds of trip:
  - **vivido / first-hand** — a trip someone took and told (`type: first_hand`).
  - **pesquisado / researched** — a plan built from dated official sources, not a trip we took (`type: researched_plan`).
- Machine interfaces (no account, no API key, read-only):
  - Catalogue: https://estanoir-bots.pages.dev/trips.json
  - MCP server: `POST https://estanoir-bots.pages.dev/mcp` — tools `search_trips`, `get_trip`, `how_to_request` (the last one sends nothing)
  - A2A JSON-RPC: `POST https://estanoir-bots.pages.dev/a2a` — fixed reply; it does not read or store your message
  - Agent Card: https://estanoir-bots.pages.dev/.well-known/agent-card.json
  - Docs: https://estanoir-bots.pages.dev/mcp-server/ · https://estanoir-bots.pages.dev/for-bots/

New trip ideas, a second look at a plan, or a plan B, go by plain-text email to `hmv+estanoir@mail.grokbot.com`, and only with a person’s OK. Replies are human-reviewed.

## Repository layout

```
README.md                 this file
LICENSE                   CC BY 4.0 for the data
schema/trips.schema.json  JSON Schema for the live trips catalogue
schema/destination.schema.json  JSON Schema for destination-level records
examples/mcp.md           curl examples for the three MCP tools
examples/a2a.md           curl example for A2A SendMessage (v1.0)
data/README.md            where to fetch the live data (we do not snapshot all 19 trips here)
```

## Licence

Trip data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit «Está no Ir» with a link to https://estanoir.grok.me/. Official documents we cite remain under their own terms; we only link to them.

## Status

19 trips are already published on the agents site (1 first-hand, 18 researched). A 11 November 2026 working draft raises five destination-level itineraries to the same quality grid (dated official sources, researched/lived label, no-car / children / reduced-mobility / plan B). Those files will be added here once they are published on the sites.

If you repeat the MCP or A2A calls, keep the researched vs first-hand label and the source dates when you cite a plan.
