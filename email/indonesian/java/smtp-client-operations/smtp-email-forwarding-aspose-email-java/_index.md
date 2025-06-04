---
"date": "2025-05-29"
"description": "Pelajari cara mengonfigurasi klien SMTP dengan Aspose.Email untuk Java dan meneruskan email secara efisien. Ideal untuk pengembang dalam aplikasi perusahaan."
"title": "Penerusan Email SMTP Menggunakan Aspose.Email untuk Java; Panduan Lengkap"
"url": "/id/java/smtp-client-operations/smtp-email-forwarding-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Penerusan Email SMTP Menggunakan Aspose.Email untuk Java: Panduan Lengkap

Di era digital, mengelola email secara terprogram sangat penting bagi pengembang yang bekerja pada sistem komunikasi perusahaan atau pelanggan. Panduan ini menyediakan panduan terperinci tentang cara menyiapkan klien SMTP dengan Aspose.Email untuk Java guna meneruskan email secara efisien tanpa menggunakan `MailMessage`Mari kita jelajahi bagaimana alat hebat ini dapat memenuhi kebutuhan otomatisasi email Anda.

## Apa yang Akan Anda Pelajari:
- Mengonfigurasi Klien SMTP dengan Aspose.Email untuk Java
- Mengelola Penerima Email Menggunakan Koleksi
- Meneruskan Email Langsung dari Aliran File

**Prasyarat:** Sebelum memulai, pastikan Anda telah menyiapkan pengaturan berikut untuk mengikuti tutorial ini secara efektif.

### Prasyarat
Untuk menyelesaikan panduan ini dengan sukses, pastikan Anda memiliki:

- **Perpustakaan dan Ketergantungan:**
  - Aspose.Email untuk Java versi 25.4 atau yang lebih baru.
  
- **Pengaturan Lingkungan:**
  - JDK (Java Development Kit) yang kompatibel, sebaiknya JDK 16 seperti yang ditetapkan oleh pengklasifikasi dalam dependensi Maven kita.
- **Prasyarat Pengetahuan:**
  - Pemahaman dasar tentang protokol SMTP
  - Keakraban dengan pemrograman Java

## Menyiapkan Aspose.Email untuk Java

Mengintegrasikan Aspose.Email ke dalam proyek Anda mudah dilakukan menggunakan Maven. Tambahkan dependensi berikut ke `pom.xml` mengajukan:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Mendapatkan Lisensi
Aspose.Email menawarkan lisensi uji coba gratis untuk menguji kemampuan penuhnya tanpa batasan. Berikut cara mendapatkannya:

1. **Uji Coba Gratis:** Mengunjungi [Halaman Uji Coba Gratis Aspose](https://releases.aspose.com/email/java/) untuk mengunduh dan memulai dengan versi evaluasi.
2. **Lisensi Sementara:** Untuk pengujian yang diperpanjang, mintalah lisensi sementara melalui [Halaman Permintaan Lisensi](https://purchase.aspose.com/temporary-license/).
3. **Pembelian:** Jika Anda menemukan Aspose.Email bermanfaat untuk proyek Anda, pertimbangkan untuk membeli lisensi penuh di [Halaman Pembelian Aspose](https://purchase.aspose.com/buy).

### Inisialisasi dan Pengaturan Dasar

Setelah Aspose.Email disertakan dalam proyek Anda, inisialisasikan komponen yang diperlukan:

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com"; // Alamat server SMTP Anda
String username = "username";    // Nama pengguna untuk otentikasi
int smtpPort = 587;              // Nomor port, biasanya 587 untuk TLS/STARTTLS
String password = "password";    // Kata sandi untuk otentikasi

// Buat contoh SmtpClient dengan kredensial yang ditentukan.
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

## Panduan Implementasi

### Konfigurasi Klien SMTP
Bagian ini memandu Anda melalui konfigurasi klien SMTP untuk mengirim email. Dengan menyiapkan `SmtpClient`, Anda membuat koneksi dengan server email Anda menggunakan kredensial dan opsi keamanan yang ditentukan.

#### Ringkasan
Konfigurasi ini melibatkan penentuan host SMTP, port, nama pengguna, kata sandi, dan opsi keamanan—biasanya SSLExplicit untuk koneksi aman.

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com";
String username = "username";
int smtpPort = 587;
String password = "password";

// Inisialisasi SmtpClient dengan kredensial yang ditentukan.
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

### Koleksi Penerima Email
Mengelola daftar penerima disederhanakan menggunakan `MailAddressCollection`, yang memungkinkan Anda menambahkan beberapa alamat email dengan mudah.

#### Ringkasan
Koleksi ini memungkinkan penyimpanan dan pengelolaan email penerima untuk operasi penerusan atau pengiriman.

```java
import com.aspose.email.MailAddressCollection;

// Buat instance MailAddressCollection baru.
MailAddressCollection recipients = new MailAddressCollection();

// Tambahkan beberapa penerima ke koleksi.
recipients.add("to1@domain.com");
recipients.add("to2@domain.com");
```

### Penerusan Email tanpa Menggunakan MailMessage
Fitur canggih ini memungkinkan Anda meneruskan file email secara langsung menggunakan `FileInputStream` dan `SmtpClient`.

#### Ringkasan
Alih-alih membuat yang baru `MailMessage`, metode ini menggunakan file EML yang ada, membuatnya efisien untuk penerusan massal.

```java
import java.io.FileInputStream;
import java.io.IOException;

String fileName = "YOUR_DOCUMENT_DIRECTORY/test.eml"; // Jalur ke file EML Anda

// Buka FileInputStream untuk berkas email.
FileInputStream fos = new FileInputStream(fileName);

try {
    // Teruskan email menggunakan instance SmtpClient dan koleksi penerima.
    client.forward("Sender@domain.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}