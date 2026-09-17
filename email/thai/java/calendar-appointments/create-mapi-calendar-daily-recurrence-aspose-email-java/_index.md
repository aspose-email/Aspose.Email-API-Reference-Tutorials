---
date: '2026-09-17'
description: เรียนรู้วิธีสร้าง outlook calendar ด้วย Java พร้อมการทำซ้ำรายวันและข้อยกเว้น
  และบันทึกปฏิทินเป็นไฟล์ PST ด้วย Aspose.Email for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: สร้าง outlook calendar ใน Java ด้วย Aspose.Email. เรียนรู้การทำซ้ำรายวัน
  การจัดการข้อยกเว้น และการบันทึกเป็น PST ผ่านคู่มือขั้นตอนโดยละเอียด.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: สร้าง outlook calendar ใน Java พร้อมการทำซ้ำรายวันและข้อยกเว้น
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: สร้าง outlook calendar ด้วย Java พร้อมการทำซ้ำรายวันและข้อยกเว้น
url: /th/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง outlook calendar java ด้วยการทำซ้ำรายวันและข้อยกเว้น

การจัดการเหตุการณ์ที่ทำซ้ำอย่างมีประสิทธิภาพอาจเป็นเรื่องท้าทาย โดยเฉพาะเมื่อคุณต้องการ **outlook calendar java** ที่รองรับรูปแบบการทำซ้ำรายวันและข้อยกเว้นเป็นครั้งคราว ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีสร้าง Outlook calendar Java objects, กำหนดการทำซ้ำรายวัน, เพิ่มข้อยกเว้น, และสุดท้าย **save calendar to PST** ด้วย Aspose.Email for Java. เมื่อจบคุณจะมีโค้ดสแนปช็อตที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในบริการกำหนดเวลาที่ใช้ Java ใดก็ได้

## คำตอบด่วน
- **ไลบรารีใด?** Aspose.Email for Java  
- **งานหลัก?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **JDK ที่ต้องการ?** Java 16 or higher  
- **ฉันสามารถแนบไฟล์ไปยังข้อยกเว้นได้หรือไม่?** Yes, using `MapiCalendarExceptionInfo`  
- **ปฏิทินถูกจัดเก็บที่ไหน?** In a PST file via `PersonalStorage`  

## Outlook calendar java คืออะไร?
Outlook calendar java เป็นการแสดงผลแบบโปรแกรมของการนัดหมาย Outlook ที่สร้างบนสเปค MAPI (Messaging Application Programming Interface) ซึ่งรวมคุณสมบัติต่าง ๆ เช่น หัวเรื่อง, สถานที่, เวลาเริ่มต้น/สิ้นสุด, กฎการทำซ้ำ, ผู้เข้าร่วม, และไฟล์แนบ วัตถุนี้สามารถจัดการ, ทำซีเรียลไลซ์, และเก็บในไฟล์ PST ได้โดยไม่ต้องใช้ Outlook

## ทำไมต้องใช้ Aspose.Email for Java?
Aspose.Email for Java ช่วยให้คุณทำงานกับวัตถุ MAPI ได้โดยไม่ต้องติดตั้ง Outlook ไลบรารีรองรับ **50+ MAPI properties**, สามารถสร้างไฟล์ PST Unicode ขนาดสูงสุด **2 GB** ในเวลา **น้อยกว่า 2 วินาที** สำหรับข้อมูลการนัดหมายทั่วไป และทำงานบนแพลตฟอร์มใด ๆ ที่รองรับ Java 16+. วิธีการแบบ Pure‑Java นี้ทำให้สามารถสร้างปฏิทินบนเซิร์ฟเวอร์, สร้างชุดการประชุมอัตโนมัติ, และควบคุมตรรกะการทำซ้ำได้อย่างเต็มที่

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณได้ตั้งค่าต่อไปนี้แล้ว:
- **Aspose.Email Library**: Version 25.4 (or later) – available via Maven or direct download.  
- **Java Development Kit (JDK)**: JDK 16 or newer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, or any Java‑compatible editor.

### ไลบรารีและการพึ่งพาที่จำเป็น

เพื่อรวม Aspose.Email เข้าในโปรเจกต์ของคุณด้วย Maven ให้เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับใบอนุญาต

เพื่อใช้ Aspose.Email คุณจะต้องมีใบอนุญาต:
- **Free trial** – explore all features without cost.  
- **Temporary license** – request for extended evaluation.  
- **Full license** – purchase for production deployments.  

## ตั้งค่า Aspose.Email สำหรับ Java

แรกสุด ตั้งค่าสภาพแวดล้อมของคุณ:

1. ตรวจสอบว่าติดตั้ง JDK 16 แล้วและตั้งค่า `JAVA_HOME` ไว้เรียบร้อย  
2. เพิ่ม dependency ของ Maven (หรือดาวน์โหลด JAR) ไปยังโปรเจกต์ของคุณ  

นี่คือตัวอย่างโค้ดสั้น ๆ ที่แสดงวิธีโหลดไฟล์ใบอนุญาต:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## คู่มือการดำเนินการ

### สร้าง outlook calendar java ด้วยการทำซ้ำรายวันและข้อยกเว้น

#### ภาพรวม
ฟีเจอร์นี้ช่วยให้คุณอัตโนมัติการนัดหมายที่ทำซ้ำได้พร้อมยังคงสามารถข้ามหรือแก้ไขเหตุการณ์เฉพาะได้

#### การดำเนินการทีละขั้นตอน

**1. ตั้งค่าวันที่เริ่มต้นของเหตุการณ์**  
กำหนดว่า series ควรเริ่มต้นเมื่อใด:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. สร้างวัตถุ MAPI calendar**  
คลาส `MapiCalendar` เป็นวัตถุระดับบนสุดที่แทนรายการปฏิทินเดียวในหน่วยความจำ ให้ระบุตำแหน่ง, หัวเรื่อง, และคำอธิบาย:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. กำหนดรูปแบบการทำซ้ำรายวัน**  
คลาส `MapiCalendarRecurrencePattern` เก็บกฎที่ทำซ้ำการนัดหมายทุกวัน ตั้งค่าให้เหตุการณ์ทำซ้ำทุกวัน:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. เพิ่มข้อยกเว้นให้กับการทำซ้ำ**  
`MapiCalendarExceptionInfo` อธิบายเหตุการณ์เดียวที่เบี่ยงเบนจากรูปแบบ—อาจถูกยกเว้นหรือแก้ไข ระบุวันที่ที่ควรยกเว้น (หรือแก้ไข):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### การแนบไฟล์ไปยังข้อยกเว้นของปฏิทิน

#### ภาพรวม
คุณสามารถแนบเอกสารสนับสนุน (เช่น ระเบียบวาระ) ไปยังข้อยกเว้นใด ๆ ได้

**1. สร้างและแนบไฟล์**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## การบันทึก outlook calendar java ไปยัง PST (save calendar to pst)

#### ภาพรวม
บันทึกปฏิทินลงไฟล์ PST เพื่อให้ Outlook หรือไคลเอนต์อื่น ๆ สามารถอ่านได้

**1. สร้างและบันทึกปฏิทินไปยัง PST**  
คลาส `PersonalStorage` มีเมธอดสำหรับสร้างไฟล์ PST ใหม่และเพิ่มรายการ MAPI ลงในไฟล์นั้น

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## การประยุกต์ใช้งานจริง
- **การจัดตารางองค์กร** – automate meeting series, automatically skipping holidays.  
- **การจัดการโครงการ** – track recurring milestones with occasional date shifts.  
- **การวางแผนงานอีเวนต์** – manage multi‑day conferences where some sessions are cancelled or rescheduled.  

### ความเป็นไปได้ในการบูรณาการ
ผสาน Aspose.Email กับแพลตฟอร์ม CRM, API การจัดการงาน, หรือเอนจิน workflow แบบกำหนดเองเพื่อขับเคลื่อนการทำงานอัตโนมัติแบบ end‑to‑end

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **ปลดปล่อยทรัพยากร** – always call `dispose()` on `PersonalStorage` to free file handles.  
- **การใช้สตรีม** – prefer `ByteArrayOutputStream` or file streams to avoid loading entire PSTs into memory.  
- **การทำงานแบบ Async** – for bulk calendar generation, run the creation logic on a background thread to keep UI responsive.  

## สรุป
โดยทำตามคู่มือนี้คุณจะรู้วิธี **create outlook calendar java** objects ด้วยการทำซ้ำรายวัน, เพิ่มข้อยกเว้น, แนบไฟล์, และ **save calendar to PST** ความสามารถเหล่านี้ช่วยให้คุณสร้างฟีเจอร์การกำหนดเวลาที่แข็งแรงโดยไม่ต้องใช้ Outlook โดยตรง

### ขั้นตอนต่อไป
- ทดลองรูปแบบการทำซ้ำแบบรายสัปดาห์หรือรายเดือน  
- สำรวจคุณสมบัติเพิ่มเติมของ MAPI เช่น ผู้เข้าร่วม, การเตือน, และหมวดหมู่  
- ตรวจสอบเอกสาร API ของ Aspose.Email อย่างละเอียดสำหรับสถานการณ์ขั้นสูง

## คำถามที่พบบ่อย

**Q: ไลบรารีสนับสนุนการนัดหมายที่รับรู้โซนเวลาไหม?**  
A: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.

**Q: ฉันสามารถลบเหตุการณ์เดี่ยวจากชุดที่ทำซ้ำได้หรือไม่?**  
A: Use the `DeletedInstanceDates` collection on the recurrence pattern to mark specific dates as removed.

**Q: มีขีดจำกัดขนาดไฟล์ PST ที่สร้างด้วย Aspose.Email หรือไม่?**  
A: PST files follow the Unicode format limits (up to 2 GB by default), but you can configure larger sizes via `PersonalStorage` settings.

**Q: จะเพิ่มผู้เข้าร่วมในคำขอประชุมอย่างไร?**  
A: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`, and add them to the `Recipients` collection of the `MapiMessage`.

**Q: มีการสนับสนุนงานที่ทำซ้ำ (ไม่ใช่แค่การนัดหมาย) หรือไม่?**  
A: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.

**Q: ฉันสามารถใช้คู่มือนี้เป็นส่วนหนึ่งของชุดบทแนะนำ Aspose.Email Java ได้หรือไม่?**  
A: Absolutely – the steps shown here are a core part of any Aspose.Email Java tutorial that deals with calendar creation.

## แหล่งข้อมูล
- [เอกสาร Aspose.Email สำหรับ Java](https://reference.aspose.com/email/java/)
- [ดาวน์โหลด Aspose.Email](https://releases.aspose.com/email/java/)
- [ซื้อใบอนุญาต](https://purchase.aspose.com/buy)
- [เวอร์ชันทดลองฟรี](https://releases.aspose.com/email/java/)
- [ขอใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)
- [ฟอรั่มสนับสนุน Aspose](https://forum.aspose.com/c/email/10)

---

**อัปเดตล่าสุด:** 2026-09-17  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [ส่งออก Outlook calendar PST ด้วย Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [วิธีสร้าง Calendar Item Java ด้วย Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [สร้าง Calendar Sharing Invitation ด้วย Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}