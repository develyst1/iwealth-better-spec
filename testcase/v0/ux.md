# UX smoke testcases (v0) — หลังมี front slice

Front: Next.js + TS + Magic UI + Ant Design · ห้าม emoji · เรียก back stub

## Evidence (REQUIRED — กติกา 2026-09-15)
UI smoke **ห้าม PASS เปล่า** · ต้องมี screenshot ใน `/workspace/inbox/` และอ้างพาธใน HANDOFF

ขั้นต่ำ 3 รูป:
1. **login** (หรือหลัง login สำเร็จ)
2. **พอร์ต** (list หรือ detail + holdings)
3. **compare** (กราฟ/events stub)

รายงาน: `inbox/iwealth-front-v0-qa-report.md` (หรือเทียบเท่า) ต้องลิงก์พาธรูป  
**Sober ห้ามรับ PASS UI ถ้าไม่มีหลักฐานรูป**

## Cases

| TC | ประเภท | หัวข้อ |
|----|--------|--------|
| TC-UX-01 | happy | Register / Login หน้าเว็บแล้วเข้าพอร์ตได้ |
| TC-UX-02 | happy | สร้างพอร์ต + เพิ่ม holding เห็นในตาราง |
| TC-UX-03 | happy | หน้า Compare โชว์กราฟ + รายการ events (stub) |
| TC-UX-04 | happy | ปุ่มสรุปด้วย AI ได้ข้อความ หรือ error 503 ชัด |
| TC-UX-05 | fail | ไม่ login เข้าพอร์ต/compare ไม่ได้ |
| TC-UX-06 | UI | Empty state เมื่อยังไม่มีพอร์ต |
| TC-UX-07 | UI | ไม่มีอักขระ emoji ในหน้าหลัก v0 |

### หน้าตาม spec
Login/Register · Portfolio list · Portfolio detail · Compare
