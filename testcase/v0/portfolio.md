# Portfolio + holdings testcases (v0)

ต้อง auth · cost-basis = **average cost** · symbol uppercase US

| TC | ประเภท | หัวข้อ |
|----|--------|--------|
| TC-PF-01 | happy | สร้างพอร์ต A, B → list มี ≥2 |
| TC-PF-02 | happy | PATCH เปลี่ยนชื่อพอร์ต |
| TC-PF-03 | happy | ใน A ใส่ AAPL qty/avgCost → detail เห็น holding |
| TC-PF-04 | happy | Upsert AAPL เปลี่ยน qty/avgCost → อัปเดต |
| TC-PF-05 | happy | ลบ holding ตาม symbol |
| TC-PF-06 | happy | ลบพอร์ตว่างได้ |
| TC-PF-07 | fail | สร้างพอร์ตชื่อว่าง → 400 |
| TC-PF-08 | fail | holding symbol ว่าง → 400 |
| TC-PF-09 | fail | qty ≤ 0 → 400 |
| TC-PF-10 | fail | avgCost < 0 → 400 |
| TC-PF-11 | fail | เข้า/แก้พอร์ตคนอื่น → 403 หรือ 404 (คงที่หนึ่งแบบ) |
| TC-PF-12 | fail | ไม่มี token → 401 |

### หมายเหตุ
- หลายพอร์ตต่อ user ได้
- ไม่มีตลาดไทย / symbol นอก US ถ้าโดเมนล็อก US ให้ reject ชัด
