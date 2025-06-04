---
"date": "2025-05-29"
"description": "เรียนรู้วิธีการกำหนดค่าไคลเอนต์ SMTP ด้วย Aspose.Email สำหรับ Java และการส่งต่ออีเมลอย่างมีประสิทธิภาพ เหมาะสำหรับนักพัฒนาในแอปพลิเคชันระดับองค์กร"
"title": "การส่งต่ออีเมล SMTP โดยใช้ Aspose.Email สำหรับ Java - คู่มือฉบับสมบูรณ์"
"url": "/th/java/smtp-client-operations/smtp-email-forwarding-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การส่งต่ออีเมล SMTP โดยใช้ Aspose.Email สำหรับ Java: คู่มือฉบับสมบูรณ์

ในยุคดิจิทัล การจัดการอีเมลด้วยโปรแกรมถือเป็นสิ่งสำคัญสำหรับนักพัฒนาที่ทำงานในระบบการสื่อสารขององค์กรหรือลูกค้า คู่มือนี้ให้คำแนะนำโดยละเอียดเกี่ยวกับการตั้งค่าไคลเอนต์ SMTP ด้วย Aspose.Email สำหรับ Java เพื่อส่งต่ออีเมลอย่างมีประสิทธิภาพโดยไม่ต้องใช้ `MailMessage`มาสำรวจกันว่าเครื่องมืออันทรงพลังนี้สามารถตอบสนองความต้องการการจัดการอัตโนมัติอีเมลของคุณได้อย่างไร

## สิ่งที่คุณจะได้เรียนรู้:
- การกำหนดค่าไคลเอนต์ SMTP ด้วย Aspose.Email สำหรับ Java
- การจัดการผู้รับอีเมลโดยใช้คอลเลกชัน
- การส่งต่ออีเมลโดยตรงจากสตรีมไฟล์

**ข้อกำหนดเบื้องต้น:** ก่อนจะดำเนินการ ให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้พร้อมแล้ว เพื่อปฏิบัติตามบทช่วยสอนนี้ได้อย่างมีประสิทธิภาพ

### ข้อกำหนดเบื้องต้น
หากต้องการดำเนินการตามคู่มือนี้ให้สำเร็จ โปรดแน่ใจว่าคุณมี:

- **ห้องสมุดและสิ่งที่ต้องพึ่งพา:**
  - Aspose.Email สำหรับ Java เวอร์ชัน 25.4 ขึ้นไป
  
- **การตั้งค่าสภาพแวดล้อม:**
  - JDK (Java Development Kit) ที่เข้ากันได้ โดยควรเป็น JDK 16 ตามที่ระบุโดยตัวจำแนกประเภทในการอ้างอิง Maven ของเรา
- **ข้อกำหนดเบื้องต้นของความรู้:**
  - ความเข้าใจพื้นฐานเกี่ยวกับโปรโตคอล SMTP
  - ความคุ้นเคยกับการเขียนโปรแกรม Java

## การตั้งค่า Aspose.Email สำหรับ Java

การรวม Aspose.Email เข้ากับโปรเจ็กต์ของคุณนั้นทำได้ง่าย ๆ โดยใช้ Maven เพิ่มการอ้างอิงต่อไปนี้ให้กับโปรเจ็กต์ของคุณ `pom.xml` ไฟล์:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การขอใบอนุญาต
Aspose.Email เสนอใบอนุญาตทดลองใช้งานฟรีเพื่อทดสอบความสามารถทั้งหมดโดยไม่มีข้อจำกัด คุณสามารถรับใบอนุญาตได้ดังนี้:

1. **ทดลองใช้งานฟรี:** เยี่ยม [หน้าทดลองใช้งานฟรีของ Aspose](https://releases.aspose.com/email/java/) เพื่อดาวน์โหลดและเริ่มต้นด้วยเวอร์ชันประเมินผล
2. **ใบอนุญาตชั่วคราว:** สำหรับการทดสอบแบบขยายเวลา ให้ขอใบอนุญาตชั่วคราวผ่านทาง [หน้าคำร้องขอใบอนุญาต](https://purchase-aspose.com/temporary-license/).
3. **ซื้อ:** หากคุณพบว่า Aspose.Email มีประโยชน์สำหรับโครงการของคุณ โปรดพิจารณาซื้อใบอนุญาตเต็มรูปแบบที่ [หน้าการซื้อของ Aspose](https://purchase-aspose.com/buy).

### การเริ่มต้นและการตั้งค่าเบื้องต้น

เมื่อรวม Aspose.Email ไว้ในโครงการของคุณแล้ว ให้เริ่มต้นส่วนประกอบที่จำเป็น:

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com"; // ที่อยู่เซิร์ฟเวอร์ SMTP ของคุณ
String username = "username";    // ชื่อผู้ใช้สำหรับการยืนยันตัวตน
int smtpPort = 587;              // หมายเลขพอร์ต โดยทั่วไปคือ 587 สำหรับ TLS/STARTTLS
String password = "password";    // รหัสผ่านสำหรับการยืนยันตัวตน

// สร้างอินสแตนซ์ของ SmtpClient ด้วยข้อมูลประจำตัวที่ระบุ
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

## คู่มือการใช้งาน

### การกำหนดค่าไคลเอนต์ SMTP
หัวข้อนี้จะแนะนำคุณเกี่ยวกับการกำหนดค่าไคลเอนต์ SMTP สำหรับการส่งอีเมล โดยการตั้งค่า `SmtpClient`คุณสร้างการเชื่อมต่อกับเซิร์ฟเวอร์อีเมลของคุณโดยใช้ข้อมูลประจำตัวและตัวเลือกความปลอดภัยที่ระบุ

#### ภาพรวม
การกำหนดค่าเกี่ยวข้องกับการระบุโฮสต์ SMTP พอร์ต ชื่อผู้ใช้ รหัสผ่าน และตัวเลือกความปลอดภัย โดยทั่วไปคือ SSLExplicit สำหรับการเชื่อมต่อที่ปลอดภัย

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com";
String username = "username";
int smtpPort = 587;
String password = "password";

// เริ่มต้น SmtpClient ด้วยข้อมูลประจำตัวที่ระบุ
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

### การรวบรวมผู้รับอีเมล์
การจัดการรายชื่อผู้รับได้รับการปรับปรุงให้มีประสิทธิภาพยิ่งขึ้นโดยใช้ `MailAddressCollection`ซึ่งช่วยให้คุณสามารถเพิ่มอีเมล์หลาย ๆ อันได้อย่างง่ายดาย

#### ภาพรวม
คอลเลกชันนี้ช่วยให้สามารถจัดเก็บและจัดการอีเมลของผู้รับเพื่อดำเนินการส่งต่อหรือส่ง

```java
import com.aspose.email.MailAddressCollection;

// สร้างอินสแตนซ์ MailAddressCollection ใหม่
MailAddressCollection recipients = new MailAddressCollection();

// เพิ่มผู้รับหลายรายลงในคอลเลกชั่น
recipients.add("to1@domain.com");
recipients.add("to2@domain.com");
```

### การส่งต่ออีเมล์โดยไม่ใช้ MailMessage
คุณสมบัติอันทรงพลังนี้ช่วยให้คุณสามารถส่งต่อไฟล์อีเมลโดยตรงโดยใช้ `FileInputStream` และ `SmtpClient`-

#### ภาพรวม
แทนที่จะสร้างสิ่งใหม่ `MailMessage`วิธีนี้ใช้ไฟล์ EML ที่มีอยู่ ทำให้มีประสิทธิภาพในการส่งต่อจำนวนมาก

```java
import java.io.FileInputStream;
import java.io.IOException;

String fileName = "YOUR_DOCUMENT_DIRECTORY/test.eml"; // เส้นทางไปยังไฟล์ EML ของคุณ

// เปิด FileInputStream สำหรับไฟล์อีเมล
FileInputStream fos = new FileInputStream(fileName);

try {
    // ส่งต่ออีเมลโดยใช้อินสแตนซ์ SmtpClient และคอลเลกชันผู้รับ
    client.forward("Sender@domain.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}