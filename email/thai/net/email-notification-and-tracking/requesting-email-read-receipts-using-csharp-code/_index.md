---
title: การขอใบรับการอ่านอีเมลโดยใช้รหัส C #
linktitle: การขอใบรับการอ่านอีเมลโดยใช้รหัส C #
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้วิธีใช้โค้ด C# เพื่อขอใบรับการอ่านอีเมลโดยใช้ Aspose.Email สำหรับ .NET ซึ่งเพิ่มประสิทธิภาพการติดตามการสื่อสาร
weight: 11
url: /th/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การขอใบรับการอ่านอีเมลโดยใช้รหัส C


ในยุคดิจิทัลปัจจุบัน การสื่อสารทางอีเมลกลายเป็นส่วนสำคัญในชีวิตส่วนตัวและอาชีพของเรา บ่อยครั้งเมื่อส่งอีเมลสำคัญ เราต้องการให้แน่ใจว่าผู้รับได้อ่านและรับทราบข้อความของเราแล้ว นี่คือจุดที่ใบตอบรับการอ่านอีเมลเข้ามามีบทบาท ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการขอใบตอบรับการอ่านอีเมลโดยใช้ C# กับ Aspose.Email สำหรับ .NET

## ข้อมูลเบื้องต้นเกี่ยวกับใบเสร็จรับเงินการอ่านอีเมล

ใบตอบรับการอ่านอีเมล หรือที่เรียกว่าการติดตามอีเมลหรือการส่งคืนใบตอบรับ ช่วยให้คุณสามารถรับการแจ้งเตือนเมื่อผู้รับเปิดและอ่านอีเมลของคุณ เป็นคุณลักษณะที่มีคุณค่า โดยเฉพาะอย่างยิ่งในการสื่อสารทางธุรกิจ เนื่องจากเป็นการยืนยันการส่งข้อความและการมีส่วนร่วม

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
- Aspose.Email สำหรับไลบรารี .NET ดาวน์โหลดและอ้างอิงในโครงการของคุณ

## ขั้นตอนที่ 1: การสร้างอินสแตนซ์ MailMessage

 ขั้นตอนแรกในการใช้งานใบรับการอ่านอีเมลคือการสร้างอินสแตนซ์ของ`MailMessage` ระดับ. คลาสนี้แสดงถึงข้อความอีเมลและอนุญาตให้คุณตั้งค่าคุณสมบัติต่างๆ ของอีเมล

```csharp
MailMessage message = new MailMessage();
```

## ขั้นตอนที่ 2: การระบุรายละเอียดข้อความ

ตอนนี้ เรามาระบุรายละเอียดของข้อความอีเมล รวมถึงตัวเลือกผู้ส่ง ผู้รับ เนื้อหา HTML และการแจ้งเตือนการจัดส่ง

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## ขั้นตอนที่ 3: การสร้างอินสแตนซ์ SmtpClient

 ในการส่งอีเมล เราจำเป็นต้องสร้างอินสแตนซ์ของ`SmtpClient` คลาสซึ่งมีหน้าที่ในการส่งข้อความ

```csharp
SmtpClient client = new SmtpClient();
```

## ขั้นตอนที่ 4: การกำหนดการตั้งค่า SMTP

กำหนดการตั้งค่าเซิร์ฟเวอร์ SMTP ของคุณโดยระบุเซิร์ฟเวอร์โฮสต์ ชื่อผู้ใช้ รหัสผ่าน และหมายเลขพอร์ต

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## ขั้นตอนที่ 5: การส่งอีเมล

 สุดท้ายก็ใช้`client.Send` วิธีการส่งข้อความอีเมล หากส่งข้อความสำเร็จ การแจ้งเตือน "ส่งข้อความ" จะปรากฏขึ้น

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

ด้วยขั้นตอนง่ายๆ ห้าขั้นตอนนี้ คุณสามารถขอใบรับการอ่านอีเมลเมื่อส่งอีเมลโดยใช้ C# และ Aspose.Email สำหรับ .NET คุณลักษณะนี้เพิ่มความมั่นใจอีกชั้นให้กับการสื่อสารทางอีเมลของคุณ เพื่อให้มั่นใจว่าคุณจะทราบเมื่อข้อความสำคัญของคุณถูกอ่าน

## กรอกซอร์สโค้ดให้สมบูรณ์
```csharp
// สร้างอินสแตนซ์ของคลาส MailMessage
MailMessage message = new MailMessage();

// ระบุฟิลด์ จาก, ถึง, HtmlBody, DeliveryNotificationOptions
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// สร้างอินสแตนซ์ของคลาส SmtpClient
SmtpClient client = new SmtpClient();

// ระบุเซิร์ฟเวอร์โฮสต์เมลของคุณ ชื่อผู้ใช้ รหัสผ่าน และหมายเลขพอร์ต
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send จะส่งข้อความนี้
	client.Send(message);
	// แสดง 'ส่งข้อความ' เฉพาะในกรณีที่ส่งข้อความสำเร็จเท่านั้น
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการขอใบตอบรับการอ่านอีเมลโดยใช้ C# กับ Aspose.Email สำหรับ .NET การติดตามอีเมลเป็นเครื่องมือที่มีประสิทธิภาพเพื่อให้แน่ใจว่าข้อความของคุณจะถูกส่งและอ่านโดยผู้รับที่ต้องการ โดยเฉพาะอย่างยิ่งในสภาพแวดล้อมแบบมืออาชีพ ด้วยการทำตามขั้นตอนที่อธิบายไว้ที่นี่ คุณจะสามารถใช้ฟังก์ชันนี้ในแอปพลิเคชันอีเมลของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย (FAQ)

1. ### ใบตอบรับการอ่านอีเมลมีจุดประสงค์อะไร?
   ใบตอบรับการอ่านอีเมลเป็นการยืนยันว่าผู้รับเปิดและอ่านอีเมลแล้ว มักใช้เพื่อติดตามข้อความที่สำคัญหรือมีความละเอียดอ่อนด้านเวลา

2. ### ผู้รับสามารถปิดใช้ใบตอบรับการอ่านอีเมลได้หรือไม่
   ใช่ โปรแกรมรับส่งอีเมลมักจะอนุญาตให้ผู้ใช้ปิดการส่งใบรับการอ่าน ดังนั้นจึงไม่รับประกันว่าคุณจะได้รับเสมอไป

3. ### ใบตอบรับการอ่านอีเมลเป็นคุณสมบัติมาตรฐานในไคลเอนต์อีเมลทั้งหมดหรือไม่
   ไม่ ใบตอบรับการอ่านอีเมลไม่ได้รับการสนับสนุนในระดับสากล ไม่ว่าจะใช้งานได้หรือไม่นั้นขึ้นอยู่กับโปรแกรมรับส่งเมลและการตั้งค่าของผู้รับ

4. ### เป็นไปได้หรือไม่ที่จะติดตามเมื่อมีการเปิดอีเมลบนอุปกรณ์มือถือ?
   โดยทั่วไปการติดตามอีเมลจะขึ้นอยู่กับไคลเอนต์อีเมลของผู้รับและการตั้งค่า ดังนั้นจึงอาจทำงานหรืออาจไม่ทำงานบนอุปกรณ์เคลื่อนที่ ขึ้นอยู่กับปัจจัยต่างๆ

5. ### มีข้อควรพิจารณาด้านความเป็นส่วนตัวเมื่อใช้ใบตอบรับการอ่านอีเมลหรือไม่
   ใช่ มีข้อกังวลด้านความเป็นส่วนตัวที่เกี่ยวข้องกับการติดตามอีเมล ผู้รับบางรายอาจพิจารณาว่าเป็นการล่วงละเมิด ดังนั้นจึงจำเป็นอย่างยิ่งที่จะต้องใช้คุณสมบัตินี้อย่างรับผิดชอบและเคารพการตั้งค่าความเป็นส่วนตัว
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
