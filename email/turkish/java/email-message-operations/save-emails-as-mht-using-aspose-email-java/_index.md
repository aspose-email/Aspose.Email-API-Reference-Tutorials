---
date: '2026-09-22'
description: Aspose.Email lisansını Maven ile kullanarak Java'da e-postaları MHT dosyaları
  olarak kaydetmeyi öğrenin. Kurulum, özel şablonlar ve takvim etkinliği yönetimi
  dahil.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Aspose.Email lisansını Maven ile kullanarak Java'da e-postaları MHT
  dosyaları olarak kaydetmeyi öğrenin. Kurulum, özel şablonlar ve takvim desteği dahil.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Aspose.Email lisansını kullanarak e-postaları MHT olarak kaydetme
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Aspose.Email lisansını kullanarak e-postaları MHT olarak kaydetme
url: /tr/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email lisansı kullanarak e-postaları MHT olarak kaydetme

## Giriş

E-posta verilerini verimli bir şekilde yönetmek zor olabilir, özellikle paylaşım ve arşivleme söz konusu olduğunda. Bu rehberde **Maven Aspose.Email for Java ve bir Aspose.Email lisansı kullanarak MHT dosyalarını nasıl kaydedeceğinizi** göstereceğiz, böylece e-postaları özel şablonlarla MHT'ye dönüştürebilir ve takvim etkinliklerini koruyabilirsiniz. Herhangi bir Java 16+ ortamında çalışan ve üretim kullanımı için lisans gereksinimlerine uyan hazır‑çalıştır bir çözüm elde edeceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneye ihtiyacım var?** Maven Aspose.Email for Java (v25.4+).  
- **Hangi format üretilir?** HTML, görseller ve takvim verilerini bir araya getiren bir MHT (MHTML) dosyası.  
- **Başlığı özelleştirebilir miyim?** Evet – `MhtFormatOptions` ve şablon dizelerini kullanın.  
- **Lisans gerekir mi?** Üretim için bir Aspose.Email lisansı gereklidir; ücretsiz deneme değerlendirme için çalışır.  
- **Hangi Java sürümü gereklidir?** JDK 16 veya daha yenisi.  

## Maven Aspose.Email for Java nedir?

Maven Aspose.Email for Java, e-posta mesajlarını doğrudan Java kodundan oluşturmanıza, okumanıza, dönüştürmenize ve manipüle etmenize olanak tanıyan kapsamlı bir API sağlayan bir kütüphanedir. MSG, EML ve MHT dahil olmak üzere 30’dan fazla e-posta formatını destekler; böylece karşılaştığınız neredeyse her e-posta dosyasını işleyebilirsiniz.

## Neden e-postaları MHT'ye dönüştürmeliyiz?

MHT dosyaları tüm kaynakları (HTML, görseller, takvim verileri) tek bir dosyada birleştirir, böylece modern bir tarayıcıda dış kaynaklara ihtiyaç duymadan anında görüntülenebilir. Bu format orijinal görünümü korur, yinelenen takvim etkinliklerini destekler ve paylaşım sırasında eklerin eksik kalma riskini azaltır.

## Önkoşullar
- **Aspose.Email for Java** (Maven artefaktı `com.aspose:aspose-email:25.4` `jdk16` sınıflandırıcısı ile).  
- **Maven** makinenizde kurulu ve yapılandırılmış.  
- **JDK 16+** (kütüphane Java 16'yı hedefler).  
- Üretim kullanımı için geçerli bir **Aspose.Email lisansı** dosyası.  
- Temel Java bilgisi (dosya işleme, Maven bağımlılıkları).

## Aspose.Email for Java kurulumu

### Maven bağımlılığı

Add the following dependency to your `pom.xml` file:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinimi

Aspose, yeteneklerini keşfetmeniz için ücretsiz bir deneme sunar; ayrıca bir lisans satın alma veya geçici bir lisans elde etme seçenekleri de vardır.

1. **Ücretsiz deneme** – [Releases](https://releases.aspose.com/email/java/) adresinden indirin ve özellikleri sınırlama olmadan keşfedin.  
2. **Geçici lisans** – tam işlevsel bir sürüm için [Temporary License Page](https://purchase.aspose.com/temporary-license/) üzerinden talepte bulunun.  
3. **Satın alma** – uzun vadeli projeler için kalıcı bir lisans edinin.

### Temel başlatma

Once installed, initialize the library in your Java application:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## Uygulama rehberi

### Özellik 1: MailMessage yükleme

#### Genel Bakış

`MailMessage` Aspose.Email'in çekirdek nesnesidir ve bir e-postayı, başlıklarını, gövdesini, eklerini ve takvim etkinliklerini temsil eder.

#### Adım‑adım

**Gerekli sınıfları içe aktar**

```java
import com.aspose.email.MailMessage;
```

**Dosyadan e-posta yükle**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

### Özellik 2: MhtSaveOptions yapılandırma

#### Genel Bakış

`MhtSaveOptions`, Aspose.Email'in bir `MailMessage`'ı MHT dosyası olarak kaydederken format bayraklarını, şablonları ve kaynak gömme ayarlarını kontrol eder. Doğru yapılandırma başlıkları gömmeyi, takvim etkinliklerini render etmeyi ve tüm görselleri dahil etmeyi sağlar.

#### Adım‑adım

**Gerekli sınıfları içe aktar**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Kaydetme seçeneklerini ve şablonları ayarla**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

### Özellik 3: MailMessage'ı MHT olarak kaydet

#### Genel Bakış

Yapılandırılmış `MailMessage`'ı MHT dosyası olarak kaydetmek, tarayıcılarda veya e-posta istemcilerinde açılabilen tek bir, bağımsız belge oluşturur. `save` yöntemi daha önce tanımladığınız seçenekleri dikkate alır.

#### Adım‑adım

**Gerekli sınıfları içe aktar**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**E-posta mesajını kaydet**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

## Pratik uygulamalar
- **E-posta arşivleme** – Önemli e-postaları uzun vadeli saklama için web‑uyumlu bir formatta dönüştür ve depola.  
- **Hukuki belgeler** – E-posta bütünlüğünün gerektiği yasal delillerin bir parçası olarak MHT dosyalarını kullanın.  
- **Çapraz platform paylaşımı** – MHT tüm içeriği tek dosyada topladığı için uyumluluk sorunları olmadan platformlar arasında e-posta paylaşın.

Bu özellikleri CRM veya proje‑yönetim araçları gibi diğer sistemlerle entegre etmek, kritik e-posta verilerini doğrudan iş akışlarına gömerek iş birliğini artırabilir.

## Performans değerlendirmeleri
Aspose.Email for Java, tüm belgeyi belleğe yüklemeden 500 MB'a kadar dosyaları işleyebilir ve tipik bir sunucuda gömülü görsellerle 100‑sayfalık bir e-postayı 2 saniyeden kısa sürede dönüştürür. Uygulamanızın yanıt verebilirliğini korumak için bellek kullanımını dikkatli yönetin ve mümkün olduğunca toplu I/O işlemleri yapın.

## Yaygın sorunlar ve çözümler
`MhtFormatOptions` bir enumerasyondur ve bir mesajı MHT olarak kaydederken hangi öğelerin (başlıklar, kaynaklar, takvim etkinlikleri) dahil edileceğini kontrol eder.

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **`msg.save` üzerinde NullPointerException** | Yanlış çıktı yolu | `YOUR_OUTPUT_DIRECTORY`'nin mevcut ve yazılabilir olduğunu doğrulayın. |
| **MHT'de eksik görseller** | `MhtFormatOptions` kaynakları gömmek için ayarlanmamış | Seçenek bayrağına `MhtFormatOptions.EmbedResources` ekleyin. |
| **Takvim etkinlikleri render edilmedi** | `RenderCalendarEvent` bayrağı atlanmış | `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` ifadesinin kullanıldığından emin olun. |

## Sıkça sorulan sorular

**S: E-postaları MHT olarak kaydederken ekleri nasıl yönetirim?**  
**C:** `MhtSaveOptions`'ı ekleri gömmek için yapılandırın; kütüphane otomatik olarak bunları MHT paketine dahil eder.

**S: Çıktı MHT dosyasında e-posta başlıklarını özelleştirebilir miyim?**  
**C:** Evet, `MhtFormatOptions.WriteHeader` kullanın ve her başlık alanı için özel şablon dizeleri sağlayın.

**S: Aspose.Email Java kullanmak için sistem gereksinimleri nelerdir?**  
**C:** JDK 16 veya daha yenisi gereklidir. Kütüphane, Maven projelerini destekleyen herhangi bir IDE ile çalışır.

**S: Bir e-posta mesajının sadece belirli bölümlerini kaydetmek mümkün mü?**  
**C:** MHT genellikle tam mesajı içerir, ancak kaydetmeden önce `MailMessage` özelliklerini değiştirerek istenmeyen bölümleri dışarıda bırakabilirsiniz.

**S: E-posta yükleme veya kaydetme sorunlarını nasıl gideririm?**  
**C:** Dosya yollarını doğrulayın, lisansın doğru uygulandığından emin olun ve ayrıntılı yardım için Aspose.Email [support forum](https://forum.aspose.com/c/email/10) adresine bakın.

**S: Kütüphane diğer formatları (EML, MSG) MHT'ye dönüştürmeyi destekliyor mu?**  
**C:** Kesinlikle. `MailMessage.load` EML, MSG ve diğer desteklenen formatları okuyabilir; ardından aynı seçeneklerle MHT olarak kaydedebilirsiniz.

## Kaynaklar
- **Dokümantasyon**: Tüm işlevselliklere daha derin bir bakış için [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) adresini ziyaret edin.  
- **İndirme**: Ücretsiz denemenize başlamak için [Releases](https://releases.aspose.com/email/java/) adresinden indirin.  
- **Satın Alma**: Uzun vadeli kullanım için [Official Purchase Page](https://purchase.aspose.com/buy) adresindeki satın alma seçeneklerini inceleyin.  
- **Ücretsiz deneme ve geçici lisans**: Bu bağlantılar aracılığıyla ücretsiz deneme sırasında kapsamlı özelliklere erişebilir veya geçici bir lisans alabilirsiniz:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Aspose.Email for Java ile e-posta işleme süreçlerinizi keşfedin, uygulayın ve dönüştürün!

**Last Updated:** 2026-09-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

## İlgili Eğitimler

- [Aspose.Email for Java'da Uzmanlaşma: Lisans ve E-posta İşleme Rehberi](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Aspose.Email for Java ile MSG'yi MHT'ye Dönüştürme – Adım‑adım Kılavuz](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Aspose.Email for Java ile MSG E-postalarını Kaydetme](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}