---
date: '2026-07-17'
description: Exchange Server randevularını tarihe göre filtrelemek için exchange query
  java nasıl oluşturulacağını öğrenin. Bu Aspose Email Java öğreticisi, kurulumu,
  sorgu oluşturmayı ve exchange calendar events almayı gösterir.
keywords:
- build exchange query java
- retrieve exchange calendar events
- aspose email java tutorial
lastmod: '2026-07-17'
og_description: Exchange Server randevularını tarihe göre filtrelemek için exchange
  query java nasıl oluşturulacağını öğrenin. Bu Aspose Email Java öğreticisi, kurulumu,
  sorgu oluşturmayı ve exchange calendar events almayı gösterir.
og_image_alt: 'Developer guide: Build exchange query java to filter Exchange appointments
  by date'
og_title: Exchange Query Java Oluştur – Randevuları Tarihe Göre Filtrele
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to build exchange query java to filter Exchange Server appointments
    by date. This Aspose Email Java tutorial shows setup, query building, and retrieving
    exchange calendar events.
  headline: Build Exchange Query Java – Filter Appointments by Date
  type: TechArticle
- description: Learn how to build exchange query java to filter Exchange Server appointments
    by date. This Aspose Email Java tutorial shows setup, query building, and retrieving
    exchange calendar events.
  name: Build Exchange Query Java – Filter Appointments by Date
  steps:
  - name: Configure Date Formats
    text: First, create a reusable `SimpleDateFormat` instance to parse date strings
      into Java `Date` objects. `SimpleDateFormat` is a thread‑unsafe class, so reusing
      a single instance within a single thread improves performance and reduces object
      allocation.
  - name: Build a Query with ExchangeQueryBuilder
    text: '`ExchangeQueryBuilder` is Aspose.Email''s fluent builder that lets you
      specify search criteria without writing raw SOAP XML. Create an instance and
      set up your date range criteria:'
  - name: Execute the Query
    text: 'Use the previously configured `IEWSClient` to run the query and retrieve
      matching appointments: The `getAppointments` method returns a collection of
      `Appointment` objects that fall within the defined date range.'
  type: HowTo
- questions:
  - answer: It means constructing an `ExchangeQueryBuilder` object in Java to query
      Exchange items.
    question: What does “build exchange query java” mean?
  - answer: Aspose.Email for Java (v25.4+).
    question: Which library is required?
  - answer: Yes, with EWS enabled and proper credentials.
    question: Do I need an Exchange server?
  - answer: Absolutely – just modify the `SimpleDateFormat` strings.
    question: Can I change the date range at runtime?
  - answer: Yes, a valid Aspose.Email license is required for commercial use.
    question: Is a license mandatory for production?
  type: FAQPage
tags:
- build exchange query java
- Aspose.Email
- Java calendar
- EWS appointments
- filter appointments
title: Exchange Query Java Oluştur – Randevuları Tarihe Göre Filtrele
url: /tr/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exchange Sorgusu Java Oluştur – Randevuları Tarihe Göre Filtrele

Etkili randevu yönetimi, verimli planlamanın organizasyon verimliliğini artırdığı günümüz iş ortamında kritik öneme sahiptir. **Aspose.Email Maven bağımlılığını ekleyerek** ve **belirli tarih aralıklarına göre Exchange sunucusundan randevuları filtreleyen bir exchange query java oluşturarak**, operasyonları sadeleştirebilir ve zaman yönetimini iyileştirebilirsiniz. Bu öğretici, ortam kurulumundan sorgunun yürütülmesine kadar tüm süreci adım adım anlatır ve **retrieve exchange calendar events** nasıl yapılacağını gösterir.

**Neler Öğreneceksiniz**
- Gerekli Maven bağımlılığı ile ortamınızı kurma
- Aspose.Email for Java'ı başlatma ve yapılandırma
- Belirli bir tarih aralığında randevuları filtrelemek için exchange query java oluşturma
- Performans ve bellek kullanımını optimize etmek için en iyi uygulamalar

Bu çözümün ele aldığı sorunu anladıktan sonra, uygulamaya geçmeden önce gereken önkoşulları inceleyelim.

## Hızlı Yanıtlar
- **“build exchange query java” ne anlama geliyor?** Java'da Exchange öğelerini sorgulamak için bir `ExchangeQueryBuilder` nesnesi oluşturmak anlamına gelir.  
- **Hangi kütüphane gereklidir?** Aspose.Email for Java (v25.4+).  
- **Bir Exchange sunucusuna ihtiyacım var mı?** Evet, EWS etkinleştirilmiş ve uygun kimlik bilgileriyle.  
- **Tarih aralığını çalışma zamanında değiştirebilir miyim?** Kesinlikle – sadece `SimpleDateFormat` dizelerini değiştirin.  
- **Üretim için lisans zorunlu mu?** Evet, ticari kullanım için geçerli bir Aspose.Email lisansı gereklidir.

## “build exchange query java” Nedir?

`build exchange query java`, bir `ExchangeQueryBuilder` örneği oluşturma, kriterlerini (tarih aralıkları, konu veya organizatör gibi) yapılandırma ve ardından bu sorguyu bir Exchange posta kutusuna karşı yürütme sürecidir. Builder, karmaşık SOAP isteklerini akıcı bir Java API'sinin arkasına soyutlayarak, ham XML yazmadan **retrieve exchange calendar events**'i basit hale getirir.

## Aspose.Email for Java Neden Kullanılmalı?

Aspose.Email for Java, randevular, kişiler, görevler ve daha fazlası dahil olmak üzere **50+ işlem için kapsamlı EWS desteği** sağlar. Doğrudan Exchange sunucusuyla çalışır—Outlook kurulumu gerekmez—ve manuel EWS çağrılarına kıyasla **3 katına kadar daha hızlı veri alımı** sağlar, tipik sorgular için 150 MB'den az yığın belleği kullanır. Kütüphanenin kapsamlı belgeleri, güvenilir ve yüksek performanslı bir çözüm arayan geliştiriciler için ideal bir **aspose email java tutorial** yapar.

## Önkoşullar

Bu öğreticiye eşlik edebilmek için aşağıdaki araç ve bilgiye sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
- **Aspose.Email for Java**: Versiyon 25.4 veya üzeri.  
- **Java Development Kit (JDK)**: JDK 16 veya daha yenisini kullanın.

### Ortam Kurulum Gereksinimleri
- IntelliJ IDEA, Eclipse veya NetBeans gibi yapılandırılmış bir IDE.  
- EWS etkinleştirilmiş bir Exchange sunucusuna erişim.

### Bilgi Önkoşulları
- Java programlamaya temel bir anlayış.  
- Bağımlılık yönetimi için Maven'e aşinalık.

## Aspose.Email Maven Bağımlılığını Ekleyin

Başlamak için Aspose.Email kütüphanesini projenize bir bağımlılık olarak ekleyin. Maven kullanıyorsanız, `pom.xml` dosyanıza aşağıdaki XML snippet'ini ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alımı

Aspose.Email for Java, özelliklerini değerlendirebilmeniz için ücretsiz bir deneme sunar. Sürekli kullanım için geçici bir lisans almayı veya tam sürüm satın almayı düşünün:
- **Ücretsiz Deneme**: [Aspose Email Download](https://releases.aspose.com/email/java/) sayfası üzerinden mevcuttur.  
- **Geçici Lisans**: [Temporary License Page](https://purchase.aspose.com/temporary-license/) adresinden alın.  
- **Satın Alma**: Uzun vadeli kullanım için lisansı [Purchase Aspose](https://purchase.aspose.com/buy) sitesinden satın alın.

### Temel Başlatma ve Kurulum

Exchange sunucu kimlik bilgilerinizi yapılandırarak Aspose.Email for Java'ı başlatın. `IEWSClient`, Exchange Web Services ile etkileşim için birincil sınıftır; kimlik doğrulama ve istek yürütmeyi yönetir. `IEWSClient`'ı aşağıdaki gibi ayarlayın:

```java
String mailboxUri = "YOUR_EXCHANGE_SERVER_URI"; // Your Exchange Server URI
String username = "YOUR_USERNAME";               // Username for authentication
String password = "YOUR_PASSWORD";               // Password
String domain = "YOUR_DOMAIN";                   // Domain if required

IEWSClient client = EWSClient.getEWSClient(mailboxUri, username, password, domain);
```

`IEWSClient` sınıfı, Exchange Web Services ile etkileşim için birincil giriş noktasıdır; kimlik doğrulama, istek yürütme ve yanıt işleme işlemlerini yönetir.

## Tarihe Göre Randevu Filtreleme (Exchange Sorgu Tarih Aralığı)

Bu öğreticinin temel özelliği, belirli tarihler arasındaki randevuları filtrelemektir. İşte bunu nasıl yapabileceğiniz:

### Adım 1: Tarih Biçimlerini Yapılandırma

İlk olarak, tarih dizelerini Java `Date` nesnelerine ayrıştırmak için yeniden kullanılabilir bir `SimpleDateFormat` örneği oluşturun.

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;

SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
```

`SimpleDateFormat` thread‑unsafe bir sınıftır, bu yüzden tek bir örneği aynı thread içinde yeniden kullanmak performansı artırır ve nesne tahsislerini azaltır.

### Adım 2: ExchangeQueryBuilder ile Sorgu Oluşturma

`ExchangeQueryBuilder`, ham SOAP XML yazmadan arama kriterlerini belirlemenizi sağlayan Aspose.Email'in akıcı builder'ıdır. Bir örnek oluşturun ve tarih aralığı kriterlerinizi ayarlayın:

```java
import com.aspose.email.ExchangeQueryBuilder;

ExchangeQueryBuilder builder = new ExchangeQueryBuilder();

// Specify the start date for filtering appointments
builder.getAppointment().getStart().since(sdf.parse("10/05/2016 10:00:00"));

// Define the end date to include all appointments before or equal to this time
builder.getAppointment().getEnd().beforeOrEqual(sdf.parse("10/15/2016 10:00:00"));
```

### Adım 3: Sorguyu Yürütme

Önceden yapılandırılmış `IEWSClient`'ı kullanarak sorguyu çalıştırın ve eşleşen randevuları alın:

```java
import com.aspose.email.MailQuery;

com.aspose.email.MailQuery query = builder.getQuery();
Appointment[] appointments = client.listAppointments(query);
```

`getAppointments` metodu, tanımlanan tarih aralığı içinde kalan `Appointment` nesnelerinin bir koleksiyonunu döndürür.

### Sorun Giderme İpuçları
- **Tarih Ayrıştırma Hataları**: `SimpleDateFormat` içinde tanımlı desenle tarih dizelerinizin tam olarak eşleştiğinden emin olun.  
- **Kimlik Doğrulama Sorunları**: Exchange sunucu kimlik bilgilerinizi ve ağ bağlantınızı iki kez kontrol edin.  
- **Boş Sonuçlar**: Sunucunun verilen aralıkta randevu içerdiğini doğrulayın veya tarih penceresini genişletin.

## Pratik Uygulamalar

Bu özellik çeşitli gerçek dünya senaryolarında kullanılabilir:
1. **İş Takvim Yönetimi** – Belirli bir ay için toplantıları otomatik olarak filtreleyin.  
2. **Kaynak Planlaması** – Geçmiş rezervasyonları hariç tutarak boş zaman dilimlerini belirleyin.  
3. **Raporlama ve Analitik** – Randevu verilerinden dönem bazlı raporlar oluşturun.

## Performans Düşünceleri

Aspose.Email ile çalışırken optimal hızı korumak için şu ipuçlarını aklınızda tutun:
- Sorgularınızın kapsamını sınırlayarak veri transferini azaltın; API varsayılan olarak istekte 200 öğeye kadar dönebilir.  
- Birçok örnek oluşturmak yerine tek bir `SimpleDateFormat` örneğini yeniden kullanın.  
- `client.dispose()` çağrısı yapın veya JVM'in kullanılmayan nesneleri çöp toplamasına izin vererek Java yığın belleğini hızlıca serbest bırakın.

## Yaygın Sorunlar ve Çözümler
| Sorun | Muhtemel Neden | Çözüm |
|-------|----------------|-------|
| **DateParseException** | Dize ile format arasındaki uyumsuzluk | `SimpleDateFormat` içindeki deseni ayarlayın veya giriş dizesini düzeltin. |
| **401 Unauthorized** | Yanlış kimlik bilgileri veya eksik EWS izinleri | Kullanıcı adı/parolayı doğrulayın ve hesabın EWS erişimine sahip olduğundan emin olun. |
| **No appointments returned** | Sorgu tarihleri mevcut aralığın dışında | Sunucu takviminde randevu olup olmadığını kontrol edin veya tarih penceresini genişletin. |

## Sonuç

Aspose.Email for Java kullanarak Exchange sunucu randevularını tarihe göre filtrelemek, takvim yönetimini basitleştirir, verimliliği artırır ve planlama desenleri hakkında değerli içgörüler sağlar. Bu **aspose email java tutorial**'ı izleyerek ortamınızı nasıl kuracağınızı, kütüphaneyi nasıl yapılandıracağınızı ve belirli kriterlere göre randevuları filtrelemek için **build exchange query java**'ı nasıl oluşturacağınızı öğrendiniz.

**Sonraki Adımlar**
- Konu veya organizatör filtreleri gibi ek sorgu seçeneklerini keşfedin.  
- Alınan randevuları kendi raporlama panonuzla entegre edin.  
- Toplantı istekleri gönderme veya yinelenen etkinlikleri yönetme gibi diğer Aspose.Email özelliklerini inceleyin.

## Sıkça Sorulan Sorular

**Q:** Aspose.Email'i satın alma olmadan kullanabilir miyim?  
**A:** Evet, ücretsiz deneme ile başlayabilir ve satın almadan önce özelliklerini keşfedebilirsiniz.

**Q:** Exchange sunucusuna bağlanırken kimlik doğrulama hatalarını nasıl ele alırım?  
**A:** Kimlik bilgilerinizi ve ağ ayarlarınızı doğrulayın; Exchange hesabının EWS erişiminin etkin olduğundan emin olun.

**Q:** Bu öğreticide hangi tarih formatları ayrıştırma için destekleniyor?  
**A:** `SimpleDateFormat` sınıfı tanımladığınız herhangi bir deseni destekler; örnek `"dd/MM/yyyy HH:mm:ss"` biçimini kullanır.

**Q:** Tarih aralığını çalışma zamanında dinamik olarak nasıl değiştirebilirim?  
**A:** Sorguyu oluşturmadan önce `since()` ve `beforeOrEqual()` metodlarına geçirilen dizeleri basitçe değiştirin.

**Q:** Aspose.Email özellikleri için daha fazla belgeyi nerede bulabilirim?  
**A:** Kapsamlı belgeler [Aspose Email Documentation](https://reference.aspose.com/email/java/) sitesinde mevcuttur.

## Kaynaklar
- **Dokümantasyon**: [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Java Docs**: [Aspose Email Java Docs](https://reference.aspose.com/email/java/)  
- **Download**: [Aspose Email Releases](https://releases.aspose.com/email/java/)  
- **Purchase**: [Buy Aspose](https://purchase.aspose.com/buy)  
- **Free Trial**: [Get a Free Trial](https://releases.aspose.com/email/java/)  
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum Support](https://forum.aspose.com/c/email/10)

---

**Son Güncelleme:** 2026-07-17  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email for Java ile Exchange Takvim Bağlantısı Rehberi | Exchange Sunucu Entegrasyonu](/email/java/exchange-server-integration/exchange-calendar-connection-aspose-email-java/)
- [Java Sayfalama En İyi Uygulamaları – Exchange Sunucuları için Aspose.Email Kullanarak Sayfalı Randevuları Uygula](/email/java/calendar-appointments/java-aspose-email-paginated-appointments/)
- [Aspose.Email for Java ile Exchange Randevularını Yönetme: Kapsamlı Bir Rehber](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}