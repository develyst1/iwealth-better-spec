# Compare + market + LLM testcases (v0)

Adapters = **stub OK** · ช่วงสูงสุด **2 ปี** · US only · events แกนแรก `filing`

| TC | ประเภท | หัวข้อ |
|----|--------|--------|
| TC-CMP-01 | happy | GET `/market/bars` symbol US ช่วง ≤2y → ได้ `bars[]` (stub) |
| TC-CMP-02 | happy | GET `/market/events` type=filing → ได้ `events[]` (stub; อาจว่างถ้าช่วงไม่มี) |
| TC-CMP-03 | happy | POST `/compare` → `CompareResult` มี bars+events ในช่วง (default 2y ถ้าไม่ส่ง from/to) |
| TC-CMP-04 | happy | POST `/compare/summarize` ด้วย compare จากข้อ 3 → `{ content, ... }` หรือ **503 ชัด** ถ้าไม่มี LLM env |
| TC-CMP-05 | happy | events types รวม `news,earnings` ไม่พัง (stub ว่างได้) |
| TC-CMP-06 | fail | symbol นอก US → 400 |
| TC-CMP-07 | fail | ช่วง >2 ปี → 400 **หรือ** clamp + ระบุใน response (เลือกหนึ่งแล้วคงที่ใน README back) |
| TC-CMP-08 | fail | ไม่ส่ง token → 401 |
| TC-CMP-09 | fail | summarize โดยไม่มี compare / payload ว่าง → 400 |
| TC-CMP-10 | contract | Summarize เรียกจาก **back** ไป gateway เท่านั้น · front ไม่มี API key |

### Stub rules
- ไม่ต้องต่อ Tiingo/EDGAR จริงในรอบนี้
- กราฟต้องเดินได้จาก stub seed
