# NorthSpace NewsRoom

ฟีดข่าวเชียงใหม่ · ภาคเหนือ — คัดกรองและเรียบเรียงโดย AI

หน้าเว็บแบบ card feed ธีมสว่าง โมเดิร์น (heading = Kanit, body = Noto Sans Thai)
แสดงข่าวและกิจกรรม/อีเวนต์ในพื้นที่ภาคเหนือแบบ overview เห็นทั้งหมดในตาเดียว

## โครงสร้าง

- `index.html` — หน้าเว็บ (static, อ่านข้อมูลจาก `data.json`)
- `data.json` — ข้อมูลฟีด (อัปเดตอัตโนมัติทุกวัน)

## data.json schema

```json
{
  "meta": { "title": "...", "tagline": "...", "updated": "...", "focus": "..." },
  "items": [
    {
      "urgency": "breaking | normal | event",
      "category": "หมวดข่าว",
      "provinces": ["เชียงใหม่", "..."],
      "headline": "พาดหัว",
      "summary": "สรุปย่อ (สำนวนเรียบเรียง อ้างอิงแหล่งข่าวจริงเสมอ)",
      "date": "วันที่",
      "sources": [{ "name": "แหล่งข่าว", "url": "https://..." }]
    }
  ]
}
```

## การอัปเดต

ฟีดอ่านจาก `data.json` — แก้ไฟล์นี้แล้ว push ขึ้น GitHub จะ deploy อัตโนมัติผ่าน Vercel
