---
date: '2026-08-11'
description: Aspose.Email for Java kullanarak pst klasörlerini ve mesajlarını nasıl
  taşıyacağınızı öğrenin – pst'yi verimli bir şekilde taşımanın adım adım rehberi.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Aspose.Email for Java ile pst klasörlerini ve mesajlarını birkaç satır
  kodla nasıl taşıyacağınızı öğrenin. Bu rehber, kurulum, alt klasörlerin taşınması,
  tek tek öğeler ve büyük PST dosyaları için en iyi uygulamaları kapsar.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Aspose.Email Java ile pst klasörlerini ve mesajlarını nasıl taşırsınız
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Aspose.Email Java ile pst klasörlerini ve mesajlarını nasıl taşırsınız
url: /tr/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email Java ile pst klasörlerini ve mesajlarını nasıl taşırsınız

Büyük Outlook PST dosyalarını yeniden düzenlemeniz gerektiğinde etkili e-posta yönetimi hayati öneme sahiptir. Bu öğreticide, Aspose.Email for Java ile **pst'yi nasıl taşıyacağınızı** programlı olarak öğrenecek, Outlook'u başlatmadan otomatik temizlik, taşıma ve arşivleme imkanı sağlayacaksınız. Tam API detayları için [Aspose Email Java Reference](https://reference.aspose.com/email/java/) sayfasına bakın.

## Hızlı cevaplar
- **Hangi kütüphane kullanılıyor?** Aspose.Email for Java  
- **Hem klasörleri hem de tek tek mesajları taşıyabilir miyim?** Evet – mesajlar için `moveItem` ve tüm klasörler için `moveSubfolders` kullanın  
- **Üretim için lisansa ihtiyacım var mı?** Ticari dağıtımlar için geçerli bir Aspose lisansı gereklidir  
- **Hangi Java sürümü önerilir?** En iyi performans için Java 16 veya daha yenisi  
- **Örnek bir PST dosyası gerekli mi?** Outlook tarafından oluşturulan herhangi bir PST çalışır; birini Outlook ile oluşturabilir veya test dosyası olarak kullanabilirsiniz  

## Java geliştirmede pst taşıma ne anlama geliyor?
Moving pst, Personal Storage Table (PST) dosyası içindeki klasörleri veya e-posta öğelerini programlı olarak yeniden konumlandırmak anlamına gelir. Bu, toplu temizlik, eski postaları arşivleme veya posta depoları arasında içeriği manuel Outlook etkileşimi olmadan taşıma işlemlerini otomatikleştirmenizi sağlar, verimliliği artırır ve insan hatasını azaltır.

## Aspose.Email for Java ile pst verilerini taşımak neden tercih edilmeli?
Aspose.Email ile pst verilerini taşıyabilirsiniz çünkü **pure‑Java API** sağlayarak herhangi bir işletim sisteminde çalışır, **100 GB'den fazla** PST dosyasını destekler ve standart sunucu donanımında **dakikada 500 000 öğeye** kadar işleyebilir. Kütüphane ayrıca ayrıntılı istisnalar sunar, böylece sorunları hızlıca tespit edebilirsiniz.

## Önkoşullar
- Aspose.Email for Java (en son sürüm)  
- JDK 16+ (veya daha yenisi)  
- Maven veya Gradle yapı sistemi  
- Test için bir PST dosyası (Outlook tarafından oluşturulan herhangi bir dosya)

## Aspose.Email for Java'ı Kurma
Aspose.Email'i kullanmak için Maven bağımlılığını `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme adımları
1. **Free trial** – Aspose.Email özelliklerini keşfetmek için ücretsiz deneme ile başlayın.  
2. **Temporary license** – Uzun süreli kullanım için geçici bir lisansı [Aspose'un web sitesinden](https://purchase.aspose.com/temporary-license/) edinin.  
3. **Purchase** – Kütüphane üretim ihtiyaçlarınızı karşılıyorsa tam bir lisans almayı düşünün. Fiyatlandırma detayları için [Aspose'un satın alma seçeneklerine](https://purchase.aspose.com/buy) bakın.  

### Temel başlatma ve kurulum
PST dosyalarıyla çalışmaya başlamadan önce kütüphanenin doğru şekilde referans edildiğinden emin olun:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## pst klasörlerini ve mesajlarını nasıl taşırsınız
Aşağıda, **how to move pst** öğelerini verimli bir şekilde taşımak istediğinizde ihtiyaç duyacağınız temel işlemler yer almaktadır.

### PST dosyasını başlatma ve erişme
`PersonalStorage`, PST dosyalarını açmak ve manipüle etmek için Aspose.Email'in birincil sınıfıdır.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Adım 1: PST dosyasını yükleyin
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Adım 2: Önceden tanımlı klasörlere erişin
- **Gelen Kutusu klasörü**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Silinen Öğeler klasörü**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### PST içinde bir alt klasörü başka bir klasöre taşıma
`FolderInfo`, PST dosyası içindeki bir klasörü temsil eder ve alt klasörleri taşıma yöntemleri sağlar.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Adım 1: Kaynak ve hedef klasörlere erişin
```java
pst.moveItem(subfolder, deletedItems);
```

#### Adım 2: Gelen Kutusundan belirli bir alt klasör alın
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Adım 3: Tüm alt klasörü taşıyın
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### PST içinde klasörler arasında tek tek mesajları taşıma
`MessageInfoCollection`, her biri bir e-posta mesajını temsil eden `MessageInfo` nesnelerinin bir koleksiyonunu tutar.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Adım 1: Belirli bir alt klasörden mesajları alın
```java
inbox.moveSubfolders(deletedItems);
```

#### Adım 2: İlk mesajı Silinen Öğeler klasörüne taşıyın
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### PST içinde bir klasörden diğerine tüm alt klasörleri taşıma
`moveSubfolders`, bir kaynaktan hedefe tek bir çağrıyla tüm alt klasörleri aktarır.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Adım 1: Kaynak ve hedef klasörlere erişin
```java
subfolder.moveContents(deletedItems);
```

#### Adım 2: Tüm alt klasörleri taşıyın
CODE_BLOCK_PLACEHOLDER_15_END

### PST içinde bir alt klasörün tüm içeriğini başka bir klasöre taşıma
`moveAllContents` (`moveItem` kullanan özel bir döngü), bir alt klasör içindeki tüm mesajları yeniden konumlandırabilir.

CODE_BLOCK_PLACEHOLDER_16_END

#### Adım 1: Kaynak ve hedef klasörlere erişin
CODE_BLOCK_PLACEHOLDER_17_END

#### Adım 2: Gelen Kutusundan belirli bir alt klasör alın
CODE_BLOCK_PLACEHOLDER_18_END

#### Adım 3: Alt klasörün tüm içeriğini taşıyın
CODE_BLOCK_PLACEHOLDER_19_END

## Pratik uygulamalar
Moving pst klasörlerini ve mesajlarını taşımak aşağıdaki durumlar için faydalıdır:
- **Veri taşıma** – posta kutularını Outlook'tan başka bir posta sistemine taşıyın.  
- **E-posta arşivleme** – eski postaları otomatik olarak arşiv klasörlerine düzenleyin.  
- **Temizlik işlemleri** – eski öğeleri arşiv veya silme klasörlerine taşıyarak gelen kutularını düzenleyin.

## Performans hususları
Aspose.Email for Java ile büyük PST dosyalarını işlerken aşağıdaki ipuçlarını izleyin:

- **Kaynak kullanımını optimize edin** – `PersonalStorage` nesnelerini try‑with‑resources veya açık `dispose` kullanarak hızlıca kapatın.  
- **Bellek yönetimi** – tüm klasörü belleğe yüklemek yerine öğeleri toplu olarak işleyin; bu, JVM'lerde yığın baskısını azaltır.  

### En iyi uygulamalar
- Her zaman işlemlerden sonra PST kaynaklarını serbest bırakın.  
- `InvalidOperationException` hatasını önlemek için taşıma işlemine başlamadan önce klasör varlığını doğrulayın.  

## Sıkça Sorulan Sorular

**Q: PST dosyası nedir?**  
A: PST (Personal Storage Table) dosyası, Outlook'un e-posta mesajları, kişiler, takvim öğeleri ve diğer posta kutusu verilerini yerel olarak depolamak için kullandığı özel formattır.

**Q: Aspose.Email for Java'ı ticari projelerde kullanabilir miyim?**  
A: Evet, [Aspose'un satın alma seçenekleri](https://purchase.aspose.com/buy) üzerinden geçerli bir lisans almanız koşuluyla ticari olarak kullanabilirsiniz.

**Q: Aspose.Email kullanarak PST dosyalarıyla çalışırken istisnaları nasıl yönetirim?**  
A: Kodunuzu `try‑catch` bloklarıyla sararak `IOException`, `InvalidOperationException` veya Aspose‑özel istisnalarını yakalayın, ardından hata ayrıntılarını kaydedin veya gerektiğinde yeniden fırlatın.

**Q: Bu kodu çalıştırmak için sistem gereksinimleri nelerdir?**  
A: JDK 16 veya daha yenisi ve IntelliJ IDEA veya Eclipse gibi uyumlu bir IDE gerekir. Aspose.Email JAR dosyası projenizin sınıf yolunda bulunmalıdır.

**Q: Aspose.Email for Java hakkında daha fazla kaynağa nereden ulaşabilirim?**  
A: Resmi belgeler için [Aspose Email Java Reference](https://reference.aspose.com/email/java/) sayfasını ziyaret edin.

**Q: Aspose.Email şifre korumalı PST dosyalarını destekliyor mu?**  
A: Evet, `PersonalStorage.fromFile` çağrısı sırasında şifreyi sağlayarak şifreli PST'leri açabilirsiniz.

**Q: Bir taşıma işleminin başarılı olduğunu nasıl doğrularım?**  
A: `moveItem` veya `moveSubfolders` çağrısından sonra, hedef klasörü `getContents()` veya `getSubFolders()` ile sorgulayarak taşınan öğelerin varlığını doğrulayabilirsiniz.

## Kaynaklar
- **Dokümantasyon**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **API detayları**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **İndirme**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Satın alma**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Ücretsiz deneme**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Geçici lisans**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Son Güncelleme:** 2026-08-11  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Email for Java ile PST Mesajlarını Toplu Güncelleme: Kapsamlı Rehber](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Aspose.Email for Java Kullanarak Outlook PST Mesajlarını Nasıl Çıkarılır: Tam Kılavuz](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Aspose.Email for Java Kullanarak PST Dosyaları Arasında Mesaj Transferi: Kapsamlı Rehber](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}