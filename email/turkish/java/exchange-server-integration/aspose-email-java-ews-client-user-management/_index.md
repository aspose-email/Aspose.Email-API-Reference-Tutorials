---
date: '2026-07-08'
description: Aspose.Email kullanarak EWS Java istemcisini nasıl oluşturacağınızı öğrenin;
  Exchange Server üzerinde message deletion, appending ve user impersonation dahil
  olmak üzere etkili e-posta yönetimi.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Aspose.Email kullanarak EWS Java istemcisini nasıl oluşturacağınızı
  öğrenin; Exchange Server üzerinde message deletion, appending ve user impersonation
  dahil olmak üzere etkili e-posta yönetimi.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Aspose.Email ile EWS Java İstemcisi Oluşturun – Kullanıcıları Yönetme
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Aspose.Email ile EWS Java İstemcisi Oluşturun – Kullanıcıları Yönetme
url: /tr/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# E-posta Yönetiminde Uzmanlaşma: Aspose.Email Java ile EWS İstemci Kullanıcı ve Taklit

## Giriş

Bu öğreticide **EWS istemci Java** uygulamalarını Aspose.Email ile oluşturacaksınız; bu sayede tek bir Java kod tabanından birden çok Exchange Server posta kutusunu yönetebileceksiniz. `EWSClient` örnekleri oluşturma, mesajları silme, yeni e-postalar ekleme ve diğer kullanıcıları taklit etme adımlarını göstereceğiz—kurumsal ortamlarda saatler süren manuel işi tasarruf ettiren görevler.

### Öğrenecekleriniz
- Ayrı kimlik bilgileriyle **EWS istemci Java** nesneleri oluşturma.  
- Seçilen bir klasörden tüm mesajları silmek için etkili teknikler.  
- Hazır bir e-postayı bir kullanıcının posta kutusuna ekleme adımları.  
- Paylaşımlı posta kutusu senaryoları için başka bir posta kutusunu taklit etme.

Şimdi neler kapsayacağımızı bildiğinize göre, geliştirme ortamını hazırlayalım.

## Hızlı Yanıtlar
- **İlk adım nedir?** `pom.xml` dosyanıza Aspose.Email Maven bağımlılığını ekleyin.  
- **Exchange bağlantısını temsil eden sınıf hangisidir?** `EWSClient` (veya arayüzü `IEWSClient`).  
- **Tüm mesajları tek bir çağrıyla silebilir miyim?** Evet—`listMessages` ile döngü yapın ve her URI için `deleteMessage` çağırın.  
- **SMTP olmadan e-posta nasıl gönderilir?** `appendMessage` kullanarak bir `MailMessage`'ı doğrudan bir klasöre yerleştirin.  
- **Taklit güvenli mi?** Orijinal kimlik bilgileri altında çalışır ve Exchange’in delegasyon politikalarına uyar.

## create EWS client Java nedir?
`create ews client java`, bir Java uygulamasında bir `EWSClient` nesnesi örnekleyerek Exchange Web Services (EWS) işlemlerini programlı olarak çağırmanızı sağlar. Bu yaklaşım manuel Outlook etkileşimini ortadan kaldırır ve otomatik posta kutusu işleme imkanı verir. Kullanıcı başına ayrı bir istemci oluşturarak kimlik bilgilerini izole edebilir, posta kutusu politikalarını uygulayabilir ve kod tekrarından kaçınarak çözümü onlarca hesapta ölçeklendirebilirsiniz.

## Aspose.Email'i EWS entegrasyonu için neden kullanmalısınız?
Aspose.Email **50+** EWS işlemini destekler, **yüzlerce sayfalık** posta kutularını tüm depoyu belleğe yüklemeden işler ve tipik sunucu donanımında **dakikada 10.000** mesaja kadar işlem yapar. Bu ölçülen yetenekler, büyük ölçekli e-posta otomasyonu için onu birincil tercih yapar. Kütüphane ayrıca düşük seviyeli SOAP detaylarını soyutlayarak temiz, tip‑güvenli bir API sunar; bu da geliştirme süresini azaltır ve hataları en aza indirir.

## Önkoşullar
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** bağımlılık yönetimi için.  
- **Aspose.Email for Java** kütüphanesi (Maven aracılığıyla ekleyin).  
- Exchange Web Services (EWS) kavramlarına temel bilgi.

## Aspose.Email for Java'ı Kurma
Kütüphaneyi Maven `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alımı
Aspose.Email ücretsiz deneme sunar; tam yetenekler için geçici bir lisans talep edebilirsiniz. Uzun vadeli kullanım için [Aspose'un satın alma sayfası](https://purchase.aspose.com/buy) üzerinden lisans satın almayı düşünün.

## create EWS client Java nasıl yapılır?
Uygun kimlik bilgileriyle Exchange hizmetini yükleyin ve bir `IEWSClient` örneği alın—bu iki adımlı desen, sonraki tüm işlemlerin temelidir. Aynı istemciyi birden çok eylem için yeniden kullanabilir veya izolasyon için kullanıcı başına ayrı örnekler oluşturabilirsiniz. **`IEWSClient` tüm EWS işlemlerini ortaya çıkaran arayüzdür, `EWSClient` ise bir uygulama elde etmek için statik fabrika metodunu sağlar.**  

İstemci oluşturma genellikle hizmet URL'si, kullanıcı adı, şifre ve isteğe bağlı olarak domain bilgisini sağlamayı içerir. Oluşturulduktan sonra istemci kimlik doğrulama, istek imzalama ve yanıt ayrıştırmayı otomatik olarak yönetir.

### EWSClient Örnekleri Oluşturma
**Tanım:** `EWSClient` ( `IEWSClient` arayüzü aracılığıyla erişilir) Aspose.Email’in Exchange sunucusuyla EWS üzerinden iletişim kurmak için ana nesnesidir.

#### Gerekli Sınıfları İçe Aktarın
Gerekli Aspose.Email sınıflarını içe aktararak başlayın:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### EWSClient Örneklerini Başlatın
Yönetmek istediğiniz her posta kutusu için `IEWSClient` nesneleri oluşturun:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Açıklama:* `getEWSClient` yardımcı yöntemi, sağlanan kimlik bilgileriyle Exchange’e bağlanır ve mevcut kullanıcının izinlerine saygı gösteren hazır bir istemci döndürür.

## Bir klasörden mesajları nasıl silinir?
Hedef klasördeki tüm öğeleri alın ve tek bir geçişte kalıcı olarak silin. Bu yöntem, her mesajı ayrı ayrı açmanın getirdiği yükü ortadan kaldırır. **`listMessages`, her mesajın benzersiz URI'sını içeren bir `MessageInfo` koleksiyonu döndürür; bu URI'yi `deleteMessage` ile sunucudan kaldırırsınız.**  

Toplu işleme, ağ tur sayısını azaltır ve büyük klasörlerde zaman aşımını önler. Silme işlemi geri alınamaz; bu yüzden hedef klasörün doğru olduğundan emin olun.

### Mesajları Listele ve Sil
Her mesaj URI'sı üzerinde döngü yapın ve silme işlemini çağırın:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Açıklama:* `listMessages` bir `MessageInfo` koleksiyonu döndürür; `getUniqueUri()` değerleri `deleteMessage`'a geçirilerek öğeler sunucudan kalıcı olarak kaldırılır.

## Bir klasöre mesaj nasıl eklenir?
Yerel olarak bir `MailMessage` nesnesi oluşturun ve doğrudan bir posta kutusu klasörüne kaydedin—SMTP sunucusuna ihtiyaç yoktur. **`MailMessage`, başlıklar, gövde ve ekleri içeren bir e-postayı temsil eder; tamamen bellekte oluşturulup Exchange’e kaydedilebilir.**  

Eklemek, gönderim hattını atlayarak taslaklar, şablonlar veya programatik mesaj oluşturma senaryoları için idealdir; mesaj anında kullanıcının posta kutusunda görünür.

### Mesaj Oluştur ve Gönder
E‑postayı oluşturun ve Taslaklar klasörüne ekleyin:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Açıklama:* `appendMessage`, `MailMessage` ve bir `FolderInfo` (ör. Drafts) alır ve öğeyi posta kutusuna yazar; böylece kullanıcı için anında erişilebilir hâle gelir.

## EWS'de bir kullanıcı nasıl taklit edilir?
İstemcinin güvenlik bağlamını başka bir posta kutusuna değiştirin, işlemleri gerçekleştirin ve ardından orijinal hesaba geri dönün. Bu, paylaşımlı posta kutusu yönetimi için kritiktir. **`impersonateUser`, temel EWS isteğinde `ImpersonatedUserId` ayarlar; sunucu çağrıyı hedef posta kutusundan geliyormuş gibi işler.**  

Gerekli işlemler tamamlandığında `resetImpersonation` çağırarak orijinal kimlik bilgilerini geri yükleyin; böylece sonraki çağrılar doğru güvenlik bağlamı altında yürütülür.

### Kullanıcı Taklidi Yapma
İstemcinin bağlamını geçici olarak başka bir kullanıcıya değiştirin:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Açıklama:* `impersonateUser`, temel EWS isteğinde `ImpersonatedUserId` ayarlar; böylece hedef kullanıcı gibi okuma veya yazma yapabilirsiniz. `resetImpersonation` ise orijinal kimlik bilgilerini geri yükler.

## Pratik Uygulamalar
Aspose.Email Java, sağlam e-posta otomasyon çözümleri sağlar:
1. **Otomatik E-posta Temizliği:** Çeşitli posta kutularındaki eski Taslak klasörlerini gecelik bir iş ile temizleyin.  
2. **Toplu E-posta Dağıtımı:** Şablon bir duyuruyu tek bir döngüyle tüm çalışanların Gelen Kutusuna ekleyin.  
3. **Paylaşımlı Posta Kutusu Yönetimi:** Bir departman posta kutusunu taklit ederek eski mesajları arşivleyin; her kullanıcıya tam erişim vermeye gerek kalmaz.

## Performans Düşünceleri
Büyük posta kutularını işlerken uygulamanızın yanıt verebilirliğini korumak için:
- **Batch API çağrılarını** mümkün olduğunca kullanın (ör. istekte 500 mesaj sil).  
- **Mesajları akış olarak** işleyin; tam gövdeleri belleğe yüklemeyin.  
- **İstemci nesnelerini** zamanında serbest bırakın; ağ soketleri ve HTTP bağlantılarını boşaltın.

## Yaygın Sorunlar ve Çözümler
- **Bağlantı hataları:** EWS uç nokta URL'sini doğrulayın, TLS 1.2'nin etkin olduğundan emin olun ve güvenlik duvarı kurallarının dışa doğru HTTPS trafiğine izin verdiğini kontrol edin.  
- **Taklitte izin reddedildi:** Hizmet hesabının Exchange'te “ApplicationImpersonation” rolüne sahip olması gerekir.  
- **Büyük klasör zaman aşımı:** `HttpWebRequest` zaman aşımını artırın veya klasörü daha küçük parçalar halinde işleyin.

## Sık Sorulan Sorular

**S: EWS bağlantı sorunlarını nasıl gideririm?**  
C: Uç nokta URL'sini, kimlik bilgilerini ve ağ güvenlik duvarlarını kontrol edin; Aspose.Email içinde HTTP istek/yanıt verilerini yakalamak için ayrıntılı günlüklemeyi etkinleştirin.

**S: Aspose.Email büyük miktarda e-postayı verimli bir şekilde işleyebilir mi?**  
C: Evet—batch API'leri sayesinde **10.000+** mesajı dakikada işleyebilir ve bellek kullanımını 200 MB altında tutar.

**S: EWS'de kullanıcı taklidi tipik olarak hangi senaryolarda kullanılır?**  
C: Paylaşımlı posta kutularının yönetimi, toplu arşivleme ve birden çok kullanıcı adına zamanlanmış raporların çalıştırılması; şifrelerini saklamaya gerek kalmaz.

**S: Aspose.Email API çağrıları üzerinde bir limit var mı?**  
C: Aspose.Email kendisi bir limit koymaz; ancak Exchange, uygulamanın uyması gereken kısıtlama politikaları uygulayabilir.

**S: Java kodumda kimlik bilgilerini nasıl güvenli tutarım?**  
C: Şifreleri şifreli yapılandırma dosyalarında saklayın veya Azure Key Vault / AWS Secrets Manager kullanın; EWS uç noktaları için her zaman HTTPS kullanın.

---

**Son Güncelleme:** 2026-07-08  
**Test Edilen Versiyon:** Aspose.Email for Java 23.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email for Java ile bir EWSClient Örneği Oluşturma: Exchange Server Entegrasyon Kılavuzu](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Aspose.Email for Java ve EWS ile Microsoft Exchange Server'a Bağlanma](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Aspose.Email ve Java EWS İstemcisi ile E-posta Yönetimini Otomatikleştirme: Kapsamlı Kılavuz](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}