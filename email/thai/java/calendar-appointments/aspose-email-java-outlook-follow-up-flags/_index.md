---
date: '2026-07-27'
description: เรียนรู้วิธีตั้ง Outlook Flag Java ด้วย Aspose.Email for Java ครอบคลุมการสร้างแฟล็ก,
  แฟล็กของผู้รับ, การทำให้เสร็จ, การลบ, และตัวเลือกการอ่าน
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: ตั้ง Outlook Flag Java ด้วย Aspose.Email for Java คู่มือนี้แสดงวิธีสร้าง,
  อ่าน, ทำให้เสร็จ, และลบ Outlook follow‑up flags อย่างมีประสิทธิภาพ
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: ตั้งค่า Outlook Flag Java – คู่มือการเขียนโปรแกรม Aspose.Email ฉบับสมบูรณ์
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: ตั้งค่า Outlook Flag Java – คู่มือการเขียนโปรแกรม Aspose.Email ฉบับสมบูรณ์
url: /th/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ตั้งค่า Outlook Flag Java ด้วย Aspose.Email สำหรับ Java

## บทนำ
หากคุณต้องการ **set outlook flag java** อย่างโปรแกรม คุณมาถูกที่แล้ว ธงติดตามของ Outlook จะเปลี่ยนอีเมลธรรมดาให้เป็นงานที่ติดตามได้ และ Aspose.Email for Java ช่วยให้คุณจัดการธงเหล่านี้ได้โดยไม่ต้องติดตั้ง Outlook ในบทเรียนนี้ เราจะอธิบายขั้นตอนการสร้าง อ่าน ทำสำเร็จ และสุดท้ายการลบธง รวมถึงวิธีการใช้ธงสำหรับผู้รับเฉพาะ ในตอนท้ายคุณจะได้สคริปต์ Java ที่สามารถนำกลับมาใช้ใหม่เพื่อทำงานติดตามงานโดยอัตโนมัติจากบริการแบ็กเอนด์ของคุณ

## คำตอบสั้น
- **หมายความว่า “set outlook flag java” คืออะไร?** การเพิ่มธงพร้อมวันที่เริ่ม, การเตือน, และวันครบกำหนดให้กับรายการ Outlook ผ่านโค้ด Java.  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Email for Java (v25.4 หรือใหม่กว่า).  
- **ต้องใช้ไลเซนส์หรือไม่?** ใช่ – เวอร์ชันทดลองใช้ได้สำหรับการประเมิน แต่ต้องมีไลเซนส์ที่ซื้อสำหรับการใช้งานจริง.  
- **ฉันสามารถตั้งธงสำหรับผู้รับเท่านั้นได้หรือไม่?** แน่นอน – ใช้ `FollowUpManager.setFlagForRecipients`.  
- **สามารถลบธงภายหลังได้หรือไม่?** ใช่ – เรียก `FollowUpManager.clearFlag`.

## ธงติดตามของ Outlook คืออะไร?
ธงติดตามของ Outlook เป็นเครื่องหมายงานในตัวที่สามารถแนบวันที่เริ่ม, การเตือน, และวันครบกำหนดให้กับรายการเมลใด ๆ ก็ได้ มันทำให้ข้อความอีเมลกลายเป็นรายการที่ติดตามได้ ช่วยให้คุณและทีมของคุณติดตามงานที่ค้างอยู่ได้อย่างมีประสิทธิภาพ

## ทำไมต้องใช้ Aspose.Email สำหรับ Java?
Aspose.Email for Java รองรับ **70+ รูปแบบอีเมล** (รวมถึง MSG, EML, MHTML, และ TNEF) และสามารถประมวลผล **มากกว่า 100,000 ข้อความต่อหนึ่งนาที** บนเซิร์ฟเวอร์ 8‑core ปกติ ทั้งหมดนี้โดยไม่ต้องมี Outlook บนเครื่องโฮสต์ ทำให้เหมาะสำหรับการอัตโนมัติด้านแบ็กเอนด์, รายงานการปฏิบัติตาม, และการรวมกับเครื่องมือจัดการโครงการ

## ข้อกำหนดเบื้องต้น
- **Aspose.Email for Java** เวอร์ชัน 25.4 หรือใหม่กว่า.  
- **JDK 16+** ติดตั้งแล้ว.  
- IDE ที่รองรับ Maven (IntelliJ IDEA, Eclipse ฯลฯ).  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับแนวคิดอีเมล

## การตั้งค่า Aspose.Email สำหรับ Java
### การกำหนดค่า Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์
Aspose.Email ต้องการไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมจริง:

- **Free trial** – การประเมิน 30 วัน.  
- **Temporary license** – การทดสอบต่อเนื่อง.  
- **Full license** – การสมัครสมาชิกถาวร.

เริ่มต้นไลเซนส์ก่อนทำการดำเนินการใด ๆ กับอีเมล:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## ตั้งค่า Outlook Flag Java (ฟีเจอร์ 1)
### คำตอบโดยตรง
โหลด `MailMessage`, แปลงเป็น `MapiMessage`, กำหนดค่า `FollowUpOptions`, แล้วเรียก `FollowUpManager.setOptions`. ขั้นตอนนี้จะสร้างรายการ Outlook ที่มีธงครบถ้วนในไม่กี่บรรทัดของโค้ด Java

### ขั้นตอน 1: สร้างและเริ่มต้นข้อความ
`MailMessage` เป็นคลาสระดับสูงของ Aspose.Email ที่แทนอีเมล หลังจากสร้างข้อความแล้วคุณจะแปลงเป็น `MapiMessage` เพื่อจัดการธง

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*เราสร้าง `MailMessage` ก่อน, ตั้งผู้ส่ง/ผู้รับ, แล้วแปลงเป็น `MapiMessage` เพื่อจัดการธง.*

### ขั้นตอน 2: กำหนดวันที่ติดตาม (การเตือน Outlook Flag)
`FollowUpOptions` เก็บวันที่เริ่ม, การเตือน, และวันครบกำหนด ใช้ `Calendar` ของ Java เพื่อกำหนดค่าเวลาอย่างแม่นยำ

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*ที่นี่เราตั้งวันที่เริ่ม, การเตือน (**outlook flag reminder**), และวันครบกำหนดโดยใช้คลาส `Calendar`.*

### ขั้นตอน 3: ใช้ตัวเลือกการติดตาม
เมธอด `FollowUpManager.setOptions` จะผูกธงเข้ากับ `MapiMessage`

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*อ็อบเจ็กต์ `FollowUpOptions` มีรายละเอียดของธงทั้งหมด เราจึงใช้ `FollowUpManager.setOptions` เพื่อแนบธง.*

### ขั้นตอน 4: บันทึกข้อความ
บันทึกข้อความที่มีธงเป็นไฟล์ `.msg` เพื่อให้ Outlook แสดงธงได้

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*ข้อความถูกบันทึกเป็นไฟล์ `.msg` พร้อมธงที่แนบอยู่.*

## วิธีตั้งธงสำหรับผู้รับ (ฟีเจอร์ 2)?
ใช้ `FollowUpManager.setFlagForRecipients` หลังจากทำเครื่องหมายข้อความเป็นฉบับร่าง วิธีนี้จะเพิ่มธงติดตามเฉพาะในสำเนาของผู้รับ โดยไม่กระทบมุมมองของผู้ส่ง ต้องตั้งค่า `MessageFlags.MSGFLAG_UNSENT` ก่อนการใช้ธง คุณยังสามารถกำหนดวันที่เริ่ม, การเตือน, และวันครบกำหนดด้วยอ็อบเจ็กต์ `FollowUpOptions` ก่อนเรียกเมธอด

### คำตอบโดยตรง
ทำเครื่องหมายข้อความเป็นฉบับร่างโดยใช้ `MessageFlags.MSGFLAG_UNSENT` แล้วเรียก `FollowUpManager.setFlagForRecipients`. Outlook จะแสดงธงเฉพาะผู้รับ ไม่แสดงกับผู้ส่ง

### ภาพรวม
บางครั้งคุณต้องการให้ธงปรากฏ **เฉพาะสำหรับผู้รับ** ตัวอย่างนี้ทำเครื่องหมายข้อความเป็นฉบับร่างก่อน แล้วจึงเพิ่มธง

#### ขั้นตอน 1: ทำเครื่องหมายเป็นฉบับร่าง
`MessageFlags` เป็น enumeration ของ MAPI ที่ควบคุมสถานะของข้อความ การตั้งค่า `MSGFLAG_UNSENT` จะบอก Outlook ว่ารายการเป็นฉบับร่าง

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*การทำเครื่องหมายข้อความว่าไม่ได้ส่งทำให้ Outlook ถือว่าเป็นฉบับร่าง.*

#### ขั้นตอน 2: ตั้งธงสำหรับผู้รับ
`FollowUpManager.setFlagForRecipients` จะผูกธงเฉพาะกับสำเนาของผู้รับ

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*ธงตอนนี้มองเห็นได้เฉพาะผู้รับ – สถานการณ์ **flag for recipients** แบบคลาสสิก.*

## วิธีทำเครื่องหมายธงติดตามของ Outlook ว่าเสร็จแล้ว (ฟีเจอร์ 3)?
โหลดไฟล์ `.msg` เข้า `MapiMessage` แล้วเรียก `FollowUpManager.completeFlag` วิธีนี้จะอัปเดตสถานะธงเป็น Completed และเพิ่มเครื่องหมายถูกใน Outlook หลังจากทำสำเร็จให้บันทึกข้อความเพื่อบันทึกการเปลี่ยนแปลง คุณอาจตั้งเวลาสำเร็จโดยปรับคุณสมบัติ `FlagCompleteTime` หากต้องการสำหรับการตรวจสอบ

### คำตอบโดยตรง
โหลดไฟล์ `.msg` ที่มีอยู่เข้า `MapiMessage`, เรียก `FollowUpManager.completeFlag`, แล้วบันทึกไฟล์ สถานะธงจะเปลี่ยนเป็น “Completed” และแสดงเครื่องหมายถูกใน Outlook

### ขั้นตอน 1: โหลดข้อความ
`MapiMessage` สามารถอ่านไฟล์ `.msg` ที่บันทึกไว้ ทำให้คุณเข้าถึงคุณสมบัติ MAPI ทั้งหมด

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### ขั้นตอน 2: ทำเครื่องหมายว่าเสร็จแล้วและบันทึก
`FollowUpManager.completeFlag` จะอัปเดตสถานะธง หลังจากนั้นคุณบันทึกการเปลี่ยนแปลง

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*สถานะธงเปลี่ยนเป็น “Completed” และไฟล์ที่อัปเดตถูกบันทึก.*

## วิธีลบธงติดตามของ Outlook (ฟีเจอร์ 4)?
เปิดไฟล์ `.msg` ด้วย `MapiMessage`, เรียก `FollowUpManager.clearFlag`, แล้วบันทึกข้อความ วิธีนี้จะลบคุณสมบัติ MAPI ที่เกี่ยวกับธงทั้งหมด ทำให้ Outlook ไม่แสดงตัวบ่งชี้การติดตามใด ๆ ใช้เมธอดนี้เมื่อภารกิจถูกยกเลิกหรือไม่เกี่ยวข้องอีกต่อไป อย่าลืมลบคุณสมบัติการเตือนแบบกำหนดเองเพื่อหลีกเลี่ยงการแจ้งเตือนที่เหลืออยู่

### คำตอบโดยตรง
เปิดไฟล์ `.msg` ด้วย `MapiMessage`, เรียก `FollowUpManager.clearFlag`, แล้วบันทึกไฟล์ ข้อความจะไม่แสดงตัวบ่งชี้การติดตามใด ๆ ใน Outlook

### ขั้นตอน 1: โหลดและลบธง
`FollowUpManager.clearFlag` จะลบคุณสมบัติทั้งหมดที่เกี่ยวกับธงออกจากข้อความ

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*ข้อความถูกบันทึกโดยไม่มีธงติดตามใด ๆ.*

## วิธีอ่านตัวเลือกของธง (ฟีเจอร์ 5)?
เรียก `FollowUpManager.getOptions` บน `MapiMessage` ที่โหลดแล้วเพื่อรับอ็อบเจ็กต์ `FollowUpOptions` อ็อบเจ็กต์นี้ให้ข้อมูลวันที่เริ่ม, วันครบกำหนด, การเตือน, และหัวข้อของธง ช่วยให้คุณแสดงหรือบันทึกรายละเอียดของธงได้ เป็นประโยชน์สำหรับการรายงานและการตรวจสอบการปฏิบัติตาม

### คำตอบโดยตรง
ใช้ `FollowUpManager.getOptions` บน `MapiMessage` ที่โหลดแล้วเพื่อดึงอ็อบเจ็กต์ `FollowUpOptions` ที่มีวันที่เริ่ม, วันครบกำหนด, การเตือน, และหัวข้อของธง ซึ่งเป็นประโยชน์สำหรับการรายงานหรือการตรวจสอบการปฏิบัติตาม

### ขั้นตอน 1: ดึงตัวเลือก
อ็อบเจ็กต์ `options` ที่คืนค่ามาให้มองเห็นการกำหนดค่าของธงทั้งหมด

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*อ็อบเจ็กต์ `options` ตอนนี้มีวันที่เริ่ม, วันครบกำหนด, การเตือน, และหัวข้อของธง – มีประโยชน์เมื่อคุณต้อง **read flag options** เพื่อการรายงาน.*

## การประยุกต์ใช้งานจริง
- **Task‑Management Integration:** ซิงค์อีเมลที่มีธงกับ Jira, Trello หรือ Azure Boards.  
- **Automated Reminders:** สร้างอีเมลเตือนประจำวันสำหรับการติดตามที่ค้างอยู่.  
- **Compliance Audits:** ส่งออกข้อมูลธงสำหรับการรายงานตามกฎระเบียบ โดยใช้ความสามารถในการอ่านตัวเลือกของธงผ่านโปรแกรม

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Date Calculations:** คำนวณวันที่ครั้งเดียวต่อชุด แทนการคำนวณในลูป.  
- **Resource Management:** ปิดสตรีมหรือไฟล์แฮนด์ลทั้งหมดหลังจากบันทึกข้อความ.  
- **Memory Usage:** ประมวลผลกล่องเมลขนาดใหญ่เป็นชิ้นส่วนเพื่อหลีกเลี่ยงความกดดันของ heap; Aspose.Email สามารถจัดการกล่องเมลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## คำถามที่พบบ่อย
**Q: Aspose.Email for Java คืออะไร?**  
A: เป็น API แบบ pure‑Java ที่ให้คุณสร้าง อ่าน และจัดการไฟล์อีเมล (MSG, EML ฯลฯ) โดยไม่ต้องติดตั้ง Outlook

**Q: จะขอรับไลเซนส์ทดลองฟรีได้อย่างไร?**  
A: เยี่ยมชม [Aspose website](https://releases.aspose.com/email/java/) เพื่อดาวน์โหลดเวอร์ชันทดลอง 30 วัน

**Q: สามารถตั้งหลายธงติดตามบนข้อความเดียวได้หรือไม่?**  
A: Outlook รองรับเพียงธงเดียวต่อข้อความ แต่คุณสามารถเก็บข้อมูลงานเพิ่มเติมในคุณสมบัติ MAPI ที่กำหนดเองได้

**Q: ข้อความของฉันไม่ถูกบันทึกหลังตั้งธง ควรตรวจสอบอะไร?**  
A: ตรวจสอบว่าเส้นทาง `outputDir` ถูกต้องและแอปพลิเคชันมีสิทธิ์เขียนในตำแหน่งนั้น

**Q: จะลบธงจากหลายข้อความพร้อมกันอย่างไร?**  
A: วนลูปผ่านคอลเลกชันข้อความของคุณและเรียก `FollowUpManager.clearFlag` บนแต่ละ `MapiMessage`

## แหล่งข้อมูล
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**อัปเดตล่าสุด:** 2026-07-27  
**ทดสอบกับ:** Aspose.Email for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [Manage Outlook Categories with Aspose.Email for Java - A Comprehensive Guide](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Create outlook notes java with Aspose.Email – Full Guide](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Create Tasks in Microsoft Exchange Using Aspose.Email for Java: A Complete Guide](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}