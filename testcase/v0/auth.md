# Auth

## Happy
1. Register อีเมลใหม่ + รหัส ≥8 → ได้ token
2. Login ด้วยชุดเดิม → ได้ token
3. GET /auth/me ด้วย token → เห็น user

## Fail
4. Register อีเมลซ้ำ → 409
5. Login รหัสผิด → 401
6. GET พอร์ตโดยไม่มี token → 401
