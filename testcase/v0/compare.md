# Compare + summarize

## Happy
1. GET bars symbol US ในช่วง ≤2y → ได้แท่ง (stub OK)
2. GET events type=filing → ได้รายการ (stub OK)
3. POST /compare → bars+events ในช่วง
4. POST /compare/summarize ด้วย compare จากข้อ 3 → ได้ content หรือ 503 ชัดถ้าไม่มี LLM env

## Fail
5. symbol นอก US / ช่วง >2y → 400 (หรือ clamp+ระบุใน response — เลือกหนึ่งแล้วคงที่)
6. ไม่ส่ง token → 401
