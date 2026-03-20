---
date: '2026-03-20'
description: เรียนรู้วิธีส่งออกไฟล์ PST ปฏิทิน Outlook ด้วย Aspose.Email สำหรับ Java
  – สร้างรายการปฏิทิน MAPI ตั้งค่าการทำซ้ำ เพิ่มผู้เข้าร่วม และบันทึกเป็น PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: ส่งออก PST ปฏิทิน Outlook ด้วย Aspose.Email – Java
url: /th/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออก Outlook calendar PST ด้วย Aspose.Email – Java

## บทนำ

คุณกำลังมองหาแนวทางทำให้การอัตโนมัติของปฏิทินในแอปพลิเคชัน Java ของคุณเป็นเรื่องง่ายขึ้นและต้องการ **export Outlook calendar PST** ไฟล์หรือไม่? ด้วย **Aspose.Email for Java** คุณสามารถ **create MAPI calendar Java** รายการ, กำหนดรูปแบบการเกิดซ้ำ, เพิ่มผู้เข้าร่วม, และ **save calendar to PST** ด้วยเพียงไม่กี่บรรทัดของโค้ด บทเรียนนี้จะพาคุณผ่านกระบวนการทั้งหมด — ตั้งแต่การตั้งค่าห้องสมุดจนถึงการสร้างรายการปฏิทินที่ทำงานเต็มรูปแบบพร้อมสำหรับการแจกจ่าย.

### สิ่งที่คุณจะได้เรียนรู้
- วิธี **create MAPI calendar Java** เหตุการณ์โดยใช้ Aspose.Email.  
- การกำหนดรูปแบบการเกิดซ้ำแบบรายวัน, รายสัปดาห์, หรือแบบกำหนดเอง.  
- การเพิ่มผู้รับ (ผู้จัด, ผู้เข้าร่วม) ไปยังคำเชิญปฏิทินของคุณ.  
- การบันทึกรายการปฏิทินโดย **saving calendar to PST** เพื่อความเข้ากันได้กับ Outlook.  
- วิธี **automate meeting scheduling** ด้วยโค้ดที่ใช้ซ้ำได้.

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใด?** Aspose.Email for Java  
- **เป้าหมายหลัก?** Export Outlook calendar PST and **save calendar to PST**  
- **ข้อกำหนดเบื้องต้น?** Java 8+, Maven, Aspose.Email license  
- **ระยะเวลาการดำเนินการโดยทั่วไป?** 10‑15 minutes for a basic event  
- **สามารถเพิ่มการเกิดซ้ำได้หรือไม่?** Yes – daily, weekly, monthly, etc.

## ส่งออก Outlook calendar PST

ในส่วนนี้เราจะมุ่งเน้นที่กระบวนการแบบครบวงจรที่ทำให้คุณสามารถ **export Outlook calendar PST** ไฟล์ได้ หลังจากสร้างอ็อบเจกต์ MAPI calendar ขั้นตอนสุดท้ายคือการเก็บไว้ในไฟล์ PST ที่ Outlook สามารถอ่านได้โดยตรง.

## ทำไมต้องใช้ Aspose.Email สำหรับการอัตโนมัติของปฏิทิน?

- **Full Outlook compatibility** – รายการที่สร้างขึ้นทำงานใน Outlook, OWA, และไคลเอนต์มือถือ.  
- **Rich recurrence support** – รองรับการเกิดซ้ำแบบรายวัน, รายสัปดาห์, รายเดือน, และรูปแบบกำหนดเองโดยพร้อมใช้งาน.  
- **No external dependencies** – ห้องสมุด Java แท้, ไม่ต้องใช้ COM interop.  
- **High performance** – การจัดการไฟล์ PST ขนาดใหญ่และการดำเนินการแบบกลุ่มอย่างมีประสิทธิภาพ.  
- **Automate meeting scheduling** – ฝังตรรกะนี้ในงานแบตช์หรือเว็บเซอร์วิสเพื่อสร้างคำเชิญหลายร้อยรายการโดยอัตโนมัติ.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

### ไลบรารีที่จำเป็น
- **Aspose.Email for Java**: Version 25.4 or later.

### ความต้องการการตั้งค่าสภาพแวดล้อม
- IDE ของ Java เช่น IntelliJ IDEA หรือ Eclipse.  
- Maven ที่ติดตั้งเพื่อจัดการ dependencies.

### ความรู้เบื้องต้นที่จำเป็น
- ทักษะการเขียนโปรแกรม Java เบื้องต้น.  
- ความคุ้นเคยกับแนวคิดเชิงวัตถุ.

## การตั้งค่า Aspose.Email สำหรับ Java

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับใบอนุญาต

Aspose.Email offers a free trial, but a license unlocks all features:

- **Free Trial**: ทดสอบโดยไม่มีข้อจำกัดเป็นเวลา 30 วัน.  
- **Temporary License**: ขอผ่าน [Aspose's website](https://purchase.aspose.com/temporary-license/) หากคุณต้องการเวลาเพิ่มเติม.  
- **Purchase**: ซื้อใบอนุญาตถาวรจาก [purchase page](https://purchase.aspose.com/buy).

### การเริ่มต้นพื้นฐาน

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## คู่มือการดำเนินการ

Now that you’re set up, let’s **create MAPI calendar Java** and **save calendar to PST**.

### สร้าง MAPI Calendar พร้อมการเกิดซ้ำ

#### ภาพรวม

We'll build a calendar event, apply a daily recurrence, add attendees, and finally store it in a PST file.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน

1. **กำหนดวันที่และรูปแบบการเกิดซ้ำ**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` เก็บรายละเอียดการเกิดซ้ำ; เราเลือกรูปแบบรายวันผ่าน `MapiCalendarDailyRecurrencePattern`.

2. **ตั้งค่าผู้รับ**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` stores each attendee; `MAPI_TO` marks them as primary recipients.

3. **สร้างรายการ MAPI Calendar**  

   Build the calendar object with all required details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explanation*: The constructor expects organizer, subject, location, start/end times, description, recipient list, and recurrence.

4. **บันทึกเป็นไฟล์ PST**  

   Finally, persist the calendar by **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` generates a new PST file, and `addMapiMessageItem` inserts the calendar entry into the "Calendar" folder.

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบเส้นทางของใบอนุญาต; ใบอนุญาตที่ไม่ถูกต้องจะจำกัดฟังก์ชัน.  
- ตรวจสอบให้แน่ใจว่าอีเมลของผู้รับถูกจัดรูปแบบอย่างถูกต้องเพื่อหลีกเลี่ยงความล้มเหลวของคำเชิญ.  
- ปิด PST (`pst.dispose()`) หลังการดำเนินการเพื่อปล่อยตัวจัดการไฟล์.

## การประยุกต์ใช้งานจริง

Here are common scenarios where **creating MAPI calendar Java** and **saving calendar to PST** shines:

1. **Automated Meeting Scheduling** – สร้างคำเชิญการประชุมที่เกิดซ้ำสำหรับทีมโครงการโดยไม่ต้องทำด้วยตนเอง.  
2. **Event Management Platforms** – ส่งออกเซสชันของการประชุมเป็นรายการปฏิทินที่เข้ากันได้กับ Outlook.  
3. **CRM Integration** – ซิงค์นัดหมายของลูกค้าจากระบบ CRM ไปยัง Outlook โดยตรงผ่านไฟล์ PST.

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **Resource Management**: ปล่อยอ็อบเจกต์ `PersonalStorage` หลังการใช้งานเพื่อป้องกันการล็อกไฟล์.  
- **Batch Processing**: สำหรับปริมาณมาก, ประมวลผลรายการปฏิทินแบบอะซิงโครนัสหรือเป็นชิ้นส่วนเพื่อรักษาการใช้หน่วยความจำน้อย.

## สรุป

You’ve now learned how to **export Outlook calendar PST** by creating MAPI calendar Java objects, configuring recurrence, adding attendees, and **saving calendar to PST** using Aspose.Email. This approach empowers your Java applications to automate sophisticated scheduling workflows with Outlook compatibility.

For deeper exploration, check the official [documentation](https://reference.aspose.com/email/java/).

## ส่วนคำถามที่พบบ่อย

### ถ: ฉันสามารถสร้างรูปแบบการเกิดซ้ำรายสัปดาห์ได้หรือไม่?
- **A**: ใช่! ใช้ `MapiCalendarWeeklyRecurrencePattern` เพื่อกำหนดการทำซ้ำรายสัปดาห์.

### ถ: ฉันจะจัดการข้อยกเว้นในการเกิดซ้ำของเหตุการณ์อย่างไร?
- **A**: เรียก `setExceptions()` บนอ็อบเจกต์ recurrence เพื่อระบุวันที่ที่แตกต่างจากรูปแบบ.

### ถ: สามารถอัปเดตรายการปฏิทินที่มีอยู่ได้หรือไม่?
- **A**: แน่นอน โหลดรายการจาก PST, แก้ไขคุณสมบัติ, แล้วบันทึกกลับ.

### ถ: ฉันสามารถเข้ารหัสไฟล์ PST ได้หรือไม่?
- **A**: ใช่, Aspose.Email อนุญาตให้ตั้งรหัสผ่านบน `PersonalStorage` เมื่อสร้าง PST.

### ถ: ถ้าฉันต้องการเพิ่มไฟล์แนบในเหตุการณ์ปฏิทินจะทำอย่างไร?
- **A**: ใช้ `calendar.getAttachments().addFileAttachment("path/to/file")` ก่อนบันทึก.

## แหล่งข้อมูล

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}