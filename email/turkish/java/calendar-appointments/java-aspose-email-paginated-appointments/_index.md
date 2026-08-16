---
date: '2026-08-16'
description: Aspose.Email kullanarak Java'da randevuları nasıl sayfalayacağınızı öğrenin
  ve kanıtlanmış sayfalama en iyi uygulamalarıyla exchange takvim verilerini verimli
  bir şekilde alın.
keywords:
- how to paginate appointments
- retrieve exchange calendar
- java pagination best practices
- Aspose.Email for Java
lastmod: '2026-08-16'
og_description: Aspose.Email kullanarak Java'da randevuları nasıl sayfalayacağınızı
  öğrenin ve exchange takvim verilerini verimli bir şekilde alın. Adım adım kod ve
  en iyi uygulama ipuçlarını izleyin.
og_image_alt: Developer guide showing paginated appointment retrieval from Exchange
  using Aspose.Email for Java
og_title: Java'da Aspose.Email ile randevuları sayfalama nasıl yapılır
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to paginate appointments in Java using Aspose.Email and retrieve
    exchange calendar data efficiently with proven pagination best practices.
  headline: How to paginate appointments in Java with Aspose.Email
  type: TechArticle
- description: Learn how to paginate appointments in Java using Aspose.Email and retrieve
    exchange calendar data efficiently with proven pagination best practices.
  name: How to paginate appointments in Java with Aspose.Email
  steps:
  - name: '**Reduce memory footprint** – only the current page lives in RAM.'
    text: '**Reduce memory footprint** – only the current page lives in RAM.'
  - name: '**Improve network efficiency** – each request transfers a predictable amount
      of data.'
    text: '**Improve network efficiency** – each request transfers a predictable amount
      of data.'
  - name: '**Enable responsive UI** – users can navigate page‑by‑page without waiting
      for a massive load.'
    text: '**Enable responsive UI** – users can navigate page‑by‑page without waiting
      for a massive load.'
  - name: '**Import pagination classes** – `PagingOptions`, `PagedResult`, and `Appointment`.'
    text: '**Import pagination classes** – `PagingOptions`, `PagedResult`, and `Appointment`.'
  - name: '**Define page size** – pick a value that matches your performance goals
      (50–200 is a common sweet spot).'
    text: '**Define page size** – pick a value that matches your performance goals
      (50–200 is a common sweet spot).'
  - name: '**Iterate through pages** – use a `while` loop that stops when the service
      reports no further pages.'
    text: '**Iterate through pages** – use a `while` loop that stops when the service
      reports no further pages.'
  - name: '**Process each appointment** – extract subject, start time, and any custom
      properties you need.'
    text: '**Process each appointment** – extract subject, start time, and any custom
      properties you need.'
  - name: '**Dispose the client** – ensure cleanup in a finally block.'
    text: '**Dispose the client** – ensure cleanup in a finally block.'
  - name: '**Corporate email management** – automate bulk calendar clean‑ups, generate
      compliance reports, or archive old meetings without overloading the server.'
    text: '**Corporate email management** – automate bulk calendar clean‑ups, generate
      compliance reports, or archive old meetings without overloading the server.'
  - name: '**Customer support systems** – pull support‑ticket appointments in a paged
      grid, allowing agents to scroll through large backlogs efficiently.'
    text: '**Customer support systems** – pull support‑ticket appointments in a paged
      grid, allowing agents to scroll through large backlogs efficiently.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports Exchange 2007 through Exchange Online, provided
      the EWS endpoint is reachable and credentials are valid.
    question: Can I use Aspose.Email for Java with any Exchange server version?
  - answer: Pagination reduces memory consumption, lowers network latency, and simplifies
      UI pagination controls, making large calendar views feasible.
    question: What are the benefits of using paginated appointment retrieval?
  - answer: Start with 50–200 items per page; increase the number if your network
      latency is low and the server has ample RAM, or decrease it for mobile or high‑latency
      environments.
    question: How do I decide the right “items per page java” value?
  - answer: A permanent license removes evaluation limits and is required for commercial
      deployments; a free trial is sufficient for development and testing.
    question: Is a license required for production use?
  - answer: Yes, `Appointment` objects expose start and end times with full time‑zone
      information, and the SDK can convert them to the local time zone as needed.
    question: Does Aspose.Email handle time‑zone conversions automatically?
  type: FAQPage
tags:
- paginate appointments
- Aspose.Email
- Java EWS client
- exchange calendar
title: Java'da Aspose.Email ile randevuları sayfalama nasıl yapılır
url: /tr/java/calendar-appointments/java-aspose-email-paginated-appointments/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Email kullanarak randevuları sayfalama

## Giriş

Bu öğreticide, bir Java uygulamasından Exchange sunucusuyla çalışırken **randevuları nasıl sayfalayacağınızı** keşfedeceksiniz. Sayfalama, bellek kullanımını düşük tutan, ağ çağrılarını hızlandıran ve UI render'ını daha akıcı hale getiren temel bir **java pagination best practice**'dır. `EWSClient` kullanarak Exchange'e bağlanmayı, takvim öğelerini sayfa sayfa almaya ve yaygın hataları önleyen gerçek dünya ipuçlarını uygulamayı öğreneceksiniz.

**Öğrenecekleriniz**
- Aspose.Email for Java'yı bir Maven projesine nasıl ekleyeceğinizi.  
- `IEWSClient` örneğini nasıl oluşturup yeniden kullanacağınızı.  
- Yapılandırılabilir bir **items per page java** değeriyle `listAppointmentsByPage` metodunu nasıl çağıracağınızı.  
- Hataları nasıl ele alacağınızı, kaynakları nasıl serbest bırakacağınızı ve performansı nasıl ayarlayacağınızı.  

Şimdi koda dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzu doğrulayalım.

## Hızlı cevaplar
- **Hangi kütüphane kullanılıyor?** Aspose.Email for Java.  
- **Hangi temel teknik?** `listAppointmentsByPage` ile Java sayfalama en iyi uygulamaları.  
- **Sayfa başına kaç öğe ayarlayabilirim?** Herhangi bir tam sayı; tipik üretim değerleri 50–200 arasındadır, demo açıklık için 2 kullanır.  
- **Lisans gerekli mi?** Test için ücretsiz deneme çalışır; kalıcı bir lisans değerlendirme sınırlamalarını kaldırır.  
- **JDK 16+ ile uyumlu mu?** Evet, kütüphane JDK 16 ve üzerini destekler.

## Sayfalama nedir ve neden önemlidir?
Sayfalama, büyük bir sonuç kümesini daha küçük, sıralı sayfalara böler. Bir alt küme (ör. 100 randevu) talep etmek bellek tüketimini azaltır, ağ yükünü sınırlar ve öngörülebilir gecikme sağlar; bu da UI yanıt süresini iyileştirir ve sunucu yükünü düşürür. Ayrıca hata yönetimini basitleştirir ve istemci uygulamalarda verimli kaydırmayı mümkün kılar.

## Java sayfalama en iyi uygulamaları genel bakış

Binlerce takvim öğesiyle çalışırken, tüm koleksiyonu tek bir çağrıyla çekmek bellek tüketimini hızla tüketebilir ve yanıt sürelerini artırabilir. Sonuç kümesini daha küçük, yönetilebilir sayfalara bölerek şunları elde edersiniz:

1. **Bellek ayak izini azaltın** – yalnızca mevcut sayfa RAM'de bulunur.  
2. **Ağ verimliliğini artırın** – her istek öngörülebilir bir veri miktarı aktarır.  
3. **Duyarlı UI'yi etkinleştirin** – kullanıcılar büyük bir yük beklemeden sayfa sayfa gezinebilir.  

Java'da tipik desen, gecikme ve bellek dengesini sağlayan bir **items per page** değeri belirlemek, ardından sunucu son sayfayı işaret edene kadar sayfalarda döngü yapmaktır. Aşağıdaki kod örnekleri bu deseni tam olarak izler.

## Önkoşullar

Bu öğreticiye devam etmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli kütüphaneler ve sürümler
- Aspose.Email for Java ≥ 25.4 (kütüphane **50+** giriş ve çıkış formatını destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı takvimleri işleyebilir).  
- Java Development Kit (JDK) 16 veya daha yeni bir sürüm.

### Ortam kurulumu
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Bağımlılıkları yönetmek için Maven kurulmuş.  

### Bilgi önkoşulları
- Temel Java sözdizimi ve Maven konusunda aşinalık.  
- Opsiyonel ancak faydalı: Exchange Web Services (EWS) kavramlarını anlama.

## Aspose.Email for Java Kurulumu

Aspose.Email, e-posta ve takvim entegrasyon görevlerini basitleştirmek için tasarlanmış güçlü bir kütüphanedir. Aşağıdaki bağımlılıkla Maven projenize ekleyin:

**Maven bağımlılığı**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme adımları

Aspose.Email ücretsiz bir deneme, geçici 30‑günlük lisans ve tam ticari lisans sunar. Deneme, tüm özellikleri keşfetmenizi sağlar, ancak kalıcı bir lisans değerlendirme kısıtlamalarını kaldırır ve üretim dağıtımları için gereklidir.

### Temel başlatma

Kütüphaneyi kullanmaya başlamak için lisans dosyasını (`Aspose.Email.lic`) sınıf yolunuza koyun ve uygulama başlangıcında yükleyin:

```java
License license = new License();
license.setLicense("Aspose.Email.lic");
```

Kütüphane hazır olduğunda, artık Exchange ile iletişim kuran bir istemci oluşturabilirsiniz.

## Exchange Java'a nasıl bağlanılır
Exchange hizmet URL'si, kullanıcı adı, şifre ve isteğe bağlı domain'i sağlayarak bir `IEWSClient` oluşturun. Tek bir istemciyi tüm sayfalama çağrıları için yeniden kullanın; bu, tekrarlanan TLS el sıkışmalarını önler ve her zaman `dispose()` metodunu bir finally bloğunda çağırarak ağ kaynaklarını serbest bırakın ve bağlantı sızıntılarını önleyin.

```java
IEWSClient client = EWSClient.getEWSClient("https://mail.example.com/EWS/Exchange.asmx", "user", "pwd", "domain");
try {
    // pagination logic will go here
} finally {
    client.dispose();
}
```

## Sayfalama desteğiyle randevuları listeleme
`IEWSClient` üzerinde `listAppointmentsByPage` metodunu kullanın ve istenen `itemsPerPage` değerini belirten bir `PagingOptions` nesnesi geçirin. Metod, mevcut dilimi ve daha fazla sayfa olup olmadığını gösteren bir bayrak içeren bir `PagedResult<Appointment>` döndürür. `hasMorePages` false olana kadar döngü yapın ve her randevuyu geldiği gibi işleyin.

**Tanım cümlesi:** `PagingOptions` bir sayfalı istekte sayfa boyutunu ve offset'i tanımlar. `PagedResult<T>` tip T öğelerinin bir sayfasını kapsar ve ek sayfaların mevcut olup olmadığını gösterir. `Appointment` konu, başlangıç zamanı ve konum gibi özelliklere sahip bir takvim öğesini temsil eder.

**Uygulama adımları**

1. **Sayfalama sınıflarını içe aktar** – `PagingOptions`, `PagedResult` ve `Appointment`.  
2. **Sayfa boyutunu tanımla** – performans hedeflerinize uygun bir değer seçin (50–200 yaygın bir aralıktır).  
3. **Sayfalarda yinele** – hizmet daha fazla sayfa raporlayana kadar bir `while` döngüsü kullanın.  
4. **Her randevuyu işle** – konu, başlangıç zamanı ve ihtiyacınız olan özel özellikleri çıkarın.  
5. **İstemciyi serbest bırak** – finally bloğunda temizlik yapın.

```java
int itemsPerPage = 100; // adjust based on latency and memory constraints
PagingOptions paging = new PagingOptions(itemsPerPage);
PagedResult<Appointment> page = client.listAppointmentsByPage(paging);
while (page != null && page.getItems() != null) {
    for (Appointment appt : page.getItems()) {
        System.out.println("Subject: " + appt.getSubject());
        System.out.println("Start: " + appt.getStartTime());
    }
    if (!page.hasMorePages()) break;
    page = client.listAppointmentsByPage(paging);
}
```

**Ana yapılandırma seçenekleri**
- **Sayfa başına öğe** – çoğu kurumsal senaryo için 50–200 olarak ayarlayın; yalnızca gecikmeyi ölçtükten sonra artırın.  
- **Sayfa ofseti** – SDK tarafından otomatik olarak işlenir; genellikle manuel olarak yönetmeniz gerekmez.  

## Yaygın tuzaklar ve ipuçları

- **Doğru sayfa boyutunu seçmek** – 10'dan düşük değerler aşırı isteklere neden olur; 500'ün üzerindeki değerler bellek kullanımını artırabilir. 100 ile başlayın ve profil oluşturduktan sonra ayarlayın.  
- **Dispose etmeyi asla unutmayın** – `dispose()` ihmal edilirse HTTP bağlantıları açık kalır, sonunda bağlantı havuzunu tüketir ve zaman aşımına neden olur.  
- **İstisnaları nazikçe ele alın** – `listAppointmentsByPage` çağrılarını `IOException` veya `ServiceException` için try‑catch bloklarıyla sarın. Hata kaydedin ve isteğe bağlı olarak üssel geri çekilme ile yeniden deneyin.  
- **İstemciyi yeniden kullanın** – her sayfa için yeni bir `IEWSClient` oluşturmak gereksiz TLS el sıkışmalarına yol açar ve verimliliği düşürür.  

## Pratik uygulamalar

Sayfalı randevu alımını uygulamak birçok gerçek dünya senaryosunda faydalıdır:

1. **Kurumsal e-posta yönetimi** – toplu takvim temizlemelerini otomatikleştirin, uyum raporları oluşturun veya sunucuyu aşırı yüklemeden eski toplantıları arşivleyin.  
2. **Müşteri destek sistemleri** – destek‑bileti randevularını sayfalı bir ızgarada çekin, böylece ajanlar büyük birikintileri verimli bir şekilde kaydırabilir.  
3. **Kaynak rezervasyon platformları** – oda veya ekipman kullanılabilirliğini sayfa sayfa gösterin, binlerce rezervasyon olsa bile ön yüzün yanıt vermesini sağlayın.  

## Performans değerlendirmeleri

Aspose.Email for Java'dan en iyi verimi almak için:

- **Sayfalamayı optimize edin** – farklı `itemsPerPage` değerlerini karşılaştırın; tipik 1 Gbps LAN'da sayfa başına 150 öğe yaklaşık 200 ms gecikme verir.  
- **Bellek yönetimi** – `dispose()`'ı hemen çağırın ve işlem sonrası büyük `Appointment` koleksiyonlarını tutmaktan kaçının.  
- **Bağlantı havuzlama** – birden fazla işlemde tek bir `IEWSClient` örneğini yeniden kullanın; SDK, maksimum verimlilik için HTTP bağlantılarını dahili olarak havuzlar.  

## Sonuç

Bu öğreticide, Aspose.Email for Java ile Exchange sunucusuna bağlanırken **randevuları nasıl sayfalayacağınızı** öğrendiniz. Gösterilen sayfalama desenini uygulayarak bellek kullanımını öngörülebilir tutacak, yanıt sürelerini iyileştirecek ve takvim‑ağır herhangi bir uygulama için daha akıcı bir kullanıcı deneyimi sunacaksınız.

### Sonraki adımlar
- E-posta gönderme, klasör senkronizasyonu ve MIME ayrıştırma gibi ek Aspose.Email özelliklerini keşfedin.  
- Ağ ve donanımınız için optimal dengeyi bulmak amacıyla bir hazırlık ortamında farklı `itemsPerPage` ayarlarıyla deney yapın.  
- Sayfalama mantığını bir REST uç noktasına veya Swing/JavaFX UI ızgarasına entegre ederek son kullanıcıya sunun.  

Yeni becerilerinizi uygulamaya koymaya hazır mısınız? Java projenizdeki kod parçacıklarını bugün uygulayın ve performans artışını ilk elden deneyimleyin.

## Sıkça Sorulan Sorular

**S: Aspose.Email for Java'yi herhangi bir Exchange sunucu sürümüyle kullanabilir miyim?**  
C: Evet, Aspose.Email Exchange 2007'den Exchange Online'a kadar destekler, EWS uç noktasına erişilebilirse ve kimlik bilgileri geçerliyse.

**S: Sayfalı randevu alımının faydaları nelerdir?**  
C: Sayfalama bellek tüketimini azaltır, ağ gecikmesini düşürür ve UI sayfalama kontrollerini basitleştirir; bu sayede büyük takvim görünümleri mümkün olur.

**S: Doğru “items per page java” değerini nasıl belirlerim?**  
C: Sayfa başına 50–200 öğe ile başlayın; ağ gecikmeniz düşük ve sunucunuzda yeterli RAM varsa sayıyı artırın, mobil veya yüksek gecikmeli ortamlar için azaltın.

**S: Üretim kullanımında lisans gerekli mi?**  
C: Kalıcı bir lisans değerlendirme sınırlamalarını kaldırır ve ticari dağıtımlar için gereklidir; ücretsiz deneme geliştirme ve test için yeterlidir.

**S: Aspose.Email zaman dilimi dönüşümlerini otomatik olarak yapıyor mu?**  
C: Evet, `Appointment` nesneleri tam zaman dilimi bilgisiyle başlangıç ve bitiş zamanlarını sunar ve SDK gerektiğinde yerel zaman dilimine dönüştürebilir.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```java
// Import necessary Aspose.Email packages
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class EmailSetup {
    public static void main(String[] args) {
        // Initialize the EWS client with server credentials
        IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
        // Always remember to dispose of the client after use
        if (client != null) {
            ((com.aspose.email.system.IDisposable)client).dispose();
        }
    }
}
```

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

```java
// Replace with your actual domain, username, and password
IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
```

```java
if (client != null) {
    ((com.aspose.email.system.IDisposable)client).dispose();
}
```

```java
import com.aspose.email.AppointmentPageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.system.collections.generic.List;
```

```java
IEWSClient client = EWSClient.getEWSClient("exchange.domain.com", "username", "password");
try {
    // Define total number of appointments per page – this is the “items per page java” setting
    int itemsPerPage = 2;
    List<AppointmentPageInfo> pages = new List<>();
```

```java
// Get the first page of appointments
AppointmentPageInfo pagedAppointmentCol = client.listAppointmentsByPage(itemsPerPage);
pages.addItem(pagedAppointmentCol);

// Loop through subsequent pages
while (!pagedAppointmentCol.getLastPage()) {
    pagedAppointmentCol = client.listAppointmentsByPage(
        itemsPerPage, pagedAppointmentCol.getPageOffset() + 1
    );
    pages.addItem(pagedAppointmentCol);
}
```

```java
} finally {
    if (client != null) 
        ((com.aspose.email.system.IDisposable)client).dispose();
}
```

## İlgili Öğreticiler

- [Aspose.Email Java Kullanarak Exchange Alt Klasörlerini Sayfalama: Etkili Bir Rehber](/email/java/exchange-server-integration/paginate-exchange-subfolders-aspose-email-java/)
- [Aspose.Email for Java ile Exchange Randevularını Yönetme: Kapsamlı Bir Rehber](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)
- [Aspose.Email ile Exchange Takvim Java Oluşturma – Tam Bir Rehber](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}