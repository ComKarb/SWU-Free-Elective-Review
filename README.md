# SWU Free Elective Review (ระบบรีวิววิชาเลือกเสรี มศว)

เว็บแอปพลิเคชันสำหรับนิสิต มหาวิทยาลัยศรีนครินทรวิโรฒ (มศว) ในการแบ่งปันและค้นหารีวิวรายวิชาเลือกเสรีและศึกษาทั่วไป พร้อมระบบเชื่อมต่อคลาวด์ Google Sheets แบบสองทิศทาง (Real-time Cloud Sync) มาพร้อมความเสถียร รองรับ Concurrency สูง และระบบสถิติ Google Analytics 4

---

## ✨ ไฮไลต์ฟีเจอร์เด่น (Key Features)

1. **คลังรายวิชาเสรี มศว ฉบับสมบูรณ์ (Master Course Catalog):**
   - รวบรวมรายวิชาจริงครบทั้ง **23 คณะ/ส่วนงาน รวม 253 รายวิชา**
   - แสดงผลแบบสองภาษา: ชื่อคณะไทย (อังกฤษ) เช่น *คณะวิทยาศาสตร์ (Faculty of Science)*
   - รองรับทั้งรหัสภาษาไทย (เช่น `สสน01`, `สวน03`, `สวศ08`) และรหัสภาษาอังกฤษ (เช่น `ZIL01`, `ZCO03`, `ZEG08`)
2. **ระบบค้นหาและตัวกรองแบบเรียลไทม์ (Live Search & Filter):**
   - ค้นหาได้รวดเร็วทันใจ: ค้นหาด้วยรหัสวิชา, ชื่อวิชา, ชื่อคณะ, หรือคีย์เวิร์ดในเนื้อหารีวิว
   - กรองตามคณะแบบไดนามิก พร้อมแสดงจำนวนวิชาที่เปิดในแต่ละคณะ
3. **ระบบการให้คะแนน 5 มิติ (5-Dimension Ratings):**
   - 🎯 **ความเข้าใจเนื้อหา** (Content Clarity)
   - ⚖️ **ความเหมาะสมของภาระงาน** (Workload Appropriateness)
   - 📝 **ความง่ายของข้อสอบ** (Exam Ease)
   - ❤️ **ความใจดี/เข้าถึงง่ายของผู้สอน** (Instructor Kindness)
   - 🌟 **ความง่ายในการตัดเกรด/เก็บ A** (Grading Ease)
4. **รายละเอียดการเรียนที่ครบถ้วน:**
   - จำนวนหน่วยกิต (4 หรือ 6 หน่วยกิต)
   - รูปแบบการเรียน (Online, Onsite, Hybrid)
   - ตัวเลือกระบุช่วงเวลาเรียน (Time Picker) พร้อมจัดรูปแบบมาตรฐานอัตโนมัติ
   - ข้อมูลการเช็คชื่อเข้าชั้นเรียน
5. **ความเสถียรและความปลอดภัยของข้อมูลระดับ Production (Production Ready):**
   - **Concurrency Lock (LockService):** ระบบคิวล็อกบน Google Apps Script สูงสุด 30 วินาที ป้องกันข้อมูลชนกันหรือเขียนทับกันเวลาคนส่งรีวิวพร้อมกัน
   - **Double-submit Guard:** ปิดการกดปุ่มส่งซ้ำทันที พร้อมแสดงสถานะโหลดหมุนติ้ว ป้องกันการส่งสแปม
   - **Offline & Retry Queue:** ระบบคิวสำรองในตัวเครื่อง (`swu_pending_reviews_v2`) หากเน็ตหลุดหรือเซิร์ฟเวอร์ติดคิว ระบบจะเก็บไว้ส่งซ้ำอัตโนมัติเมื่อออนไลน์
   - **Smart Cloud Merge:** รวมข้อมูลในเครื่องและคลาวด์เข้าด้วยกัน รีวิวใหม่ไม่สูญหายระหว่างรอชีตบันทึก
6. **ระบบวัดสถิติผู้เข้าชมเว็บ (Web Analytics):**
   - ติดตั้ง **Google Analytics 4 (GA4)** ตรวจสอบจำนวนผู้เข้าชมแบบ Real-time และติดตาม Event การส่งรีวิว (`submit_review`)
7. **ดีไซน์สะอาดตา สไตล์ Modern Apple x SWU:**
   - คุมโทนสีเอกลักษณ์ แดง-เทา-ดำ (`#DA2128`, `#636466`, `#231F20`)
   - ใช้องค์ประกอบไอคอนแบบ SVG คมชัดระดับ Vector สะอาดตา ไม่ใช้อิโมจิ เพื่อความเป็นมืออาชีพ

---

## 🎨 ระบบสีและธีม (Design & Color System)

- **SWU Red (`#DA2128`):** สีแดงหลัก มศว สำหรับปุ่ม CTA, หัวข้อ, และจุดไฮไลต์คะแนน
- **SWU Grey (`#636466` / `#4B4C4E`):** สีเทาสำหรับตัวหนังสือรอง ข้อความคำอธิบาย และเส้นขอบ
- **Background (`#F7F7F8`):** สีพื้นหลังโทนสะอาด สบายตา อ่านง่ายและมีความเปรียบต่างสูง (High Contrast)
- **Card Background (`#FFFFFF`):** สีขาวบริสุทธิ์พร้อมเงาละมุน (Soft Shadow) แยกมิติการ์ดชัดเจน

---

## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```
SWU-Free-Elective-Review/
│
├── index.html                  # หน้าหลัก (Hero, ตัวนับสถิติ, ค้นหา & ตัวกรองคณะ, การ์ดรีวิว)
├── review.html                 # หน้าฟอร์มส่งรีวิว (เลือกคณะ/วิชา, เกณฑ์ 5 มิติ, เวลาเรียน)
├── GoogleAppsScript_Code.gs    # Backend Apps Script (LockService, doGet, doPost, Sheet Integration)
├── README.md                   # เอกสารประกอบการพัฒนาและการใช้งาน
│
├── css/
│   └── style.css               # สไตล์ชีตหลัก (CSS Variables, Responsive, Clean Apple Theme)
│
├── js/
│   ├── courses.js              # ฐานข้อมูลรายวิชาเลือกเสรี มศว (23 คณะ 253 รายวิชา)
│   ├── storage.js              # Data Layer (Google Sheets Sync, Retry Queue, localStorage v2)
│   ├── home.js                 # ควบคุมหน้าหลัก (Live Search, Filter, Render การ์ดรีวิว)
│   └── review.js               # ควบคุมหน้าฟอร์ม (Form Validation, Dynamic Course Select, Double-submit Guard)
│
└── assets/
    └── README.txt              # โฟลเดอร์สำหรับเก็บภาพหรือไอคอนเพิ่มเติม
```

---

## 🚀 วิธีรันโปรเจกต์บนเครื่อง (Local Development)

โปรเจกต์นี้พัฒนาด้วย **HTML5 + Vanilla CSS3 + Vanilla JavaScript** สามารถเปิดทดสอบได้ทันที:

### วิธีที่ 1 — VS Code Live Server (แนะนำ)
1. เปิดโฟลเดอร์โปรเจกต์ใน Visual Studio Code
2. คลิกขวาที่ `index.html` → เลือก **"Open with Live Server"**

### วิธีที่ 2 — รันผ่าน Python
```bash
python -m http.server 8000
```
เปิดเบราว์เซอร์ไปที่: `http://localhost:8000`

---

## ☁️ การเชื่อมต่อ Google Sheets & Google Apps Script

โปรเจกต์นี้ใช้ Google Sheets เป็นฐานข้อมูลหลักผ่าน Web App URL:

1. นำโค้ดจาก [GoogleAppsScript_Code.gs](GoogleAppsScript_Code.gs) ไปใส่ใน Apps Script ของ Google Sheet
2. กด **Deploy (การทำให้ใช้งานได้)** → **Manage deployments** หรือ **New deployment**
   - *Execute as:* **Me (ฉัน)**
   - *Who has access:* **Anyone (ทุกคน)** *(สำคัญมาก)*
3. นำ URL เว็บแอป (`https://script.google.com/macros/s/.../exec`) มาใส่ใน `js/storage.js` ตรง:
   ```javascript
   const GOOGLE_SCRIPT_URL = "YOUR_WEB_APP_URL";
   ```

---

## 📊 การติดตามสถิติด้วย Google Analytics (GA4)

โปรเจกต์ติดตั้ง GA4 Measurement ID (`G-TJ08TLX7KQ`) ไว้ใน `<head>` ของทั้ง `index.html` และ `review.html`:
- ตรวจสอบยอดผู้เข้าชมแบบสด ๆ ผ่านแท็บ **Realtime** บน [Google Analytics](https://analytics.google.com/)
- มี Custom Event `submit_review` บันทึกทุกครั้งที่มีนิสิตส่งรีวิวสำเร็จ

---

## 🤝 การมีส่วนร่วมพัฒนา (Contributing)

ยินดีต้อนรับนิสิตและผู้สนใจทุกคนที่ต้องการช่วยปรับปรุง:
- เพิ่ม/แก้ไขรายวิชาเลือกเสรีใหม่ ๆ ใน `js/courses.js`
- ปรับปรุงการออกแบบ UI/UX หรือรายงานข้อผิดพลาดผ่าน GitHub Issues / Pull Requests
