# Auth testcases (v0)

API: `/api/v0/auth/*` · รหัส ≥8 · hash มาตรฐาน · ห้าม plain

| TC | ประเภท | หัวข้อ |
|----|--------|--------|
| TC-AUTH-01 | happy | Register อีเมลใหม่ + รหัส ≥8 → ได้ `user` + `token` |
| TC-AUTH-02 | happy | Login ด้วยชุดเดิม → ได้ token |
| TC-AUTH-03 | happy | GET `/auth/me` ด้วย Bearer → เห็น user |
| TC-AUTH-04 | happy | Logout → token ใช้ต่อไม่ได้ (หรือ client drop + 401) |
| TC-AUTH-05 | fail | Register อีเมลซ้ำ → 409 |
| TC-AUTH-06 | fail | Register รหัสสั้นกว่า 8 → 400 |
| TC-AUTH-07 | fail | Register อีเมลไม่ถูกต้อง → 400 |
| TC-AUTH-08 | fail | Login รหัสผิด → 401 |
| TC-AUTH-09 | fail | Login อีเมลไม่มี → 401 |
| TC-AUTH-10 | fail | GET `/auth/me` ไม่มี token → 401 |
| TC-AUTH-11 | fail | GET `/portfolios` ไม่มี token → 401 |

### หมายเหตุ
- ไม่มี Google OAuth ใน v0
