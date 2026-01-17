---
date: '2026-01-17'
description: เรียนรู้วิธีแปลง MSG เป็น MHT ด้วย Aspose.Email สำหรับ Java คำแนะนำทีละขั้นตอนนี้ครอบคลุมการโหลด
  การบันทึก และการปรับแต่งเทมเพลตสำหรับการแปลงอีเมลในโลกจริง
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 'วิธีแปลงไฟล์ MSG เป็น MHT ด้วย Aspose.Email สำหรับ Java: คู่มือฉบับสมบูรณ์'
url: /th/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# แปลง MSG เป็น MHT ด้วย Aspose.Email สำหรับ Java: คู่มือฉบับสมบูรณ์

## บทนำ

การแปลง **MSG เป็น MHT** เป็นความต้องการทั่วไปเมื่อคุณต้องการเก็บถาวรหรือแสดงข้อความ Outlook ในรูปแบบที่เป็นมิตรกับเว็บ ในบทเรียนนี้คุณจะได้เห็นว่า Aspose.Email สำหรับ Java ทำให้การแปลงเป็นเรื่องง่าย โดยให้คุณโหลดไฟล์ MAPI (MSG) ปรับแต่งผลลัพธ์ด้วยเทมเพลต HTML แบบกำหนดเอง และบันทึกเป็นไฟล์ MHT พร้อมใช้งานในเบราว์เซอร์หรือระบบจัดเก็บข้อมูล

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีโหลดและแยกวิเคราะห์ไฟล์ MSG อย่างมีประสิทธิภาพ  
- วิธีกำหนดค่า `MhtSaveOptions` เพื่อให้ได้ผลลัพธ์ MHT ที่ดีที่สุด  
- วิธีใช้เทมเพลตแบบกำหนดเองเพื่อปรับปรุงการอ่าน  
- สถานการณ์จริงที่การแปลง MSG เป็น MHT เพิ่มคุณค่า  

เตรียมสภาพแวดล้อมให้พร้อมและเริ่มลงมือเขียนโค้ดกัน

## คำตอบอย่างรวดเร็ว
- **อะไรคือการ “แปลง MSG เป็น MHT”?** มันแปลงไฟล์ Outlook `.msg` ให้เป็นรูปแบบ `.mht` (MHTML) ที่เข้ากันได้กับเว็บ  
- **ไลบรารีที่ใช้คืออะไร?** Aspose.Email สำหรับ Java (aspose email tutorial)  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรี 30 วันเพียงพอสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **เวอร์ชัน Java ที่รองรับ?** Java 16 หรือใหม่กว่า (classifier `jdk16`)  
- **กรณีการใช้งานทั่วไป?** เก็บอีเมลเพื่อการปฏิบัติตามหรือแสดงในเบราว์เซอร์โดยไม่ต้องใช้ Outlook  

## อะไรคือ “แปลง MSG เป็น MHT”?
กระบวนการแปลงจะอ่านข้อความ Outlook แบบไบนารี (`.msg`) แล้วเขียนเนื้อหา, ไฟล์แนบ, และเมตาดาต้าใหม่เป็นไฟล์ MHTML แบบ HTML เดียว (`.mht`). รูปแบบไฟล์เดียวนี้รักษาเค้าโครงเดิมไว้ขณะสามารถดูได้ในเบราว์เซอร์สมัยใหม่ใด ๆ  

## ทำไมต้องใช้ Aspose.Email สำหรับ Java?
- **API ครบคุณสมบัติ:** จัดการคุณสมบัติ MAPI ทั้งหมด, ไฟล์แนบ, และอ็อบเจ็กต์ฝัง  
- **ไม่มีการพึ่งพา Outlook:** ทำงานบนสภาพแวดล้อม Java ฝั่งเซิร์ฟเวอร์ใดก็ได้  
- **เทมเพลตที่ปรับแต่งได้:** ปรับผลลัพธ์ HTML ให้ตรงกับแบรนด์หรือมาตรฐานรายงานของคุณ  
- **ประสิทธิภาพสูง:** ปรับให้เหมาะกับการประมวลผลเป็นชุดใหญ่และแบบอะซิงโครนัส  

## ข้อกำหนดเบื้องต้น
- **ไลบรารี Aspose.Email:** เวอร์ชัน 25.4 หรือใหม่กว่า (classifier `jdk16`)  
- **สภาพแวดล้อมการพัฒนา Java:** มี Maven ติดตั้งเพื่อจัดการ dependencies  
- **ความรู้พื้นฐาน Java:** คุ้นเคยกับการทำงานไฟล์ I/O และโครงการ Maven  

## การตั้งค่า Aspose.Email สำหรับ Java

เพื่อเพิ่ม Aspose.Email ไปยังโครงการ Maven ของคุณ ให้ใส่ dependency ด้านล่างนี้:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์ (aspose email tutorial)

Aspose.Email เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถเริ่มต้นด้วย **การทดลองใช้ฟรี**:

- **Free Trial:** ฟังก์ชันเต็มสำหรับ 30 วัน.  
- **Temporary License:** ขยายการประเมินหากต้องการ.  
- **Purchase:** รับไลเซนส์ถาวรสำหรับการใช้งานในสภาพแวดล้อมจริง.  

### การเริ่มต้นพื้นฐาน

หลังจากเพิ่ม dependency ของ Maven แล้ว ให้เริ่มต้นไลบรารีในโค้ด Java ของคุณ:

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## วิธีแปลง MSG เป็น MHT ด้วย Aspose.Email สำหรับ Java

### โหลดไฟล์ MSG

**ขั้นตอนที่ 1 – นำเข้าคลาสที่จำเป็น**

```java
import com.aspose.email.MapiMessage;
```

**ขั้นตอนที่ 2 – โหลดข้อความจากดิสก์**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

เมธอด `MapiMessage.fromFile()` จะอ่านไฟล์ `.msg` และสร้างอ็อบเจ็กต์ `MapiMessage` ที่สามารถจัดการได้  

### กำหนดค่า MHT Save Options

**ขั้นตอนที่ 1 – นำเข้าคลาสตัวเลือกการบันทึก**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**ขั้นตอนที่ 2 – ตั้งค่าตัวเลือก**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` ทำให้แน่ใจว่าฟิลด์เฉพาะงานถูกรวมไว้, ส่วน `WriteHeader` จะเพิ่มหัวอีเมลมาตรฐานลงในผลลัพธ์ MHT.  

### กำหนดเทมเพลต HTML แบบกำหนดเอง (ไม่บังคับ)

**ขั้นตอนที่ 1 – นำเข้าค่า enum ของเทมเพลต**

```java
import com.aspose.email.MhtTemplateName;
```

**ขั้นตอนที่ 2 – ปรับแต่งเทมเพลต**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

เทมเพลตเหล่านี้ทำให้คุณควบคุมการแสดงผลของแต่ละคุณสมบัติงานในไฟล์ MHT สุดท้าย ทำให้ผลลัพธ์ชัดเจนยิ่งขึ้นสำหรับผู้ใช้ปลายทาง.  

### บันทึกข้อความเป็นไฟล์ MHT

**ขั้นตอนที่ 1 – กำหนดไดเรกทอรีผลลัพธ์**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**ขั้นตอนที่ 2 – ดำเนินการบันทึก**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

เมธอด `save` จะเขียนไฟล์ MHT ที่ปรับแต่งแล้วลงดิสก์ ตรวจสอบเส้นทาง `outputDir` ก่อนรันโค้ด.  

## การประยุกต์ใช้งานจริง (ทำไมต้องแปลง MSG เป็น MHT?)

- **Archiving:** เก็บอีเมลในรูปแบบเดียวพกพาที่เบราว์เซอร์สามารถแสดงได้โดยไม่ต้องใช้ Outlook.  
- **Migration:** ย้ายคลังเก็บ Outlook เก่าไปยังแพลตฟอร์มอีเมลบนเว็บ.  
- **Reporting & Analytics:** วิเคราะห์ไฟล์ MHT ด้วยตัวแยก HTML เพื่อสกัดข้อมูลและทำ Business Intelligence.  
- **Legal Compliance:** รักษาเนื้อหาและเมตาดาต้าของข้อความต้นฉบับในรูปแบบที่ตรวจจับการดัดแปลงได้.  

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **Batch Processing:** เมื่อจัดการไฟล์ MSG จำนวนหลายพันไฟล์ ให้ประมวลผลเป็นชุดเพื่อหลีกเลี่ยงการเพิ่มขึ้นของหน่วยความจำ.  
- **Asynchronous Execution:** ใช้ `CompletableFuture` หรือบริการ executor ของ Java เพื่อแปลงไฟล์แบบขนาน.  
- **Resource Cleanup:** ปิดสตรีมอย่างชัดเจนหากคุณเปิดสตรีมแบบกำหนดเองนอกเหนือจาก API ของ Aspose.  

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|-------------------|----------|
| **NullPointerException on `msg.save`** | ไดเรกทอรีผลลัพธ์ไม่มีอยู่ | สร้างไดเรกทอรีหรือใช้ `Files.createDirectories(Paths.get(outputDir));` |
| **Missing attachments in MHT** | `MhtSaveOptions` ไม่ได้ตั้งค่าให้ฝังทรัพยากร | Use `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **Incorrect date format** | การตั้งค่า Locale แตกต่าง | Adjust `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## คำถามที่พบบ่อย

**Q: ความแตกต่างระหว่าง MSG และ MHT คืออะไร?**  
A: MSG เป็นรูปแบบไบนารีของ Outlook ที่เป็นกรรมสิทธิ์ซึ่งเก็บอีเมล, ไฟล์แนบ, และเมตาดาต้า. MHT (MHTML) เป็นรูปแบบไฟล์เดียวแบบ HTML ที่รวมเนื้อหาอีเมล, รูปภาพ, และ CSS ทำให้สามารถดูได้ในเบราว์เซอร์ใด ๆ  

**Q: ฉันสามารถแปลงรายการ MAPI อื่น ๆ เช่น การนัดหมายหรือรายชื่อผู้ติดต่อได้หรือไม่?**  
A: ได้. Aspose.Email รองรับการแปลงการนัดหมาย, รายชื่อผู้ติดต่อ, และงานเป็น MHT โดยใช้คลาส `Mapi*` ที่สอดคล้องและปรับชื่อเทมเพลต  

**Q: จำเป็นต้องเชื่อมต่ออินเทอร์เน็ตสำหรับการแปลงหรือไม่?**  
A: ไม่. การประมวลผลทั้งหมดทำงานในเครื่องภายใน Java runtime; เพียงการตรวจสอบการเปิดใช้งานไลเซนส์อาจติดต่อเซิร์ฟเวอร์ของ Aspose ครั้งเดียว  

**Q: การแปลงนี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?**  
A: API เองปลอดภัยต่อการทำงานหลายเธรดสำหรับการดำเนินการแบบอ่านอย่างเดียว. เมื่อแปลงไฟล์หลายไฟล์พร้อมกัน ควรสร้างอ็อบเจ็กต์ `MapiMessage` แยกต่างหากต่อเธรด  

**Q: Aspose.Email สามารถจัดการไฟล์ MSG ขนาดเท่าไหร่?**  
A: ไลบรารีสามารถประมวลผลไฟล์ได้ถึงหลายร้อยเมกะไบต์, แต่ควรตรวจสอบขนาด heap ของ JVM และพิจารณาการสตรีมไฟล์แนบขนาดใหญ่  

## สรุป

ตอนนี้คุณมีขั้นตอนทำงานที่ครบถ้วนและพร้อมใช้งานในสภาพแวดล้อมการผลิตเพื่อ **แปลง MSG เป็น MHT** ด้วย Aspose.Email สำหรับ Java. ด้วยการใช้เทมเพลตแบบกำหนดเอง คุณสามารถปรับผลลัพธ์ HTML ให้ตรงกับแบรนด์หรือมาตรฐานรายงานขององค์กรของคุณ, ในขณะที่ไลบรารีจัดการการแยกวิเคราะห์รูปแบบไบนารีของ Outlook อย่างเต็มที่.  

**ขั้นตอนต่อไป:**  
- ทดลองใช้ค่า `MhtTemplateName` ต่าง ๆ เพื่อจัดรูปแบบประเภทรายการ MAPI อื่น  
- รวมการแปลงเข้าเป็นงานแบบ batch หรือบริการ REST เพื่อประมวลผลตามความต้องการ  
- สำรวจคุณลักษณะอื่นของ Aspose.Email เช่น การจัดการ PST, การส่งอีเมล, และการแยกวิเคราะห์ MIME  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-17  
**ทดสอบด้วย:** Aspose.Email for Java 25.4 (classifier `jdk16`)  
**ผู้เขียน:** Aspose