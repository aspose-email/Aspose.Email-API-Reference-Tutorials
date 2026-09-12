---
date: '2026-09-12'
description: เรียนรู้วิธีสร้างไฟล์ iCalendar ด้วย Java โดยใช้ Aspose.Email, ตั้งค่าสถานะผู้เข้าร่วม,
  และสร้างหลายเหตุการณ์ในปฏิทินอย่างมีประสิทธิภาพ
keywords:
- create icalendar file java
- java generate ics calendar
- aspose email java
- ics export java
lastmod: '2026-09-12'
og_description: สร้างไฟล์ iCalendar ด้วย Java โดยใช้ Aspose.Email. ตั้งค่าสถานะผู้เข้าร่วม,
  เขียนหลายเหตุการณ์, และเชื่อมต่อกับ Outlook, Google Calendar, และอื่น ๆ
og_image_alt: Guide to creating iCalendar files in Java with Aspose.Email
og_title: สร้างไฟล์ iCalendar ด้วย Java – ส่งออกไฟล์ ICS ด้วย Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  headline: How to create iCalendar file Java – export ICS with Aspose.Email
  type: TechArticle
- description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  name: How to create iCalendar file Java – export ICS with Aspose.Email
  steps:
  - name: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
    text: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
  - name: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
    text: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
  - name: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
    text: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
  - name: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
    text: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
  - name: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
    text: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
  type: HowTo
- questions:
  - answer: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide
      the UID of the appointment you wish to update.
    question: Can I update an existing ICS file instead of creating a new one?
  - answer: Absolutely. Configure recurrence patterns on the `Appointment` object
      before writing to the ICS file.
    question: Does Aspose.Email support recurring events?
  - answer: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")`
      to embed non‑standard fields.
    question: Is it possible to add custom properties to an ICS event?
  - answer: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are
      supported.
    question: What time‑zone formats are accepted?
  - answer: A temporary license removes evaluation restrictions; a full license is
      required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- create icalendar file java
- aspose.email
- java calendar integration
title: วิธีสร้างไฟล์ iCalendar ด้วย Java – ส่งออกไฟล์ ICS ด้วย Aspose.Email
url: /th/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ iCalendar ด้วย Java – ส่งออกไฟล์ ICS ด้วย Aspose.Email

การจัดการตารางการประชุมข้ามโซนเวลาอาจทำให้ปวดหัว โดยเฉพาะเมื่อคุณต้องแชร์คำเชิญให้กับผู้เข้าร่วมหลายสิบคน ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างไฟล์ iCalendar ด้วย Java** โดยใช้ Aspose.Email for Java ตั้งค่าสถานะผู้เข้าร่วม และเขียนเหตุการณ์หลายรายการลงในไฟล์ `.ics` ไฟล์เดียว ตัวอย่างโค้ดแบบขั้นตอน‑ต่อ‑ขั้นตอนพร้อมคัดลอกไปใช้ในโปรเจกต์ของคุณ และคำอธิบายแสดงเหตุผลว่าทำไมแต่ละส่วนจึงสำคัญ

## คำตอบด่วน
- **ฉันสามารถตั้งค่าสถานะผู้เข้าร่วมด้วย Aspose.Email for Java ได้หรือไม่?** ใช่ – คุณสามารถกำหนดค่า Accepted, Declined หรือ Tentative ให้กับผู้เข้าร่วมแต่ละคน  
- **ฉันสามารถเขียนเหตุการณ์ได้กี่รายการลงในไฟล์ ICS ไฟล์เดียว?** ไลบรารีไม่มีข้อจำกัดที่เข้มงวด; ตัวอย่างแสดงการเขียนสิบเหตุการณ์และคุณสามารถขยายเป็นหลายพันรายการได้  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวฟรีจะลบข้อจำกัดการประเมิน; ไลเซนส์ที่ซื้อจะต้องใช้สำหรับการผลิต  
- **แนะนำให้ใช้เวอร์ชัน Java ใด?** JDK 16 (หรือใหม่กว่า) ตรงกับ classifier ที่ให้มาและรับประกันความเข้ากันได้เต็มรูปแบบของ API  
- **การจัดการโซนเวลาทำงานอัตโนมัติหรือไม่?** คุณสามารถระบุโซนเวลาเมื่อสร้างวันที่และ Aspose.Email จะฝัง TZID ที่ถูกต้องลงไป

## iCalendar คืออะไรและทำไมจึงสำคัญ?
รูปแบบ iCalendar (ICS) เป็นมาตรฐานสากลสำหรับการแลกเปลี่ยนข้อมูลปฏิทินระหว่าง Outlook, Google Calendar, Apple Calendar และไคลเอนต์อื่น ๆ อีกหลายรายการ การส่งออกเป็น iCalendar ช่วยให้คุณสามารถแจกจ่ายคำเชิญการประชุม, สร้างเหตุการณ์เป็นกลุ่ม, หรือผสานระบบเก่าโดยไม่สูญเสียสถานะผู้เข้าร่วมหรือคุณสมบัติเฉพาะ

## ทำไมต้องใช้ Aspose.Email for Java เพื่อส่งออกไฟล์ iCalendar?
Aspose.Email ให้คุณควบคุมแต่ละองค์ประกอบของ iCalendar อย่างละเอียดในขณะที่การใช้งานยังง่าย รองรับ **รูปแบบเข้าและออกกว่า 50 ประเภท**, ประมวลผลปฏิทินหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, และทำงานบนแพลตฟอร์มใด ๆ ที่รัน Java 16 หรือใหม่กว่า หมายความว่าคุณสามารถสร้างไฟล์ `.ics` ที่แข็งแรงและแสดงผลถูกต้องในไคลเอนต์ปฏิทินหลักทุกตัว

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีและเวอร์ชันที่ต้องการ
- **Aspose.Email for Java** เวอร์ชัน 25.4 หรือใหม่กว่า (ไลบรารีมีคลาสกว่า 30 คลาสสำหรับการจัดการ iCalendar)  
- Maven สำหรับการจัดการ dependencies (หรือดาวน์โหลด JAR โดยตรงจาก [Aspose](https://releases.aspose.com/email/java/))

### การตั้งค่าสภาพแวดล้อม
- JDK 16 (หรือใหม่กว่า) ติดตั้งบนเครื่องของคุณ  
- IDE เช่น IntelliJ IDEA หรือ Eclipse

### ความรู้พื้นฐานที่ต้องมี
- ทักษะการเขียนโปรแกรม Java เบื้องต้น  
- ความคุ้นเคยกับ `java.util.Calendar` และ `java.util.Date` สำหรับการจัดการวันที่‑เวลา

## การตั้งค่า Aspose.Email for Java

เพิ่มไลบรารี Aspose.Email ไปยังโปรเจกต์ Maven ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ขั้นตอนการรับไลเซนส์

1. **Free trial** – ดาวน์โหลดไลเซนส์ชั่วคราวเพื่อทดสอบ Aspose.Email โดยไม่มีข้อจำกัด เยี่ยมชม [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) สำหรับรายละเอียด  
2. **Purchase** – สำหรับการใช้งานระยะยาว ให้ซื้อการสมัครสมาชิกที่ [Aspose Purchase](https://purchase.aspose.com/buy)

เริ่มต้นไลเซนส์ในโค้ดของคุณ:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

ตอนนี้คุณพร้อมที่จะดำเนินการกับคุณลักษณะหลักสองประการของคู่มือนี้แล้ว

## วิธีส่งออกไฟล์ iCalendar ด้วย Java: ตั้งค่าสถานะผู้เข้าร่วมของการนัดหมาย

### สถานะผู้เข้าร่วมในนัดหมายปฏิทินคืออะไร?
สถานะผู้เข้าร่วมบันทึกว่าผู้เข้าร่วมตอบรับคำเชิญอย่างไร – Accepted, Declined หรือ Tentative การตั้งค่านี้โดยโปรแกรมเป็นสิ่งสำคัญสำหรับระบบกำหนดเวลาที่อัตโนมัติและการติดตามการประชุมที่แม่นยำ

คุณสามารถตั้งค่าสถานะผู้เข้าร่วมโดยตรงบนอ็อบเจ็กต์ `Attendee` แต่ละตัวก่อนเขียนไฟล์ปฏิทิน

### การดำเนินการแบบขั้นตอน‑ต่อ‑ขั้นตอน

#### 1️⃣ สร้างและกำหนดค่าข้อมูลวันที่ของนัดหมาย
`java.util.Calendar` เป็นคลาสของ Java สำหรับจัดการค่าเวลาและวันที่ กำหนดเวลาเริ่มต้นและสิ้นสุดโดยใช้ `java.util.Calendar` ไลบรารีจะเคารพตัวระบุโซนเวลาที่คุณระบุ

```java
String location = "Room 5";
Calendar calendar = Calendar.getInstance();

// Set start date and time
calendar.set(2011, Calendar.NOVEMBER, 10, 10, 12, 11);
Date startDate = calendar.getTime();

// Set end date and time
calendar.set(2012, Calendar.OCTOBER, 13, 13, 11, 12);
Date endDate = calendar.getTime();
```

#### 2️⃣ กำหนดผู้จัดและรายการผู้เข้าร่วม
`AttendeeCollection` เป็นคลาสคอลเลกชันที่เก็บอ็อบเจ็กต์ `Attendee` แสดงผู้เข้าร่วมการประชุม สร้าง `AttendeeCollection` แล้วเพิ่มที่อยู่อีเมลของผู้เข้าร่วมแต่ละคน

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ กำหนดสถานะการเข้าร่วมให้แต่ละผู้เข้าร่วม
`ResponseType` ระบุสถานะการตอบกลับของผู้เข้าร่วม เช่น Accepted, Declined หรือ Tentative ตั้งค่าคุณสมบัติ `ResponseType` ของแต่ละ `Attendee` เพื่อบ่งบอกสถานะที่ต้องการ

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ สร้างอ็อบเจ็กต์ `Appointment`
`Appointment` แทนเหตุการณ์ปฏิทินที่มีรายละเอียดเช่น หัวเรื่อง, สถานที่, และเวลา หลังจากกำหนดวันที่, ผู้จัด, และผู้เข้าร่วมแล้ว คุณสามารถทำการซีเรียลไลซ์เป็น iCalendar ได้

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**Pro tip:** ตรวจสอบที่อยู่อีเมลด้วย regex อย่างง่ายก่อนเพิ่มลงในคอลเลกชัน; ที่อยู่อีเมลที่ผิดรูปแบบจะทำให้เกิด `ParseException`

## วิธีส่งออกไฟล์ iCalendar ด้วย Java: เขียนหลายเหตุการณ์ลงในไฟล์ ICS

### ทำไมต้องส่งออกปฏิทินเป็น iCalendar ด้วย Java?
รูปแบบ iCalendar เป็นที่เข้าใจทั่วโลก ช่วยให้คุณแชร์ข้อมูลการประชุมระหว่าง Outlook, Google Calendar, Apple Calendar และไคลเอนต์อื่น ๆ อีกหลายรายการ โดย **java generate ics calendar** ด้วย Aspose.Email คุณจะคงสถานะผู้เข้าร่วม, คุณสมบัติเฉพาะ, และกฎการทำซ้ำโดยไม่ต้องแปลงเพิ่มเติม

### การดำเนินการแบบขั้นตอน‑ต่อ‑ขั้นตอน

#### 1️⃣ กำหนดค่า save options และสร้าง writer
`IcsSaveOptions` กำหนดวิธีการเขียนไฟล์ iCalendar รวมถึงการเข้ารหัสและรูปแบบ `IcsSaveOptions` ควบคุมการเขียนไฟล์ การใช้ instance เดียวหลายครั้งช่วยเพิ่มประสิทธิภาพเมื่อจัดการเหตุการณ์จำนวนมาก

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ กำหนดช่วงเวลาสำหรับแต่ละเหตุการณ์
`java.util.Date` แสดงจุดเวลาเฉพาะ ใช้สำหรับกำหนดเวลาเริ่มต้นและสิ้นสุดวนลูปผ่านแหล่งข้อมูลของคุณเพื่อสร้างอ็อบเจ็กต์ `Date` สำหรับแต่ละนัดหมาย

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ เตรียมคอลเลกชันผู้เข้าร่วม
สร้าง `AttendeeCollection` ครั้งเดียวแล้วแนบไปกับ `Appointment` ทุกอันที่คุณสร้าง

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ สร้างและเขียนหลายนัดหมาย
วนลูป สร้าง `Appointment` สำหรับแต่ละรายการ แล้วเรียก `writer.write(appointment)` สุดท้ายเรียก `writer.dispose()` เพื่อปิดไฟล์

```java
try {
    for (int i = 0; i < 10; i++) {
        Appointment app = new Appointment("Room 112", startDate, endDate,
                new MailAddress("organizer@domain.com"), attendees);
        app.setDescription("Test body " + i);
        app.setSummary("Test summary:" + i);
        
        writer.write(app); // Write the appointment to ICS file
    }
} finally {
    writer.dispose(); // Clean up resources
}
```

**Common pitfall:** ลืมเรียก `writer.dispose()` ทำให้ไฟล์เปิดค้างและเกิดข้อผิดพลาด “file in use” ในการรันครั้งต่อไป

## การประยุกต์ใช้งานจริง

Aspose.Email for Java มีประโยชน์ในสถานการณ์จริงหลายแบบ:

1. **การกำหนดเวลาการประชุมอัตโนมัติ** – สร้างคำเชิญปฏิทินแบบไดนามิกสำหรับเครื่องมือภายในหรือระบบ CRM  
2. **การผสานปฏิทินข้ามแพลตฟอร์ม** – ส่งออกนัดหมายจากฐานข้อมูลเก่าไปยัง Outlook, Google Calendar หรือ Apple Calendar ด้วยรูปแบบ iCalendar มาตรฐาน  
3. **แพลตฟอร์มจัดการกิจกรรม** – สร้างตารางงานจำนวนมากสำหรับการประชุม, เวิร์กช็อป, หรือเว็บบินาร์ด้วยการเรียก API ครั้งเดียว พร้อมคงสถานะผู้เข้าร่วมทั้งหมด

## ข้อควรพิจารณาด้านประสิทธิภาพ

เมื่อทำงานกับ **Aspose.Email for Java** ให้คำนึงถึงเคล็ดลับต่อไปนี้:

- ปิด `CalendarWriter`, `Appointment`, และอ็อบเจ็กต์ `MailMessage` ใด ๆ ทันทีที่ใช้งานเสร็จเพื่อคืนทรัพยากรเนทีฟ  
- ประมวลผลเป็นชุดเมื่อจัดการข้อมูลจำนวนมาก; วิธีนี้ลดภาระการทำงานของ garbage‑collection ได้ถึง 30 %  
- ใช้ instance ของ `IcsSaveOptions` เพียงอันเดียวแทนการสร้างใหม่ทุกครั้งที่เขียนไฟล์

## คำถามที่พบบ่อย

**Q: ฉันสามารถอัปเดตไฟล์ ICS ที่มีอยู่แทนการสร้างไฟล์ใหม่ได้หรือไม่?**  
A: ได้. ตั้งค่า `saveOptions.setAction(AppointmentAction.Modify)` แล้วระบุ UID ของนัดหมายที่ต้องการอัปเดต

**Q: Aspose.Email รองรับเหตุการณ์ที่เกิดซ้ำหรือไม่?**  
A: รองรับเต็มที่. ตั้งค่ารูปแบบการทำซ้ำบนอ็อบเจ็กต์ `Appointment` ก่อนเขียนลงไฟล์ ICS

**Q: สามารถเพิ่มคุณสมบัติเฉพาะลงในเหตุการณ์ ICS ได้หรือไม่?**  
A: ได้. ใช้ `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` เพื่อฝังฟิลด์ที่ไม่เป็นมาตรฐาน

**Q: รูปแบบโซนเวลาใดบ้างที่รับรอง?**  
A: รองรับทั้ง IANA time‑zone IDs (เช่น “America/New_York”) และการระบุออฟเซ็ต GMT

**Q: จำเป็นต้องมีไลเซนส์สำหรับการสร้างบิลด์การพัฒนาหรือไม่?**  
A: ไลเซนส์ชั่วคราวจะลบข้อจำกัดการประเมิน; ไลเซนส์เต็มจะต้องใช้สำหรับการปรับใช้ในสภาพแวดล้อมการผลิต

## สรุป

คุณได้เรียนรู้ **วิธีสร้างไฟล์ iCalendar ด้วย Java**, ตั้งค่าสถานะผู้เข้าร่วม, และเขียนหลายเหตุการณ์โดยใช้ Aspose.Email for Java ความสามารถเหล่านี้ช่วยให้คุณสร้างฟีเจอร์การกำหนดเวลาที่แข็งแรง, ผสานกับไคลเอนต์ปฏิทินใด ๆ, และทำให้การกระจายเหตุการณ์เป็นเรื่องง่ายในองค์กรของคุณ

---

**Last Updated:** 2026-09-12  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [Generate .ics File Java – Create Calendar Invite with Aspose.Email for Java – Full Tutorial](/email/java/)
- [Parse ics file java – Read Calendar Events with Aspose.Email](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [Create Calendar Sharing Invitation with Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}