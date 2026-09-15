# PRD v0 — iwealth-better (thin lock)

## Problem
คนถือหุ้น US อยากตัดสินใจ **ซื้อ / ถือ / ขาย** จากพอร์ตตัวเอง โดยเทียบเหตุการณ์อดีตกับกราฟ — ไม่ใช่ chatbot ทายราคาเปล่า

## Goals (v0)
1. **(ก)** Login อีเมล+รหัส · คนหนึ่งมีได้**หลายพอร์ต** · ใส่ตำแหน่ง + **ต้นทุนต่อตัว** (average cost v0)
2. **(ข) จุดขาย** เทียบ historical: กราฟราคา EOD + เหตุการณ์ (แกนแรก = **SEC filings**) ย้อนหลัง **2 ปี**
3. **(ค)** LLM สรุป**บนผลเทียบ** ผ่าน gateway `ai.develyst.online` (เรียกจาก back เท่านั้น)

## Non-goals (v0)
- Google OAuth (later)
- Realtime / intraday แพง
- ตลาดไทย
- Vendor จริงก่อนคนยืนคีย์
- Deploy โดยทีม
- Emoji ใน UI

## Market / data
- US only
- Price: EOD/delayed ในงบ $0–10
- Events v0 core: SEC EDGAR filings (+ stub)
- News / earnings: **interface + stub** · ต่อจริงทีหลัง

## Success (stub round)
- Auth register/login เดินได้ (local)
- CRUD พอร์ต + holdings เดินได้
- หน้า compare โชว์กราฟ+events จาก **stub adapters**
- ปุ่มสรุป LLM เรียก gateway ได้ (หรือ fail ชัดถ้าไม่มีคีย์ env บน back)
