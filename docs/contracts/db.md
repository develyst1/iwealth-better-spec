# DB sketch v0 — PostgreSQL

## Tables
### users
- id uuid PK
- email citext unique not null
- password_hash text not null
- created_at timestamptz default now()

### sessions (ถ้า opaque; ข้ามได้ถ้า JWT-only)
- id uuid PK
- user_id FK
- token_hash text unique
- expires_at timestamptz
- created_at timestamptz

### portfolios
- id uuid PK
- user_id FK
- name text not null
- currency text not null default 'USD'
- created_at / updated_at timestamptz

### holdings
- id uuid PK
- portfolio_id FK
- symbol text not null
- quantity numeric(18,6) not null check (quantity > 0)
- avg_cost numeric(18,6) not null check (avg_cost >= 0)
- unique (portfolio_id, symbol)

## Notes
- ไม่บังคับเก็บ bars/events ใน DB รอบ stub (ดึงจาก adapter)
- Migration tool: back เลือก (drizzle/prisma/sql) แล้วระบุใน README
