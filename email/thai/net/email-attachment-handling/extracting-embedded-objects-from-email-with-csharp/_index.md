---
title: แยกวัตถุฝังตัวออกจากอีเมลด้วย C#
linktitle: แยกวัตถุฝังตัวออกจากอีเมลด้วย C#
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้วิธีแยกวัตถุที่ฝังตัวออกจากอีเมลโดยใช้ C# และ Aspose.Email สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 16
url: /th/net/email-attachment-handling/extracting-embedded-objects-from-email-with-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกวัตถุฝังตัวออกจากอีเมลด้วย C#


## ข้อมูลเบื้องต้นเกี่ยวกับออบเจ็กต์ฝังตัวในอีเมล

ออบเจ็กต์ที่ฝังอยู่ในอีเมลหมายถึงไฟล์ที่แทรกลงในเนื้อหาอีเมลโดยตรง แทนที่จะแนบแยกกัน ออบเจ็กต์เหล่านี้ช่วยยกระดับประสบการณ์อีเมลด้วยการอนุญาตให้ผู้ส่งรวมรูปภาพ ภาพเคลื่อนไหว หรือเนื้อหาเชิงโต้ตอบภายในเนื้อหาข้อความ

## เริ่มต้นใช้งาน Aspose.Email สำหรับ .NET

 Aspose.Email สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณลักษณะต่างๆ สำหรับการทำงานกับอีเมล รวมถึงการแยกวิเคราะห์ การสร้าง และการจัดการข้อความอีเมล ในการเริ่มต้น คุณจะต้องติดตั้งไลบรารี Aspose.Email สำหรับ .NET ในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก กำหนดเผยแพร่:[Aspose.Releases](https://releases.aspose.com/email/net/) หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet

## กำลังโหลดและแยกวิเคราะห์อีเมล

หากต้องการแยกออบเจ็กต์ที่ฝังตัวออกจากอีเมล คุณต้องโหลดและแยกวิเคราะห์ข้อความอีเมลก่อน ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
// นำเข้าเนมสเปซที่จำเป็น
using Aspose.Email;


// โหลดข้อความอีเมล
var message = MailMessage.Load("path/to/your/email.eml");
```

## การระบุและการแยกวัตถุฝังตัว

เมื่อโหลดข้อความอีเมลแล้ว คุณสามารถวนซ้ำผ่าน AlternateViews เพื่อระบุและแยกอ็อบเจ็กต์ที่ฝังไว้ได้ AlternateViews แสดงถึงรูปแบบต่างๆ ของอีเมล รวมถึง HTML และข้อความธรรมดา ออบเจ็กต์ที่ฝังมักพบในมุมมอง HTML

```csharp
// ทำซ้ำผ่านมุมมองอื่น
foreach (var view in message.AlternateViews)
{
    if (view.ContentType.MediaType == "text/html")
    {
        // แยกวัตถุที่ฝังตัวออกจากเนื้อหา HTML
        foreach (var linkedResource in view.LinkedResources)
        {
            // แยกและบันทึกทรัพยากรที่เชื่อมโยง (วัตถุฝังตัว)
            linkedResource.Save("path/to/save/" + linkedResource.ContentId);
        }
    }
}
```

## กำลังบันทึกวัตถุที่แยกออกมา

เมื่อคุณระบุและแยกวัตถุที่ฝังไว้แล้ว คุณสามารถบันทึกลงในตำแหน่งที่คุณต้องการได้ ContentId ของทรัพยากรที่เชื่อมโยงมักจะใช้เป็นชื่อไฟล์

## กรอกซอร์สโค้ดให้สมบูรณ์

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแยกอ็อบเจ็กต์ที่ฝังตัวออกจากอีเมลโดยใช้ Aspose.Email สำหรับ .NET:

```csharp
using Aspose.Email;


namespace EmbeddedObjectExtractor
{
    class Program
    {
        static void Main(string[] args)
        {
            // โหลดข้อความอีเมล
            var message = MailMessage.Load("path/to/your/email.eml");

            // ทำซ้ำผ่านมุมมองอื่น
            foreach (var view in message.AlternateViews)
            {
                if (view.ContentType.MediaType == "text/html")
                {
                    // แยกวัตถุที่ฝังตัวออกจากเนื้อหา HTML
                    foreach (var linkedResource in view.LinkedResources)
                    {
                        // แยกและบันทึกทรัพยากรที่เชื่อมโยง (วัตถุฝังตัว)
                        linkedResource.Save("path/to/save/" + linkedResource.ContentId);
                    }
                }
            }
        }
    }
}
```

## บทสรุป

ในบทความนี้ เราได้ศึกษาวิธีการแยกอ็อบเจ็กต์ที่ฝังตัวออกจากอีเมลโดยใช้ C# และไลบรารี Aspose.Email สำหรับ .NET เราครอบคลุมกระบวนการทั้งหมดตั้งแต่การโหลดและแยกวิเคราะห์อีเมลไปจนถึงการระบุและบันทึกออบเจ็กต์ที่ฝังไว้ โดยการปฏิบัติตามคู่มือนี้ คุณจะสามารถเพิ่มความสามารถในการประมวลผลอีเมลและเพิ่มเนื้อหาในแอปพลิเคชันของคุณได้

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Email สำหรับ .NET ได้อย่างไร

 คุณสามารถติดตั้ง Aspose.Email สำหรับ .NET ได้โดยการดาวน์โหลดจาก กำหนดเผยแพร่:[Aspose.Releases](https://releases.aspose.com/email/net/) หรือใช้ตัวจัดการแพ็คเกจเช่น NuGet 

### ฉันสามารถแยกวัตถุที่ฝังตัวออกจากไฟล์แนบอื่นที่ไม่ใช่ HTML ได้หรือไม่

ใช่ Aspose.Email สำหรับ .NET มีวิธีแยกอ็อบเจ็กต์ที่ฝังมาจากไฟล์แนบประเภทต่างๆ รวมถึง HTML ข้อความธรรมดา และแม้แต่รูปแบบมัลติมีเดีย

### Aspose.Email สำหรับ .NET ใช้งานได้ฟรีหรือไม่

 Aspose.Email สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ และคุณอาจต้องได้รับใบอนุญาตเพื่อใช้ในโครงการของคุณ อ้างถึง[หน้าราคา](https://purchase.aspose.com/pricing/email/net) สำหรับข้อมูลเพิ่มเติม.

### ฉันสามารถแก้ไขออบเจ็กต์ฝังตัวที่แยกออกมาก่อนที่จะบันทึกได้หรือไม่

ได้ คุณสามารถจัดการออบเจ็กต์ฝังตัวที่แยกออกมาก่อนที่จะบันทึกได้ ไลบรารี Aspose.Email นำเสนอวิธีการต่างๆ ในการแก้ไขเนื้อหาและทรัพยากรอีเมล

### ฉันจะหาตัวอย่างเพิ่มเติมของการใช้ Aspose.Email สำหรับ .NET ได้ที่ไหน

 คุณสามารถค้นหาตัวอย่างโค้ดและบทช่วยสอนเพิ่มเติมได้ใน[การอ้างอิง API](https://reference.aspose.com/email/net/). 
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
