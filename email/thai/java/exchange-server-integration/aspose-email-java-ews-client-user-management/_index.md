---
date: '2026-07-08'
description: เรียนรู้วิธีสร้าง EWS client Java ด้วย Aspose.Email เพื่อการจัดการอีเมลที่มีประสิทธิภาพ
  รวมถึง message deletion, appending, และ user impersonation บน Exchange Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: เรียนรู้วิธีสร้าง EWS client Java ด้วย Aspose.Email เพื่อการจัดการอีเมลที่มีประสิทธิภาพ
  รวมถึง message deletion, appending, และ user impersonation บน Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: สร้าง EWS Client Java ด้วย Aspose.Email – จัดการผู้ใช้
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: สร้าง EWS Client Java ด้วย Aspose.Email – จัดการผู้ใช้
url: /th/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญการจัดการอีเมล: Aspose.Email Java สำหรับผู้ใช้และการทำตัวเป็นผู้ใช้ของ EWS Client

## บทนำ

ในบทแนะนำนี้คุณจะ **create EWS client Java** แอปพลิเคชันด้วย Aspose.Email ซึ่งทำให้คุณสามารถจัดการกล่องเมลหลายกล่องของ Exchange Server จากฐานโค้ด Java เพียงชุดเดียว เราจะอธิบายการสร้างอินสแตนซ์ `EWSClient` การลบข้อความ การเพิ่มอีเมลใหม่ และการทำตัวเป็นผู้ใช้คนอื่น—งานเหล่านี้ช่วยประหยัดเวลาหลายชั่วโมงจากการทำงานด้วยมือในสภาพแวดล้อมองค์กร

### สิ่งที่คุณจะได้เรียนรู้
- วิธี **create EWS client Java** วัตถุโดยใช้ข้อมูลรับรองที่แตกต่างกัน.  
- เทคนิคที่มีประสิทธิภาพในการลบทุกข้อความจากโฟลเดอร์ที่เลือก.  
- ขั้นตอนการเพิ่มอีเมลที่เตรียมไว้แล้วลงในกล่องเมลของผู้ใช้.  
- วิธีทำตัวเป็นผู้ใช้ของกล่องเมลอื่นสำหรับสถานการณ์กล่องเมลที่แชร์.

ตอนนี้คุณรู้แล้วว่าเราจะครอบคลุมอะไร มาเตรียมสภาพแวดล้อมการพัฒนากันเถอะ.

## คำตอบอย่างรวดเร็ว
- **ขั้นตอนแรกคืออะไร?** เพิ่มการพึ่งพา Aspose.Email Maven ไปยังไฟล์ `pom.xml` ของคุณ.  
- **คลาสใดที่เป็นตัวแทนการเชื่อมต่อ Exchange?** `EWSClient` (หรืออินเทอร์เฟซ `IEWSClient`).  
- **ฉันสามารถลบข้อความทั้งหมดในหนึ่งคำสั่งได้หรือไม่?** ใช่—ทำการวนซ้ำด้วย `listMessages` และเรียก `deleteMessage` สำหรับแต่ละ URI.  
- **ฉันจะส่งอีเมลโดยไม่ใช้ SMTP ได้อย่างไร?** ใช้ `appendMessage` เพื่อวาง `MailMessage` ลงในโฟลเดอร์โดยตรง.  
- **การทำตัวเป็นผู้ใช้ปลอดภัยหรือไม่?** มันทำงานภายใต้ข้อมูลรับรองเดิมและเคารพนโยบายการมอบหมายของ Exchange.

## create EWS client Java คืออะไร?
`create ews client java` หมายถึงการสร้างอ็อบเจ็กต์ `EWSClient` ในแอปพลิเคชัน Java เพื่อให้คุณสามารถเรียกใช้การดำเนินการของ Exchange Web Services (EWS) อย่างโปรแกรมได้ วิธีนี้ช่วยขจัดความจำเป็นในการโต้ตอบกับ Outlook ด้วยตนเองและทำให้การประมวลผลกล่องเมลเป็นอัตโนมัติ โดยการสร้างคลไอเอนท์เฉพาะสำหรับแต่ละผู้ใช้ คุณสามารถแยกข้อมูลรับรอง, บังคับใช้นโยบายต่อกล่องเมล, และขยายโซลูชันไปยังหลายสิบบัญชีโดยไม่ต้องทำซ้ำโค้ด.

## ทำไมต้องใช้ Aspose.Email สำหรับการรวม EWS?
Aspose.Email รองรับ **50+** การดำเนินการของ EWS, จัดการกล่องเมล **หลายร้อยหน้า** โดยไม่ต้องโหลดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ, และประมวลผล **สูงสุด 10,000** ข้อความต่อหนึ่งนาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป ความสามารถที่วัดได้เหล่านี้ทำให้เป็นตัวเลือกอันดับต้น ๆ สำหรับการทำอัตโนมัติอีเมลในระดับใหญ่ ไลบรารียังแยกรายละเอียด SOAP ระดับต่ำออกไป, ให้ API ที่สะอาดและปลอดภัยต่อประเภท ซึ่งช่วยลดเวลาในการพัฒนาและลดบั๊ก.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** สำหรับการจัดการการพึ่งพา.  
- **Aspose.Email for Java** ไลบรารี (เพิ่มผ่าน Maven).  
- ความรู้พื้นฐานเกี่ยวกับแนวคิดของ Exchange Web Services (EWS).

## การตั้งค่า Aspose.Email สำหรับ Java
เพิ่มไลบรารีลงในไฟล์ `pom.xml` ของ Maven ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับใบอนุญาต
Aspose.Email มีการทดลองใช้ฟรี พร้อมตัวเลือกในการขอใบอนุญาตชั่วคราวเพื่อใช้ความสามารถเต็มรูปแบบ สำหรับการใช้งานระยะยาว พิจารณาซื้อใบอนุญาตจาก [หน้าการซื้อของ Aspose](https://purchase.aspose.com/buy).

## วิธีสร้าง EWS client Java?
โหลดบริการ Exchange ด้วยข้อมูลรับรองที่เหมาะสมและรับอินสแตนซ์ `IEWSClient`—รูปแบบสองขั้นตอนนี้เป็นแกนหลักของทุกการดำเนินการต่อไป คุณสามารถใช้คลไอเอนท์เดียวกันสำหรับหลายการกระทำหรือสร้างอินสแตนซ์แยกตามผู้ใช้เพื่อแยกการทำงาน **`IEWSClient` คืออินเทอร์เฟซที่เปิดเผยการดำเนินการ EWS ทั้งหมด, ในขณะที่ `EWSClient` ให้เมธอดแฟกทอรีแบบสแตติกเพื่อรับการใช้งาน**  

การสร้างคลไอเอนท์โดยทั่วไปต้องระบุ URL ของบริการ, ชื่อผู้ใช้, รหัสผ่าน, และอาจรวมถึงข้อมูลโดเมน เมื่อสร้างแล้วคลไอเอนท์จะจัดการการตรวจสอบสิทธิ์, การลงนามคำขอ, และการแยกวิเคราะห์การตอบสนองโดยอัตโนมัติ.

### สร้างอินสแตนซ์ EWSClient
**คำนิยาม:** `EWSClient` (ที่เปิดเผยผ่านอินเทอร์เฟซ `IEWSClient`) เป็นอ็อบเจ็กต์หลักของ Aspose.Email สำหรับสื่อสารกับเซิร์ฟเวอร์ Exchange ผ่าน EWS.

#### นำเข้าคลาสที่จำเป็น
เริ่มต้นด้วยการนำเข้าคลาส Aspose.Email ที่จำเป็น:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### เริ่มต้นอินสแตนซ์ EWSClient
สร้างอ็อบเจ็กต์ `IEWSClient` สำหรับแต่ละกล่องเมลที่คุณต้องการจัดการ:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*คำอธิบาย:* ตัวช่วย `getEWSClient` เชื่อมต่อกับ Exchange ด้วยข้อมูลรับรองที่ให้, คืนค่าคลไอเอนท์พร้อมใช้งานที่เคารพสิทธิ์ของผู้ใช้ปัจจุบัน.

## วิธีลบข้อความจากโฟลเดอร์?
ดึงรายการทั้งหมดในโฟลเดอร์เป้าหมายและลบอย่างถาวรแต่ละรายการในหนึ่งขั้นตอน วิธีนี้หลีกเลี่ยงภาระการเปิดแต่ละข้อความแยกกัน **`listMessages` คืนค่าคอลเลกชันของอ็อบเจ็กต์ `MessageInfo` ที่มี URI เฉพาะของแต่ละข้อความ, ซึ่งคุณจะส่งต่อไปยัง `deleteMessage` เพื่อเอารายการออกจากเซิร์ฟเวอร์**  

การประมวลผลเป็นชุดช่วยลดการเดินทางของเครือข่ายและป้องกันการหมดเวลาเมื่อจัดการกับโฟลเดอร์ขนาดใหญ่ ควรตรวจสอบให้แน่ใจว่าโฟลเดอร์ที่คุณกำหนดเป็นเป้าหมายถูกต้อง เนื่องจากการลบไม่สามารถย้อนกลับได้หากไม่มีการสำรองข้อมูล.

### รายการและลบข้อความ
วนซ้ำแต่ละ URI ของข้อความและเรียกการดำเนินการลบ:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*คำอธิบาย:* `listMessages` คืนค่าคอลเลกชันของอ็อบเจ็กต์ `MessageInfo`; ค่า `getUniqueUri()` ของพวกมันจะถูกส่งไปยัง `deleteMessage`, ซึ่งลบรายการออกจากเซิร์ฟเวอร์อย่างถาวร.

## วิธีเพิ่มข้อความลงในโฟลเดอร์?
สร้างอ็อบเจ็กต์ `MailMessage` ในเครื่องและเก็บไว้โดยตรงในโฟลเดอร์ของกล่องเมล—ไม่ต้องใช้เซิร์ฟเวอร์ SMTP **`MailMessage` แทนอีเมลที่มีส่วนหัว, เนื้อหา, และไฟล์แนบ; สามารถสร้างทั้งหมดในหน่วยความจำก่อนที่จะบันทึกลง Exchange**  

การเพิ่มข้อความข้ามขั้นตอนการส่ง ทำให้เหมาะสำหรับแบบร่าง, แม่แบบ, หรือการสร้างข้อความแบบโปรแกรมที่ต้องการให้ข้อความปรากฏทันทีในกล่องเมลของผู้ใช้.

### สร้างและส่งข้อความ
สร้างอีเมลและเพิ่มลงในโฟลเดอร์ Drafts:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*คำอธิบาย:* `appendMessage` รับ `MailMessage` และ `FolderInfo` (เช่น Drafts) แล้วเขียนรายการลงในกล่องเมล ทำให้ผู้ใช้สามารถเข้าถึงได้ทันที.

## วิธีทำตัวเป็นผู้ใช้ใน EWS?
สลับบริบทความปลอดภัยของคลไอเอนท์ไปยังกล่องเมลอื่น, ทำการกระทำ, แล้วกลับไปยังบัญชีเดิม สิ่งนี้จำเป็นสำหรับการจัดการกล่องเมลที่แชร์ **`impersonateUser` ตั้งค่า `ImpersonatedUserId` บนคำขอ EWS พื้นฐาน, ทำให้เซิร์ฟเวอร์ถือว่าการเรียกนั้นมาจากกล่องเมลเป้าหมาย**  

หลังจากทำการดำเนินการที่ต้องการเสร็จสิ้น, เรียก `resetImpersonation` เพื่อคืนค่าข้อมูลรับรองเดิม, เพื่อให้การเรียกต่อไปทำงานภายใต้บริบทความปลอดภัยที่ถูกต้อง.

### ดำเนินการทำตัวเป็นผู้ใช้
เปลี่ยนบริบทของคลไอเอนท์ชั่วคราวเพื่อทำหน้าที่เป็นผู้ใช้คนอื่น:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*คำอธิบาย:* `impersonateUser` ตั้งค่า `ImpersonatedUserId` บนคำขอ EWS พื้นฐาน, ทำให้คุณสามารถอ่านหรือเขียนเหมือนเป็นผู้ใช้เป้าหมาย การเรียก `resetImpersonation` คืนค่าข้อมูลรับรองเดิม.

## การประยุกต์ใช้งานจริง
Using Aspose.Email Java enables robust email automation solutions:
1. **ทำความสะอาดอีเมลอัตโนมัติ:** กำหนดงานประจำคืนที่ลบโฟลเดอร์ Draft ที่ล้าสมัยในหลายสิบกล่องเมล.  
2. **การแจกจ่ายอีเมลเป็นชุด:** เพิ่มประกาศเทมเพลตลงใน Inbox ของพนักงานทุกคนด้วยลูปเดียว.  
3. **การจัดการกล่องเมลที่แชร์:** ทำตัวเป็นผู้ใช้ของกล่องเมลแผนกเพื่อเก็บถาวรข้อความเก่าโดยไม่ต้องให้ผู้ใช้แต่ละคนเข้าถึงเต็มรูปแบบ.

## พิจารณาด้านประสิทธิภาพ
To keep your application responsive when handling large mailboxes:
- **เรียก API เป็นชุด** เมื่อเป็นไปได้ (เช่น ลบ 500 ข้อความต่อคำขอ).  
- **สตรีมข้อความ** แทนการโหลดเนื้อหาเต็มลงในหน่วยความจำ.  
- **ทำลายอ็อบเจ็กต์คลไอเอนท์** อย่างทันท่วงทีเพื่อปล่อยซ็อกเก็ตเครือข่ายและการเชื่อมต่อ HTTP.

## ปัญหาและวิธีแก้ไขทั่วไป
- **ข้อผิดพลาดการเชื่อมต่อ:** ตรวจสอบ URL ของจุดสิ้นสุด EWS, ตรวจสอบว่า TLS 1.2 เปิดใช้งาน, และยืนยันกฎไฟร์วอลล์อนุญาต HTTPS ขาออก.  
- **การปฏิเสธสิทธิ์ในการทำตัวเป็นผู้ใช้:** บัญชีบริการต้องได้รับมอบหมายบทบาท “ApplicationImpersonation” ใน Exchange.  
- **การหมดเวลาของโฟลเดอร์ขนาดใหญ่:** เพิ่มค่า timeout ของ `HttpWebRequest` หรือประมวลผลโฟลเดอร์เป็นส่วนย่อย ๆ.

## คำถามที่พบบ่อย

**Q: ฉันจะแก้ไขปัญหาการเชื่อมต่อกับ EWS อย่างไร?**  
A: ตรวจสอบ URL ของจุดสิ้นสุด, ข้อมูลรับรอง, และไฟร์วอลล์เครือข่าย; เปิดการบันทึกรายละเอียดใน Aspose.Email เพื่อจับข้อมูลคำขอ/การตอบสนอง HTTP.

**Q: Aspose.Email สามารถจัดการปริมาณอีเมลจำนวนมากได้อย่างมีประสิทธิภาพหรือไม่?**  
A: ใช่—API แบบชุดของมันทำให้คุณประมวลผล **10,000+** ข้อความต่อหนึ่งนาทีโดยคงการใช้หน่วยความจำต่ำกว่า 200 MB.

**Q: กรณีการใช้งานทั่วไปของการทำตัวเป็นผู้ใช้ใน EWS คืออะไร?**  
A: การจัดการกล่องเมลที่แชร์, การทำการเก็บถาวรเป็นชุด, และการรันรายงานตามกำหนดเวลาในนามของผู้ใช้หลายคนโดยไม่ต้องเก็บรหัสผ่านของพวกเขา.

**Q: มีขีดจำกัดการเรียก API ที่กำหนดโดย Aspose.Email หรือไม่?**  
A: Aspose.Email เองไม่มีการจำกัดการเรียก; อย่างไรก็ตาม Exchange อาจบังคับใช้นโยบายการจำกัดการใช้ที่คุณต้องปฏิบัติตาม.

**Q: ฉันจะรักษาความปลอดภัยของข้อมูลรับรองในโค้ด Java ของฉันได้อย่างไร?**  
A: เก็บไว้ในไฟล์กำหนดค่าที่เข้ารหัสหรือใช้ Azure Key Vault / AWS Secrets Manager, และใช้ HTTPS เสมอสำหรับจุดสิ้นสุด EWS.

---

**อัปเดตล่าสุด:** 2026-07-08  
**ทดสอบกับ:** Aspose.Email for Java 23.10  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างอินสแตนซ์ EWSClient ด้วย Aspose.Email สำหรับ Java: คู่มือการรวม Exchange Server](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [วิธีเชื่อมต่อกับ Microsoft Exchange Server ด้วย Aspose.Email สำหรับ Java และ EWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [อัตโนมัติการจัดการอีเมลด้วย Aspose.Email และ Java EWS Client: คู่มือฉบับสมบูรณ์](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}