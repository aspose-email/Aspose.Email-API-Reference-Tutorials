---
"description": "เรียนรู้วิธีระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET สร้าง กำหนดค่า และส่งอีเมลอย่างมีประสิทธิภาพ"
"linktitle": "การระบุที่อยู่ผู้รับใน C#"
"second_title": "API การประมวลผลอีเมล Aspose.Email .NET"
"title": "การระบุที่อยู่ผู้รับใน C#"
"url": "/th/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การระบุที่อยู่ผู้รับใน C#



คู่มือนี้จะแนะนำคุณเกี่ยวกับขั้นตอนในการระบุที่อยู่ผู้รับใน C# โดยใช้ไลบรารี Aspose.Email สำหรับ .NET Aspose.Email เป็น API ของ .NET ที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถทำงานกับข้อความอีเมลและงานต่างๆ ที่เกี่ยวข้องกับอีเมลได้ ในบทช่วยสอนนี้ เราจะกล่าวถึงวิธีการเพิ่มที่อยู่ผู้รับในข้อความอีเมลโดยใช้ไลบรารี

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. มีการติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ใด ๆ
2. Aspose.Email สำหรับไลบรารี .NET คุณสามารถรับได้จาก [Aspose.Email สำหรับการเปิดตัว .NET](https://releases-aspose.com/email/net/).

## ขั้นตอน

ปฏิบัติตามขั้นตอนเหล่านี้เพื่อระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET:

### 1. สร้างโครงการ C# ใหม่

เริ่มต้นด้วยการสร้างโครงการ C# ใหม่ในสภาพแวดล้อมการพัฒนาของคุณ

### 2. เพิ่มการอ้างอิงถึง Aspose.Email

1. ดาวน์โหลดและติดตั้งไลบรารี Aspose.Email สำหรับ .NET หากคุณยังไม่ได้ทำ
2. เปิดโครงการ C# ของคุณ
3. คลิกขวาที่ "ข้อมูลอ้างอิง" ใน Solution Explorer และเลือก "เพิ่มข้อมูลอ้างอิง"
4. เรียกดูและเลือกไฟล์ DLL Aspose.Email ที่คุณดาวน์โหลด

### 3. นำเข้าเนมสเปซที่จำเป็น

ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการใช้คลาส Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. สร้างและกำหนดค่าข้อความอีเมล์

สร้างอินสแตนซ์ใหม่ของ `MailMessage` คลาสที่จะแสดงข้อความอีเมลของคุณ กำหนดค่าผู้ส่งและหัวเรื่องของอีเมล:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. เพิ่มที่อยู่ผู้รับ

คุณสามารถเพิ่มที่อยู่ผู้รับได้โดยใช้ `To`- `Cc`, และ `Bcc` คุณสมบัติของ `MailMessage` ชั้นเรียน นี่คือวิธีที่คุณสามารถเพิ่มที่อยู่ผู้รับ:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. กรอกข้อความอีเมล์ให้ครบถ้วน

เพิ่มเนื้อหาอีเมลและเนื้อหาอื่น ๆ ที่จำเป็นลงในข้อความอีเมลของคุณ:

```csharp
message.Body = "This is the email body.";
```

### 7. ส่งอีเมล์

หากต้องการส่งอีเมล์ คุณสามารถใช้ `SmtpClient` คลาสที่จัดทำโดย Aspose.Email กำหนดค่าการตั้งค่าเซิร์ฟเวอร์ SMTP และส่งอีเมล:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## คำถามที่พบบ่อย

### ฉันจะเพิ่มผู้รับหลายรายลงใน `To`- `Cc`, หรือ `Bcc` ทุ่งนา?

คุณสามารถเพิ่มผู้รับหลายรายได้โดยโทรไปที่ `Add` วิธีการหลายครั้งในแต่ละ `MailAddressCollection`-

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### ฉันสามารถระบุชื่อผู้รับพร้อมกับที่อยู่อีเมลได้หรือไม่?

ใช่ คุณสามารถระบุทั้งชื่อผู้รับและที่อยู่อีเมลเมื่อเพิ่มผู้รับได้:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### ฉันจะจัดการข้อยกเว้นเมื่อส่งอีเมลอย่างไร

คุณสามารถใช้บล็อก try-catch เพื่อจัดการข้อยกเว้นที่อาจเกิดขึ้นในระหว่างการส่งอีเมล:

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

สำหรับข้อมูลเพิ่มเติมและคุณลักษณะขั้นสูงของ Aspose.Email สำหรับ .NET โปรดดูที่ [เอกสารอ้างอิง API ของ Aspose](https://reference-aspose.com/email/net/).

บทความนี้เป็นบทสรุปของคู่มือการระบุที่อยู่ผู้รับใน C# โดยใช้ Aspose.Email สำหรับ .NET คุณได้เรียนรู้วิธีสร้างข้อความอีเมล เพิ่มที่อยู่ผู้รับ และส่งอีเมลโดยใช้คุณลักษณะของไลบรารีแล้ว

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}