---
date: '2026-03-20'
description: เรียนรู้วิธีสร้างปฏิทิน Outlook ด้วย Java พร้อมการทำซ้ำรายวันและข้อยกเว้น
  และบันทึกปฏิทินเป็นไฟล์ PST โดยใช้ Aspose.Email สำหรับ Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: สร้างปฏิทิน Outlook ด้วย Java พร้อมการทำซ้ำรายวันและข้อยกเว้น
url: /th/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้าง outlook calendar java พร้อมการทำซ้ำรายวันและข้อยกเว้น

การจัดการเหตุการณ์ที่ทำซ้ำอย่างมีประสิทธิภาพอาจเป็นเรื่องท้าทาย โดยเฉพาะเมื่อคุณต้องการ **outlook calendar java** ที่รองรับรูปแบบการทำซ้ำรายวันและข้อยกเว้นเป็นครั้งคราว ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้าง Outlook calendar Java objects, ตั้งค่าการทำซ้ำรายวัน, เพิ่มอินสแตนซ์ข้อยกเว้น, และสุดท้าย **save calendar to PST** ด้วย Aspose.Email for Java เมื่อจบคุณจะมีโค้ดสแนปช็อตที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในบริการกำหนดเวลาที่ใช้ Java ใดก็ได้

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใด?** Aspose.Email for Java  
- **งานหลัก?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **JDK ที่ต้องการ?** Java 16 หรือสูงกว่า  
- **สามารถแนบไฟล์ไปยังข้อยกเว้นได้หรือไม่?** Yes, using `MapiCalendarExceptionInfo`  
- **ปฏิทินถูกเก็บไว้ที่ไหน?** In a PST file via `PersonalStorage`

## Outlook calendar java คืออะไร?
Outlook calendar Java object (ที่ทำงานเป็น MAPI calendar) ปฏิบัติตามมาตรฐานเดียวกับการนัดหมายของ Microsoft Outlook มันเก็บกฎการทำซ้ำที่ซับซ้อน, การจัดการข้อยกเว้น, ผู้เข้าร่วม, และไฟล์แนบ ทำให้เหมาะสำหรับการกำหนดเวลาระดับองค์กร

## ทำไมต้องใช้ Aspose.Email for Java?
Aspose.Email ให้ API แบบ pure‑Java ที่ทำให้คุณทำงานกับวัตถุ MAPI ได้โดยไม่ต้องติดตั้ง Outlook วิธีการ **aspose email tutorial java** นี้ช่วยให้คุณสร้างไฟล์ PST ฝั่งเซิร์ฟเวอร์, สร้างชุดการประชุมอัตโนมัติ, และควบคุมตรรกะการทำซ้ำได้อย่างเต็มที่

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม โปรดตรวจสอบว่าคุณได้ตั้งค่าต่อไปนี้แล้ว:
- **Aspose.Email Library**: เวอร์ชัน 25.4 (หรือใหม่กว่า) – สามารถดาวน์โหลดผ่าน Maven หรือดาวน์โหลดโดยตรง  
- **Java Development Kit (JDK)**: JDK 16 หรือใหม่กว่า  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans หรือเครื่องมือแก้ไข Java ใดก็ได้

### ไลบรารีและการพึ่งพาที่จำเป็น

เพื่อรวม Aspose.Email เข้าในโปรเจกต์ด้วย Maven ให้เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

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
- **Free Trial** – ทดลองใช้ทุกฟีเจอร์โดยไม่มีค่าใช้จ่าย  
- **Temporary License** – ขอรับเพื่อการประเมินผลระยะยาว  
- **Full License** – ซื้อเพื่อใช้งานในสภาพแวดล้อมการผลิต

## การตั้งค่า Aspose.Email for Java

ขั้นแรก ตั้งค่าสภาพแวดล้อมของคุณ:

1. ตรวจสอบว่า JDK 16 ถูกติดตั้งและตั้งค่า `JAVA_HOME` แล้ว  
2. เพิ่ม dependency ของ Maven (หรือดาวน์โหลด JAR) ลงในโปรเจกต์ของคุณ  

ต่อไปนี้คือตัวอย่างโค้ดสั้น ๆ ที่แสดงวิธีโหลดไฟล์ใบอนุญาต:

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

## คู่มือการทำงาน

### การสร้าง outlook calendar java พร้อมการทำซ้ำรายวันและข้อยกเว้น

#### ภาพรวม
ฟีเจอร์นี้ช่วยให้คุณอัตโนมัติการนัดหมายที่ทำซ้ำได้พร้อมยังคงสามารถข้ามหรือแก้ไขอินสแตนซ์เฉพาะได้

#### การดำเนินการตามขั้นตอน

**1. ตั้งค่าวันเริ่มต้นของเหตุการณ์**  
กำหนดว่าชุดนัดหมายควรเริ่มเมื่อใด:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. สร้างวัตถุ MAPI Calendar**  
ระบุสถานที่, หัวเรื่อง, และคำอธิบาย:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. นิยามรูปแบบการทำซ้ำรายวัน**  
กำหนดให้เหตุการณ์ทำซ้ำทุกวัน:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. เพิ่มข้อยกเว้นให้กับการทำซ้ำ**  
ระบุวันที่ที่ต้องการยกเว้น (หรือแก้ไข):

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
คุณสามารถแนบเอกสารสนับสนุน (เช่น ระเบียบวาระ) ไปยังอินสแตนซ์ข้อยกเว้นใดก็ได้

**1. สร้างและแนบไฟล์**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### การบันทึก outlook calendar java ไปยัง PST (save calendar to pst)

#### ภาพรวม
บันทึกปฏิทินลงในไฟล์ PST เพื่อให้ Outlook หรือไคลเอนต์อื่น ๆ สามารถอ่านได้

**1. สร้างและบันทึกปฏิทินไปยัง PST**

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
- **Corporate Scheduling** – อัตโนมัติชุดการประชุมโดยข้ามวันหยุดอัตโนมัติ  
- **Project Management** – ติดตามมิลสโตนที่ทำซ้ำพร้อมการเปลี่ยนแปลงวันที่เป็นครั้งคราว  
- **Event Planning** – จัดการการประชุมหลายวันที่บางเซสชันอาจถูกยกเลิกหรือเลื่อนเวลา

### ความเป็นไปได้ในการรวมระบบ
ผสาน Aspose.Email กับแพลตฟอร์ม CRM, API การจัดการงาน, หรือเอนจินเวิร์กโฟลว์แบบกำหนดเองเพื่อขับเคลื่อนการอัตโนมัติแบบครบวงจร

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Dispose Resources** – เรียก `dispose()` บน `PersonalStorage` เสมอเพื่อปล่อยตัวจัดการไฟล์  
- **Stream Usage** – ใช้ `ByteArrayOutputStream` หรือสตรีมไฟล์เพื่อหลีกเลี่ยงการโหลด PST ทั้งไฟล์เข้าหน่วยความจำ  
- **Async Operations** – สำหรับการสร้างปฏิทินจำนวนมาก ให้รันโลจิกการสร้างบนเธรดพื้นหลังเพื่อให้ UI ตอบสนองได้ดี

## สรุป
โดยทำตามคู่มือนี้คุณจะรู้วิธี **create outlook calendar java** พร้อมการทำซ้ำรายวัน, เพิ่มข้อยกเว้น, แนบไฟล์, และ **save calendar to PST** ความสามารถเหล่านี้ช่วยให้คุณสร้างฟีเจอร์การกำหนดเวลาที่แข็งแกร่งโดยไม่ต้องใช้ Outlook โดยตรง

### ขั้นตอนต่อไป
- ทดลองใช้รูปแบบการทำซ้ำรายสัปดาห์หรือรายเดือน  
- สำรวจคุณสมบัติเพิ่มเติมของ MAPI เช่น ผู้เข้าร่วม, การแจ้งเตือน, และประเภท  
- ตรวจสอบเอกสาร API ของ Aspose.Email สำหรับสถานการณ์ขั้นสูงเพิ่มเติม

## คำถามที่พบบ่อย

**Q: ไลบรารีรองรับการนัดหมายที่รับรู้โซนเวลาไหม?**  
A: ใช่, คุณสามารถตั้งค่า `StartTimeZone` และ `EndTimeZone` บน `MapiCalendar`

**Q: สามารถลบอินสแตนซ์เดียวจากชุดการทำซ้ำได้หรือไม่?**  
A: ใช้คอลเลกชัน `DeletedInstanceDates` ของรูปแบบการทำซ้ำเพื่อระบุวันที่ที่ต้องการลบ

**Q: มีขีดจำกัดขนาดไฟล์ PST ที่สร้างด้วย Aspose.Email หรือไม่?**  
A: ไฟล์ PST ตามรูปแบบ Unicode มีขีดจำกัดสูงสุดที่ 2 GB โดยค่าเริ่มต้น แต่คุณสามารถกำหนดขนาดใหญ่กว่าได้ผ่านการตั้งค่า `PersonalStorage`

**Q: วิธีเพิ่มผู้เข้าร่วมในคำขอประชุมคืออะไร?**  
A: สร้างวัตถุ `MapiRecipient`, ตั้งค่า `RecipientType` เป็น `MapiRecipientType.MAPI_TO`, แล้วเพิ่มลงในคอลเลกชัน `Recipients` ของ `MapiMessage`

**Q: รองรับงานที่ทำซ้ำ (task) ไม่ใช่แค่การนัดหมายหรือไม่?**  
A: ใช่, Aspose.Email ยังมี `MapiTask` ที่ให้ความสามารถการทำซ้ำเช่นเดียวกัน

**Q: สามารถใช้คู่มือนี้เป็นส่วนหนึ่งของชุดบทเรียน aspose email tutorial java ได้หรือไม่?**  
A: แน่นอน – ขั้นตอนที่แสดงในที่นี้เป็นส่วนสำคัญของบทเรียน Aspose.Email Java ใด ๆ ที่เกี่ยวกับการสร้างปฏิทิน

## แหล่งข้อมูล
- [เอกสาร Aspose.Email สำหรับ Java](https://reference.aspose.com/email/java/)
- [ดาวน์โหลด Aspose.Email](https://releases.aspose.com/email/java/)
- [ซื้อใบอนุญาต](https://purchase.aspose.com/buy)
- [เวอร์ชันทดลองฟรี](https://releases.aspose.com/email/java/)
- [ขอใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)
- [ฟอรั่มสนับสนุนของ Aspose](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}