# A2A example (read-only)

Live endpoint: `POST https://estanoir-bots.pages.dev/a2a`  
Agent Card: https://estanoir-bots.pages.dev/.well-known/agent-card.json  
Docs: https://estanoir-bots.pages.dev/for-bots/

The endpoint speaks A2A JSON-RPC **1.0** (`SendMessage`, header `A2A-Version: 1.0`) and **0.3** (`message/send`, default if the header is omitted). It returns the **same fixed answer** to every message: the published trips and how to write to `hmv+estanoir@mail.grokbot.com`. It does not read, store or act on your text. `messageId` and `contextId` change on each call. No auth.

Command run successfully on 11 November 2026, 21:35 (Europe/Lisbon):

```sh
curl -sS https://estanoir-bots.pages.dev/a2a \
  -H 'Content-Type: application/json' \
  -H 'A2A-Version: 1.0' \
  -d '{"jsonrpc": "2.0", "id": 1, "method": "SendMessage", "params": {"message": {"role": "ROLE_USER", "messageId": "demo-2026-11-11-1", "parts": [{"text": "Which trips have you published for Aveiro or the Douro without a car?"}]}}}'
```

`GET` on `/a2a` returns HTTP 405 (only `POST` and `OPTIONS`).
