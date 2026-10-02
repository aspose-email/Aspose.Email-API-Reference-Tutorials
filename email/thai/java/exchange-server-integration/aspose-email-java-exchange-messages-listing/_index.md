---
date: '2026-10-02'
description: เรียนรู้วิธีเชื่อมต่อ Exchange และแสดงรายการโฟลเดอร์สาธารณะของ Exchange
  ด้วย Aspose.Email for Java คู่มือแบบขั้นตอนนี้แสดงการพึ่งพา Maven และการตั้งค่าแบบไม่ต้องเขียนโค้ด
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: เรียนรู้วิธีเชื่อมต่อ Exchange และแสดงรายการโฟลเดอร์สาธารณะของ Exchange
  ด้วย Aspose.Email for Java คู่มือนี้ครอบคลุมการพึ่งพา Maven, การจัดการลิขสิทธิ์,
  และการดึงข้อความแบบเรียกซ้ำ
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: วิธีเชื่อมต่อ Exchange และแสดงรายการโฟลเดอร์สาธารณะใน Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: วิธีเชื่อมต่อ Exchange และแสดงรายการโฟลเดอร์สาธารณะใน Java
url: /th/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเชื่อมต่อ Exchange และแสดงรายการโฟลเดอร์สาธารณะใน Java

## บทนำ
ในองค์กรสมัยใหม่ การเข้าถึงกล่องเมล Microsoft Exchange อย่างโปรแกรมมิ่งทำให้คุณสามารถอัตโนมัติการเก็บถาวร การตรวจสอบ และงานรายงานได้ การสอนนี้จะแสดง **วิธีเชื่อมต่อ exchange** ด้วย Aspose.Email for Java และจากนั้น **แสดงรายการโฟลเดอร์สาธารณะของ Exchange** อย่างเรียงลำดับ คุณจะได้เห็นการพึ่งพา Maven ที่จำเป็น ขั้นตอนการขอใบอนุญาต และลำดับการเรียก API อย่างแม่นยำ — ไม่ต้องใช้ไลบรารีเพิ่มเติม เมื่อเสร็จสิ้น คุณจะสามารถดึงข้อความจากโฟลเดอร์สาธารณะใดก็ได้และบันทึกลงเครื่องได้

## คำตอบอย่างรวดเร็ว
- **ขั้นตอนแรกคืออะไร?** เพิ่มการพึ่งพา Aspose.Email Maven ลงใน `pom.xml` ของคุณ  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่ — ใช้ใบอนุญาตชั่วคราวสำหรับการประเมินหรือซื้อใบอนุญาตเต็มสำหรับการใช้งานจริง  
- **คลาสใดสร้างการเชื่อมต่อ?** `ExchangeClient` (หรือ `ImapClient` สำหรับ IMAP) จัดการการตรวจสอบสิทธิ์และการสื่อสารกับเซิร์ฟเวอร์  
- **ฉันสามารถแสดงรายการโฟลเดอร์ย่อยโดยอัตโนมัติได้หรือไม่?** ใช่ — ใช้เมธอด `listSubFolders` แบบเรียกซ้ำที่ API ให้มา  
- **วิธีนี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** วัตถุคลไอเอนท์ไม่ปลอดภัยต่อเธรด; ควรสร้างอินสแตนซ์แยกสำหรับแต่ละเธรดเมื่อทำงานพร้อมกัน

## อะไรคือวิธีเชื่อมต่อ exchange?
**วิธีเชื่อมต่อ exchange** คือกระบวนการตรวจสอบสิทธิ์แอปพลิเคชัน Java กับเซิร์ฟเวอร์ Microsoft Exchange ที่อยู่ในเครื่องหรือบนคลาวด์ เพื่อให้คุณสามารถเรียก API เช่น การนับโฟลเดอร์หรือการดึงข้อความได้ Aspose.Email ทำให้โปรโตคอล EWS/IMAP พื้นฐานเป็นนามธรรม ให้คุณมีโมเดลอ็อบเจ็กต์เดียวที่สอดคล้องกัน

## ทำไมต้องแสดงรายการโฟลเดอร์สาธารณะของ Exchange?
การแสดงรายการโฟลเดอร์สาธารณะทำให้คุณมองเห็นโครงสร้างลำดับชั้นที่องค์กรใช้สำหรับกล่องเมลที่แชร์ รายการกระจาย และที่เก็บข้อมูลระยะยาว Aspose.Email สามารถนับ **โฟลเดอร์สาธารณะกว่า 50+** ในการเรียกเดียวและรองรับการประมวลผลกล่องเมลหลายร้อยหน้าโดยไม่ต้องโหลดทั้งสโตร์เข้าสู่หน่วยความจำ ซึ่งช่วยลดการใช้ RAM ได้ถึง 70 %

## ข้อกำหนดเบื้องต้น
- **Aspose.Email for Java** — เวอร์ชัน 25.4 หรือใหม่กว่า (รุ่นเสถียรล่าสุด)  
- **Java Development Kit (JDK)** — JDK 11 หรือใหม่กว่า ติดตั้งและตั้งค่า `JAVA_HOME` แล้ว  
- **Maven** — สำหรับการจัดการการพึ่งพาและการสร้างอัตโนมัติ  
- ความรู้พื้นฐานเกี่ยวกับไวยากรณ์ Java และแนวคิด Exchange (กล่องเมล, โฟลเดอร์, EWS)

## การตั้งค่า Aspose.Email สำหรับ Java
เพื่อรวมไลบรารีนี้ ให้เพิ่มการพึ่งพา Maven ลงใน `pom.xml` ของโปรเจกต์ นี่คือ **maven dependency aspose email** ที่คุณต้องการ

### การพึ่งพา Maven
เพิ่มโค้ดต่อไปนี้ภายในแท็ก `<dependencies>` ของ `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ขั้นตอนการรับใบอนุญาต
Aspose.Email ต้องการใบอนุญาตที่ถูกต้องเพื่อใช้ฟีเจอร์เต็มรูปแบบ:

- **Free trial** – ดาวน์โหลดใบอนุญาตชั่วคราวจาก [Aspose website](https://purchase.aspose.com/temporary-license/) เพื่อประเมิน API  
- **Purchase** – ซื้อใบอนุญาตเชิงพาณิชย์ผ่านพอร์ทัล Aspose สำหรับการใช้งานในสภาพแวดล้อมการผลิต

#### การเริ่มต้นพื้นฐาน
หลังจาก Maven ดึงแพ็กเกจและคุณมีไฟล์ใบอนุญาตแล้ว ให้วางไฟล์ `.lic` ไว้บน classpath และเริ่มต้นไลบรารี:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## คู่มือการดำเนินการ
เราจะเดินผ่านแต่ละบล็อกฟังก์ชัน ตอบคำถามสำคัญด้วยย่อหน้าสั้น ๆ ก่อนเข้าสู่ขั้นตอนละเอียด

### วิธีเชื่อมต่อ Exchange?
โหลด `ExchangeClient` ด้วย URL ของเซิร์ฟเวอร์, ข้อมูลประจำตัวผู้ใช้, และโดเมน แล้วเรียก `connect()` คลไอเอนท์จะสร้างเซสชัน HTTPS กับ Exchange Web Services (EWS) และตรวจสอบข้อมูลประจำตัว หากการเชื่อมต่อล้มเหลว API จะโยน `AuthenticationException` ที่มีรหัสสถานะ HTTP เพื่อช่วยแก้ปัญหาอย่างรวดเร็ว  
`ExchangeClient` คือคลาสของ Aspose.Email ที่จัดการการเชื่อมต่อกับ Exchange Web Services

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### วิธีแสดงรายการโฟลเดอร์สาธารณะของ Exchange?
เรียก `client.listPublicFolders()` เพื่อรับคอลเลกชันของอ็อบเจ็กต์ `FolderInfo` ที่แสดงโฟลเดอร์สาธารณะระดับบนแต่ละรายการ เมธอดนี้คืนข้อมูลเมตาเช่น ชื่อโฟลเดอร์, จำนวนรายการทั้งหมด, และตัวระบุที่ใช้ในการเรียกต่อไป การเรียกนี้ใช้เวลาน้อยกว่า 2 วินาทีสำหรับการปรับใช้ทั่วไปในองค์กรที่มีโฟลเดอร์สูงสุด 500 โฟลเดอร์  
`listPublicFolders()` คืนคอลเลกชันของอ็อบเจ็กต์ `FolderInfo`  
`FolderInfo` เก็บข้อมูลเมตาเช่น ชื่อที่แสดงและจำนวนรายการ

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### วิธีแสดงข้อมูลโฟลเดอร์?
วนลูปผ่านคอลเลกชัน `FolderInfo` และพิมพ์ `displayName` กับ `subFolderCount` ภาพรวมสั้น ๆ นี้ช่วยให้คุณเข้าใจโครงสร้างลำดับชั้นก่อนทำการสำรวจลึก สำหรับองค์กรขนาดใหญ่ API สามารถแบ่งหน้าผลลัพธ์ได้ 100 โฟลเดอร์ต่อหน้า เพื่อลดการใช้หน่วยความจำ

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### วิธีแสดงรายการข้อความจากโฟลเดอร์?
เรียก `client.listMessages(folderId)` โดยที่ `folderId` คือรหัสที่ได้จากขั้นตอนก่อนหน้า เมธอดนี้คืนรายการของอ็อบเจ็กต์ `MessageInfo` ที่มีหัวเรื่อง, ผู้ส่ง, และวันที่รับ คุณสามารถจำกัดผลลัพธ์ด้วย `maxCount` เพื่อหลีกเลี่ยงการทำให้ไคลเอนท์หนักเกินไปเมื่อประมวลผลโฟลเดอร์ขนาดใหญ่มาก  
`listMessages(folderId)` คืนรายการของอ็อบเจ็กต์ `MessageInfo`  
`MessageInfo` มีคุณสมบัติพื้นฐานของอีเมล เช่น หัวเรื่อง, ผู้ส่ง, และวันที่รับ

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### วิธีดึงและบันทึกข้อความ?
สำหรับแต่ละ `MessageInfo` ใช้ `client.fetchMessage(messageId)` เพื่อดาวน์โหลดเนื้อหา MIME เต็มรูปแบบ จากนั้นเขียนอาร์เรย์ไบต์ลงไฟล์ `.eml` บนดิสก์ API จะสตรีมเนื้อหา ดังนั้นข้อความขนาด 100 MB ก็สามารถจัดการได้โดยไม่ต้องโหลดทั้งหมดเข้าสู่หน่วยความจำ  
`fetchMessage(messageId)` ดาวน์โหลดเนื้อหา MIME เต็มของอีเมลที่ระบุ

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### วิธีแสดงรายการข้อความจากโฟลเดอร์ย่อยแบบเรียกซ้ำ?
ทำการท่องแบบลึก‑ก่อน (depth‑first): เริ่มจากโฟลเดอร์ระดับบน, แสดงรายการโฟลเดอร์ย่อยด้วย `client.listSubFolders(parentId)` แล้วเรียกขั้นตอนการแสดงรายการข้อความเดียวกันสำหรับแต่ละโฟลเดอร์ลูก รูปแบบนี้ทำให้ข้อความทุกข้อความในต้นไม้โฟลเดอร์สาธารณะถูกประมวลผล ความลึกของการเรียกซ้ำจำกัดแค่โครงสร้างโฟลเดอร์ของเซิร์ฟเวอร์ (โดยทั่วไป < 20 ระดับ)  
`listSubFolders(parentId)` คืนโฟลเดอร์ลูกโดยตรงของโฟลเดอร์ที่ระบุ

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## การประยุกต์ใช้ในทางปฏิบัติ
สถานการณ์จริงที่เวิร์กโฟลว์นี้โดดเด่น:

1. **การเก็บถาวรอีเมลอัตโนมัติ** – ดึงข้อความจากโฟลเดอร์สาธารณะทั้งหมดเป็นระยะและเก็บไว้ในคลังเก็บที่สอดคล้องตามกฎระเบียบ  
2. **โซลูชันสำรองข้อมูล** – ทำสำเนาโฟลเดอร์สาธารณะของ Exchange ไปยังระบบไฟล์ที่ปลอดภัยหรือคลาวด์บัคเก็ต เพื่อรับประกันความซ้ำซ้อนของข้อมูล  
3. **ไคลเอนท์อีเมลแบบกำหนดเอง** – สร้างตัวดูแบบเบาที่แสดงเฉพาะโฟลเดอร์และข้อความที่ต้องการ ลดความซับซ้อนของ UI

## ข้อควรพิจารณาด้านประสิทธิภาพ
เมื่อขยายเป็นพันโฟลเดอร์และล้านข้อความ ให้คำนึงถึงเคล็ดลับต่อไปนี้:

- **การใช้พูลการเชื่อมต่อ** – ใช้ `ExchangeClient` ตัวเดียวหลายงานแทนการสร้างไคลเอนท์ใหม่สำหรับแต่ละโฟลเดอร์  
- **การโหลดแบบ Lazy** – ขอเมตาเดต้าเท่านั้นที่ต้องการ (`listMessages` พร้อมพารามิเตอร์ `maxCount`) แล้วดึงเนื้อหาเต็มเมื่อจำเป็น  
- **การทำลายอ็อบเจ็กต์** – เรียก `client.dispose()` หลังจากรันแบตช์เพื่อปล่อยการเชื่อมต่อ HTTP และบัฟเฟอร์ท้องถิ่น  
- **การประมวลผลแบบขนาน** – แบ่งโฟลเดอร์ระดับบนให้หลายเธรด แต่ละเธรดมีไคลเอนท์ของตนเอง เพื่อใช้ประโยชน์จาก CPU หลายคอร์อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้โค้ดนี้กับ Exchange Online (Office 365) ได้หรือไม่?**  
A: ใช่ ให้ใช้ endpoint EWS ของ Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) และใช้การตรวจสอบแบบสมัยใหม่ (OAuth) – Aspose.Email รองรับโทเคน OAuth โดยตรง

**Q: ถ้าโฟลเดอร์มีข้อความมากกว่า 10 000 รายการจะทำอย่างไร?**  
A: ใช้ overload ของ `listMessages` ที่รับพารามิเตอร์ `skip` และ `take` เพื่อแบ่งหน้า ผลลัพธ์จะอยู่ในระดับหน่วยความจำที่ควบคุมได้

**Q: มีขีดจำกัดขนาดของอีเมลเดียวที่สามารถดาวน์โหลดได้หรือไม่?**  
A: API สตรีมเนื้อหา ดังนั้นข้อความขนาดสูงสุดถึง 150 MB จะรองรับได้โดยไม่กระทบขีดจำกัด heap ของ Java ตราบใดที่ JVM มีหน่วยความจำเนทีฟเพียงพอ

**Q: ฉันต้องจัดการใบรับรอง SSL ด้วยตนเองหรือไม่?**  
A: โดยค่าเริ่มต้น Aspose.Email เชื่อถือ keystore เริ่มต้นของ Java หากเซิร์ฟเวอร์ Exchange ใช้ใบรับรอง self‑signed ให้นำเข้าไปยัง truststore ของ JVM หรือกำหนด `client.setEnableSslVerification(false)` สำหรับการทดสอบเท่านั้น

**Q: ฉันจะบันทึกการทำงานเพื่อการตรวจสอบได้อย่างไร?**  
A: เปิดการบันทึกในตัวของ Aspose.Email โดยกำหนด `Logger.setLevel(Level.INFO)` และส่งออกผลลัพธ์ไปยังไฟล์หรือระบบมอนิเตอร์

## สรุป
ตอนนี้คุณมีสูตรครบถ้วนสำหรับ **วิธีเชื่อมต่อ exchange** และแสดงรายการข้อความจากโฟลเดอร์สาธารณะแบบเรียกซ้ำโดยใช้ Aspose.Email for Java ขั้นตอนครอบคลุมการตั้งค่า Maven, การขอใบอนุญาต, การเชื่อมต่อ, การนับโฟลเดอร์, การดึงข้อความ, และการปรับจูนประสิทธิภาพ คุณสามารถต่อยอดโดยเชื่อมต่อกับฐานข้อมูล, ที่เก็บบนคลาวด์, หรือสายงานวิเคราะห์แบบกำหนดเอง เพื่อให้ตรงกับความต้องการเฉพาะขององค์กรคุณ

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเชื่อมต่อกับเซิร์ฟเวอร์ Exchange ด้วย Aspose.Email ใน Java: คู่มือขั้นตอน](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [วิธีเชื่อมต่อและแสดงรายการโฟลเดอร์เซิร์ฟเวอร์ Exchange ด้วย Aspose.Email for Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [การจัดการโฟลเดอร์เซิร์ฟเวอร์ Exchange ด้วย Aspose.Email for Java: คู่มือครบวงจร](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}