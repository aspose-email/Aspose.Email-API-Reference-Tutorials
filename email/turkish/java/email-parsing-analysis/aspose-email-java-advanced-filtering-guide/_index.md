---
date: '2026-04-11'
description: Aspose.Email for Java kullanarak e-postaları konu, tarih, gönderici ve
  alan adına göre nasıl filtreleyeceğinizi öğrenin. Gelişmiş filtreleme ile gelen
  kutusu yönetimini kolaylaştırın.
keywords:
- filter emails by subject
- filter emails by date
- filter emails by sender
- filter emails by domain
title: Aspose.Email for Java ile konuya göre e-postaları filtreleyin
url: /tr/java/email-parsing-analysis/aspose-email-java-advanced-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Konuya göre e-postaları filtreleme Aspose.Email for Java

## Giriş

Yoğun bir gelen kutusunu yönetmek, günümüz dijital dünyasında zordur. Günlük yüzlerce e-posta arasında geziniyor ya da e-posta yönetim sürecinizi optimize etmeye çalışıyor olun, gelişmiş filtreleme çözümleri hayati öneme sahiptir. **Bu öğreticide, konuya göre e-postaları nasıl filtreleyeceğinizi öğreneceksiniz**, ayrıca tarih, gönderici ve alan adı gibi güçlü kriterleri de Aspose.Email for Java kullanarak. Aspose.Email for Java ile geliştiriciler, e-postaları verimli bir şekilde filtreleyebilir ve yönetebilir. Bu kılavuz, Aspose.Email for Java kullanarak çeşitli e-posta filtreleme özelliklerini uygulamanız için adım adım yol gösterir.

**Öğrenecekleriniz:**
- Aspose.Email for Java'ı kurma
- Mesajları konu, tarih, gönderici, alan adı ve alıcıya göre filtreleme
- Sorguları mantıksal VE/VEYA işlemleriyle birleştirme
- E-posta filtrelerinde büyük/küçük harf duyarlılığını anlama

Bu rehberin sonunda, e-posta işleme mantığınızı belirli ihtiyaçlara göre özelleştirebileceksiniz. Önkoşullarla başlayalım.

## Hızlı Yanıtlar
- **Exchange posta kutularını sorgulamak için birincil sınıf nedir?** `MailQueryBuilder` esnek filtre ifadeleri oluşturmanıza olanak tanır.  
- **Bir sorguda hem konu hem de tarih ile e-postaları filtreleyebilir miyim?** Evet—aynı `MailQueryBuilder` üzerinde koşulları zincirleyin.  
- **Bugün gelen mesajları nasıl filtrelerim?** `builder.getInternalDate().on(new Date())` kullanın.  
- **Büyük/küçük harf duyarlı filtreleme destekleniyor mu?** `contains` metoduna ikinci argüman olarak `true` geçin.  
- **Üretim kullanımı için lisansa ihtiyacım var mı?** Geçerli bir Aspose.Email lisansı, tüm özellikleri sınırsız olarak açar.

## Önkoşullar

Aspose.Email for Java ile gelişmiş e-posta filtreleme uygulamaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Gerekli Kütüphaneler:** Aspose.Email for Java sürüm 25.4
- **Ortam Kurulumu:** En az 16 sürümünde bir Java Development Kit (JDK) gereklidir.
- **Bilgi Önkoşulları:** Java programlamaya temel bir anlayış ve e-posta protokollerine aşinalık.

## Aspose.Email for Java'ı Kurma

Başlamak için, projenize Aspose.Email kütüphanesini ekleyin. Maven kullanıyorsanız, aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alımı

Aspose.Email'i tam olarak kullanabilmek için bir lisansa ihtiyacınız olacak. Ücretsiz deneme ile başlayabilir veya değerlendirme amaçlı geçici bir lisans talep edebilirsiniz. Üretim kullanımı için tüm özellikleri açmak adına bir lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum

Gerekli kimlik bilgileriyle `ExchangeClient`'inizi başlatın:

```java
ExchangeClient client = new ExchangeClient("YOUR_DOCUMENT_DIRECTORY", "username", "password", "domain");
```

## Uygulama Kılavuzu

Bu bölüm, karmaşık e-posta filtreleme işlevlerini yönetilebilir adımlara ayırarak uygulamanızı sağlar.

### Konu ve Tarihe Göre Mesajları Filtreleme

**Genel Bakış:** Bu işlev, belirli konu anahtar kelimeleri ve dahili tarihlere göre bir Exchange posta kutusundaki e-postaları filtreler.

#### Adım Adım Uygulama:
1. **Sorgu Oluşturucuyu Başlatın:**
   ```java
   SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
   ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
   builder.getSubject().contains("Newsletter");
   ```
2. **Tarih Filtresini Ayarlayın:**
   ```java
   try {
       builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
   } catch (ParseException e) {
       e.printStackTrace(); // Handle parsing errors gracefully
   }
   ```
3. **Sorguyu Çalıştırın:**
   ```java
   MailQuery query = builder.getQuery();
   ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
   ```

### Günün Tarihine Göre Mesajları Filtreleme

**Genel Bakış:** Bugün gelen e-postaları alın.

#### Uygulama:
1. **Sorguyu Oluşturun:**
   ```java
   MailQueryBuilder builderToday = new MailQueryBuilder();
   builderToday.getInternalDate().on(new Date());
   ```
2. **Mesajları Listele:**  
   `client.listMessages()` metodunu önceki örneklerdeki gibi kullanarak sorgunuzu çalıştırın; belirli tarihi bugünün tarihiyle değiştirin.

### Belirli Bir Tarih Aralığında Mesajları Filtreleme

**Genel Bakış:** Bugünden önce ve bir gün öncesinden itibaren alınan e-postaları filtreleyin.

#### Uygulama:
1. **Tarih Aralığını Yapılandırın:**
   ```java
   MailQueryBuilder builderDateRange = new MailQueryBuilder();
   builderDateRange.getInternalDate().beforeOrEqual(new Date());
   builderDateRange.getInternalDate().since(new Date(System.currentTimeMillis() - TimeUnit.DAYS.toMillis(1)));
   ```

### Belirli Göndericiye Göre Mesajları Filtreleme

**Genel Bakış:** Belirli bir göndericiden gelen e-postaları alın.

#### Uygulama:
1. **Sorguyu Ayarlayın:**
   ```java
   MailQueryBuilder builderSender = new MailQueryBuilder();
   builderSender.getFrom().contains("saqib.razzaq@127.0.0.1");
   ```

### Belirli Alan Adına Göre Mesajları Filtreleme

**Genel Bakış:** Belirli bir alan adından gelen e-postaları alın.

#### Uygulama:
1. **Alan Adına Dayalı Filtreleme:**
   ```java
   MailQueryBuilder builderDomain = new MailQueryBuilder();
   builderDomain.getFrom().contains("SpecificHost.com");
   ```

### Belirli Alıcıya Gönderilen Mesajları Filtreleme

**Genel Bakış:** Belirli bir alıcıya gönderilen e-postaları alın.

#### Uygulama:
1. **Alıcı Sorgusu Ayarı:**
   ```java
   MailQueryBuilder builderRecipient = new MailQueryBuilder();
   builderRecipient.getTo().contains("recipient@example.com");
   ```

### Sorguları AND Mantığıyla Birleştirme

**Genel Bakış:** Birden fazla koşulu mantıksal AND işlemleriyle birleştirin.

#### Uygulama:
1. **Birleştirilmiş Koşulları Ayarlayın:**
   ```java
   MailQueryBuilder builderAnd = new MailQueryBuilder();
   builderAnd.getFrom().contains("SpecificHost.com");
   builderAnd.getInternalDate().before(new Date());
   builderAnd.getInternalDate().since(new Date(System.currentTimeMillis() + TimeUnit.DAYS.toMillis(-7)));
   ```

### Sorguları OR Mantığıyla Birleştirme

**Genel Bakış:** Mantıksal OR koşullarıyla e-postaları alın.

#### Uygulama:
1. **VEYA Koşulu Ayarı:**
   ```java
   MailQueryBuilder builderOr = new MailQueryBuilder();
   builderOr.or(builderOr.getSubject().contains("test"), builderOr.getFrom().contains("noreply@host.com"));
   ```

### Büyük/Küçük Harf Duyarlılığına Göre Mesajları Filtreleme

**Genel Bakış:** E-posta adresleri için büyük/küçük harf duyarlı filtreler kullanın.

#### Uygulama:
1. **Büyük/Küçük Harf Duyarlı Filtreleme:**
   ```java
   MailQueryBuilder builderCaseSensitive = new MailQueryBuilder();
   builderCaseSensitive.getFrom().contains("tesT", true);
   ```

## Pratik Uygulamalar

- **Otomatik E-posta Sıralama:** Konu satırları veya gönderenlere göre e-postaları otomatik olarak kategorilere ayırın.  
- **Güvenlik Filtreleri:** Gönderen alan adına göre olası kimlik avı girişimlerini belirleyin ve filtreleyin.  
- **Pazarlama Analizi:** Bültenleri ve tanıtım e-postalarını pazarlama içgörüleri için izleyin.  
- **Zaman‑Tabanlı Arşivleme:** Belirli tarih aralıklarında alınan e-postaları uyumluluk amaçları için arşivleyin.

## Performans Düşünceleri

Büyük miktarda e-posta verisi işlenirken performansı optimize etmek kritiktir:

- Kaynak kullanımını en aza indirmek için verimli sorgular kullanın.  
- Geniş veri setleriyle çalışıyorsanız bellek aşımını önlemek için sayfalama (paging) uygulayın.  
- Uygulama performansını düzenli olarak profil ve izleyin.

## Yaygın Sorunlar ve Çözümler

| Sorun | Tipik Neden | Önerilen Çözüm |
|-------|-------------|----------------|
| **ParseException** when parsing dates | Yanlış tarih formatı | Giriş dizesiyle eşleşen bir `SimpleDateFormat` kullanın ve her zaman `try‑catch` içinde sarın. |
| No results returned | Filtreler çok kısıtlayıcı | Kriterleri gevşetin veya posta kutusunun gerçekten eşleşen mesajlar içerdiğini doğrulayın. |
| Case‑sensitivity not respected | `contains` metoduna `true` bayrağı eklenmemiş | Büyük/küçük harf duyarlı eşleşmeyi zorlamak için ikinci argüman olarak `true` geçin. |
| Large mailbox slows down query | Sayfalama eksik | Sonuçları parçalar halinde almak için `client.listMessages(..., pageSize, pageNumber)` kullanın. |

## SSS Bölümü

**S1: Tarih filtrelerinde ParseException hatasını en iyi nasıl yönetebilirim?**  
- **C:** `sdf.parse()` çağrılarını her zaman `try‑catch` blokları içinde sararak istisna durumlarını sorunsuz bir şekilde ele alın.

**S2: Aspose.Email for Java'yı Exchange dışındaki diğer e-posta protokolleriyle kullanabilir miyim?**  
- **C:** Evet, Aspose.Email IMAP ve POP3 dahil çeşitli protokolleri destekler. Ayrıntılar için belgelere bakın.

**S3: Büyük posta kutularında sorgu performansını nasıl optimize edebilirim?**  
- **C:** Filtre koşullarını mümkün olduğunca daraltın ve sayfalama mekanizmalarını kullanmayı düşünün.

**S4: Ücretsiz deneme sonrası hemen lisans satın almam gerekiyor mu?**  
- **C:** Ücretsiz deneme değerlendirme için mükemmeldir, ancak lisans satın alındığında tüm özellikler sınırsız olarak açılır.

**S5: Aspose.Email'i diğer Java uygulamalarıyla nasıl entegre ederim?**  
- **C:** Aspose.Email'i Java projenize bir kütüphane olarak ekleyin. Entegrasyon oldukça basittir.

**S6: AND/OR mantığıyla iki’den fazla koşulu birleştirebilir miyim?**  
- **C:** Evet—aynı `MailQueryBuilder` üzerinde ek koşulları zincirleyebilir veya gerektiğinde OR çağrılarını iç içe kullanabilirsiniz.

**S7: Büyük/küçük harf duyarlı filtreleme konu satırı için de çalışıyor mu?**  
- **C:** Kesinlikle. Konu satırı dahil herhangi bir alanı büyük/küçük harf duyarlı eşleştirmek için `contains` metoduna `true` geçin.

---

**Son Güncelleme:** 2026-04-11  
**Test Edilen:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}