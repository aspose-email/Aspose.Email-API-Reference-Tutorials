---
"description": "เรียนรู้วิธีจัดการสถานะผู้เข้าร่วมประชุมโดยใช้ C# และ Aspose.Email สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "การกำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วมการนัดหมายด้วย C#"
"second_title": "API การประมวลผลอีเมล Aspose.Email .NET"
"title": "การกำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วมการนัดหมายด้วย C#"
"url": "/th/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วมการนัดหมายด้วย C#


## บทนำสู่ Aspose.Email สำหรับ .NET

Aspose.Email สำหรับ .NET เป็นไลบรารีที่มีความยืดหยุ่นซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อความอีเมล การนัดหมาย รายชื่อติดต่อ และอื่นๆ ภายในแอปพลิเคชัน .NET ของตนเองได้ ด้วย API ที่ใช้งานง่าย นักพัฒนาสามารถจัดการด้านต่างๆ ของการสื่อสารทางอีเมลได้อย่างง่ายดาย ทำให้เป็นตัวเลือกที่ยอดเยี่ยมสำหรับการจัดการงานที่เกี่ยวข้องกับการนัดหมาย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Visual Studio (หรือ C# IDE ใดๆ)
- Aspose.Email สำหรับไลบรารี .NET
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## การสร้างการนัดหมาย

ในการเริ่มต้น คุณต้องสร้างอินสแตนซ์การนัดหมายโดยใช้ Aspose.Email สำหรับ .NET การนัดหมายแสดงถึงเหตุการณ์ที่กำหนดเวลาไว้ และคุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น เวลาเริ่มต้น เวลาสิ้นสุด ตำแหน่งที่ตั้ง และอื่นๆ

```csharp
// เพิ่มคำสั่งที่จำเป็นในการใช้งาน
using Aspose.Email;
using Aspose.Email.Appointment;

// สร้างอินสแตนซ์ของคลาสการนัดหมาย
var appointment = new Appointment();

// ตั้งค่าคุณสมบัติการนัดหมาย
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## การเพิ่มผู้เข้าร่วม

จากนั้นคุณสามารถเพิ่มผู้เข้าร่วมการนัดหมายได้โดยใช้ `Attendees` การรวบรวม ผู้เข้าร่วมคือบุคคลที่จะเข้าร่วมการนัดหมาย คุณสามารถระบุที่อยู่อีเมลและชื่อของพวกเขาได้

```csharp
// เพิ่มผู้เข้าร่วมการนัดหมาย
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## การตั้งค่าสถานะผู้เข้าร่วม

ตอนนี้มาถึงส่วนสำคัญ: การกำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม สถานะผู้เข้าร่วมจะระบุว่าผู้เข้าร่วมได้ยอมรับ ปฏิเสธ หรือยอมรับคำเชิญนัดหมายชั่วคราว Aspose.Email สำหรับ .NET มีตัวเลือกสถานะต่างๆ ให้เลือก

```csharp
// กำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## ซอร์สโค้ดที่สมบูรณ์

นี่คือซอร์สโค้ดที่สมบูรณ์ซึ่งสาธิตขั้นตอนการสร้างการนัดหมาย การเพิ่มผู้เข้าร่วม และการกำหนดสถานะผู้เข้าร่วม:

```csharp
// เพิ่มคำสั่งที่จำเป็นในการใช้งาน
using Aspose.Email;
using Aspose.Email.Appointment;

// สร้างอินสแตนซ์ของคลาสการนัดหมาย
var appointment = new Appointment();

// ตั้งค่าคุณสมบัติการนัดหมาย
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// เพิ่มผู้เข้าร่วมการนัดหมาย
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// กำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## บทสรุป

ในคู่มือนี้ เราได้สำรวจกระบวนการจัดการผู้เข้าร่วมการนัดหมายและกำหนดสถานะของผู้เข้าร่วมโดยใช้ C# และ Aspose.Email สำหรับ .NET คุณสมบัติที่ครอบคลุมของไลบรารีทำให้เป็นเครื่องมือที่มีค่าสำหรับนักพัฒนาที่ต้องการทำงานกับงานที่เกี่ยวข้องกับอีเมลอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะได้รับไลบรารี Aspose.Email สำหรับ .NET ได้อย่างไร

คุณสามารถดาวน์โหลดไลบรารี Aspose.Email สำหรับ .NET ได้จากเว็บไซต์: [ดาวน์โหลด Aspose.Email สำหรับ .NET](https://releases-aspose.com).

### ฉันสามารถปรับแต่งตัวเลือกสถานะผู้เข้าร่วมได้หรือไม่

ใช่ คุณสามารถปรับแต่งตัวเลือกสถานะผู้เข้าร่วมตามความต้องการของแอปพลิเคชันของคุณได้โดยใช้ `AppointmentParticipantStatus` การแจงนับที่จัดทำโดย Aspose.Email สำหรับ .NET

### Aspose.Email สำหรับ .NET เหมาะกับการจัดการงานที่เกี่ยวข้องกับอีเมลอื่นๆ หรือไม่

แน่นอน! Aspose.Email สำหรับ .NET นำเสนอคุณลักษณะต่างๆ มากมายสำหรับการทำงานกับอีเมล ไฟล์แนบ การนัดหมาย และอื่นๆ ทำให้เป็นตัวเลือกที่หลากหลายสำหรับงานต่างๆ ที่เกี่ยวข้องกับอีเมล

### ฉันสามารถรวมฟังก์ชันนี้ลงในแอปพลิเคชัน .NET ที่มีอยู่ของฉันได้หรือไม่

ใช่ คุณสามารถรวมฟังก์ชันการทำงานที่กล่าวถึงในคู่มือนี้ลงในแอปพลิเคชัน .NET ที่มีอยู่ของคุณได้อย่างง่ายดาย โดยอ้างอิงไลบรารี Aspose.Email สำหรับ .NET และทำตามตัวอย่างโค้ดที่ให้มา

### ฉันสามารถหาเอกสารและทรัพยากรเพิ่มเติมได้ที่ไหน

สำหรับเอกสารและทรัพยากรโดยละเอียดเพิ่มเติม โปรดดูเอกสาร Aspose.Email สำหรับ .NET: [เอกสาร Aspose.Email สำหรับ .NET](https://reference-aspose.com/email/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}