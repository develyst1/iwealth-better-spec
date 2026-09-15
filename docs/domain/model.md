# Domain model v0

## User
- email (unique), password_hash, created_at
- 1 user → N portfolios

## Portfolio
- id, user_id, name, currency=`USD`, created_at, updated_at
- soft-delete optional later; v0 = hard delete ถ้าไม่มี holdings หรือ cascade ตาม API

## Holding (ตำแหน่งในพอร์ต)
- id, portfolio_id, symbol (US ticker uppercase), quantity (>0), avg_cost (USD per share)
- unique (portfolio_id, symbol)
- v0 cost basis = **average** only (lots = later / OPEN)

## PriceBar (ไม่จำเป็นเก็บถาวรใน DB ถ้าดึงจาก adapter)
- symbol, date, open, high, low, close, volume
- ช่วงที่รองรับใน compare: สูงสุด **2 ปี** ย้อนหลังจาก “วันนี้”

## Event (normalized)
- id (vendor/stub id), symbol, type: `filing` | `news` | `earnings` | `other`
- occurred_at (UTC), title, summary?, url?, source (`stub`|`edgar`|…)
- meta JSON (form type 10-K/8-K, accession, …)

## CompareResult (response shape, ไม่บังคับ persist v0)
- symbol, range: { from, to }
- bars: PriceBar[]
- events: Event[]
- peers?: similar past windows (stub may return empty/fixed)

## SummaryJob (optional persist later)
- v0: request/response ผ่าน API โดยไม่บังคับเก็บ — เก็บ log ภายหลังได้
