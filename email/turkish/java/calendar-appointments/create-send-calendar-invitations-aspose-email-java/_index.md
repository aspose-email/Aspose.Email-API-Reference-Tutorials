---
date: '2026-09-17'
description: Aspose.Email for Java ile takvim daveti oluşturmak, takvimleri paylaşmanıza,
  delege izinlerini ayarlamanıza ve paylaşım e-postalarını programlı olarak göndermenize
  olanak tanır.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Aspose.Email for Java ile takvim daveti oluşturmak, takvimleri programlı
  olarak paylaşmanıza, delege izinlerini ayarlamanıza ve Exchange Web Services üzerinden
  paylaşım e-postalarını göndermenize olanak tanır, ekip iş birliğini geliştirir.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Aspose.Email for Java ile takvim daveti nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Aspose.Email for Java ile takvim daveti nasıl oluşturulur
url: /tr/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvim paylaşımını yönetme: Aspose.Email for Java kılavuzu

## Takvim paylaşımını yönetmeye giriş
Takvim paylaşım davetlerini yönetmek, özellikle farklı platformlarda birden çok kullanıcıyla çalışırken karmaşık bir görev olabilir. Bu öğreticide Aspose.Email for Java ile **create calendar sharing invitation** oluşturacak, delegasyon erişimi oluşturulmasından takvim paylaşım e-postalarının gönderilmesine kadar her şeyi kapsayacaksınız. Sonunda delegasyon izinlerini ayarlayabilecek, **configure calendar permissions** yapabilecek ve organizasyonunuzda iş birliğini kolaylaştırabileceksiniz.

**Öğrenecekleriniz**
- Aspose.Email for Java ile EWS istemcisini nasıl başlatılır  
- Bir delegasyon kullanıcısı oluşturma ve **set delegate permissions**  
- **Create delegate access** ve takvim izinlerini yapılandırma  
- **calendar sharing email** (daveti) programlı olarak gönderme  
- Bu özelliklerin değer kattığı gerçek dünya senaryoları  

Derinlemeden önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.

## Hızlı cevaplar
- **Bu kılavuzun temel amacı nedir?** Aspose.Email for Java kullanarak **create calendar sharing invitation** göstermektir.  
- **Hangi kütüphane sürümü gereklidir?** Aspose.Email for Java 25.4 (JDK 16 classifier).  
- **Bir lisansa ihtiyacım var mı?** Evet – üretim kullanımı için deneme veya tam lisans gereklidir.  
- **Hangi ortam gerekli?** JDK 16+, Maven ve bir Exchange Online hesabı.  
- **Bunu diğer Exchange sunucularıyla kullanabilir miyim?** Evet, ancak hizmet URL'si ve izin seviyelerini ayarlamanız gerekebilir.

## Takvim paylaşım daveti nedir?
Takvim paylaşım daveti, başka bir kullanıcıya takviminizi tam posta kutusu hakları vermeden görüntüleme (veya düzenleme) izni veren bir e-posta mesajıdır. Bu, ekip üyelerinin programınızı görmesini, toplantı önermesini veya etkinlikleri yönetmesini sağlar ve posta kutunuzu güvenli tutar.

## Neden takvim izinlerini yapılandırmalısınız?
Takvim izinlerini yapılandırmak, bir delegasyonun ne yapabileceğini tam olarak kontrol etmenizi sağlar—sadece etkinlikleri okuyabilir, yeni önerilerde bulunabilir veya mevcut girdileri düzenleyebilir. Doğru izin ayarları, hassas bilgileri korurken etkili iş birliğine olanak tanır. Örneğin, sadece okuma izni vermek yanlışlıkla değişiklik yapılmasını önlerken, düzenleme izni delegasyonun sizin adınıza toplantı planlamasına veya değiştirmesine izin verir.

## Önkoşullar
- **Java Development Kit (JDK):** Versiyon 16 veya üzeri.  
- **Maven:** Bağımlılık yönetimi ve proje derlemesi için.  
- **Aspose.Email for Java Library:** JDK 16 desteğiyle Versiyon 25.4.  

### Ortam kurulum gereksinimleri
1. Henüz kurmadıysanız JDK'yı kurun. [Oracle'ın resmi sitesinden](https://www.oracle.com/java/technologies/javase-downloads.html) indirebilirsiniz.  
2. Maven'ın makinenizde kurulu ve yapılandırılmış olduğundan emin olun.  
3. Daha kolay geliştirme için IntelliJ IDEA veya Eclipse gibi bir IDE seçin.

### Bilgi önkoşulları
- Temel Java programlama becerileri  
- Maven bağımlılıklarına aşinalık  
- İsteğe bağlı: Exchange Web Services (EWS) deneyimi  

## Aspose.Email for Java'ı kurma
### Maven yapılandırması
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme
Aspose.Email for Java tam işlevsellik için bir lisans gerektirir. Şunları yapabilirsiniz:
- **Ücretsiz deneme:** [Aspose'un sürüm sayfasından](https://releases.aspose.com/email/java/) indirin.  
- **Geçici lisans:** Aspose web sitesinden geçici bir anahtar isteyin.  
- **Satın al:** Üretim dağıtımları için kalıcı bir lisans edinin.

### Temel başlatma ve kurulum
Maven bağımlılığı çözdükten sonra, EWS istemcisini başlatın:

`ExchangeService` Exchange Web Services ile iletişim kurmak için kullanılan ana sınıftır.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Takvim paylaşım daveti nasıl oluşturulur
Takvim paylaşım daveti oluşturmak için önce `ExchangeService` istemcisiyle Exchange'e bağlanırsınız, ardından istenen izin seviyesine sahip bir delegasyon tanımlarsınız ve son olarak paylaşım isteğini içeren bir `MailMessage` oluşturursunuz. Aşağıdaki adımlar bu iş akışını Java'da gösterir.

Aşağıda iki temel özelliği ele alıyoruz: takvim paylaşım daveti oluşturma ve gönderme, ve takvim erişimi için **set delegate permissions**.

### Özellik 1: takvim paylaşım daveti oluşturma ve gönderme
#### Genel Bakış
Bu özellik, istemciyi başlatma, **create delegate access**, ve davet e-postasını gönderme adımlarını size gösterir.

#### Adım adım uygulama
##### 1️⃣ EWS istemcisini başlatma
`ExchangeService` bir Exchange sunucusuna bağlantıyı temsil eder ve mesajları göndermek ve almak için kullanılır.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Bu, Java uygulamanızı Exchange Online'a bağlar.

##### 2️⃣ Delegasyon kullanıcısı oluşturma
`DelegateUser` delegasyonun e-posta adresini ve verilecek izin seviyesini tanımlar.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Burada **create delegate access** yapıyor ve delegasyonun takvim öğelerini görmesini sağlayan `Reviewer` seviyesini atıyoruz.

##### 3️⃣ Takvim paylaşım davetini gönderme
`MailMessage` takvim paylaşım davetini taşıyan e-postayı oluşturur.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Kod, bir **calendar sharing email** (daveti) oluşturur ve EWS istemcisi aracılığıyla gönderir.

### Özellik 2: delegasyon takvim erişim izni
#### Genel Bakış
Bu bölüm, **configure calendar permissions** nasıl yapılacağını ve delegasyonun doğru haklara sahip olduğundan nasıl emin olunacağını gösterir.

#### Uygulama adımları
##### 1️⃣ EWS istemcisini başlatma (yeniden kullanım)
`ExchangeService` ilk yapılandırmadan sonra birden fazla işlem için yeniden kullanılabilir.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Delegasyon izinlerini oluşturma ve ayarlama
`ExchangeDelegateFolderPermissionLevel` bir delegasyonun bir takvim klasörüne sahip olabileceği erişim seviyelerini listeler.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Bu snippet **sets delegate permissions** böylece kullanıcı tam posta kutusu erişimi olmadan takvim girdilerini görebilir.

## Delegeler için takvim izinlerini nasıl yapılandırılır
Bir delegasyonun sadece okuma izninden daha fazlasına ihtiyacı olduğunda, `ExchangeDelegateFolderPermissionLevel`'ı düzenleyerek düzenleme, yazar veya sahip hakları verebilirsiniz. Güvenliği korurken gerekli işlevselliği sağlamak için iş ihtiyacını karşılayan en düşük seviyeyi seçin. Örneğin, Editor seviyesini atamak delegasyonun etkinlikleri oluşturmasına, değiştirmesine ve silmesine izin verirken, Reviewer seviyesi sadece görüntülemeye izin verir.

- `Reviewer` – sadece okuma erişimi.  
- `Editor` – okuma/yazma erişimi.  
- `Author` – oluşturma ve okuma, ancak silme yapılamaz.  
- `Owner` – tam kontrol, izin değişiklikleri dahil.  

**Pro ipucu:** Takvim verilerinizi güvenli tutmak için iş gereksinimini karşılayan en az ayrıcalıklı seviyeyi kullanın.

## Pratik uygulamalar
Gerçek dünya senaryoları **manage calendar sharing**'in parladığı yerler:
1. **Kurumsal toplantılar** – Takım üyelerinin tam posta kutusu hakları vermeden toplantı takvimlerini görmesini sağlar.  
2. **Proje yönetimi** – Proje liderleri zaman çizelgelerini izleyebilirken geliştiriciler kendi takvimleri üzerinde kontrol sahibi olur.  
3. **Etkinlik planlaması** – Satıcılar, iç detayları ifşa etmeden lojistiği koordine etmek için bir **calendar sharing email** alır.

## Performans değerlendirmeleri
- **Bellek yönetimi:** Yüksek hacimli uygulamalarda büyük `MailMessage` nesnelerini hızlıca serbest bırakın.  
- **İstisna yönetimi:** Bağlantı sorunlarını nazikçe ele almak için ağ çağrılarını try‑catch bloklarıyla sarın.  
- **Kütüphane güncellemeleri:** Aspose.Email for Java 50+ protokolü destekler ve takvimleri tüm dosyayı belleğe yüklemeden 10.000 öğeye kadar işleyebilir; bu yüzden performans iyileştirmeleri ve hata düzeltmelerinden yararlanmak için kütüphaneyi güncel tutun.

## Yaygın sorunlar ve çözümler
| Sorun | Muhtemel neden | Çözüm |
|-------|----------------|-------|
| Davet alınmadı | Spam filtreleri veya hatalı e-posta adresi | Alıcı adresini doğrulayın ve gönderim alanını güvenilir göndericiler listesine ekleyin |
| İzin uygulanmadı | Yanlış `ExchangeDelegateFolderPermissionLevel` kullanılması | İzin seviyesinin gerekli erişimle eşleştiğini tekrar kontrol edin |
| `createCalendarSharingInvitationMessage` üzerinde çalışma zamanı istisnası | Lisans eksikliği veya eski kütüphane | Geçerli bir lisans yüklendiğinden ve en son Aspose.Email sürümünü kullandığınızdan emin olun |

## Sıkça sorulan sorular
**S: Aspose.Email for Java ne için kullanılır?**  
C: Java uygulamalarında e-posta, takvim ve kişileri işlemek için kapsamlı bir kütüphane olup, Outlook, Exchange ve diğer protokolleri destekler.

**S: Aspose.Email kullanmak için ortamımı nasıl kurarım?**  
C: JDK 16+, Maven kurun, `pom.xml` dosyasına Aspose.Email bağımlılığını ekleyin ve bir lisans (deneme veya tam) edinin.

**S: Bu kodu diğer Exchange Online sürümleriyle kullanabilir miyim?**  
C: Evet, ancak hizmet URL'si ve izin seviyelerinin sunucu yapılandırmanızla eşleştiğini doğrulayın.

**S: Takvim paylaşım daveti gönderilemezse ne yapmalıyım?**  
C: Ağ bağlantısını, kimlik bilgilerini ve delegasyon kullanıcısının geçerli izinlere sahip olduğunu kontrol edin. İstisna detaylarını inceleyerek ipuçları bulun.

**S: Düzenleme veya tam erişim gibi ek izinler eklemek mümkün mü?**  
C: Kesinlikle – ihtiyaca göre `ExchangeDelegateFolderPermissionLevel.Reviewer` yerine `Editor`, `Author` veya `Owner` kullanın.

## Sonuç
Artık Aspose.Email for Java ile **create calendar sharing invitation** için tam bir uçtan uca çözümünüz var. EWS istemcisini başlatarak, **create delegate access**, **set delegate permissions** ve bir **calendar sharing email** göndererek organizasyonunuzda iş birliğini otomatikleştirebilirsiniz.

**Sonraki adımlar**
- Diğer izin seviyelerini (Editor, Owner) deneyin.  
- Bu mantığı mevcut planlama veya İK sistemlerinize entegre edin.  
- Tekrarlayan etkinlikler veya toplantı istekleri gibi ek Aspose.Email özelliklerini keşfedin.

---

**Son Güncelleme:** 2026-09-17  
**Test Edilen:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email Kullanarak Java'da Takvim Öğesi Oluşturma](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java ile Exchange Randevularını Tarihe Göre Filtreleme](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Aspose.Email ile Java'da Exchange Takvimi Oluşturma – Tam Kılavuz](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}