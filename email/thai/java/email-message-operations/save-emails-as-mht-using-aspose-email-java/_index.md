---
date: '2026-03-02'
description: เรียนรู้วิธีใช้ Maven Aspose.Email สำหรับ Java เพื่อบันทึกอีเมลเป็นไฟล์
  MHT คู่มือทีละขั้นตอนนี้ครอบคลุมการตั้งค่า แม่แบบที่กำหนดเอง และการแปลงอีเมลเป็น
  MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email สำหรับ Java: บันทึกอีเมลเป็นไฟล์ MHT'
url: /th/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email สำหรับ Java: วิธีบันทึกอีเมลเป็นไฟล์ MHT

## การแนะนำ

ข้อมูลข่าวสารอย่างมีประสิทธิภาพอาจเป็นไปได้ที่จะนำไปใช้กับการแชร์และการเก็บถาวรในคู่มือนี้เราจะแสดงให้คุณ ** วิธีบันทึกไฟล์ MHT** ด้วย **Maven Aspose.Email for Java** เพื่อให้คุณสามารถแปลงอีเมลเป็น MHT ด้วยวิธีการรวบรวมข้อมูลและคงข้อมูลปฏิทินไว้คุณจะได้ใช้งานระบบปฏิบัติการ Java 16+ ใด ๆ ใด ๆ

## คำตอบด่วน
- **ต้องใช้ไลบรารีอะไร?** Maven Aspose.Email for Java (v25.4+)
- ** รูปแบบที่ต้องการตลอดเวลาคืออะไร?** ใน MHT (MHTML) ที่รวม HTML, รูปภาพ, ปฏิทินปฏิทิน
- **ฉันสามารถทำได้หรือเปล่า?** ได้ – ใช้ `MhtFormatOptions` และต้องรอตามนั้น
- ** ตรวจสอบไลเซนส์หรือไม่?** เอกสารฟรีทำงานสำหรับระบบปฏิบัติการ; อย่าลืมไลเซนส์ถาวรอย่างแท้จริง.
- **ต้องการเจาะ Java อะไร?** JDK16 หรือใหม่กว่า.

## Maven Aspose.Email สำหรับ Java คืออะไร
Maven Aspose.Email for Java คือ API ที่คุณให้คุณสร้างอ่านและจัดการข้อความอีเมลต่างๆ โค้ด Java รองรับรูปแบบต่างๆ รวมถึง MSG, EML, และ MHT—ทำให้เหมาะสำหรับงาน **การแปลงอีเมล java**.

## ทำไมต้องแปลงอีเมลเป็น MHT
- ** เข้ามาจัดการเว็บ**: ด้วย MHT ในการปรับแต่งทรัพยากรภายนอก
- **ทรัพยากรของการเก็บถาวร**: ทรัพยากรทั้งหมดถูกฝังไว้ซึ่งไม่คงลักษณะเดิม
- ** รองรับปฏิทิน**: บันทึกเหตุการณ์ที่เกิดขึ้นซ้ำอีกครั้งด้วยปฏิทินดังกล่าว

## ข้อกำหนดเบื้องต้น
- **Aspose.Email สำหรับ Java** (ส่วน Maven `com.aspose:aspose-email:25.4` พร้อมด้วยตัวแยกประเภท `jdk16`)
- **Maven** สามารถติดตั้งและไม่จำเป็นต้องในเครื่องของคุณ
- **JDK16+** (ไลบรารีนี้มีเป้าหมายไปที่ Java16).
- ความรู้ในรูปแบบ Java (การจัดการไฟล์, การบันเทิง Maven)

## การตั้งค่า Aspose.Email สำหรับ Java

### การเพิ่ม Dependency ใน Maven

เพิ่ม Dependency ต่อไปนี้ลงในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### การได้มาซึ่งใบอนุญาต

พิจารณาภาพรวมฟรีเพื่อสำรวจเพิ่มเติมเกี่ยวกับตัวเลือกต่างๆ ในการซื้อไลเซนส์หรือขอรับสิทธิ์เช่นเซนส์ชั่วคราว

1. **ทดลองใช้ฟรี**: ดาวน์โหลดจาก [เผยแพร่](https://releases.aspose.com/email/java/) และสำรวจโดยไม่ต้องคำนึงถึง
2. **ใบอนุญาตชั่วคราว**: เข้าถึงแบบเต็มโดยขอผ่านหน้า [หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)
3. **การซื้อ**: ซื้อ: พิจารณาซื้อหาก Aspose.Email เรียกร้องโครงการระยะยาวของคุณ

### การเริ่มต้นขั้นพื้นฐาน

เมื่อติดตั้งแล้ว ให้เริ่มต้นไลบรารีในแอปพลิเคชัน Java ของคุณ:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```
เมื่อทำตามขั้นตอนเหล่านี้เสร็จแล้ว คุณก็พร้อมที่จะใช้คุณสมบัติของ Aspose.Email เพื่อการจัดการอีเมลอย่างมีประสิทธิภาพ

## คู่มือการใช้งาน

### คุณสมบัติที่ 1: โหลด MailMessage

#### ภาพรวม
การโหลดข้อความอีเมลเป็นขั้นตอนแรกในการประมวลผลและบันทึกเป็นไฟล์ MHT ในที่นี้ เราจะสาธิตวิธีการโหลดไฟล์ `.msg` โดยใช้ `MailMessage`

#### ขั้นตอนทีละขั้น

**นำเข้าคลาสที่จำเป็น**

```java
import com.aspose.email.MailMessage;
```

**โหลดอีเมลจากไฟล์**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

โค้ดส่วนนี้โหลดข้อความอีเมลที่อยู่ในไดเรกทอรีที่คุณระบุ.

### คุณสมบัติที่ 2: กำหนดค่า MhtSaveOptions

#### ภาพรวม
การกำหนดค่า `MhtSaveOptions` มีความสำคัญอย่างยิ่งในการกำหนดวิธีการบันทึกอีเมลของคุณเป็นไฟล์ MHT รวมถึงการจัดรูปแบบที่กำหนดเองสำหรับกิจกรรมในปฏิทิน


#### ขั้นตอนทีละขั้น

**นำเข้าคลาสที่จำเป็น**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**ตั้งค่าตัวเลือกการบันทึกและเทมเพลต**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

การตั้งค่านี้จะกำหนดส่วนหัวและการแสดงผลกิจกรรมในปฏิทินในเอาต์พุต MHT

### คุณสมบัติที่ 3: บันทึกข้อความอีเมลเป็น MHT

#### ภาพรวม
ขั้นตอนสุดท้ายคือการบันทึก `ข้อความอีเมล` ที่คุณกำหนดค่าไว้เป็นไฟล์ MHT โดยใช้ตัวเลือกที่ระบุ

#### ขั้นตอนทีละขั้น

**นำเข้าคลาสที่จำเป็น**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**บันทึกข้อความอีเมล**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

คำสั่งนี้เขียนอีเมลเป็นไฟล์ MHT พร้อมสำหรับการแชร์หรือเก็บถาวร.

## การใช้งานจริง
- **การเก็บถาวรอีเมล**: รูปแบบและเก็บอีเมลสำคัญที่เป็นมิตรกับเว็บ
- ** เอกสารการแก้ไข**: ใช้ไฟล์ MHT พิสูจน์หลักฐานที่ต้องการยืนยันรายละเอียดอีเมล
- **การแชร์ข้ามแพลตฟอร์ม**: แชร์อีเมลระหว่างแพลตฟอร์มโดยตำนาน.

การสังเกตระบบอื่น ๆ เช่น CRM หรือเครื่องมือจัดการโครงการที่มีการตรวจสอบโดยฝังข้อมูลอีเมลสำคัญลงในโปรแกรมทำงานโดยตรง

## ข้อควรพิจารณาด้านประสิทธิภาพ
เพื่อให้มั่นใจถึงประสิทธิภาพสูงสุด:
- การจัดการประสิทธิภาพของประสิทธิภาพอย่างมีประสิทธิภาพเมื่อจัดการอีเมลจำนวนมาก
- ปรับแต่ง I/O เพื่อรองรับคอขวดระหว่างฐานข้อมูลบันทึก

คำอธิบายเหตุผลในการจัดการของ Java จะทำให้แอปพลิเคชันของคุณมีประสิทธิภาพได้ดี

## ปัญหาทั่วไปและแนวทางแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **NullPointerException บน `msg.save`** | ไม่ต้องออกคำสั่ง | เพลง `YOUR_OUTPUT_DIRECTORY` ของเรามีอยู่ที่เขียนได้ |
| **ภาพหายไปใน MHT** | `MhtFormatOptions` ในการติดตั้งให้ฝังทรัพยากร | ยังคง `MhtFormatOptions.EmbedResources` ส่วนแฟล็กของตัวเลือก |
| **กิจกรรมในปฏิทินไม่แสดงผล** | การตั้งค่าแฟล็ก `RenderCalendarEvent` | คุณยังสามารถ `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## คำถามที่พบบ่อย

**ถาม: ฉันจะจัดการไฟล์แนบอย่างไรเมื่อบันทึกอีเมลเป็น MHT?**
ตอบ: การตัดให้ `MhtSaveOptions` ไม่จำเป็นต้องให้รวมการจัดการไฟล์แนบ ไลบรารีรองรับการฝังไฟล์แนบในไฟล์ MHT.

**คำถาม: สามารถสแกนอีเมลในไฟล์ MHT ที่ส่งออกได้หรือไม่**
ตอบ: ได้ ให้ใช้ `MhtFormatOptions.WriteHeader` และกำหนดทิศทางสำหรับความถี่ต่างๆ มากมายตามคำแนะนำบทแนะนำ

**คำถาม: ระบบสำหรับการใช้ Aspose.Email Java คืออะไร?**
ตอบ: ต้องการ JDK16 หรือไลบรารี่ทำงานร่วมกับ IDE ที่รองรับโครงการ Maven.

**ถาม: สามารถบันทึกเฉพาะข้อความที่เขียนถึงได้?**
ตอบ: รูปแบบของรูปแบบ MHT ปกติจะรวมข้อความทั้งหมดที่มีคุณสมบัติ `MailMessage` เพื่อยืนยันและรวมเนื้อหาแบบเลือกได้

**ถาม: ช่วยอธิบายเกี่ยวกับเรื่องนี้หรือบันทึกอีเมลได้อย่างไร?**
A: การถ่ายทำเส้นทางไฟล์ว่าถูกต้อง, การควบคุมตรวจการณ์ลไบบรารีตรวจสอบของคุณ, และอ้างอิงที่ [support forum](https://forum.aspose.com/c/email/10) สำหรับความช่วยเหลือ.

**ถาม: ไลบรารีรองรับรูปแบบอื่น (EML, MSG) เป็น MHT อย่างเป็นทางการ?**
A: แน่นอน. `MailMessage.load` สามารถอ่าน EML, MSG และรูปแบบอื่นๆ ที่คุณสามารถบันทึกเป็น MHT ในรูปแบบเดียวกัน

## ทรัพยากร
- **เอกสาร**: เพื่อทำความเข้าใจฟังก์ชันทั้งหมดอย่างลึกซึ้ง ให้เยี่ยมชม [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **ดาวน์โหลด**: เริ่มต้นทดลองใช้ฟรีโดยดาวน์โหลดจาก [Releases](https://releases.aspose.com/email/java/).  
- **ซื้อ**: สำรวจตัวเลือกการซื้อที่ [Official Purchase Page](https://purchase.aspose.com/buy) สำหรับการใช้งานระยะยาว.  
- **การทดลองใช้ฟรีและไลเซนส์ชั่วคราว**: เข้าถึงคุณสมบัติครบถ้วนในช่วงทดลองใช้ฟรีหรือขอรับไลเซนส์ชั่วคราวผ่านลิงก์เหล่านี้:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

สำรวจ, นำไปใช้, และเปลี่ยนแปลงการจัดการอีเมลของคุณด้วย Aspose.Email for Java วันนี้!

---

**อัปเดตล่าสุด:** 2026-03-02  
**ทดสอบกับ:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
