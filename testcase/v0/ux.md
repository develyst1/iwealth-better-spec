# UX smoke (front)

Front: Next.js + TS + Magic UI + Ant Design · ห้าม emoji · เรียก back stub

## Evidence (REQUIRED — กติกา 2026-09-15)
UI smoke **ห้าม PASS เปล่า** · ต้องมี screenshot ใน `/workspace/inbox/` และอ้างพาธใน HANDOFF

ขั้นต่ำ 3 รูป:
1. **login** (หรือ register สำเร็จแล้วอยู่หน้าพอร์ต/login สำเร็จ)
2. **พอร์ต** (list หรือ detail + holdings)
3. **compare** (กราฟ/events stub + UI สรุป AI ถ้ามี)

รายงาน: `inbox/iwealth-front-v0-qa-report.md` (หรือเทียบเท่า) ต้องลิงก์พาธรูป

## Happy
1. Login/register เดินได้
2. สร้างพอร์ต + ใส่ holding เห็นบน UI
3. เปิด compare เห็น bars/events จาก stub

## Fail / notes
4. ไม่มี token → เด้ง login
5. LLM 503 โชว์ error ชัด (ไม่ต้องแคปบังคับถ้ายังไม่กดสรุป)
