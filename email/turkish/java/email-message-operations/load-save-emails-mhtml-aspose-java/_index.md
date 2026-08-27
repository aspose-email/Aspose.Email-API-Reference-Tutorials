---
date: '2026-08-27'
description: Aspose.Email for Java ile MSG dosyalarını nasıl yükleyeceğinizi ve MHTML'ye
  dönüştüreceğinizi öğrenin, özel saat dilimi ayarları ve toplu e-posta işleme ipuçları
  dahil.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Aspose.Email for Java kullanarak msg dosyalarını nasıl yükleyeceğinizi
  ve MHTML olarak dışa aktaracağınızı öğrenin. Saat dilimi yönetimi ve toplu işleme
  ipuçları içerir.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Aspose.Email for Java kullanarak msg dosyalarını nasıl yükleyip MHTML olarak
  kaydedilir
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Aspose.Email for Java kullanarak msg dosyalarını nasıl yükleyip MHTML olarak
  kaydedilir
url: /tr/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java kullanarak msg dosyasını nasıl yükleyip MHTML olarak kaydedilir

## Giriş

Eğer **msg dosyasını nasıl yükleyeceğinizi** dosyaları yüklemek, zaman damgalarını ayarlamak ve ardından **msg'yi mhtml'ye dönüştürmek** istiyorsanız, doğru yerdesiniz. Bu öğreticide bir `.msg` e‑postasını nasıl yükleyeceğimizi, özel bir saat dilimi kayması uygulayacağımızı ve sonucu bir MHTML arşivi olarak nasıl kaydedeceğimizi adım adım göstereceğiz — tümü Aspose.Email for Java ile. Tek bir mesajla mı yoksa bir **toplu e‑posta işleme** hattıyla mı çalışıyorsanız, bu adımlar güvenilir arşivleme ve taşıma için sağlam bir temel sağlayacak.

**Öğrenecekleriniz**
- `MailMessage` sınıfını bir `.msg` dosyasından nasıl yükleyeceğinizi.
- Özel bir saat dilimi ve geçerli tarihi nasıl ayarlayacağınızı.
- Mesajı kesin biçimlendirme ile MHTML olarak nasıl kaydedeceğinizi.
- Yaklaşımı toplu senaryolara ölçeklendirmek için ipuçları.

E-posta iş akışınızı artırmaya hazır mısınız? Önce ortamı hazırlayalım.

## Hızlı cevaplar
- **Ana kütüphane nedir?** Aspose.Email for Java.
- **MSG'yi yükleyip MHTML'ye tek adımda dışa aktarabilir miyim?** Hayır, önce yüklersiniz, ayarlarsınız, ardından kaydedersiniz.
- **Üretim için lisansa ihtiyacım var mı?** Evet, geçerli bir Aspose.Email lisansı gereklidir.
- **Saat dilimi işleme destekleniyor mu?** Evet, `setTimeZoneOffset` ile.
- **Bu toplu işleme için kullanılabilir mi?** Kesinlikle – adımları bir döngü içinde sarın.

## Aspose.Email for Java nedir?

Aspose.Email for Java, Microsoft Outlook gerektirmeden e‑posta mesajları oluşturmanıza, okumanıza, dönüştürmenize ve manipüle etmenize olanak tanıyan kapsamlı bir API'dir. 30'dan fazla e‑posta formatını destekler ve bellek kullanımını düşük tutarak çok sayfalı mesajları işleyebilir.

## MSG'yi MHTML'ye neden dönüştürmeliyiz?

MSG dosyalarını MHTML'ye dönüştürmek, herhangi bir modern tarayıcıda açılabilen web‑uyumlu, tek dosya temsili sağlar. Bu format, özgün stil, gömülü görseller ve ekleri korur, bu da **yasal arşivleme**, **çok platformlu paylaşım** ve **e‑postaları web sayfalarına veya belgelere yerleştirme** için idealdir.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli kütüphaneler ve bağımlılıklar
- **Aspose.Email for Java** kütüphane sürümü 25.4 (jdk16 sınıflandırıcı) – kütüphane **50+** giriş ve çıkış e‑posta formatını destekler.
- Temel Java bilgisi.
- IntelliJ IDEA veya Eclipse gibi bir IDE.

### Ortam kurulum gereksinimleri
- JDK 16 veya daha yeni bir sürüm yüklü.
- Bağımlılık yönetimi için Maven.

## Aspose.Email for Java kurulumu

Kütüphaneyi bir Maven projesine eklemek için aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme adımları

Kütüphanenin tam yeteneklerini sınırsız olarak değerlendirmek için **ücretsiz deneme** ile başlayın veya **geçici lisans** alın. Uzun vadeli kullanım için bir lisans satın almayı düşünün:

- [Ücretsiz Deneme](https://releases.aspose.com/email/java/)
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)

### Temel başlatma

`License` sınıfı, tam özellikleri açmak için Aspose.Email lisansınızı kaydeder.  
Bağımlılığı ekledikten sonra, Java kodunuzda lisansı başlatın:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## msg dosyasını nasıl yükleyip MHTML olarak kaydedilir?

MSG dosyasını yükleyin, zaman damgasını ayarlayın ve üç basit adımda MHTML olarak kaydedin. İlk olarak, `MsgLoadOptions` kullanarak MSG dosyasından bir `MailMessage` örneği oluşturun. Sonra, `setTimeZoneOffset` ile istediğiniz saat dilimi kaymasını ayarlayın. Son olarak, `MhtSaveOptions` yapılandırın ve `save` çağrısıyla MHTML arşivini oluşturun.

### Özellik 1: bir dosyadan MailMessage yükleme

`MailMessage` sınıfı, başlıklar, gövde ve ekler içeren bir e‑posta mesajını temsil eder.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` MSG dosyasının nasıl ayrıştırılacağını kontrol etmenizi sağlar; varsayılan ayarlar çoğu senaryo için çalışır.

### Özellik 2: geçerli tarihi ve özel saat dilimi kaymasını ayarlama

`Date` nesnesi, e‑postanın **Date** başlığına yazılacak zaman damgasını tutar.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Kayma milisaniye cinsinden ifade edilir; UTC+5 için `5 * 60 * 60 * 1000` geçersiniz.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Özellik 3: MailMessage'ı MHTML dosyası olarak kaydetme

`MhtSaveOptions` e‑postanın bir MHTML arşivine nasıl paketleneceğini tanımlar, satır içi görselleri ve ekleri korur.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Oluşan `.mhtml` dosyası özgün biçimlendirmeyi, görselleri ve ekleri korur, böylece orijinal MSG'nin doğru bir görsel kopyasını oluşturur.

## Özel saat dilimi kayması nasıl ayarlanır?

`MailMessage` örneği üzerinde `setTimeZoneOffset` çağırarak saat dilimini değiştirebilirsiniz. Metot milisaniye cinsinden bir kayma bekler, hem pozitif (UTC'nin doğusunda) hem de negatif (UTC'nin batısında) değerleri kabul eder. Örneğin, UTC‑3 için `-3 * 60 * 60 * 1000` kullanılır.

## MSG dosyalarını toplu olarak nasıl işlersiniz?

Üç adımlı iş akışını, bir `.msg` dosyaları dizininde dönen bir döngü içinde sarın. Tek bir `License` örneğini yeniden kullanarak tekrar tekrar I/O'dan kaçının ve her `MailMessage`'ı kaydettikten sonra serbest bırakın, böylece bellek kullanımı düşük kalır.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Toplu işleme ipuçları
1. **Lisansı yeniden kullanın** – uygulama başlangıcında bir kez `new License().setLicense(...)` çağırın.
2. **try‑with‑resources** kullanarak akışların otomatik temizlenmesini sağlayın.
3. **Başarısızlıkları** ayrı bir dosyaya kaydedin, böylece sorunlu mesajları daha sonra yeniden deneyebilirsiniz.
4. **Paralellik** düşünün; büyük toplular için `ForkJoinPool` kullanın, ancak her iş parçacığının kendi `MailMessage` örneğini kullandığından emin olun.

## Yaygın sorunlar ve çözümler

- **Büyük MSG dosyalarında bellek dalgalanmaları** – `MailMessage.load(InputStream, MsgLoadOptions)` kullanarak akışlamayı etkinleştirin ve akışı parçalar halinde işleyin.
- **Yanlış zaman damgaları** – kaymaları uygulamadan önce sistem saatinin UTC olarak ayarlandığını doğrulayın veya açıkça bir `java.util.Calendar` örneği geçirin.
- **MHTML'de eksik ekler** – `MhtSaveOptions.setWriteHeader(true)` ayarlandığından emin olun; bu ekleri `cid:` kaynakları olarak gömer.

## Sıkça sorulan sorular

**Q:** .msg dışındaki formatlardan e‑postaları yükleyebilir miyim?  
**A:** Evet, Aspose.Email EML, MHT, EMLX ve birkaç diğer formatı destekler, toplamda 30'dan fazla giriş türü vardır.

**Q:** Çok büyük e‑posta dosyalarını verimli bir şekilde nasıl yönetebilirim?  
**A:** `MailMessage.load(InputStream, ...)` gibi akış API'lerini kullanarak verileri parça parça okuyup yazın; bu, 500 sayfalık mesajlarda bile bellek tüketimini 50 MB'ın altında tutar.

**Q:** Bir MailMessage içindeki ekleri değiştirmek mümkün mü?  
**A:** Kesinlikle. `msg.getAttachments()` koleksiyonu üzerinden ekleri ekleyebilir, kaldırabilir veya değiştirebilir, ardından değişiklikleri kalıcı kılmak için `save` çağırabilirsiniz.

**Q:** Saat dilimi kaymam negatif (UTC'nin gerisinde) ise ne olur?  
**A:** `setTimeZoneOffset` metoduna negatif bir milisaniye değeri geçirin, örneğin UTC‑3 için `-3 * 60 * 60 * 1000`.

**Q:** Aspose.Email'i ticari projelerde kullanabilir miyim?  
**A:** Evet, geçerli bir ticari lisansınız olduğu sürece kullanabilirsiniz. Ücretsiz deneme sürümü belge başına 20 MB ile sınırlıdır.

**Q:** Binlerce MSG dosyasını bellek tükenmeden nasıl işleyebilirim?  
**A:** Dosyaları partiler halinde işleyin, her `MailMessage`'ı kaydettikten sonra serbest bırakın ve otomatik temizlik için Java’nın `try‑with‑resources` desenini kullanın.

## Kaynaklar
- [belgeleme](https://reference.aspose.com/email/java/)
- [Belgeleme](https://reference.aspose.com/email/java/)
- [Kütüphaneyi İndir](https://releases.aspose.com/email/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/email/java/)
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/email/10)

---

**Son Güncelleme:** 2026-08-27  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email for Java Kullanarak Outlook MSG Dosyalarını Yükleme ve Ayrıştırma: Kapsamlı Rehber](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email for Java: E‑postaları MHT Dosyaları Olarak Kaydet](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Aspose.Email for Java Kullanarak msg dosyalarından ekleri çıkarmak](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}