---
date: '2026-02-27'
description: เรียนรู้วิธีโหลดไฟล์ MSG และแปลงเป็น MHTML ด้วย Aspose.Email สำหรับ Java
  รวมถึงการตั้งค่าโซนเวลาที่กำหนดเองและเคล็ดลับการประมวลผลอีเมลแบบแบตช์
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: วิธีโหลดไฟล์ MSG และบันทึกเป็น MHTML ด้วย Aspose.Email สำหรับ Java
url: /th/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีโหลดไฟล์ MSG และบันทึกเป็น MHTML ด้วย Aspose.Email สำหรับ Java

## บทนำ

หากคุณต้องการ **how to load msg** ไฟล์, ปรับค่า timestamp ของพวกมัน, แล้ว **convert msg to mhtml**, คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนการโหลดอีเมล `.msg`, ปรับค่า offset ของเขตเวลาแบบกำหนดเอง, และบันทึกผลลัพธ์เป็นไฟล์ MHTML ทั้งหมดด้วย Aspose.Email สำหรับ Java ไม่ว่าคุณจะทำงานกับข้อความเดียวหรือ **batch email processing** pipeline ขั้นตอนเหล่านี้จะให้พื้นฐานที่มั่นคงแก่คุณ

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีโหลด `MailMessage` จากไฟล์ `.msg`
- วิธีตั้งค่าเขตเวลาแบบกำหนดเองและวันที่ปัจจุบัน
- วิธีบันทึกข้อความเป็น MHTML พร้อมการจัดรูปแบบที่แม่นยำ
- เคล็ดลับการขยายวิธีการนี้สำหรับสถานการณ์แบบ batch

พร้อมเพิ่มประสิทธิภาพการทำงานกับอีเมลของคุณหรือยัง? มาเตรียมสภาพแวดล้อมกันก่อน

## คำตอบสั้น ๆ
- **ไลบรารีหลักคืออะไร?** Aspose.Email for Java
- **ฉันสามารถโหลด MSG และส่งออกเป็น MHTML ได้ในขั้นตอนเดียวหรือไม่?** ไม่ได้ คุณต้องโหลด, ปรับค่า, แล้วบันทึก
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** ต้อง มีไลเซนส์ Aspose.Email ที่ถูกต้อง
- **การจัดการเขตเวลาถูกสนับสนุนหรือไม่?** ใช่ ผ่าน `setTimeZoneOffset`
- **สามารถใช้ในการประมวลผลแบบ batch ได้หรือไม่?** แน่นอน – ห่อขั้นตอนทั้งหมดในลูป

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

### ไลบรารีและการพึ่งพาที่จำเป็น
- **Aspose.Email for Java** เวอร์ชัน 25.4 (jdk16 classifier)
- ความรู้พื้นฐานของ Java
- IDE เช่น IntelliJ IDEA หรือ Eclipse

### ความต้องการการตั้งค่าสภาพแวดล้อม
- ติดตั้ง JDK 16 หรือใหม่กว่า
- Maven สำหรับการจัดการ dependencies

## การตั้งค่า Aspose.Email สำหรับ Java

เพื่อเพิ่มไลบรารีลงในโครงการ Maven ให้ใส่ dependency ดังต่อไปนี้:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ขั้นตอนการรับไลเซนส์

เริ่มต้นด้วย **free trial** หรือรับ **temporary license** เพื่อประเมินความสามารถเต็มรูปแบบของไลบรารีโดยไม่มีข้อจำกัด สำหรับการใช้งานระยะยาว ควรพิจารณาซื้อไลเซนส์:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### การเริ่มต้นพื้นฐาน

หลังจากเพิ่ม dependency แล้ว ให้ทำการเริ่มต้นไลเซนส์ในโค้ด Java ของคุณ:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## คู่มือการทำงาน

เราจะแบ่งการทำงานออกเป็นสามฟีเจอร์ที่ชัดเจน

### ฟีเจอร์ 1: การโหลด MailMessage จากไฟล์

#### ภาพรวม
การโหลดไฟล์ `.msg` จะทำให้คุณเข้าถึงเนื้อหาอีเมล, ไฟล์แนบ, และเมตาดาต้าได้อย่างเต็มที่

#### ขั้นตอนทีละขั้นตอน

**นำเข้าคลาสที่จำเป็น**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**โหลดอีเมล**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` ให้คุณควบคุมวิธีการตีความไฟล์ MSG; การตั้งค่าเริ่มต้นทำงานได้กับสถานการณ์ส่วนใหญ่

### ฟีเจอร์ 2: การตั้งค่าวันที่ปัจจุบันและออฟเซ็ตเขตเวลาแบบกำหนดเอง

#### ภาพรวม
Timestamp ที่แม่นยำเป็นสิ่งสำคัญเมื่อคุณทำงานกับผู้ใช้ในหลายภูมิภาค

**ตั้งค่าวันที่ปัจจุบัน**

```java
import java.util.Date;

msg.setDate(new Date());
```

**กำหนดออฟเซ็ตเขตเวลาแบบกำหนดเอง (เช่น UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

ออฟเซ็ตจะถูกระบุเป็นมิลลิวินาที ดังนั้นคุณสามารถส่งค่าลบสำหรับโซนที่อยู่ทางตะวันตกของ UTC ได้เช่นกัน

### ฟีเจอร์ 3: การบันทึก MailMessage เป็นไฟล์ MHTML

#### ภาพรวม
MHTML จะบรรจุเนื้อหา HTML และทรัพยากรที่ฝังอยู่ในไฟล์เดียว เหมาะสำหรับการเก็บถาวรหรือการแชร์

**กำหนดค่า options การบันทึก**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**บันทึกอีเมล**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

ไฟล์ `.mhtml` ที่ได้จะคงรูปแบบเดิม, รูปภาพ, และไฟล์แนบทั้งหมด

## ทำไมต้องแปลง MSG เป็น MHTML?

การแปลงไฟล์ MSG เป็น MHTML จะให้รูปแบบไฟล์เดียวที่เป็นมิตรต่อเว็บและสามารถเปิดได้ในเบราว์เซอร์สมัยใหม่ทุกตัว สิ่งนี้มีประโยชน์เป็นพิเศษสำหรับ:

- **Legal archiving** ที่ต้องการสำเนาภาพที่ตรงกับต้นฉบับ
- **Cross‑platform sharing** โดยไม่ต้องใช้ Outlook
- **Embedding emails** ลงในหน้าเว็บหรือเอกสาร

## เคล็ดลับการประมวลผลอีเมลแบบ batch

หากคุณต้องการ **batch email processing** ให้ห่อขั้นตอนการโหลด, ปรับเขตเวลา, และบันทึกไว้ในลูปที่วนผ่านไดเรกทอรีของไฟล์ `.msg` อย่าลืม:

1. ใช้ `License` ตัวเดียวซ้ำเพื่อหลีกเลี่ยงค่าใช้จ่ายเพิ่ม
2. ปล่อยทรัพยากรหลังจากแต่ละรอบ (`msg.dispose()` หากจำเป็น)
3. บันทึกข้อผิดพลาดใด ๆ ลงไฟล์แยกเพื่อการตรวจสอบในภายหลัง

## การประยุกต์ใช้ในทางปฏิบัติ

1. **Email Archiving:** เก็บรักษาการสื่อสารในรูปแบบพกพาเพื่อการปฏิบัติตามกฎระเบียบ
2. **Global Scheduling:** ปรับ timestamp ให้เป็นเขตเวลาเดียวก่อนส่งการแจ้งเตือน
3. **CRM Integration:** นำอีเมลที่เก็บไว้เข้าสู่ระบบ CRM อัตโนมัติเป็นไฟล์แนบ MHTML

## พิจารณาประสิทธิภาพ

- **Memory Management:** ประมวลผล batch ขนาดใหญ่เป็นชิ้นย่อยเพื่อรักษาการใช้หน่วยความจำให้ต่ำ
- **I/O Optimization:** ใช้ buffered streams หากต้องอ่าน/เขียนไฟล์จำนวนมาก
- **Parallel Execution:** พิจารณาใช้ `ForkJoinPool` ของ Java สำหรับการประมวลผลแบบขนาน แต่ต้องตรวจสอบความปลอดภัยของเธรดสำหรับอ็อบเจ็กต์ของ Aspose

## สรุป

คุณได้เรียนรู้ **how to load msg** ไฟล์, ปรับออฟเซ็ตเขตเวลาแบบกำหนดเอง, และ **convert msg to mhtml** ด้วย Aspose.Email สำหรับ Java แล้ว เทคนิคเหล่านี้สามารถขยายเพื่อจัดการกับงาน **batch email processing** ให้คุณมีโซลูชันที่แข็งแกร่งสำหรับการเก็บถาวร, การย้าย, และการอัตโนมัติของอีเมล

**ขั้นตอนต่อไป**  
สำรวจฟีเจอร์เพิ่มเติมของ Aspose.Email เช่น การจัดการไฟล์แนบ, การสกัดข้อมูลปฏิทิน, หรือการส่ง SMTP โดยเยี่ยมชม [documentation](https://reference.aspose.com/email/java/)

## คำถามที่พบบ่อย

**Q: ฉันสามารถโหลดอีเมลจากรูปแบบอื่นนอกจาก .msg ได้หรือไม่?**  
A: ได้, Aspose.Email รองรับ EML, MSG, MHT และหลายรูปแบบอื่น

**Q: จะจัดการไฟล์อีเมลขนาดใหญ่มากอย่างมีประสิทธิภาพได้อย่างไร?**  
A: ใช้ streaming API ของ Aspose.Email เพื่ออ่าน/เขียนข้อมูลเป็นชิ้นส่วน ลดความกดดันของหน่วยความจำ

**Q: สามารถแก้ไขไฟล์แนบภายใน MailMessage ได้หรือไม่?**  
A: แน่นอน คุณสามารถเพิ่ม, ลบ, หรือแทนที่ไฟล์แนบผ่านคอลเลกชัน `MailMessage.getAttachments()`

**Q: ถ้าออฟเซ็ตเขตเวลาของฉันเป็นค่าลบ (อยู่หลัง UTC) จะทำอย่างไร?**  
A: ส่งค่ามิลลิวินาทีลบให้กับ `setTimeZoneOffset` เช่น `-3 * 60 * 60 * 1000` สำหรับ UTC‑3

**Q: ฉันสามารถใช้ Aspose.Email ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ได้, เพียงแค่มีไลเซนส์เชิงพาณิชย์ที่ถูกต้อง

**Q: จะประมวลผลไฟล์ MSG จำนวนหลายพันไฟล์โดยไม่ให้หน่วยความจำหมดทำอย่างไร?**  
A: ประมวลผลเป็น batch, ปล่อย `MailMessage` หลังบันทึกแต่ละครั้ง, และพิจารณาใช้ pattern `try‑with‑resources` ของ Java เพื่อทำความสะอาดอัตโนมัติ

## แหล่งข้อมูล
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-02-27  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}