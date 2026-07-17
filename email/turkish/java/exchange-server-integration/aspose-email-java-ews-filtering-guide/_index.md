---
date: '2026-07-17'
description: 'Aspose.Email Java ve EWS kullanarak e-posta filtreleme: date, sender
  ve subject filtreleme tekniklerini öğrenerek mailbox''ınızı düzenleyin.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Aspose.Email Java ve EWS kullanarak e-posta filtreleme. date, sender
  ve subject filtreleme tekniklerini keşfedin ve mailbox'unuzu düzenli tutun.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Aspose.Email Java ve EWS ile E-posta Filtreleme
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Aspose.Email Java ve EWS ile E-posta Filtreleme Rehberi
url: /tr/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email Java & EWS ile E-posta Filtreleme Ustalığı: Tam Bir Kılavuz

## Giriş

**E-postaları nasıl filtreleyeceğiniz** verimli bir şekilde, Microsoft Exchange veya herhangi bir modern posta kutusuyla çalışan herkes için temel bir beceridir. İster kurumsal çapta otomasyon geliştiren bir geliştirici olun, ister gelen kutunuzu düzenli tutmak isteyen bir birey, doğru filtreleme tekniklerine hâkim olmak saatlerce manuel çabayı tasarruf ettirebilir. Bu kılavuzda, Aspose.Email for Java ile Exchange Web Services (EWS) üzerinden tarih, gönderen, konu, alan adı, alıcı gibi kriterlere göre nasıl filtreleme yapacağınızı ve mantıksal operatörlerle birden çok kriteri nasıl birleştireceğinizi göstereceğiz.

### Neler Öğreneceksiniz
- Java'da EWS kullanarak mesajları filtreleme teknikleri.  
- Tarih, gönderen, konu vb. kriterlere göre e-posta filtreleme.  
- Büyük posta kutularını yönetmek için sayfalama desteği uygulama.  
- Bu filtreleme yöntemlerinin gerçek dünyadaki senaryolarda pratik uygulamaları.  
- Aspose.Email Java ile performans hususları ve en iyi uygulamalar.

Bu öğreticinin sonunda, Exchange sunucusundan ihtiyacınız olan mesajları tam olarak çeken temiz ve yüksek performanslı Java kodu yazabilecek duruma geleceksiniz.

## Hızlı Yanıtlar
- **Ana kütüphane nedir?** Aspose.Email for Java.  
- **Hangi protokolü kullanır?** Exchange Web Services (EWS).  
- **Tarih aralığına göre filtreleyebilir miyim?** Evet – `SearchFilter` içinde `DateTime` kriterini kullanın.  
- **Sayfalama destekleniyor mu?** Kesinlikle, API `ItemView` ile offset/limit sunar.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, ticari bir lisans değerlendirme sınırlamalarını kaldırır.

## Aspose.Email for Java Nedir?
Aspose.Email for Java, Outlook veya başka bir istemciye ihtiyaç duymadan e-posta sunucularına, MIME mesajlarına ve Exchange Web Services'e programlı erişim sağlayan kapsamlı bir API'dir. Temel protokolleri soyutlayarak iş mantığına odaklanmanıza olanak tanır. Kütüphane, hem yerel Exchange sunucularını hem de Exchange Online'ı destekler ve çeşitli dağıtım senaryoları için birleşik bir API sunar.

## Aspose.Email'i EWS ile Neden Kullanmalısınız?
Aspose.Email, **50+** e-posta protokolünü destekler ve akış mimarisi sayesinde bellek kullanımını **100 MB** altında tutarak saat başı **yüz binlerce mesaj** işleyebilir. Bu ölçülebilir performans, kurumsal ölçekli posta kutusu otomasyonu için idealdir. Ayrıca, OAuth ve modern kimlik doğrulama için yerleşik destek sunar, Office 365 ortamlarına güvenli bağlantıları basitleştirir.

## Ön Koşullar

- **Gerekli Kütüphaneler**: Projenize Aspose.Email kütüphanesini ekleyin.  
- **Ortam Kurulumu**: Java uygulamaları için hazır bir geliştirme ortamı gereklidir.  
- **Bilgi Ön Koşulları**: Java programlaması ve e-posta protokolleri konusundaki aşinalık avantaj sağlayacaktır.

## Aspose.Email for Java'ı Kurma

### Maven Kurulumu
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alımı
- **Ücretsiz Deneme**: Aspose.Email'in yeteneklerini keşfetmek için ücretsiz deneme ile başlayın.  
- **Geçici Lisans**: Uzatılmış değerlendirme için geçici bir lisans edinin.  
- **Satın Alma**: Araç ihtiyaçlarınızı karşılıyorsa tam lisans satın almayı düşünün.

Gerekli paketleri içe aktararak ve EWS kimlik bilgilerini kullanarak e-posta sunucunuza bir bağlantı kurarak Aspose.Email'i başlatın ve kurun. Bu adım, posta kutusu verilerine programlı olarak erişmek için kritiktir.

## EWS ile Java'da E-postaları Nasıl Filtrelersiniz?

ExchangeService, bir Exchange sunucusuna bağlantıyı temsil eden Aspose.Email sınıfıdır.  
SearchFilter, sunucudaki öğeleri bulmak için kriterleri tanımlar.  
FindItems, aramayı yürütür ve eşleşen öğeleri döndürür.  
ItemView, sayfalama ve istekte döndürülen öğe sayısını kontrol eder.

`ExchangeService` örneğini kimlik bilgilerinizle yükleyin, kriterlerinize uyan bir `SearchFilter` oluşturun ve yalnızca ihtiyacınız olan mesajları almak için bir `ItemView` ile `FindItems` çağırın. Bu tek‑satır desen—bağlan → filtrele → getir—çoğu kullanım senaryosunu kapsar ve sayfalama etkinleştirildiğinde büyük posta kutularına ölçeklenir.

## Uygulama Kılavuzu

### EWS Kullanarak Mesajları Filtreleme

#### Genel Bakış
Filtreleme, belirli bir konu veya tarih gibi belirli koşulları karşılayan e-postaları doğrudan posta kutunuzdan almanıza olanak tanır.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Açıklama**: Kod, posta kutunuza bir bağlantı kurar ve belirli bir tarihte konu satırında 'Newsletter' içeren e-postaları filtrelemek için bir sorgu oluşturur.

### Bugünün Tarihiyle E-postaları Nasıl Filtrelersiniz?

SearchFilter.IsEqualTo, bir özelliğin verilen bir değere eşit olduğu öğeleri eşleştiren bir filtre oluşturur.  
DateTimeReceived, e-postanın ne zaman alındığını gösteren özelliktir.

Mevcut tarihi yükleyin, `DateTimeReceived` özelliği üzerinde bir `SearchFilter.IsEqualTo` oluşturun ve sorguyu yürütün. Bu, kodu çalıştırdığınız gün alınan mesajları yalnızca döndürür, günlük işleme betiklerini basitleştirir. Bu filtreyi gönderen veya konu gibi ek kriterlerle birleştirerek gün için sonuçları daha da daraltabilirsiniz.

### Tarih Aralığıyla E-postaları Nasıl Filtrelersiniz?

SearchFilter.IsGreaterThanOrEqualTo, bir özelliğin değerinin belirtilen değerden büyük veya eşit olduğu öğeleri eşleştiren bir filtre oluşturur.  
SearchFilter.IsLessThanOrEqualTo, bir özelliğin değerinin belirtilen değerden küçük veya eşit olduğu öğeleri eşleştiren bir filtre oluşturur.  
SearchFilter.And, tüm koşulların karşılanması gerektiği şekilde birden fazla filtreyi birleştirir.

Bir başlangıç ve bitiş `DateTime` tanımlayın, bunları `SearchFilter.IsGreaterThanOrEqualTo` ve `SearchFilter.IsLessThanOrEqualTo` ile birleştirin, ardından iki filtreyi birleştirmek için `SearchFilter.And` kullanın. Sonuç kümesi, belirtilen zaman dilimine giren tüm mesajları içerir. Bu yaklaşım, son çeyrek veya belirli bir proje zaman çizelgesi gibi herhangi bir özel dönemdeki tüm iletişimleri almanızı sağlar.

### Belirli Bir Gönderenle E-postaları Nasıl Filtrelersiniz?

SearchFilter.IsEqualTo, bir özelliğin verilen bir değere eşit olduğu öğeleri eşleştiren bir filtre oluşturur.

`From` özelliği üzerinde göndericinin e-posta adresiyle bir `SearchFilter.IsEqualTo` oluşturun. Bu, o kişiden gelen tüm mesajları izole eder, öncelikli gelen kutuları veya uyumluluk kontrolleri için idealdir. Tam adres bilinmediğinde veya alan adına göre filtreleme yaparken kısmi eşleşmeler için `SearchFilter.ContainsSubstring` da kullanabilirsiniz.

### Belirli Bir Alan Adıyla E-postaları Nasıl Filtrelersiniz?

SearchFilter.ContainsSubstring, bir özelliğin belirtilen bir alt dizeyi içerdiği öğeleri eşleştiren bir filtre oluşturur.

`From` özelliği üzerinde alan adı dizesi (ör. “@example.com”) ile `SearchFilter.ContainsSubstring` kullanın. Bu, o alan adından gelen tüm e-postaları çeker, ortak veya satıcı izleme için faydalıdır. Bu filtreyi tarih kriterleriyle birleştirerek zaman içinde alan adına özgü iletişimleri izleyebilir, güvenlik denetimlerine yardımcı olabilirsiniz.

### Belirli Bir Alıcıyla E-postaları Nasıl Filtrelersiniz?

SearchFilter.IsEqualTo, bir özelliğin verilen bir değere eşit olduğu öğeleri eşleştiren bir filtre oluşturur.

Hedef adres için `ToRecipients` koleksiyonunda `SearchFilter.IsEqualTo` uygulayın. Bu, belirli bir posta kutusuna veya dağıtım listesine gönderilen mesajları denetlemeniz gerektiğinde kullanışlıdır. Birden çok alıcı aynı alanı paylaştığında kısmi eşleşmeler için `SearchFilter.ContainsSubstring` da kullanabilirsiniz.

### Sorguları AND Mantığıyla Nasıl Birleştirirsiniz?

SearchFilter.And, tüm koşulların karşılanması gerektiği şekilde birden fazla filtreyi birleştirir.

`SearchFilter.And` kullanarak birden fazla `SearchFilter` nesnesini zincirleyin. Örneğin, bir gönderici filtresini konu filtresiyle birleştirerek yalnızca güvenilir bir göndericiden gelen bültenleri alın. AND operatörü, yalnızca tüm belirtilen koşulları karşılayan öğelerin döndürülmesini sağlar ve sonuç kümesini en ilgili mesajlara indirger.

### Sorguları OR Mantığıyla Nasıl Birleştirirsiniz?

SearchFilter.Or, bir koşulun eşleşmesi durumunda filtreleri birleştirir.

Herhangi bir koşulun eşleşmesi gerektiğinde filtreleri birleştirmek için `SearchFilter.Or` kullanın—örneğin, bir dizi göndericiden gelen **veya** belirli anahtar kelimeleri içeren mesajları çekmek için mükemmeldir. OR mantığını uygulamak, birden çok kategori arasında tüm ilgili iletişimleri yakalamak için aramaları genişletebilir ve kritik bilgileri kaçırmaz.

## Yaygın Tuzaklar ve İpuçları

- **Sayfalama esastır**: 1.000'den fazla öğe içeren posta kutularıyla çalışırken, zaman aşımını önlemek için her zaman sayfa boyutlu `ItemView` kullanın.  
- **Zaman dilimi yönetimi**: EWS tarihleri UTC olarak döndürür; karşılaştırmadan önce yerel bölgenize dönüştürün.  
- **Tam posta kutusu taramalarından kaçının**: Her zaman sunucu tarafında bir `SearchFilter` uygulayın; istemci tarafı filtreleme bant genişliğini ve belleği boşa harcar.  
- **Pro ipucu**: Uygulamanızın ömrü boyunca `ExchangeService` nesnesini önbelleğe alarak kimlik doğrulama yükünü azaltın.

## Sık Sorulan Sorular

**S: Bu yaklaşımı Office 365 ile kullanabilir miyim?**  
C: Evet, Aspose.Email, hizmet URL'sini `https://outlook.office365.com/EWS/Exchange.asmx` adresine yönlendirerek Office 365 Exchange Online ile çalışır.

**S: Aspose.Email OAuth kimlik doğrulamayı destekliyor mu?**  
C: Kesinlikle—kullanıcı şifrelerini saklamadan kimlik doğrulamak için `OAuthCredentials` kullanın.

**S: İşleyebileceğim maksimum posta kutusu boyutu nedir?**  
C: API, **birkaç gigabayt** boyutundaki posta kutularını işleyebilir; sonuçları akış olarak gönderdiği için bellek tüketimi düşük kalır.

**S: Ekleri dosya türüne göre nasıl filtrelerim?**  
C: `AttachmentNames` özelliği üzerinde bir `SearchFilter.ContainsSubstring` ekleyin, ardından yalnızca eşleşen öğeleri yineleyin.

**S: Sonuçları sıralamanın bir yolu var mı?**  
C: Evet—`FindItems` çağrısına bir `SortDirection` ve sıralamak istediğiniz özelliği (ör. `DateTimeReceived`) geçirin.

**Son Güncelleme:** 2026-07-17  
**Test Edilen Versiyon:** Aspose.Email for Java 24.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email for Java Kullanarak EWSClient Örneği Oluşturma: Exchange Sunucu Entegrasyon Kılavuzu](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Aspose.Email Java Kullanarak Exchange Sunucusundan E-posta İndirme](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Aspose.Email for Java ile EWS Mailbox Bilgilerini Yönetme: Kapsamlı Bir Kılavuz](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```