---
date: '2026-09-17'
description: วิธีสร้างคำเชิญปฏิทินด้วย Aspose.Email for Java ช่วยให้คุณแชร์ปฏิทิน
  ตั้งค่าการมอบอำนาจ (delegate permissions) และส่งอีเมลแชร์แบบอัตโนมัติ
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: วิธีสร้างคำเชิญปฏิทินด้วย Aspose.Email for Java ช่วยให้คุณแชร์ปฏิทินแบบอัตโนมัติ
  ตั้งค่าการมอบอำนาจ (delegate permissions) และส่งอีเมลแชร์ผ่าน Exchange Web Services
  เพื่อปรับปรุงการทำงานร่วมกันของทีม
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: วิธีสร้างคำเชิญปฏิทินด้วย Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: วิธีสร้างคำเชิญปฏิทินด้วย Aspose.Email for Java
url: /th/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการการแชร์ปฏิทิน: คู่มือ Aspose.Email สำหรับ Java

## บทนำสู่การจัดการการแชร์ปฏิทิน
การจัดการคำเชิญแชร์ปฏิทินอาจเป็นงานที่ซับซ้อน โดยเฉพาะเมื่อต้องทำงานกับผู้ใช้หลายคนบนแพลตฟอร์มต่าง ๆ ในบทแนะนำนี้คุณจะ **สร้างคำเชิญแชร์ปฏิทิน** ด้วย Aspose.Email สำหรับ Java ครอบคลุมตั้งแต่การสร้างการเข้าถึงของผู้แทนจนถึงการส่งอีเมลแชร์ปฏิทิน เมื่อเสร็จสิ้นคุณจะสามารถตั้งค่าสิทธิ์ของผู้แทน, **กำหนดสิทธิ์ปฏิทิน**, และทำให้การทำงานร่วมกันในองค์กรของคุณเป็นเรื่องง่ายขึ้น

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีการเริ่มต้น client EWS ด้วย Aspose.Email สำหรับ Java  
- การสร้างผู้ใช้ผู้แทนและ **ตั้งค่าสิทธิ์ผู้แทน**  
- **สร้างการเข้าถึงผู้แทน** และกำหนดสิทธิ์ปฏิทิน  
- ส่ง **อีเมลแชร์ปฏิทิน** (คำเชิญ) อย่างอัตโนมัติ  
- สถานการณ์จริงที่คุณลักษณะเหล่านี้เพิ่มคุณค่า  

ก่อนที่เราจะลงลึก ให้แน่ใจว่าคุณมีทุกอย่างที่ต้องการแล้ว

## คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักของคู่มือนี้คืออะไร?** เพื่อแสดงวิธี **สร้างคำเชิญแชร์ปฏิทิน** ด้วย Aspose.Email สำหรับ Java  
- **ต้องใช้เวอร์ชันของไลบรารีใด?** Aspose.Email สำหรับ Java 25.4 (classifier JDK 16)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ใช่ – ต้องมีลิขสิทธิ์ทดลองหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์  
- **ต้องการสภาพแวดล้อมอะไร?** JDK 16+, Maven, และบัญชี Exchange Online  
- **สามารถใช้กับเซิร์ฟเวอร์ Exchange อื่นได้หรือไม่?** ใช่ แต่คุณอาจต้องปรับ URL ของบริการและระดับสิทธิ์

## คำเชิญแชร์ปฏิทินคืออะไร?
คำเชิญแชร์ปฏิทินคือข้อความอีเมลที่ให้ผู้ใช้คนอื่นเข้าถึงเพื่อดู (หรือแก้ไข) ปฏิทินของคุณโดยไม่ต้องให้สิทธิ์เต็มของกล่องจดหมาย ช่วยให้สมาชิกทีมเห็นกำหนดการของคุณ, เสนอการประชุม, หรือจัดการเหตุการณ์ต่าง ๆ ในขณะที่กล่องจดหมายของคุณยังคงปลอดภัย

## ทำไมต้องกำหนดสิทธิ์ปฏิทิน?
การกำหนดสิทธิ์ปฏิทินทำให้คุณควบคุมได้ว่าผู้แทนทำอะไรได้บ้าง—อ่านเหตุการณ์เท่านั้น, เสนอเหตุการณ์ใหม่, หรือแก้ไขรายการที่มีอยู่ การตั้งค่าสิทธิ์ที่เหมาะสมช่วยปกป้องข้อมูลที่สำคัญพร้อมกับส่งเสริมการทำงานร่วมกัน ตัวอย่างเช่น การให้สิทธิ์อ่าน‑อย่างเดียวจะป้องกันการเปลี่ยนแปลงโดยบังเอิญ ในขณะที่สิทธิ์แก้ไขจะให้ผู้แทนกำหนดหรือปรับเปลี่ยนการประชุมในนามของคุณ

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** เวอร์ชัน 16 หรือใหม่กว่า  
- **Maven:** สำหรับการจัดการ dependencies และการสร้างโปรเจกต์  
- **Aspose.Email สำหรับ Java Library:** เวอร์ชัน 25.4 รองรับ JDK 16  

### ความต้องการการตั้งค่าสภาพแวดล้อม
1. ติดตั้ง JDK หากยังไม่ได้ทำ คุณสามารถดาวน์โหลดได้จาก [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html)  
2. ตรวจสอบให้แน่ใจว่า Maven ถูกติดตั้งและกำหนดค่าในเครื่องของคุณแล้ว  
3. เลือก IDE เช่น IntelliJ IDEA หรือ Eclipse เพื่อความสะดวกในการพัฒนา  

### ความรู้พื้นฐานที่จำเป็น
- ทักษะการเขียนโปรแกรม Java ขั้นพื้นฐาน  
- ความคุ้นเคยกับ dependencies ของ Maven  
- ตัวเลือก: ประสบการณ์กับ Exchange Web Services (EWS)

## การตั้งค่า Aspose.Email สำหรับ Java
### การกำหนดค่า Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การรับลิขสิทธิ์
Aspose.Email สำหรับ Java ต้องการลิขสิทธิ์เพื่อใช้งานเต็มรูปแบบ คุณสามารถ:
- **ทดลองใช้ฟรี:** ดาวน์โหลดจาก [Aspose's release page](https://releases.aspose.com/email/java/)  
- **ลิขสิทธิ์ชั่วคราว:** ขอคีย์ชั่วคราวบนเว็บไซต์ของ Aspose  
- **ซื้อ:** รับลิขสิทธิ์ถาวรสำหรับการใช้งานในผลิตภัณฑ์

### การเริ่มต้นและตั้งค่าเบื้องต้น
เมื่อ Maven ดึง dependency แล้ว ให้เริ่มต้น client EWS:

`ExchangeService` เป็นคลาสหลักที่ใช้สื่อสารกับ Exchange Web Services  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## วิธีสร้างคำเชิญแชร์ปฏิทิน
เพื่อสร้างคำเชิญแชร์ปฏิทิน คุณต้องเชื่อมต่อกับ Exchange ด้วย client `ExchangeService` ก่อน, จากนั้นกำหนดผู้แทนพร้อมระดับสิทธิ์ที่ต้องการ, และสุดท้ายสร้าง `MailMessage` ที่รวมคำขอแชร์ ขั้นตอนต่อไปนี้แสดงกระบวนการใน Java

ด้านล่างนี้เราจะครอบคลุมสองคุณลักษณะหลัก: การสร้างและส่งคำเชิญแชร์ปฏิทิน, และ **ตั้งค่าสิทธิ์ผู้แทน** สำหรับการเข้าถึงปฏิทิน

### คุณลักษณะ 1: สร้างและส่งคำเชิญแชร์ปฏิทิน
#### ภาพรวม
คุณลักษณะนี้จะพาคุณผ่านการเริ่มต้น client, **สร้างการเข้าถึงผู้แทน**, และการส่งอีเมลคำเชิญ

#### การดำเนินการแบบขั้นตอน
##### 1️⃣ เริ่มต้น client EWS
`ExchangeService` แสดงการเชื่อมต่อกับเซิร์ฟเวอร์ Exchange และใช้สำหรับส่งและรับข้อความ  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
การเชื่อมต่อนี้ทำให้แอป Java ของคุณเชื่อมกับ Exchange Online

##### 2️⃣ สร้างผู้ใช้ผู้แทน
`DelegateUser` กำหนดที่อยู่อีเมลของผู้แทนและระดับสิทธิ์ที่จะมอบให้  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
ที่นี่เราจะ **สร้างการเข้าถึงผู้แทน** และกำหนดระดับ `Reviewer` ซึ่งทำให้ผู้แทนสามารถดูรายการปฏิทินได้

##### 3️⃣ ส่งคำเชิญแชร์ปฏิทิน
`MailMessage` สร้างอีเมลที่บรรจุคำเชิญแชร์ปฏิทิน  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
โค้ดนี้สร้าง **อีเมลแชร์ปฏิทิน** (คำเชิญ) และส่งผ่าน client EWS

### คุณลักษณะ 2: สิทธิ์การเข้าถึงปฏิทินของผู้แทน
#### ภาพรวม
ส่วนนี้แสดงวิธี **กำหนดสิทธิ์ปฏิทิน** และทำให้ผู้แทนมีสิทธิ์ที่เหมาะสม

#### ขั้นตอนการดำเนินการ
##### 1️⃣ เริ่มต้น client EWS (ใช้ซ้ำ)
`ExchangeService` สามารถใช้ซ้ำสำหรับหลายการดำเนินการหลังจากกำหนดค่าแล้ว  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ สร้างและตั้งค่าสิทธิ์ผู้แทน
`ExchangeDelegateFolderPermissionLevel` ระบุระดับการเข้าถึงที่ผู้แทนสามารถมีต่อโฟลเดอร์ปฏิทิน  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
ส่วนนี้ **ตั้งค่าสิทธิ์ผู้แทน** เพื่อให้ผู้ใช้สามารถดูรายการปฏิทินได้โดยไม่ต้องมีสิทธิ์เต็มของกล่องจดหมาย

## วิธีกำหนดสิทธิ์ปฏิทินสำหรับผู้แทน
เมื่อผู้แทนต้องการสิทธิ์มากกว่าการอ่าน‑อย่างเดียว คุณสามารถปรับ `ExchangeDelegateFolderPermissionLevel` เพื่อมอบสิทธิ์แก้ไข, ผู้เขียน, หรือเจ้าของ เลือกระดับที่ต่ำที่สุดที่ตอบสนองความต้องการทางธุรกิจเพื่อรักษาความปลอดภัยพร้อมให้ฟังก์ชันที่จำเป็น ตัวอย่างเช่น ระดับ Editor อนุญาตให้ผู้แทนสร้าง, แก้ไข, และลบเหตุการณ์ ส่วนระดับ Reviewer ให้เพียงการดูเท่านั้น

- `Reviewer` – สิทธิ์อ่าน‑อย่างเดียว  
- `Editor` – สิทธิ์อ่าน/เขียน  
- `Author` – สร้างและอ่าน, แต่ไม่สามารถลบได้  
- `Owner` – ควบคุมเต็มรูปแบบ รวมถึงการเปลี่ยนแปลงสิทธิ์  

**เคล็ดลับ:** ใช้ระดับสิทธิ์ที่น้อยที่สุดที่ตอบสนองความต้องการเพื่อรักษาความปลอดภัยของข้อมูลปฏิทินของคุณ

## การประยุกต์ใช้งานจริง
สถานการณ์จริงที่ **จัดการการแชร์ปฏิทิน** มีประโยชน์:
1. **การประชุมองค์กร** – ให้สมาชิกทีมดูกำหนดการประชุมโดยไม่ต้องให้สิทธิ์เต็มของกล่องจดหมาย  
2. **การจัดการโครงการ** – หัวหน้าโครงการสามารถตรวจสอบไทม์ไลน์ได้ในขณะที่นักพัฒนายังคงควบคุมปฏิทินของตนเอง  
3. **การวางแผนกิจกรรม** – ผู้ขายได้รับ **อีเมลแชร์ปฏิทิน** เพื่อประสานงานโลจิสติกส์โดยไม่เปิดเผยรายละเอียดภายใน

## พิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** ทำลายวัตถุ `MailMessage` ขนาดใหญ่โดยเร็วในแอปที่มีปริมาณสูง  
- **การจัดการข้อยกเว้น:** ห่อการเรียกเครือข่ายด้วย try‑catch เพื่อจัดการข้อขัดข้องของการเชื่อมต่ออย่างราบรื่น  
- **การอัปเดตไลบรารี:** Aspose.Email สำหรับ Java รองรับโปรโตคอลกว่า 50 รายการและสามารถประมวลผลปฏิทินที่มีรายการถึง 10,000 รายการโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ดังนั้นควรอัปเดตไลบรารีเพื่อรับประโยชน์จากการปรับปรุงประสิทธิภาพและการแก้บั๊ก

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|-------|-------------------|----------|
| ไม่ได้รับคำเชิญ | ตัวกรองสแปมหรือที่อยู่อีเมลไม่ถูกต้อง | ตรวจสอบที่อยู่อีเมลผู้รับและเพิ่มโดเมนผู้ส่งในรายการผู้ส่งที่ปลอดภัย |
| สิทธิ์ไม่ถูกนำไปใช้ | ใช้ `ExchangeDelegateFolderPermissionLevel` ผิด | ตรวจสอบระดับสิทธิ์ตรงกับการเข้าถึงที่ต้องการ |
| เกิดข้อยกเว้นที่ `createCalendarSharingInvitationMessage` | ไม่มีลิขสิทธิ์หรือไลบรารีล้าสมัย | ตรวจสอบว่ามีลิขสิทธิ์ที่ถูกต้องและใช้เวอร์ชันล่าสุดของ Aspose.Email |

## คำถามที่พบบ่อย
**ถาม:** Aspose.Email สำหรับ Java ใช้ทำอะไร?  
**ตอบ:** เป็นไลบรารีครบวงจรสำหรับจัดการอีเมล, ปฏิทิน, และรายชื่อผู้ติดต่อในแอป Java รองรับ Outlook, Exchange, และโปรโตคอลอื่น ๆ  

**ถาม:** ฉันต้องตั้งค่าสภาพแวดล้อมอย่างไรเพื่อใช้ Aspose.Email?  
**ตอบ:** ติดตั้ง JDK 16+, Maven, เพิ่ม dependency Aspose.Email ใน `pom.xml`, และรับลิขสิทธิ์ (ทดลองหรือเต็ม)  

**ถาม:** สามารถใช้โค้ดนี้กับเวอร์ชันอื่นของ Exchange Online ได้หรือไม่?  
**ตอบ:** ใช่ แต่ควรตรวจสอบให้ URL ของบริการและระดับสิทธิ์สอดคล้องกับการกำหนดค่าของเซิร์ฟเวอร์ของคุณ  

**ถาม:** ควรทำอย่างไรหากคำเชิญแชร์ปฏิทินส่งไม่สำเร็จ?  
**ตอบ:** ตรวจสอบการเชื่อมต่อเครือข่าย, ข้อมูลประจำตัว, และให้แน่ใจว่าผู้ใช้ผู้แทนมีสิทธิ์ที่ถูกต้อง ตรวจสอบรายละเอียดข้อยกเว้นเพื่อหาสาเหตุ  

**ถาม:** สามารถเพิ่มสิทธิ์เพิ่มเติมเช่นการแก้ไขหรือการเข้าถึงเต็มได้หรือไม่?  
**ตอบ:** แน่นอน – แทนที่ `ExchangeDelegateFolderPermissionLevel.Reviewer` ด้วย `Editor`, `Author`, หรือ `Owner` ตามความต้องการ

## สรุป
คุณมีโซลูชันครบวงจรสำหรับ **สร้างคำเชิญแชร์ปฏิทิน** ด้วย Aspose.Email สำหรับ Java ตั้งแต่การเริ่มต้น client EWS, **สร้างการเข้าถึงผู้แทน**, **ตั้งค่าสิทธิ์ผู้แทน**, และการส่ง **อีเมลแชร์ปฏิทิน** คุณสามารถอัตโนมัติการทำงานร่วมกันทั่วทั้งองค์กรได้

**ขั้นตอนต่อไป**
- ทดลองใช้ระดับสิทธิ์อื่น ๆ (Editor, Owner)  
- ผสานตรรกะนี้เข้ากับระบบการจัดตารางหรือ HR ที่มีอยู่  
- สำรวจคุณลักษณะเพิ่มเติมของ Aspose.Email เช่น งานซ้ำหรือคำขอประชุม

---

**อัปเดตล่าสุด:** 2026-09-17  
**ทดสอบด้วย:** Aspose.Email สำหรับ Java 25.4 (classifier JDK 16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java Filter Exchange Appointments By Date](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Create Exchange Calendar Java with Aspose.Email – A Complete Guide](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}