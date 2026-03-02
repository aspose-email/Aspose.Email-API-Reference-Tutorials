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
# Maven Aspose.Email for Java: วิธีบันทึกอีเมลเป็นไฟล์ MHT

## Introduction

การจัดการข้อมูลอีเมลอย่างมีประสิทธิภาพอาจเป็นความท้าทาย โดยเฉพาะเมื่อพูดถึงการแชร์และการเก็บถาวร ในคู่มือนี้เราจะแสดงให้คุณ **วิธีบันทึกไฟล์ MHT** ด้วย **Maven Aspose.Email for Java** เพื่อให้คุณสามารถแปลงอีเมลเป็น MHT ด้วยเทมเพลตที่กำหนดเองและคงข้อมูลปฏิทินไว้ คุณจะได้โซลูชันพร้อมใช้งานที่ทำงานในสภาพแวดล้อม Java 16+ ใด ๆ

## Quick Answers
- **ต้องใช้ไลบรารีอะไร?** Maven Aspose.Email for Java (v25.4+).  
- **รูปแบบที่สร้างคืออะไร?** ไฟล์ MHT (MHTML) ที่รวม HTML, รูปภาพ, และข้อมูลปฏิทิน.  
- **ฉันสามารถปรับแต่งส่วนหัวได้หรือไม่?** ได้ – ใช้ `MhtFormatOptions` และสตริงเทมเพลต.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์ถาวรสำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java อะไร?** JDK 16 หรือใหม่กว่า.

## What is Maven Aspose.Email for Java?
Maven Aspose.Email for Java คือ API ที่ทรงพลังที่ให้คุณสร้าง อ่าน แปลง และจัดการข้อความอีเมลโดยตรงจากโค้ด Java มันรองรับรูปแบบหลากหลายรวมถึง MSG, EML, และ MHT—ทำให้เหมาะสำหรับงาน **java email conversion**.

## Why Convert Emails to MHT?
- **เป็นมิตรกับเว็บ**: ไฟล์ MHT แสดงผลในเบราว์เซอร์โดยไม่ต้องใช้ทรัพยากรภายนอก.  
- **ความเสถียรของการเก็บถาวร**: ทรัพยากรทั้งหมดถูกฝังไว้ ทำให้คงลักษณะเดิม.  
- **รองรับปฏิทิน**: คุณสามารถแสดงเหตุการณ์ที่เกิดซ้ำด้วยเทมเพลตที่กำหนดเอง.  

## Prerequisites
- **Aspose.Email for Java** (Maven artifact `com.aspose:aspose-email:25.4` with `jdk16` classifier).  
- **Maven** ที่ติดตั้งและกำหนดค่าในเครื่องของคุณ.  
- **JDK 16+** (ไลบรารีนี้มุ่งเป้าไปที่ Java 16).  
- ความรู้พื้นฐานของ Java (การจัดการไฟล์, การพึ่งพา Maven).

## Setting Up Aspose.Email for Java

### Maven Dependency

Add the following dependency to your `pom.xml` file:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

Aspose มีการทดลองใช้ฟรีเพื่อสำรวจความสามารถของมัน พร้อมตัวเลือกในการซื้อไลเซนส์หรือขอรับไลเซนส์ชั่วคราว

1. **Free Trial**: ดาวน์โหลดจาก [Releases](https://releases.aspose.com/email/java/) และสำรวจฟีเจอร์โดยไม่มีข้อจำกัด.  
2. **Temporary License**: เข้าถึงเวอร์ชันเต็มโดยขอผ่านหน้า [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase**: ซื้อ: พิจารณาซื้อหาก Aspose.Email ตอบสนองความต้องการของโครงการระยะยาวของคุณ.

### Basic Initialization

Once installed, initialize the library in your Java application:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## Implementation Guide

### Feature 1: Load MailMessage

#### Overview
Loading an email message is the first step in processing and saving it as an MHT file. Here, we demonstrate how to load a `.msg` file using `MailMessage`.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MailMessage;
```

**Load Email from File**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

โค้ดส่วนนี้โหลดข้อความอีเมลที่อยู่ในไดเรกทอรีที่คุณระบุ.

### Feature 2: Configure MhtSaveOptions

#### Overview
Configuring `MhtSaveOptions` is crucial for defining how your email will be saved as an MHT file, including custom formatting for calendar events.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Set Save Options and Templates**

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

การกำหนดค่านี้ตั้งค่าส่วนหัวและการแสดงเหตุการณ์ปฏิทินในผลลัพธ์ MHT.

### Feature 3: Save MailMessage as MHT

#### Overview
The final step is to save your configured `MailMessage` as an MHT file using the specified options.

#### Step‑by‑Step

**Import Required Classes**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Save Email Message**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

คำสั่งนี้เขียนอีเมลเป็นไฟล์ MHT พร้อมสำหรับการแชร์หรือเก็บถาวร.

## Practical Applications
- **การเก็บถาวรอีเมล**: แปลงและเก็บอีเมลสำคัญในรูปแบบที่เป็นมิตรกับเว็บ.  
- **เอกสารทางกฎหมาย**: ใช้ไฟล์ MHT เป็นส่วนหนึ่งของหลักฐานทางกฎหมายที่ต้องการการเก็บรักษารายละเอียดอีเมล.  
- **การแชร์ข้ามแพลตฟอร์ม**: แชร์อีเมลระหว่างแพลตฟอร์มโดยไม่มีปัญหาความเข้ากันได้.  

การผสานรวมกับระบบอื่น ๆ เช่น CRM หรือเครื่องมือจัดการโครงการ สามารถเพิ่มประสิทธิภาพการทำงานร่วมกันโดยฝังข้อมูลอีเมลสำคัญลงในกระบวนการทำงานโดยตรง.

## Performance Considerations
To ensure optimal performance:
- จัดการการใช้หน่วยความจำอย่างมีประสิทธิภาพเมื่อจัดการอีเมลจำนวนมาก.  
- ปรับแต่งการทำงานของ I/O ไฟล์เพื่อป้องกันคอขวดระหว่างกระบวนการบันทึก.  

การปฏิบัติตามแนวทางการจัดการหน่วยความจำของ Java จะทำให้แอปพลิเคชันของคุณตอบสนองได้ดี.

## Common Issues and Solutions
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **NullPointerException on `msg.save`** | เส้นทางออกไม่ถูกต้อง | ตรวจสอบว่า `YOUR_OUTPUT_DIRECTORY` มีอยู่และสามารถเขียนได้. |
| **Missing images in MHT** | `MhtFormatOptions` ไม่ได้ตั้งค่าให้ฝังทรัพยากร | เพิ่ม `MhtFormatOptions.EmbedResources` ไปยังแฟล็กของตัวเลือก. |
| **Calendar events not rendered** | ไม่ได้ตั้งค่าแฟล็ก `RenderCalendarEvent` | ตรวจสอบให้แน่ใจว่า `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Frequently Asked Questions

**Q: ฉันจะจัดการไฟล์แนบอย่างไรเมื่อบันทึกอีเมลเป็น MHT?**  
A: ตรวจสอบให้ `MhtSaveOptions` ถูกกำหนดค่าให้รวมตรรกะการจัดการไฟล์แนบ ไลบรารีรองรับการฝังไฟล์แนบลงในไฟล์ MHT.

**Q: ฉันสามารถปรับแต่งส่วนหัวของอีเมลในไฟล์ MHT ที่ส่งออกได้หรือไม่?**  
A: ได้, ใช้ `MhtFormatOptions.WriteHeader` และกำหนดเทมเพลตที่กำหนดเองสำหรับฟิลด์ส่วนหัวต่าง ๆ ตามที่แสดงในบทแนะนำ.

**Q: ความต้องการระบบสำหรับการใช้ Aspose.Email Java คืออะไร?**  
A: ต้องการ JDK 16 หรือสูงกว่า ไลบรารีทำงานได้อย่างราบรื่นกับ IDE สมัยใหม่ส่วนใหญ่ที่รองรับโครงการ Maven.

**Q: สามารถบันทึกเฉพาะส่วนของข้อความอีเมลได้หรือไม่?**  
A: แม้รูปแบบ MHT ปกติจะรวมข้อความทั้งหมด คุณสามารถใช้คุณสมบัติของ `MailMessage` เพื่อประมวลผลและรวมเนื้อหาแบบเลือกได้.

**Q: ฉันจะแก้ไขปัญหาเกี่ยวกับการโหลดหรือบันทึกอีเมลได้อย่างไร?**  
A: ตรวจสอบเส้นทางไฟล์ว่าถูกต้อง, ตรวจสอบการตั้งค่าลไบบรารีในโครงการของคุณ, และอ้างอิงที่ [support forum](https://forum.aspose.com/c/email/10) สำหรับความช่วยเหลือ.

**Q: ไลบรารีรองรับการแปลงรูปแบบอื่น (EML, MSG) เป็น MHT หรือไม่?**  
A: แน่นอน. `MailMessage.load` สามารถอ่าน EML, MSG และรูปแบบอื่น ๆ หลังจากนั้นคุณสามารถบันทึกเป็น MHT ด้วยตัวเลือกเดียวกัน.

## Resources
- **เอกสาร**: เพื่อทำความเข้าใจฟังก์ชันทั้งหมดอย่างลึกซึ้ง ให้เยี่ยมชม [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **ดาวน์โหลด**: เริ่มต้นทดลองใช้ฟรีโดยดาวน์โหลดจาก [Releases](https://releases.aspose.com/email/java/).  
- **ซื้อ**: สำรวจตัวเลือกการซื้อที่ [Official Purchase Page](https://purchase.aspose.com/buy) สำหรับการใช้งานระยะยาว.  
- **การทดลองใช้ฟรีและไลเซนส์ชั่วคราว**: เข้าถึงคุณสมบัติครบถ้วนในช่วงทดลองใช้ฟรีหรือขอรับไลเซนส์ชั่วคราวผ่านลิงก์เหล่านี้:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

สำรวจ, นำไปใช้, และเปลี่ยนแปลงการจัดการอีเมลของคุณด้วย Aspose.Email for Java วันนี้!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-02  
**ทดสอบกับ:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose