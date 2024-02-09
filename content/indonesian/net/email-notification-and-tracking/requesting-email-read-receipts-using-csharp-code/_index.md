---
title: Meminta Tanda Terima Email Telah Dibaca menggunakan Kode C#
linktitle: Meminta Tanda Terima Email Telah Dibaca menggunakan Kode C#
second_title: API Pemrosesan Email Aspose.Email .NET
description: Pelajari cara menggunakan kode C# untuk meminta tanda terima email telah dibaca menggunakan Aspose.Email untuk .NET, sehingga meningkatkan pelacakan komunikasi.
type: docs
weight: 11
url: /id/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

Di era digital saat ini, komunikasi melalui email telah menjadi bagian integral dari kehidupan pribadi dan profesional kita. Seringkali, saat mengirim email penting, kita ingin memastikan bahwa penerima telah membaca dan mengetahui pesan kita. Di sinilah tanda terima email telah dibaca berperan. Dalam tutorial langkah demi langkah ini, kami akan memandu Anda melalui proses meminta tanda terima email telah dibaca menggunakan C# dengan Aspose.Email untuk .NET.

## Pengantar Tanda Terima Email Telah Dibaca

Tanda terima email telah dibaca, juga dikenal sebagai pelacakan email atau tanda terima pengembalian, memungkinkan Anda menerima pemberitahuan saat penerima membuka dan membaca email Anda. Ini adalah fitur yang berharga, terutama dalam komunikasi bisnis, karena memberikan konfirmasi pengiriman pesan dan keterlibatan.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Visual Studio diinstal pada sistem Anda.
- Pustaka Aspose.Email untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 1: Membuat Instans MailMessage

 Langkah pertama dalam mengimplementasikan tanda terima email telah dibaca adalah membuat sebuah instance dari`MailMessage` kelas. Kelas ini mewakili pesan email dan memungkinkan Anda mengatur berbagai properti email.

```csharp
MailMessage message = new MailMessage();
```

## Langkah 2: Menentukan Detail Pesan

Sekarang, mari tentukan detail pesan email, termasuk pengirim, penerima, isi HTML, dan opsi pemberitahuan pengiriman.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Langkah 3: Membuat Instans SmtpClient

 Untuk mengirim email, kita perlu membuat sebuah instance dari`SmtpClient` kelas, yang bertanggung jawab untuk mengirim pesan.

```csharp
SmtpClient client = new SmtpClient();
```

## Langkah 4: Mengonfigurasi Pengaturan SMTP

Konfigurasikan pengaturan server SMTP Anda dengan menentukan server host, nama pengguna, kata sandi, dan nomor port.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Langkah 5: Mengirim Email

 Terakhir, gunakan`client.Send` metode untuk mengirim pesan email. Jika pesan berhasil terkirim, maka akan muncul notifikasi “Pesan Terkirim”.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

Dengan lima langkah sederhana ini, Anda dapat meminta tanda terima email telah dibaca saat mengirim email menggunakan C# dan Aspose.Email untuk .NET. Fitur ini menambahkan lapisan jaminan pada komunikasi email Anda, memastikan bahwa Anda mengetahui kapan pesan penting Anda dibaca.

## Kode Sumber Lengkap
```csharp
// Buat Instance kelas MailMessage
MailMessage message = new MailMessage();

// Tentukan bidang Dari, Ke, HtmlBody, DeliveryNotificationOptions
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Buat instance Kelas SmtpClient
SmtpClient client = new SmtpClient();

// Tentukan server host surat Anda, Nama Pengguna, Kata Sandi dan No Port
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send akan mengirimkan pesan ini
	client.Send(message);
	// Tampilkan 'Pesan Terkirim', hanya jika pesan berhasil terkirim
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara meminta tanda terima email telah dibaca menggunakan C# dengan Aspose.Email untuk .NET. Pelacakan email adalah alat yang ampuh untuk memastikan pesan Anda terkirim dan dibaca oleh penerima yang dituju, terutama di lingkungan profesional. Dengan mengikuti langkah-langkah yang diuraikan di sini, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi email Anda.

## Pertanyaan yang Sering Diajukan (FAQ)

1. ### Apa tujuan dari tanda terima email telah dibaca?
   Tanda terima telah dibaca email memberikan konfirmasi bahwa email telah dibuka dan dibaca oleh penerima. Mereka sering digunakan untuk melacak pesan penting atau sensitif terhadap waktu.

2. ### Bisakah tanda terima email telah dibaca dinonaktifkan oleh penerima?
   Ya, klien email sering kali mengizinkan pengguna untuk menonaktifkan pengiriman tanda terima telah dibaca. Oleh karena itu, tidak ada jaminan Anda akan selalu menerimanya.

3. ### Apakah tanda terima email telah dibaca merupakan fitur standar di semua klien email?
   Tidak, tanda terima email telah dibaca tidak didukung secara universal. Berfungsi atau tidaknya bergantung pada klien email dan pengaturan penerima.

4. ### Apakah mungkin melacak kapan email dibuka di perangkat seluler?
   Pelacakan email biasanya didasarkan pada klien dan pengaturan email penerima, sehingga mungkin berfungsi atau tidak pada perangkat seluler, bergantung pada berbagai faktor.

5. ### Apakah ada pertimbangan privasi saat menggunakan tanda terima email telah dibaca?
   Ya, ada masalah privasi terkait pelacakan email. Beberapa penerima mungkin menganggapnya invasif, jadi penting untuk menggunakan fitur ini secara bertanggung jawab dan menghormati preferensi privasi.