# StudyBalance

เว็บจัดตารางเรียนสมดุล: วิชาที่เลื่อนไม่ได้, เวลาพัก, คะแนน Work-Life, เช็กอินความรู้สึก และแผนเตรียมสอบ

## ขึ้นเว็บด้วย GitHub Pages

1. สร้าง repository ใหม่ (เช่น `studybalance`)
2. อัปโหลด `index.html` และ `README.md` ไปที่ root ของ repo
3. ไปที่ **Settings → Pages**
4. เลือก **Deploy from a branch** → Branch `main` → Folder `/ (root)` → Save
5. รอ 1–2 นาที เว็บจะอยู่ที่ `https://<ชื่อผู้ใช้>.github.io/studybalance/`

## การทำงาน

- ข้อมูลทั้งหมดเก็บใน `localStorage` ของเบราว์เซอร์ ไม่ส่งไปที่ใด
- จัดตาราง คำนวณคะแนน และแผนสอบ ทำงานได้เองโดยไม่ต้องใช้ AI
- ปุ่ม "ให้ AI…" ใช้ Anthropic API key ที่ผู้ใช้ใส่เองในแท็บตั้งค่า

## ถ้าจะเปิดให้คนทั่วไปใช้ AI

ห้ามฝัง API key ในโค้ด ให้สร้างตัวกลางฝั่งเซิร์ฟเวอร์ (Cloudflare Workers / Vercel / Netlify Functions)
เก็บ key ไว้ในนั้น แล้วแก้ฟังก์ชัน `askAI` ใน `index.html` ให้เรียก URL ของตัวกลางแทน `api.anthropic.com`

## หมายเหตุ

ส่วนเช็กอินเป็นการสำรวจความรู้สึกประจำวัน ไม่ใช่การวินิจฉัยทางการแพทย์
