---
date: '2026-09-02'
description: Aspose.Email for Java kullanarak Outlook PST dosyalarından ekleri nasıl
  çıkaracağınızı öğrenin. Bu rehber, Maven kurulumu, PST'lerin yüklenmesi ve PDF'ler
  ile diğer dosyaların verimli bir şekilde çıkarılmasını kapsar.
keywords:
- extract attachments from outlook
- how to extract pst attachments
- aspose email java tutorial
- maven dependency aspose email
- aspose email java example
lastmod: '2026-09-02'
og_description: Aspose.Email for Java kullanarak Outlook PST dosyalarından ekleri
  çıkarın. Maven'i kurmak, PST'leri yüklemek ve PDF'ler ile diğer dosyaları çıkarmak
  için bu adım adım rehberi izleyin.
og_image_alt: Developer guide showing Java code to extract Outlook PST attachments
  using Aspose.Email
og_title: Aspose.Email ile Java'da Outlook PST'den ekleri çıkarın
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to extract attachments from Outlook PST files using Aspose.Email
    for Java. This guide covers Maven setup, loading PSTs, and extracting PDFs and
    other files efficiently.
  headline: How to extract attachments from Outlook PST in Java
  type: TechArticle
- description: Learn how to extract attachments from Outlook PST files using Aspose.Email
    for Java. This guide covers Maven setup, loading PSTs, and extracting PDFs and
    other files efficiently.
  name: How to extract attachments from Outlook PST in Java
  steps:
  - name: define your directory path
    text: Identify where your PST file resides and set the path.
  - name: load the PST file
    text: '`PersonalStorage` is Aspose.Email’s top‑level class that represents a single
      PST or OST file in memory. After you create an instance, you can navigate folders,
      read messages, and extract data.'
  - name: access the Inbox subfolder
    text: '`MapiFolder` represents a folder inside the PST (e.g., Inbox, Sent Items).
      The `getSubFolders` method lets you drill down to the exact location you need.'
  - name: iterate through emails and extract attachments
    text: '`MapiMessage` encapsulates an individual email message. Its `getAttachments`
      collection provides every file attached to that message. `MapiAttachment` is
      the class that holds the binary data and metadata for each attachment.'
  type: HowTo
- questions:
  - answer: After retrieving each `MapiAttachment`, check the file extension with
      `attachment.getLongFileName().endsWith(".pdf")` before saving.
    question: How can I extract only PDF attachments (java extract pdf attachments)?
  - answer: The official documentation and sample repository provide extensive examples—see
      the links below.
    question: Where can I find more detailed code examples for the aspose email java
      tutorial?
  - answer: Yes, Aspose.Email for Java is forward‑compatible; just ensure you use
      the appropriate classifier (e.g., `jdk21`) when it becomes available.
    question: Is the library compatible with newer Java versions (e.g., JDK 21)?
  - answer: Absolutely. Package the code into a JAR, configure a cron job, and ensure
      the server has the required JDK and Maven runtime.
    question: Can I run this extraction as a scheduled job on a Linux server?
  type: FAQPage
tags:
- extract attachments
- Aspose.Email
- Java email processing
title: Java ile Outlook PST'den ekleri nasıl çıkarılır
url: /tr/java/attachments-handling/extract-email-attachments-pst-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook PST'den Java ile ekleri nasıl çıkarılır

## Giriş

Outlook PST dosyalarından ekleri çıkarmak, veri göçü, uyumluluk arşivleme ve otomatik fatura işleme gibi senaryolar için yaygın bir gereksinimdir. Bu öğreticide **Outlook'tan ekleri nasıl çıkarılır** sorusunun cevabını Aspose.Email for Java kullanarak öğrenecek, Maven bağımlılığını kuracak, bir PST dosyasını yükleyecek ve sadece birkaç satır kodla PDF, görüntü veya diğer ekli belgeleri alacaksınız.

**Öğrenecekleriniz**
- Aspose.Email için Maven bağımlılığının nasıl ekleneceği (aspose email java tutorial)  
- Bir PST dosyasının nasıl açılacağı ve klasör hiyerarşisinin nasıl gezileceği  
- E-posta eklerini verimli bir şekilde çıkarmak, *how to extract pst attachments* sorusuna yanıt vermek  

E-posta ekleri iş akışınızı otomatikleştirmeye hazır mısınız? Hadi başlayalım.

## Hızlı yanıtlar
- **Ana kütüphane?** Aspose.Email for Java  
- **Tipik uygulama süresi?** Temel çıkarma için 10–15 dakika  
- **Temel ön koşul?** JDK 16+ ve Maven kurulu  
- **Lisans gerekli mi?** Evet, üretim kullanımı için geçerli bir Aspose lisansı  
- **PST & OST destekleniyor mu?** Her iki format da destekleniyor  

## “How to extract attachments” nedir?

Ekleri çıkarmak, Java kodu kullanarak Outlook PST (veya OST) dosyalarını okuyup ekli dosyaları—belgeler, görseller, PDF’ler—seçtiğiniz bir klasöre kaydetmek anlamına gelir. Bu yaklaşım veri göçü projeleri, otomatik fatura işleme veya arşivleme çözümleri için idealdir. İşlem, her mesajın MIME bölümlerini ayrıştırır, her ekin ikili içeriğini alır ve belirtilen çıktı klasörüne yazar; böylece indeksleme veya dönüşüm gibi ek işlemler yapılabilir.

## Neden Aspose.Email bu görev için?

Aspose.Email, sunucuda Outlook veya MAPI gerektirmeyerek kurulum süresini %80’e kadar azaltır ve lisans maliyetlerini düşürür. **50+** giriş ve çıkış formatını destekler, şifreli depoları yönetir ve düşük seviyeli ayrıştırma detaylarını soyutlayan `extractAttachments` gibi yüksek seviyeli metodlar sunar.

## Önkoşullar

- **Java Development Kit (JDK):** Versiyon 16 veya daha yenisi.  
- **Maven:** Bağımlılık yönetimi için.  
- **Aspose.Email for Java kütüphanesi:** Maven üzerinden eklenir (aşağıdaki *maven dependency aspose email* kod parçacığına bakın).  
- **IDE:** IntelliJ IDEA, Eclipse veya VS Code kod düzenleme ve çalıştırma için.  

## Aspose.Email for Java kurulumu

### Maven bağımlılığını ekleyin (maven dependency aspose email)

Projenizin `pom.xml` dosyasındaki `<dependencies>` bölümüne aşağıdaki XML’i ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinimi

Aspose ücretsiz bir deneme sunar, ancak tam lisans tüm özelliklerin kilidini açar. Geçici bir lisans alabilirsiniz: [temporary license page](https://purchase.aspose.com/temporary-license/).

## Uygulama rehberi (aspose email java tutorial)

### Özellik 1: PST dosyasını yükle

#### Adım 1: dizin yolunu tanımlayın

PST dosyanızın bulunduğu yeri belirleyin ve yolu ayarlayın.

```java
String pstFilePath = "YOUR_DOCUMENT_DIRECTORY/Sub.pst";
```

#### Adım 2: PST dosyasını yükleyin

`PersonalStorage`, Aspose.Email’in bellek içinde tek bir PST veya OST dosyasını temsil eden üst‑seviye sınıfıdır. Bir örnek oluşturduktan sonra klasörlerde gezinebilir, mesajları okuyabilir ve veri çıkarabilirsiniz.

```java
PersonalStorage pst = PersonalStorage.fromFile(pstFilePath);
```

### Özellik 2: E-postalardan ekleri çıkar

#### Adım 1: Inbox alt klasörüne erişin

`MapiFolder`, PST içindeki bir klasörü temsil eder (ör. Inbox, Sent Items). `getSubFolders` metodu, ihtiyacınız olan konuma inmeyi sağlar.

```java
FolderInfo inboxFolder = pst.getRootFolder().getSubFolder("Inbox");
```

#### Adım 2: E-postaları döngüye alıp ekleri çıkarın

`MapiMessage`, tek bir e‑posta mesajını kapsar. `getAttachments` koleksiyonu, o mesaja eklenmiş tüm dosyaları verir. `MapiAttachment`, her ekin ikili verisini ve meta verilerini tutan sınıftır.

```java
for (String entryId : inboxFolder.enumerateMessagesEntryId()) {
    MapiAttachmentCollection attachments = pst.extractAttachments(entryId);
    
    if (!attachments.isEmpty()) {
        for (MapiAttachment attachment : attachments) {
            String outputFilePath = "YOUR_OUTPUT_DIRECTORY/" + attachment.getLongFileName();
            attachment.save(outputFilePath); // Save each attachment
        }
    }
}
```

### Temel yapılandırma seçenekleri

- **Çıktı dizini:** Klasörün var olduğunu ve uygulamanın yazma iznine sahip olduğunu doğrulayın.  
- **Hata yönetimi:** Yukarıdaki mantığı `try‑catch` bloklarıyla sararak I/O hatalarını veya bozuk PST girdilerini nazikçe ele alın.  

### Sorun giderme ipuçları (how to extract pst attachments)

PST eklerini çıkarırken sorun yaşarsanız şu hızlı çözümleri deneyin:

- **Dosya bulunamadı:** `pstFilePath` dizesini iki kez kontrol edin; güvenilirlik için mutlak yollar kullanın.  
- **İzin sorunları:** JVM’i uygun dosya sistemi izinleriyle çalıştırın veya kullanıcının ev klasöründeki bir dizini seçin.  
- **Büyük PST dosyaları:** Mesajları partiler halinde işleyin ve her partiden sonra `System.gc()` çağırarak belleği serbest bırakın.  

## Pratik uygulamalar

1. **Veri yedekleme:** Ekleri periyodik olarak çekip güvenli bir dış konuma depolayın.  
2. **Otomatik fatura işleme:** Gelen faturalardan PDF’leri çıkarıp bir ERP sistemine besleyin.  
3. **E-posta arşivleme:** Uyumluluk gerektiren arşivlerin bir parçası olarak her eki saklayın.  

## Performans hususları

- **Bellek yönetimi:** 1 GB’den büyük PST’ler için JVM heap’ini artırın (`-Xmx2g` veya daha yüksek).  
- **Parti çıkarma:** Bellek kullanımını düşük tutmak için döngü başına sınırlı sayıda mesaj işleyin.  

## Yaygın sorunlar ve çözümler

| Sorun | Çözüm |
|-------|----------|
| `fromFile` `FileNotFoundException` fırlatıyor | Yolu doğrulayın ve dosyanın başka bir süreç tarafından kilitlenmediğinden emin olun. |
| Büyük PST’lerde Out‑of‑Memory hataları | Heap boyutunu artırın ve daha küçük partilerde çıkarma yapın. |
| Eklerin aynı isimde olması | Kaydetmeden önce `outputFilePath`’e zaman damgası veya GUID ekleyin. |

## Sıkça sorulan sorular

**S:** *PST dosyası nedir?*  
**C:** PST (Personal Storage Table) dosyası, Outlook’un e‑postalar, kişiler, takvim öğeleri ve ekleri sakladığı bir veri dosyasıdır.

**S:** *OST dosyalarından da ek çıkarabilir miyim?*  
**C:** Evet, Aspose.Email hem PST hem de OST formatlarını destekler. Aynı API’yi kullanın; sadece `PersonalStorage.fromFile` metoduna OST dosyasını gösterin.

**S:** *Şifreli PST dosyalarını nasıl ele alırım?*  
**C:** Mağazayı açarken şifreyi sağlayın: `PersonalStorage.fromFile(pstFilePath, "password")`. Ayrıntılı şifreleme yönetimi için Aspose dokümantasyonuna bakın.

**S:** *Hangi e‑postaların işleneceğini filtreleyebilir miyim?*  
**C:** Kesinlikle. `extractAttachments` çağırmadan önce her `MapiMessage`’ı konu, gönderen veya tarih kriterlerine göre inceleyip istenmeyen öğeleri atlayabilirsiniz.

**S:** *Geliştirme için lisans gerekir mi?*  
**C:** Test için geçici bir lisans yeterlidir. Üretim ortamında değerlendirme sınırlamalarını kaldırmak için tam lisans satın alın.

## Ek FAQ (AI‑friendly)

**S:** *Sadece PDF eklerini nasıl çıkarırım (java extract pdf attachments)?*  
**C:** Her `MapiAttachment` alındıktan sonra `attachment.getLongFileName().endsWith(".pdf")` kontrolü yapıp sadece PDF’leri kaydedin.

**S:** *aspose email java tutorial için daha detaylı kod örneklerini nereden bulabilirim?*  
**C:** Resmi dokümantasyon ve örnek deposu kapsamlı örnekler sunar—aşağıdaki linklere bakın.

**S:** *Kütüphane yeni Java sürümleriyle (ör. JDK 21) uyumlu mu?*  
**C:** Evet, Aspose.Email for Java ileri‑uyumludur; sadece uygun sınıflandırıcıyı (ör. `jdk21`) kullandığınızdan emin olun.

**S:** *Bu çıkarma işlemini Linux sunucusunda zamanlanmış bir iş olarak çalıştırabilir miyim?*  
**C:** Kesinlikle. Kodu bir JAR’a paketleyin, bir cron işi oluşturun ve sunucunun gerekli JDK ve Maven ortamına sahip olduğundan emin olun.

## Kaynaklar
- **Dokümantasyon:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/)
- **İndirme:** [Aspose Email Java Release](https://releases.aspose.com/email/java/)
- **Lisans satın al:** [Buy Aspose Email](https://purchase.aspose.com/buy)
- **Ücretsiz deneme:** [Start with a Free Trial](https://releases.aspose.com/email/java/)
- **Destek forumu:** [Ask Questions on the Support Forum](https://forum.aspose.com/c/email/10)

Aspose.Email for Java’ın gücünü benimseyin ve e‑posta eklerini yönetme şeklinizi dönüştürün!

---

**Son Güncelleme:** 2026-09-02  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Efficiently Load and Process Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-outlook-pst-processing/)
- [How to Extract Outlook PST Messages Using Aspose.Email for Java: A Complete Guide](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Manipulate PST Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}