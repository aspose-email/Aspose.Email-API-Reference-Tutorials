---
date: 2025-12-01
description: Pelajari cara mengirim email dengan gambar tersemat menggunakan Aspose.Email
  untuk Java. Panduan ini menunjukkan cara menyematkan gambar dalam email dan membuat
  email HTML Java dengan lampiran inline.
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Cara Mengirim Email dengan Gambar Tersemat Menggunakan Aspose.Email untuk Java
url: /id/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengirim Email dengan Gambar Tersemat Menggunakan Aspose.Email untuk Java

## Jawaban Cepat
- **Apa kelas utama untuk gambar inline?** `LinkedResource`
- **Metode mana yang merujuk gambar dalam HTML?** Gunakan `cid:yourContentId` dalam tag `<img>`
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi
- **Bisakah saya mengirim email melalui server SMTP mana pun?** Ya, cukup konfigurasikan `SmtpClient` dengan detail server Anda
- **Apakah pendekatan ini kompatibel dengan semua klien email utama?** Sebagian besar klien modern (Outlook, Gmail, Thunderbird) mendukung gambar CID‑embedded

## Apa Itu Lampiran Inline (Gambar Tersemat)?

Lampiran inline—kadang disebut gambar tersemat atau gambar CID—adalah file yang berada di dalam badan MIME sebuah email. Mereka dirujuk dari bagian HTML pesan dengan **Content‑ID** (CID). Teknik ini memungkinkan Anda **menyematkan gambar dalam email** sehingga muncul tepat di tempat Anda menempatkan tag `<img>`, tanpa muncul sebagai lampiran terpisah yang dapat diunduh.

## Mengapa Menggunakan Gambar Tersemat dalam Email Java Anda?

- **Tampilan profesional:** Logo, spanduk, dan gambar produk ditampilkan secara instan.  
- **Keterlibatan lebih baik:** Penerima lebih cenderung membaca email yang tampak lengkap.  
- **Tidak ada klik tambahan:** Pengguna tidak perlu mengunduh lampiran untuk melihat gambar.  
- **Branding konsisten:** Aset merek Anda tetap sejalan dengan konten pesan.

## Prasyarat

- Perpustakaan Aspose.Email untuk Java (unduh dari [dokumentasi Aspose.Email untuk Java](https://reference.aspose.com/email/java/))
- Lingkungan pengembangan Java 8+
- Akses ke server SMTP untuk mengirim email
- File gambar yang ingin Anda sematkan (mis., `logo.png`)

## Panduan Langkah‑demi‑Langkah

### Langkah 1: Buat Pesan Email HTML Dasar

Pertama, siapkan `MailMessage` sederhana dengan badan HTML. Ini akan menjadi kanvas tempat kita nanti menyematkan gambar.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Langkah 2: Tambahkan Gambar Inline Menggunakan `LinkedResource`

Sekarang kita menyematkan gambar. Kelas `LinkedResource` mewakili lampiran inline. Tetapkan **Content‑ID** yang unik dan rujuk dalam badan HTML dengan `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Pro tip:** Jaga `ContentId` tetap sederhana dan unik dalam pesan untuk menghindari konflik.

### Langkah 3: Kirim Email melalui `SmtpClient`

Konfigurasikan pengaturan SMTP Anda dan kirim pesan. Gambar tersemat akan dikirim bersama email, sehingga penerima melihatnya secara langsung.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Langkah 4: Terima dan Ekstrak Gambar Inline (Opsional)

Jika Anda perlu memproses pesan masuk yang berisi gambar tersemat, Anda dapat memuat file `.eml` dan mengakses `LinkedResources`‑nya.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Masalah Umum & Cara Memperbaikinya

| Masalah | Mengapa Terjadi | Solusi |
|---------|-----------------|--------|
| **Content‑ID mismatch** | Referensi `cid:` dalam HTML tidak cocok dengan `ContentId` yang ditetapkan pada `LinkedResource`. | Pastikan stringnya identik (`image001` vs `cid:image001`). |
| **File not found** | Jalur ke gambar tidak tepat atau file tidak ada. | Verifikasi jalur absolut/relatif dan pastikan file tersebut ada di server. |
| **SMTP authentication failure** | Kredensial atau pengaturan server salah. | Periksa kembali host, port, nama pengguna, dan kata sandi. Aktifkan TLS/SSL jika diperlukan. |
| **Image not displayed in some clients** | Beberapa klien memblokir sumber eksternal. | Gunakan gambar CID‑embedded (seperti contoh) alih‑alih URL eksternal. |

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara mengunduh Aspose.Email untuk Java?**  
A: Anda dapat mengunduh Aspose.Email untuk Java dari [dokumentasi](https://reference.aspose.com/email/java/). Ikuti petunjuk instalasi untuk menyiapkannya dalam proyek Anda.

**Q: Bisakah saya menggunakan Aspose.Email untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, Aspose.Email terintegrasi dengan mulus bersama perpustakaan Java lain, memungkinkan Anda menggabungkan pemrosesan email dengan pembuatan PDF, OCR, atau akses basis data.

**Q: Format file apa yang didukung untuk lampiran inline?**  
A: Format gambar umum seperti PNG, JPEG, GIF, serta tipe dokumen lain (mis., SVG) didukung sebagai sumber inline.

**Q: Bagaimana cara menangani lampiran inline dalam email HTML?**  
A: Gunakan kelas `LinkedResource` untuk menetapkan `ContentId`, tambahkan ke `message.getLinkedResources()`, dan rujuk dalam badan HTML dengan `<img src='cid:yourContentId'>`.

**Q: Apakah Aspose.Email untuk Java kompatibel dengan berbagai server email?**  
A: Ya, ia bekerja dengan server SMTP/IMAP/POP3 apa pun. Cukup berikan alamat server, port, dan detail autentikasi yang benar.

---

**Terakhir Diperbarui:** 2025-12-01  
**Diuji Dengan:** Aspose.Email untuk Java 24.12 (versi terbaru saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}