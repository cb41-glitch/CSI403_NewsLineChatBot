
<div align="center">

```
███╗   ██╗███████╗██╗    ██╗███████╗
████╗  ██║██╔════╝██║    ██║██╔════╝
██╔██╗ ██║█████╗  ██║ █╗ ██║███████╗
██║╚██╗██║██╔══╝  ██║███╗██║╚════██║
██║ ╚████║███████╗╚███╔███╔╝███████║
╚═╝  ╚═══╝╚══════╝ ╚══╝╚══╝ ╚══════╝
```

# 📰 NewsArticleBot

### LINE Bot สำหรับสรุปบทความข่าว อัตโนมัติด้วย AI

[![Make.com](https://img.shields.io/badge/Make.com-6D00CC?style=for-the-badge&logo=make&logoColor=white)](https://www.make.com)
[![LINE](https://img.shields.io/badge/LINE_Messaging_API-00C300?style=for-the-badge&logo=line&logoColor=white)](https://developers.line.biz)
[![Gemini AI](https://img.shields.io/badge/Google_Gemini_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://aistudio.google.com)
[![Google Sheets](https://img.shields.io/badge/Google_Sheets-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)](https://sheets.google.com)
[![Version](https://img.shields.io/badge/version-1.0.0-orange?style=for-the-badge)](https://github.com)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

</div>

---

## 🌟 ภาพรวมโปรเจกต์

> **NewsArticleBot** คือ LINE Bot ที่ใช้ **Gemini AI** เพื่อวิเคราะห์และสรุปบทความข่าว ทั้งในรูปแบบข้อความและรูปภาพ พร้อมบันทึกผลลัพธ์ลงใน **Google Sheets** โดยอัตโนมัติ ผ่าน Automation Workflow บน **Make.com**

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│             │     │             │     │             │     │             │
│  LINE User  │────▶│  Make.com   │────▶│  Gemini AI  │────▶│Goog Sheets  │
│             │     │  Workflow   │     │             │     │             │
└─────────────┘     └─────────────┘     └─────────────┘     └─────────────┘
     ส่งข้อความ/รูป    ประมวลผล Webhook    วิเคราะห์+สรุป      บันทึกข้อมูล
```

---

## ✨ ฟีเจอร์หลัก

<table>
  <thead>
    <tr>
      <th align="center">ไอคอน</th>
      <th>ฟีเจอร์</th>
      <th>รายละเอียด</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">💬</td>
      <td><strong>ประมวลผลข้อความ</strong></td>
      <td>รับข้อความและสรุปด้วย Gemini AI</td>
    </tr>
    <tr>
      <td align="center">🖼️</td>
      <td><strong>ประมวลผลรูปภาพ</strong></td>
      <td>ดึงข้อความจากรูปภาพและสรุปเนื้อหา</td>
    </tr>
    <tr>
      <td align="center">😊</td>
      <td><strong>รองรับ Emoji</strong></td>
      <td>ใช้ Emoji เพื่อการนำเสนอที่สวยงาม</td>
    </tr>
    <tr>
      <td align="center">🛡️</td>
      <td><strong>จัดการข้อผิดพลาด</strong></td>
      <td>รองรับข้อผิดพลาดพร้อมข้อความแจ้งเตือนที่เข้าใจง่าย</td>
    </tr>
  </tbody>
</table>

---

## 📋 สิ่งที่ต้องเตรียมก่อนเริ่มต้น

ตรวจสอบให้แน่ใจว่ามีสิ่งต่อไปนี้ครบถ้วน:

| # | เครื่องมือ | ลิงก์ |
|:---:|-----------|-------|
| 1 | 🔧 **บัญชี Make.com** สำหรับ Automation Workflow | [สร้างที่นี่ →](https://www.make.com/en) |
| 2 | 💬 **บัญชี LINE Developers** สำหรับ Chatbot | [สร้างที่นี่ →](https://developers.line.biz) |
| 3 | 🤖 **Gemini API Key** จาก Google AI Studio | [รับ API Key →](https://aistudio.google.com) |
| 4 | 📊 **Google Spreadsheet** สำหรับเก็บข้อมูล | [สร้างที่นี่ →](https://docs.google.com/spreadsheets/create) |

---

## 🔑 ตัวอย่าง Credentials ที่ต้องใช้

> ⚠️ **คำเตือน:** ห้ามแชร์ API Key หรือ Token จริงของคุณกับผู้อื่น ตัวอย่างด้านล่างเป็นค่าสมมติเท่านั้น

### 🤖 Google Gemini API Key

```
ตัวอย่าง:   AIzaSyD4xK9mNpQr2wVtUjH8LcE6oBfGnYs3Xae
รูปแบบ:     AIzaSy[A-Za-z0-9_-]{33}
ความยาว:    39 ตัวอักษร
ที่มา:       Google AI Studio → API Keys
```

> 💡 วิธีเช็ค: ขึ้นต้นด้วย `AIzaSy` ตามด้วยตัวอักษรและตัวเลข 33 ตัว

---

### 💬 LINE Channel Access Token

```
ตัวอย่าง:   U2FsdGVkX1+AbCdEfGhIjKlMnOpQrStUvWxYz0123456789/
            ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstu==

รูปแบบ:     Base64 Encoded String (ยาวประมาณ 172 ตัวอักษร)
ที่มา:       LINE Developers Console → Messaging API → Channel Access Token → Issue
```

> 💡 วิธีเช็ค: เป็น String ยาวที่ประกอบด้วยตัวอักษร ตัวเลข `/` และ `+` ลงท้ายด้วย `==`

---

### 🌐 Make.com Webhook URL

```
ตัวอย่าง:   https://hook.eu1.make.com/1yrcfxxxxx
            https://hook.eu2.make.com/ab3de12345fghij
            https://hook.us1.make.com/xyz9876543210abc

รูปแบบ:     https://hook.[region].make.com/[unique-id]
Region:     eu1, eu2, us1, us2 (ขึ้นอยู่กับ Server ที่ใช้)
ที่มา:       Make.com → Scenario → LINE Node → Copy Address to Clipboard
```

> 💡 วิธีเช็ค: ขึ้นต้นด้วย `https://hook.` และมี Region Code ตามด้วย `.make.com/`

---

## 🚀 การติดตั้งและตั้งค่า (Step-by-Step)

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
   อีเมล              : your-email@example.com
   ประเทศที่ตั้งบริษัท  : ไทย
   ชื่อบริษัท/ธุรกิจ   : News Fast Mak
   ประเภทธุรกิจ       : "ผู้เชี่ยวชาญ" / "ผู้ประกาศข่าว"
   ```

5. กด **ตกลง** และยืนยันข้อมูล จากนั้นจะเข้าสู่หน้า LINE Official Account Dashboard
6. ไปที่ **ตั้งค่า** (มุมขวาบน) → **ตั้งค่าการตอบกลับ**
7. ตั้งค่า **ฟีเจอร์การตอบข้อความ** ดังนี้:

   ```
   แชท                       : ❌ ปิด
   ข้อความทักทายเพื่อนใหม่    : ❌ ปิด
   Webhook                   : ✅ เปิด
   ข้อความตอบกลับอัตโนมัติ   : ❌ ปิด
   ```

8. ไปที่หน้า **Messaging API** → กด **ใช้ Messaging API** → เลือก Provider `News Bot` → กด **ยอมรับ**
9. กลับไปที่ LINE Developers → เลือก **News Bot** → **Channels** → **News Chat Bot**
10. ไปที่แท็บ **Messaging API** เลื่อนลงหา **Channel access token** แล้วกด **Issue**

> 📌 **สำคัญ:** เก็บ **Channel Access Token** นี้ไว้ใช้ในขั้นตอนถัดไป
>
> ตัวอย่าง Token ที่ได้รับ:
> ```
> U2FsdGVkX1+AbCdEfGhIjKlMnOpQrStUvWxYz0123456789/ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstu==
> ```

---

### ขั้นตอนที่ 5 — รับ API Key จาก Google AI Studio

1. ไปที่ [Google AI Studio](https://aistudio.google.com) แล้ว Login ด้วยบัญชี Google
2. กดที่ **API keys**
3. กดที่ **ตัวหนังสือฟ้า (รหัส API Key)** ตรง Column Key

> 📌 **สำคัญ:** Copy **API Key** และเก็บไว้ใช้ในขั้นตอนถัดไป
>
> ตัวอย่าง API Key ที่ได้รับ:
> ```
> AIzaSyD4xK9mNpQr2wVtUjH8LcE6oBfGnYs3Xae
> ```

---

### ขั้นตอนที่ 6 — สร้าง Google Sheet สำหรับเก็บข้อมูล

1. ไปที่ [Google Sheets](https://docs.google.com/spreadsheets/create)
2. ตั้งชื่อ Spreadsheet ว่า **`Chat History`**
3. ตั้งชื่อหัวคอลัมน์ในแถวแรก (A, B, C):

   | A | B | C |
   |:---:|:---:|:---:|
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

> ⚠️ **หมายเหตุ:** เนื่องจาก Filter ของ Route ที่ 2 อาจหายไปหลัง Import ให้ตั้งค่าใหม่ดังนี้

1. คลิกที่เส้นระหว่าง **Router** กับ **LINE Node** ของ Route ที่ 2 (ชื่อ `2nd`)
2. ตั้งชื่อ Label ว่า **`Image`**
3. ตั้งค่า Condition ดังนี้:

   ```
   {{4.events[].message.type}}  |  Text Operators: Equal to  |  image
   ```

4. กด Save

---

### ขั้นตอนที่ 11 — ตั้งค่าใน LINE Developer Console

1. ไปที่ Scenario ที่เราสร้างใน Make.com
2. กดคลิกที่ LINE Node ตัวแรก (นับจากซ้ายไปขวา)
3. กดคลิก **Copy Address to Clipboard** แล้วเก็บ Webhook URL ไว้

   > ตัวอย่าง Webhook URL ที่ได้:
   > ```
   > https://hook.eu1.make.com/1yrcfxxxxx
   > ```

4. ไปที่ [LINE Developers Console](https://developers.line.biz)
5. ไปที่ Provider **News Bot**
6. เลื่อนลงมาที่ส่วนของ **Webhook URL** → กด **Edit**
7. วาง Webhook URL ลงในช่อง
8. กด **Run once** ใน Scenario เพื่อ Verify Webhook URL

---

## 📝 วิธีการใช้งาน

### 🟢 เริ่มต้นใช้งาน

1. **เปิดใช้งาน Workflow** — ไปที่ Scenario แล้วกด Switch จาก **Inactive** → **Active**
2. **เพิ่มเพื่อน Bot ใน LINE** — ผ่านหน้า LINE Official Account หรือแท็บ Messaging API ใน LINE Developers Console
3. **ส่งข้อความ** — ส่งได้ทั้งข้อความ ลิงก์ หรือรูปภาพ
4. **รอการตอบกลับ** — Bot จะประมวลผลและตอบกลับพร้อมสรุป

---

### 💬 ตัวอย่างการใช้งาน

#### กรณีที่ 1: ส่งข้อความปกติ

```
👤 User  : "ข่าวกีฬาเมื่อวาน"

🤖 Bot   :
┌──────────────────────────────────────┐
│  สรุปหัวข้อข่าว 📰                   │
│                                      │
│  Topic 🔹    : ข่าวกีฬา             │
│  Content 📚  : เนื้อหาข่าวกีฬา...   │
│  Summary 📑  : สรุปย่อ...            │
└──────────────────────────────────────┘
```

#### กรณีที่ 2: เกิดข้อผิดพลาด

```
👤 User  : [ส่งรูปภาพที่เสียหาย]

🤖 Bot   : ❌ เกิดข้อผิดพลาดในการประมวลรูปภาพ
```

---

## 🔧 การแก้ไขปัญหาที่พบบ่อย

| # | ปัญหา | สาเหตุ | วิธีแก้ไข |
|:---:|-------|--------|-----------|
| 1 | 🔕 **Bot ไม่ตอบสนอง** | Node ยังไม่ได้ Save หรือค่าผิดพลาด | ตรวจสอบว่าทุก Node ได้ Save แล้ว และ Token / API Key / Webhook URL ถูกต้อง |
| 2 | 🔑 **`Invalid LINE_CHANNEL_ACCESS_TOKEN`** | Token หมดอายุหรือผิดพลาด | ไปที่ LINE Developers Console แล้วตรวจสอบ Channel Access Token |
| 3 | 🤖 **`Gemini API error`** | API Key ผิดหรือ Quota เต็ม | ตรวจสอบว่า API Key ถูกต้องและยังไม่เกิน Quota |
| 4 | 📊 **`Google Sheets permission denied`** | ยังไม่ได้สร้างหรือตั้งค่า Sheets | ตรวจสอบว่าสร้าง Google Sheets แล้ว ถ้ายังให้ทำตามขั้นตอนที่ 6 |
| 5 | 🌐 **`Webhook URL not working`** | URL ผิดหรือ Bot ไม่ได้รัน | ตรวจสอบว่า Bot กำลังรันอยู่ และ Webhook URL ถูกตั้งค่าใน LINE Developers Console อย่างถูกต้อง |

---

## 🛠️ โครงสร้างโปรเจกต์

```
📁 NewsArticleBot/
├── 📄 workflow.json       ← Make.com Automation Blueprint
└── 📖 README.md           ← เอกสารนี้
```

---

## 👥 ผู้จัดทำ

<div align="center">

> **กลุ่ม News Chat Bot**
>
> 🏛️ คณะเทคโนโลยีสารสนเทศ สาขาวิทยาการคอมพิวเตอร์
>
> 🎓 มหาวิทยาลัยศรีปทุม วิทยาเขตบางเขน

</div>

<br>

<div align="center">

| รหัสนักศึกษา | ชื่อ-นามสกุล |
|:---:|---|
| `66057907` | นาย วิทวัส กุยสิงห์ |
| `66090864` | นาย ชลกร บัวหลวง |
| `66036668` | นาย อรรธพงษ์ พินนา |
| `66063367` | นาย พีรพัฒน์ ดอกสันเทียะ |

</div>

---

<div align="center">

📅 **วันที่สร้าง:** 23 เมษายน 2026 &nbsp;•&nbsp; 🏷️ **เวอร์ชัน:** 1.0.0

<br>

*Made with ❤️ by News Chat Bot Team — Sripatum University*

</div>
