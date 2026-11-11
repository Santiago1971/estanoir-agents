# MCP examples (read-only)

Live endpoint: `https://estanoir-bots.pages.dev/mcp`  
Docs: https://estanoir-bots.pages.dev/mcp-server/  
These commands were run successfully on 11 November 2026, 21:35 (Europe/Lisbon). They store nothing and send nothing.

Client hint:

```json
{
  "mcpServers": {
    "esta-no-ir": { "type": "http", "url": "https://estanoir-bots.pages.dev/mcp" }
  }
}
```

## search_trips

Optional arguments: `country` (ISO 3166-1 alpha-2), `origin_contains`, `max_days` (1–3), `no_car`, `no_flight`.

```sh
curl -sS https://estanoir-bots.pages.dev/mcp \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -H 'MCP-Protocol-Version: 2025-06-18' \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "tools/call", "params": {"name": "search_trips", "arguments": {"country": "PT", "no_car": true, "max_days": 2}}}'
```

Run the command to see the live response. On 11 November 2026 it returned HTTP 200 and a `count` of matching trips.

## get_trip

Argument: `id` (from `search_trips` or https://estanoir-bots.pages.dev/trips.json).

```sh
curl -sS https://estanoir-bots.pages.dev/mcp \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -H 'MCP-Protocol-Version: 2025-06-18' \
  -d '{"jsonrpc": "2.0", "id": 2, "method": "tools/call", "params": {"name": "get_trip", "arguments": {"id": "porto-douro-train-2-days"}}}'
```

## how_to_request

No arguments. Returns the email address and a plain-text template. **It does not send mail.**

```sh
curl -sS https://estanoir-bots.pages.dev/mcp \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -H 'MCP-Protocol-Version: 2025-06-18' \
  -d '{"jsonrpc": "2.0", "id": 3, "method": "tools/call", "params": {"name": "how_to_request", "arguments": {}}}'
```
