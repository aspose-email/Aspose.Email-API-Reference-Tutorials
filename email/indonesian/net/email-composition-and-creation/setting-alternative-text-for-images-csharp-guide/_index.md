---
"description": "Pelajari cara mengatur teks alternatif untuk gambar dalam email menggunakan Aspose.Email for .NET. Pastikan aksesibilitas dengan teks alt yang jelas. Dokumentasi dan kode disertakan."
"linktitle": "Mengatur Teks Alternatif untuk Gambar - Panduan C#"
"second_title": "API Pemrosesan Email Aspose.Email .NET"
"title": "Mengatur Teks Alternatif untuk Gambar - Panduan C#"
"url": "/id/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Teks Alternatif untuk Gambar - Panduan C#


Panduan ini akan memandu Anda melalui proses pengaturan teks alternatif untuk gambar dalam email menggunakan Aspose.Email untuk .NET. Teks alternatif, juga dikenal sebagai "teks alt," digunakan untuk memberikan deskripsi tekstual dari suatu gambar jika gambar tersebut tidak dapat ditampilkan. Aspose.Email untuk .NET adalah pustaka canggih yang memungkinkan Anda bekerja dengan email dan lampiran dalam berbagai format. Dalam panduan ini, kami akan fokus pada pengaturan teks alternatif untuk gambar dalam pesan email menggunakan C#.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio atau lingkungan pengembangan C# yang kompatibel terpasang.
2. Aspose.Email untuk pustaka .NET. Anda dapat menggunakan NuGet Package Manager di Visual Studio.

## Langkah 1: Buat Proyek Baru

1. Luncurkan Visual Studio dan buat proyek aplikasi konsol C# baru.

## Langkah 2: Instal Aspose.Email melalui NuGet

1. Klik kanan pada proyek Anda di Solution Explorer dan pilih "Kelola Paket NuGet."
2. Cari "Aspose.Email" dan instal versi terbaru paket tersebut.

## Langkah 3: Tambahkan Pernyataan Menggunakan

```csharp

using Aspose.Email.Mime;
```

## Langkah 4: Memuat dan Memodifikasi Pesan Email

1. Muat pesan email menggunakan `MailMessage` kelas:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Muat konten HTML dari pesan email:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Langkah 5: Tambahkan AlternativeView untuk Teks Alternatif ke Gambar

Tambahkan htmlview untuk Teks Alternatif ke Gambar sebagai AlternateView ke dalam pesan. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Langkah 6: Simpan dan Kirim Email

1. Simpan pesan yang dimodifikasi ke file atau kirim menggunakan metode yang Anda inginkan:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Kesimpulan

Dalam panduan ini, Anda mempelajari cara mengatur teks alternatif untuk gambar dalam pesan email menggunakan Aspose.Email untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memastikan bahwa konten email Anda tetap dapat diakses dan informatif meskipun gambar tidak dapat ditampilkan.

## Tanya Jawab Umum

## Bagaimana cara mengunduh pustaka Aspose.Email?

Anda dapat mengunduh pustaka Aspose.Email dari Rilis Aspose atau menginstalnya melalui NuGet Package Manager di Visual Studio.

### Bagaimana cara menambahkan gambar sebagai sumber daya tertaut dalam email?

Untuk menambahkan gambar sebagai sumber daya tertaut dalam email, Anda dapat menggunakan `LinkedResource` kelas. Tetapkan ID konten ke sumber daya yang ditautkan, lalu rujuk ID konten ini di badan HTML menggunakan `cid:` skema. Untuk informasi lebih rinci, lihat [Dokumentasi LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Email untuk .NET?

Anda dapat menemukan dokumentasi, tutorial, dan contoh yang lebih rinci tentang bekerja dengan Aspose.Email untuk .NET di [Referensi API](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}