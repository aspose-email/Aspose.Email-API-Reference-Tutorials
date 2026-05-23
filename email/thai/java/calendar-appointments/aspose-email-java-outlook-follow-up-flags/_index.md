---
date: '2026-02-22'
description: เรียนรู้วิธีตั้งธงติดตามใน Outlook ด้วย Aspose.Email สำหรับ Java รวมถึงการตั้งค่า
  การอ่าน และการลบธงสำหรับผู้รับ.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: วิธีตั้งธงติดตามใน Outlook ด้วย Aspose.Email สำหรับ Java
url: /th/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีตั้ง Outlook Follow Up Flag ด้วย Aspose.Email สำหรับ Java

## บทนำ
หากคุณเคยประสบปัญหาในการติดตามอีเมลสำคัญ คุณคงรู้ว่าฟีเจอร์ **outlook follow up flag** ของ Outlook มีคุณค่ามากแค่ไหน ในคู่มือนี้เราจะแสดง **วิธีตั้ง outlook follow up flag** อย่างโปรแกรมมิ่งด้วย Aspose.Email สำหรับ Java รวมถึงวิธี **ตั้ง outlook follow up flag สำหรับผู้รับ** และวิธี **ลบ outlook follow up flag** เมื่อภารกิจเสร็จสิ้น เมื่ออ่านจบคุณจะสามารถทำงานอัตโนมัติในการติดตามงาน, การเตือน, และบันทึกการตรวจสอบโดยตรงจากโค้ด Java ของคุณ

**สิ่งที่คุณจะได้เรียนรู้**
- สร้างและใช้ฟล็กติดตามบนข้อความ Outlook  
- ตั้งฟล็กติดตามสำหรับผู้รับเฉพาะ  
- ทำเครื่องหมายฟล็กว่าเสร็จแล้วและลบภายหลัง  
- อ่านตัวเลือกของฟล็กเพื่อการรายงานหรือการปฏิบัติตาม  

มาเตรียมสภาพแวดล้อมให้พร้อมก่อนที่จะลงลึกในโค้ดกัน

## คำตอบอย่างรวดเร็ว
- **What does “how to set follow‑up” mean?** การเพิ่มฟล็กพร้อมวันที่เริ่ม, การเตือน, และวันครบกำหนดให้กับรายการ Outlook.  
- **Which library is required?** Aspose.Email for Java (v25.4 หรือใหม่กว่า).  
- **Do I need a license?** ใช่, จำเป็นต้องมีไลเซนส์แบบทดลองหรือซื้อเพื่อใช้งานเต็มรูปแบบ.  
- **Can I set flags for recipients only?** แน่นอน – ใช้ `FollowUpManager.setFlagForRecipients`.  
- **Is it possible to remove a flag later?** ใช่, เรียก `FollowUpManager.clearFlag`.

## Outlook Follow Up Flag คืออะไร?
Outlook follow up flag คือเครื่องหมายงานในตัวที่สามารถแนบวันที่เริ่ม, การเตือน, และวันครบกำหนดให้กับรายการเมลใดก็ได้ มันทำให้ข้อความอีเมลธรรมดากลายเป็นรายการงานที่ติดตามได้ ช่วยให้คุณและทีมของคุณคอยตรวจสอบงานที่ค้างอยู่ได้อย่างต่อเนื่อง.

## ทำไมต้องใช้ Aspose.Email สำหรับ Java?
Aspose.Email ให้ API แบบ pure‑Java ที่ทำงานได้โดยไม่ต้องติดตั้ง Outlook ช่วยให้คุณจัดการไฟล์ .msg, ตั้งฟล็ก, และจัดการงานบนแพลตฟอร์มใดก็ได้—เหมาะอย่างยิ่งสำหรับ **automate outlook tasks**, บริการ backend, หรือการรวมกับเครื่องมือจัดการโครงการ.

## ข้อกำหนดเบื้องต้น
- **Aspose.Email for Java** เวอร์ชัน 25.4 หรือใหม่กว่า (รู้จักอีกชื่อว่า **aspose email java**).  
- **JDK 16+** ติดตั้งแล้ว.  
- IDE ที่รองรับ Maven (IntelliJ IDEA, Eclipse, ฯลฯ).  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับแนวคิดอีเมล.

## การตั้งค่า Aspose.Email สำหรับ Java
### การกำหนดค่า Maven
เพิ่ม dependency ต่อไปนี้ลงในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์
Aspose.Email ต้องการไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมการผลิต:
- **Free trial** – การประเมิน 30 วัน.  
- **Temporary license** – การทดสอบต่อเนื่อง.  
- **Full license** – การสมัครสมาชิกถาวร.  

เริ่มต้นไลเซนส์ก่อนทำการดำเนินการใด ๆ กับอีเมล:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## ตั้ง Outlook Follow Up Flag (Feature 1)
### ขั้นตอน 1: สร้างและเริ่มต้นข้อความ
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*เราจะสร้าง `MailMessage` ก่อน, ตั้งผู้ส่ง/ผู้รับ, แล้วแปลงเป็น `MapiMessage` เพื่อจัดการฟล็ก.*

### ขั้นตอน 2: กำหนดวันที่ Follow‑Up (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*ที่นี่เราตั้งวันที่เริ่ม, การเตือน (คือ **outlook flag reminder**), และวันครบกำหนดโดยใช้คลาส `Calendar`.*

### ขั้นตอน 3: ใช้ตัวเลือก Follow‑Up
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*อ็อบเจ็กต์ `FollowUpOptions` เก็บรายละเอียดของฟล็กทั้งหมด ซึ่งเรานำไปใช้ด้วย `FollowUpManager.setOptions`.*

### ขั้นตอน 4: บันทึกข้อความ
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*ข้อความจะถูกบันทึกเป็นไฟล์ `.msg` พร้อมฟล็กที่แนบอยู่.*

## วิธีตั้งฟล็กสำหรับผู้รับ (Feature 2)
### ภาพรวม
บางครั้งคุณต้องการให้ฟล็กปรากฏ **เฉพาะผู้รับ** ตัวอย่างนี้ทำเครื่องหมายข้อความเป็นแบบร่างก่อน แล้วจึงเพิ่มฟล็ก.

#### ขั้นตอน 1: ทำเครื่องหมายเป็นแบบร่าง
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*การทำเครื่องหมายข้อความว่าไม่ได้ส่งทำให้ Outlook ถือว่าเป็นแบบร่าง.*

#### ขั้นตอน 2: ตั้งฟล็กสำหรับผู้รับ
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*ฟล็กตอนนี้จะมองเห็นได้เฉพาะผู้รับ – สถานการณ์คลาสสิกของ **flag for recipients**.*

## วิธีทำเครื่องหมาย Outlook Follow Up Flag ว่าเสร็จแล้ว (Feature 3)
### ขั้นตอน 1: โหลดข้อความ
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### ขั้นตอน 2: ทำเครื่องหมายว่าเสร็จแล้วและบันทึก
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*สถานะฟล็กจะเปลี่ยนเป็น “Completed” และไฟล์ที่อัปเดตจะถูกบันทึก.*

## วิธีลบ Outlook Follow Up Flag (Feature 4)
### ขั้นตอน 1: โหลดและลบฟล็ก
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*ข้อความจะถูกบันทึกโดยไม่มีฟล็กใด ๆ.*

## วิธีอ่านตัวเลือกฟล็ก (Feature 5)
### ขั้นตอน 1: ดึงตัวเลือก
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*อ็อบเจ็กต์ `options` ตอนนี้มีวันที่เริ่ม, วันครบกำหนด, และการเตือน รวมถึงหัวข้อฟล็ก – มีประโยชน์เมื่อคุณต้อง **read flag options** เพื่อการรายงาน.*

## การประยุกต์ใช้งานจริง
- **Task‑Management Integration:** ซิงค์อีเมลที่มีฟล็กกับ Jira, Trello, หรือ Azure Boards.  
- **Automated Reminders:** สร้างอีเมลเตือนประจำวันสำหรับการติดตามที่ค้างอยู่.  
- **Compliance Audits:** ส่งออกข้อมูลฟล็กเพื่อการรายงานตามกฎระเบียบ.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Date Calculations:** คำนวณวันที่ครั้งเดียวต่อชุด แทนการคำนวณในลูป.  
- **Resource Management:** ปิดสตรีมหรือไฟล์แฮนด์เดิลใด ๆ หลังบันทึกข้อความ.  
- **Memory Usage:** ประมวลผลกล่องเมลขนาดใหญ่เป็นชิ้นส่วนเพื่อหลีกเลี่ยงความกดดันของ heap.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| ฟล็กไม่แสดงใน Outlook | ข้อความถูกบันทึกโดยไม่มี `MessageFlags` ที่เหมาะสม | ตรวจสอบให้แน่ใจว่า `setMessageFlags` ถูกตั้งเป็น `MSGFLAG_UNSENT` ก่อนทำการตั้งฟล็กสำหรับผู้รับ. |
| การบันทึกเกิดข้อผิดพลาด `AccessDeniedException` | เส้นทางไฟล์ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่าไดเรกทอรีปลายทางมีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |
| วันที่ผิดพลาดหนึ่งวัน | ความไม่ตรงกันของเขตเวลา | ใช้ `TimeZone.getTimeZone("GMT")` หรือเขตเวลาท้องถิ่นของคุณอย่างสม่ำเสมอ. |

## คำถามที่พบบ่อย
**Q: Aspose.Email for Java คืออะไร?**  
A: เป็น API แบบ pure‑Java ที่ให้คุณสร้าง, อ่าน, และจัดการไฟล์อีเมล (MSG, EML, ฯลฯ) โดยไม่ต้องติดตั้ง Outlook.

**Q: จะขอรับไลเซนส์ทดลองฟรีได้อย่างไร?**  
A: เยี่ยมชม [Aspose website](https://releases.aspose.com/email/java/) เพื่อดาวน์โหลดการทดลอง 30 วัน.

**Q: สามารถตั้งหลายฟล็กติดตามบนข้อความเดียวได้หรือไม่?**  
A: Outlook รองรับฟล็กเพียงหนึ่งอันต่อข้อความเท่านั้น แต่คุณสามารถเก็บข้อมูลงานเพิ่มเติมในคุณสมบัติ MAPI แบบกำหนดเองได้.

**Q: ข้อความของฉันไม่ถูกบันทึกหลังตั้งฟล็ก ควรตรวจสอบอะไร?**  
A: ตรวจสอบว่าเส้นทาง `outputDir` ถูกต้องและแอปพลิเคชันมีสิทธิ์เขียนในตำแหน่งนั้น.

**Q: จะลบฟล็กจากหลายข้อความพร้อมกันได้อย่างไร?**  
A: วนลูปผ่านคอลเลกชันข้อความของคุณและเรียก `FollowUpManager.clearFlag` สำหรับแต่ละ `MapiMessage`.

## แหล่งข้อมูล
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**อัปเดตล่าสุด:** 2026-02-22  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}