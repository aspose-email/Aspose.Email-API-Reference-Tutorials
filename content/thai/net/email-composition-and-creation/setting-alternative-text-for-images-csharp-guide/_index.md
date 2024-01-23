---
title: การตั้งค่าข้อความแสดงแทนสำหรับรูปภาพ - คู่มือ C #
linktitle: การตั้งค่าข้อความแสดงแทนสำหรับรูปภาพ - คู่มือ C #
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้วิธีการตั้งค่าข้อความแสดงแทนสำหรับรูปภาพในอีเมลโดยใช้ Aspose.Email สำหรับ .NET รับประกันการเข้าถึงด้วยข้อความแสดงแทนที่ชัดเจน มีเอกสารและรหัสรวมอยู่ด้วย
type: docs
weight: 15
url: /th/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

คู่มือนี้จะแนะนำคุณตลอดขั้นตอนการตั้งค่าข้อความแสดงแทนสำหรับรูปภาพในอีเมลโดยใช้ Aspose.Email สำหรับ .NET ข้อความแสดงแทนหรือที่เรียกว่า "ข้อความแสดงแทน" ใช้เพื่อระบุคำอธิบายที่เป็นข้อความของรูปภาพในกรณีที่ไม่สามารถแสดงรูปภาพได้ Aspose.Email สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสามารถทำงานกับอีเมลและไฟล์แนบในรูปแบบต่างๆ ในคู่มือนี้ เราจะเน้นที่การตั้งค่าข้อความแสดงแทนสำหรับรูปภาพในข้อความอีเมลโดยใช้ C#

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ที่เข้ากันได้
2. Aspose.Email สำหรับไลบรารี .NET คุณสามารถใช้ NuGet Package Manager ใน Visual Studio

## ขั้นตอนที่ 1: สร้างโครงการใหม่

1. เรียกใช้ Visual Studio และสร้างโครงการแอปพลิเคชันคอนโซล C# ใหม่

## ขั้นตอนที่ 2: ติดตั้ง Aspose.Email ผ่าน NuGet

1. คลิกขวาที่โครงการของคุณใน Solution Explorer และเลือก "จัดการแพ็คเกจ NuGet"
2. ค้นหา "Aspose.Email" และติดตั้งแพ็คเกจเวอร์ชันล่าสุด

## ขั้นตอนที่ 3: เพิ่มการใช้คำสั่ง

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## ขั้นตอนที่ 4: โหลดและแก้ไขข้อความอีเมล

1.  โหลดข้อความอีเมลโดยใช้ไฟล์`MailMessage` ระดับ:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. โหลดเนื้อหา HTML ของข้อความอีเมล:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## ขั้นตอนที่ 5: เพิ่ม AlternativeView สำหรับข้อความทางเลือกให้กับรูปภาพ

เพิ่ม htmlview สำหรับข้อความแสดงแทนลงในรูปภาพเป็น AlternateView ลงในข้อความ 
```csharp
message.AlternateViews.Add(htmlView);
```

## ขั้นตอนที่ 6: บันทึกและส่งอีเมล

1. บันทึกข้อความที่แก้ไขลงในไฟล์หรือส่งโดยใช้วิธีที่คุณต้องการ:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## บทสรุป

ในคู่มือนี้ คุณได้เรียนรู้วิธีการตั้งค่าข้อความแสดงแทนสำหรับรูปภาพในข้อความอีเมลโดยใช้ Aspose.Email สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถมั่นใจได้ว่าเนื้อหาอีเมลของคุณยังคงเข้าถึงได้และให้ความรู้ แม้ว่าจะไม่สามารถแสดงรูปภาพได้ก็ตาม

## คำถามที่พบบ่อย

## ฉันจะดาวน์โหลดไลบรารี Aspose.Email ได้อย่างไร

คุณสามารถดาวน์โหลดไลบรารี Aspose.Email ได้จาก Aspose Releases หรือติดตั้งผ่าน NuGet Package Manager ใน Visual Studio

### ฉันจะเพิ่มรูปภาพเป็นทรัพยากรที่เชื่อมโยงในอีเมลได้อย่างไร

หากต้องการเพิ่มรูปภาพเป็นทรัพยากรที่เชื่อมโยงในอีเมล คุณสามารถใช้`LinkedResource` ระดับ. กำหนด ID เนื้อหาให้กับทรัพยากรที่เชื่อมโยง จากนั้นอ้างอิง ID เนื้อหานี้ในส่วนเนื้อหา HTML โดยใช้`cid:` โครงการ สำหรับข้อมูลโดยละเอียด โปรดดูที่[เอกสาร LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Email สำหรับ .NET ได้ที่ไหน

 คุณสามารถค้นหาเอกสารประกอบ บทช่วยสอน และตัวอย่างโดยละเอียดเพิ่มเติมเกี่ยวกับการทำงานกับ Aspose.Email สำหรับ .NET ได้ใน[การอ้างอิง API](https://reference.aspose.com/email/net/).