---
date: '2026-08-01'
description: เรียนรู้วิธีส่งออกปฏิทินเป็น PST ด้วย Aspose.Email for Java รวมถึงวิธีเพิ่ม
  attendees ตั้งค่าวันเริ่มต้นและวันสิ้นสุด และจัดการ appointments อย่างมีประสิทธิภาพ
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email for Java. เรียนรู้ขั้นตอนต่อขั้นตอนวิธีสร้าง
  appointments, เพิ่ม attendees, และสร้างไฟล์ Outlook PST
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: ส่งออกปฏิทินเป็น PST – คู่มือฉบับสมบูรณ์ด้วย Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email for Java
url: /th/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email for Java

หากคุณกำลังพัฒนาแอปพลิเคชัน Java ที่ต้องการแชร์ข้อมูลการกำหนดเวลากับ Outlook คุณมักจะต้อง **export calendar to PST**. ในบทแนะนำนี้เราจะอธิบายทุกขั้นตอนที่คุณต้องการ—ตั้งแต่การสร้างการนัดหมายง่าย ๆ การเพิ่มผู้เข้าร่วม และสุดท้ายการบันทึกเหตุการณ์ลงในไฟล์ PST ทั้งหมดด้วย Aspose.Email for Java. เมื่อเสร็จสิ้นคุณจะได้โซลูชันพร้อมใช้งานในระดับผลิตที่ทำงานบน Windows, Linux, และ macOS.

## คำตอบสั้น
- **เป้าหมายหลักคืออะไร?** ส่งออกเหตุการณ์ปฏิทินเป็นไฟล์ PST.  
- **ต้องใช้ไลบรารีใด?** Aspose.Email for Java (v25.4+).  
- **ต้องการไลเซนส์หรือไม่?** ใช่, ไลเซนส์ Aspose.Email ที่ถูกต้องจะลบข้อจำกัดการประเมิน.  
- **สามารถเพิ่มผู้เข้าร่วมได้หรือไม่?** แน่นอน – ใช้ `MapiRecipientCollection`.  
- **รองรับเวอร์ชัน Java ใด?** JDK 16 หรือสูงกว่า.

## **export calendar to pst** คืออะไร?
`MapiCalendar` คือคลาสของ Aspose.Email ที่จำลองรายการปฏิทินของ Outlook รวมถึงหัวเรื่อง, สถานที่, และรายละเอียดเวลา.

การส่งออกปฏิทินเป็น PST หมายถึงการแปลงอ็อบเจกต์ `MapiCalendar` ที่อยู่ในหน่วยความจำให้เป็น Microsoft Outlook Personal Storage Table (PST). ไฟล์ PST ที่สร้างขึ้นสามารถเปิดโดยตรงใน Outlook, แชร์กับเพื่อนร่วมงาน, หรือนำเข้าไปยังระบบใด ๆ ที่รองรับรูปแบบ PST, โดยคงรายละเอียดเหตุการณ์ทั้งหมดเช่น ผู้เข้าร่วม, การทำซ้ำ, และการแจ้งเตือน.

## ทำไมต้องใช้ Aspose.Email for Java เพื่อส่งออกปฏิทินเป็น PST?
คุณสามารถสร้างไฟล์ PST ที่เข้ากันได้เต็มรูปแบบโดยไม่ต้องติดตั้ง Outlook. Aspose.Email ให้ **full MAPI support**, ทำงานบน **all major OSes**, และสามารถจัดการ **up to 2 TB** ของข้อมูลในรูปแบบ Unicode PST—เพียงพอสำหรับการเก็บข้อมูลระดับองค์กร. API ยังช่วยให้คุณจัดการผู้เข้าร่วม, รูปแบบการทำซ้ำ, การแจ้งเตือน, และคุณสมบัติกำหนดเองด้วยการเรียกเมธอดเพียงไม่กี่ครั้ง, ลดความพยายามในการพัฒนาอย่างมาก.

## ข้อกำหนดเบื้องต้น
- **ไลบรารีและการพึ่งพา**: Aspose.Email for Java เวอร์ชัน 25.4 หรือใหม่กว่า.  
- **สภาพแวดล้อม**: JDK 16 หรือสูงกว่า, Maven สำหรับการจัดการการพึ่งพา.  
- **ความรู้**: การเขียนโปรแกรม Java เบื้องต้นและความคุ้นเคยกับ Maven.

## วิธีตั้งค่า Aspose.Email for Java
เพิ่มการพึ่งพา Aspose.Email ลงในไฟล์ `pom.xml` ของคุณและรีเฟรชโปรเจกต์ Maven. ขั้นตอนเดียวนี้ทำให้ API ของ MAPI ทั้งหมดพร้อมใช้งานใน classpath ของคุณ.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์
1. **Free Trial**: เยี่ยมชม [Aspose download page](https://releases.aspose.com/email/java/) เพื่อรับไลเซนส์ชั่วคราว.  
2. **Temporary License**: สมัครผ่าน [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: พิจารณาซื้อจาก [Aspose's purchase portal](https://purchase.aspose.com/buy) สำหรับการใช้งานระยะยาว.

เมื่อคุณมีไลเซนส์แล้ว ให้เริ่มต้นในแอปพลิเคชันของคุณเพื่อเปิดใช้งานคุณลักษณะทั้งหมด.

## วิธีการ **สร้างการนัดหมาย** (สร้างเหตุการณ์ปฏิทิน Java)
โหลดอ็อบเจกต์ `MapiCalendar`, ตั้งค่าคุณสมบัติหลักของมัน, และคืนค่าเพื่อพร้อมสำหรับการประมวลผลต่อไป. เมธอดนี้สร้างรายการปฏิทินที่มีหัวเรื่อง, สถานที่, คำอธิบาย, และ **java calendar start date** / **java calendar end date** ที่คุณกำหนด.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Explanation*: คลาส `MapiCalendar` เป็นการแสดงของ Aspose.Email สำหรับรายการปฏิทินของ Outlook. หลังจากตั้งค่าฟิลด์พื้นฐานแล้วคุณยังสามารถกำหนดรูปแบบการทำซ้ำ, การแจ้งเตือน, และหมวดหมู่ก่อนบันทึก.

## วิธีการ **เพิ่มผู้เข้าร่วม** (java เพิ่มผู้เข้าร่วมการประชุม)
สร้าง `MapiRecipientCollection`, เติมข้อมูลด้วยผู้เข้าร่วมแต่ละคน, และแนบเข้ากับการประชุม. สิ่งนี้ทำให้ผู้เข้าร่วมทุกคนได้รับคำเชิญที่เหมาะสมเมื่อเปิดไฟล์ PST.

`MapiRecipientCollection` คือคลาสคอลเลกชันที่เก็บอ็อบเจกต์ `MapiRecipient` ซึ่งเป็นตัวแทนของผู้เข้าร่วมการประชุม. `MapiRecipient` แสดงผู้เข้าร่วมแต่ละคนพร้อมคุณสมบัติเช่น ที่อยู่อีเมลและประเภทผู้รับ.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Explanation*: `MapiRecipient` กำหนดผู้เข้าร่วมการประชุมหนึ่งคน. การตั้งค่าชนิดเป็น `MAPI_TO` ทำให้ที่อยู่นั้นเป็นผู้เข้าร่วมหลัก, ในขณะที่ `MAPI_CC` หรือ `MAPI_BCC` สามารถใช้สำหรับผู้เข้าร่วมแบบเลือกได้.

## วิธีการ **ส่งออกปฏิทินเป็น pst** (สร้าง PST พร้อมเหตุการณ์ปฏิทิน)
สร้างไฟล์ PST แบบ Unicode, เพิ่มโฟลเดอร์ "Calendar", และแทรกอ็อบเจกต์ `MapiCalendar` ที่สร้างไว้ก่อนหน้านี้. PST ที่ได้สามารถเปิดใน Outlook หรือแจกจ่ายให้ผู้ใช้ปลายทางได้.

`PersonalStorage` คือคลาสของ Aspose.Email ที่ใช้ในการสร้าง, เปิด, และจัดการไฟล์ PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Explanation*: `PersonalStorage` เป็นจุดเริ่มต้นสำหรับการจัดการ PST. การใช้รูปแบบ Unicode ทำให้คุณหลีกเลี่ยงข้อจำกัด 2 GB ของเวอร์ชัน PST เก่าและได้รับประโยชน์จาก I/O ที่เร็วขึ้นสำหรับคลังข้อมูลขนาดใหญ่.

## การประยุกต์ใช้งานจริง
1. **การกำหนดเวลาทางธุรกิจ** – อัตโนมัติการสร้างและแจกจ่ายการประชุมภายใน.  
2. **การจัดการกิจกรรม** – ติดตามการประชุม, เวิร์กช็อป, และรายการผู้เข้าร่วม.  
3. **การบูรณาการ CRM** – ซิงค์การนัดหมายกับเครื่องมือการจัดการความสัมพันธ์กับลูกค้า.  
4. **การวางแผนโครงการ** – เก็บมิลสโตนของโครงการเป็นรายการปฏิทิน.  
5. **การทำงานร่วมกันของทีมระยะไกล** – สร้างไฟล์ PST สำหรับการแชร์แบบออฟไลน์.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Dispose objects** ที่คุณไม่ต้องการใช้แล้วเพื่อปล่อยหน่วยความจำโดยเร็ว.  
- **Use efficient collections** (เช่น `ArrayList` สำหรับรายการผู้เข้าร่วม) เมื่อจัดการผู้เข้าร่วมจำนวนหลายพันคน.  
- **Cache frequently accessed events** หากคุณสอบถาม PST บ่อย ๆ เพื่อลดการอ่าน/เขียนบนดิสก์.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **PST file not created** | ตรวจสอบสิทธิ์การเขียนในไดเรกทอรีเป้าหมายและให้แน่ใจว่าเส้นทางโฟลเดอร์มีอยู่. |
| **Attendees not receiving invitations** | ยืนยันว่าแต่ละ `MapiRecipient` ใช้ `MapiRecipientType.MAPI_TO` และอีเมลผู้จัดเป็นที่ถูกต้อง. |
| **Date mismatch** | ใช้ `Calendar` อย่างสม่ำเสมอสำหรับวันที่เริ่ม/สิ้นสุด; หลีกเลี่ยงการผสม `java.util.Date` กับไลบรารีวันที่อื่นโดยไม่มีการแปลง. |

## คำถามที่พบบ่อย

**Q: ฉันจะเริ่มต้นกับ Aspose.Email for Java อย่างไร?**  
A: เพิ่มการพึ่งพา Maven ตามที่แสดงข้างต้น, รับไลเซนส์, และทำตามขั้นตอนในคู่มือนี้เพื่อสร้างและส่งออกเหตุการณ์ปฏิทิน.

**Q: ฉันสามารถปรับแต่งชื่อและตำแหน่งของไฟล์ PST ได้หรือไม่?**  
A: ได้, เปลี่ยนตัวแปร `pstFilePath` ใน `createPSTWithCalendarEvents()` ให้เป็นเส้นทางที่ถูกต้องบนระบบของคุณ.

**Q: สามารถเพิ่มรูปแบบการทำซ้ำให้กับการนัดหมายได้หรือไม่?**  
A: แน่นอน – `MapiCalendar` มีคุณสมบัติ `RecurrencePattern` ที่คุณสามารถกำหนดค่าได้ก่อนบันทึก.

**Q: Aspose.Email รองรับรูปแบบปฏิทินอื่น ๆ นอกจาก PST หรือไม่?**  
A: ใช่, คุณสามารถส่งออกเป็น iCalendar (`.ics`) และรูปแบบอื่น ๆ โดยใช้เมธอด API ที่เหมาะสม.

**Q: ขนาดสูงสุดของไฟล์ PST ที่ฉันสามารถสร้างได้คือเท่าไหร่?**  
A: ด้วยรูปแบบ Unicode (`FileFormatVersion.Unicode`), ไฟล์ PST สามารถขยายได้ถึง 2 TB, จำกัดเพียงโดยพื้นที่ดิสก์ที่มีอยู่.

---
**Last Updated:** 2026-08-01  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [เชี่ยวชาญ Aspose.Email for Java: จัดการไฟล์ Outlook PST อย่างมีประสิทธิภาพ](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [เชี่ยวชาญการสร้างและบันทึกรายการปฏิทินด้วย Aspose.Email for Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [วิธีอ่านหลายเหตุการณ์ปฏิทินจากไฟล์ ICS ด้วย Aspose.Email ใน Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}