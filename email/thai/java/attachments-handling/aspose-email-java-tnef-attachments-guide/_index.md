---
date: '2025-12-13'
description: เรียนรู้วิธีแปลงไฟล์ msg และ eml ด้วย Aspose.Email สำหรับ Java, เพิ่มไฟล์แนบใหม่,
  บันทึกไฟล์แนบของอีเมลและจัดการข้อมูล TNEF.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: แปลงไฟล์ msg, eml ด้วย Aspose.Email Java – คู่มือการแนบไฟล์ TNEF
url: /th/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญ Aspose.Email Java: การจัดการ TNEF และไฟล์แนบอีเมล  

ในแอปพลิเคชันที่เน้นอีเมลสมัยใหม่ คุณมักต้อง **convert msg eml** ไฟล์, เพิ่มไฟล์แนบใหม่ลงในข้อความที่มีอยู่, และคงรูปแบบพิเศษอย่าง TNEF ไว้ ไม่ว่าคุณจะสร้างบริการจัดเก็บข้อมูล, เครื่องมือย้ายข้อมูล, หรือโปรแกรมดูเมลฝั่งไคลเอนต์ Aspose.Email for Java จะมอบวิธีการที่สะอาดและเป็นโปรแกรมเมติกให้คุณทำได้ ในบทแนะนำนี้คุณจะได้เห็นวิธี **convert msg to eml**, เพิ่มไฟล์แนบใหม่, บันทึกไฟล์แนบอีเมล, และทำงานกับข้อมูล TNEF ด้วยไลบรารี Aspose.Email Java

## คำตอบสั้น
- **วิธีแปลง MSG เป็น EML?** ใช้ `MapiMessage` พร้อม `MailConversionOptions` และตั้งค่า `convertAsTnef` เป็น `true`  
- **สามารถเพิ่มไฟล์แนบลงใน EML ที่เปิดใช้งาน TNEF ได้หรือไม่?** ได้ – โหลด EML, เรียก `getAttachments().addItem(...)`, แล้วบันทึก  
- **ต้องใช้เวอร์ชันของ Aspose.Email ใด?** ตัวอย่างใช้เวอร์ชัน 25.4 (JDK 16)  
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** ใช่ – เวอร์ชันทดลองใช้ได้สำหรับการประเมิน, แต่ไลเซนส์เต็มจะลบข้อจำกัดทั้งหมด  
- **มีวิธีตรวจจับ TNEF ในข้อความที่มีอยู่หรือไม่?** เรียก `mail.getOriginalIsTnef()` หลังจากโหลด EML  

## “convert msg eml” คืออะไร?
การแปลงไฟล์ Microsoft Outlook MSG ไปเป็นรูปแบบมาตรฐาน EML ทำให้ข้อความสามารถอ่านได้โดยไคลเอนต์เมลที่สอดคล้องกับ RFC‑822 การแปลงนี้ยังให้คุณโอกาสในการคงหรือจัดการข้อมูลที่เข้ารหัสด้วย TNEF ระหว่างกระบวนการ

## ทำไมต้องใช้ Aspose.Email Java สำหรับงานนี้?
- **รองรับรูปแบบครบวงจร** – MSG, EML, MHTML, และอื่น ๆ  
- **จัดการ TNEF ในตัว** – ไม่ต้องพึ่งพาตัวแยกพาร์สของบุคคลที่สาม  
- **API ง่าย** – เรียกใช้บรรทัดเดียวสำหรับการโหลด, แปลง, และบันทึก  
- **ไลเซนส์ยืดหยุ่น** – ทดลองใช้สำหรับการทดสอบ, ไลเซนส์เต็มสำหรับการผลิต  

## ข้อกำหนดเบื้องต้น
- **Aspose.Email for Java** (v25.4, JDK 16) – ดูการอ้างอิง Maven ด้านล่าง  
- **Maven** หรือเครื่องมือสร้างอื่นที่สามารถดึงแพคเกจ Aspose ได้  
- ความรู้พื้นฐานเกี่ยวกับ Java I/O และการจัดการข้อยกเว้น  

## การตั้งค่า Aspose.Email for Java
เพิ่มไลบรารีลงใน `pom.xml` ของ Maven:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์
Aspose.Email มีรุ่นทดลองฟรี, แต่ต้องมีไลเซนส์สำหรับการใช้โดยไม่มีข้อจำกัด

- **รุ่นทดลองฟรี:** ดาวน์โหลดไลเซนส์ชั่วคราว [ที่นี่](https://releases.aspose.com/email/java/)  
- **ซื้อไลเซนส์:** เยี่ยมชม [หน้าซื้อ](https://purchase.aspose.com/buy)

เริ่มต้นไลเซนส์ในโค้ด Java ของคุณ:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## คู่มือการทำงาน

### การเพิ่มไฟล์แนบใหม่ลงในข้อความหลักที่มี TNEF
**วิธีเพิ่มไฟล์แนบ:** โหลด EML, เพิ่มไฟล์, แล้วบันทึก

#### ขั้นตอนที่ 1: โหลดข้อความอีเมลที่มีอยู่
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### ขั้นตอนที่ 2: เพิ่มไฟล์แนบใหม่
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### ขั้นตอนที่ 3: บันทึกข้อความอีเมลที่แก้ไขแล้ว
```java
eml.save(dataDir + "test_out.eml");
```
*เคล็ดลับ:* ใช้ `try‑with‑resources` เพื่อให้สตรีมปิดอย่างถูกต้องและหลีกเลี่ยง `FileNotFoundException`

### การสร้าง EML ที่เปิดใช้งาน TNEF จาก MSG
**วิธีแปลง msg เป็น eml:** ตั้งค่า `convertAsTnef` เป็น `true`

#### ขั้นตอนที่ 1: โหลดไฟล์ MSG
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### ขั้นตอนที่ 3: แปลงและบันทึก
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### การคงไฟล์แนบ TNEF เมื่อโหลดไฟล์ EML
**วิธีบันทึกไฟล์แนบอีเมลพร้อมคง TNEF:** ใช้ `MsgLoadOptions`

#### ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการโหลด
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### ขั้นตอนที่ 2: โหลดไฟล์ EML ด้วยตัวเลือก
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### การตรวจจับว่าข้อความเป็น TNEF หรือไม่
**วิธีตรวจสอบการมีอยู่ของ TNEF:** เรียก `getOriginalIsTnef()`

#### ขั้นตอนที่ 1: โหลดไฟล์ EML
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### ขั้นตอนที่ 2: ตรวจจับการมี TNEF
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## การประยุกต์ใช้ในเชิงปฏิบัติ
1. **การจัดเก็บอีเมล:** คงไฟล์แนบทุกไฟล์รวมถึงไฟล์ที่เข้ารหัสด้วย TNEF เพื่อการตรวจสอบตามกฎระเบียบ  
2. **การย้ายข้อมูลองค์กร:** แปลงไฟล์ MSG เก่าเป็น EML เพื่อให้สามารถนำเข้าไปยังเซิร์ฟเวอร์เมลสมัยใหม่ได้  
3. **การสนับสนุนลูกค้า:** ตรวจจับข้อมูล TNEF อัตโนมัติเมื่อผู้ใช้ส่งต่อข้อความระหว่าง Outlook กับไคลเอนต์เว็บเมล  

## พิจารณาด้านประสิทธิภาพ
- **การจัดการทรัพยากร:** ห่อสตรีมไฟล์ด้วย `try‑with‑resources` เพื่อปล่อยตัวจัดการไฟล์โดยเร็ว  
- **ไฟล์แนบขนาดใหญ่:** ประมวลผลไฟล์ใหญ่เป็นชิ้นหรือสตรีมโดยตรงเพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง  
- **การเฝ้าติดตาม:** ใช้เครื่องมือ profiling ของ Java เพื่อตรวจสอบการใช้ heap เมื่อจัดการไฟล์แนบจำนวนมาก  

## สรุป
โดยทำตามขั้นตอนข้างต้น คุณสามารถ **convert msg eml**, เพิ่มไฟล์แนบใหม่, บันทึกไฟล์แนบอีเมล, และทำงานกับข้อมูล TNEF อย่างมั่นใจด้วย Aspose.Email for Java ไลบรารีจะจัดการส่วน MIME ระดับต่ำให้คุณ ทำให้คุณโฟกัสที่ตรรกะธุรกิจได้ หากต้องการสำรวจเพิ่มเติม ดูเอกสารอย่างเป็นทางการของ [Aspose documentation](https://reference.aspose.com/email/java/) หรือทดลองกับตัวเลือกการแปลงอื่น ๆ

## FAQ Section
**Q1: TNEF file คืออะไร?**  
A1: TNEF ย่อมาจาก Transport Neutral Encapsulation Format ใช้โดย Microsoft Outlook เพื่อคงรูปแบบ rich‑text เมื่อส่งอีเมลเป็นไฟล์แนบ  

**Q2: สามารถใช้ Aspose.Email ได้โดยไม่ซื้อไลเซนส์หรือไม่?**  
A2: ใช่, คุณสามารถเริ่มต้นด้วยรุ่นทดลองฟรี อย่างไรก็ตามรุ่นทดลองมีข้อจำกัดบางประการที่อาจส่งผลต่อการใช้งานเต็มรูปแบบ  

**Q3: Aspose.Email สามารถแปลงระหว่างรูปแบบอีเมลทั้งหมดได้หรือไม่?**  
A3: Aspose.Email รองรับการแปลงระหว่างรูปแบบที่นิยมที่สุดรวมถึง EML, MSG, และ MHTML – ตรวจสอบการสนับสนุนรูปแบบเฉพาะใน [documentation](https://reference.aspose.com/email/java/)  

**Q4: วิธีแก้ไขข้อผิดพลาด file‑not‑found กับ Aspose.Email คืออะไร?**  
A4: ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ที่ส่งให้ API ถูกต้อง, ไฟล์มีอยู่จริง, และกระบวนการทำงานมีสิทธิ์อ่าน/เขียนในไดเรกทอรีนั้น  

**Q5: วิธีที่ดีที่สุดในการจัดการไฟล์แนบขนาดใหญ่กับ Aspose.Email คืออะไร?**  
A5: ประมวลผลไฟล์แนบเป็นสตรีมหรือชิ้นเล็ก ๆ และปิดสตรีมโดยเร็ว เพื่อลดภาระหน่วยความจำและป้องกัน `OutOfMemoryError`  

## Frequently Asked Questions (Additional)

**Q: Aspose.Email จะลบ TNEF อัตโนมัติเมื่อแปลงเป็น EML หรือไม่?**  
A: ไม่ใช่ โดยค่าเริ่มต้นข้อมูล TNEF จะถูกคงไว้ คุณสามารถควบคุมพฤติกรรมนี้ด้วย `MailConversionOptions.setConvertAsTnef`  

**Q: สามารถแสดงรายการไฟล์แนบทั้งหมดในข้อความที่โหลดได้หรือไม่?**  
A: ได้ – ใช้ `mail.getAttachments()` ซึ่งคืนคอลเลกชันที่คุณสามารถวนลูปได้  

**Q: มีวิธีแปลงชุดไฟล์ MSG เป็น EML ในการทำงานครั้งเดียวหรือไม่?**  
A: มีแน่นอน เพียงวนลูปผ่านไฟล์แต่ละไฟล์, ใช้ขั้นตอนการแปลงที่แสดงข้างต้น, แล้วบันทึกผลลัพธ์แต่ละไฟล์  

**แหล่งข้อมูลที่เกี่ยวข้อง:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | ดาวน์โหลดไลเซนส์ชั่วคราว [ที่นี่](https://releases.aspose.com/email/java/).

---

**อัปเดตล่าสุด:** 2025-12-13  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}