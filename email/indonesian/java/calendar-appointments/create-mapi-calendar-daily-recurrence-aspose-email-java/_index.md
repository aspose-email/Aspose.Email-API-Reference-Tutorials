---
date: '2026-03-20'
description: Pelajari cara membuat kalender Outlook Java dengan pengulangan harian
  dan pengecualian, serta menyimpan kalender ke PST menggunakan Aspose.Email untuk
  Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Buat kalender Outlook Java dengan pengulangan harian dan pengecualian
url: /id/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat outlook calendar java dengan pengulangan harian dan pengecualian

Mengelola acara berulang secara efisien dapat menjadi tantangan, terutama ketika Anda membutuhkan **outlook calendar java** yang mendukung pola pengulangan harian dan pengecualian sesekali. Dalam tutorial ini Anda akan belajar cara membuat objek Outlook calendar Java, mengonfigurasi pengulangan harian, menambahkan contoh pengecualian, dan akhirnya **save calendar to PST** menggunakan Aspose.Email for Java. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam layanan penjadwalan berbasis Java mana pun.

## Jawaban Cepat
- **Library mana?** Aspose.Email for Java  
- **Tugas utama?** Membuat Outlook calendar Java dengan pengulangan harian dan pengecualian  
- **JDK prasyarat?** Java 16 atau lebih tinggi  
- **Bisakah saya melampirkan file ke pengecualian?** Ya, menggunakan `MapiCalendarExceptionInfo`  
- **Di mana kalender disimpan?** Di file PST melalui `PersonalStorage`

## Apa itu Outlook calendar java?
Objek Outlook calendar Java (diimplementasikan sebagai kalender MAPI) mengikuti standar yang sama dengan janji temu Microsoft Outlook. Objek ini menyimpan aturan pengulangan yang kaya, penanganan pengecualian, peserta, dan lampiran, menjadikannya sempurna untuk penjadwalan tingkat perusahaan.

## Mengapa menggunakan Aspose.Email for Java?
Aspose.Email menyediakan API murni‑Java yang memungkinkan Anda bekerja dengan objek MAPI tanpa perlu menginstal Outlook. Pendekatan **aspose email tutorial java** ini memungkinkan pembuatan file PST di sisi server, seri rapat otomatis, dan kontrol penuh atas logika pengulangan.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki pengaturan berikut:
- **Aspose.Email Library**: Versi 25.4 (atau lebih baru) – tersedia melalui Maven atau unduhan langsung.  
- **Java Development Kit (JDK)**: JDK 16 atau yang lebih baru.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, atau editor kompatibel Java apa pun.

### Perpustakaan dan Ketergantungan yang Diperlukan

Untuk mengintegrasikan Aspose.Email ke dalam proyek Anda menggunakan Maven, tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Akuisisi Lisensi

Untuk menggunakan Aspose.Email, Anda memerlukan lisensi:
- **Free Trial** – jelajahi semua fitur tanpa biaya.  
- **Temporary License** – minta untuk evaluasi yang diperpanjang.  
- **Full License** – beli untuk penerapan produksi.

## Menyiapkan Aspose.Email untuk Java

Pertama, siapkan lingkungan Anda:

1. Verifikasi JDK 16 terinstal dan `JAVA_HOME` telah dikonfigurasi.  
2. Tambahkan dependensi Maven (atau unduh JAR) ke proyek Anda.  

Berikut contoh potongan kode kecil yang menunjukkan cara memuat file lisensi:

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

## Panduan Implementasi

### Membuat Outlook calendar java dengan Pengulangan Harian dan Pengecualian

#### Gambaran Umum
Fitur ini memungkinkan Anda mengotomatisasi janji berulang sambil tetap dapat melewatkan atau memodifikasi contoh tertentu.

#### Implementasi Langkah‑per‑Langkah

**1. Atur Tanggal Mulai Acara**  
Tentukan kapan seri harus dimulai:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Buat Objek Kalender MAPI**  
Berikan lokasi, subjek, dan deskripsi:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Tentukan Pola Pengulangan Harian**  
Konfigurasikan acara agar berulang setiap hari:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Tambahkan Pengecualian ke Pengulangan**  
Tentukan tanggal yang harus dikecualikan (atau diubah):

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

### Melampirkan File ke Pengecualian Kalender

#### Gambaran Umum
Anda dapat melampirkan dokumen pendukung (mis., agenda) ke contoh pengecualian mana pun.

**1. Buat dan Lampirkan File**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Menyimpan Outlook calendar java ke PST (save calendar to pst)

#### Gambaran Umum
Simpan kalender ke file PST sehingga Outlook atau klien lain dapat membacanya.

**1. Buat dan Simpan Kalender ke PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Aplikasi Praktis
- **Penjadwalan Korporat** – mengotomatisasi seri rapat, secara otomatis melewatkan hari libur.  
- **Manajemen Proyek** – melacak tonggak berulang dengan pergeseran tanggal sesekali.  
- **Perencanaan Acara** – mengelola konferensi multi‑hari dimana beberapa sesi dibatalkan atau dijadwal ulang.

### Kemungkinan Integrasi
Gabungkan Aspose.Email dengan platform CRM, API manajemen tugas, atau mesin alur kerja khusus untuk menggerakkan otomatisasi end‑to‑end.

## Pertimbangan Kinerja
- **Buang Sumber Daya** – selalu panggil `dispose()` pada `PersonalStorage` untuk membebaskan handle file.  
- **Penggunaan Stream** – pilih `ByteArrayOutputStream` atau stream file untuk menghindari memuat seluruh PST ke memori.  
- **Operasi Asinkron** – untuk pembuatan kalender massal, jalankan logika pembuatan pada thread latar belakang agar UI tetap responsif.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini tahu cara **create outlook calendar java** objek dengan pengulangan harian, menambahkan pengecualian, melampirkan file, dan **save calendar to PST**. Kemampuan ini memungkinkan Anda membangun fitur penjadwalan yang kuat tanpa pernah menyentuh Outlook secara langsung.

### Langkah Selanjutnya
- Bereksperimen dengan pola pengulangan mingguan atau bulanan.  
- Jelajahi properti MAPI tambahan seperti peserta, pengingat, dan kategori.  
- Tinjau dokumentasi API lengkap Aspose.Email untuk skenario yang lebih maju.

## Pertanyaan yang Sering Diajukan

**Q: Apakah perpustakaan mendukung janji dengan zona waktu?**  
A: Ya, Anda dapat mengatur properti `StartTimeZone` dan `EndTimeZone` pada `MapiCalendar`.

**Q: Bisakah saya secara program menghapus satu kejadian dari seri berulang?**  
A: Gunakan koleksi `DeletedInstanceDates` pada pola pengulangan untuk menandai tanggal tertentu sebagai dihapus.

**Q: Apakah ada batas ukuran file PST yang dibuat dengan Aspose.Email?**  
A: File PST mengikuti batas format Unicode (hingga 2 GB secara default), namun Anda dapat mengonfigurasi ukuran lebih besar melalui pengaturan `PersonalStorage`.

**Q: Bagaimana cara menambahkan peserta ke permintaan rapat?**  
A: Buat objek `MapiRecipient`, atur `RecipientType` mereka menjadi `MapiRecipientType.MAPI_TO`, dan tambahkan ke koleksi `Recipients` pada `MapiMessage`.

**Q: Apakah ada dukungan untuk tugas berulang (bukan hanya janji)?**  
A: Ya, Aspose.Email juga menyediakan `MapiTask` dengan kemampuan pengulangan serupa.

**Q: Bisakah saya menggunakan panduan ini sebagai bagian dari seri tutorial aspose email java?**  
A: Tentu – langkah-langkah yang ditunjukkan di sini merupakan bagian inti dari tutorial Aspose.Email Java mana pun yang membahas pembuatan kalender.

## Sumber Daya
- [Dokumentasi Aspose.Email untuk Java](https://reference.aspose.com/email/java/)
- [Unduh Aspose.Email](https://releases.aspose.com/email/java/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Versi Free Trial](https://releases.aspose.com/email/java/)
- [Minta Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan Aspose](https://forum.aspose.com/c/email/10)

---

**Terakhir Diperbarui:** 2026-03-20  
**Diuji Dengan:** Aspose.Email for Java 25.4 (JDK 16)  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}