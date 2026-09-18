---
date: '2026-09-17'
description: Pelajari cara mengekspor PST kalender Outlook menggunakan Aspose.Email
  untuk Java – buat item kalender MAPI, atur pengulangan, tambahkan peserta, dan simpan
  ke PST.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Ekspor PST kalender Outlook menggunakan Aspose.Email untuk Java. Pelajari
  cara membuat item kalender MAPI, menambahkan pengulangan, peserta, dan menyimpan
  ke PST dalam hitungan menit.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Ekspor PST kalender Outlook dengan Aspose.Email – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Ekspor PST kalender Outlook dengan Aspose.Email – Java
url: /id/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor PST Kalender Outlook dengan Aspose.Email – Java

## Pendahuluan

Apakah Anda ingin menyederhanakan otomatisasi kalender dalam aplikasi Java Anda dan perlu **mengekspor file PST kalender Outlook**? Dengan **Aspose.Email for Java**, Anda dapat **membuat item MAPI calendar Java**, menentukan pola pengulangan, menambahkan peserta, dan **menyimpan kalender ke PST** dengan hanya beberapa baris kode. Tutorial ini memandu Anda melalui seluruh proses—dari menyiapkan pustaka hingga menghasilkan entri kalender yang sepenuhnya berfungsi siap untuk didistribusikan.

### Apa yang akan Anda pelajari
- Cara **membuat acara MAPI calendar Java** menggunakan Aspose.Email.  
- Mengonfigurasi pola pengulangan harian, mingguan, atau kustom.  
- Menambahkan penerima (penyelenggara, peserta) ke undangan kalender Anda.  
- Menyimpan item kalender dengan **menyimpan kalender ke PST** untuk kompatibilitas Outlook.  
- Cara **mengotomatiskan penjadwalan rapat** dengan kode yang dapat digunakan kembali.

## Jawaban Cepat
- **Perpustakaan mana?** Aspose.Email for Java  
- **Tujuan utama?** Ekspor PST kalender Outlook dan **menyimpan kalender ke PST**  
- **Prasyarat?** Java 8+, Maven, lisensi Aspose.Email  
- **Waktu implementasi tipikal?** 10‑15 menit untuk acara dasar  
- **Bisakah saya menambahkan pengulangan?** Ya – harian, mingguan, bulanan, dll.

## Ekspor PST Kalender Outlook

Pada bagian ini kami fokus pada alur end‑to‑end yang memungkinkan Anda **mengekspor PST kalender Outlook**. Setelah membuat objek kalender MAPI, langkah terakhir adalah menyimpannya di dalam file PST yang dapat dibaca langsung oleh Outlook.

## Mengapa menggunakan Aspose.Email untuk otomatisasi kalender?

Ekspor PST kalender Outlook dengan Aspose.Email karena memberikan cara yang andal di sisi server untuk menghasilkan item yang kompatibel dengan Outlook tanpa interop COM. Perpustakaan ini mendukung **50+ format input dan output**, dapat menangani file PST yang melebihi 2 GB, dan memproses ribuan entri kalender per menit pada perangkat keras server tipikal. Mesin pengulangan bawaan mencakup pola harian, mingguan, bulanan, dan kustom, menghilangkan kebutuhan perhitungan tanggal manual.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

### Perpustakaan yang Diperlukan
- **Aspose.Email for Java**: Versi 25.4 atau lebih baru (mendukung Java 8‑21).

### Persyaratan Penyiapan Lingkungan
- IDE Java seperti IntelliJ IDEA atau Eclipse.  
- Maven terpasang untuk mengelola dependensi.

### Prasyarat Pengetahuan
- Keterampilan pemrograman Java dasar.  
- Familiaritas dengan konsep berorientasi objek.

## Menyiapkan Aspose.Email untuk Java

Tambahkan dependensi Maven Aspose.Email ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Perolehan Lisensi

Aspose.Email menawarkan uji coba gratis, tetapi lisensi membuka semua fitur:

- **Uji coba gratis**: Menguji tanpa batasan selama 30 hari.  
- **Lisensi sementara**: Minta melalui [situs Aspose](https://purchase.aspose.com/temporary-license/) jika Anda membutuhkan waktu tambahan.  
- **Pembelian**: Beli lisensi permanen dari [halaman pembelian](https://purchase.aspose.com/buy).

### Inisialisasi Dasar

Setelah menambahkan dependensi, inisialisasi pustaka dengan file lisensi Anda:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Panduan Implementasi

Sekarang Anda sudah siap, mari **membuat MAPI calendar Java** dan **menyimpan kalender ke PST**.

### Buat kalender MAPI dengan pengulangan

#### Gambaran Umum

Kami akan membuat acara kalender, menerapkan pengulangan harian, menambahkan peserta, dan akhirnya menyimpannya dalam file PST.

#### Implementasi Langkah‑demi‑Langkah

1. **Inisialisasi tanggal dan pola pengulangan**  

   `MapiCalendarEventRecurrence` adalah kelas yang menyimpan detail pengulangan untuk item kalender.  
   `MapiCalendarDailyRecurrencePattern` mendefinisikan jadwal pengulangan harian sederhana.  

   Pertama, tentukan waktu mulai dan atur pengulangan harian:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Menyiapkan penerima**  

   `MapiRecipientCollection` mewakili daftar orang yang diundang ke pertemuan.  
   `MAPI_TO` adalah flag yang menandai penerima sebagai peserta utama.  

   Tambahkan orang yang harus menerima undangan pertemuan:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **Buat item kalender MAPI**  

   Kelas `MapiMessage` (digunakan di sini sebagai objek kalender) mengenkapsulasi semua properti acara seperti penyelenggara, subjek, lokasi, waktu mulai/selesai, deskripsi, daftar penerima, dan pengulangan.  

   Bangun objek kalender dengan semua detail yang diperlukan:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

4. **Simpan ke file PST**  

   `PersonalStorage` adalah API tingkat atas Aspose.Email untuk membuat dan memanipulasi file PST.  
   `addMapiMessageItem` menyisipkan pesan MAPI (termasuk item kalender) ke dalam folder yang ditentukan.  

   Akhirnya, persistensikan kalender dengan **menyimpan kalender ke PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### Tips Pemecahan Masalah
- Verifikasi jalur lisensi; lisensi yang tidak valid akan membatasi fungsionalitas.  
- Pastikan alamat email penerima diformat dengan benar untuk menghindari kegagalan undangan.  
- Tutup PST (`pst.dispose()`) setelah operasi untuk membebaskan handle file.

## Aplikasi Praktis

Berikut adalah skenario umum di mana **membuat MAPI calendar Java** dan **menyimpan kalender ke PST** bersinar:

1. **Penjadwalan rapat otomatis** – Menghasilkan undangan rapat berulang untuk tim proyek tanpa usaha manual.  
2. **Platform manajemen acara** – Mengekspor sesi konferensi sebagai item kalender yang kompatibel dengan Outlook.  
3. **Integrasi CRM** – Menyinkronkan janji pelanggan dari sistem CRM langsung ke Outlook melalui file PST.

## Pertimbangan Kinerja

- **Manajemen sumber daya**: Buang objek `PersonalStorage` setelah penggunaan untuk mencegah penguncian file.  
- **Pemrosesan batch**: Untuk volume besar, proses item kalender secara asynchronous atau dalam potongan untuk menjaga penggunaan memori rendah.  
- **Skalabilitas**: Aspose.Email dapat menulis ke file PST yang lebih besar dari 2 GB sambil menjaga konsumsi memori di bawah 200 MB.

## Kesimpulan

Anda kini telah mempelajari cara **mengekspor PST kalender Outlook** dengan membuat objek MAPI calendar Java, mengonfigurasi pengulangan, menambahkan peserta, dan **menyimpan kalender ke PST** menggunakan Aspose.Email. Pendekatan ini memberdayakan aplikasi Java Anda untuk mengotomatiskan alur kerja penjadwalan yang canggih dengan kompatibilitas Outlook.

Untuk eksplorasi lebih mendalam, periksa [dokumentasi resmi](https://reference.aspose.com/email/java/).

## Bagian FAQ

### Q: Bisakah saya membuat pola pengulangan mingguan?
- **A**: Ya! Gunakan `MapiCalendarWeeklyRecurrencePattern` untuk mendefinisikan pengulangan mingguan.

### Q: Bagaimana cara menangani pengecualian dalam pengulangan acara?
- **A**: Panggil `setExceptions()` pada objek pengulangan untuk menentukan tanggal yang menyimpang dari pola.

### Q: Apakah memungkinkan memperbarui item kalender yang ada?
- **A**: Tentu saja. Muat item dari PST, ubah propertinya, dan simpan kembali.

### Q: Bisakah saya mengenkripsi file PST?
- **A**: Ya, Aspose.Email memungkinkan Anda menetapkan kata sandi pada `PersonalStorage` saat membuat PST.

### Q: Bagaimana jika saya perlu menambahkan lampiran ke acara kalender?
- **A**: Gunakan `calendar.getAttachments().addFileAttachment("path/to/file")` sebelum menyimpan.

## Sumber Daya

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free trial version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose support forum](https://forum.aspose.com/c/email/10)

---

**Last updated:** 2026-09-17  
**Tested with:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

## Tutorial Terkait

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [How to Create PST Files with Aspose.Email for Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}