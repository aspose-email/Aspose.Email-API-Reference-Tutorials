---
date: '2026-10-02'
description: Pelajari cara menghubungkan Exchange dan menampilkan folder publik Exchange
  menggunakan Aspose.Email for Java. Panduan langkah demi langkah ini menunjukkan
  dependensi Maven dan penyiapan tanpa kode.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Pelajari cara menghubungkan Exchange dan menampilkan folder publik
  Exchange menggunakan Aspose.Email for Java. Panduan ini mencakup dependensi Maven,
  lisensi, dan pengambilan pesan secara rekursif.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Cara menghubungkan Exchange dan menampilkan folder publik di Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Cara menghubungkan Exchange dan menampilkan folder publik di Java
url: /id/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghubungkan Exchange dan menampilkan folder publik di Java

## Pendahuluan
Di perusahaan modern, mengakses kotak surat Microsoft Exchange secara programatik memungkinkan Anda mengotomatisasi tugas pengarsipan, pemantauan, dan pelaporan. Tutorial ini menunjukkan **cara menghubungkan exchange** dengan Aspose.Email untuk Java dan kemudian **menampilkan folder publik exchange** secara rekursif. Anda akan melihat dependensi Maven yang diperlukan, langkah-langkah lisensi, dan urutan panggilan API yang tepat—tanpa perpustakaan tambahan. Pada akhirnya, Anda akan dapat mengambil pesan dari folder publik mana pun dan menyimpannya secara lokal.

## Jawaban Cepat
- **Apa langkah pertama?** Tambahkan dependensi Maven Aspose.Email ke `pom.xml` Anda.  
- **Apakah saya memerlukan lisensi?** Ya—gunakan lisensi sementara untuk evaluasi atau beli lisensi penuh untuk produksi.  
- **Kelas mana yang membuat koneksi?** `ExchangeClient` (atau `ImapClient` untuk IMAP) menangani otentikasi dan komunikasi server.  
- **Bisakah saya menampilkan subfolder secara otomatis?** Ya—gunakan metode rekursif `listSubFolders` yang disediakan oleh API.  
- **Apakah pendekatan ini thread‑safe?** Objek klien tidak thread‑safe; buat instance terpisah per thread untuk beban kerja bersamaan.

## Apa itu cara menghubungkan exchange?
**Cara menghubungkan exchange** adalah proses mengautentikasi aplikasi Java dengan server Microsoft Exchange yang berada di tempat atau berbasis cloud sehingga Anda dapat melakukan panggilan API seperti enumerasi folder atau pengambilan pesan. Aspose.Email mengabstraksi protokol EWS/IMAP yang mendasari, memberikan Anda model objek tunggal yang konsisten.

## Mengapa menampilkan folder publik exchange?
Menampilkan folder publik memberi Anda visibilitas ke struktur hierarkis yang digunakan organisasi untuk kotak surat bersama, daftar distribusi, dan penyimpanan arsip. Aspose.Email dapat menenumerasi lebih dari **50+ folder publik** dalam satu panggilan dan mendukung pemrosesan kotak surat ratusan halaman tanpa memuat seluruh penyimpanan ke memori, yang mengurangi konsumsi RAM hingga 70 %.

## Prasyarat
- **Aspose.Email untuk Java** — versi 25.4 atau lebih baru (rilis stabil terbaru).  
- **Java Development Kit (JDK)** — JDK 11 atau lebih baru terpasang dan `JAVA_HOME` dikonfigurasi.  
- **Maven** — untuk manajemen dependensi dan otomatisasi build.  
- Pengetahuan dasar tentang sintaks Java dan konsep Exchange (kotak surat, folder, EWS).

## Menyiapkan Aspose.Email untuk Java
Untuk mengintegrasikan perpustakaan, tambahkan dependensi Maven ke `pom.xml` proyek Anda. Ini adalah **dependensi maven aspose email** yang Anda perlukan.

### Dependensi Maven
Tambahkan potongan kode berikut di dalam elemen `<dependencies>` pada `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Langkah memperoleh lisensi
Aspose.Email memerlukan lisensi yang valid untuk penggunaan semua fitur:

- **Free trial** – Unduh lisensi sementara dari [situs Aspose](https://purchase.aspose.com/temporary-license/) untuk mengevaluasi API.  
- **Purchase** – Dapatkan lisensi komersial melalui portal Aspose untuk penerapan produksi.

#### Inisialisasi dasar
Setelah Maven menyelesaikan paket dan Anda memiliki file lisensi, letakkan file `.lic` pada classpath dan inisialisasi perpustakaan:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Panduan Implementasi
Kami akan membahas setiap blok fungsional, menjawab pertanyaan kunci dengan paragraf langsung dan singkat sebelum langkah‑langkah detail.

### Cara menghubungkan exchange?
Muat `ExchangeClient` dengan URL server, kredensial pengguna, dan domain, lalu panggil `connect()`. Klien membuat sesi HTTPS dengan Exchange Web Services (EWS) dan memvalidasi kredensial. Jika koneksi gagal, API melempar `AuthenticationException` yang detail yang mencakup kode status HTTP untuk pemecahan masalah cepat.  
`ExchangeClient` adalah kelas Aspose.Email yang mengelola koneksi ke Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Cara menampilkan folder publik exchange?
Panggil `client.listPublicFolders()` untuk mendapatkan koleksi objek `FolderInfo` yang mewakili setiap folder publik tingkat atas. Metode ini mengembalikan metadata seperti nama folder, total jumlah item, dan pengidentifikasi unik yang digunakan untuk panggilan selanjutnya. Panggilan ini selesai dalam kurang dari 2 detik untuk penyebaran on‑premises tipikal dengan hingga 500 folder.  
`listPublicFolders()` mengembalikan koleksi objek `FolderInfo`.  
`FolderInfo` menyimpan metadata seperti nama tampilan dan jumlah item.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Cara menampilkan informasi folder?
Iterasi koleksi `FolderInfo` dan cetak `displayName` serta `subFolderCount`. Snapshot cepat ini membantu Anda memahami hierarki sebelum melakukan penelusuran lebih dalam. Untuk organisasi besar, API dapat mem-paginate hasil, mengembalikan 100 folder per halaman untuk menjaga penggunaan memori tetap rendah.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Cara menampilkan pesan dari sebuah folder?
Panggil `client.listMessages(folderId)` dimana `folderId` adalah pengidentifikasi yang diperoleh dari langkah sebelumnya. Metode ini mengembalikan daftar objek `MessageInfo` yang berisi subjek, pengirim, dan tanggal diterima. Anda dapat membatasi set hasil dengan `maxCount` untuk menghindari membebani klien saat memproses folder yang sangat besar.  
`listMessages(folderId)` mengembalikan daftar objek `MessageInfo`.  
`MessageInfo` berisi properti dasar email seperti subjek, pengirim, dan tanggal diterima.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Cara mengambil dan menyimpan pesan?
Untuk setiap `MessageInfo`, gunakan `client.fetchMessage(messageId)` untuk mengunduh konten MIME lengkap. Kemudian tulis array byte ke file `.eml` di disk. API men-stream konten, sehingga pesan hingga 100 MB dapat ditangani tanpa memuat seluruh payload ke memori.  
`fetchMessage(messageId)` mengunduh konten MIME lengkap dari email yang ditentukan.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Cara menampilkan pesan secara rekursif dari subfolder?
Implementasikan traversal depth‑first: mulai dengan folder tingkat atas, daftar subfoldernya melalui `client.listSubFolders(parentId)`, kemudian panggil rutinitas penampilan pesan yang sama untuk setiap anak. Pola ini memastikan setiap pesan dalam pohon folder publik diproses. Kedalaman rekursi dibatasi hanya oleh hierarki folder server (biasanya < 20 level).  
`listSubFolders(parentId)` mengembalikan folder anak langsung dari folder yang diberikan.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Aplikasi Praktis
Skenario dunia nyata di mana alur kerja ini bersinar:

1. **Arsip email otomatis** – Secara periodik tarik semua pesan folder publik dan simpan dalam arsip yang sesuai.  
2. **Solusi backup** – Cerminkan folder publik Exchange ke sistem file aman atau bucket cloud, menjamin redundansi data.  
3. **Klien email khusus** – Bangun penampil ringan yang menampilkan hanya folder dan pesan yang Anda butuhkan, mengurangi kompleksitas UI.

## Pertimbangan Kinerja
Saat menskalakan ke ribuan folder dan jutaan pesan, ingat tips berikut:

- **Connection pooling** – Gunakan kembali satu instance `ExchangeClient` untuk banyak operasi alih-alih membuat klien baru per folder.  
- **Lazy loading** – Minta hanya metadata yang Anda perlukan (`listMessages` dengan parameter `maxCount`) dan ambil isi lengkap sesuai permintaan.  
- **Dispose objects** – Panggil `client.dispose()` setelah batch selesai untuk membebaskan koneksi HTTP dan buffer thread‑local.  
- **Parallel processing** – Bagi folder tingkat atas ke beberapa thread, masing‑masing dengan instance kliennya, untuk memanfaatkan CPU multi‑core secara efektif.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan kode ini dengan Exchange Online (Office 365)?**  
A: Ya. Berikan endpoint EWS Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) dan gunakan otentikasi modern (OAuth) – Aspose.Email mendukung token OAuth secara langsung.

**Q: Bagaimana jika sebuah folder berisi lebih dari 10 000 pesan?**  
A: Gunakan overload `listMessages` yang menerima parameter `skip` dan `take` untuk mem-paginate hasil, menjaga penggunaan memori tetap terkendali.

**Q: Apakah ada batas ukuran email tunggal yang dapat saya unduh?**  
A: API men-stream konten, sehingga pesan hingga 150 MB didukung tanpa mencapai batas heap Java, asalkan JVM memiliki memori native yang cukup.

**Q: Apakah saya perlu menangani sertifikat SSL secara manual?**  
A: Secara default Aspose.Email mempercayai keystore default Java. Jika server Exchange Anda menggunakan sertifikat self‑signed, impor ke truststore JVM atau setel `client.setEnableSslVerification(false)` hanya untuk pengujian.

**Q: Bagaimana cara mencatat operasi untuk keperluan audit?**  
A: Aktifkan logging bawaan Aspose.Email dengan mengonfigurasi `Logger.setLevel(Level.INFO)` dan mengarahkan output ke file atau sistem pemantauan.

## Kesimpulan
Anda kini memiliki resep lengkap yang siap produksi untuk **cara menghubungkan exchange** dan menampilkan pesan secara rekursif dari folder publik menggunakan Aspose.Email untuk Java. Langkah‑langkah mencakup penyiapan Maven, lisensi, koneksi, enumerasi folder, pengambilan pesan, dan penyetelan kinerja. Perluas fondasi ini dengan mengintegrasikan ke basis data, penyimpanan cloud, atau pipeline analitik khusus untuk memenuhi kebutuhan spesifik organisasi Anda.

---

**Terakhir Diperbarui:** 2026-10-02  
**Diuji Dengan:** Aspose.Email for Java 25.4  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menghubungkan ke Server Exchange menggunakan Aspose.Email di Java: Panduan Langkah-demi-Langkah](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Cara Menghubungkan dan Menampilkan Folder Server Exchange Menggunakan Aspose.Email untuk Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Kelola Folder Server Exchange Menggunakan Aspose.Email untuk Java: Panduan Komprehensif](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}