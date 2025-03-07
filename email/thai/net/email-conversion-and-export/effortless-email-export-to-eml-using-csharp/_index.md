---
title: ส่งออกอีเมลไปยัง EML ได้อย่างง่ายดายโดยใช้ C#
linktitle: ส่งออกอีเมลไปยัง EML ได้อย่างง่ายดายโดยใช้ C#
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: ส่งออกอีเมลเป็นรูปแบบ EML ได้อย่างง่ายดายโดยใช้ C# และ Aspose.Email สำหรับ .NET เรียนรู้ทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ด
weight: 11
url: /th/net/email-conversion-and-export/effortless-email-export-to-eml-using-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออกอีเมลไปยัง EML ได้อย่างง่ายดายโดยใช้ C#


## ข้อมูลเบื้องต้นเกี่ยวกับการส่งออกอีเมลไปยัง EML ได้อย่างง่ายดาย

Aspose.Email สำหรับ .NET เป็นไลบรารี่ที่แข็งแกร่งและเต็มไปด้วยคุณสมบัติที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อความอีเมลและงานต่างๆ ที่เกี่ยวข้องกับอีเมลในแอปพลิเคชัน .NET ของตนได้ โดยมีชุดคลาสและวิธีการที่ครอบคลุมในการจัดการอีเมล ไฟล์แนบ ส่วนหัว และอื่นๆ ในบทช่วยสอนนี้ เราจะเน้นที่การใช้ Aspose.Email เพื่อส่งออกข้อความอีเมลเป็นรูปแบบ EML ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเรื่องการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
-  Aspose.Email สำหรับไลบรารี .NET (ดาวน์โหลดจาก[ที่นี่](https://downloads.aspose.com/email/net)

## การติดตั้ง Aspose.Email สำหรับ .NET

ทำตามขั้นตอนเหล่านี้เพื่อติดตั้งไลบรารี Aspose.Email สำหรับ .NET ในโครงการของคุณ:

1.  ดาวน์โหลดไลบรารี Aspose.Email จาก[ที่นี่](https://releases.aspose.com/email/net).
2. แยกไฟล์ zip ที่ดาวน์โหลดมาไปยังไดเร็กทอรีบนคอมพิวเตอร์ของคุณ
3. เปิดโครงการ C # ของคุณใน Visual Studio
4. คลิกขวาที่โครงการของคุณใน Solution Explorer และเลือก "จัดการแพ็คเกจ NuGet"
5. ใน NuGet Package Manager คลิกที่ "เรียกดู" และค้นหา "Aspose.Email"
6. เลือกเวอร์ชันที่เหมาะสมของแพ็คเกจแล้วคลิก "ติดตั้ง"

## กำลังโหลดข้อความอีเมล

หากต้องการส่งออกอีเมลเป็นรูปแบบ EML เราต้องโหลดข้อความอีเมลจากแหล่งที่มาก่อน ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Email;


// โหลดข้อความอีเมลต้นฉบับ
string sourcePath = "path/to/source/email.msg";
MailMessage email = MailMessage.Load(sourcePath);
```

## การส่งออกอีเมลเป็นรูปแบบ EML

 เมื่อคุณโหลดข้อความอีเมลแล้ว ขั้นตอนต่อไปคือส่งออกเป็นรูปแบบ EML ทำได้โดยเพียงแค่สร้างอินสแตนซ์ของ`MailMessage` คลาสและการตั้งค่าคุณสมบัติ:

```csharp
// สร้างอินสแตนซ์ใหม่ของ MailMessage
MailMessage emlMessage = new MailMessage();

// ตั้งค่าคุณสมบัติจากอีเมลที่โหลด
emlMessage.Subject = email.Subject;
emlMessage.From = email.From;
emlMessage.To = email.To;
emlMessage.Body = email.Body;
// ตั้งค่าคุณสมบัติอื่นๆ ตามความจำเป็น

// ขณะนี้อีเมลที่ส่งออกอยู่ในวัตถุ emlMessage
```

## กำลังบันทึกไฟล์ EML

เมื่อคุณเตรียมข้อความอีเมลในรูปแบบ EML แล้ว คุณสามารถบันทึกเป็นไฟล์ได้ ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางที่เหมาะสมสำหรับการบันทึกไฟล์:

```csharp
string outputPath = "path/to/output/eml.eml";
emlMessage.Save(outputPath, SaveOptions.DefaultEml);
```

## การจัดการสิ่งที่แนบมา

ข้อความอีเมลมักจะมีไฟล์แนบที่ต้องส่งออกพร้อมกับข้อความ ต่อไปนี้คือวิธีที่คุณสามารถจัดการไฟล์แนบโดยใช้ Aspose.Email:

```csharp
foreach (Attachment attachment in email.Attachments)
{
    emlMessage.Attachments.Add(attachment);
}
```

## การเพิ่มข้อมูลเมตาอีเมลเพิ่มเติม

คุณยังสามารถเพิ่มข้อมูลเมตาเพิ่มเติมให้กับอีเมลที่ส่งออกโดยใช้ Aspose.Email ซึ่งรวมถึงส่วนหัว คุณสมบัติที่กำหนดเอง และอื่นๆ:

```csharp
emlMessage.Headers.Add("X-Custom-Header", "Custom Value");
emlMessage.Headers.Add("Date", DateTime.Now.ToString("r"));
// เพิ่มส่วนหัวและข้อมูลเมตาอื่นๆ ตามความจำเป็น
```

## การจัดการข้อผิดพลาด

ในระหว่างขั้นตอนการส่งออก สิ่งสำคัญคือต้องจัดการกับข้อผิดพลาดที่อาจเกิดขึ้นเพื่อให้มั่นใจว่าผู้ใช้จะได้รับประสบการณ์ที่ราบรื่น ใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้น:

```csharp
try
{
    // ส่งออกอีเมลและจัดการข้อผิดพลาด
}
catch (Exception ex)
{
    // จัดการกับข้อยกเว้น
}
```

## กรอกซอร์สโค้ดให้สมบูรณ์

ต่อไปนี้เป็นซอร์สโค้ดที่สมบูรณ์สำหรับการส่งออกอีเมลเป็นรูปแบบ EML โดยใช้ Aspose.Email สำหรับ .NET:

```csharp
using Aspose.Email;


namespace EmailExportApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // โหลดข้อความอีเมลต้นฉบับ
            string sourcePath = "path/to/source/email.msg";
            MailMessage email = MailMessage.Load(sourcePath);

            // สร้างอินสแตนซ์ใหม่ของ MailMessage
            MailMessage emlMessage = new MailMessage();

            // ตั้งค่าคุณสมบัติจากอีเมลที่โหลด
            emlMessage.Subject = email.Subject;
            emlMessage.From = email.From;
            emlMessage.To = email.To;
            emlMessage.Body = email.Body;
            // ตั้งค่าคุณสมบัติอื่นๆ ตามความจำเป็น

            // จัดการสิ่งที่แนบมา
            foreach (Attachment attachment in email.Attachments)
            {
                emlMessage.Attachments.Add(attachment);
            }

            // เพิ่มข้อมูลเมตาเพิ่มเติม
            emlMessage.Headers.Add("X-Custom-Header", "Custom Value");

            // บันทึกไฟล์ EML
            string outputPath = "path/to/output/eml.eml";
            emlMessage.Save(outputPath, SaveOptions.DefaultEml);

            Console.WriteLine("Email exported successfully.");
        }
    }
}
```

## บทสรุป

การส่งออกอีเมลเป็นรูปแบบ EML โดยใช้ C# และ Aspose.Email สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อนซึ่งให้ความยืดหยุ่นในการจัดการข้อความอีเมลและคุณสมบัติของข้อความเหล่านั้น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันการส่งออกอีเมลเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ฉันจะจัดการกับข้อผิดพลาดระหว่างขั้นตอนการส่งออกอีเมลได้อย่างไร

ในการจัดการข้อผิดพลาดระหว่างขั้นตอนการส่งออกอีเมล ให้ใช้บล็อก try-catch รวมโค้ดส่งออกไว้ภายในบล็อก try และตรวจจับข้อยกเว้นใดๆ ที่อาจเกิดขึ้น เพื่อให้แน่ใจว่าแอปพลิเคชันของคุณจัดการกับข้อผิดพลาดได้อย่างงดงามและมอบประสบการณ์ผู้ใช้ที่ดี

### ฉันสามารถส่งออกไฟล์แนบอีเมลโดยใช้ Aspose.Email สำหรับ .NET ได้หรือไม่

ได้ คุณสามารถส่งออกไฟล์แนบอีเมลพร้อมกับข้อความอีเมลได้โดยใช้ Aspose.Email for .NET วนซ้ำไฟล์แนบของอีเมลต้นทาง และเพิ่มลงในคอลเลกชันไฟล์แนบของอีเมลที่ส่งออก

### ฉันจะดาวน์โหลดไลบรารี Aspose.Email สำหรับ .NET ได้ที่ไหน

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Email สำหรับ .NET ได้จาก[ที่นี่](https://downloads.aspose.com/email/net).

### ซอร์สโค้ดที่ให้ไว้ในบทช่วยสอนเสร็จสมบูรณ์หรือไม่

ใช่ บทช่วยสอนมีซอร์สโค้ดที่สมบูรณ์ซึ่งสาธิตวิธีการส่งออกอีเมลเป็นรูปแบบ EML โดยใช้ Aspose.Email สำหรับ .NET คุณสามารถใช้รหัสนี้เป็นจุดเริ่มต้นได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
