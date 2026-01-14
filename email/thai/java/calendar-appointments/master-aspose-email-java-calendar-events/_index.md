---
date: '2025-12-24'
description: เรียนรู้วิธีส่งออกปฏิทินเป็น PST ด้วย Aspose.Email สำหรับ Java รวมถึงวิธีเพิ่มผู้เข้าร่วม
  ตั้งค่าวันเริ่มต้นและวันสิ้นสุด และจัดการนัดหมายอย่างมีประสิทธิภาพ.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: ส่งออกปฏิทินเป็นไฟล์ PST ด้วย Aspose.Email สำหรับ Java
url: /th/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email สำหรับ Java

การ **export calendar to PST** อย่างมีประสิทธิภาพเป็นความต้องการทั่วไปเมื่อพัฒนาแอปพลิเคชัน Java ที่ต้องแชร์ข้อมูลการกำหนดเวลาไปยัง Outlook หรือผลิตภัณฑ์ Microsoft อื่น ๆ ในบทเรียนนี้คุณจะได้เห็นวิธีสร้างนัดหมาย, เพิ่มผู้เข้าร่วม, กำหนดวันที่เริ่มและสิ้นสุด, และสุดท้ายบันทึกทุกอย่างลงในไฟล์ PST — ทั้งหมดโดยใช้ Aspose.Email สำหรับ Java.

## คำตอบอย่างรวดเร็ว
- **เป้าหมายหลักคืออะไร?** ส่งออกเหตุการณ์ปฏิทินเป็นไฟล์ PST.  
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Email for Java (v25.4+).  
- **ต้องการใบอนุญาตหรือไม่?** ใช่, ใบอนุญาต Aspose.Email ที่ถูกต้องจะลบข้อจำกัดการประเมินผล.  
- **สามารถเพิ่มผู้เข้าร่วมได้หรือไม่?** แน่นอน – ใช้ `MapiRecipientCollection`.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 16 หรือสูงกว่า.

## อะไรคือ **export calendar to pst**?
การส่งออกปฏิทินเป็น PST หมายถึงการแปลงอ็อบเจ็กต์ `MapiCalendar` ที่อยู่ในหน่วยความจำเป็น Microsoft Outlook Personal Storage Table (PST) ไฟล์นี้สามารถเปิดใน Outlook, แชร์กับเพื่อนร่วมงาน, หรือนำเข้าไปยังระบบอื่นที่รองรับรูปแบบ PST ได้.

## ทำไมต้องใช้ Aspose.Email สำหรับ Java เพื่อส่งออกปฏิทินเป็น PST?
- **Full MAPI support** – สร้าง, แก้ไข, และบันทึกนัดหมายโดยไม่ต้องติดตั้ง Outlook.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS.  
- **Rich API** – จัดการผู้เข้าร่วม, การทำซ้ำ, การแจ้งเตือน, และอื่น ๆ.  
- **Performance‑optimized** – จัดการปริมาณเหตุการณ์จำนวนมากด้วยการใช้หน่วยความจำน้อย.

## ข้อกำหนดเบื้องต้น
- **Libraries & Dependencies**: Aspose.Email for Java version 25.4 หรือใหม่กว่า.  
- **Environment**: JDK 16 หรือสูงกว่า, Maven สำหรับการจัดการการพึ่งพา.  
- **Knowledge**: ความรู้พื้นฐานการเขียนโปรแกรม Java และความคุ้นเคยกับ Maven.

## วิธีตั้งค่า Aspose.Email สำหรับ Java
เพิ่มการพึ่งพา Aspose.Email ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### การรับใบอนุญาต
ปลดล็อกฟังก์ชันเต็มของ Aspose.Email โดยไม่มีข้อจำกัดการประเมินผลโดยการรับใบอนุญาต:

1. **Free Trial**: เยี่ยมชม [Aspose download page](https://releases.aspose.com/email/java/) เพื่อรับใบอนุญาตชั่วคราว.  
2. **Temporary License**: สมัครผ่าน [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: พิจารณาซื้อจาก [Aspose's purchase portal](https://purchase.aspose.com/buy) สำหรับการใช้งานระยะยาว.

เมื่อคุณมีใบอนุญาตแล้ว ให้ทำการเริ่มต้นในแอปพลิเคชันของคุณเพื่อเปิดใช้งานคุณสมบัติทั้งหมด.

## วิธี **create appointment** (Create Calendar Event Java)

### ขั้นตอนที่ 1: กำหนดวันที่เริ่มและสิ้นสุด (java calendar start date / java calendar end date)
เมธอดต่อไปนี้แสดงวิธีตั้งค่าวันที่เริ่มและสิ้นสุดสำหรับนัดหมายและคืนค่าอ็อบเจ็กต์ `MapiCalendar`:

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

*Explanation*: โค้ดส่วนนี้สร้าง `MapiCalendar` ที่มีตำแหน่งที่ตั้ง, หัวเรื่อง, คำอธิบายเฉพาะ, และ **java calendar start date** / **java calendar end date** ที่คุณกำหนด.

## วิธี **add attendees** (how to add attendees)

### ขั้นตอนที่ 2: สร้างรายการผู้เข้าร่วม
ใช้ `MapiRecipientCollection` เพื่อระบุว่าผู้ใดควรได้รับคำเชิญประชุม:

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

*Explanation*: โค้ดนี้สร้างการประชุม, ตั้งค่าองค์กร, และแนบรายการ **how to add attendees** เพื่อให้ทุกคนได้รับคำเชิญที่เหมาะสม.

## วิธี **export calendar to pst** (Create PST with calendar events)

### ขั้นตอนที่ 3: สร้างไฟล์ PST และเพิ่มเหตุการณ์
เมธอดด้านล่างแสดงการสร้างไฟล์ PST แบบ Unicode และจัดเก็บทั้งนัดหมายแบบง่ายและการประชุมที่มีผู้เข้าร่วม:

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

*Explanation*: โค้ดส่วนนี้ **exports calendar to PST** โดยการสร้างคอนเทนเนอร์ PST, เพิ่มโฟลเดอร์ "Calendar" ที่กำหนดไว้ล่วงหน้า, และแทรกอ็อบเจ็กต์ `MapiCalendar` ที่สร้างไว้ก่อนหน้า.

## การประยุกต์ใช้งานจริง
1. **Business Scheduling** – อัตโนมัติการสร้างและแจกจ่ายการประชุมภายใน.  
2. **Event Management** – ติดตามการประชุม, เวิร์กช็อป, และรายการผู้เข้าร่วม.  
3. **CRM Integration** – ซิงค์นัดหมายกับเครื่องมือจัดการความสัมพันธ์ลูกค้า.  
4. **Project Planning** – เก็บมิลสโตนของโครงการเป็นรายการปฏิทิน.  
5. **Remote Team Collaboration** – สร้างไฟล์ PST สำหรับการแชร์แบบออฟไลน์.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Dispose objects** ที่คุณไม่ต้องการใช้แล้วเพื่อคืนหน่วยความจำ.  
- **Choose efficient collections** สำหรับรายการผู้เข้าร่วมขนาดใหญ่.  
- **Cache frequently accessed events** หากคุณต้องสอบถาม PST อย่างต่อเนื่อง.

## ปัญหาทั่วไปและวิธีแก้ไข
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ไฟล์ PST ไม่ถูกสร้าง** | ตรวจสอบสิทธิ์การเขียนในไดเรกทอรีเป้าหมายและให้แน่ใจว่าเส้นทางโฟลเดอร์มีอยู่. |
| **ผู้เข้าร่วมไม่ได้รับคำเชิญ** | ยืนยันว่าแต่ละ `MapiRecipient` ใช้ `MapiRecipientType.MAPI_TO` และอีเมลผู้จัดเป็นที่ถูกต้อง. |
| **วันที่ไม่ตรงกัน** | ใช้ `Calendar` อย่างสม่ำเสมอสำหรับวันที่เริ่ม/สิ้นสุด; หลีกเลี่ยงการผสม `java.util.Date` กับไลบรารีวันที่อื่นโดยไม่มีการแปลง. |

## คำถามที่พบบ่อย

**Q: ฉันจะเริ่มต้นกับ Aspose.Email สำหรับ Java อย่างไร?**  
A: เพิ่มการพึ่งพา Maven ตามที่แสดงด้านบน, รับใบอนุญาต, และทำตามขั้นตอนในคู่มือนี้เพื่อสร้างและส่งออกเหตุการณ์ปฏิทิน.

**Q: สามารถปรับแต่งชื่อไฟล์และตำแหน่งของไฟล์ PST ได้หรือไม่?**  
A: ได้, เปลี่ยนค่าตัวแปร `pstFilePath` ใน `createPSTWithCalendarEvents()` ไปยังเส้นทางที่ต้องการบนระบบของคุณ.

**Q: สามารถเพิ่มรูปแบบการทำซ้ำให้กับนัดหมายได้หรือไม่?**  
A: แน่นอน – `MapiCalendar` เปิดเผยคุณสมบัติการทำซ้ำเช่น `RecurrencePattern` ที่คุณสามารถกำหนดค่าได้ก่อนบันทึก.

**Q: Aspose.Email รองรับรูปแบบปฏิทินอื่นนอกจาก PST หรือไม่?**  
A: ใช่, คุณสามารถส่งออกเป็น iCalendar (`.ics`) และรูปแบบอื่น ๆ โดยใช้เมธอด API ที่เหมาะสม.

**Q: ขนาดสูงสุดของไฟล์ PST ที่สามารถสร้างได้คือเท่าไหร่?**  
A: ด้วยรูปแบบ Unicode (`FileFormatVersion.Unicode`), ไฟล์ PST สามารถขยายได้สูงสุดถึง 2 TB, จำกัดเพียงพื้นที่ดิสก์ที่มี.

**อัปเดตล่าสุด:** 2025-12-24  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}