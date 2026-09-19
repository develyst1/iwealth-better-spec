# API sketch v0 (back = Bun+Hono)

Base: `/api/v0` · JSON · Bearer/session ตาม auth.md  
Timestamps: ISO-8601 UTC · Money: number USD · Symbol: uppercase

## Health
- `GET /health` → `{ ok: true }`

## Auth
- `POST /auth/register` `{ email, password }` → `{ user, token }`
- `POST /auth/login` `{ email, password }` → `{ user, token }`
- `POST /auth/logout` → `{ ok: true }`
- `GET /auth/me` → `{ user }`

## Portfolios
- `GET /portfolios` → `{ items: Portfolio[] }`
- `POST /portfolios` `{ name }` → Portfolio
- `GET /portfolios/:id` → Portfolio + holdings
- `PATCH /portfolios/:id` `{ name }` → Portfolio
- `DELETE /portfolios/:id` → `{ ok: true }`

## Holdings
- `PUT /portfolios/:id/holdings` `{ symbol, quantity, avgCost }` upsert
- `DELETE /portfolios/:id/holdings/:symbol` → `{ ok: true }`

## Market / compare (stub adapters OK)
- `GET /market/bars?symbol=&from=&to=` → `{ bars: PriceBar[] }` (max 2y window)
- `GET /market/events?symbol=&from=&to=&types=` → `{ events: Event[] }`  
  `types` default `filing` · อนุญาต `filing,news,earnings`
- `POST /compare` `{ symbol, from?, to?, eventTypes? }` → `CompareResult`  
  Default range = last 2 years if omitted

## LLM summarize (ค)
- `POST /compare/summarize` `{ compare: CompareResult, question?: string }`  
  → `{ content, provider?, model?, latency_ms? }`  
  Back เรียก `POST https://ai.develyst.online/chat` ด้วย messages ที่ประกอบจาก compare เท่านั้น  
  ห้ามฝัง API key ใน front · ถ้า env ขาด → 503 ชัดเจน

## Errors
`{ error: string, code?: string }` · 400/401/403/404/409/503

## Out of v0
- Real vendor proxy beyond stub · OAuth · streaming WS

## JSON field names (LOCKED 2026-09-19)

Wire JSON matches back stub shapes:

- Portfolio / Holding / User: **camelCase** (`createdAt`, `avgCost`, `userId`, …)
- Event (compare/market): **`occurred_at`** (snake_case) — ห้าม `occurredAt` บน wire
- LLM summarize usage: `latency_ms` ตาม gateway

Front ต้องอ่าน `occurred_at` จาก API (อย่า map ผิดแล้ว `.slice` บน undefined)

