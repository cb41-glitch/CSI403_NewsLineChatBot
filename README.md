# 📰 NewsArticleBot
### LINE Bot สำหรับสรุปบทความข่าว

> LINE Bot ที่ใช้ **Gemini AI** เพื่อสรุปบทความข่าว และบันทึกผลลัพธ์ลงใน **Google Sheets**

---

## ✨ ฟีเจอร์

| ฟีเจอร์ | รายละเอียด |
|---------|-----------|
| 💬 ประมวลผลข้อความ | รับข้อความและสรุปด้วย Gemini AI |
| 🖼️ ประมวลผลรูปภาพ | ดึงข้อความจากรูปภาพและสรุปเนื้อหา |
| 😊 รองรับ Emoji | ใช้ Emoji เพื่อการนำเสนอที่สวยงาม |
| 🛡️ จัดการข้อผิดพลาด | รองรับข้อผิดพลาดพร้อมข้อความแจ้งเตือนที่เข้าใจง่าย |

---

## 📋 เครื่องมือเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่ามีสิ่งต่อไปนี้:

1. 🔧 **บัญชี Make.com** Workflow — [สร้างที่นี่](https://www.make.com/en)
2. 💬 **บัญชี LINE Developers** สำหรับ Chatbot — [สร้างที่นี่](https://developers.line.biz)
3. 🤖 **Gemini API Key** — [รับจาก Google AI Studio](https://aistudio.google.com)
4. 📊 **Google Spreadsheet** สำหรับเก็บข้อมูล — [สร้างที่นี่](https://docs.google.com/spreadsheets/create)

---

## 🚀 การติดตั้งและตั้งค่า

### ขั้นตอนที่ 1 — สมัคร Make.com

ไปที่ [make.com](https://www.make.com/en) กดที่ **Get started free** และกรอกข้อมูลในการสมัคร

---

### ขั้นตอนที่ 2 — สร้าง Scenario

กดที่ปุ่ม **Create Scenario**

---

### ขั้นตอนที่ 3 — Import Workflow.json ของโปรเจค

ดาวน์โหลด workflow ของพวกเราได้ที่นี่ 👉 [Google Drive](https://drive.google.com/file/d/1DfflM4WvMgfjE_kRoxS-a7OeYORfoEDS/view?usp=sharing)

กดที่จุด 3 จุด **`...`** และกด **Import Blue Print**

---

### ขั้นตอนที่ 4 — สร้าง Chatbot ใน LINE Developers

1. ไปที่ [LINE Developers Console](https://developers.line.biz) แล้ว Login ด้วยบัญชี LINE
2. ไปที่หัวข้อ **Provider** แล้วกด **Create** ตั้งชื่อว่า `"News Bot"`
3. กดเข้า Provider ที่สร้าง แล้วกด **Create a Messaging API Channel**
4. กด **Create a Line Official Account** แล้วกรอกข้อมูลดังนี้:

```
ชื่อบัญชี          : News Chat Bot
อีเมล              : *อีเมลล์ของท่าน*
ประเทศที่ตั้งบริษัท  : ไทย
ชื่อบริษัท/ธุรกิจ   : News Fast Mak
ประเภทธุรกิจ       : "ผู้เชี่ยวชาญ" / "ผู้ประกาศข่าว"
```

5. กด **ตกลง** และยืนยันข้อมูล จากนั้นจะเข้าสู่หน้า LINE Official Account Dashboard
6. ไปที่ **ตั้งค่า** (มุมขวาบน) → **ตั้งค่าการตอบกลับ**
7. ตั้งค่า **ฟีเจอร์การตอบข้อความ** ดังนี้:

```
แชท                       : ❌
ข้อความทักทายเพื่อนใหม่    : ❌
Webhook                   : ✅
ข้อความตอบกลับอัตโนมัติ   : ❌
```

8. ไปที่หน้า **Messaging API** → กด **ใช้ Messaging API** → เลือก Provider `News Bot` → กด **ยอมรับ**
9. กลับไปที่ LINE Developers → เลือก **News Bot** → **Channels** → **News Chat Bot**
10. ไปที่แท็บ **Messaging API** เลื่อนลงหา **Channel access token** แล้วกด **Issue**

> 📌 เก็บ **Channel Access Token** นี้ไว้ใช้ในขั้นตอนถัดไป

---

### ขั้นตอนที่ 5 — รับ API Key จาก Google AI Studio

1. ไปที่ [Google AI Studio](https://aistudio.google.com) แล้ว Login ด้วยบัญชี Google
2. กดที่ **API keys**
3. กดที่ **ตัวหนังสือฟ้า (รหัส API Key)** ตรง Column Key

> 📌 Copy **API Key** และเก็บไว้ใช้ในขั้นตอนถัดไป

---

### ขั้นตอนที่ 6 — สร้าง Google Sheet สำหรับเก็บข้อมูล

1. ไปที่ [Google Sheets](https://docs.google.com/spreadsheets/create)
2. ตั้งชื่อ Spreadsheet ว่า **`Chat History`**
3. ตั้งชื่อหัวคอลัมน์ในแถวแรก (A, B, C):

| A | B | C |
|---|---|---|
| `Topic` | `Content` | `Summary` |

4. กด **แชร์** (มุมขวาบน) → ไปที่ **General Access** → เปลี่ยนเป็น **Anyone with the link**

---

### ขั้นตอนที่ 7 — ตั้งค่า LINE Node ใน Make.com

1. กลับไปที่ Scenario ที่สร้างไว้
2. คลิกที่ **Animation นาฬิกา** (มุมซ้ายล่างของ Node) → เปลี่ยน Run Scenario จาก `At regular intervals` เป็น **`Immediately`** แล้วกด Save
3. คลิกที่ LINE Node อันแรก → กด **Add** เพื่อสร้าง Webhook
4. ตั้งชื่อ Webhook ว่า **`Line Webhook`**
5. ไปที่ส่วน Connection → กด **Add** → ตั้งชื่อว่า **`News bot Message API`**
6. วาง **Channel Access Token** จากขั้นตอนที่ 4 → กด Save 2 ครั้ง
7. สำหรับ LINE Node อื่น ๆ ให้เลือก Connection **`News bot Message API`** แล้วกด Save

---

### ขั้นตอนที่ 8 — ตั้งค่า Google Gemini AI Node ใน Make.com

1. คลิกที่ Google Gemini AI Node ใดก็ได้ → ไปที่ส่วน Connection → กด **Add**
2. ตั้งชื่อว่า **`Google API Key`** → วาง API Key จากขั้นตอนที่ 5 → กด Save
3. ไปที่ส่วน **AI Model** → เปลี่ยนเป็น **`Gemini Flash Latest`** → กด Save
4. ทำซ้ำกับทุก Gemini Node โดยเลือก Connection **`Google API Key`** และ Model **`Gemini Flash Latest`**

---

### ขั้นตอนที่ 9 — ตั้งค่า Google Sheets Node ใน Make.com

1. คลิกที่ Google Sheets Node ใดก็ได้ → ไปที่ส่วน Connection → กด **Add**
2. ตั้งชื่อว่า **`My Google connection`** → กด **Sign in with Google**
3. เลือกบัญชีที่สร้าง Google Sheets ไว้ → กด **ดำเนินการต่อ** → **เลือกทั้งหมด** → **ดำเนินการต่อ**
4. ไปที่ **Spreadsheet Name** → เลือก **`Chat History`**
5. ไปที่ **Sheet Name** → เลือก **`Sheet1`** → กด Save

---

### ขั้นตอนที่ 10 — ตั้งค่า Route ที่ 2 ใน Make.com

> ⚠️ เนื่องจาก Filter ของ Route ที่ 2 อาจหายไปหลัง Import ให้ตั้งค่าใหม่ดังนี้

1. คลิกที่เส้นระหว่าง **Router** กับ **LINE Node** ของ Route ที่ 2 (ชื่อ `2nd`)
2. ตั้งชื่อ Label ว่า **`Image`**
3. ตั้งค่า Condition ดังนี้:

```
{{4.events[].message.type}}  |  Text Operators: Equal to  |  image
```

4. กด Save

---

## 📝 วิธีการใช้งาน

1. **เปิดใช้งาน Workflow** — ไปที่ Scenario แล้วกด Switch จาก **Inactive** → **Active**
2. **เพิ่มเพื่อน Bot ใน LINE** — ผ่านหน้า LINE Official Account หรือแท็บ Messaging API ใน LINE Developers Console
3. **ส่งข้อความ** — ส่งได้ทั้งข้อความ ลิงก์ หรือรูปภาพ
4. **รอการตอบกลับ** — Bot จะประมวลผลและตอบกลับพร้อมสรุป

### 💬 ตัวอย่างการใช้งานปกติ

```
👤 User  : "ข่าวกีฬาเมื่อวาน"

🤖 Bot   :
สรุปหัวข้อข่าว 📰
Topic 🔹    : ข่าวกีฬา
Content 📚  : เนื้อหาข่าวกีฬาเมื่อวาน...
Summary 📑  : สรุปย่อ...
```

### ❌ ตัวอย่างกรณีเกิดข้อผิดพลาด

```
👤 User  : [ส่งรูปภาพที่เสียหาย]
🤖 Bot   : ❌ เกิดข้อผิดพลาดในการประมวลรูปภาพ
```

---

## 🔧 การแก้ไขปัญหา

| ปัญหา | วิธีแก้ไข |
|-------|-----------|
| 🔕 Bot ไม่ตอบสนอง | ตรวจสอบว่าทุก Node ได้ Save แล้ว และ Token / API Key / Webhook URL ถูกต้อง |
| 🔑 `Invalid LINE_CHANNEL_ACCESS_TOKEN` | ไปที่ LINE Developers Console แล้วตรวจสอบ Channel Access Token |
| 🤖 `Gemini API error` | ตรวจสอบว่า API Key ถูกต้องและยังไม่เกิน Quota |
| 📊 `Google Sheets permission denied` | ตรวจสอบว่าสร้าง Google Sheets แล้วหรือยัง ถ้ายังให้ทำตามขั้นตอนที่ 6 |
| 🌐 `Webhook URL not working` | ตรวจสอบว่า Bot กำลังรันอยู่ และ Webhook URL ถูกตั้งค่าใน LINE Developers Console อย่างถูกต้อง |

---

## 🛠️ โครงสร้างโปรเจกต์

```
NewsArticleBot/
├── workflow.json
└── README.md
```

---

## 👥 ผู้จัดทำ

> **กลุ่ม News Chat Bot**  
> คณะเทคโนโลยีสารสนเทศ สาขาวิทยาการคอมพิวเตอร์  
> มหาวิทยาลัยศรีปทุม วิทยาเขตบางเขน

| รหัสนักศึกษา | ชื่อ-นามสกุล |
|-------------|-------------|
| 66057907 | นาย วิทวัส กุยสิงห์ |
| 66090864 | นาย ชลกร บัวหลวง |
| 66036668 | นาย อรรธพงษ์ พินนา |
| 66063367 | นาย พีรพัฒน์ ดอกสันเทียะ |

---

<div align="center">

📅 **วันที่สร้าง:** 23 เมษายน 2026 &nbsp;|&nbsp; 🏷️ **เวอร์ชัน:** 1.0.0

</div>
