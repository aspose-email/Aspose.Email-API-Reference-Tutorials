---
date: '2026-06-18'
description: เรียนรู้วิธีใช้ Aspose.Email for Java เพื่อดึงอีเมลจาก Zimbra TGZ archives.
  รวมการตั้งค่า Maven dependency ของ Aspose Email และตัวอย่างการใช้งานจริง.
keywords:
- how to use aspose.email
- maven dependency aspose email
- extract emails from zimbra tgz
schemas:
- author: Aspose
  dateModified: '2026-06-18'
  description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  headline: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  type: TechArticle
- description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  name: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  steps:
  - name: Define File Path
    text: Specify the absolute or relative path to the TGZ file you want to process.
  - name: Initialize TgzReader
    text: Create a `TgzReader` instance using the file path. *Direct answer:* Initializing
      `TgzReader` opens the archive and prepares it for sequential message extraction.
  - name: Extract Emails
    text: Iterate through each stored message, retrieve its folder location, and obtain
      a `MailMessage` object. - `readNextMessage()` returns `false` when no more messages
      remain. - `getCurrentDirectory()` shows the internal folder path inside the
      TGZ. - `getCurrentMessage()` gives you a fully parsed `MailMes
  type: HowTo
- questions:
  - answer: JDK 16+, Maven, and the `com.aspose:aspose-email` Maven artifact.
    question: What are the prerequisites for using Aspose.Email for Java?
  - answer: Purchase a license or request a temporary one via the [Aspose purchase
      page](https://purchase.aspose.com/buy).
    question: How can I obtain a license for production use?
  - answer: Verify the file exists, the path is correctly escaped for Java strings,
      and the process has read permissions.
    question: My TGZ path seems invalid—what should I check?
  - answer: Yes, the API is thread‑safe; you can instantiate separate `TgzReader`
      objects per thread.
    question: Does Aspose.Email support multi‑threaded extraction?
  - answer: Save each `MailMessage` as EML, JSON, or XML using `SaveOptions`, then
      feed the files into your downstream pipelines.
    question: How do I integrate extracted emails with other systems?
  type: FAQPage
title: 'วิธีใช้ Aspose.Email for Java: ดึงอีเมลจาก Zimbra TGZ archives'
url: /th/java/email-parsing-analysis/extract-emails-zimbra-tgz-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีใช้ Aspose.Email สำหรับ Java: ดึงอีเมลจากไฟล์เก็บ Zimbra TGZ

## บทนำ

หากคุณต้องการ **how to use Aspose.Email** เพื่อดึงข้อความที่เก็บไว้ในไฟล์เก็บ Zimbra TGZ คุณมาถูกที่แล้ว ในคู่มือนี้เราจะอธิบายขั้นตอนทั้งหมด—from การตั้งค่า Maven ไปจนถึงการอ่านแต่ละอีเมล—เพื่อให้คุณสามารถทำงานสำรองข้อมูล การย้ายข้อมูล หรือการวิเคราะห์เชิงนิติวิทยาศาสตร์โดยอัตโนมัติได้อย่างมั่นใจ เมื่ออ่านจบคุณจะเข้าใจวิธีตั้งค่าห้องสมุด การวนลูปข้อความ และการบูรณาการผลลัพธ์เข้ากับกระบวนการทำงานของคุณ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ดึงอีเมล Zimbra TGZ คืออะไร?** Aspose.Email for Java.
- **Maven artifact ที่ต้องการคืออะไร?** `com.aspose:aspose-email`.
- **เวอร์ชัน Java ขั้นต่ำ?** JDK 16 หรือใหม่กว่า.
- **สามารถประมวลผลไฟล์เก็บขนาดใหญ่ได้หรือไม่?** ใช่ การประมวลผลแบบแบตช์ช่วยให้ใช้หน่วยความจำน้อย.
- **ต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่ ไลเซนส์ Aspose.Email แบบเต็มหรือแบบชั่วคราว.

## ข้อกำหนดเบื้องต้น

- **Java Development Kit (JDK)** 16 หรือสูงกว่า.
- **Maven** สำหรับการจัดการ dependencies.
- **Aspose.Email for Java** v25.4 (หรือใหม่กว่า) – เราจะเพิ่ม dependency ของ Maven ต่อไป.
- เข้าถึงไฟล์เก็บ Zimbra TGZ ที่คุณต้องการวิเคราะห์.

## วิธีเพิ่ม Maven dependency ของ Aspose.Email?

เพื่อรวม Aspose.Email ในโปรเจกต์ Maven ของคุณ ให้เพิ่ม snippet ของ dependency ลงในส่วน `<dependencies>` ของไฟล์ `pom.xml` ของคุณ Maven จะทำการ resolve artifact ดาวน์โหลด JAR ที่จำเป็นและทำให้ไลบรารีพร้อมใช้งานใน classpath ของคุณ ทำให้คุณสามารถเริ่มเขียนโค้ดได้ทันทีโดยไม่ต้องจัดการ JAR ด้วยตนเอง.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
</dependency>
```

*คำตอบโดยตรง:* การเพิ่ม dependency ด้านบนจะดาวน์โหลดไลบรารีโดยอัตโนมัติ ดังนั้นคุณสามารถเริ่มเขียนโค้ดได้โดยไม่ต้องจัดการ JAR ด้วยตนเอง.

## การรับไลเซนส์

Aspose มีเส้นทางไลเซนส์สามแบบ:
- **Free Trial** – ไลเซนส์ชั่วคราวสำหรับการประเมินผล.
- **Temporary License** – การใช้งานระยะสั้นโดยไม่มีข้อจำกัดการประเมิน.
- **Full Purchase** – การใช้งานในผลิตภัณฑ์โดยไม่มีข้อจำกัด.

เยี่ยมชม [Aspose purchase page](https://purchase.aspose.com/buy) เพื่อดูรายละเอียด.

## การเริ่มต้นพื้นฐาน

เพื่อเริ่มใช้ Aspose.Email ให้ import คลาสที่จำเป็นและสร้างบล็อกการตั้งค่าพื้นฐาน.

```java
import com.aspose.email.*;
```

*คำตอบโดยตรง:* หลังจากเพิ่ม import แล้ว คุณสามารถสร้างอ็อบเจ็กต์ Aspose.Email ได้โดยตรงในโค้ด Java ของคุณ.

## คู่มือการใช้งาน

### คลาส TgzReader คืออะไรและทำงานอย่างไร?

คลาส `TgzReader` เป็น Streaming API ของ Aspose.Email สำหรับอ่านไฟล์เก็บ Zimbra TGZ โดยไม่ต้องโหลดไฟล์เก็บทั้งหมดเข้าสู่หน่วยความจำ.

#### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์

ระบุเส้นทางแบบ absolute หรือ relative ไปยังไฟล์ TGZ ที่คุณต้องการประมวลผล.

```java
String tgzPath = "C:/archives/zimbra_backup.tgz";
```

#### ขั้นตอนที่ 2: เริ่มต้น TgzReader

สร้างอินสแตนซ์ของ `TgzReader` โดยใช้เส้นทางไฟล์.

```java
TgzReader tgzReader = new TgzReader(tgzPath);
```

*คำตอบโดยตรง:* การเริ่มต้น `TgzReader` จะเปิดไฟล์เก็บและเตรียมพร้อมสำหรับการดึงข้อความแบบต่อเนื่อง.

#### ขั้นตอนที่ 3: ดึงอีเมล

วนลูปผ่านแต่ละข้อความที่เก็บไว้ ดึงตำแหน่งโฟลเดอร์ของมัน และรับอ็อบเจ็กต์ `MailMessage`.

```java
while (tgzReader.readNextMessage()) {
    String directory = tgzReader.getCurrentDirectory();
    MailMessage message = tgzReader.getCurrentMessage();
    // Process the MailMessage (save, analyze, etc.)
}
tgzReader.dispose();
```

- `readNextMessage()` คืนค่า `false` เมื่อไม่มีข้อความเหลืออยู่.
- `getCurrentDirectory()` แสดงเส้นทางโฟลเดอร์ภายใน TGZ.
- `getCurrentMessage()` ให้ `MailMessage` ที่ถูกแปลงอย่างเต็มรูปแบบ.

*คำตอบโดยตรง:* ลูปด้านบนดึงอีเมลทุกฉบับในไฟล์เก็บ ทำให้คุณสามารถจัดการแต่ละข้อความได้แยกกัน.

### ฉันจะทำให้การจัดการไดเรกทอรีง่ายขึ้นด้วยยูทิลิตี้ของ Aspose.Email อย่างไร?

Aspose.Email มีเมธอดช่วยสร้างเส้นทางระบบไฟล์แบบไดนามิก ด้านล่างเป็นเมธอดยูทิลิตี้สั้น ๆ ที่คุณสามารถใส่ลงในคลาสใดก็ได้.

```java
public static String buildOutputPath(String base, String folder, String fileName) {
    return Paths.get(base, folder, fileName).toString();
}
```

*คำตอบโดยตรง:* ใช้ `buildOutputPath` เพื่อสร้างตำแหน่งออกผลที่สอดคล้องสำหรับไฟล์อีเมลที่บันทึก.

#### การใช้ฟังก์ชันยูทิลิตี้

ผสานยูทิลิตี้กับลูปการดึงข้อมูลเพื่อบันทึกแต่ละอีเมลเป็นไฟล์ EML.

```java
String outputBase = "C:/extracted_emails";
while (tgzReader.readNextMessage()) {
    String dir = tgzReader.getCurrentDirectory();
    MailMessage msg = tgzReader.getCurrentMessage();
    String outPath = buildOutputPath(outputBase, dir, msg.getSubject() + ".eml");
    msg.save(outPath, SaveOptions.getDefaultEml());
}
```

*คำตอบโดยตรง:* โค้ดนี้บันทึกแต่ละข้อความไปยังโฟลเดอร์ที่สะท้อนตำแหน่งต้นฉบับภายในไฟล์ TGZ.

## ทำไมต้องใช้ Aspose.Email สำหรับการดึงข้อมูลจาก Zimbra TGZ?

Aspose.Email ให้โซลูชันครบวงจรและประสิทธิภาพสูงสำหรับการดึงอีเมลจากไฟล์เก็บ Zimbra TGZ รองรับการสตรีมมิ่งเพื่อให้การใช้หน่วยความจำน้อย จัดการไฟล์เก็บขนาดใหญ่กว่า 1 GB และมี API ปลอดภัยต่อเธรด ทำให้เหมาะสำหรับโครงการสำรองข้อมูล การย้ายข้อมูล หรือการวิเคราะห์เชิงนิติวิทยาศาสตร์ในระดับใหญ่ที่ต้องการความน่าเชื่อถือและความเร็ว.

- **รูปแบบอินพุตกว่า 50** – Aspose.Email อ่าน EML, MSG, MBOX, PST, และ Zimbra TGZ รวมถึงอื่น ๆ.
- **รองรับไฟล์เก็บขนาด 1 GB+** – ประมวลผลไฟล์ TGZ ขนาดหลายกิกะไบต์ด้วยการสตรีมมิ่ง ทำให้การใช้ RAM ต่ำกว่า 200 MB.
- **ไม่มี dependencies ภายนอก** – ไม่ต้องใช้ไลบรารีเซิร์ฟเวอร์ Zimbra หรือเครื่องมือเนทีฟ.
- **API ปลอดภัยต่อเธรด** – คุณสามารถรันหลายอินสแตนซ์ของ `TgzReader` พร้อมกันสำหรับงานแบตช์.

ข้อดีที่วัดได้เหล่านี้ทำให้ Aspose.Email เป็นตัวเลือกพร้อมใช้งานในผลิตภัณฑ์สำหรับโครงการจัดเก็บอีเมลขนาดใหญ่.

## ข้อควรพิจารณาด้านประสิทธิภาพ

เมื่อจัดการกับไฟล์ TGZ ขนาดใหญ่มาก ให้ปฏิบัติตามแนวปฏิบัติที่ดีที่สุดต่อไปนี้:

- **ทำการ Dispose ทันที** – เรียก `tgzReader.dispose()` ทันทีที่เสร็จเพื่อปล่อยทรัพยากรเนทีฟ.
- **ประมวลผลแบบแบตช์** – ประมวลผลข้อความเป็นกลุ่ม (เช่น 500 รายการต่อครั้ง) และบันทึกผลลัพธ์ลงดิสก์ก่อนดำเนินการต่อ.
- **หลีกเลี่ยงการโหลดเนื้อหาทั้งหมด** – ใช้ API สตรีมมิ่ง (`readNextMessage`) แทนการอ่านไฟล์เก็บทั้งหมดเข้าสู่หน่วยความจำ.

การปฏิบัติตามแนวทางเหล่านี้ช่วยให้การใช้ CPU และหน่วยความจำต่ำ แม้บนเซิร์ฟเวอร์ที่มีสเปคปานกลาง.

## การประยุกต์ใช้ในทางปฏิบัติ

การดึงอีเมลจากไฟล์เก็บ Zimbra TGZ มีประโยชน์สำหรับ:

- **สำรองข้อมูลและกู้คืน** – สร้างกล่องเมลใหม่จากไฟล์ TGZ ที่เก็บไว้.
- **การย้ายข้อมูล** – ย้ายข้อมูล Zimbra เก่าไปยัง Exchange, Office 365 หรือที่เก็บข้อมูลแบบกำหนดเอง.
- **การวิเคราะห์เชิงนิติวิทยาศาสตร์** – ตรวจสอบการสื่อสารในอดีตโดยไม่ต้องกู้คืนอินสแตนซ์ Zimbra ทั้งหมด.

## คำถามที่พบบ่อย

**Q: ข้อกำหนดเบื้องต้นสำหรับการใช้ Aspose.Email สำหรับ Java มีอะไรบ้าง?**  
A: JDK 16+, Maven, และ Maven artifact `com.aspose:aspose-email`.

**Q: จะได้รับไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์อย่างไร?**  
A: ซื้อไลเซนส์หรือขอไลเซนส์ชั่วคราวผ่าน [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: เส้นทาง TGZ ของฉันดูเหมือนไม่ถูกต้อง—ควรตรวจสอบอะไร?**  
A: ตรวจสอบว่าไฟล์มีอยู่จริง เส้นทางถูก escape อย่างถูกต้องสำหรับสตริง Java และกระบวนการมีสิทธิ์อ่านไฟล์.

**Q: Aspose.Email รองรับการดึงข้อมูลแบบหลายเธรดหรือไม่?**  
A: ใช่ API ปลอดภัยต่อเธรด; คุณสามารถสร้างอ็อบเจ็กต์ `TgzReader` แยกต่างหากต่อเธรดได้.

**Q: จะบูรณาการอีเมลที่ดึงมาเข้ากับระบบอื่นอย่างไร?**  
A: บันทึกแต่ละ `MailMessage` เป็น EML, JSON หรือ XML ด้วย `SaveOptions` แล้วส่งไฟล์เหล่านั้นเข้าสู่ pipeline ต่อไปของคุณ.

## แหล่งข้อมูล
- **เอกสาร**: [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- **ดาวน์โหลด**: [Aspose Email Releases](https://releases.aspose.com/email/java/)
- **ซื้อ**: [Buy Aspose Products](https://purchase.aspose.com/buy)
- **ทดลองใช้ฟรี**: [Aspose Email Free Trials](https://releases.aspose.com/email/java/)
- **ไลเซนส์ชั่วคราว**: [Obtain a Temporary License](https://purchase.aspose.com/temporary-license/)
- **สนับสนุน**: สำหรับคำถามหรือความช่วยเหลือ เยี่ยมชม [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**อัปเดตล่าสุด:** 2026-06-18  
**ทดสอบกับ:** Aspose.Email for Java 25.4  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [บทแนะนำการวิเคราะห์และแยกอีเมลสำหรับ Aspose.Email Java](/email/java/email-parsing-analysis/)
- [ดึงไฟล์แนบจากอีเมลโดยใช้ Aspose.Email for Java](/email/java/advanced-email-attachments/)
- [โหลดและแสดงอีเมล EML อย่างมีประสิทธิภาพด้วย Aspose.Email for Java](/email/java/email-message-operations/load-display-eml-emails-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```java
import com.aspose.email.TgzReader;
import com.aspose.email.MailMessage;
```

```java
String storagePath = "YOUR_DOCUMENT_DIRECTORY/ZimbraSample.tgz";
```

```java
TgzReader reader = new TgzReader(storagePath);
```

```java
try {
    while (reader.readNextMessage()) { // Continue until all messages are read.
        String directoryName = reader.getCurrentDirectory(); // Get the current email's storage path.
        MailMessage eml = reader.getCurrentMessage(); // Retrieve the current email message.

        // At this point, 'directoryName' and 'eml' hold crucial details of each email.
    }
} finally {
    reader.dispose(); // Always dispose of resources to prevent memory leaks.
}
```

```java
import com.aspose.email.examples.Utils;

public class ExampleUtils {
    public static String getSharedDataDir(Class<?> cls) {
        return "YOUR_DOCUMENT_DIRECTORY/"; // Set your shared data directory path.
    }
}
```

```java
String dataDir = ExampleUtils.getSharedDataDir(ExampleUtils.class) + "email/";
// 'dataDir' now points to a specific subdirectory for email-related operations.
```