---
"description": "เรียนรู้วิธีตั้งค่าข้อความทางเลือกสำหรับรูปภาพในอีเมลโดยใช้ Aspose.Email สำหรับ .NET รับรองการเข้าถึงได้ด้วยข้อความทางเลือกที่ชัดเจน มีเอกสารประกอบและโค้ดรวมอยู่ด้วย"
"linktitle": "การตั้งค่าข้อความทางเลือกสำหรับรูปภาพ - คำแนะนำ C#"
"second_title": "API การประมวลผลอีเมล Aspose.Email .NET"
"title": "การตั้งค่าข้อความทางเลือกสำหรับรูปภาพ - คำแนะนำ C#"
"url": "/th/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าข้อความทางเลือกสำหรับรูปภาพ - คำแนะนำ C#


คู่มือนี้จะแนะนำคุณเกี่ยวกับขั้นตอนการตั้งค่าข้อความทางเลือกสำหรับรูปภาพในอีเมลโดยใช้ Aspose.Email สำหรับ .NET ข้อความทางเลือกหรือที่เรียกว่า "ข้อความทางเลือก" ใช้เพื่อระบุข้อความอธิบายรูปภาพในกรณีที่ไม่สามารถแสดงรูปภาพได้ Aspose.Email สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณทำงานกับอีเมลและไฟล์แนบในรูปแบบต่างๆ ได้ ในคู่มือนี้ เราจะเน้นที่การตั้งค่าข้อความทางเลือกสำหรับรูปภาพในข้อความอีเมลโดยใช้ C#

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. มีการติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ที่เข้ากันได้
2. Aspose.Email สำหรับไลบรารี .NET คุณสามารถใช้ตัวจัดการแพ็กเกจ NuGet ใน Visual Studio ได้

## ขั้นตอนที่ 1: สร้างโครงการใหม่

1. เปิดใช้งาน Visual Studio และสร้างโปรเจ็กต์แอปพลิเคชันคอนโซล C# ใหม่

## ขั้นตอนที่ 2: ติดตั้ง Aspose.Email ผ่าน NuGet

1. คลิกขวาที่โครงการของคุณใน Solution Explorer และเลือก "จัดการแพ็คเกจ NuGet"
2. ค้นหา "Aspose.Email" และติดตั้งแพ็คเกจเวอร์ชันล่าสุด

## ขั้นตอนที่ 3: เพิ่มการใช้คำสั่ง

```csharp

using Aspose.Email.Mime;
```

## ขั้นตอนที่ 4: โหลดและแก้ไขข้อความอีเมล

1. โหลดข้อความอีเมล์โดยใช้ `MailMessage` ระดับ:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. โหลดเนื้อหา HTML ของข้อความอีเมล์:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## ขั้นตอนที่ 5: เพิ่ม AlternativeView สำหรับข้อความทางเลือกให้กับรูปภาพ

เพิ่ม htmlview สำหรับข้อความทางเลือกให้กับรูปภาพเป็น AlternateView ในข้อความ 
```csharp
message.AlternateViews.Add(htmlView);
```

## ขั้นตอนที่ 6: บันทึกและส่งอีเมล

1. บันทึกข้อความที่แก้ไขไปยังไฟล์หรือส่งโดยใช้วิธีที่คุณต้องการ:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## บทสรุป

ในคู่มือนี้ คุณจะได้เรียนรู้วิธีตั้งค่าข้อความทางเลือกสำหรับรูปภาพในข้อความอีเมลโดยใช้ Aspose.Email สำหรับ .NET เมื่อทำตามขั้นตอนที่ระบุไว้ข้างต้นแล้ว คุณจะมั่นใจได้ว่าเนื้อหาอีเมลของคุณยังคงเข้าถึงได้และให้ข้อมูลได้ แม้ว่าจะไม่สามารถแสดงรูปภาพได้ก็ตาม

## คำถามที่พบบ่อย

## ฉันจะดาวน์โหลดไลบรารี Aspose.Email ได้อย่างไร?

คุณสามารถดาวน์โหลดไลบรารี Aspose.Email ได้จาก Aspose Releases หรือติดตั้งผ่าน NuGet Package Manager ใน Visual Studio

### ฉันจะเพิ่มรูปภาพเป็นทรัพยากรที่เชื่อมโยงในอีเมลได้อย่างไร

หากต้องการเพิ่มรูปภาพเป็นทรัพยากรที่เชื่อมโยงในอีเมล คุณสามารถใช้ `LinkedResource` คลาส กำหนด ID เนื้อหาให้กับทรัพยากรที่เชื่อมโยง จากนั้นอ้างอิง ID เนื้อหานี้ในเนื้อหา HTML โดยใช้ `cid:` แผนการ สำหรับข้อมูลรายละเอียด โปรดดูที่ [เอกสารประกอบ LinkedResource](https://reference-aspose.com/email/net/aspose.email/linkedresource/).
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Email สำหรับ .NET ได้จากที่ใด

คุณสามารถค้นหาเอกสารประกอบ บทช่วยสอน และตัวอย่างโดยละเอียดเพิ่มเติมเกี่ยวกับการทำงานกับ Aspose.Email สำหรับ .NET ได้ใน [เอกสารอ้างอิง API](https://reference-aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}