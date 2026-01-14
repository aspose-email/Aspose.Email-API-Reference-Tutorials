---
date: '2025-12-17'
description: เรียนรู้วิธีดึงไฟล์แนบแบบอินไลน์ใน Java และอ่านไฟล์ Outlook MSG ด้วย
  Java โดยใช้ Aspose.Email for Java คู่มือขั้นตอนต่อขั้นตอนสำหรับการจัดการไฟล์ Outlook
  MSG อย่างมีประสิทธิภาพ
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: สกัดไฟล์แนบแบบอินไลน์ใน Java – ไฟล์ MSG ด้วย Aspose.Email
url: /th/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# แยกไฟล์แนบแบบอินไลน์ Java – ไฟล์ MSG ด้วย Aspose.Email

## บทนำ

หากคุณต้องการ **แยกไฟล์แนบแบบอินไลน์ java** จากไฟล์ Microsoft Outlook MSG คุณมาถูกที่แล้ว นักพัฒนาหลายคนประสบปัญหาในการอ่านไฟล์ Outlook msg java เนื่องจากรูปแบบไฟล์ซ่อนรูปภาพและเอกสารที่ฝังอยู่ในส่วนเนื้อความของข้อความ ในบทแนะนำนี้เราจะอธิบายวิธีแก้ไขที่สะอาดและพร้อมใช้งานในสภาพการผลิตโดยใช้ไลบรารี Aspose.Email สำหรับ Java เพื่อค้นหา ระบุ และบันทึกไฟล์แนบแบบอินไลน์เหล่านั้น

เมื่ออ่านคู่มือนี้จนจบแล้วคุณจะสามารถ:

* ตั้งค่า Aspose.Email สำหรับ Java ในโครงการ Maven  
* **อ่านไฟล์ Outlook msg java** และแสดงรายการไฟล์แนบทั้งหมด  
* ตรวจจับไฟล์แนบที่เป็นอินไลน์และบันทึกลงดิสก์  
* ปรับใช้แนวปฏิบัติด้านประสิทธิภาพสำหรับการประมวลผลเป็นกลุ่ม

## คำตอบสั้น ๆ
- **“ไฟล์แนบแบบอินไลน์” หมายถึงอะไร?** ไฟล์แนบที่ฝังอยู่ในส่วนเนื้อความของอีเมล (เช่น รูปภาพที่แสดงภายในข้อความ)  
- **ไลบรารีใดจัดการไฟล์ MSG?** Aspose.Email สำหรับ Java  
- **ต้องมีลิขสิทธิ์หรือไม่?** รุ่นทดลองทำงานได้สำหรับการประเมิน; ลิขสิทธิ์ถาวรจะลบข้อจำกัดการใช้งานออก  
- **สามารถประมวลผลไฟล์ MSG จำนวนมากพร้อมกันได้หรือไม่?** ได้ – ทำเป็นแบชและใช้ thread pool เพื่อเพิ่มความสามารถในการขยายตัว  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 16 หรือใหม่กว่า

## “extract inline attachments java” คืออะไร?

การแยกไฟล์แนบแบบอินไลน์ใน Java หมายถึงการเปิดไฟล์ MSG ด้วยโปรแกรม, สแกนคอลเลกชันไฟล์แนบ, และดึงเฉพาะรายการที่ถูกทำเครื่องหมายว่า *inline* (ต่างจากไฟล์แนบทั่วไป) สิ่งนี้สำคัญเมื่อคุณต้องการบันทึกเนื้อหาภาพของอีเมล—เช่น โลโก้หรือสกรีนช็อตที่ฝังอยู่—เป็นไฟล์ภาพแยกต่างหาก

## ทำไมต้องใช้ Aspose.Email สำหรับงานนี้?

Aspose.Email ทำให้โครงสร้าง MAPI ระดับต่ำเป็นเรื่องง่ายและให้ API ที่เป็นชนิดข้อมูลอย่างชัดเจน เมื่อเทียบกับการพยายามแยกรูปแบบไบนารี MSG ด้วยตนเอง, Aspose.Email:

* รองรับรูปแบบ MSG ทุกประเภท (Unicode, RTF, HTML)  
* ให้การเข้าถึงคุณสมบัติของไฟล์แนบอย่างเชื่อถือได้  
* มีการตรวจสอบลิขสิทธิ์ในตัวและเอกสารอธิบายที่ครอบคลุม  

## ข้อกำหนดเบื้องต้น

เพื่อทำตามขั้นตอนนี้, โปรดตรวจสอบว่าคุณมี:

1. **ไลบรารีและการพึ่งพา**  
   * Aspose.Email สำหรับ Java (เวอร์ชันล่าสุด)  
   * Maven (หรือ IDE ที่รองรับ Maven)  

2. **สภาพแวดล้อมการทำงาน**  
   * JDK 16 หรือใหม่กว่า  

3. **ความรู้พื้นฐาน**  
   * ความคุ้นเคยกับ Java I/O และการจัดการข้อยกเว้น  

## การตั้งค่า Aspose.Email สำหรับ Java

เพิ่มการพึ่งพา Aspose.Email ลงใน `pom.xml` ของคุณ โค้ดตัวอย่างด้านล่างคงไว้ตามต้นฉบับ

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### ขั้นตอนการขอรับลิขสิทธิ์

* **รุ่นทดลองฟรี:** ดาวน์โหลดไฟล์ DLL/JAR ทดลองจากเว็บไซต์ Aspose  
* **ลิขสิทธิ์ชั่วคราว:** ขอรับลิขสิทธิ์ทดลอง 30‑วันสำหรับการทดสอบโดยไม่มีข้อจำกัด  
* **การซื้อเต็มรูปแบบ:** รับลิขสิทธิ์ถาวรสำหรับการใช้งานในสภาพการผลิต  

## คู่มือการนำไปใช้

ด้านล่างเราจะแบ่งวิธีแก้เป็นสามคุณลักษณะหลัก แต่ละคุณลักษณะมีคำอธิบายสั้น ๆ ตามด้วยบล็อกโค้ดต้นฉบับ (ต้องคงไว้โดยไม่เปลี่ยนแปลง)

### คุณลักษณะ 1 – โหลดไฟล์ MSG

แรกเริ่ม, โหลดข้อความ Outlook ลงในอ็อบเจ็กต์ `MapiMessage`

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### คุณลักษณะ 2 – ดึงไฟล์แนบทั้งหมด

ต่อมา, ดึงคอลเลกชันไฟล์แนบทั้งหมดจากข้อความ

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### คุณลักษณะ 3 – ระบุและบันทึกไฟล์แนบแบบอินไลน์

วนลูปผ่านไฟล์แนบแต่ละรายการ, ตรวจสอบว่ามันเป็นอินไลน์หรือไม่, แล้วบันทึกลงดิสก์

```java
for (Object untypedAttachment : attachments) {
    MapiAttachment attachment = (MapiAttachment) untypedAttachment;
    if (IsAttachmentInline(attachment)) {
        try {
            SaveAttachment(attachment, UUID.randomUUID().toString());
        } catch (IOException e) {
            // Handle exception
        }
    }
}
```

#### ยูทิลิตี้: ตรวจสอบว่าไฟล์แนบเป็นอินไลน์หรือไม่

เมธอดช่วยเหลือนี้ตรวจสอบคุณสมบัติ MAPI เพื่อพิจารณาว่าไฟล์แนบนั้นฝังอยู่หรือไม่

```java
import com.aspose.email.MapiAttachment;
import com.aspose.email.MapiObjectProperty;
import com.aspose.email.MapiProperty;

static boolean IsAttachmentInline(MapiAttachment attachment) {
    MapiObjectProperty objectData = attachment.getObjectData();
    if (objectData == null) return false;

    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("\u0003ObjInfo".equals(property.getName())) {
            byte[] data = property.getData();
            int odtPersist1 = data[1] << 8 | data[0];
            return (odtPersist1 & 0x40) == 0;
        }
    }
    return false;
}
```

#### ยูทิลิตี้: บันทึกไฟล์แนบแบบอินไลน์

เขียนข้อมูลไบนารีของไฟล์แนบแบบอินไลน์ลงไฟล์บนระบบไฟล์ท้องถิ่น

```java
import com.aspose.email.MapiAttachment;
import java.io.FileOutputStream;
import java.io.IOException;

static void SaveAttachment(MapiAttachment attachment, String fileName) throws IOException {
    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("Package".equals(property.getName())) {
            try (FileOutputStream fs = new FileOutputStream(fileName)) {
                fs.write(property.getData(), 0, property.getData().length);
            }
        }
    }
}
```

## การประยุกต์ใช้งานจริง

การแยกไฟล์แนบแบบอินไลน์มีประโยชน์ในหลายสถานการณ์จริง:

* **การประมวลผลอีเมลอัตโนมัติ** – ดึงรูปภาพจากจดหมายข่าวเพื่อวิเคราะห์  
* **การย้ายข้อมูล** – ย้ายเนื้อหาที่ฝังอยู่เมื่อย้ายจาก Exchange ไปยังแพลตฟอร์มอื่น  
* **โซลูชันการจัดเก็บ** – รักษาความสมบูรณ์ของภาพในข้อความที่เก็บถาวรโดยแยกเก็บทรัพยากรอินไลน์เป็นไฟล์แยก  

## พิจารณาด้านประสิทธิภาพ

เมื่อจัดการกับไฟล์ MSG จำนวนหลายร้อยหรือหลายพันไฟล์, ควรคำนึงถึงเคล็ดลับต่อไปนี้:

* **การประมวลผลเป็นแบช:** แบ่งไฟล์เป็นกลุ่มที่จัดการได้เพื่อหลีกเลี่ยงการเพิ่มขึ้นของหน่วยความจำอย่างฉับพลัน  
* **ปล่อยทรัพยากรโดยเร็ว:** ปิดสตรีม (`try‑with‑resources`) และให้ garbage collector ทำงานทำความสะอาดอ็อบเจ็กต์  
* **การทำงานแบบขนาน:** ใช้ `ExecutorService` ขนาดคงที่เพื่อรันงานแยกไฟล์หลายงานพร้อมกัน, แต่ต้องตรวจสอบการใช้ CPU  

## ปัญหาที่พบบ่อยและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `NullPointerException` ที่ `attachment.getObjectData()` | ข้อความไม่มีข้อมูลเมตาดาต้าไฟล์แนบ (เช่น MSG เสียหาย) | ตรวจสอบไฟล์ MSG ก่อนประมวลผลหรือจับข้อยกเว้นและบันทึกชื่อไฟล์ |
| ไฟล์ที่บันทึกเป็นไฟล์ว่างหรือเสียหาย | ชื่อคุณสมบัติไม่ถูกต้อง (`"Package"` ความแตกต่างตัวพิมพ์) | ยืนยันว่าชื่อคุณสมบัติตรงกับของ MSG; เอกสาร Aspose.Email ระบุสตริงที่ถูกต้อง |
| ประสิทธิภาพลดลงเมื่อไฟล์ใหญ่ | สตรีมไม่ถูกปิดทำให้เกิดการรั่วของหน่วยความจำ | ใช้ `try‑with‑resources` (ตามตัวอย่าง) และพิจารณาเพิ่ม heap ของ JVM หากจำเป็น |

## คำถามที่พบบ่อย

**ถาม:** เวอร์ชันขั้นต่ำของ Aspose.Email ที่ต้องใช้คืออะไร?  
**ตอบ:** บทแนะนำใช้เวอร์ชัน 25.4, แต่เวอร์ชัน 24.x+ ที่รองรับ JDK 16 จะทำงานได้เช่นกัน  

**ถาม:** สามารถแยกไฟล์แนบแบบอินไลน์จากไฟล์ MSG ที่เข้ารหัสได้หรือไม่?  
**ตอบ:** ได้, หากคุณส่งรหัสผ่านถอดรหัสที่ถูกต้องเมื่อโหลด `MapiMessage`  

**ถาม:** วิธีแยกความแตกต่างระหว่างภาพอินไลน์และไฟล์แนบทั่วไปคืออะไร?  
**ตอบ:** ใช้เมธอด `IsAttachmentInline` ซึ่งตรวจสอบแฟล็ก `ObjInfo` ของ MAPI ที่ระบุว่าไฟล์แนบเป็นอินไลน์  

**ถาม:** มีวิธีเก็บชื่อไฟล์เดิมของไฟล์แนบแบบอินไลน์หรือไม่?  
**ตอบ:** ตัวอย่างสร้าง UUID เพื่อความเป็นเอกลักษณ์, แต่คุณสามารถอ่านคุณสมบัติ `attachment.getLongFileName()` และใช้เป็นชื่อไฟล์เมื่อเรียก `SaveAttachment`  

**ถาม:** วิธีการนี้ทำงานบน Linux/macOS ได้เช่นเดียวกับ Windows หรือไม่?  
**ตอบ:** ทำได้แน่นอน—Aspose.Email เป็นไลบรารีที่ไม่ขึ้นกับแพลตฟอร์ม ตราบใดที่ติดตั้ง JDK  

## แหล่งข้อมูล
- **เอกสาร:** [Aspose Email Documentation](https://docs.aspose.com/email/java/)

---

**อัปเดตล่าสุด:** 2025-12-17  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}