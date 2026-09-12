---
date: 2026-09-12
description: เรียนรู้วิธีสร้างไฟล์ ics ด้วย Java โดยใช้ Aspose.Email, สร้างเหตุการณ์ปฏิทินด้วย
  Java, และส่งออกการนัดหมาย iCalendar พร้อมตัวอย่างโค้ดเต็มรูปแบบ
keywords:
- generate ics file java
- create calendar event java
- Aspose.Email Java
- iCalendar generation Java
lastmod: 2026-09-12
og_description: สร้างไฟล์ ics ด้วย Java ด้วย Aspose.Email. บทเรียนนี้แสดงวิธีสร้างเหตุการณ์ปฏิทินด้วย
  Java, กำหนดการทำซ้ำ, และส่งออกไฟล์ iCalendar ที่ทำงานร่วมกับ Outlook, Google Calendar,
  และ Apple Calendar.
og_image_alt: 'Aspose.Email Java tutorial: generate ics file and calendar event'
og_title: สร้างไฟล์ ics ด้วย Java ด้วย Aspose.Email – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to generate ics file java using Aspose.Email, create calendar
    event java, and export iCalendar appointments with full code examples.
  headline: Generate ics file java – email calendar and appointments with Aspose.Email
  type: TechArticle
- description: Learn how to generate ics file java using Aspose.Email, create calendar
    event java, and export iCalendar appointments with full code examples.
  name: Generate ics file java – email calendar and appointments with Aspose.Email
  steps:
  - name: Set up the project and add the Aspose.Email JAR
    text: Create a Maven or Gradle project and include the Aspose.Email dependency.
      This gives you access to the `MailMessage`, `MapiMessage`, and `Appointment`
      classes needed for calendar handling.
  - name: Create a new `Appointment` object
    text: '`Appointment` is Aspose.Email''s core class that represents a calendar
      event and holds all event properties such as subject, location, and attendees.
      Instantiate `Appointment` and fill in the essential fields such as subject,
      location, start/end times, and attendees. This object represents the calend'
  - name: Define recurrence or exceptions (optional)
    text: '`RecurrencePattern` defines how an appointment repeats over time, supporting
      daily, weekly, monthly, and custom patterns. If the meeting repeats, use the
      `RecurrencePattern` class to specify daily, weekly, or custom patterns. You
      can also add exception dates to skip specific occurrences.'
  - name: Save the appointment as an .ics file
    text: Call `appointment.save("MyMeeting.ics", AppointmentSaveFormat.Ics)` to write
      the iCalendar data to disk. The file can now be attached to an email or uploaded
      to a server.
  - name: (optional) Send the invitation via email
    text: '`MailMessage` represents an email message that can contain attachments,
      body, and recipients. `SmtpClient` is the class used to send email messages
      through an SMTP server. Wrap the saved .ics file in a `MailMessage` and use
      `SmtpClient` to deliver it to recipients. This step demonstrates the full wo'
  type: HowTo
- questions:
  - answer: Yes. Aspose.Email creates iCalendar files locally, so no server connection
      is required.
    question: Can I generate an .ics file without an Exchange server?
  - answer: Use `appointment.getReminder().setMinutesBeforeStart(15);` to set a 15‑minute
      reminder.
    question: How do I add a reminder to the event?
  - answer: Absolutely. Call `appointment.getCustomFields().add("X‑MyProperty", "MyValue");`
      to add non‑standard iCal fields.
    question: Is it possible to embed custom properties?
  - answer: Any recent version that supports `AppointmentSaveFormat.Ics`; we tested
      with the latest release.
    question: What version of Aspose.Email is required?
  - answer: Yes. Load the Outlook item with `MapiMessage.fromFile("appointment.msg")`
      and then call `appointment.save(..., AppointmentSaveFormat.Ics)`.
    question: Can I convert existing Outlook appointments to .ics?
  type: FAQPage
tags:
- generate ics
- Aspose.Email
- Java calendar events
- iCalendar
title: สร้างไฟล์ ics ด้วย Java – ปฏิทินอีเมลและการนัดหมายด้วย Aspose.Email
url: /th/java/calendar-appointments/
weight: 5
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ ics ด้วย Java – ปฏิทินอีเมลและนัดหมายด้วย Aspose.Email

ในบทแนะนำนี้คุณจะได้ค้นพบวิธีการ **generate ics file java** ด้วย Aspose.Email ไม่ว่าคุณจะสร้างตัวจัดตารางการประชุม, ผสานรวมกับ Microsoft Exchange, หรือเพียงต้องการส่งออกข้อมูลปฏิทิน เราจะพาคุณผ่านกระบวนการทั้งหมด—ตั้งแต่การสร้างอ็อบเจ็กต์เหตุการณ์จนถึงการบันทึกไฟล์ .ics ที่เป็นไปตามมาตรฐาน คุณยังจะได้เห็นวิธี **create calendar event java** ที่สามารถส่ง, เก็บ, หรือนำเข้าไปยังไคลเอนต์ปฏิทินใดก็ได้

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Email for Java
- **ฉันสามารถสร้างไฟล์ .ics ได้โดยไม่ต้องใช้ลิขสิทธิ์หรือไม่?** ใบอนุญาตชั่วคราวทำงานสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง
- **ฟอร์แมตใดที่ API ส่งออก?** ไฟล์ iCalendar (.ics) มาตรฐานที่เข้ากันได้กับ Outlook, Google Calendar ฯลฯ
- **ฉันต้องการเซิร์ฟเวอร์ Exchange หรือไม่?** ไม่จำเป็น, API สามารถสร้างไฟล์ได้โดยทำงานในเครื่องโดยไม่ต้องเชื่อมต่อกับเซิร์ฟเวอร์
- **การทำซ้ำได้รับการสนับสนุนหรือไม่?** ใช่, คุณสามารถกำหนดรูปแบบการทำซ้ำรายวัน, รายสัปดาห์ หรือแบบกำหนดเองได้

## “generate ics file java” คืออะไร?
การสร้างไฟล์ .ics ใน Java หมายถึงการสร้างตัวแทน iCalendar ของการประชุมหรือการนัดหมายโดยอัตโนมัติ รวมถึงรายละเอียดเช่น หัวเรื่อง, สถานที่, เวลา, ผู้เข้าร่วม, และการแจ้งเตือน ไฟล์นี้สอดคล้องกับสเปค RFC 5545 ทำให้แอปพลิเคชันปฏิทินใดก็ได้—Outlook, Google Calendar, Apple Calendar หรืออื่น ๆ—สามารถอ่าน, แสดงผล, และประมวลผลเหตุการณ์ได้อย่างถูกต้อง

## ทำไมต้องสร้างไฟล์ iCalendar ด้วย Aspose.Email?
คุณควรสร้างไฟล์ iCalendar ด้วย Aspose.Email เพราะไลบรารีนี้จัดการสเปค RFC 5545 อย่างครบถ้วน รองรับคุณสมบัติที่เกี่ยวกับปฏิทินมากกว่า **50** รายการ และทำงานบนแพลตฟอร์ม Java ใดก็ได้โดยไม่ต้องพึ่งพาไลบรารีภายนอก มันรับประกันว่าไฟล์ .ics จะเปิดได้อย่างถูกต้องใน Outlook, Google Calendar, Apple Calendar และไคลเอนต์อื่น ๆ พร้อมให้คุณควบคุมผู้เข้าร่วม, การแจ้งเตือน, และการทำซ้ำได้อย่างละเอียด

## ข้อกำหนดเบื้องต้น
- Java 8 หรือสูงกว่า  
- Aspose.Email for Java (ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ)  
- ใบอนุญาตชั่วคราวหรือเต็มที่ถูกต้องสำหรับ Aspose.Email  

## วิธีสร้าง calendar event java ด้วย Aspose.Email?
โหลดโปรเจกต์ Java ของคุณ, สร้างอ็อบเจ็กต์ `Appointment`, ตั้งค่ารายละเอียด, แล้วบันทึกเป็นไฟล์ .ics — ทั้งหมดในไม่กี่บรรทัด โค้ด `Appointment` จะบรรจุข้อมูลเหตุการณ์ทั้งหมด เช่น หัวเรื่อง, สถานที่, เวลาเริ่ม/สิ้นสุด, ผู้เข้าร่วม, และรูปแบบการทำซ้ำ หลังจากกำหนดคุณสมบัติที่ต้องการแล้ว ให้เรียก `save` พร้อม `AppointmentSaveFormat.Ics` เพื่อสร้างไฟล์ที่เป็นมาตรฐานซึ่งไคลเอนต์ปฏิทินใดก็สามารถนำเข้าได้

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์และเพิ่ม JAR ของ Aspose.Email
สร้างโปรเจกต์ Maven หรือ Gradle แล้วเพิ่มการอ้างอิง Aspose.Email นี้จะทำให้คุณเข้าถึงคลาส `MailMessage`, `MapiMessage`, และ `Appointment` ที่จำเป็นสำหรับการจัดการปฏิทิน

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ `Appointment` ใหม่
`Appointment` เป็นคลาสหลักของ Aspose.Email ที่แทนเหตุการณ์ปฏิทินและเก็บคุณสมบัติต่าง ๆ เช่น หัวเรื่อง, สถานที่, และผู้เข้าร่วม สร้างอินสแตนซ์ `Appointment` แล้วกรอกฟิลด์สำคัญ เช่น หัวเรื่อง, สถานที่, เวลาเริ่ม/สิ้นสุด, และผู้เข้าร่วม ซึ่งอ็อบเจ็กต์นี้คือตัวแทนของเหตุการณ์ที่คุณต้องการส่งออก

### ขั้นตอนที่ 3: กำหนดการทำซ้ำหรือข้อยกเว้น (ไม่บังคับ)
`RecurrencePattern` กำหนดว่าการนัดหมายจะทำซ้ำอย่างไร รองรับรูปแบบรายวัน, รายสัปดาห์, รายเดือน, และแบบกำหนดเอง หากการประชุมต้องทำซ้ำ ให้ใช้คลาส `RecurrencePattern` เพื่อระบุรูปแบบที่ต้องการ คุณยังสามารถเพิ่มวันที่ยกเว้นเพื่อข้ามการเกิดเหตุบางครั้งได้

### ขั้นตอนที่ 4: บันทึกการนัดหมายเป็นไฟล์ .ics
เรียก `appointment.save("MyMeeting.ics", AppointmentSaveFormat.Ics)` เพื่อเขียนข้อมูล iCalendar ลงดิสก์ ไฟล์นี้สามารถแนบไปกับอีเมลหรืออัปโหลดไปยังเซิร์ฟเวอร์ได้ทันที

### ขั้นตอนที่ 5: (ไม่บังคับ) ส่งคำเชิญทางอีเมล
`MailMessage` แทนข้อความอีเมลที่สามารถมีไฟล์แนบ, เนื้อหา, และผู้รับ `SmtpClient` เป็นคลาสที่ใช้ส่งอีเมลผ่านเซิร์ฟเวอร์ SMTP ห่อไฟล์ .ics ที่บันทึกไว้ใน `MailMessage` แล้วใช้ `SmtpClient` ส่งไปยังผู้รับ ขั้นตอนนี้แสดงการทำงานเต็มรูปแบบตั้งแต่การสร้างเหตุการณ์จนถึงการกระจาย

## ปัญหาทั่วไปและวิธีแก้
- **Time‑zone mismatches** – ตรวจสอบให้แน่ใจว่า `TimeZoneInfo` ของการนัดหมายตรงกับโซนที่ต้องการ; มิฉะนั้นผู้รับอาจเห็นเวลาไม่ถูกต้อง  
- **Missing attendees** – เพิ่มผู้เข้าร่วมแต่ละคนโดยใช้ `appointment.getAttendees().add(new MailAddress("user@example.com"));`  
- **File not opening in Outlook** – ยืนยันว่าไฟล์มีนามสกุล `.ics` และเนื้อหาตรงตาม RFC 5545 (Aspose.Email จะจัดการให้โดยอัตโนมัติ)  

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างไฟล์ .ics ได้โดยไม่ต้องใช้เซิร์ฟเวอร์ Exchange หรือไม่?**  
A: ได้. Aspose.Email สร้างไฟล์ iCalendar ในเครื่องโดยไม่ต้องเชื่อมต่อกับเซิร์ฟเวอร์

**Q: วิธีเพิ่มการแจ้งเตือนให้กับเหตุการณ์คืออะไร?**  
A: ใช้ `appointment.getReminder().setMinutesBeforeStart(15);` เพื่อกำหนดการแจ้งเตือนล่วงหน้า 15 นาที

**Q: สามารถฝังคุณสมบัติที่กำหนดเองได้หรือไม่?**  
A: แน่นอน. เรียก `appointment.getCustomFields().add("X‑MyProperty", "MyValue");` เพื่อเพิ่มฟิลด์ iCal ที่ไม่เป็นมาตรฐาน

**Q: ต้องใช้เวอร์ชันใดของ Aspose.Email?**  
A: เวอร์ชันล่าสุดที่รองรับ `AppointmentSaveFormat.Ics` ใดก็ได้; เราได้ทดสอบกับรุ่นล่าสุด

**Q: สามารถแปลงการนัดหมาย Outlook ที่มีอยู่เป็น .ics ได้หรือไม่?**  
A: ได้. โหลดรายการ Outlook ด้วย `MapiMessage.fromFile("appointment.msg")` แล้วเรียก `appointment.save(..., AppointmentSaveFormat.Ics)`

## แหล่งข้อมูลเพิ่มเติม
- [สร้างและส่งคำเชิญปฏิทินด้วย Aspose.Email สำหรับ Java: คู่มือแบบขั้นตอน](./create-send-calendar-invitations-aspose-email-java/)
- [สร้างและบันทึกปฏิทิน MAPI ใน Java ด้วย Aspose.Email: คู่มือเชิงลึก](./create-save-mapi-calendar-aspose-email-java/)
- [วิธีแปลงรายการปฏิทิน Outlook เป็น ICS ด้วย Aspose.Email สำหรับ Java](./extract-outlook-calendar-to-ics-aspose-email-java/)
- [วิธีสร้างร่างการนัดหมายอีเมลใน Java ด้วย Aspose.Email](./create-draft-email-appointment-java-aspose/)
- [วิธีสร้างปฏิทิน MAPI พร้อมการทำซ้ำรายวันและข้อยกเว้นด้วย Aspose.Email สำหรับ Java](./create-mapi-calendar-daily-recurrence-aspose-email-java/)
- [วิธีสร้างและปรับแต่งโน้ต Outlook ด้วย Aspose.Email สำหรับ Java: คู่มือเชิงลึก](./create-customize-outlook-notes-aspose-email-java/)
- [วิธีกรองการนัดหมายเซิร์ฟเวอร์ Exchange ตามวันที่ด้วย Aspose.Email Java](./aspose-email-java-filter-exchange-appointments-by-date/)
- [วิธีทำการนัดหมายแบบแบ่งหน้าใน Java ด้วย Aspose.Email สำหรับเซิร์ฟเวอร์ Exchange](./java-aspose-email-paginated-appointments/)
- [วิธีอ่านหลายเหตุการณ์ ICS ด้วย Aspose.Email ใน Java: คู่มือเชิงลึก](./read-multiple-ics-events-aspose-email-java/)
- [จัดการหมวดหมู่ Outlook ด้วย Aspose.Email สำหรับ Java: คู่มือเชิงลึก](./manage-outlook-categories-aspose-email-java/)
- [จัดการธงติดตาม Outlook ด้วย Aspose.Email สำหรับ Java: คู่มือสำหรับนักพัฒนา](./aspose-email-java-outlook-follow-up-flags/)
- [จัดการงานอย่างมีประสิทธิภาพด้วย Aspose.Email สำหรับ Java: คู่มือปฏิทินและการนัดหมาย](./aspose-email-java-task-management/)
- [การจัดการการนัดหมายขั้นสูงด้วย Aspose.Email Java: คู่มือเชิงลึกการผสานรวม EWS API](./master-appointment-management-aspose-email-java/)
- [Aspose.Email Java ขั้นสูง: สร้างและจัดการเหตุการณ์ปฏิทินอย่างมีประสิทธิภาพ](./master-aspose-email-java-calendar-events/)
- [Aspose.Email Java ขั้นสูง: ตั้งค่าสถานะผู้เข้าร่วมและเขียนไฟล์ ICS อย่างมีประสิทธิภาพ](./aspose-email-java-set-participant-status-write-ics/)
- [ขั้นสูงการสร้างและบันทึกรายการปฏิทินด้วย Aspose.Email สำหรับ Java](./create-save-calendar-items-aspose-email-java/)
- [การจัดการปฏิทิน Exchange ขั้นสูงด้วย Aspose.Email สำหรับ Java: คู่มือเชิงลึก](./mastering-exchange-calendar-management-aspose-email-java/)
- [การจัดการเทมเพลต Outlook ขั้นสูงโดยใช้ Aspose.Email สำหรับ Java](./master-outlook-template-management-aspose-email-java/)
- [เอกสาร Aspose.Email สำหรับ Java](https://docs.aspose.com/email/java/)
- [อ้างอิง API Aspose.Email สำหรับ Java](https://reference.aspose.com/email/java/)
- [ดาวน์โหลด Aspose.Email สำหรับ Java](https://releases.aspose.com/email/java/)
- [ฟอรั่ม Aspose.Email](https://forum.aspose.com/c/email)
- [การสนับสนุนฟรี](https://forum.aspose.com/)
- [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-09-12  
**ทดสอบด้วย:** Aspose.Email for Java (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง
- [แยกไฟล์ ics ด้วย Java – อ่านเหตุการณ์ปฏิทินด้วย Aspose.Email](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [วิธีส่งออก ICS – ตั้งค่าสถานะ – Aspose.Email Java](/email/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/)
- [วิธีสร้างรายการปฏิทิน Java ด้วย Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}