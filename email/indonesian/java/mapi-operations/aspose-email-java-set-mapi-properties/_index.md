---
"date": "2025-05-29"
"description": "Pelajari cara mengelola beberapa properti secara efisien dalam pesan MAPI menggunakan Aspose.Email untuk Java. Panduan ini mencakup pengaturan tipe float, double, long, dan lainnya."
"title": "Mengatur Beberapa Properti MAPI di Java dengan Aspose.Email&#58; Panduan Lengkap"
"url": "/id/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mengatur Beberapa Properti MAPI di Java dengan Aspose.Email: Panduan Lengkap

## Perkenalan

Mengelola properti pesan MAPI secara efektif sangat penting untuk meningkatkan aplikasi Java Anda. Dengan Aspose.Email untuk Java, Anda dapat mengatur beberapa properti seperti float, double, long, short, boolean, dan properti kustom dengan mudah. Panduan ini akan memandu Anda melalui berbagai metode untuk mencapainya.

**Apa yang Akan Anda Pelajari:**
- Mengatur beberapa properti dalam pesan MAPI menggunakan Aspose.Email Java
- Memahami berbagai jenis properti dan kegunaannya
- Contoh kode praktis untuk implementasi

Mari kita mulai dengan membahas prasyaratnya.

## Prasyarat

Untuk mengikutinya, pastikan Anda memiliki:
- **Kit Pengembangan Java (JDK):** JDK 8 atau yang lebih baru terpasang.
- **Pustaka Aspose.Email:** Versi 25.4 direkomendasikan.
- **Pengaturan Maven:** Maven harus dikonfigurasi dalam IDE Anda untuk manajemen ketergantungan.

### Perpustakaan yang Diperlukan

Sertakan Aspose.Email sebagai dependensi di `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Akuisisi Lisensi
- **Uji Coba Gratis:** Mulailah dengan uji coba gratis untuk menjelajahi fitur-fiturnya.
- **Lisensi Sementara:** Dapatkan untuk pengujian lanjutan tanpa batasan.
- **Pembelian:** Pertimbangkan untuk membeli jika sesuai dengan kebutuhan Anda.

## Menyiapkan Aspose.Email untuk Java

Pastikan Aspose.Email dikonfigurasi dengan benar di lingkungan pengembangan Anda:
1. **Ketergantungan Impor:** Menyelesaikan dependensi Maven.
2. **Set Lisensi:**
   - Unduh file lisensi dari [Asumsikan](https://purchase.aspose.com/buy).
   - Terapkan menggunakan:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Setelah pengaturan selesai, mari jelajahi cara mengatur berbagai properti.

## Panduan Implementasi

### Mengatur Beberapa Properti Float

Pengaturan properti float memungkinkan penyimpanan data numerik yang efisien:

#### Ringkasan
Fitur ini menunjukkan penambahan beberapa nilai float sebagai properti pesan MAPI menggunakan Aspose.Email untuk Java.

#### Tangga
1. **Membuat dan Menginisialisasi Pesan**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Menambahkan Nilai Float ke Daftar**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Tetapkan Properti dengan Pengidentifikasi Unik**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Penjelasan:* Tag properti `0x23901004` mengidentifikasi set properti float ini.

### Mengatur Beberapa Properti Ganda

Properti ganda menyimpan angka floating-point presisi tinggi:

#### Ringkasan
Bagian ini menunjukkan penyimpanan beberapa nilai ganda sebagai properti pesan MAPI.

#### Tangga
1. **Inisialisasi Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Mengisi Nilai Ganda**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Tetapkan ke Tag Properti**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Mengatur Beberapa Properti APPTIME

Properti APPTIME menyimpan durasi waktu secara efisien:

#### Ringkasan
Fitur ini menggambarkan penggunaan angka presisi ganda untuk representasi waktu.

#### Tangga
1. **Buat Objek Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tambahkan Nilai Waktu**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Mengatur Properti**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Mengatur Beberapa Properti Panjang

Properti panjang ideal untuk bilangan bulat besar:

#### Ringkasan
Fitur ini berfokus pada pengaturan beberapa nilai integer panjang dalam sebuah pesan.

#### Tangga
1. **Inisialisasi Pesan MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tambahkan Nilai Panjang**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Definisikan Tag Properti**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Mengatur Beberapa Properti Pendek

Properti pendek menyimpan data integer kecil secara efisien:

#### Ringkasan
Panduan ini memperagakan pengaturan bilangan bulat pendek sebagai properti pesan.

#### Tangga
1. **Inisialisasi Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tambahkan Nilai Pendek**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Tetapkan Tag Properti**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Mengatur Beberapa Properti Boolean

Properti Boolean menyimpan status benar/salah:

#### Ringkasan
Pelajari cara menetapkan beberapa nilai boolean dalam sebuah pesan.

#### Tangga
1. **Buat Objek Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tambahkan Nilai Boolean**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Tetapkan Properti dengan Pengidentifikasi**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Menetapkan Properti Null

Menetapkan properti secara eksplisit sebagai null dapat berguna:

#### Ringkasan
Bagian ini memperagakan penetapan nilai null pada suatu properti.

#### Tangga
1. **Inisialisasi Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tetapkan Properti Null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Pengaturan Properti Bernama Panjang dengan ID Kustom dan UUID

Untuk skenario yang kompleks, tetapkan properti bernama:

#### Ringkasan
Fitur ini menunjukkan pengaturan properti panjang dengan pengenal dan UUID khusus.

#### Tangga
1. **Inisialisasi Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tambahkan Nilai Panjang**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Membuat dan Memetakan Properti**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Mengatur Properti Kustom dengan Nama

Properti kustom dapat diberi nama untuk memudahkan identifikasi:

#### Ringkasan
Panduan ini menunjukkan pengaturan properti dengan nama khusus.

#### Tangga
1. **Inisialisasi Objek Pesan**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Tentukan Properti Kustom**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Pengaturan dan Validasi Properti

Memastikan properti diatur dengan benar sangatlah penting:

#### Ringkasan
Bagian ini mencakup pengaturan dan validasi beberapa properti dalam pesan MAPI.

#### Tangga
1. **Tetapkan Properti**
   Ikuti contoh sebelumnya untuk menetapkan properti.
2. **Validasi Properti**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Kesimpulan

Panduan ini menyediakan pendekatan komprehensif untuk mengelola beberapa properti dalam pesan MAPI menggunakan Aspose.Email untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat menyimpan dan mengelola berbagai tipe data dalam aplikasi Anda secara efisien.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}