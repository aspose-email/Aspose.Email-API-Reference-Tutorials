---
date: '2026-05-18'
description: คู่มือขั้นตอนโดยละเอียดเกี่ยวกับวิธีสร้าง calendar item ใน Java ด้วย
  Aspose.Email for Java รวมถึงโค้ดสำหรับบันทึกเป็น .ics, เพิ่มการแจ้งเตือน, และทำงานกับ
  MAPI.
keywords:
- how to create calendar item java
- Aspose.Email Java
- calendar item Java
- ICS format Java
- MAPI calendar Java
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  headline: How to Create Calendar Item Java Using Aspose.Email
  type: TechArticle
- description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  name: How to Create Calendar Item Java Using Aspose.Email
  steps:
  - name: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
    text: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
  - name: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
    text: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
  - name: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
    text: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
  - name: '**Initialize MapiCalendar:**'
    text: '**Initialize MapiCalendar:**'
  - name: '**Set Appointment Details:**'
    text: '**Set Appointment Details:**'
  - name: '**Define Start and End Dates:**'
    text: '**Define Start and End Dates:**'
  - name: '**Add Reminders (Optional):**'
    text: '**Add Reminders (Optional):**'
  - name: '**Save the Appointment:**'
    text: '**Save the Appointment:**'
  type: HowTo
- questions:
  - answer: Yes – set the `Recurrence` property on `MapiCalendar` and define the recurrence
      pattern (daily, weekly, etc.).
    question: Can I generate recurring appointments?
  - answer: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate
      existing calendar data.
    question: Is it possible to read existing .ics files?
  - answer: It does; the library converts UTC to the target zone based on the `TimeZoneInfo`
      object you provide.
    question: Does Aspose.Email support time‑zone conversion automatically?
  - answer: Attach a `MapiReminderAudio` object to the `Reminders` collection and
      specify the path to a .wav file.
    question: How do I add an audio reminder?
  - answer: Up to **2 GB** per file without performance degradation, thanks to streaming
      APIs.
    question: What is the maximum file size Aspose.Email can handle?
  type: FAQPage
title: วิธีสร้าง Calendar Item ใน Java ด้วย Aspose.Email
url: /th/java/calendar-appointments/create-save-calendar-items-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างรายการปฏิทินใน Java ด้วย Aspose.Email

ในแอปพลิเคชันองค์กรสมัยใหม่ การอัตโนมัติการเชิญประชุมและรายการปฏิทินช่วยประหยัดเวลานับไม่ถ้วน บทเรียนนี้แสดง **วิธีสร้างรายการปฏิทินใน Java** ด้วย Aspose.Email ครอบคลุมตั้งแต่การเริ่มต้นอ็อบเจกต์จนถึงการบันทึกการนัดหมายเป็นไฟล์ *.ics* การเพิ่มการเตือนแบบภาพและเสียง และการสกัดสถานะผู้รับจากข้อความ MAPI เมื่อเสร็จสิ้นคุณจะสามารถฝังฟังก์ชันปฏิทินที่เต็มรูปแบบลงในบริการ Java ของคุณได้

## คำตอบด่วน
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Email for Java (v25.4 or later).  
- **ฉันสามารถบันทึกเป็น .ics ได้หรือไม่?** Yes – call `MapiCalendar.save(..., SaveOptions.getIcs())`.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** A valid Aspose.Email license removes evaluation limits.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 + (including Java 11 and 17).  
- **Maven รองรับหรือไม่?** Absolutely – add the Maven dependency to `pom.xml`.

คลาส `SaveOptions` ให้ตัวเลือกการบันทึก; `getIcs()` คืนค่าการตั้งค่าสำหรับรูปแบบ iCalendar.

## วิธีสร้างรายการปฏิทินใน Java?

โหลดคลาส `MapiCalendar` ตั้งค่าคุณสมบัติที่จำเป็น (หัวเรื่อง, สถานที่, เวลาเริ่ม/สิ้นสุด) และเรียก `save` ด้วยรูปแบบ ICS – ทั้งหมดสามารถทำได้ในไม่เกินสิบบรรทัดของโค้ด Aspose.Email จะจัดการการแปลงโซนเวลาและกฎการทำซ้ำโดยอัตโนมัติ เพื่อให้ไฟล์ *.ics* ที่สร้างขึ้นสอดคล้องกับ RFC 5545.

## ทำไมต้องใช้ Aspose.Email สำหรับการจัดการปฏิทิน?

Aspose.Email รองรับรูปแบบอีเมลและปฏิทิน **70+** รูปแบบ, ประมวลผลไฟล์ขนาดถึง **2 GB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, และให้วิธีการ **single‑API** สำหรับมาตรฐาน MAPI และ iCalendar ความสามารถที่วัดได้นี้หมายความว่าคุณสามารถสร้าง, แก้ไข, และอ่านรายการปฏิทินได้อย่างเชื่อถือในระดับใหญ่

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** Version 8 หรือสูงกว่า.  
- **Maven:** สำหรับการจัดการ dependencies.  
- **Aspose.Email for Java:** Version 25.4 or newer (the latest release is recommended).

## การตั้งค่าสภาพแวดล้อม

เพื่อรวม Aspose.Email ในโครงการ Maven ของคุณ ให้เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## การรับใบอนุญาต

Aspose.Email มีใบอนุญาตทดลองใช้ฟรีที่ลบข้อจำกัดการประเมินส่วนใหญ่ สำหรับการใช้งานในผลิตภัณฑ์ ให้ซื้อสมาชิกหรือขอใบอนุญาตชั่วคราวเพื่อการทดสอบ.

## การตั้งค่า Aspose.Email สำหรับ Java

1. **Add Dependency:** ตรวจสอบให้แน่ใจว่า `pom.xml` ของคุณรวม dependency ที่จำเป็นตามที่แสดงข้างต้น.  
2. **Download and Include JAR:** หรือดาวน์โหลดไฟล์ JAR จาก [Aspose Downloads](https://releases.aspose.com/email/java/) แล้วเพิ่มลงใน classpath ของโครงการของคุณ.  
3. **License Setup:** หากคุณมีไฟล์ใบอนุญาต ให้เริ่มต้นใช้งานในโค้ดของคุณเพื่อเปิดใช้งานคุณสมบัติทั้งหมด:

   ```java
   License license = new License();
   license.setLicense("Path_to_Aspose.Email_License_File");
   ```

คลาส `License` โหลดและใช้ไฟล์ใบอนุญาต Aspose.Email ทำให้สามารถใช้คุณสมบัติทั้งหมดได้.

## คู่มือการดำเนินการ

ด้านล่างนี้เราจะอธิบายขั้นตอนหลักที่จำเป็นในการ **สร้างรายการปฏิทินใน Java** เพิ่มการเตือนและบันทึกเป็นไฟล์ *.ics*.

### การสร้างและบันทึกรายการปฏิทิน

#### ภาพรวม
ส่วนนี้แสดงวิธีสร้างการนัดหมายปฏิทินโดยโปรแกรม, แนบการเตือนแบบแสดงผลและเสียง, และบันทึกผลลัพธ์ในรูปแบบ iCalendar สากล.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน

1. **Initialize MapiCalendar:**  
   คลาส `MapiCalendar` แสดงอ็อบเจกต์ปฏิทินในรูปแบบ MAPI ใช้เป็นจุดเริ่มต้นสำหรับการตั้งค่าคุณสมบัติการนัดหมายทั้งหมด.

   ```java
   MapiCalendar appointment = new MapiCalendar();
   ```

2. **Set Appointment Details:**  
   ระบุหัวเรื่องที่ชัดเจน, สถานที่, และเนื้อหาที่อธิบายการประชุม.

   ```java
   appointment.setLocation("LAKE ARGYLE WA 6743");
   appointment.setSubject("Appointment");
   appointment.setBody("This is a very important meeting");
   ```

3. **Define Start and End Dates:**  
   ใช้ `GregorianCalendar` เพื่อระบุเวลาเริ่มและสิ้นสุดที่แม่นยำ พร้อมคำนึงถึงโซนเวลา.

   ```java
   Calendar cal = GregorianCalendar.getInstance();
   cal.set(2016, 10, 2); // Month is zero-based.
   Date startDate = cal.getTime();

   cal.setTime(startDate);
   cal.add(Calendar.DAY_OF_MONTH, 1); // End date is one day later.
   Date endDate = cal.getTime();

   appointment.setStartDate(startDate);
   appointment.setEndDate(endDate);
   ```

4. **Add Reminders (Optional):**  
   คุณสามารถแนบการเตือนแบบภาพ (pop‑up) และการเตือนแบบเสียง (ไฟล์ wav) เพื่อเพิ่มการแจ้งเตือนให้ผู้เข้าร่วม.  
   *เคล็ดลับ:* ตั้งค่า `ReminderMinutesBeforeStart` เป็น `15` เพื่อแจ้งเตือนล่วงหน้า 15 นาที.  
   คลาส `MapiReminderAudio` แสดงการเตือนแบบเสียงที่แนบกับรายการปฏิทิน.

5. **Save the Appointment:**  
   บันทึกรายการปฏิทินเป็นไฟล์ *.ics* ไปยังโฟลเดอร์ผลลัพธ์ที่ต้องการ.

   ```java
   String dataDir = "YOUR_OUTPUT_DIRECTORY/";
   appointment.save(dataDir + "CalendarItem_out.ics\
   ```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **Time‑zone mismatches:** ควรระบุโซนเวลาเสมอเมื่อตั้งค่า `StartDate` และ `EndDate` เพื่อหลีกเลี่ยงข้อผิดพลาดจากการเปลี่ยนแปลงเวลาแสงอาทิตย์.  
- **Large attendee lists:** สำหรับการประชุมที่มีผู้เข้าร่วมมากกว่า 200 ราย, ใช้การจัดกลุ่ม `MapiRecipientCollection` เพื่อให้อยู่ในขีดจำกัดหน่วยความจำ.  
  คลาส `MapiRecipientCollection` เก็บรายการผู้เข้าร่วมประชุม.  
- **Missing license:** หากไฟล์ใบอนุญาตไม่ถูกโหลด, API จะกลับไปใช้โหมดทดลองที่จำกัดจำนวนรายการที่บันทึกได้ที่ **10** รายการต่อการทำงานหนึ่งครั้ง.

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างการนัดหมายที่ทำซ้ำได้หรือไม่?**  
A: ใช่ – ตั้งค่า property `Recurrence` บน `MapiCalendar` และกำหนดรูปแบบการทำซ้ำ (รายวัน, รายสัปดาห์, ฯลฯ).

**Q: สามารถอ่านไฟล์ .ics ที่มีอยู่ได้หรือไม่?**  
A: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate existing calendar data.

**Q: Aspose.Email รองรับการแปลงโซนเวลาโดยอัตโนมัติหรือไม่?**  
A: It does; the library converts UTC to the target zone based on the `TimeZoneInfo` object you provide.

**Q: จะเพิ่มการเตือนแบบเสียงได้อย่างไร?**  
A: Attach a `MapiReminderAudio` object to the `Reminders` collection and specify the path to a .wav file.

**Q: ขนาดไฟล์สูงสุดที่ Aspose.Email สามารถจัดการได้คือเท่าไหร่?**  
A: Up to **2 GB** per file without performance degradation, thanks to streaming APIs.

---

**Last Updated:** 2026-05-18  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [จัดการการแชร์ปฏิทิน - คู่มือ Aspose.Email สำหรับ Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [วิธีสกัดรายการปฏิทิน Outlook ไปยัง ICS ด้วย Aspose.Email สำหรับ Java](/email/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/)
- [วิธีอ่านหลายเหตุการณ์ปฏิทินจากไฟล์ ICS ด้วย Aspose.Email ใน Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}