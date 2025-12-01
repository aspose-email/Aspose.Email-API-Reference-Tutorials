---
date: 2025-12-01
description: เรียนรู้วิธีส่งอีเมลพร้อมรูปภาพฝังในเนื้อหาโดยใช้ Aspose.Email สำหรับ
  Java คู่มือนี้แสดงวิธีฝังรูปภาพในอีเมลและสร้างอีเมล HTML ด้วย Java พร้อมแนบไฟล์แบบอินไลน์
language: th
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: วิธีส่งอีเมลพร้อมภาพฝังในข้อความโดยใช้ Aspose.Email สำหรับ Java
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# วิธีส่งอีเมลพร้อมภาพฝังในข้อความโดยใช้ Aspose.Email for Java

การฝังภาพโดยตรงในอีเมลทำให้ข้อความของคุณดูเป็นมืออาชีพและรับประกันว่าผู้รับจะเห็นกราฟิกโดยไม่ต้องดาวน์โหลดไฟล์แยกต่างหาก ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีส่งอีเมลพร้อมภาพฝัง** โดยใช้ Aspose.Email for Java ครอบคลุมตั้งแต่การตั้งค่าไลบรารี การสร้างอีเมล HTML การเพิ่มทรัพยากรแบบอินไลน์ และสุดท้ายการส่งข้อความ

## คำตอบสั้น ๆ
- **คลาสหลักสำหรับภาพแบบอินไลน์คืออะไร?** `LinkedResource`
- **วิธีใดที่อ้างอิงภาพใน HTML?** ใช้ `cid:yourContentId` ในแท็ก `<img>`
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีได้สำหรับการทดสอบ; ต้องมีไลเซนส์สำหรับการใช้งานจริง
- **ฉันสามารถส่งอีเมลผ่านเซิร์ฟเวอร์ SMTP ใดก็ได้หรือไม่?** ได้ เพียงกำหนดค่า `SmtpClient` ด้วยรายละเอียดเซิร์ฟเวอร์ของคุณ
- **วิธีนี้เข้ากันได้กับไคลเอนต์อีเมลหลักทั้งหมดหรือไม่?** ไคลเอนต์สมัยใหม่ส่วนใหญ่ (Outlook, Gmail, Thunderbird) รองรับภาพฝังแบบ CID

## ไฟล์แนบแบบอินไลน์ (ภาพฝัง) คืออะไร?

ไฟล์แนบแบบอินไลน์—บางครั้งเรียกว่าภาพฝังหรือภาพ CID—เป็นไฟล์ที่อยู่ภายในส่วน MIME ของอีเมล พวกมันถูกอ้างอิงจากส่วน HTML ของข้อความด้วย **Content‑ID** (CID) เทคนิคนี้ทำให้คุณ **ฝังภาพในอีเมล** เพื่อให้ภาพปรากฏตรงตำแหน่งที่คุณใส่แท็ก `<img>` โดยไม่ปรากฏเป็นไฟล์แนบที่ดาวน์โหลดแยกต่างหาก

## ทำไมต้องใช้ภาพฝังในอีเมล Java ของคุณ?

- **รูปลักษณ์มืออาชีพ:** โลโก้ แบนเนอร์ และรูปภาพสินค้าแสดงผลทันที
- **การมีส่วนร่วมที่ดีกว่า:** ผู้รับมีแนวโน้มที่จะอ่านอีเมลที่ดูสมบูรณ์มากขึ้น
- **ไม่มีการคลิกเพิ่มเติม:** ผู้ใช้ไม่ต้องดาวน์โหลดไฟล์แนบเพื่อดูภาพ
- **การสร้างแบรนด์ที่สอดคล้อง:** สินทรัพย์ของแบรนด์ของคุณอยู่ในบรรทัดเดียวกับเนื้อหาอีเมล

## ข้อกำหนดเบื้องต้น

- ไลบรารี Aspose.Email for Java (ดาวน์โหลดจาก [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- สภาพแวดล้อมการพัฒนา Java 8+
- เข้าถึงเซิร์ฟเวอร์ SMTP สำหรับส่งเมล
- ไฟล์รูปภาพที่ต้องการฝัง (เช่น `logo.png`)

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้างอีเมล HTML เบื้องต้น

ก่อนอื่นตั้งค่า `MailMessage` อย่างง่ายพร้อมเนื้อหา HTML นี้จะเป็นผืนผ้าใบที่เราจะฝังภาพต่อไป

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### ขั้นตอนที่ 2: เพิ่มภาพอินไลน์โดยใช้ `LinkedResource`

ตอนนี้เราจะฝังภาพ คลาส `LinkedResource` แทนไฟล์แนบแบบอินไลน์ กำหนด **Content‑ID** ที่ไม่ซ้ำและอ้างอิงในส่วน HTML ด้วย `cid:`

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **เคล็ดลับ:** ทำให้ `ContentId` เรียบง่ายและไม่ซ้ำกันภายในข้อความเพื่อหลีกเลี่ยงความขัดแย้ง

### ขั้นตอนที่ 3: ส่งอีเมลผ่าน `SmtpClient`

กำหนดค่าการตั้งค่า SMTP ของคุณและส่งข้อความ ภาพที่ฝังจะเดินทางพร้อมกับอีเมล ทำให้ผู้รับเห็นได้ทันที

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### ขั้นตอนที่ 4: รับและแยกภาพอินไลน์ (ทางเลือก)

หากคุณต้องการประมวลผลข้อความที่เข้ามาซึ่งมีภาพฝัง คุณสามารถโหลดไฟล์ `.eml` และเข้าถึง `LinkedResources` ของมันได้

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## ปัญหาที่พบบ่อยและวิธีแก้ไข

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **ความไม่ตรงกันของ Content‑ID** | การอ้างอิง `cid:` ใน HTML ไม่ตรงกับ `ContentId` ที่ตั้งไว้บน `LinkedResource` | ตรวจสอบให้สตริงตรงกัน (`image001` กับ `cid:image001`) |
| **ไฟล์ไม่พบ** | เส้นทางไปยังรูปภาพไม่ถูกต้องหรือไฟล์หายไป | ตรวจสอบเส้นทางแบบ absolute/relative และให้แน่ใจว่าไฟล์มีอยู่บนเซิร์ฟเวอร์ |
| **การยืนยันตัวตน SMTP ล้มเหลว** | ข้อมูลประจำตัวหรือการตั้งค่าเซิร์ฟเวอร์ไม่ถูกต้อง | ตรวจสอบ host, port, username, และ password อีกครั้ง. เปิดใช้งาน TLS/SSL หากจำเป็น |
| **ภาพไม่แสดงในบางไคลเอนต์** | ไคลเอนต์บางตัวบล็อกทรัพยากรภายนอก | ใช้ภาพที่ฝังด้วย CID (ตามที่แสดง) แทนการใช้ URL ภายนอก |

## คำถามที่พบบ่อย

**ถาม: ฉันจะดาวน์โหลด Aspose.Email for Java ได้อย่างไร?**  
ตอบ: คุณสามารถดาวน์โหลด Aspose.Email for Java จาก [documentation](https://reference.aspose.com/email/java/). ทำตามคำแนะนำการติดตั้งเพื่อตั้งค่าในโปรเจกต์ของคุณ

**ถาม: ฉันสามารถใช้ Aspose.Email for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
ตอบ: ได้, Aspose.Email สามารถทำงานร่วมกับไลบรารี Java อื่นได้อย่างราบรื่น, ทำให้คุณสามารถรวมการประมวลผลอีเมลกับการสร้าง PDF, OCR, หรือการเข้าถึงฐานข้อมูล

**ถาม: รูปแบบไฟล์ใดที่รองรับสำหรับไฟล์แนบแบบอินไลน์?**  
ตอบ: รูปแบบภาพทั่วไปเช่น PNG, JPEG, GIF, รวมถึงรูปแบบเอกสารอื่น (เช่น SVG) รองรับเป็นทรัพยากรแบบอินไลน์

**ถาม: ฉันจะจัดการไฟล์แนบแบบอินไลน์ในอีเมล HTML อย่างไร?**  
ตอบ: ใช้คลาส `LinkedResource` เพื่อกำหนด `ContentId`, เพิ่มเข้าไปใน `message.getLinkedResources()`, และอ้างอิงในส่วน HTML ด้วย `<img src='cid:yourContentId'>`

**ถาม: Aspose.Email for Java เข้ากันได้กับเซิร์ฟเวอร์อีเมลต่าง ๆ หรือไม่?**  
ตอบ: ได้, มันทำงานกับเซิร์ฟเวอร์ SMTP/IMAP/POP3 ใด ๆ เพียงแค่ระบุที่อยู่เซิร์ฟเวอร์, พอร์ต, และรายละเอียดการยืนยันตัวตนที่ถูกต้อง

**อัปเดตล่าสุด:** 2025-12-01  
**ทดสอบด้วย:** Aspose.Email for Java 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}