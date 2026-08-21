---
date: '2026-06-23'
description: เรียนรู้วิธีกรองอีเมลตามวันที่ ผู้ส่ง และหัวเรื่องโดยใช้ Aspose.Email
  สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะแสดงวิธีทำการกรองอีเมลผ่าน IMAP อย่างอัตโนมัติอย่างมีประสิทธิภาพ
keywords:
- how to filter emails
- filter emails by date
- filter emails by sender
- filter emails by subject
- aspose email java tutorial
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  headline: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  type: TechArticle
- description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  name: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later.'
    text: '**Java Development Kit (JDK)** – version 8 or later.'
  - name: '**Maven** – for dependency management.'
    text: '**Maven** – for dependency management.'
  - name: '**Aspose.Email for Java** – the core library we’ll use.'
    text: '**Aspose.Email for Java** – the core library we’ll use.'
  - name: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
    text: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
  - name: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
    text: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
  type: HowTo
- questions:
  - answer: Instantiate `ImapClient` with host, port, username, and password, then
      call `client.selectFolder("Inbox")`.
    question: How do I connect to an IMAP server using Aspose.Email?
  - answer: Yes – use `ImapQueryBuilder` to combine `date` and `fromAddress` criteria;
      the library sends a single SEARCH command.
    question: Can I filter emails by both date and sender in one request?
  - answer: Absolutely – set `client.setSecurityOptions(SecurityOptions.SSL_TLS)`
      before connecting.
    question: Does Aspose.Email support SSL/TLS for secure connections?
  - answer: The library can process mailboxes with **over 100,000 messages** as long
      as you use paging; memory usage stays below 50 MB.
    question: What is the maximum mailbox size Aspose.Email can handle?
  - answer: A temporary license removes the evaluation watermark and limits; a full
      license is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
title: วิธีกรองอีเมลใน Java ด้วย Aspose.Email – คู่มือสำหรับนักพัฒนา
url: /th/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีกรองอีเมลใน Java ด้วย Aspere.Email – คู่มือสำหรับนักพัฒนา

## บทนำ

หากคุณกำลังมองหา **วิธีกรองอีเมล** อย่างเป็นโปรแกรม คุณมาถูกที่แล้ว ไม่ว่าคุณจะจัดการกล่องเมลขององค์กร สร้างระบบตั๋วสนับสนุนลูกค้า หรือเพียงแค่ต้องการให้กล่องจดหมายส่วนตัวของคุณเป็นระเบียบ การทำอัตโนมัติการกรองอีเมลจะช่วยประหยัดเวลาหลายชั่วโมงจากการทำงานด้วยตนเอง ในบทแนะนำนี้เราจะใช้ **Aspose.Email for Java** ซึ่งเป็นไลบรารีที่รองรับโปรโตคอลอีเมลกว่า 30+ และสามารถจัดการกล่องเมลที่มีข้อความมากกว่า 100,000 ข้อความโดยไม่ต้องโหลดโฟลเดอร์ทั้งหมดเข้าสู่หน่วยความจำ คุณจะได้เรียนรู้วิธีเชื่อมต่อกับเซิร์ฟเวอร์ IMAP, กรองตามวันที่, ผู้ส่ง, หัวเรื่อง, และอื่น ๆ รวมถึงการเพิ่มประสิทธิภาพสำหรับการประมวลผลขนาดใหญ่

## คำตอบสั้น
- **ไลบรารีใดที่จัดการการกรอง IMAP ใน Java?** Aspose.Email for Java.  
- **ฉันสามารถกรองตามวันที่และผู้ส่งในคำสั่งเดียวได้หรือไม่?** ได้ – รวมเกณฑ์ด้วย `ImapQueryBuilder`.  
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** ไลเซนส์เต็มจะลบข้อจำกัดของรุ่นทดลอง; ไลเซนส์ชั่วคราวใช้สำหรับการทดสอบ.  
- **รองรับการแบ่งหน้า (paging) หรือไม่?** แน่นอน – ดึงข้อความเป็นหน้าเพื่อรักษาการใช้หน่วยความจำให้ต่ำ.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 8 หรือใหม่กว่า.

## การกรองอีเมลใน Java คืออะไร?

การกรองอีเมลใน Java หมายถึงการเลือกข้อความโดยอัตโนมัติตามเกณฑ์ที่กำหนด—เช่น วันที่, ผู้ส่ง, หรือหัวเรื่อง—เพื่อให้คุณประมวลผลเฉพาะส่วนที่เกี่ยวข้อง วิธีนี้ช่วยลดปริมาณข้อมูลที่ส่งผ่านเครือข่ายและทำให้ระบบต่อไปทำงานกับชุดอีเมลที่มุ่งเน้นได้, เพิ่มความเร็วและประหยัดทรัพยากร

## ทำไมต้องใช้ Aspose.Email for Java?

Aspose.Email for Java รองรับ **รูปแบบอินพุตและเอาต์พุตกว่า 30+** รวมถึง EML, MSG, MBOX, และ PST, และสามารถประมวลผล **กล่องเมลที่มีข้อความมากกว่า 100,000 ข้อความ** โดยคงการใช้หน่วยความจำต่ำกว่า 50 MB ด้วยการกรองและแบ่งหน้าที่ทำบนเซิร์ฟเวอร์ ไลบรารียังให้การสนับสนุนฟลัก IMAP ที่กำหนดเอง, การเข้ารหัส UTF‑8, และการค้นหาแบบแยกตัวพิมพ์ใหญ่‑เล็ก, ทำให้เป็นโซลูชันครบวงจรสำหรับการอัตโนมัติอีเมลระดับองค์กร

## ข้อกำหนดเบื้องต้น

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
2. **Maven** – สำหรับการจัดการ dependencies.  
3. **Aspose.Email for Java** – ไลบรารีหลักที่เราจะใช้.

### ไลบรารีและ Dependencies ที่จำเป็น

เพิ่ม dependency ของ Aspose.Email ลงในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับไลเซนส์

- **Free Trial** – ดาวน์โหลดรุ่นทดลองเพื่อสำรวจฟีเจอร์ทั้งหมด.  
- **Temporary License** – รับไลเซนส์แบบจำกัดเวลาเพื่อการทดสอบที่ยาวนานขึ้น.  
- **Full License** – ซื้อเพื่อใช้ในผลิตภัณฑ์และลบข้อจำกัดการประเมิน.  
- **License File** – รับไฟล์จาก [Aspose's website](https://purchase.aspose.com/temporary-license/).

## การตั้งค่า Aspose.Email for Java

เพื่อเริ่มใช้ Aspose.Email ให้ทำตามขั้นตอนต่อไปนี้:

1. **Download and Install** – Maven จะดึงไลบรารีโดยอัตโนมัติจาก placeholder ด้านบน.  
2. **Initialize Library** – โหลดไฟล์ไลเซนส์ของคุณ (ถ้ามี) ก่อนทำการเรียก API ใด ๆ:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## คู่มือการใช้งาน

### วิธีเชื่อมต่อกับเซิร์ฟเวอร์ IMAP?

ก่อนอื่นคุณต้องสร้างการเชื่อมต่อกับเซิร์ฟเวอร์ IMAP โดยใช้คลาส `ImapClient` ซึ่งเป็นเซสชันไคลเอนต์ที่สามารถทำการตรวจสอบสิทธิ์และส่งคำสั่งไปยังเซิร์ฟเวอร์ การเชื่อมต่อนี้เป็นพื้นฐานสำหรับการทำงานกับกล่องเมลทั้งหมดต่อไป

ลำดับการเชื่อมต่อทั่วไปจะระบุโฮสต์, พอร์ต, ข้อมูลผู้ใช้, และตัวเลือกความปลอดภัย, จากนั้นเลือกโฟลเดอร์เมลที่ต้องการ (เช่น **Inbox**) ก่อนทำการค้นหาใด ๆ

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### วิธีกรองอีเมลตามหัวเรื่องและวันที่?

คลาส `ImapQueryBuilder` ช่วยให้คุณสร้างเกณฑ์การค้นหาที่ซับซ้อนซึ่งจะถูกแปลงเป็นคำสั่ง IMAP SEARCH ที่มีประสิทธิภาพ โดยการรวมคีย์เวิร์ดหัวเรื่องกับช่วงวันที่ คุณสามารถดึงข้อความที่เกี่ยวข้องกับตรรกะการประมวลผลของคุณเท่านั้น

ในตัวอย่างนี้เราจะค้นหาข้อความที่หัวเรื่องมีคำว่า “Newsletter” และได้รับในวันปัจจุบัน เพื่อลดการถ่ายโอนข้อมูลและภาระการประมวลผล

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### วิธีกรองอีเมลตามวันที่วันนี้?

โดยใช้ `ImapQueryBuilder` คุณสามารถสร้างฟิลเตอร์ที่ตรงกับวันที่ปฏิทินของเวลาที่ส่งของข้อความได้ นี่เป็นประโยชน์สำหรับงานประมวลผลรายวันที่ต้องทำงานกับข้อความใหม่ที่สุดเท่านั้น

บิลเดอร์จะจัดรูปแบบวันที่ตามโปรโตคอล IMAP โดยอัตโนมัติ, ทำให้การกรองบนเซิร์ฟเวอร์แม่นยำโดยไม่ต้องทำการแปลงเพิ่มเติมบนไคลเอนต์

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### วิธีกรองอีเมลตามช่วงวันที่?

เมื่อคุณต้องทำงานกับช่วงหลายวัน, `ImapQueryBuilder` อนุญาตให้กำหนด `DateTime` เริ่มต้นและสิ้นสุด ไลบรารีจะเปลี่ยนค่าเหล่านี้เป็นไวยากรณ์ IMAP SEARCH ที่เหมาะสม, ส่งคืนข้อความทั้งหมดที่อยู่ในช่วงที่กำหนด

เทคนิคนี้เหมาะสำหรับการสร้างรายงานประจำสัปดาห์หรือการเก็บถาวรข้อความที่เก่ากว่าขีดจำกัดที่กำหนด

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### วิธีกรองอีเมลตามผู้ส่งเฉพาะ?

`ImapQueryBuilder` สามารถกำหนดเป้าหมายที่อยู่อีเมลเดียวหรือโดเมนทั้งหมดโดยจับคู่กับหัว `From` ทำให้คุณแยกการสื่อสารจากพันธมิตรที่เชื่อถือได้หรือกรองผู้ส่งที่ไม่ต้องการออก

ระบุที่อยู่ที่ต้องการ (เช่น `user@example.com`) หรือรูปแบบโดเมน (เช่น `@example.com`) จะให้ผลลัพธ์ที่แม่นยำโดยตรงจากเซิร์ฟเวอร์

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### วิธีกรองอีเมลตามโดเมนเฉพาะ?

คล้ายกับการกรองผู้ส่ง, คุณสามารถจำกัดผลลัพธ์ให้เป็นโดเมนเฉพาะโดยใช้เมธอด `fromAddress` ของ `ImapQueryBuilder` นี่เป็นประโยชน์เมื่อคุณต้องประมวลผลข้อความทั้งหมดที่มาจากพันธมิตรองค์กรหรือผู้ให้บริการอีเมลเฉพาะ

การค้นหาจะดำเนินการบนเซิร์ฟเวอร์, ดังนั้นจะส่งข้อความที่ตรงเงื่อนไขเท่านั้นไปยังแอปพลิเคชันของคุณ

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### วิธีกรองอีเมลตามผู้รับเฉพาะ?

เพื่อโฟกัสที่ข้อความที่ส่งถึงกล่องเมลใดกล่องหนึ่ง, ใช้เมธอด `toAddress` ของ `ImapQueryBuilder` นี้มีประโยชน์สำหรับกล่องจดหมายร่วมหรือกล่องเมลตามบทบาทที่ผู้ใช้หลายคนต้องประมวลผลชุดอีเมลเดียวกัน

บิลเดอร์จะสร้าง clause IMAP SEARCH ที่จับคู่หัว `To`, ทำให้การกรองบนเซิร์ฟเวอร์มีประสิทธิภาพ

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### วิธีทำการกรองอีเมลแบบแยกตัวพิมพ์ใหญ่‑เล็ก?

โดยค่าเริ่มต้นการค้นหา IMAP ไม่แยกตัวพิมพ์ใหญ่‑เล็ก, แต่ `ImapQueryBuilder` มีตัวเลือกให้บังคับใช้การแยกตัวพิมพ์ใหญ่‑เล็กสำหรับการจับคู่ที่ตรงกันเต็มที่ นี่สำคัญเมื่อคุณต้องแยกแยะตัวระบุที่ต่างกันเพียงแค่ตัวอักษร

เปิดฟลัก `setCaseSensitive(true)` ก่อนเพิ่มเกณฑ์อื่นเพื่อให้ได้การกรองที่แม่นยำ

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### วิธีกำหนดการเข้ารหัสสำหรับ Query Builder?

เมื่อทำงานกับหัวเรื่องหรือที่อยู่ที่เป็นสากล, คุณควรตั้งค่าการเข้ารหัสอักขระบน `ImapQueryBuilder` การใช้ UTF‑8 จะทำให้ตัวอักษรที่ไม่ใช่ ASCII ถูกตีความโดยเซิร์ฟเวอร์ IMAP อย่างถูกต้อง

เรียก `setEncoding(Encoding.UTF_8)` ก่อนสร้าง query เพื่อหลีกเลี่ยงผลลัพธ์ที่อ่านไม่ออก

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### วิธีกรองข้อความพร้อมการสนับสนุน Paging?

Paging มีความสำคัญสำหรับกล่องเมลขนาดใหญ่ `ImapClient` มีเมธอดสำหรับดึงข้อความเป็นชุด, ตัวอย่างเช่น ดึง 500 ข้อความต่อครั้ง วิธีนี้ช่วยให้การใช้หน่วยความจำต่ำและเพิ่มอัตราการทำงานโดยรวม

ผสานการแบ่งหน้ากับ `ImapQueryBuilder` เพื่อดึงเฉพาะส่วนที่ต้องการในแต่ละหน้า

```java
ImapClient client = new ImapClient(host, port, username, password);
client.setSecurityOptions(SecurityOptions.Auto);

int itemsPerPage = 5;
String searchBody = "example body text";

ImapQueryBuilder iqb = new ImapQueryBuilder();
iqb.getBody().contains(searchBody);
MailQuery query = iqb.getQuery();

PageSettings pageSettings = new PageSettings();
pageSettings.setFolderName("Inbox");

List<ImapPageInfo> pages = new ArrayList<>();
ImapPageInfo pageInfo = client.listMessagesByPage(query, new PageInfo(itemsPerPage, 0), pageSettings);

pages.add(pageInfo);
while (!pageInfo.getLastPage()) {
    pageInfo = client.listMessagesByPage(query, pageInfo.getNextPage(), pageSettings);
    pages.add(pageInfo);
}

int retrievedItems = 0;
for (ImapPageInfo folderCol : pages) {
    retrievedItems += folderCol.getItems().size();
}
client.dispose();
```

### วิธีกรองข้อความตาม Flag ที่กำหนดเอง?

IMAP รองรับ flag ที่ผู้ใช้กำหนดเองเช่น `\Flagged` หรือแท็กแบบกำหนดเอง ด้วย `ImapQueryBuilder` คุณสามารถระบุ flag เหล่านี้เพื่อดึงข้อความที่ถูกทำเครื่องหมายเท่านั้น

ความสามารถนี้มีประโยชน์สำหรับเวิร์กโฟลว์ที่พึ่งพาการทำ flag ข้อความเพื่อการตรวจสอบหรือการจัดการพิเศษในภายหลัง

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## การประยุกต์ใช้งานจริง

- **การจัดการอีเมลองค์กร** – จัดเรียงเมลที่เข้ามาอัตโนมัติเข้าสู่โฟลเดอร์แผนกตามผู้ส่งหรือหัวเรื่อง.  
- **ระบบสนับสนุนลูกค้า** – ให้ความสำคัญกับตั๋วโดยกรองอีเมลที่มีคำว่า “Urgent” หรือมาจากลูกค้า VIP.  
- **เครื่องมือจัดการส่วนบุคคล** – สร้างยูทิลิตี้ Java ขนาดเล็กที่เก็บอีเมลข่าวสารของวันนี้และลบสแปมในหนึ่งรอบการทำงาน.

## พิจารณาด้านประสิทธิภาพ

- **Server‑Side Filtering** – ให้เซิร์ฟเวอร์ IMAP ทำงานหนัก; เพียงข้อความที่ตรงเงื่อนไขเท่านั้นจะเดินทางผ่านเครือข่าย.  
- **Paging** – ดึงผลลัพธ์เป็นชิ้นส่วน (เช่น หน้า 200 ข้อความ) เพื่อหลีกเลี่ยงการโหลดกล่องเมลทั้งหมดเข้าสู่ RAM.  
- **Connection Reuse** – รักษาอินสแตนซ์ `ImapClient` ตัวเดียวให้คงอยู่ตลอดงานแบตช์เพื่อ ลด overhead ของการจับมือ.  
- **Monitoring** – บันทึกจำนวนข้อความที่ประมวลผลและเวลาที่ใช้; ปรับขนาดหน้า หากพบการเพิ่มขึ้นของหน่วยความจำ.

## สรุป

คุณมีเครื่องมือครบชุดสำหรับ **วิธีกรองอีเมล** ด้วย Aspose.Email for Java ตั้งแต่การค้นหาตามวันที่ง่าย ๆ ไปจนถึงฟิลเตอร์หลายเกณฑ์ที่ซับซ้อนพร้อม flag ที่กำหนดเอง ไลบรารีให้การควบคุมระดับละเอียดพร้อมประสิทธิภาพที่เหมาะสม

### ขั้นตอนต่อไป

- รวมฟิลเตอร์เหล่านี้เป็นเมธอดที่ใช้ซ้ำได้ในแอปพลิเคชันของคุณ.  
- สำรวจ API ของ **Aspose.Email** สำหรับการส่ง, ส่งต่อ, และตอบกลับข้อความ.  
- ผสานกับฐานข้อมูลเพื่อเก็บเมตาดาต้าของข้อความที่กรองไว้สำหรับการวิเคราะห์.

---

## คำถามที่พบบ่อย

**ถาม: ฉันจะเชื่อมต่อกับเซิร์ฟเวอร์ IMAP ด้วย Aspose.Email อย่างไร?**  
ตอบ: สร้างอินสแตนซ์ `ImapClient` ด้วย host, port, username, และ password, จากนั้นเรียก `client.selectFolder("Inbox")`.

**ถาม: ฉันสามารถกรองอีเมลตามวันที่และผู้ส่งในคำขอเดียวได้หรือไม่?**  
ตอบ: ได้ – ใช้ `ImapQueryBuilder` เพื่อรวมเกณฑ์ `date` และ `fromAddress`; ไลบรารีจะส่งคำสั่ง SEARCH เพียงครั้งเดียว.

**ถาม: Aspose.Email รองรับ SSL/TLS สำหรับการเชื่อมต่อที่ปลอดภัยหรือไม่?**  
ตอบ: แน่นอน – ตั้งค่า `client.setSecurityOptions(SecurityOptions.SSL_TLS)` ก่อนเชื่อมต่อ.

**ถาม: ขนาดกล่องเมลสูงสุดที่ Aspose.Email สามารถจัดการได้คือเท่าไหร่?**  
ตอบ: ไลบรารีสามารถประมวลผลกล่องเมลที่มี **มากกว่า 100,000 ข้อความ** หากใช้ paging; การใช้หน่วยความจำคงที่ต่ำกว่า 50 MB.

**ถาม: จำเป็นต้องใช้ไลเซนส์สำหรับการสร้างเวอร์ชันพัฒนาไหม?**  
ตอบ: ไลเซนส์ชั่วคราวจะลบลายน้ำและข้อจำกัดการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานในผลิตภัณฑ์.

---

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Email for Java 24.9  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Fetch Emails from IMAP Server Using Aspose.Email for Java: A Step-by-Step Guide](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [Master IMAP Client Initialization in Java with Aspose.Email: A Comprehensive Guide](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [How to Backup IMAP Emails with Aspose.Email for Java: A Step-by-Step Guide](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}