# Market + event adapters (v0)

## Principle
Back คุยกับ **interface** เท่านั้น · implementation แรก = **Stub**  
Vendor จริงต้องคนยืน + ส่งคีย์แบบปลอดภัย · ห้าม commit secrets

## MarketDataPort
```ts
getBars(symbol: string, from: string /*YYYY-MM-DD*/, to: string): Promise<PriceBar[]>
```
- US symbols only · reject others
- Clamp range to ≤ 2 years
- Stub: สังเคราะห์ EOD จาก seed(symbol) ให้กราฟเดินได้

## EventPort
```ts
getEvents(symbol: string, from: string, to: string, types: EventType[]): Promise<Event[]>
```
- v0 **primary type**: `filing` (SEC EDGAR shape ใน meta)
- `news` / `earnings`: stub ว่างหรือตัวอย่างน้อย ๆ ได้
- Future: EdgarEventPort (free) · NewsEventPort (TBD vendor)

## Recommended path (not locked)
| Need | Candidate | Note |
|------|-----------|------|
| EOD price | Tiingo / Twelve Data / Polygon free tier | งบ $0–10 |
| Filings | SEC EDGAR | free · User-Agent required |
| News | later | มักเกินงบถ้าย้อน 2 ปีครบ |

ดูรายละเอียดสำรวจ: inbox `iwealth-v0-explore.md` · `docs/vendors.md`
