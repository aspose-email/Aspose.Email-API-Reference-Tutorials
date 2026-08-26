---
date: '2026-07-27'
description: Aspose.Email for Java kullanarak outlook flag'ı nasıl ayarlayacağınızı
  öğrenin; flag creation, recipient flags, completion, removal ve reading options
  konularını kapsar.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Aspose.Email for Java ile outlook flag java ayarlayın. Bu kılavuz,
  Outlook follow‑up flags'ı verimli bir şekilde create, read, complete ve remove etmeyi
  gösterir.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Outlook Flag'ı Ayarlama (Java) – Tam Aspose.Email Programlama Kılavuzu
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Outlook Flag'ı Ayarlama (Java) – Tam Aspose.Email Programlama Kılavuzu
url: /tr/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook Bayrağını Java ile Ayarlama (Aspose.Email for Java kullanarak)

## Giriş
Programlı olarak **set outlook flag java** ayarlamanız gerekiyorsa doğru yerdesiniz. Outlook'un takip bayrağı normal bir e‑postayı izlenen bir göreve dönüştürür ve Aspose.Email for Java, Outlook yüklü olmadan bu bayrakları yönetmenizi sağlar. Bu öğreticide bayrak oluşturma, okuma, tamamlama ve sonunda kaldırma adımlarını, ayrıca belirli alıcılar için bayrak uygulamayı ele alacağız. Sonunda, arka uç hizmetlerinizden görev takibini otomatikleştiren yeniden kullanılabilir bir Java kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **“set outlook flag java” ne anlama geliyor?** Java kodu aracılığıyla bir Outlook öğesine başlangıç, hatırlatma ve son tarihleri içeren bir bayrak eklemek.  
- **Hangi kütüphane gerekiyor?** Aspose.Email for Java (v25.4 veya daha yeni).  
- **Lisans gerekir mi?** Evet – değerlendirme için bir deneme sürümü çalışır, ancak üretim için satın alınmış bir lisans gereklidir.  
- **Sadece alıcılar için bayrak ayarlayabilir miyim?** Kesinlikle – `FollowUpManager.setFlagForRecipients` kullanın.  
- **Daha sonra bayrağı kaldırmak mümkün mü?** Evet – `FollowUpManager.clearFlag` çağırın.

## Outlook Takip Bayrağı Nedir?
Outlook takip bayrağı, herhangi bir posta öğesine başlangıç tarihi, hatırlatma ve son tarih ekleyebilen yerleşik bir görev işaretçisidir. Bir e‑postayı izlenen bir eylem öğesine dönüştürerek siz ve ekibinizin bekleyen işleri takip etmenize yardımcı olur.

## Neden Aspose.Email for Java Kullanmalı?
Aspose.Email for Java **70+ e‑posta formatını** (MSG, EML, MHTML ve TNEF dahil) destekler ve tipik bir 8‑çekirdek sunucuda **dakikada 100.000'den fazla mesaj** işleyebilir; tüm bunlar host makinede Outlook gerektirmez. Bu, arka uç otomasyonu, uyumluluk raporlaması ve proje‑yönetim araçlarıyla entegrasyon için idealdir.

## Önkoşullar
- **Aspose.Email for Java** sürüm 25.4 veya üzeri.  
- **JDK 16+** yüklü.  
- Maven‑uyumlu IDE (IntelliJ IDEA, Eclipse vb.).  
- Temel Java bilgisi ve e‑posta kavramlarına aşinalık.

## Aspose.Email for Java Kurulumu
### Maven Yapılandırması
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alımı
Aspose.Email, üretim kullanımı için bir lisans gerektirir:

- **Ücretsiz deneme** – 30‑günlük değerlendirme.  
- **Geçici lisans** – uzatılmış test.  
- **Tam lisans** – süresiz abonelik.

Herhangi bir e‑posta işlemi yapmadan önce lisansı başlatın:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook Bayrağını Java ile Ayarlama (Özellik 1)
### Direkt cevap
`MailMessage` yükleyin, `MapiMessage`'a dönüştürün, `FollowUpOptions` yapılandırın ve `FollowUpManager.setOptions` çağırın. Bu sıra, sadece birkaç satır Java koduyla tamamen bayraklı bir Outlook öğesi oluşturur.

### Adım 1: Mesajı Oluştur ve Başlat
`MailMessage`, Aspose.Email'in e‑posta temsil eden yüksek‑seviye sınıfıdır. Mesajı oluşturduktan sonra bayrak manipülasyonu için `MapiMessage`'a dönüştürürsünüz.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*İlk olarak bir `MailMessage` oluşturur, gönderici/alıcı ayarları yapar ve ardından bayrak manipülasyonu için bir `MapiMessage`'a dönüştürürüz.*

### Adım 2: Takip Tarihlerini Tanımla (Outlook Bayrak Hatırlatıcısı)
`FollowUpOptions`, başlangıç, hatırlatma ve son tarihleri tutar. Kesin zaman damgalarını ayarlamak için Java’nın `Calendar` sınıfını kullanın.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Burada `Calendar` sınıfını kullanarak başlangıç, hatırlatma (**outlook flag reminder**) ve son tarihleri ayarlıyoruz.*

### Adım 3: Takip Seçeneklerini Uygula
`FollowUpManager.setOptions` yöntemi bayrağı `MapiMessage`'a ekler.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` nesnesi tüm bayrak detaylarını içerir; bu nesneyi `FollowUpManager.setOptions` ile uygularız.*

### Adım 4: Mesajı Kaydet
Bayraklı mesajı bir `.msg` dosyası olarak kaydedin, böylece Outlook bayrağı gösterebilir.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Mesaj, bayrak eklenmiş bir `.msg` dosyası olarak kaydedilir.*

## Alıcılar İçin Bayrak Nasıl Ayarlanır (Özellik 2)?
`FollowUpManager.setFlagForRecipients` yöntemini, mesajı taslak olarak işaretledikten sonra kullanın. Bu yöntem bayrağı yalnızca alıcının kopyasına ekler, göndericinin görünümünü değiştirmez. Bayrak uygulamadan önce `MessageFlags.MSGFLAG_UNSENT` ayarlanmalıdır. Ayrıca `FollowUpOptions` nesnesiyle başlangıç, hatırlatma ve son tarihleri özelleştirebilirsiniz.

### Direkt cevap
Mesajı `MessageFlags.MSGFLAG_UNSENT` ile taslak olarak işaretleyin, ardından `FollowUpManager.setFlagForRecipients` çağırın. Outlook bayrağı yalnızca alıcılara gösterilir, göndericiye gösterilmez.

### Genel Bakış
Bazen bayrağın **yalnızca alıcılar için** görünmesi gerekir. Bu örnek önce mesajı taslak olarak işaretler, ardından bayrağı ekler.

#### Adım 1: Taslak Olarak İşaretle
`MessageFlags`, mesajın durumunu kontrol eden bir MAPI enum'ıdır. `MSGFLAG_UNSENT` ayarı Outlook'a öğenin bir taslak olduğunu söyler.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Mesajın gönderilmemiş olarak işaretlenmesi, Outlook'un onu taslak olarak ele almasını sağlar.*

#### Adım 2: Alıcı Bayrağını Ayarla
`FollowUpManager.setFlagForRecipients` bayrağı yalnızca alıcının kopyasına ekler.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Bayrak artık yalnızca alıcılara görünür – klasik bir **flag for recipients** senaryosu.*

## Outlook Takip Bayrağını Tamamlandı Olarak İşaretleme (Özellik 3)?
`.msg` dosyasını bir `MapiMessage` içine yükleyin, ardından `FollowUpManager.completeFlag` çağırın. Bu, bayrak durumunu Tamamlandı olarak günceller ve Outlook'ta bir onay işareti ekler. Tamamladıktan sonra değişikliği kalıcı kılmak için mesajı kaydedin. Gerekirse denetim amaçlı `FlagCompleteTime` özelliğini ayarlayarak tamamlama zamanını belirtebilirsiniz.

### Direkt cevap
Mevcut `.msg` dosyasını bir `MapiMessage` içine yükleyin, `FollowUpManager.completeFlag` çağırın ve dosyayı kaydedin. Bayrak durumu “Completed” olarak değişir ve Outlook'ta bir onay işaretiyle görünür.

### Adım 1: Mesajı Yükle
`MapiMessage`, kaydedilmiş bir `.msg` dosyasını okuyabilir ve tüm MAPI özelliklerine tam erişim sağlar.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Adım 2: Tamamlandı Olarak İşaretle ve Kaydet
`FollowUpManager.completeFlag` bayrak durumunu günceller; ardından değişiklikleri kalıcı hâle getirirsiniz.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Bayrak durumu “Completed” olarak değişir ve güncellenmiş dosya kaydedilir.*

## Outlook Takip Bayrağını Kaldırma (Özellik 4)?
`.msg` dosyasını `MapiMessage` ile açın, `FollowUpManager.clearFlag` yöntemini çağırın ve ardından mesajı kaydedin. Bu, tüm bayrak‑ilişkili MAPI özelliklerini kaldırır; Outlook artık herhangi bir takip göstergesi göstermez. Görev iptal edildiğinde veya artık ilgili olmadığında bunu kullanın. Kalan hatırlatma bildirimlerini önlemek için özel hatırlatma özelliklerini de temizlemeyi unutmayın.

### Direkt cevap
`.msg` dosyasını `MapiMessage` ile açın, `FollowUpManager.clearFlag` çağırın ve dosyayı kaydedin. Mesaj Outlook'ta artık hiçbir takip göstergesi göstermez.

### Adım 1: Yükle ve Bayrağı Temizle
`FollowUpManager.clearFlag` mesajın tüm bayrak‑ilişkili özelliklerini kaldırır.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Mesaj, herhangi bir takip bayrağı olmadan kaydedilir.*

## Bayrak Seçeneklerini Okuma (Özellik 5)?
Yüklenmiş bir `MapiMessage` üzerinde `FollowUpManager.getOptions` çağırarak bir `FollowUpOptions` nesnesi alın. Bu nesne başlangıç, son, hatırlatma tarihlerini ve bayrak konusunu sağlar; böylece bayrak detaylarını görüntüleyebilir veya kaydedebilirsiniz. Raporlama ve uyumluluk denetimleri için faydalıdır.

### Direkt cevap
Yüklenmiş bir `MapiMessage` üzerinde `FollowUpManager.getOptions` kullanarak, başlangıç, son, hatırlatma tarihleri ve bayrak konusunu içeren bir `FollowUpOptions` nesnesi alın. Bu, raporlama veya uyumluluk denetimleri için kullanışlıdır.

### Adım 1: Seçenekleri Al
Dönen `options` nesnesi bayrağın yapılandırmasına tam görünürlük sağlar.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` nesnesi artık başlangıç, son ve hatırlatma tarihlerini ve bayrak konusunu içerir – raporlama için **read flag options** gerektiğinde faydalıdır.*

## Pratik Uygulamalar
- **Görev‑Yönetimi Entegrasyonu:** Bayraklı e‑postaları Jira, Trello veya Azure Boards ile senkronize edin.  
- **Otomatik Hatırlatıcılar:** Bekleyen takipler için günlük hatırlatma e‑postaları oluşturun.  
- **Uyumluluk Denetimleri:** Bayrak verilerini düzenleyici raporlamalar için dışa aktarın; bayrak seçeneklerini programlı olarak okuma yeteneğinden yararlanın.

## Performans Düşünceleri
- **Tarih Hesaplamaları:** Döngüler içinde değil, toplu işlem başına bir kez tarihleri hesaplayın.  
- **Kaynak Yönetimi:** Mesajları kaydettikten sonra tüm akışları veya dosya tutucularını kapatın.  
- **Bellek Kullanımı:** Büyük posta kutularını parçalar halinde işleyerek yığın (heap) baskısını önleyin; Aspose.Email, tüm dosyayı belleğe yüklemeden çok sayfalı posta kutularını işleyebilir.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-------|
| Bayrak Outlook'ta görünmüyor | `MessageFlags` doğru ayarlanmadan mesaj kaydedildi | Alıcı bayrakları uygulamadan önce `setMessageFlags` değerinin `MSGFLAG_UNSENT` olduğundan emin olun. |
| Kaydetme sırasında `AccessDeniedException` alınıyor | Yanlış dosya yolu veya yazma izni eksikliği | Çıktı dizininin var olduğunu ve uygulamanın yazma iznine sahip olduğunu doğrulayın. |
| Tarihler bir gün eksik | Zaman dilimi uyumsuzluğu | `TimeZone.getTimeZone("GMT")` ya da yerel saat diliminizi tutarlı şekilde kullanın. |

## Sık Sorulan Sorular
**S: Aspose.Email for Java nedir?**  
C: Outlook yüklü olmadan e‑posta dosyalarını (MSG, EML vb.) oluşturmanıza, okumanıza ve manipüle etmenize olanak tanıyan saf Java API'sidir.

**S: Ücretsiz deneme lisansı nasıl alınır?**  
C: 30‑günlük deneme sürümünü indirmek için [Aspose web sitesini](https://releases.aspose.com/email/java/) ziyaret edin.

**S: Tek bir mesajda birden fazla takip bayrağı ayarlayabilir miyim?**  
C: Outlook bir mesajda yalnızca bir bayrağa izin verir, ancak ek görev verilerini özel MAPI özelliklerinde saklayabilirsiniz.

**S: Bayrak ayarladıktan sonra mesaj kaydedilmiyor. Ne kontrol etmeliyim?**  
C: `outputDir` yolunun geçerli olduğundan ve uygulamanın bu konuma yazma iznine sahip olduğundan emin olun.

**S: Birçok mesajdan bayrakları toplu olarak nasıl kaldırırım?**  
C: Mesaj koleksiyonunuzu döngüye alıp her `MapiMessage` üzerinde `FollowUpManager.clearFlag` çağırın.

## Kaynaklar
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Manage Outlook Categories with Aspose.Email for Java - A Comprehensive Guide](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Create outlook notes java with Aspose.Email – Full Guide](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Create Tasks in Microsoft Exchange Using Aspose.Email for Java: A Complete Guide](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}