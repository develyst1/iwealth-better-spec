# CHANGE — Event.occurred_at

- Front FAIL: อ่าน `occurredAt` แต่ API ส่ง `occurred_at` → ComparePage crash
- **LOCKED:** wire field = `occurred_at` (ตาม domain + back)
- Fix: Fero แก้ type/UI ให้ใช้ `occurred_at` แล้ว Tanya แคป compare ใหม่
