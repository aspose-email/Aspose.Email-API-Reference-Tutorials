---
date: '2026-03-20'
description: Pelajari cara mengekspor PST kalender Outlook menggunakan Aspose.Email
  untuk Java – buat item kalender MAPI, atur pengulangan, tambahkan peserta, dan simpan
  ke PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Ekspor Kalender Outlook PST dengan Aspose.Email – Java
url: /id/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Outlook calendar PST dengan Aspose.Email – Java

## Pendahuluan

Apakah Anda ingin menyederhanakan otomatisasi kalender dalam aplikasi Java Anda dan perlu **export Outlook calendar PST**? Dengan **Aspose.Email for Java**, Anda dapat **create MAPI calendar Java** items, define recurrence patterns, add attendees, dan **save calendar to PST** dengan hanya beberapa baris kode. Tutorial ini memandu Anda melalui seluruh proses—from setting up the library to generating a fully functional calendar entry ready for distribution.

### Apa yang Akan Anda Pelajari
- Cara **create MAPI calendar Java** event menggunakan Aspose.Email.  
- Mengonfigurasi pola pengulangan harian, mingguan, atau kustom.  
- Menambahkan penerima (penyelenggara, peserta) ke undangan kalender Anda.  
- Menyimpan item kalender dengan **saving calendar to PST** untuk kompatibilitas Outlook.  
- Cara **automate meeting scheduling** dengan kode yang dapat digunakan kembali.

## Jawaban Cepat
- **Library mana?** Aspose.Email for Java  
- **Tujuan utama?** Export Outlook calendar PST dan **save calendar to PST**  
- **Prasyarat?** Java 8+, Maven, lisensi Aspose.Email  
- **Waktu implementasi tipikal?** 10‑15 menit untuk event dasar  
- **Bisakah menambahkan pengulangan?** Ya – harian, mingguan, bulanan, dll.

## Export Outlook calendar PST

Dalam bagian ini kami fokus pada alur end‑to‑end yang memungkinkan Anda **export Outlook calendar PST** files. Setelah membuat objek MAPI calendar, langkah terakhir adalah menyimpannya di dalam file PST yang dapat dibaca langsung oleh Outlook.

## Mengapa menggunakan Aspose.Email untuk otomatisasi kalender?

- **Kompatibilitas Outlook penuh** – item yang dihasilkan berfungsi di Outlook, OWA, dan klien seluler.  
- **Dukungan pengulangan lengkap** – pola harian, mingguan, bulanan, dan kustom siap pakai.  
- **Tanpa ketergantungan eksternal** – pustaka Java murni, tidak memerlukan interop COM.  
- **Kinerja tinggi** – penanganan efisien file PST besar dan operasi massal.  
- **Automate meeting scheduling** – sematkan logika ini dalam pekerjaan batch atau layanan web untuk membuat ratusan undangan secara otomatis.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

### Perpustakaan yang Diperlukan
- **Aspose.Email for Java**: Versi 25.4 atau lebih baru.

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

Aspose.Email menawarkan free trial, tetapi lisensi membuka semua fitur:

- **Free Trial**: Uji tanpa batas selama 30 hari.  
- **Temporary License**: Minta melalui [Aspose's website](https://purchase.aspose.com/temporary-license/) jika Anda membutuhkan waktu tambahan.  
- **Purchase**: Beli lisensi permanen dari [purchase page](https://purchase.aspose.com/buy).

### Inisialisasi Dasar

Setelah menambahkan dependensi, inisialisasi pustaka dengan file lisensi Anda:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Panduan Implementasi

Sekarang Anda sudah siap, mari **create MAPI calendar Java** dan **save calendar to PST**.

### Buat MAPI Calendar dengan Pengulangan

#### Gambaran Umum

Kami akan membangun sebuah event kalender, menerapkan pengulangan harian, menambahkan peserta, dan akhirnya menyimpannya dalam file PST.

#### Implementasi Langkah‑per‑Langkah

1. **Initialize Date and Recurrence Pattern**  

   Pertama, definisikan waktu mulai dan atur pengulangan harian:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` holds recurrence details; we choose a daily pattern via `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Tambahkan orang‑orang yang harus menerima undangan rapat:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` stores each attendee; `MAPI_TO` marks them as primary recipients.

3. **Create the MAPI Calendar Item**  

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

   *Explanation*: The constructor expects organizer, subject, location, start/end times, description, recipient list, and recurrence.

4. **Save to PST File**  

   Akhirnya, persist kalender dengan **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` generates a new PST file, and `addMapiMessageItem` inserts the calendar entry into the "Calendar" folder.

### Tips Pemecahan Masalah
- Verifikasi jalur lisensi; lisensi tidak valid akan membatasi fungsionalitas.  
- Pastikan alamat email penerima diformat dengan benar untuk menghindari kegagalan undangan.  
- Tutup PST (`pst.dispose()`) setelah operasi untuk membebaskan handle file.

## Aplikasi Praktis

Berikut adalah skenario umum di mana **creating MAPI calendar Java** dan **saving calendar to PST** bersinar:

1. **Automated Meeting Scheduling** – Hasilkan undangan rapat berulang untuk tim proyek tanpa usaha manual.  
2. **Event Management Platforms** – Ekspor sesi konferensi sebagai item kalender yang kompatibel dengan Outlook.  
3. **CRM Integration** – Sinkronkan janji pelanggan dari sistem CRM langsung ke Outlook melalui file PST.

## Pertimbangan Kinerja

- **Manajemen Sumber Daya**: Buang objek `PersonalStorage` setelah penggunaan untuk mencegah penguncian file.  
- **Pemrosesan Batch**: Untuk volume besar, proses item kalender secara asynchronous atau dalam potongan untuk menjaga penggunaan memori tetap rendah.  

## Kesimpulan

Anda kini telah mempelajari cara **export Outlook calendar PST** dengan membuat objek MAPI calendar Java, mengonfigurasi pengulangan, menambahkan peserta, dan **saving calendar to PST** menggunakan Aspose.Email. Pendekatan ini memberi kekuatan pada aplikasi Java Anda untuk mengotomatisasi alur kerja penjadwalan yang canggih dengan kompatibilitas Outlook.

Untuk eksplorasi lebih dalam, periksa [documentation](https://reference.aspose.com/email/java/) resmi.

## Bagian FAQ

### Q: Bisakah saya membuat pola pengulangan mingguan?
- **A**: Yes! Use `MapiCalendarWeeklyRecurrencePattern` to define weekly repeats.

### Q: Bagaimana cara menangani pengecualian dalam pengulangan acara?
- **A**: Call `setExceptions()` on the recurrence object to specify dates that deviate from the pattern.

### Q: Apakah memungkinkan memperbarui item kalender yang ada?
- **A**: Absolutely. Load the item from the PST, modify its properties, and save it back.

### Q: Bisakah saya mengenkripsi file PST?
- **A**: Yes, Aspose.Email allows you to set a password on `PersonalStorage` when creating the PST.

### Q: Bagaimana jika saya perlu menambahkan lampiran ke acara kalender?
- **A**: Use `calendar.getAttachments().addFileAttachment("path/to/file")` before saving.

## Sumber Daya

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}