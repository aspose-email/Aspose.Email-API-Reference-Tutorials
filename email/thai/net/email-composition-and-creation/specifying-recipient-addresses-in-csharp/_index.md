---
title: การระบุที่อยู่ผู้รับใน C #
linktitle: การระบุที่อยู่ผู้รับใน C #
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้วิธีระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET สร้าง กำหนดค่า และส่งอีเมลอย่างมีประสิทธิภาพ
weight: 19
url: /th/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การระบุที่อยู่ผู้รับใน C



คู่มือนี้จะแนะนำคุณตลอดกระบวนการระบุที่อยู่ผู้รับใน C# โดยใช้ไลบรารี Aspose.Email สำหรับ .NET Aspose.Email เป็น .NET API ที่ทรงพลังซึ่งช่วยให้คุณทำงานกับข้อความอีเมลและงานที่เกี่ยวข้องกับอีเมลต่างๆ ได้ ในบทช่วยสอนนี้ เราจะกล่าวถึงวิธีการเพิ่มที่อยู่ผู้รับลงในข้อความอีเมลโดยใช้ไลบรารี

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C # ใด ๆ
2.  Aspose.Email สำหรับไลบรารี .NET คุณสามารถรับได้จาก[Aspose.Email สำหรับการเผยแพร่ .NET](https://releases.aspose.com/email/net/).

## ขั้นตอน

ทำตามขั้นตอนเหล่านี้เพื่อระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET:

### 1. สร้างโปรเจ็กต์ C# ใหม่

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาของคุณ

### 2. เพิ่มการอ้างอิงถึง Aspose.Email

1. ดาวน์โหลดและติดตั้งไลบรารี Aspose.Email สำหรับ .NET หากคุณยังไม่ได้ติดตั้ง
2. เปิดโครงการ C # ของคุณ
3. คลิกขวาที่ "การอ้างอิง" ใน Solution Explorer และเลือก "เพิ่มการอ้างอิง"
4. เรียกดูและเลือกไฟล์ DLL ของ Aspose.Email ที่คุณดาวน์โหลด

### 3. นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการใช้คลาส Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. สร้างและกำหนดค่าข้อความอีเมล

 สร้างอินสแตนซ์ใหม่ของ`MailMessage` คลาสเพื่อแสดงข้อความอีเมลของคุณ กำหนดค่าผู้ส่งและหัวเรื่องของอีเมล:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. เพิ่มที่อยู่ผู้รับ

คุณสามารถเพิ่มที่อยู่ผู้รับโดยใช้`To`, `Cc` , และ`Bcc` คุณสมบัติของ`MailMessage` ระดับ. ต่อไปนี้คือวิธีที่คุณสามารถเพิ่มที่อยู่ผู้รับ:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. กรอกข้อความอีเมลให้สมบูรณ์

เพิ่มเนื้อหาอีเมลและเนื้อหาที่จำเป็นอื่น ๆ ลงในข้อความอีเมลของคุณ:

```csharp
message.Body = "This is the email body.";
```

### 7. ส่งอีเมล

 หากต้องการส่งอีเมลคุณสามารถใช้`SmtpClient` คลาสที่จัดทำโดย Aspose.Email กำหนดการตั้งค่าเซิร์ฟเวอร์ SMTP และส่งอีเมล:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## คำถามที่พบบ่อย

###  ฉันจะเพิ่มผู้รับหลายคนในไฟล์`To`, `Cc`, or `Bcc` fields?

 คุณสามารถเพิ่มผู้รับได้หลายคนโดยการโทรไปที่`Add` วิธีการหลายครั้งตามลำดับ`MailAddressCollection`: :

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### ฉันสามารถระบุชื่อผู้รับพร้อมกับที่อยู่อีเมลได้หรือไม่

ได้ คุณสามารถระบุทั้งชื่อและที่อยู่อีเมลของผู้รับเมื่อเพิ่มผู้รับ:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### ฉันจะจัดการกับข้อยกเว้นเมื่อส่งอีเมลได้อย่างไร

คุณสามารถใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้นที่อาจเกิดขึ้นระหว่างการส่งอีเมล:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 สำหรับข้อมูลเพิ่มเติมและคุณสมบัติขั้นสูงของ Aspose.Email สำหรับ .NET โปรดดูที่[กำหนดการอ้างอิง API](https://reference.aspose.com/email/net/).

นี่เป็นการสรุปคำแนะนำในการระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET คุณได้เรียนรู้วิธีสร้างข้อความอีเมล เพิ่มที่อยู่ผู้รับ และส่งอีเมลโดยใช้คุณลักษณะของไลบรารี
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
