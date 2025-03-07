---
title: การลงนามอีเมลด้วย DKIM โดยใช้รหัส C#
linktitle: การลงนามอีเมลด้วย DKIM โดยใช้รหัส C#
second_title: Aspose.Email .NET API การประมวลผลอีเมล
description: เรียนรู้การรักษาความปลอดภัยอีเมลด้วย DKIM โดยใช้ C# และ Aspose.Email สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด เพิ่มความน่าเชื่อถือและความถูกต้องของอีเมล
weight: 11
url: /th/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การลงนามอีเมลด้วย DKIM โดยใช้รหัส C#


ในโลกดิจิทัลปัจจุบัน การรับรองความถูกต้องและความสมบูรณ์ของการสื่อสารทางอีเมลถือเป็นสิ่งสำคัญยิ่ง วิธีหนึ่งในการบรรลุเป้าหมายนี้คือการใช้ลายเซ็น DomainKeys Identified Mail (DKIM) ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีลงนามอีเมลด้วย DKIM โดยใช้ C# และไลบรารี Aspose.Email สำหรับ .NET อันทรงพลัง

## ข้อมูลเบื้องต้นเกี่ยวกับ DKIM

### ดีคิมคืออะไร?
DKIM ย่อมาจาก DomainKeys Identified Mail เป็นวิธีการตรวจสอบความถูกต้องของอีเมลที่ช่วยให้ผู้ส่งลงนามในอีเมลแบบดิจิทัล โดยมีลายเซ็นเข้ารหัสที่ตรวจสอบความถูกต้องของอีเมล

### เหตุใด DKIM จึงมีความสำคัญ
DKIM ช่วยในการป้องกันการปลอมแปลงอีเมลและการโจมตีแบบฟิชชิ่งโดยทำให้แน่ใจว่าอีเมลขาเข้ามาจากแหล่งที่ถูกต้องและไม่ได้รับการแก้ไขระหว่างการส่ง

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Email for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Email for .NET ในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/email/net/).

2. รหัสส่วนตัว DKIM: คุณจะต้องมีรหัสส่วนตัว DKIM เพื่อลงนามอีเมลของคุณ ตรวจสอบให้แน่ใจว่าคุณมีมันพร้อม 

## ขั้นตอนที่ 1: เริ่มต้นพารามิเตอร์ DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

ในขั้นตอนนี้ เราจะเริ่มต้นพารามิเตอร์ DKIM เราโหลดคีย์ส่วนตัวจากไฟล์ ระบุตัวเลือกและโดเมน และแสดงรายการส่วนหัวที่ควรรวมไว้ในลายเซ็น DKIM

## ขั้นตอนที่ 2: สร้างและเตรียมอีเมล

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

ที่นี่เราสร้างอินสแตนซ์ของ`MailMessage` และตั้งค่าผู้ส่ง ผู้รับ หัวเรื่อง และเนื้อหาของอีเมล

## ขั้นตอนที่ 3: ลงชื่ออีเมล

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

ตอนนี้ เราลงนามอีเมลโดยใช้พารามิเตอร์ DKIM และคีย์ส่วนตัวที่เราเริ่มต้นไว้ก่อนหน้านี้

## ขั้นตอนที่ 4: ส่งอีเมลที่ลงนาม

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // รหัสการล้างข้อมูล ถ้ามี
}
```
 ในขั้นตอนนี้ เราจะส่งอีเมลที่ลงนามโดยใช้ไคลเอ็นต์ SMTP ให้แน่ใจว่าคุณเปลี่ยน`"your.email@gmail.com"` และ`"your.password"` ด้วยข้อมูลรับรอง Gmail ของคุณ

## กรอกซอร์สโค้ด
```csharp

string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP()+ "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");

MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);

try
{
	SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
	client.Send(signedMsg);                
}
finally
{}
```

## บทสรุป

การลงนามอีเมลด้วย DKIM เป็นขั้นตอนสำคัญในการรับรองความปลอดภัยและความถูกต้องของการสื่อสารทางอีเมลของคุณ ด้วยความช่วยเหลือของ Aspose.Email สำหรับ .NET และ C# คุณจะสามารถใช้ลายเซ็น DKIM ในกระบวนการส่งอีเมลของคุณได้อย่างง่ายดาย

---

## คำถามที่พบบ่อย

### คำถามที่ 1: DKIM คืออะไร และเหตุใดจึงสำคัญสำหรับการรักษาความปลอดภัยอีเมล

DKIM ย่อมาจาก DomainKeys Identified Mail และมีความสำคัญต่อการรักษาความปลอดภัยอีเมล เนื่องจากจะตรวจสอบความถูกต้องของข้อความอีเมล ป้องกันการปลอมแปลงและฟิชชิ่ง

### คำถามที่ 2: ฉันจะรับคีย์ส่วนตัว DKIM ได้อย่างไร

คุณสามารถรับคีย์ส่วนตัว DKIM ผ่านทางผู้ให้บริการอีเมลของคุณ หรือโดยการสร้างคีย์ส่วนตัวโดยใช้เครื่องมือเข้ารหัส

### คำถามที่ 3: ฉันสามารถใช้ Aspose.Email สำหรับ .NET กับผู้ให้บริการอีเมลรายอื่นนอกเหนือจาก Gmail ได้หรือไม่

ได้ Aspose.Email สำหรับ .NET สามารถใช้ได้กับผู้ให้บริการอีเมลหลายราย ไม่จำกัดเฉพาะ Gmail

### คำถามที่ 4: ฉันควรรวมส่วนหัวใดไว้ในลายเซ็น DKIM

ส่วนหัวทั่วไปที่จะรวมไว้ในลายเซ็น DKIM ได้แก่ "จาก" "หัวเรื่อง" และส่วนหัวอื่นๆ ที่มีความสำคัญสำหรับการตรวจสอบสิทธิ์อีเมล

### คำถามที่ 5: DKIM เป็นวิธีเดียวในการตรวจสอบสิทธิ์อีเมลหรือไม่

ไม่ มีวิธีอื่นๆ เช่น SPF และ DMARC ที่ใช้ร่วมกับ DKIM เพื่อเพิ่มความปลอดภัยให้กับอีเมล
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
