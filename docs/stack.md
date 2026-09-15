# Stack + repos (LOCKED)

## Repos
- `develyst1/iwealth-better-spec`
- `develyst1/iwealth-better-front`
- `develyst1/iwealth-better-back`

## Runtime
| Layer | Choice |
|-------|--------|
| Front | **Next.js + TypeScript** · UI: **Mantine v7** (+ Tabler icons) — เข้ากับทิศ antd/Magic UI ได้; เปลี่ยน lib ต้องอัปเดต spec |
| Back | **Bun + Hono + TypeScript** |
| DB | **PostgreSQL** (สมมติจนกว่าคนทัก) |
| Market | US equities only · **EOD/delayed** · งบ **$0–10/mo** |
| LLM | Back → `https://ai.develyst.online` only |

## Branch (ทุก repo)
- `main` = showcase
- `production` = human deploy only
- `develop` = integration
- Person branches: `Sober`, `Jason`, `Fero`, `Tanya`
- Flow: merge `develop` → person → work → merge person → `develop`
- ทีม**ห้าม deploy** · ห้าม commit secrets
