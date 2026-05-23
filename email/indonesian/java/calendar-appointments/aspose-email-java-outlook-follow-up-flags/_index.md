---
date: '2026-02-22'
description: Pelajari cara mengatur bendera tindak lanjut Outlook di Outlook menggunakan
  Aspose.Email untuk Java, termasuk mengatur, membaca, dan menghapus bendera untuk
  penerima.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Cara Mengatur Bendera Tindak Lanjut Outlook menggunakan Aspose.Email untuk
  Java
url: /id/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menetapkan Outlook Follow Up Flag menggunakan Aspose.Email untuk Java

## Introduction
Jika Anda pernah kesulitan melacak email penting, Anda pasti tahu betapa berharga **outlook follow up flag** di Outlook. Dalam panduan ini kami akan menunjukkan **cara menetapkan outlook follow up flag** secara programatis dengan Aspose.Email untuk Java, serta cara **menetapkan outlook follow up flag untuk penerima**, dan cara **menghapus outlook follow up flag** ketika tugas selesai. Pada akhir panduan, Anda akan dapat mengotomatisasi pelacakan tugas, pengingat, dan jejak audit langsung dari kode Java Anda.

**Apa yang akan Anda pelajari**
- Membuat dan menerapkan bendera tindak lanjut pada pesan Outlook.  
- Menetapkan bendera tindak lanjut untuk penerima tertentu.  
- Menandai bendera sebagai selesai dan kemudian menghapusnya.  
- Membaca opsi bendera untuk pelaporan atau kepatuhan.  

Mari siapkan lingkungan sebelum menyelam ke kode.

## Quick Answers
- **Apa arti “how to set follow‑up”?** Menambahkan bendera dengan tanggal mulai, pengingat, dan tanggal jatuh tempo pada item Outlook.  
- **Perpustakaan apa yang diperlukan?** Aspose.Email untuk Java (v25.4 atau lebih baru).  
- **Apakah saya memerlukan lisensi?** Ya, lisensi percobaan atau lisensi berbayar diperlukan untuk fungsi penuh.  
- **Bisakah saya menetapkan bendera hanya untuk penerima?** Tentu – gunakan `FollowUpManager.setFlagForRecipients`.  
- **Apakah memungkinkan menghapus bendera nanti?** Ya, panggil `FollowUpManager.clearFlag`.

## What is an Outlook Follow Up Flag?
Outlook follow up flag adalah penanda tugas bawaan yang dapat melampirkan tanggal mulai, pengingat, dan tanggal jatuh tempo pada item email apa pun. Ini mengubah email biasa menjadi item tindakan yang dilacak, membantu Anda dan tim tetap di atas pekerjaan yang menunggu.

## Why Use Aspose.Email for Java?
Aspose.Email menyediakan API murni‑Java yang berfungsi tanpa Outlook terpasang, memungkinkan Anda memanipulasi file .msg, menetapkan bendera, dan mengelola tugas di platform apa pun—sempurna untuk **automate outlook tasks**, layanan backend, atau integrasi dengan alat manajemen proyek.

## Prerequisites
- **Aspose.Email untuk Java** versi 25.4 atau lebih baru (juga dikenal sebagai **aspose email java**).  
- **JDK 16+** terpasang.  
- IDE yang kompatibel dengan Maven (IntelliJ IDEA, Eclipse, dll.).  
- Pengetahuan dasar Java dan pemahaman tentang konsep email.

## Setting Up Aspose.Email for Java
### Maven Configuration
Tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email memerlukan lisensi untuk penggunaan produksi:

- **Free trial** – evaluasi 30 hari.  
- **Temporary license** – pengujian lanjutan.  
- **Full license** – langganan permanen.

Inisialisasi lisensi sebelum operasi email apa pun:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Pertama kami membuat `MailMessage`, mengatur pengirim/penerima, lalu mengonversinya menjadi `MapiMessage` untuk manipulasi bendera.*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Di sini kami menetapkan tanggal mulai, pengingat (**outlook flag reminder**), dan tanggal jatuh tempo menggunakan kelas `Calendar`.*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Objek `FollowUpOptions` menyimpan semua detail bendera, yang kami terapkan dengan `FollowUpManager.setOptions`.*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Pesan disimpan sebagai file `.msg` dengan bendera terlampir.*

## How to Set Flag for Recipients (Feature 2)
### Overview
Kadang‑kadang Anda memerlukan bendera yang muncul **hanya untuk penerima**. Contoh ini menandai pesan sebagai draft terlebih dahulu, lalu menambahkan bendera.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Menandai pesan sebagai belum terkirim memastikan Outlook memperlakukannya sebagai draft.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Bendera kini terlihat hanya oleh penerima – skenario klasik **flag for recipients**.*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status bendera berubah menjadi “Completed” dan file yang diperbarui disimpan.*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Pesan disimpan tanpa bendera tindak lanjut apa pun.*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Objek `options` kini berisi tanggal mulai, jatuh tempo, dan pengingat, serta subjek bendera – berguna ketika Anda perlu **read flag options** untuk pelaporan.*

## Practical Applications
- **Task‑Management Integration:** Sinkronkan email yang diberi bendera dengan Jira, Trello, atau Azure Boards.  
- **Automated Reminders:** Hasilkan email pengingat harian untuk tindak lanjut yang tertunda.  
- **Compliance Audits:** Ekspor data bendera untuk pelaporan regulasi.

## Performance Considerations
- **Date Calculations:** Hitung tanggal sekali per batch, bukan di dalam loop.  
- **Resource Management:** Tutup semua stream atau handle file setelah menyimpan pesan.  
- **Memory Usage:** Proses mailbox besar dalam potongan untuk menghindari tekanan heap.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: It’s a pure‑Java API that lets you create, read, and manipulate email files (MSG, EML, etc.) without needing Outlook installed.

**Q: How do I obtain a free trial license?**  
A: Visit the [Aspose website](https://releases.aspose.com/email/java/) to download a 30‑day trial.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook supports only one flag per message, but you can store additional task data in custom MAPI properties.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Confirm the `outputDir` path is valid and that the application has permission to write to that location.

**Q: How can I remove flags from many messages at once?**  
A: Loop through your message collection and call `FollowUpManager.clearFlag` on each `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}