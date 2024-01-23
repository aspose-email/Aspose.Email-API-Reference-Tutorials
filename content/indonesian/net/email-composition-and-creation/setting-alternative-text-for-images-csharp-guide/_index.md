---
title: Mengatur Teks Alternatif untuk Gambar - Panduan C#
linktitle: Mengatur Teks Alternatif untuk Gambar - Panduan C#
second_title: API Pemrosesan Email Aspose.Email .NET
description: Pelajari cara mengatur teks alternatif untuk gambar dalam email menggunakan Aspose.Email untuk .NET. Pastikan aksesibilitas dengan teks alternatif yang jelas. Dokumentasi dan kode disertakan.
type: docs
weight: 15
url: /id/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Panduan ini akan memandu Anda melalui proses pengaturan teks alternatif untuk gambar dalam email menggunakan Aspose.Email untuk .NET. Teks alternatif, juga dikenal sebagai "teks alternatif", digunakan untuk memberikan deskripsi tekstual suatu gambar jika gambar tidak dapat ditampilkan. Aspose.Email untuk .NET adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan email dan lampiran dalam berbagai format. Dalam panduan ini, kami akan fokus pada pengaturan teks alternatif untuk gambar dalam pesan email menggunakan C#.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio atau lingkungan pengembangan C# apa pun yang kompatibel diinstal.
2. Aspose.Email untuk perpustakaan .NET. Anda dapat menggunakan Manajer Paket NuGet di Visual Studio.

## Langkah 1: Buat Proyek Baru

1. Luncurkan Visual Studio dan buat proyek aplikasi konsol C# baru.

## Langkah 2: Instal Aspose.Email melalui NuGet

1. Klik kanan proyek Anda di Solution Explorer dan pilih "Kelola Paket NuGet."
2. Cari "Aspose.Email" dan instal paket versi terbaru.

## Langkah 3: Tambahkan Menggunakan Pernyataan

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## Langkah 4: Muat dan Ubah Pesan Email

1.  Muat pesan email menggunakan`MailMessage` kelas:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Muat konten HTML pesan email:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Langkah 5: Tambahkan Tampilan Alternatif untuk Teks Alternatif ke Gambar

Tambahkan htmlview untuk Teks Alternatif ke Gambar sebagai AlternateView ke dalam pesan. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Langkah 6: Simpan dan Kirim Email

1. Simpan pesan yang diubah ke file atau kirimkan menggunakan metode yang Anda inginkan:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Kesimpulan

Dalam panduan ini, Anda mempelajari cara mengatur teks alternatif untuk gambar dalam pesan email menggunakan Aspose.Email untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memastikan bahwa konten email Anda tetap dapat diakses dan informatif meskipun gambar tidak dapat ditampilkan.

## Pertanyaan Umum

## Bagaimana cara mengunduh perpustakaan Aspose.Email?

Anda dapat mengunduh pustaka Aspose.Email dari Aspose Releases atau menginstalnya melalui NuGet Package Manager di Visual Studio.

### Bagaimana cara menambahkan gambar sebagai sumber tertaut dalam email?

Untuk menambahkan gambar sebagai sumber tertaut dalam email, Anda dapat menggunakan`LinkedResource` kelas. Tetapkan ID konten ke sumber daya tertaut, lalu referensikan ID konten ini di isi HTML menggunakan`cid:` skema. Untuk informasi selengkapnya, lihat[Dokumentasi LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Email untuk .NET?

 Anda dapat menemukan dokumentasi, tutorial, dan contoh lebih detail tentang cara bekerja dengan Aspose.Email untuk .NET di[Referensi API](https://reference.aspose.com/email/net/).