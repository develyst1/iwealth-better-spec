# UX screens v0 (thin)

Front: Next.js + TS + **shadcn/ui + Magic UI** · ห้าม emoji · ห้าม Mantine

1. **Login / Register** — อีเมล+รหัส
2. **Portfolio list** — สร้าง/เปลี่ยนชื่อ/ลบ · เข้าพอร์ต
3. **Portfolio detail** — ตาราง holdings (symbol, qty, avg cost) · เพิ่ม/แก้/ลบ
4. **Compare** — เลือก symbol (จาก holding หรือพิมพ์) · กราฟ EOD stub · รายการ events (filings) · ปุ่ม **สรุปด้วย AI**
5. Empty/error states ชัด (ไม่มีพอร์ต · adapter fail · LLM 503)

## Notes
- Mobile-first พอใช้ได้
- ใช้คอมโพเนนต์ shadcn เป็นฐาน · Magic UI สำหรับ motion/accent ที่เข้าชุด
- ไม่ทำ design system เต็มในรอบ stub
