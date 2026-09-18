---
date: '2026-09-17'
description: Pelajari cara membuat kalender Outlook Java dengan daily recurrence dan
  exceptions, serta menyimpan kalender ke PST menggunakan Aspose.Email for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Buat kalender Outlook di Java menggunakan Aspose.Email. Pelajari daily
  recurrence, exception handling, dan penyimpanan ke PST dalam panduan langkah demi
  langkah.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Buat kalender Outlook di Java dengan daily recurrence dan exceptions
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Buat kalender Outlook Java dengan daily recurrence dan exceptions
url: /id/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat outlook calendar java dengan pengulangan harian dan pengecualian

Mengelola acara berulang secara efisien dapat menjadi tantangan, terutama ketika Anda membutuhkan **outlook calendar java** yang mendukung pola pengulangan harian dan pengecualian sesekali. Dalam tutorial ini Anda akan belajar cara membuat objek Outlook calendar Java, mengonfigurasi pengulangan harian, menambahkan contoh pengecualian, dan akhirnya **save calendar to PST** menggunakan Aspose.Email untuk Java. Pada akhir tutorial Anda akan memiliki cuplikan kode yang dapat digunakan kembali dan dapat disisipkan ke layanan penjadwalan berbasis Java apa pun.

## Jawaban Cepat
- **Library mana?** Aspose.Email for Java  
- **Tugas utama?** Buat Outlook calendar Java dengan pengulangan harian dan pengecualian  
- **JDK prasyarat?** Java 16 atau lebih tinggi  
- **Bisakah saya melampirkan file ke pengecualian?** Ya, menggunakan `MapiCalendarExceptionInfo`  
- **Di mana kalender disimpan?** Di file PST via `PersonalStorage`  

## Apa itu Outlook calendar java?
Objek Outlook calendar Java adalah representasi programatik dari sebuah janji Outlook, dibangun di atas spesifikasi MAPI (Messaging Application Programming Interface), yang mencakup properti seperti subjek, lokasi, waktu mulai/berakhir, aturan pengulangan, peserta, dan lampiran. Objek ini dapat dimanipulasi, diserialisasi, dan disimpan dalam file PST tanpa memerlukan Outlook.

## Mengapa menggunakan Aspose.Email untuk Java?
Aspose.Email untuk Java memungkinkan Anda bekerja dengan objek MAPI tanpa menginstal Outlook. Pustaka ini mendukung **50+ properti MAPI**, dapat menghasilkan file PST Unicode hingga **2 GB** dalam waktu kurang dari **2 detik** untuk data janji tipikal, dan berjalan pada platform apa pun yang mendukung Java 16+. Pendekatan murni Java ini memungkinkan pembuatan kalender sisi server, seri pertemuan otomatis, dan kontrol penuh atas logika pengulangan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki pengaturan berikut:
- **Pustaka Aspose.Email**: Versi 25.4 (atau lebih baru) – tersedia via Maven atau unduhan langsung.  
- **Java Development Kit (JDK)**: JDK 16 atau lebih baru.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, atau editor yang kompatibel dengan Java.

### Perpustakaan dan dependensi yang diperlukan

Untuk mengintegrasikan Aspose.Email ke dalam proyek Anda menggunakan Maven, tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Perolehan lisensi

Untuk menggunakan Aspose.Email, Anda memerlukan lisensi:
- **Uji coba gratis** – jelajahi semua fitur tanpa biaya.  
- **Lisensi sementara** – minta untuk evaluasi yang diperpanjang.  
- **Lisensi penuh** – beli untuk penerapan produksi.

## Menyiapkan Aspose.Email untuk Java

Pertama, siapkan lingkungan Anda:

1. Verifikasi JDK 16 terpasang dan `JAVA_HOME` dikonfigurasi.  
2. Tambahkan dependensi Maven (atau unduh JAR) ke proyek Anda.  

Berikut cuplikan kecil yang menunjukkan cara memuat file lisensi:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Panduan implementasi

### Membuat outlook calendar java dengan pengulangan harian dan pengecualian

#### Gambaran Umum
Fitur ini memungkinkan Anda mengotomatisasi janji berulang sambil tetap dapat melewatkan atau mengubah contoh tertentu.

#### Implementasi langkah‑demi‑langkah

**1. Atur tanggal mulai acara**  
Tentukan kapan seri harus dimulai:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Buat objek kalender MAPI**  
Kelas `MapiCalendar` adalah objek tingkat atas yang mewakili satu item kalender dalam memori. Berikan lokasi, subjek, dan deskripsi:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Tentukan pola pengulangan harian**  
Kelas `MapiCalendarRecurrencePattern` menyimpan aturan yang mengulang janji setiap hari. Konfigurasikan acara untuk berulang setiap hari:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Tambahkan pengecualian ke pengulangan**  
`MapiCalendarExceptionInfo` menjelaskan satu kejadian yang menyimpang dari pola—baik dikecualikan atau diubah. Tentukan tanggal yang harus dikecualikan (atau diubah):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Melampirkan file ke pengecualian kalender

#### Gambaran Umum
Anda dapat melampirkan dokumen pendukung (mis., agenda) ke contoh pengecualian mana pun.

**1. Buat dan lampirkan file**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Menyimpan outlook calendar java ke PST (save calendar to pst)

#### Gambaran Umum
Persist kalender ke file PST sehingga Outlook atau klien lain dapat membacanya.

**1. Buat dan simpan kalender ke PST**  
Kelas `PersonalStorage` menyediakan metode untuk membuat file PST baru dan menambahkan item MAPI ke dalamnya.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Aplikasi praktis
- **Penjadwalan korporat** – otomatisasi seri pertemuan, secara otomatis melewatkan hari libur.  
- **Manajemen proyek** – lacak tonggak berulang dengan pergeseran tanggal sesekali.  
- **Perencanaan acara** – kelola konferensi multi‑hari di mana beberapa sesi dibatalkan atau dijadwal ulang.

### Kemungkinan integrasi
Gabungkan Aspose.Email dengan platform CRM, API manajemen tugas, atau mesin alur kerja khusus untuk menggerakkan otomatisasi ujung‑ke‑ujung.

## Pertimbangan kinerja
- **Bebaskan sumber daya** – selalu panggil `dispose()` pada `PersonalStorage` untuk membebaskan handle file.  
- **Penggunaan stream** – pilih `ByteArrayOutputStream` atau stream file untuk menghindari memuat seluruh PST ke memori.  
- **Operasi async** – untuk pembuatan kalender massal, jalankan logika pembuatan pada thread latar belakang agar UI tetap responsif.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini tahu cara **create outlook calendar java** objek dengan pengulangan harian, menambahkan pengecualian, melampirkan file, dan **save calendar to PST**. Kemampuan ini memungkinkan Anda membangun fitur penjadwalan yang kuat tanpa pernah menyentuh Outlook secara langsung.

### Langkah selanjutnya
- Bereksperimen dengan pola pengulangan mingguan atau bulanan.  
- Jelajahi properti MAPI tambahan seperti peserta, pengingat, dan kategori.  
- Tinjau dokumentasi API lengkap Aspose.Email untuk skenario yang lebih maju.

## Pertanyaan yang sering diajukan

**Q: Apakah pustaka mendukung janji dengan zona waktu?**  
A: Ya, Anda dapat mengatur properti `StartTimeZone` dan `EndTimeZone` pada `MapiCalendar`.

**Q: Bisakah saya secara programatis menghapus satu kejadian dari seri berulang?**  
A: Gunakan koleksi `DeletedInstanceDates` pada pola pengulangan untuk menandai tanggal tertentu sebagai dihapus.

**Q: Apakah ada batasan ukuran file PST yang dibuat dengan Aspose.Email?**  
A: File PST mengikuti batas format Unicode (hingga 2 GB secara default), namun Anda dapat mengonfigurasi ukuran lebih besar melalui pengaturan `PersonalStorage`.

**Q: Bagaimana cara menambahkan peserta ke permintaan pertemuan?**  
A: Buat objek `MapiRecipient`, atur `RecipientType` menjadi `MapiRecipientType.MAPI_TO`, dan tambahkan ke koleksi `Recipients` pada `MapiMessage`.

**Q: Apakah ada dukungan untuk tugas berulang (bukan hanya janji)?**  
A: Ya, Aspose.Email juga menyediakan `MapiTask` dengan kemampuan pengulangan serupa.

**Q: Bisakah saya menggunakan panduan ini sebagai bagian dari seri tutorial Aspose.Email Java?**  
A: Tentu – langkah‑langkah yang ditunjukkan di sini merupakan bagian inti dari setiap tutorial Aspose.Email Java yang membahas pembuatan kalender.

## Sumber daya
- [Dokumentasi Aspose.Email untuk Java](https://reference.aspose.com/email/java/)
- [Unduh Aspose.Email](https://releases.aspose.com/email/java/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Versi Uji Coba Gratis](https://releases.aspose.com/email/java/)
- [Minta Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan Aspose](https://forum.aspose.com/c/email/10)

---

**Last updated:** 2026-09-17  
**Tested with:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

## Tutorial Terkait

- [Ekspor PST Kalender Outlook dengan Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Cara Membuat Item Kalender Java Menggunakan Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Buat Undangan Berbagi Kalender dengan Aspose.Email untuk Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}