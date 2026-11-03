---
date: '2026-11-03'
description: Aspose.Email Java kullanarak eml'ye attachment eklemeyi, msg'yi eml java'ya
  dönüştürmeyi, batch msg'yi eml'ye dönüştürmeyi ve TNEF'yi yönetmeyi öğrenin.
images:
- /java/attachments-handling/aspose-email-java-tnef-attachments-guide/og-image.png
keywords:
- convert msg to eml
- add attachment to eml
- batch convert msg to eml
- maven aspose email dependency
- tnef handling
lastmod: '2026-11-03'
og_description: Aspose.Email Java ile msg'yi eml'ye dönüştürün ve EML dosyalarına
  attachments ekleyin. Maven kurulumu, TNEF yönetimi, batch dönüşüm ve code examples
  içerir.
og_image_alt: Guide showing how to convert MSG to EML and add attachments using Aspose.Email
  Java
og_title: Aspose.Email Java ile msg'yi eml'ye dönüştürün, attachments ekleyin
schemas:
- author: Aspose
  dateModified: '2026-11-03'
  description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  headline: Add attachment to eml with Aspose.Email Java – convert msg to eml and
    handle TNEF
  type: TechArticle
- description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  name: Add attachment to eml with Aspose.Email Java – convert msg to eml and handle
    TNEF
  steps:
  - name: Load the existing email message
    text: The `MailMessage` class represents an email message in memory, exposing
      headers, body, and attachments.
  - name: Add the new attachment
    text: The `Attachment` class encapsulates a file to be attached to a `MailMessage`.
  - name: Save the modified email message
    text: Calling `mail.save()` writes the updated message back to disk in EML format.
      *Pro tip:* Use try‑with‑resources to ensure streams are closed and avoid `FileNotFoundException`.
  - name: Load the MSG file
    text: The `MapiMessage` class reads Outlook MSG files and exposes their properties.
  - name: Set conversion options
    text: '`MailConversionOptions` lets you control how the conversion handles TNEF
      data.'
  - name: Convert and save
    text: Calling `msg.save()` with the appropriate options writes a TNEF‑preserving
      EML file.
  - name: Set load options
    text: '`MsgLoadOptions` instructs the loader to keep TNEF parts intact.'
  - name: Load EML file with options
    text: '`MailMessage.load()` reads the EML using the options defined above.'
  - name: Load the EML file
    text: The `MailMessage` class again serves as the entry point for reading an EML
      file.
  - name: Detect TNEF presence
    text: The boolean returned by `mail.getOriginalIsTnef()` tells you whether the
      original message contained TNEF data.
  type: HowTo
- questions:
  - answer: No. By default, TNEF data is preserved. You can control this behavior
      with `MailConversionOptions.setConvertAsTnef`.
    question: Does Aspose.Email automatically strip TNEF when converting to EML?
  - answer: Yes—use `mail.getAttachments()` which returns a collection you can iterate
      over.
    question: Can I programmatically list all attachments in a loaded message?
  - answer: Absolutely. Loop through the files, apply the conversion steps shown above,
      and save each result.
    question: Is there a way to batch convert msg files to eml in one run?
  type: FAQPage
tags:
- email conversion
- Aspose.Email
- java email processing
- attachment handling
title: Aspose.Email Java ile eml'ye attachment ekleyin – msg'yi eml'ye dönüştürün
  ve TNEF'yi yönetin
url: /tr/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email Java ile eml'ye ek ekleme ve msg'yi eml'ye dönüştürmeyi ustalaşma: TNEF ve e-posta eklerini yönetme  

Modern e-posta odaklı uygulamalarda sık sık **add attachment to eml**, **convert msg to eml java** yapmanız ve TNEF gibi özel formatları korumanız gerekir. Arşivleme hizmeti, göç aracı veya istemci tarafı posta görüntüleyici oluşturuyor olsanız da, Aspose.Email for Java bunu temiz, programatik bir şekilde yapmanızı sağlar. Bu öğreticide tam olarak **add attachment to eml**, **convert msg to eml java** nasıl yapılır, toplu msg‑den eml senaryoları nasıl çalışır ve Aspose.Email Java kütüphanesiyle TNEF verileri nasıl işlenir göreceksiniz.

## Hızlı cevaplar
- **Java'da MSG'yi EML'ye nasıl dönüştürürüm?** MSG'yi `MapiMessage` ile yükleyin, `MailConversionOptions.convertAsTnef` özelliğini `true` olarak ayarlayın, ardından EML olarak kaydedin.  
- **TNEF‑etkinleştirilmiş bir EML'ye ek ekleyebilir miyim?** Evet – EML'yi yükleyin, `mail.getAttachments().addItem(...)` çağırın, ardından kaydedin.  
- **Hangi Maven bağımlılığı gerekiyor?** Aşağıda gösterilen **Aspose.Email** Maven artefaktını ekleyin.  
- **Üretim için lisansa ihtiyacım var mı?** Evet – deneme sürümü değerlendirme için çalışır, ancak tam lisans sınırlamaları kaldırır.  
- **Mevcut bir mesajda TNEF tespit etmenin bir yolu var mı?** EML'yi yükledikten sonra `mail.getOriginalIsTnef()` çağırın.

## “convert msg to eml java” nedir?
Convert msg to eml java, bir Microsoft Outlook MSG dosyasını Java kullanarak RFC‑822 uyumlu bir EML dosyasına dönüştürme sürecidir. Bu, herhangi bir standart e-posta istemcisinin mesajı okumasını sağlar ve dönüşüm sırasında TNEF‑kodlu verileri manipüle etme imkanı verir.

## eml'ye ek ekleme nasıl yapılır?
Hedef EML'yi yükleyin, yeni dosyayı ekleyin ve sonucu kaydedin – tümü üç kısa API çağrısında. Aspose.Email kullanarak manuel MIME oluşturmayı önlersiniz ve kütüphane mevcut TNEF bölümlerini otomatik olarak korur, böylece son EML Outlook ve diğer istemcilerle tam uyumlu kalır.

## Bu görev için Aspose.Email Java neden kullanılmalı?
Aspose.Email **30+ e-posta formatını** destekler ve **2 GB**'a kadar dosyaları bellek içine tüm belgeyi yüklemeden işleyebilir, bu da büyük ölçekli göçler için idealdir. Kütüphane ayrıca toplu işleme yardımcı araçları, TNEF koruması ve kod tekrarını azaltan akıcı bir API sunar.

## Önkoşullar
- **Aspose.Email for Java** (v25.4, JDK 16) – aşağıdaki Maven bağımlılığına bakın.  
- **Maven** veya Aspose paketini çözebilen başka bir yapı aracı.  
- Java I/O ve istisna yönetimi hakkında temel bilgi.  

## Aspose.Email for Java kurulumu
Add the library to your Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme
Aspose.Email ücretsiz bir deneme sunar, ancak sınırsız kullanım için lisanslı bir sürüm gereklidir.

- **Ücretsiz deneme:** Aspose.Email Java sürüm sayfasından geçici bir lisans indirin: [Aspose.Email Java releases](https://releases.aspose.com/email/java/).  
- **Satın alma:** Lisans satın almak için [satın alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin.

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## Uygulama rehberi

### TNEF içeren ana mesaja yeni ek ekleme
**eml'ye ek ekleme nasıl yapılır:** EML'yi yükleyin, dosyayı ekleyin, ardından kaydedin.

#### Adım 1: Mevcut e-posta mesajını yükleyin
`MailMessage` sınıfı, bellekte bir e-posta mesajını temsil eder, başlıkları, gövdeyi ve ekleri ortaya çıkarır.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### Adım 2: Yeni eki ekleyin
`Attachment` sınıfı, bir `MailMessage`'a eklenecek bir dosyayı kapsüller.  
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### Adım 3: Değiştirilmiş e-posta mesajını kaydedin
`mail.save()` `MailMessage`'ı EML formatında diske yazar.  
```java
eml.save(dataDir + "test_out.eml");
```
*Pro ipucu:* Akışların kapatıldığından emin olmak ve `FileNotFoundException` önlemek için try‑with‑resources kullanın.

### MSG'den TNEF‑etkinleştirilmiş EML oluşturma
**msg'yi eml'ye dönüştürme java:** `convertAsTnef`'i `true` olarak ayarlayın.

#### Adım 1: MSG dosyasını yükleyin
`MapiMessage` sınıfı Outlook MSG dosyalarını okur ve özelliklerine erişim sağlar.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### Adım 2: Dönüşüm seçeneklerini ayarlayın
`MailConversionOptions` dönüşüm davranışını, TNEF işleme dahil, kontrol etmenizi sağlar.  
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### Adım 3: Dönüştür ve kaydet
`msg.save()` belirtilen dönüşüm seçeneklerini kullanarak bir EML dosyası oluşturur.  
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### MSG'den TNEF‑etkinleştirilmiş EML koruma
**TNEF'yi korurken e-posta ekini kaydetme:** `MsgLoadOptions` kullanın.

#### Adım 1: Yükleme seçeneklerini ayarlayın
`MsgLoadOptions` bir EML dosyasının nasıl yükleneceğini yapılandırır, gerektiğinde TNEF bölümlerini korur.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### Adım 2: Seçeneklerle EML dosyasını yükleyin
`MailMessage.load()` sağlanan `MsgLoadOptions`'a göre bir EML dosyasını okur.  
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### Bir mesajın TNEF olup olmadığını tespit etme
**TNEF varlığını kontrol etme:** `getOriginalIsTnef()` çağırın.

#### Adım 1: EML dosyasını yükleyin
`MailMessage.load()` denetim veya değişiklik için mevcut bir EML dosyasını yükler.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### Adım 2: TNEF varlığını tespit edin
`mail.getOriginalIsTnef()` orijinal mesaj TNEF verisi içeriyorsa true döndürür.  
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## Yaygın kullanım senaryoları ve toplu senaryolar
- **Batch convert msg:** `.msg` dosyalarından oluşan bir klasörü döngüye alarak, yukarıdaki dönüşüm adımlarını uygulayın ve her sonucu `.eml` olarak kaydedin. Bu, büyük ölçekli göçler için idealdir.  
- **Add attachment to eml in bulk:** “add attachment” kodunu bir dosya sistemi yineleyicisiyle birleştirerek birçok mesajı aynı anda zenginleştirin.  
- **Automated archiving:** Uyum denetimleri için hem orijinal MSG'yi hem de TNEF korumalı EML'yi saklayın.  

## Performans hususları
- **Kaynak yönetimi:** Dosya akışlarını hızlı bir şekilde serbest bırakmak için try‑with‑resources ile sarın.  
- **Büyük ekler:** Yüksek bellek kullanımını önlemek için büyük dosyaları parçalar halinde işleyin veya doğrudan akıtın.  
- **İzleme:** Çok sayıda ek işlenirken yığın tüketimini izlemek için Java profil araçlarını kullanın.  

## Sonuç
Yukarıdaki adımları izleyerek **add attachment to eml**, **convert msg to eml java** yapabilir ve Aspose.Email for Java kullanarak TNEF verileriyle güvenilir bir şekilde çalışabilirsiniz. Kütüphane düşük seviyeli MIME işlemlerini soyutlayarak iş mantığına odaklanmanızı sağlar. Daha derin bir keşif için resmi [Aspose.Email Java documentation](https://reference.aspose.com/email/java/) sayfasına bakın veya diğer dönüşüm seçenekleriyle deney yapın. Ek kaynaklar arasında [Aspose Email Java Documentation](https://reference.aspose.com/email/java/), [Aspose Email Java Releases](https://releases.aspose.com/email/java/) ve [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) sayfası bulunur.

## SSS bölümü
**S1: TNEF dosyası nedir?**  
C1: TNEF, Transport Neutral Encapsulation Format'ın kısaltmasıdır ve Microsoft Outlook tarafından e-postaları ek olarak gönderirken zengin metin biçimlendirmesini korumak için kullanılır.

**S2: Lisans satın almadan Aspose.Email kullanabilir miyim?**  
C2: Evet, ücretsiz bir deneme ile başlayabilirsiniz. Ancak, deneme sürümü tam ölçekli kullanımda etkili olabilecek bazı sınırlamalar getirir.

**S3: Aspose.Email tüm e-posta formatları arasında dönüşüm yapabilir mi?**  
C3: Aspose.Email, EML, MSG ve MHTML dahil olmak üzere en popüler formatlar arasında dönüşümü destekler; ancak belirli format desteğini [documentation](https://reference.aspose.com/email/java/) içinde doğrulayın.

**S4: Aspose.Email ile dosya‑bulunamadı hatalarını nasıl gideririm?**  
C5: API'ye gönderdiğiniz dosya yollarının doğru, dosyaların mevcut ve çalışan sürecin bu dizinlere okuma/yazma izinlerinin olduğundan emin olun.

**S5: Aspose.Email ile büyük ekleri yönetmenin en iyi yolu nedir?**  
C5: Ekleri daha küçük akışlar veya parçalar halinde işleyin ve her zaman akışları hızlı bir şekilde kapatın. Bu, bellek baskısını azaltır ve `OutOfMemoryError` oluşmasını önler.

## Sıkça sorulan sorular (ek)

**S: Aspose.Email EML'ye dönüştürürken TNEF'i otomatik olarak kaldırır mı?**  
C: Hayır. Varsayılan olarak TNEF verileri korunur. Bu davranışı `MailConversionOptions.setConvertAsTnef` ile kontrol edebilirsiniz.

**S: Yüklenmiş bir mesajdaki tüm ekleri programlı olarak listeleyebilir miyim?**  
C: Evet—`mail.getAttachments()` kullanın; bu, üzerinde döngü kurabileceğiniz bir koleksiyon döndürür.

**S: Tek bir çalıştırmada msg dosyalarını eml'ye toplu olarak dönüştürmenin bir yolu var mı?**  
C: Kesinlikle. Dosyalar arasında döngü yapın, yukarıda gösterilen dönüşüm adımlarını uygulayın ve her sonucu kaydedin.

**İlgili kaynaklar:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Aspose.Email Java sürüm sayfasından geçici bir lisans indirin: [Aspose.Email Java releases](https://releases.aspose.com/email/java/).

---

**Son Güncelleme:** 2026-11-03  
**Test Edilen:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

## İlgili Öğreticiler

- [Maven Aspose Email: EML'de TNEF Eklerini Korumak (Java)](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [Aspose.Email Maven Bağımlılığını Eklemek ve E-posta Ek İçerik Açıklamalarını Almak (Java)](/email/java/attachments-handling/retrieve-email-attachment-content-descriptions-aspose-email-java/)
- [Aspose.Email ile Java'da E-posta Eklerini Çıkarma – Tam Kılavuz](/email/java/attachments-handling/)

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}