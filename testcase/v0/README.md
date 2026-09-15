# Testcases v0 — iwealth-better

แหล่ง: `docs/product/prd-v0.md` + `docs/contracts/*` + adapters  
รันกับ **stub adapters** · ไม่ต้องมี vendor จริง · ห้าม deploy

| ไฟล์ | โฟกัส |
|------|--------|
| [auth.md](./auth.md) | register / login / me / logout |
| [portfolio.md](./portfolio.md) | multi-portfolio + holdings + isolation |
| [compare.md](./compare.md) | bars / events / compare / LLM summarize |
| [ux.md](./ux.md) | หน้า login · พอร์ต · compare (หลังมี front slice) |

## DoD รอบ stub
- [x] เคส happy/fail หลักครบในไฟล์ด้านบน
- [ ] Jason back stub ผ่านเคส API
- [ ] Fero front stub ผ่านเคส UX
- [ ] Tanya รันจริงหลังมี slice แล้วอัปผล
