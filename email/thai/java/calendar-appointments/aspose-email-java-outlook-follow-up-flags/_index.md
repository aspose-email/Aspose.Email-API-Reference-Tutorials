---
date: '2025-12-19'
description: เรียนรู้วิธีตั้งธงติดตามใน Outlook ด้วย Aspose.Email สำหรับ Java รวมถึงวิธีตั้งและลบธงติดตามใน
  Outlook อย่างมีประสิทธิภาพ
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
# วิธีตั้งค่าสัญญาณติดตามใน Outlook ด้วย Aspose.Email for Java

## บทนำ
หากคุณเคยประสบปัญหาในการติดตามอีเมลสำคัญ คุณคงรู้ว่าการใช้สัญญาณติดตามของ Outlook มีคุณค่ามากแค่ไหน ในคู่มือนี้เราจะสาธิต **วิธีตั้งค่าสัญญาณติดตาม** อย่างอัตโนมัติด้วย Aspose.Email for Java รวมถึงวิธี **ตั้งค่าสัญญาณติดตาม Outlook** สำหรับผู้รับ และวิธี **ลบสัญญาณติดตาม Outlook** เมื่อภารกิจเสร็จสิ้น สุดท้ายคุณจะสามารถทำงานอัตโนมัติในการติดตามงาน การเตือนความจำ และบันทึกการตรวจสอบโดยตรงจากโค้ด Java ของคุณ

**สิ่งที่คุณจะได้เรียนรู้**
- สร้างและใช้สัญญาณติดตามบนข้อความ Outlook  
- ตั้งค่าสัญญาณติดตามสำหรับผู้รับเฉพาะ  
- ทำเครื่องหมายสัญญาณว่าเสร็จแล้วและลบออกในภายหลัง  
- อ่านตัวเลือกของสัญญาณเพื่อนำไปใช้ในการรายงานหรือการปฏิบัติตามข้อกำหนด  

เตรียมสภาพแวดล้อมให้พร้อมก่อนจะลงมือเขียนโค้ดกัน

## คำตอบสั้น ๆ
- **“วิธีตั้งค่าสัญญาณติดตาม” หมายถึงอะไร?** การเพิ่มสัญญาณพร้อมวันที่เริ่มต้น, การเตือน, และกำหนดเส้นตายให้กับรายการ Outlook  
- **ต้องใช้ไลบรารีใด?** Aspose.Email for Java (เวอร์ชัน 25.4 หรือใหม่กว่า)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ต้องมีลิขสิทธิ์แบบทดลองหรือแบบซื้อเพื่อใช้งานเต็มรูปแบบ  
- **สามารถตั้งค่าสัญญาณเฉพาะผู้รับได้หรือไม่?** ได้ – ใช้ `FollowUpManager.setFlagForRecipients`  
- **สามารถลบสัญญาณภายหลังได้หรือไม่?** ได้ – เรียก `FollowUpManager.clearFlag`

## สัญญาณติดตามคืออะไร?
สัญญาณติดตามเป็นฟีเจอร์ของ Outlook ที่ทำเครื่องหมายอีเมลเป็นงาน พร้อมกำหนดวันที่เริ่มต้น, การเตือน, และกำหนดเส้นตาย ช่วยให้คุณและทีมของคุณติดตามการดำเนินการที่ค้างอยู่ได้อย่างมีประสิทธิภาพ

## ทำไมต้องใช้ Aspose.Email for Java?
Aspose.Email ให้ API แบบ pure‑Java ที่ทำงานได้โดยไม่ต้องติดตั้ง Outlook ช่วยให้คุณจัดการไฟล์ .msg, ตั้งค่าสัญญาณ, และบริหารงานบนแพลตฟอร์มใดก็ได้ – เหมาะสำหรับบริการแบ็กเอนด์, เวิร์กโฟลว์อัตโนมัติ, หรือการเชื่อมต่อกับเครื่องมือจัดการโครงการ

## ข้อกำหนดเบื้องต้น
- **Aspose.Email for Java** เวอร์ชัน 25.4 หรือใหม่กว่า  
- **JDK 16+** ติดตั้งแล้ว  
- IDE ที่รองรับ Maven (IntelliJ IDEA, Eclipse ฯลฯ)  
- ความรู้พื้นฐานด้าน Java และแนวคิดเกี่ยวกับอีเมล

## การตั้งค่า Aspose.Email for Java
### การกำหนดค่า Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับลิขสิทธิ์
Aspose.Email ต้องการลิขสิทธิ์สำหรับการใช้งานในสภาพแวดล้อมจริง

- **ทดลองใช้ฟรี** – ประเมินผล 30 วัน  
- **ลิขสิทธิ์ชั่วคราว** – ทดสอบต่อเนื่อง  
- **ลิขสิทธิ์เต็ม** – สมัครสมาชิกถาวร  

ทำการเริ่มต้นลิขสิทธิ์ก่อนทำงานกับอีเมลใด ๆ

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## คู่มือการทำงาน

### วิธีตั้งค่าสัญญาณติดตาม (ฟีเจอร์ 1)
#### ภาพรวม
ส่วนนี้จะอธิบายขั้นตอนการสร้างข้อความ Outlook, กำหนดวันที่เริ่ม/เตือน/กำหนดเส้นตาย, และใส่สัญญาณติดตาม

#### ขั้นตอน 1: สร้างและเริ่มต้นข้อความ
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*เราจะสร้าง `MailMessage`, ตั้งผู้ส่ง/ผู้รับ, แล้วแปลงเป็น `MapiMessage` เพื่อจัดการสัญญาณ*

#### ขั้นตอน 2: กำหนดวันที่ติดตาม
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*กำหนดวันที่เริ่ม, การเตือน, และกำหนดเส้นตายด้วยคลาส `Calendar`*

#### ขั้นตอน 3: ใส่ตัวเลือกสัญญาณติดตาม
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*อ็อบเจ็กต์ `FollowUpOptions` เก็บรายละเอียดสัญญาณทั้งหมด เราจะนำไปใช้ด้วย `FollowUpManager.setOptions`*

#### ขั้นตอน 4: บันทึกข้อความ
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*บันทึกเป็นไฟล์ `.msg` พร้อมสัญญาณที่แนบอยู่*

### วิธีตั้งค่าสัญญาณติดตาม Outlook สำหรับผู้รับ (ฟีเจอร์ 2)
#### ภาพรวม
บางครั้งคุณต้องการใส่สัญญาณให้ผู้รับเท่านั้น ตัวอย่างนี้จะทำให้ข้อความเป็นแบบร่างก่อน แล้วจึงเพิ่มสัญญาณ

#### ขั้นตอน 1: ทำเครื่องหมายเป็นร่าง
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*การทำให้ข้อความเป็น “unsent” ทำให้ Outlook ถือว่าเป็นร่าง*

#### ขั้นตอน 2: ตั้งค่าสัญญาณสำหรับผู้รับ
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*สัญญาณจะปรากฏต่อผู้รับเท่านั้น*

### วิธีทำเครื่องหมายสัญญาณติดตาม Outlook ว่าเสร็จแล้ว (ฟีเจอร์ 3)
#### ภาพรวม
เมื่อภารกิจเสร็จ คุณสามารถทำเครื่องหมายสัญญาณว่าเสร็จได้โดยอัตโนมัติ

#### ขั้นตอน 1: โหลดข้อความ
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### ขั้นตอน 2: ทำเครื่องหมายว่าเสร็จและบันทึก
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*สถานะสัญญาณเปลี่ยนเป็น “Completed” และบันทึกไฟล์ที่อัปเดต*

### วิธีลบสัญญาณติดตาม Outlook (ฟีเจอร์ 4)
#### ภาพรวม
หากสัญญาณไม่จำเป็นต้องใช้แล้ว สามารถลบออกได้ทั้งหมด

#### ขั้นตอน 1: โหลดและลบสัญญาณ
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*บันทึกข้อความโดยไม่มีสัญญาณติดตามใด ๆ*

### วิธีอ่านตัวเลือกสัญญาณติดตาม (ฟีเจอร์ 5)
#### ภาพรวม
สำหรับการตรวจสอบหรือรายงาน คุณอาจต้องอ่านการตั้งค่าสัญญาณที่มีอยู่

#### ขั้นตอน 1: ดึงตัวเลือก
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*อ็อบเจ็กต์ `options` จะมีวันที่เริ่ม, กำหนดเส้นตาย, การเตือน, และหัวข้อสัญญาณ*

## การนำไปใช้จริง
- **การรวมกับระบบจัดการงาน:** ซิงค์อีเมลที่มีสัญญาณกับ Jira, Trello หรือ Azure Boards  
- **การเตือนอัตโนมัติ:** สร้างอีเมลเตือนประจำวันสำหรับสัญญาณที่ค้างอยู่  
- **การตรวจสอบตามข้อกำหนด:** ส่งออกข้อมูลสัญญาณเพื่อรายงานตามกฎระเบียบ

## พิจารณาด้านประสิทธิภาพ
- **การคำนวณวันที่:** คำนวณวันที่ครั้งเดียวต่อชุดข้อมูล แทนการทำซ้ำในลูป  
- **การจัดการทรัพยากร:** ปิดสตรีมหรือไฟล์แฮนด์เดิลทุกครั้งหลังบันทึกข้อความ  
- **การใช้หน่วยความจำ:** ประมวลผลกล่องเมลขนาดใหญ่เป็นชิ้นย่อยเพื่อหลีกเลี่ยงการใช้ heap มากเกินไป

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| สัญญาณไม่แสดงใน Outlook | ข้อความบันทึกโดยไม่มี `MessageFlags` ที่เหมาะสม | ตรวจสอบให้ `setMessageFlags` ตั้งเป็น `MSGFLAG_UNSENT` ก่อนใส่สัญญาณสำหรับผู้รับ |
| การบันทึกโยน `AccessDeniedException` | เส้นทางไฟล์ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ยืนยันว่าไดเรกทอรีปลายทางมีอยู่และแอปมีสิทธิ์เขียน |
| วันที่ช้าหนึ่งวัน | ความแตกต่างของโซนเวลา | ใช้ `TimeZone.getTimeZone("GMT")` หรือโซนเวลาท้องถิ่นอย่างสม่ำเสมอ |

## คำถามที่พบบ่อย
**ถาม: Aspose.Email for Java คืออะไร?**  
ตอบ: เป็น API แบบ pure‑Java ที่ช่วยให้คุณสร้าง, อ่าน, และจัดการไฟล์อีเมล (MSG, EML ฯลฯ) โดยไม่ต้องติดตั้ง Outlook

**ถาม: จะขอรับลิขสิทธิ์ทดลองฟรีได้อย่างไร?**  
ตอบ: เยี่ยมชม [Aspose website](https://releases.aspose.com/email/java/) เพื่อดาวน์โหลดรุ่นทดลอง 30 วัน

**ถาม: สามารถตั้งค่าสัญญาณติดตามหลายรายการในข้อความเดียวได้หรือไม่?**  
ตอบ: Outlook รองรับสัญญาณหนึ่งรายการต่อข้อความเท่านั้น แต่คุณสามารถเก็บข้อมูลงานเพิ่มเติมในคุณสมบัติ MAPI แบบกำหนดเอง

**ถาม: ข้อความไม่บันทึกหลังตั้งค่าสัญญาณ ควรตรวจสอบอะไร?**  
ตอบ: ตรวจสอบว่าเส้นทาง `outputDir` ถูกต้องและแอปมีสิทธิ์เขียนที่ตำแหน่งนั้น

**ถาม: จะลบสัญญาณจากหลายข้อความพร้อมกันอย่างไร?**  
ตอบ: วนลูปผ่านคอลเลกชันข้อความของคุณและเรียก `FollowUpManager.clearFlag` กับแต่ละ `MapiMessage`

## แหล่งข้อมูล
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**อัปเดตล่าสุด:** 2025-12-19  
**ทดสอบกับ:** Aspose.Email for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}