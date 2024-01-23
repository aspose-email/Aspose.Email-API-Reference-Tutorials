---
title: การตั้งค่าสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วมประชุมด้วย C#
linktitle: การตั้งค่าสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วมประชุมด้วย C#
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้วิธีจัดการสถานะของผู้เข้าร่วมประชุมโดยใช้ C# และ Aspose.Email สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
type: docs
weight: 16
url: /th/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/
---

## ข้อมูลเบื้องต้นเกี่ยวกับ Aspose.Email สำหรับ .NET

Aspose.Email สำหรับ .NET เป็นไลบรารีอเนกประสงค์ที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อความอีเมล การนัดหมาย ผู้ติดต่อ และอื่นๆ ภายในแอปพลิเคชัน .NET ของตน ด้วย API ที่ใช้งานง่าย นักพัฒนาสามารถจัดการด้านต่างๆ ของการสื่อสารทางอีเมลได้อย่างง่ายดาย ทำให้เป็นตัวเลือกที่ยอดเยี่ยมสำหรับการจัดการงานที่เกี่ยวข้องกับการนัดหมาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเรื่องการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Visual Studio (หรือ C# IDE ใด ๆ )
- Aspose.Email สำหรับไลบรารี .NET
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## การสร้างการนัดหมาย

ในการเริ่มต้น คุณต้องสร้างอินสแตนซ์การนัดหมายโดยใช้ Aspose.Email สำหรับ .NET การนัดหมายแสดงถึงเหตุการณ์ที่จัดกำหนดการไว้ และคุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น เวลาเริ่มต้น เวลาสิ้นสุด สถานที่ และอื่นๆ

```csharp
// เพิ่มที่จำเป็นโดยใช้คำสั่ง
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

 ถัดไป คุณสามารถเพิ่มผู้เข้าร่วมประชุมในการนัดหมายได้โดยใช้`Attendees` ของสะสม. ผู้เข้าร่วมคือบุคคลที่จะมีส่วนร่วมในการนัดหมาย คุณสามารถระบุที่อยู่อีเมลและชื่อได้

```csharp
// เพิ่มผู้เข้าร่วมในการนัดหมาย
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## การตั้งค่าสถานะผู้เข้าร่วม

มาถึงส่วนสำคัญแล้ว: การตั้งค่าสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม สถานะผู้เข้าร่วมบ่งชี้ว่าผู้เข้าร่วมได้ยอมรับ ปฏิเสธ หรือตอบรับคำเชิญการนัดหมายอย่างไม่แน่นอน Aspose.Email สำหรับ .NET มีตัวเลือกสถานะต่างๆ ให้เลือก

```csharp
// กำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## กรอกซอร์สโค้ดให้สมบูรณ์

นี่คือซอร์สโค้ดฉบับสมบูรณ์ที่สาธิตกระบวนการสร้างการนัดหมาย การเพิ่มผู้เข้าร่วม และการตั้งค่าสถานะผู้เข้าร่วม:

```csharp
// เพิ่มที่จำเป็นโดยใช้คำสั่ง
using Aspose.Email;
using Aspose.Email.Appointment;

// สร้างอินสแตนซ์ของคลาสการนัดหมาย
var appointment = new Appointment();

// ตั้งค่าคุณสมบัติการนัดหมาย
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// เพิ่มผู้เข้าร่วมในการนัดหมาย
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// กำหนดสถานะผู้เข้าร่วมสำหรับผู้เข้าร่วม
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## บทสรุป

ในคู่มือนี้ เราได้สำรวจกระบวนการจัดการผู้เข้าร่วมประชุมและการตั้งค่าสถานะผู้เข้าร่วมโดยใช้ C# และ Aspose.Email สำหรับ .NET คุณสมบัติที่ครอบคลุมของไลบรารีทำให้เป็นเครื่องมือที่มีค่าสำหรับนักพัฒนาที่ต้องการทำงานกับงานที่เกี่ยวข้องกับอีเมลอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะรับไลบรารี Aspose.Email สำหรับ .NET ได้อย่างไร

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Email สำหรับ .NET ได้จากเว็บไซต์:[ดาวน์โหลด Aspose.Email สำหรับ .NET](https://releases.aspose.com).

### ฉันสามารถปรับแต่งตัวเลือกสถานะของผู้เข้าร่วมได้หรือไม่?

 ได้ คุณสามารถปรับแต่งตัวเลือกสถานะผู้เข้าร่วมได้ตามความต้องการของแอปพลิเคชันของคุณโดยใช้`AppointmentParticipantStatus` การแจงนับจัดทำโดย Aspose.Email สำหรับ .NET

### Aspose.Email สำหรับ .NET เหมาะสำหรับการจัดการงานอื่นๆ ที่เกี่ยวข้องกับอีเมลหรือไม่

อย่างแน่นอน! Aspose.Email for .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการทำงานกับอีเมล เอกสารแนบ การนัดหมาย และอื่นๆ ทำให้เป็นตัวเลือกที่หลากหลายสำหรับงานที่เกี่ยวข้องกับอีเมลต่างๆ

### ฉันสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ของฉันได้หรือไม่

ได้ คุณสามารถรวมฟังก์ชันการทำงานที่กล่าวถึงในคู่มือนี้เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ของคุณได้อย่างง่ายดายโดยการอ้างอิงไลบรารี Aspose.Email สำหรับ .NET และทำตามตัวอย่างโค้ดที่ให้มา

### ฉันจะหาเอกสารและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน?

 สำหรับเอกสารและทรัพยากรโดยละเอียดเพิ่มเติม โปรดดูที่เอกสารประกอบ Aspose.Email สำหรับ .NET:[Aspose.Email สำหรับเอกสาร .NET](https://reference.aspose.com/email/net).