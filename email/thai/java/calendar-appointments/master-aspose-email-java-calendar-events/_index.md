---
date: '2026-02-24'
description: เรียนรู้วิธีส่งออกปฏิทินเป็นไฟล์ PST ด้วย Aspose.Email สำหรับ Java รวมถึงวิธีเพิ่มผู้เข้าร่วม
  ตั้งค่าวันเริ่มต้นและวันสิ้นสุด และจัดการนัดหมายอย่างมีประสิทธิภาพ
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email สำหรับ Java
url: /th/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

 placeholders remain. Ensure no extra spaces.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออกปฏิทินเป็น PST ด้วย Aspose.Email สำหรับ Java

หากคุณกำลังสร้างแอปพลิเคชัน Java ที่ต้องการแชร์ข้อมูลการกำหนดเวลากับ Outlook คุณมักจะต้อง **export calendar to PST**. ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่คุณต้องการ—ตั้งแต่การสร้างการนัดหมายง่าย ๆ การเพิ่มผู้เข้าร่วมประชุม และสุดท้ายการบันทึกเหตุการณ์ลงในไฟล์ PST ทั้งหมดด้วย Aspose.Email for Java.

## คำตอบอย่างรวดเร็ว
- **เป้าหมายหลักคืออะไร?** ส่งออกเหตุการณ์ปฏิทินเป็นไฟล์ PST.  
- **ไลบรารีที่ต้องใช้คืออะไร?** Aspose.Email for Java (v25.4+).  
- **ฉันต้องการไลเซนส์หรือไม่?** ใช่, ไลเซนส์ Aspose.Email ที่ถูกต้องจะลบข้อจำกัดการประเมินผล.  
- **ฉันสามารถเพิ่มผู้เข้าร่วมได้หรือไม่?** แน่นอน – ใช้ `MapiRecipientCollection`.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 16 หรือสูงกว่า.

## **export calendar to pst** คืออะไร
การส่งออกปฏิทินเป็น PST หมายถึงการแปลงอ็อบเจกต์ `MapiCalendar` ที่อยู่ในหน่วยความจำเป็น Microsoft Outlook Personal Storage Table (PST). ไฟล์ที่ได้สามารถเปิดโดยตรงใน Outlook, แชร์กับเพื่อนร่วมงาน, หรือนำเข้าไปยังระบบใด ๆ ที่รองรับรูปแบบ PST.

## ทำไมต้องใช้ Aspose.Email for Java เพื่อส่งออกปฏิทินเป็น PST?
- **Full MAPI support** – สร้าง, แก้ไข, และบันทึกการนัดหมายโดยไม่ต้องติดตั้ง Outlook.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS.  
- **Rich API** – จัดการผู้เข้าร่วม, การทำซ้ำ, การแจ้งเตือน, และอื่น ๆ.  
- **Performance‑optimized** – จัดการปริมาณเหตุการณ์จำนวนมากด้วยการใช้หน่วยความจำน้อย.

## ข้อกำหนดเบื้องต้น
- **Libraries & Dependencies**: Aspose.Email for Java version 25.4 หรือใหม่กว่า.  
- **Environment**: JDK 16 หรือสูงกว่า, Maven สำหรับการจัดการ dependencies.  
- **Knowledge**: ความรู้พื้นฐานการเขียนโปรแกรม Java และความคุ้นเคยกับ Maven.

## วิธีตั้งค่า Aspose.Email for Java
เพิ่ม dependency ของ Aspose.Email ลงใน `pom.xml` ของคุณ:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์
Unlock full functionality of Aspose.Email without evaluation limitations by acquiring a license:

1. **Free Trial**: ไปที่ [Aspose download page](https://releases.aspose.com/email/java/) เพื่อรับไลเซนส์ชั่วคราว.  
2. **Temporary License**: สมัครผ่าน [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: พิจารณาซื้อจาก [Aspose's purchase portal](https://purchase.aspose.com/buy) สำหรับการใช้งานระยะยาว.

เมื่อคุณมีไลเซนส์แล้ว ให้ทำการเริ่มต้นในแอปพลิเคชันของคุณเพื่อเปิดใช้งานฟีเจอร์ทั้งหมด.

## วิธี **create appointment** (Create Calendar Event Java)

### ขั้นตอนที่ 1: กำหนดวันที่เริ่มต้นและสิ้นสุด (java calendar start date / java calendar end date)
เมธอดต่อไปนี้แสดงวิธีตั้งค่าวันที่เริ่มต้นและสิ้นสุดสำหรับการนัดหมายและคืนค่าอ็อบเจกต์ `MapiCalendar`:

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

*Explanation*: โค้ดส่วนนี้สร้าง `MapiCalendar` พร้อมตำแหน่งที่ตั้ง, หัวเรื่อง, คำอธิบาย, และ **java calendar start date** / **java calendar end date** ที่คุณกำหนด.

## วิธี **add attendees** (java add meeting attendees)

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

*Explanation*: โค้ดนี้สร้างการประชุม, ตั้งค่า organizer, และแนบรายการ **java add meeting attendees** เพื่อให้ทุกคนได้รับคำเชิญที่เหมาะสม.

## วิธี **export calendar to pst** (Create PST with calendar events)

### ขั้นตอนที่ 3: สร้างไฟล์ PST และเพิ่มเหตุการณ์
เมธอดด้านล่างแสดงการสร้างไฟล์ PST แบบ Unicode และเก็บทั้งการนัดหมายแบบง่ายและการประชุมที่มีผู้เข้าร่วม:

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

*Explanation*: โค้ดส่วนนี้ **exports calendar to PST** โดยสร้างคอนเทนเนอร์ PST, เพิ่มโฟลเดอร์ "Calendar" ที่กำหนดไว้ล่วงหน้า, และแทรกอ็อบเจกต์ `MapiCalendar` ที่สร้างไว้ก่อนหน้านี้.

## การประยุกต์ใช้ในทางปฏิบัติ
1. **Business Scheduling** – อัตโนมัติการสร้างและแจกจ่ายการประชุมภายใน.  
2. **Event Management** – ติดตามการประชุม, เวิร์กช็อป, และรายการผู้เข้าร่วม.  
3. **CRM Integration** – ซิงค์การนัดหมายกับเครื่องมือ CRM.  
4. **Project Planning** – เก็บ milestones ของโครงการเป็นรายการปฏิทิน.  
5. **Remote Team Collaboration** – สร้างไฟล์ PST เพื่อแชร์แบบออฟไลน์.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Dispose objects** ที่คุณไม่ต้องการใช้แล้วเพื่อคืนหน่วยความจำ.  
- **Choose efficient collections** สำหรับรายการผู้เข้าร่วมขนาดใหญ่.  
- **Cache frequently accessed events** หากคุณเรียกดู PST อย่างต่อเนื่อง.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **PST file not created** | ตรวจสอบสิทธิ์การเขียนในไดเรกทอรีเป้าหมายและยืนยันว่าเส้นทางโฟลเดอร์มีอยู่. |
| **Attendees not receiving invitations** | ยืนยันว่าแต่ละ `MapiRecipient` ใช้ `MapiRecipientType.MAPI_TO` และอีเมลผู้จัดเป็นค่าที่ถูกต้อง. |
| **Date mismatch** | ใช้ `Calendar` อย่างสม่ำเสมอสำหรับวันที่เริ่มต้น/สิ้นสุด; หลีกเลี่ยงการผสม `java.util.Date` กับไลบรารีวันที่อื่นโดยไม่มีการแปลง. |

## คำถามที่พบบ่อย

**Q: ฉันจะเริ่มต้นกับ Aspose.Email for Java อย่างไร?**  
A: เพิ่ม dependency ของ Maven ตามที่แสดงด้านบน, รับไลเซนส์, และทำตามขั้นตอนในคู่มือนี้เพื่อสร้างและส่งออกเหตุการณ์ปฏิทิน.

**Q: ฉันสามารถปรับแต่งชื่อและตำแหน่งของไฟล์ PST ได้หรือไม่?**  
A: ใช่, เปลี่ยนตัวแปร `pstFilePath` ใน `createPSTWithCalendarEvents()` ให้เป็นเส้นทางที่ถูกต้องบนระบบของคุณ.

**Q: สามารถเพิ่มรูปแบบการทำซ้ำให้กับการนัดหมายได้หรือไม่?**  
A: แน่นอน – `MapiCalendar` มีคุณสมบัติการทำซ้ำเช่น `RecurrencePattern` ที่คุณสามารถกำหนดค่าได้ก่อนบันทึก.

**Q: Aspose.Email รองรับรูปแบบปฏิทินอื่น ๆ นอกจาก PST หรือไม่?**  
A: ใช่, คุณสามารถส่งออกเป็น iCalendar (`.ics`) และรูปแบบอื่น ๆ โดยใช้เมธอด API ที่เหมาะสม.

**Q: ขนาดสูงสุดของไฟล์ PST ที่ฉันสามารถสร้างได้คือเท่าไหร่?**  
A: ด้วยรูปแบบ Unicode (`FileFormatVersion.Unicode`), ไฟล์ PST สามารถขยายได้สูงสุดถึง 2 TB, จำกัดโดยพื้นที่ดิสก์ที่มีอยู่เท่านั้น.

---

**อัปเดตล่าสุด:** 2026-02-24  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}