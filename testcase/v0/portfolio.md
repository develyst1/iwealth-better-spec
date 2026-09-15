# Portfolio + holdings

## Happy
1. สร้างพอร์ต A, B → list มี 2
2. ใน A ใส่ AAPL qty/avgCost → เห็นใน detail
3. Upsert AAPL เปลี่ยน qty → อัปเดต
4. ลบ holding · ลบพอร์ตว่างได้

## Fail
5. symbol ว่าง / qty ≤0 → 400
6. เข้าพอร์ตคนอื่น → 403/404
