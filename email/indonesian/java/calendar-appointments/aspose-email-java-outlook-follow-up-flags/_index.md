---
date: '2026-07-27'
description: Pelajari cara mengatur outlook flag java menggunakan Aspose.Email for
  Java, mencakup pembuatan flag, flag penerima, penyelesaian, penghapusan, dan opsi
  membaca.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Set outlook flag java dengan Aspose.Email for Java. Panduan ini menunjukkan
  cara membuat, membaca, menyelesaikan, dan menghapus Outlook follow‑up flags secara
  efisien.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Set Outlook Flag Java – Panduan Pemrograman Aspose.Email Lengkap
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Set Outlook Flag Java – Panduan Pemrograman Aspose.Email Lengkap
url: /id/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Atur Bendera Outlook Java menggunakan Aspose.Email untuk Java

## Pendahuluan
Jika Anda perlu **mengatur bendera outlook java** secara programatis, Anda berada di tempat yang tepat. Bendera tindak‑lanjut Outlook mengubah email biasa menjadi tugas yang dilacak, dan Aspose.Email untuk Java memungkinkan Anda mengelola bendera tersebut tanpa harus menginstal Outlook. Dalam tutorial ini kami akan membahas cara membuat, membaca, menyelesaikan, dan akhirnya menghapus bendera, serta cara menerapkan bendera untuk penerima tertentu. Pada akhir tutorial Anda akan memiliki potongan kode Java yang dapat digunakan kembali untuk mengotomatisasi pelacakan tugas langsung dari layanan backend Anda.

## Jawaban Cepat
- **Apa arti “set outlook flag java”?** Menambahkan bendera dengan tanggal mulai, pengingat, dan tanggal jatuh tempo ke item Outlook melalui kode Java.  
- **Perpustakaan apa yang diperlukan?** Aspose.Email untuk Java (v25.4 atau lebih baru).  
- **Apakah saya memerlukan lisensi?** Ya – versi percobaan dapat digunakan untuk evaluasi, tetapi lisensi berbayar diperlukan untuk produksi.  
- **Bisakah saya mengatur bendera hanya untuk penerima?** Tentu – gunakan `FollowUpManager.setFlagForRecipients`.  
- **Apakah bendera dapat dihapus nanti?** Ya – panggil `FollowUpManager.clearFlag`.

## Apa itu Bendera Tindak Lanjut Outlook?
Bendera tindak‑lanjut Outlook adalah penanda tugas bawaan yang dapat melampirkan tanggal mulai, pengingat, dan tanggal jatuh tempo ke item email apa pun. Ini mengubah email menjadi item tindakan yang dilacak, membantu Anda dan tim tetap mengawasi pekerjaan yang tertunda.

## Mengapa Menggunakan Aspose.Email untuk Java?
Aspose.Email untuk Java mendukung **lebih dari 70 format email** (termasuk MSG, EML, MHTML, dan TNEF) dan dapat memproses **lebih dari 100.000 pesan per menit** pada server 8‑core tipikal, semuanya tanpa memerlukan Outlook di mesin host. Ini menjadikannya ideal untuk otomatisasi backend, pelaporan kepatuhan, dan integrasi dengan alat manajemen proyek.

## Prasyarat
- **Aspose.Email untuk Java** versi 25.4 atau lebih baru.  
- **JDK 16+** terinstal.  
- IDE yang kompatibel dengan Maven (IntelliJ IDEA, Eclipse, dll.).  
- Pengetahuan dasar Java dan pemahaman tentang konsep email.

## Menyiapkan Aspose.Email untuk Java
### Konfigurasi Maven
Tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Perolehan Lisensi
Aspose.Email memerlukan lisensi untuk penggunaan produksi:

- **Percobaan gratis** – evaluasi 30 hari.  
- **Lisensi sementara** – pengujian lanjutan.  
- **Lisensi penuh** – langganan permanen.

Inisialisasi lisensi sebelum melakukan operasi email apa pun:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Atur Bendera Outlook Java (Fitur 1)
### Jawaban langsung
Muat sebuah `MailMessage`, konversi ke `MapiMessage`, konfigurasikan `FollowUpOptions`, dan panggil `FollowUpManager.setOptions`. Urutan ini membuat item Outlook yang ber‑bendera lengkap dalam beberapa baris kode Java.

### Langkah 1: Buat dan Inisialisasi Pesan
`MailMessage` adalah kelas tingkat tinggi Aspose.Email yang mewakili email. Setelah Anda membangun pesan, konversi ke `MapiMessage` untuk manipulasi bendera.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Kami pertama membangun sebuah `MailMessage`, mengatur pengirim/penerima, lalu mengkonversinya ke `MapiMessage` untuk manipulasi bendera.*

### Langkah 2: Tentukan Tanggal Tindak Lanjut (Pengingat Bendera Outlook)
`FollowUpOptions` menyimpan tanggal mulai, pengingat, dan jatuh tempo. Gunakan `Calendar` Java untuk mengatur timestamp yang tepat.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Di sini kami mengatur tanggal mulai, pengingat (**pengingat bendera outlook**), dan tanggal jatuh tempo menggunakan kelas `Calendar`.*

### Langkah 3: Terapkan Opsi Tindak Lanjut
Metode `FollowUpManager.setOptions` menempelkan bendera pada `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Objek `FollowUpOptions` berisi semua detail bendera, yang kami terapkan dengan `FollowUpManager.setOptions`.*

### Langkah 4: Simpan Pesan
Simpan pesan yang ber‑bendera sebagai file `.msg` agar Outlook dapat menampilkan bendera tersebut.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Pesan disimpan sebagai file `.msg` dengan bendera terlampir.*

## Cara Mengatur Bendera untuk Penerima (Fitur 2)?
Gunakan `FollowUpManager.setFlagForRecipients` setelah menandai pesan sebagai draf. Metode ini menambahkan bendera tindak‑lanjut hanya pada salinan penerima, meninggalkan tampilan pengirim tidak berubah. Hal ini memerlukan pengaturan `MessageFlags.MSGFLAG_UNSENT` sebelum menerapkan bendera. Anda juga dapat menyesuaikan tanggal mulai, pengingat, dan jatuh tempo menggunakan objek `FollowUpOptions` sebelum memanggil metode tersebut.

### Jawaban langsung
Tandai pesan sebagai draf menggunakan `MessageFlags.MSGFLAG_UNSENT`, lalu panggil `FollowUpManager.setFlagForRecipients`. Outlook akan menampilkan bendera hanya kepada penerima, bukan kepada pengirim.

### Ikhtisar
Kadang‑kadang Anda memerlukan bendera yang muncul **hanya untuk penerima**. Contoh ini menandai pesan sebagai draf terlebih dahulu, kemudian menambahkan bendera.

#### Langkah 1: Tandai sebagai Draf
`MessageFlags` adalah enumerasi MAPI yang mengontrol status pesan. Menetapkan `MSGFLAG_UNSENT` memberi tahu Outlook bahwa item tersebut adalah draf.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Menandai pesan sebagai tidak terkirim memastikan Outlook memperlakukannya sebagai draf.*

#### Langkah 2: Atur Bendera Penerima
`FollowUpManager.setFlagForRecipients` menempelkan bendera secara eksklusif pada salinan penerima.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Bendera kini hanya terlihat oleh penerima – skenario klasik **bendera untuk penerima**.*

## Cara Menandai Bendera Tindak Lanjut Outlook sebagai Selesai (Fitur 3)?
Muat file .msg ke dalam `MapiMessage`, lalu panggil `FollowUpManager.completeFlag`. Ini memperbarui status bendera menjadi Completed dan menambahkan tanda centang di Outlook. Setelah selesai, simpan pesan untuk mempertahankan perubahan. Anda juga dapat mengatur waktu penyelesaian dengan menyesuaikan properti `FlagCompleteTime` bila diperlukan untuk keperluan audit.

### Jawaban langsung
Muat file `.msg` yang ada ke dalam `MapiMessage`, panggil `FollowUpManager.completeFlag`, dan simpan file. Status bendera berubah menjadi “Completed” dan muncul dengan tanda centang di Outlook.

### Langkah 1: Muat Pesan
`MapiMessage` dapat membaca file `.msg` yang disimpan, memberi Anda akses penuh ke properti MAPI-nya.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Langkah 2: Tandai sebagai Selesai dan Simpan
`FollowUpManager.completeFlag` memperbarui status bendera, setelah itu Anda menyimpan perubahan.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status bendera berubah menjadi “Completed” dan file yang diperbarui disimpan.*

## Cara Menghapus Bendera Tindak Lanjut Outlook (Fitur 4)?
Buka file .msg dengan `MapiMessage`, panggil `FollowUpManager.clearFlag`, lalu simpan pesan. Ini menghapus semua properti MAPI terkait bendera, sehingga Outlook tidak lagi menampilkan indikator tindak‑lanjut apa pun. Gunakan ini ketika tugas dibatalkan atau tidak lagi relevan. Pastikan juga menghapus properti pengingat khusus agar tidak ada notifikasi tersisa.

### Jawaban langsung
Buka file `.msg` dengan `MapiMessage`, panggil `FollowUpManager.clearFlag`, dan simpan file. Pesan tidak lagi menampilkan indikator tindak‑lanjut di Outlook.

### Langkah 1: Muat dan Hapus Bendera
`FollowUpManager.clearFlag` menghapus semua properti terkait bendera dari pesan.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Pesan disimpan tanpa bendera tindak‑lanjut apa pun.*

## Cara Membaca Opsi Bendera (Fitur 5)?
Panggil `FollowUpManager.getOptions` pada `MapiMessage` yang telah dimuat untuk memperoleh objek `FollowUpOptions`. Objek ini menyediakan tanggal mulai, jatuh tempo, pengingat, serta subjek bendera, memungkinkan Anda menampilkan atau mencatat detail bendera. Ini berguna untuk pelaporan dan audit kepatuhan.

### Jawaban langsung
Gunakan `FollowUpManager.getOptions` pada `MapiMessage` yang dimuat untuk mengambil objek `FollowUpOptions` yang berisi tanggal mulai, jatuh tempo, pengingat, dan subjek bendera. Ini berguna untuk pelaporan atau audit kepatuhan.

### Langkah 1: Ambil Opsi
Objek `options` yang dikembalikan memberi Anda visibilitas penuh ke konfigurasi bendera.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Objek `options` kini berisi tanggal mulai, jatuh tempo, dan pengingat, serta subjek bendera – berguna ketika Anda perlu **membaca opsi bendera** untuk pelaporan.*

## Aplikasi Praktis
- **Integrasi Manajemen Tugas:** Sinkronkan email ber‑bendera dengan Jira, Trello, atau Azure Boards.  
- **Pengingat Otomatis:** Hasilkan email pengingat harian untuk tindak‑lanjut yang belum selesai.  
- **Audit Kepatuhan:** Ekspor data bendera untuk pelaporan regulasi, memanfaatkan kemampuan membaca opsi bendera secara programatis.

## Pertimbangan Kinerja
- **Perhitungan Tanggal:** Hitung tanggal satu kali per batch, bukan di dalam loop.  
- **Manajemen Sumber Daya:** Tutup semua stream atau handle file setelah menyimpan pesan.  
- **Penggunaan Memori:** Proses kotak surat besar dalam potongan untuk menghindari tekanan pada heap; Aspose.Email dapat menangani kotak surat ratusan halaman tanpa memuat seluruh file ke memori.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Bendera tidak muncul di Outlook | Pesan disimpan tanpa `MessageFlags` yang tepat | Pastikan `setMessageFlags` diatur ke `MSGFLAG_UNSENT` sebelum menerapkan bendera untuk penerima. |
| Penyimpanan menghasilkan `AccessDeniedException` | Path file tidak benar atau izin menulis tidak ada | Verifikasi direktori output ada dan aplikasi memiliki hak menulis. |
| Tanggal meleset satu hari | Perbedaan zona waktu | Gunakan `TimeZone.getTimeZone("GMT")` atau zona lokal Anda secara konsisten. |

## Pertanyaan yang Sering Diajukan
**T: Apa itu Aspose.Email untuk Java?**  
J: Ini adalah API murni‑Java yang memungkinkan Anda membuat, membaca, dan memanipulasi file email (MSG, EML, dll.) tanpa perlu menginstal Outlook.

**T: Bagaimana cara mendapatkan lisensi percobaan gratis?**  
J: Kunjungi [situs Aspose](https://releases.aspose.com/email/java/) untuk mengunduh percobaan 30 hari.

**T: Bisakah saya mengatur beberapa bendera tindak lanjut pada satu pesan?**  
J: Outlook hanya mendukung satu bendera per pesan, tetapi Anda dapat menyimpan data tugas tambahan dalam properti MAPI khusus.

**T: Pesan saya tidak tersimpan setelah mengatur bendera. Apa yang harus saya periksa?**  
J: Pastikan path `outputDir` valid dan aplikasi memiliki izin menulis ke lokasi tersebut.

**T: Bagaimana cara menghapus bendera dari banyak pesan sekaligus?**  
J: Loop melalui koleksi pesan Anda dan panggil `FollowUpManager.clearFlag` pada setiap `MapiMessage`.

## Sumber Daya
- [Dokumentasi](https://reference.aspose.com/email/java/)
- [Unduh Aspose.Email untuk Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Percobaan Gratis](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Terakhir Diperbarui:** 2026-07-27  
**Diuji Dengan:** Aspose.Email untuk Java 25.4 (JDK 16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Kelola Kategori Outlook dengan Aspose.Email untuk Java - Panduan Komprehensif](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Buat catatan outlook java dengan Aspose.Email – Panduan Lengkap](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Buat Tugas di Microsoft Exchange Menggunakan Aspose.Email untuk Java: Panduan Lengkap](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}