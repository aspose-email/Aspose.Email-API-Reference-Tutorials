---
date: '2026-06-13'
description: เรียนรู้วิธีอ่านไฟล์ MSG และแยกวิเคราะห์ไฟล์แนบ MSG ด้วย Aspose.Email
  for Java เพื่อดึงข้อมูลใบรับรองการจัดส่ง/การอ่านและผลการโหวตอย่างมีประสิทธิภาพ รวมถึงการตั้งค่า,
  โค้ด, และแนวปฏิบัติที่ดีที่สุด
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: วิธีอ่านไฟล์ MSG ด้วย Aspose.Email for Java
url: /th/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีอ่านไฟล์ MSG ด้วย Aspose.Email สำหรับ Java

## บทนำ

การอ่านไฟล์ MSG ด้วยโปรแกรมช่วยให้คุณดึงข้อมูลการติดตามที่มีค่า—ใบรับรองการจัดส่ง, การยืนยันการอ่าน, และผลการโหวต—จากข้อความ Outlook ได้ ในคู่มือนี้เราจะแสดง **วิธีอ่านไฟล์ msg** ด้วย Aspose.Email สำหรับ Java, แสดงขั้นตอนการตั้งค่าที่จำเป็น, และสาธิตวิธีดึงข้อมูลใบรับรองและโหวตอย่างมีประสิทธิภาพ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่จัดการการแยกวิเคราะห์ MSG คืออะไร?** Aspose.Email for Java.  
- **ฉันสามารถดึงใบรับรองการอ่านได้หรือไม่?** ใช่, API จะคืนค่า timestamp ของการจัดส่งและการอ่าน.  
- **ข้อมูลการโหวตสามารถเข้าถึงได้หรือไม่?** แน่นอน; คุณสามารถดึงการตอบโหวตของผู้รับแต่ละคนได้.  
- **ฉันต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองทำงานสำหรับการทดสอบ; ไลเซนส์แบบชำระเงินจะลบข้อจำกัดการประเมิน.  
- **ต้องการเวอร์ชัน Java ไหน?** แนะนำให้ใช้ Java 16 หรือใหม่กว่า.

## Aspose.Email สำหรับ Java คืออะไร?

Aspose.Email for Java เป็นไลบรารี Java แยกส่วนที่ช่วยให้สร้าง, ปรับแต่ง, และแปลงรูปแบบอีเมลโดยไม่ต้องใช้ Microsoft Outlook มันให้โมเดลวัตถุที่ครอบคลุมสำหรับ MSG, EML, PST, และรูปแบบอื่น ๆ มากมาย, ทำให้นักพัฒนาสามารถทำงานกับข้อมูลอีเมลโดยตรงจากโค้ด Java. (45 คำ)

## ทำไมต้องใช้ Aspose.Email สำหรับ Java เพื่ออ่านไฟล์ MSG?

Aspose.Email for Java รองรับ **รูปแบบอีเมลกว่า 30 แบบ** และสามารถประมวลผลไฟล์ MSG ขนาด **สูงสุด 500 MB** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ เครื่องยนต์การแยกวิเคราะห์ที่มีประสิทธิภาพสูงช่วยลดการใช้ CPU และหน่วยความจำ, ทำให้เหมาะสำหรับการประมวลผลอีเมลขนาดใหญ่และสถานการณ์วิเคราะห์แบบเรียลไทม์. (48 คำ)

## ข้อกำหนดเบื้องต้น

- **ไลบรารีและการพึ่งพา:** Aspose.Email for Java เวอร์ชัน 25.4 หรือใหม่กว่าและรันไทม์ JDK 16+.  
- **IDE:** IntelliJ IDEA, Eclipse หรือ IDE ที่รองรับ Java ใด ๆ พร้อมการสนับสนุน Maven.  
- **ทักษะพื้นฐาน:** ความคุ้นเคยกับไวยากรณ์ Java และแนวคิดเชิงวัตถุ.

## การรับไลเซนส์

- **ทดลองใช้ฟรี:** เริ่มต้นด้วยเวอร์ชันทดลองใช้ฟรีที่มีบน [Aspose's website](https://releases.aspose.com/email/java/).  
- **ไลเซนส์ชั่วคราว:** ขอไลเซนส์ชั่วคราวจาก [purchase page](https://purchase.aspose.com/temporary-license/).  
- **การซื้อ:** หากคุณพอใจกับการประเมิน, ซื้อไลเซนส์เพื่อเข้าถึงคุณสมบัติทั้งหมดผ่านหน้า [Buy Aspose Products](https://purchase.aspose.com/buy) .

## วิธีดึงข้อมูลใบรับรองการอ่านและการจัดส่งจากไฟล์ MSG?

โหลดไฟล์ MSG, วนลูปผ่านผู้รับ, และอ่านคุณสมบัติ `DeliveryTime` และ `ReadTime`. วิธีนี้จะคืนค่า timestamp ที่แน่นอนเมื่อเซิร์ฟเวอร์ของผู้รับแต่ละคนจัดส่งข้อความและเมื่อผู้รับเปิดข้อความ, ให้ข้อมูลการติดตามที่แม่นยำสำหรับการวิเคราะห์. (53 คำ)

### ขั้นตอนที่ 1: โหลดไฟล์ MSG
MapiMessage คือคลาสของ Aspose.Email ที่แสดงข้อความ Outlook MSG.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### ขั้นตอนที่ 2: วนลูปผู้รับ
MapiRecipient แสดงผู้รับคนเดียว (To, CC หรือ BCC) ในไฟล์ MSG.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### ขั้นตอนที่ 3: ดึงและพิมพ์เวลาการจัดส่ง
DeliveryTime เป็นคุณสมบัติของ MapiRecipient ที่เก็บ timestamp เมื่อข้อความถูกจัดส่งไปยังเซิร์ฟเวอร์ของผู้รับ.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### ขั้นตอนที่ 4: ดึงและพิมพ์เวลาการอ่าน
ReadTime เป็นคุณสมบัติของ MapiRecipient ที่บ่งบอกว่าเมื่อใดผู้รับเปิดข้อความ, หากข้อมูลนั้นมีอยู่.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## วิธีอ่านผลการโหวตจากไฟล์ MSG?

หลังจากโหลดข้อความ, API จะเปิดเผยการตอบโหวตของผู้รับแต่ละคนและเวลาที่พวกเขาตอบ, ทำให้คุณสามารถสรุปผลโพลได้โดยอัตโนมัติ ข้อมูลนี้สามารถใช้สร้างรายงานสรุปหรือป้อนโดยตรงเข้าสู่แดชบอร์ด BI เพื่อการตัดสินใจอย่างรวดเร็ว. (53 คำ)

### ขั้นตอนที่ 1: โหลดไฟล์ MSG
MapiMessage ถูกใช้อีกครั้งเพื่อเข้าถึงข้อมูลการโหวตที่ฝังอยู่ในไฟล์ MSG.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### ขั้นตอนที่ 2: วนลูปผู้รับ
MapiRecipient ให้เข้าถึงการเลือกโหวตและเวลาตอบของผู้เข้าร่วมแต่ละคน.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### ขั้นตอนที่ 3: ดึงและพิมพ์การตอบสนอง
คุณสมบัติ `VotingResponse` มีการโหวตจริง (เช่น “Accept”, “Decline”, หรือตัวเลือกที่กำหนดเอง).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### ขั้นตอนที่ 4: ดึงและพิมพ์เวลาการตอบสนอง
`VotingResponseTime` บันทึกเวลาที่ผู้รับส่งการโหวตของพวกเขา, ช่วยให้วิเคราะห์กิจกรรมโพลตามลำดับเวลา.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## การประยุกต์ใช้งานจริง

1. **การติดตามแคมเปญอีเมล:** วัดอัตราการเปิดและความสำเร็จของการจัดส่งโดยวิเคราะห์ timestamp ของใบรับรอง.  
2. **การวิเคราะห์แบบสำรวจ:** รวมผลการโหวตจากโพล Outlook เพื่อการตัดสินใจอย่างรวดเร็ว.  
3. **การจัดการข้อเสนอแนะของลูกค้า:** ดึงข้อมูลการตอบกลับเข้าสู่ CRM หรือแพลตฟอร์มวิเคราะห์เพื่อความเข้าใจที่ลึกซึ้ง.

การรวมข้อมูลที่ดึงเหล่านี้กับฐานข้อมูลหรือเครื่องมือ BI จะเพิ่มคุณค่าของข้อมูลอีเมลดิบ.

## ข้อควรพิจารณาด้านประสิทธิภาพ

- ประมวลผลไฟล์ MSG ขนาดใหญ่เป็น **chunks** เพื่อรักษาการใช้หน่วยความจำน้อย.  
- ใช้ **streaming APIs** เมื่อจัดการกับข้อความหลายพันฉบับ.  
- เก็บข้อมูลผู้รับในคอลเลกชันที่เบา เช่น `ArrayList` หรือ `HashMap` เพื่อการค้นหาเร็ว.

## ปัญหาที่พบบ่อยและวิธีแก้ไข

- **Timestamp เป็น null:** การไม่มี `ReadTime` มักหมายความว่าผู้รับยังไม่ได้เปิดข้อความ.  
- **ไฟล์แนบขนาดใหญ่:** หาก MSG มีไฟล์แนบขนาดใหญ่, เปิดใช้งาน `LoadOptions.setPreserveEmbeddedResources(false)` เพื่อข้ามการโหลดเข้าสู่หน่วยความจำ.  
- **ปัญหา Encoding:** ตรวจสอบให้แน่ใจว่าได้ตั้ง code page ที่ถูกต้องผ่าน `MailMessage.setCharset(Charset.forName("UTF-8"))` เมื่ออ่านเนื้อหาที่ไม่ใช่ ASCII.

## คำถามที่พบบ่อย

**Q: วิธีจัดการไฟล์ MSG ที่ใหญ่กว่า 500 MB?**  
A: แบ่งไฟล์เป็นส่วนย่อยหรือใช้ streaming API เพื่ออ่านส่วนโดยไม่ต้องโหลดเต็มในหน่วยความจำ.

**Q: สามารถเก็บข้อมูลที่ดึงได้โดยตรงลงฐานข้อมูลได้หรือไม่?**  
A: ได้, ทำการแมปฟิลด์ใบรับรองและโหวตไปยังสคีมาฐานข้อมูลของคุณและใช้ JDBC หรือ ORM เพื่อบันทึก.

**Q: ไลบรารีทำงานบนสภาพแวดล้อม Linux หรือไม่?**  
A: แน่นอน; Aspose.Email for Java เป็นแบบ platform‑agnostic และทำงานบน OS ใดก็ได้ที่มี JDK ที่รองรับ.

**Q: มีวิธีดึงไฟล์แนบพร้อมกับการอ่านใบรับรองหรือไม่?**  
A: ใช้ `MailMessage.getAttachments()` หลังจากโหลด MSG; เมธอดนี้จะคืนคอลเลกชันของไฟล์แนบทั้งหมดที่ฝังอยู่.

**Q: มีตัวเลือกการสนับสนุนอะไรบ้างหากพบบั๊ก?**  
A: ติดต่อผ่าน Aspose Email Forum อย่างเป็นทางการเพื่อขอความช่วยเหลือจากชุมชนหรือเปิด ticket สนับสนุนพร้อมไลเซนส์ที่ถูกต้อง.

## แหล่งข้อมูล
- **เอกสาร:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **เอกสาร (สำเนา):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **ดาวน์โหลด SDK:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **ส่วนดาวน์โหลด:** [Download Section](https://releases.aspose.com/email/java/)  
- **ซื้อไลเซนส์:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **ทดลองใช้ฟรี:** เริ่มต้นด้วย [Free Trial Version](https://releases.aspose.com/email/java/)  
- **ไลเซนส์ชั่วคราว:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **ฟอรั่มสนับสนุน:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **ฟอรั่มสนับสนุน (สำเนา):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**อัปเดตล่าสุด:** 2026-06-13  
**ทดสอบด้วย:** Aspose.Email for Java 25.4  
**ผู้เขียน:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีโหลดและแยกวิเคราะห์ไฟล์ Outlook MSG ด้วย Aspose.Email สำหรับ Java: คู่มือครบถ้วน](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [แปลง MSG เป็น EML และจัดการไฟล์แนบด้วย Aspose.Email สำหรับ Java](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [ดึงไฟล์แนบแบบอินไลน์ Java – ไฟล์ MSG ด้วย Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}