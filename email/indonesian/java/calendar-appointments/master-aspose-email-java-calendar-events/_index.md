---
date: '2026-08-01'
description: Pelajari cara mengekspor kalender ke PST dengan Aspose.Email for Java,
  termasuk cara menambahkan peserta, mengatur tanggal mulai dan selesai, serta mengelola
  janji dengan efisien.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Ekspor kalender ke PST menggunakan Aspose.Email for Java. Pelajari
  langkah demi langkah cara membuat janji, menambahkan peserta, dan menghasilkan file
  Outlook PST.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Ekspor kalender ke PST – Panduan Lengkap dengan Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Ekspor kalender ke PST dengan Aspose.Email for Java
url: /id/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ekspor kalender ke PST dengan Aspose.Email untuk Java

Jika Anda membangun aplikasi Java yang perlu berbagi data penjadwalan dengan Outlook, Anda sering perlu **mengekspor kalender ke PST**. Dalam tutorial ini kami akan membahas semua yang Anda perlukan—dari membuat janji sederhana hingga menambahkan peserta dan akhirnya menulis acara ke dalam file PST, semuanya dengan Aspose.Email untuk Java. Pada akhir tutorial Anda akan memiliki solusi siap produksi yang berfungsi di Windows, Linux, dan macOS.

## Jawaban Cepat
- **Apa tujuan utama?** Ekspor acara kalender ke file PST.  
- **Perpustakaan apa yang diperlukan?** Aspose.Email untuk Java (v25.4+).  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Email yang valid menghapus batas evaluasi.  
- **Bisakah saya menambahkan peserta?** Tentu – gunakan `MapiRecipientCollection`.  
- **Versi Java apa yang didukung?** JDK 16 atau lebih tinggi.

## Apa itu **ekspor kalender ke pst**?
`MapiCalendar` adalah kelas Aspose.Email yang memodelkan item kalender Outlook, termasuk subjek, lokasi, dan detail waktu.

Mengekspor kalender ke PST berarti mengonversi objek `MapiCalendar` dalam memori menjadi Microsoft Outlook Personal Storage Table (PST). File PST yang dihasilkan dapat dibuka langsung di Outlook, dibagikan dengan rekan kerja, atau diimpor ke sistem apa pun yang memahami format PST, menjaga semua detail acara seperti peserta, pengulangan, dan pengingat.

## Mengapa menggunakan Aspose.Email untuk Java untuk mengekspor kalender ke PST?
Anda dapat menghasilkan file PST yang sepenuhnya kompatibel tanpa menginstal Outlook. Aspose.Email menyediakan **dukungan MAPI penuh**, bekerja pada **semua sistem operasi utama**, dan dapat menangani **hingga 2 TB** data dalam format PST Unicode—cukup untuk arsip skala perusahaan. API juga memungkinkan Anda mengelola peserta, pola pengulangan, pengingat, dan properti khusus dengan hanya beberapa pemanggilan metode, secara dramatis mengurangi upaya pengembangan.

## Prasyarat
- **Perpustakaan & Ketergantungan**: Aspose.Email untuk Java versi 25.4 atau lebih baru.  
- **Lingkungan**: JDK 16 atau lebih tinggi, Maven untuk manajemen ketergantungan.  
- **Pengetahuan**: Pemrograman Java dasar dan familiaritas dengan Maven.

## Cara menyiapkan Aspose.Email untuk Java
Tambahkan dependensi Aspose.Email ke `pom.xml` Anda dan segarkan proyek Maven Anda. Langkah tunggal ini membuat seluruh API MAPI tersedia di classpath Anda.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Akuisisi Lisensi
Buka fungsionalitas penuh Aspose.Email tanpa batasan evaluasi dengan memperoleh lisensi:

1. **Uji Coba Gratis**: Kunjungi [halaman unduhan Aspose](https://releases.aspose.com/email/java/) untuk lisensi sementara.  
2. **Lisensi Sementara**: Ajukan melalui [halaman pembelian](https://purchase.aspose.com/temporary-license/).  
3. **Beli Lisensi**: Pertimbangkan membeli dari [portal pembelian Aspose](https://purchase.aspose.com/buy) untuk penggunaan jangka panjang.

Setelah Anda memiliki lisensi, inisialisasi di aplikasi Anda untuk mengaktifkan semua fitur.

## Cara **membuat janji** (Membuat Acara Kalender Java)

Muat objek `MapiCalendar`, atur properti inti-nya, dan kembalikan siap untuk pemrosesan lebih lanjut. Metode ini membuat entri kalender dengan subjek, lokasi, deskripsi, serta **tanggal mulai kalender java** / **tanggal akhir kalender java** yang Anda tentukan.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Penjelasan*: Kelas `MapiCalendar` adalah representasi Aspose.Email dari item kalender Outlook. Setelah mengatur bidang dasar, Anda juga dapat mengonfigurasi pengulangan, pengingat, dan kategori sebelum menyimpan.

## Cara **menambahkan peserta** (java menambahkan peserta rapat)

Buat `MapiRecipientCollection`, isi dengan setiap peserta, dan lampirkan ke rapat. Ini memastikan setiap peserta menerima undangan yang tepat ketika PST dibuka.

`MapiRecipientCollection` adalah kelas koleksi yang menyimpan objek `MapiRecipient` yang mewakili peserta rapat. `MapiRecipient` mewakili satu peserta dengan properti seperti alamat email dan tipe penerima.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Penjelasan*: `MapiRecipient` mendefinisikan satu peserta rapat. Menetapkan tipe ke `MAPI_TO` menandai alamat sebagai peserta utama, sementara `MAPI_CC` atau `MAPI_BCC` dapat digunakan untuk peserta opsional.

## Cara **mengekspor kalender ke pst** (Membuat PST dengan acara kalender)

Buat file PST Unicode, tambahkan folder "Calendar", dan sisipkan objek `MapiCalendar` yang telah dibuat sebelumnya. PST kemudian dapat dibuka di Outlook atau didistribusikan ke pengguna akhir.

`PersonalStorage` adalah kelas Aspose.Email yang digunakan untuk membuat, membuka, dan memanipulasi file PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Penjelasan*: `PersonalStorage` adalah titik masuk untuk manipulasi PST. Dengan menggunakan format Unicode Anda menghindari batas 2 GB pada versi PST lama dan mendapatkan manfaat I/O yang lebih cepat pada arsip besar.

## Aplikasi Praktis
1. **Penjadwalan Bisnis** – Mengotomatisasi pembuatan dan distribusi rapat internal.  
2. **Manajemen Acara** – Melacak konferensi, lokakarya, dan daftar peserta.  
3. **Integrasi CRM** – Menyinkronkan janji dengan alat hubungan pelanggan.  
4. **Perencanaan Proyek** – Menyimpan tonggak proyek sebagai item kalender.  
5. **Kolaborasi Tim Jarak Jauh** – Menghasilkan file PST untuk berbagi secara offline.

## Pertimbangan Kinerja
- **Dispose objek** yang tidak lagi Anda perlukan untuk membebaskan memori dengan cepat.  
- **Gunakan koleksi yang efisien** (mis., `ArrayList` untuk daftar peserta) saat menangani ribuan peserta.  
- **Cache acara yang sering diakses** jika Anda sering mengkueri PST, mengurangi I/O disk.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **File PST tidak dibuat** | Verifikasi izin menulis pada direktori target dan pastikan jalur folder ada. |
| **Peserta tidak menerima undangan** | Pastikan setiap `MapiRecipient` menggunakan `MapiRecipientType.MAPI_TO` dan email penyelenggara valid. |
| **Ketidaksesuaian tanggal** | Gunakan `Calendar` secara konsisten untuk tanggal mulai/akhir; hindari mencampur `java.util.Date` dengan perpustakaan tanggal lain tanpa konversi. |

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara memulai dengan Aspose.Email untuk Java?**  
A: Tambahkan dependensi Maven yang ditunjukkan di atas, dapatkan lisensi, dan ikuti langkah-langkah dalam panduan ini untuk membuat dan mengekspor acara kalender.

**Q: Bisakah saya menyesuaikan nama dan lokasi file PST?**  
A: Ya, ubah variabel `pstFilePath` dalam `createPSTWithCalendarEvents()` ke jalur yang valid di sistem Anda.

**Q: Apakah memungkinkan menambahkan pola pengulangan ke janji?**  
A: Tentu – `MapiCalendar` menyediakan properti `RecurrencePattern` yang dapat Anda konfigurasikan sebelum menyimpan.

**Q: Apakah Aspose.Email mendukung format kalender lain selain PST?**  
A: Ya, Anda dapat mengekspor ke iCalendar (`.ics`) dan format lain menggunakan metode API yang sesuai.

**Q: Berapa ukuran maksimum file PST yang dapat saya buat?**  
A: Dengan format Unicode (`FileFormatVersion.Unicode`), file PST dapat tumbuh hingga 2 TB, terbatas hanya oleh ruang disk yang tersedia.

---

**Terakhir Diperbarui:** 2026-08-01  
**Diuji Dengan:** Aspose.Email untuk Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Menguasai Aspose.Email untuk Java: Mengelola File PST Outlook Secara Efisien](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Menguasai Membuat dan Menyimpan Item Kalender dengan Aspose.Email untuk Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Cara Membaca Banyak Acara Kalender dari File ICS Menggunakan Aspose.Email di Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}