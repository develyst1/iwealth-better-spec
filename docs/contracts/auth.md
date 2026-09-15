# Auth v0 — email + password

## Rules
- Register: email + password (min 8)
- Login: email + password → session token (JWT หรือ opaque session — back เลือก ระบุใน README back)
- Logout: invalidate session / client drop token
- All portfolio/compare/summary routes require auth
- Google OAuth = **out of v0**

## Password
- Hash ด้วยอัลกอริทึมมาตรฐาน (เช่น argon2/bcrypt) · ห้ามเก็บ plain

## Errors
- 401 unauthorized
- 409 email already registered
- 400 validation
