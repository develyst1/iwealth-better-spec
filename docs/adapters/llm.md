# LLM adapter (ค)

## Gateway
- Base: `https://ai.develyst.online`
- Used by **back only**
- Endpoints: `GET /`, `GET /models`, `POST /chat`, `POST /chat/multi`
- Bruno samples: `/workspace/inbox/iwealth-llm-gateway/` (reference; copy notes into back README if useful)

## Summarize contract
Input: CompareResult (+ optional user question)  
Prompt rules:
- สรุปเฉพาะหลักฐานใน bars/events ที่ส่งมา
- ห้ามทายราคาอนาคตเด็ดขาด / ห้ามแนะนำการลงทุนแบบ unconditional
- ภาษา: ตาม question หรือ default ไทย

Output to client: `{ content, provider?, model?, latency_ms? }` จาก gateway `data`

## Env (back)
- e.g. `LLM_GATEWAY_URL=https://ai.develyst.online`
- Auth header ถ้า gateway ต้องการ — **ใส่บนเซิร์ฟเท่านั้น** · ไม่ commit
