---
date: '2026-09-17'
description: Cara membuat undangan kalender dengan Aspose.Email for Java memungkinkan
  Anda berbagi kalender, mengatur izin delegasi, dan mengirim email berbagi secara
  programatik.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Cara membuat undangan kalender dengan Aspose.Email for Java memungkinkan
  Anda berbagi kalender secara programatik, mengatur izin delegasi, dan mengirim email
  berbagi melalui Exchange Web Services, meningkatkan kolaborasi tim.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Cara membuat undangan kalender dengan Aspose.Email for Java
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
title: Cara membuat undangan kalender dengan Aspose.Email for Java
url: /id/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola berbagi kalender: Panduan Aspose.Email untuk Java

## Pengenalan mengelola berbagi kalender
Mengelola undangan berbagi kalender dapat menjadi tugas yang kompleks, terutama ketika menangani banyak pengguna di berbagai platform. Dalam tutorial ini Anda akan **membuat undangan berbagi kalender** dengan Aspose.Email untuk Java, mencakup segala hal mulai dari membuat akses delegasi hingga mengirim email berbagi kalender. Pada akhir tutorial, Anda akan dapat mengatur izin delegasi, **mengonfigurasi izin kalender**, dan menyederhanakan kolaborasi di organisasi Anda.

**Apa yang akan Anda pelajari**
- Cara menginisialisasi klien EWS dengan Aspose.Email untuk Java  
- Membuat pengguna delegasi dan **mengatur izin delegasi**  
- **Membuat akses delegasi** dan mengonfigurasi izin kalender  
- Mengirim **email berbagi kalender** (undangan) secara programatis  
- Skenario dunia nyata di mana fitur ini menambah nilai  

Sebelum kita mulai, pastikan Anda memiliki semua yang diperlukan.

## Jawaban cepat
- **Apa tujuan utama panduan ini?** Menunjukkan cara **membuat undangan berbagi kalender** menggunakan Aspose.Email untuk Java.  
- **Versi perpustakaan mana yang diperlukan?** Aspose.Email untuk Java 25.4 (klasifikasi JDK 16).  
- **Apakah saya memerlukan lisensi?** Ya – lisensi percobaan atau penuh diperlukan untuk penggunaan produksi.  
- **Lingkungan apa yang dibutuhkan?** JDK 16+, Maven, dan akun Exchange Online.  
- **Bisakah saya menggunakan ini dengan server Exchange lain?** Ya, tetapi Anda mungkin perlu menyesuaikan URL layanan dan tingkat izin.

## Apa itu undangan berbagi kalender?
Undangan berbagi kalender adalah pesan email yang memberikan pengguna lain akses untuk melihat (atau mengedit) kalender Anda tanpa memberikan hak penuh pada kotak surat. Ini memungkinkan anggota tim melihat jadwal Anda, mengusulkan rapat, atau mengelola acara sambil menjaga keamanan kotak surat Anda.

## Mengapa mengonfigurasi izin kalender?
Mengonfigurasi izin kalender memungkinkan Anda mengontrol secara tepat apa yang dapat dilakukan delegasi—apakah mereka hanya dapat membaca acara, mengusulkan yang baru, atau mengedit entri yang ada. Pengaturan izin yang tepat melindungi informasi sensitif sambil memungkinkan kolaborasi yang efektif. Misalnya, memberikan akses hanya baca mencegah perubahan tidak sengaja, sementara hak edit memungkinkan delegasi menjadwalkan atau memodifikasi rapat atas nama Anda.

## Prasyarat
- **Java Development Kit (JDK):** Versi 16 atau lebih baru.  
- **Maven:** Untuk manajemen dependensi dan membangun proyek.  
- **Aspose.Email for Java Library:** Versi 25.4 dengan dukungan JDK 16.  

### Persyaratan penyiapan lingkungan
1. Instal JDK jika belum. Anda dapat mengunduhnya dari [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Pastikan Maven terinstal dan dikonfigurasi di mesin Anda.  
3. Pilih IDE seperti IntelliJ IDEA atau Eclipse untuk pengembangan yang lebih mudah.

### Prasyarat pengetahuan
- Keterampilan pemrograman Java dasar  
- Keterbiasaan dengan dependensi Maven  
- Opsional: Pengalaman dengan Exchange Web Services (EWS)

## Menyiapkan Aspose.Email untuk Java
### Konfigurasi Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Akuisisi lisensi
Aspose.Email for Java requires a license for full functionality. You can:
- **Uji coba gratis:** Unduh dari [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Lisensi sementara:** Minta kunci sementara di situs Aspose.  
- **Pembelian:** Dapatkan lisensi permanen untuk penerapan produksi.

### Inisialisasi dan penyiapan dasar
Once Maven resolves the dependency, initialize the EWS client:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

`ExchangeService` adalah kelas utama yang digunakan untuk berkomunikasi dengan Exchange Web Services.  

## Cara membuat undangan berbagi kalender
Mengelola undangan berbagi kalender Anda pertama‑tama menghubungkan ke Exchange menggunakan klien `ExchangeService`, kemudian mendefinisikan delegasi dengan tingkat izin yang diinginkan, dan akhirnya menyusun `MailMessage` yang mencakup permintaan berbagi. Langkah‑langkah berikut menunjukkan alur kerja ini dalam Java.

Di bawah ini kami membahas dua fitur inti: membuat dan mengirim undangan berbagi kalender, serta **mengatur izin delegasi** untuk akses kalender.

### Fitur 1: membuat dan mengirim undangan berbagi kalender
#### Ikhtisar
Fitur ini memandu Anda melalui inisialisasi klien, **membuat akses delegasi**, dan mengirim email undangan.

#### Implementasi langkah‑demi‑langkah
##### 1️⃣ Initialize EWS client
`ExchangeService` mewakili koneksi ke server Exchange dan digunakan untuk mengirim serta menerima pesan.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Ini menghubungkan aplikasi Java Anda ke Exchange Online.

##### 2️⃣ Create delegate user
`DelegateUser` mendefinisikan alamat email delegasi dan tingkat izin yang akan diberikan.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Di sini kami **membuat akses delegasi** dan menetapkan tingkat `Reviewer`, yang memungkinkan delegasi melihat item kalender.

##### 3️⃣ Send calendar sharing invitation
`MailMessage` menyusun email yang membawa undangan berbagi kalender.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Kode ini membangun **email berbagi kalender** (undangan) dan mengirimnya melalui klien EWS.

### Fitur 2: izin akses kalender delegasi
#### Ikhtisar
Bagian ini menunjukkan cara **mengonfigurasi izin kalender** dan memastikan delegasi memiliki hak yang tepat.

#### Langkah‑langkah implementasi
##### 1️⃣ Initialize EWS client (reuse)
`ExchangeService` dapat digunakan kembali untuk beberapa operasi setelah konfigurasi awal.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Create and set delegate permissions
`ExchangeDelegateFolderPermissionLevel` mengenumerasi tingkat akses yang dapat dimiliki delegasi ke folder kalender.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Potongan kode ini **mengatur izin delegasi** sehingga pengguna dapat melihat entri kalender tanpa akses penuh ke kotak surat.

## Cara mengonfigurasi izin kalender untuk delegasi
Ketika delegasi membutuhkan lebih dari akses hanya baca, Anda dapat menyesuaikan `ExchangeDelegateFolderPermissionLevel` untuk memberikan hak edit, author, atau owner. Pilih tingkat minimal yang memenuhi kebutuhan bisnis untuk menjaga keamanan sambil menyediakan fungsionalitas yang diperlukan. Misalnya, menetapkan tingkat Editor memungkinkan delegasi membuat, memodifikasi, dan menghapus acara, sedangkan tingkat Reviewer hanya memperbolehkan melihat.

- `Reviewer` – akses hanya baca.  
- `Editor` – akses baca/tulis.  
- `Author` – dapat membuat dan membaca, tetapi tidak dapat menghapus.  
- `Owner` – kontrol penuh, termasuk perubahan izin.  

**Pro tip:** Gunakan tingkat hak istimewa paling rendah yang memenuhi kebutuhan bisnis untuk menjaga data kalender Anda tetap aman.

## Aplikasi praktis
Skenario dunia nyata di mana **kelola berbagi kalender** bersinar:
1. **Rapat korporat** – Membiarkan anggota tim melihat jadwal rapat tanpa memberikan hak penuh kotak surat.  
2. **Manajemen proyek** – Pemimpin proyek dapat memantau jadwal sementara pengembang tetap mengontrol kalender mereka sendiri.  
3. **Perencanaan acara** – Vendor menerima **email berbagi kalender** untuk mengoordinasikan logistik tanpa mengungkap detail internal.

## Pertimbangan kinerja
- **Manajemen memori:** Buang objek `MailMessage` besar dengan cepat dalam aplikasi bervolume tinggi.  
- **Penanganan pengecualian:** Bungkus panggilan jaringan dalam blok try‑catch untuk menangani gangguan konektivitas dengan elegan.  
- **Pembaruan perpustakaan:** Aspose.Email for Java mendukung lebih dari 50 protokol dan dapat memproses kalender dengan hingga 10.000 item tanpa memuat seluruh file ke memori, jadi pastikan perpustakaan selalu terbaru untuk mendapatkan peningkatan kinerja dan perbaikan bug.

## Masalah umum dan solusi
| Masalah | Penyebab kemungkinan | Solusi |
|-------|--------------|----------|
| Undangan tidak diterima | Filter spam atau alamat email yang salah | Verifikasi alamat penerima dan tambahkan domain pengirim ke daftar pengirim aman |
| Izin tidak diterapkan | Menggunakan `ExchangeDelegateFolderPermissionLevel` yang salah | Periksa kembali bahwa tingkat izin sesuai dengan akses yang diperlukan |
| Pengecualian runtime pada `createCalendarSharingInvitationMessage` | Lisensi hilang atau perpustakaan usang | Pastikan lisensi yang valid dimuat dan Anda menggunakan versi Aspose.Email terbaru |

## Pertanyaan yang sering diajukan
**Q: Apa kegunaan Aspose.Email untuk Java?**  
A: Ini adalah perpustakaan komprehensif untuk menangani email, kalender, dan kontak dalam aplikasi Java, mendukung Outlook, Exchange, dan protokol lainnya.

**Q: Bagaimana cara menyiapkan lingkungan saya untuk menggunakan Aspose.Email?**  
A: Instal JDK 16+, Maven, tambahkan dependensi Aspose.Email ke `pom.xml`, dan dapatkan lisensi (percobaan atau penuh).

**Q: Bisakah saya menggunakan kode ini dengan versi lain dari Exchange Online?**  
A: Ya, tetapi pastikan URL layanan dan tingkat izin sesuai dengan konfigurasi server Anda.

**Q: Apa yang harus saya lakukan jika undangan berbagi kalender gagal dikirim?**  
A: Periksa konektivitas jaringan, kredensial, dan pastikan pengguna delegasi memiliki izin yang valid. Tinjau detail pengecualian untuk petunjuk.

**Q: Apakah memungkinkan menambahkan izin tambahan seperti mengedit atau akses penuh?**  
A: Tentu – ganti `ExchangeDelegateFolderPermissionLevel.Reviewer` dengan `Editor`, `Author`, atau `Owner` sesuai kebutuhan.

## Kesimpulan
Anda kini memiliki solusi lengkap dari ujung ke ujung untuk **membuat undangan berbagi kalender** dengan Aspose.Email untuk Java. Dengan menginisialisasi klien EWS, **membuat akses delegasi**, **mengatur izin delegasi**, dan mengirim **email berbagi kalender**, Anda dapat mengotomatiskan kolaborasi di seluruh organisasi Anda.

**Langkah selanjutnya**
- Bereksperimen dengan tingkat izin lain (Editor, Owner).  
- Integrasikan logika ini ke dalam sistem penjadwalan atau HR yang ada.  
- Jelajahi fitur Aspose.Email tambahan seperti acara berulang atau permintaan rapat.

---

**Terakhir diperbarui:** 2026-09-17  
**Diuji dengan:** Aspose.Email for Java 25.4 (klasifikasi JDK 16)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Item Kalender Java Menggunakan Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java Filter Janjian Exchange Berdasarkan Tanggal](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Buat Kalender Exchange Java dengan Aspose.Email – Panduan Lengkap](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}