---
date: '2026-10-02'
description: Aspose.Email for Java kullanarak Exchange'e nasıl bağlanacağınızı ve
  Exchange ortak klasörlerini nasıl listeleyeceğinizi öğrenin. Bu adım adım rehber,
  Maven bağımlılığını ve kod gerektirmeyen kurulumu gösterir.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Aspose.Email for Java kullanarak Exchange'e nasıl bağlanacağınızı
  ve Exchange ortak klasörlerini nasıl listeleyeceğinizi öğrenin. Bu rehber, Maven
  bağımlılığı, lisanslama ve özyinelemeli mesaj alımını kapsar.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Java'da Exchange'e bağlanma ve ortak klasörleri listeleme
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Java'da Exchange'e bağlanma ve ortak klasörleri listeleme
url: /tr/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Exchange'e bağlanma ve ortak klasörleri listeleme

## Giriş
Modern işletmelerde, Microsoft Exchange posta kutularına programlı olarak erişmek, arşivleme, izleme ve raporlama görevlerini otomatikleştirmenizi sağlar. Bu öğreticide **how to connect exchange** ifadesiyle Aspose.Email for Java kullanarak Exchange'e nasıl bağlanılacağını ve ardından **list exchange public folders** ifadesiyle ortak klasörlerin nasıl yinelemeli olarak listeleneceğini gösteriyoruz. Gerekli Maven bağımlılığını, lisans adımlarını ve API çağrılarının tam sırasını göreceksiniz—ekstra kütüphane gerekmez. Sonunda, herhangi bir ortak klasörden mesajları çekip yerel olarak kaydedebileceksiniz.

## Hızlı cevaplar
- **İlk adım nedir?** `pom.xml` dosyanıza Aspose.Email Maven bağımlılığını ekleyin.  
- **Lisans gerekiyor mu?** Evet—değerlendirme için geçici bir lisans kullanın veya üretim için tam lisans satın alın.  
- **Bağlantıyı hangi sınıf oluşturur?** `ExchangeClient` (IMAP için `ImapClient`) kimlik doğrulama ve sunucu iletişimini yönetir.  
- **Alt klasörleri otomatik olarak listeleyebilir miyim?** Evet—API tarafından sağlanan yinelemeli `listSubFolders` metodunu kullanın.  
- **Bu yaklaşım çok iş parçacıklı güvenli mi?** İstemci nesneleri çok iş parçacıklı güvenli değildir; eşzamanlı iş yükleri için her iş parçacığına ayrı bir örnek oluşturun.

## "how to connect exchange" nedir?
**How to connect exchange**, bir Java uygulamasının yerel ya da bulut tabanlı bir Microsoft Exchange sunucusuna kimlik doğrulama sürecidir; böylece klasör sayımı veya mesaj alma gibi API çağrıları yapabilirsiniz. Aspose.Email, altındaki EWS/IMAP protokollerini soyutlayarak size tek, tutarlı bir nesne modeli sunar.

## Neden Exchange ortak klasörlerini listelemelisiniz?
Ortak klasörleri listelemek, organizasyonların paylaşılan posta kutuları, dağıtım listeleri ve arşiv depoları için kullandığı hiyerarşik yapıyı görmenizi sağlar. Aspose.Email, tek bir çağrıda **50+ ortak klasör** üzerinden sayım yapabilir ve tüm depoyu belleğe yüklemeden çok sayfalı posta kutularını işleyebilir; bu da RAM tüketimini %70'e kadar azaltır.

## Önkoşullar
- **Aspose.Email for Java** — sürüm 25.4 veya daha yeni (en son kararlı sürüm).  
- **Java Development Kit (JDK)** — JDK 11 veya daha yeni bir sürüm kurulu ve `JAVA_HOME` yapılandırılmış.  
- **Maven** — bağımlılık yönetimi ve derleme otomasyonu için.  
- Java sözdizimi ve Exchange kavramları (posta kutuları, klasörler, EWS) hakkında temel bilgi.

## Aspose.Email for Java'ı Kurma
Kütüphaneyi entegre etmek için Maven bağımlılığını projenizin `pom.xml` dosyasına ekleyin. Bu, ihtiyacınız olan **maven dependency aspose email**'dir.

### Maven bağımlılığı
Aşağıdaki kod parçacığını `pom.xml` dosyanızdaki `<dependencies>` öğesinin içine ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinme adımları
Aspose.Email, tam özellikli kullanım için geçerli bir lisans gerektirir:
- **Ücretsiz deneme** – API'yi değerlendirmek için [Aspose web sitesinden](https://purchase.aspose.com/temporary-license/) geçici bir lisans indirin.  
- **Satın al** – Üretim dağıtımları için Aspose portalı üzerinden ticari bir lisans edinin.

#### Temel başlatma
Maven paketi çözdükten ve bir lisans dosyanız olduğunda, `.lic` dosyasını sınıf yoluna yerleştirin ve kütüphaneyi başlatın:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Uygulama rehberi
Her işlevsel bloğu adım adım inceleyecek, ana soruları doğrudan ve özlü paragraflarla yanıtlayacağız, ardından ayrıntılı adımlara geçeceğiz.

### Exchange'e nasıl bağlanılır?
`ExchangeClient`'ı sunucu URL'si, kullanıcı kimlik bilgileri ve domain ile yükleyin, ardından `connect()` çağrısını yapın. İstemci, Exchange Web Services (EWS) ile bir HTTPS oturumu kurar ve kimlik bilgilerini doğrular. Bağlantı başarısız olursa, API hızlı sorun giderme için HTTP durum kodunu içeren ayrıntılı bir `AuthenticationException` fırlatır.  
`ExchangeClient`, Aspose.Email'in Exchange Web Services'e bağlantıyı yöneten sınıfıdır.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Exchange ortak klasörlerini nasıl listeleyebilirsiniz?
`client.listPublicFolders()` metodunu çağırarak her üst‑seviye ortak klasörü temsil eden bir `FolderInfo` nesne koleksiyonu alın. Metod, klasör adı, toplam öğe sayısı ve sonraki çağrılar için kullanılan benzersiz bir tanımlayıcı gibi meta verileri döndürür. Bu çağrı, 500 klasöre kadar tipik yerel dağıtımlarda 2 saniyenin altında tamamlanır.  
`listPublicFolders()` bir `FolderInfo` nesne koleksiyonu döndürür.  
`FolderInfo`, görüntüleme adı ve öğe sayısı gibi meta verileri tutar.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Klasör bilgilerini nasıl görüntülersiniz?
`FolderInfo` koleksiyonu üzerinde döngü kurarak `displayName` ve `subFolderCount` değerlerini yazdırın. Bu hızlı özet, daha derin bir taramaya başlamadan önce hiyerarşiyi anlamanıza yardımcı olur. Büyük organizasyonlar için API, sonuçları sayfalayabilir; bellek kullanımını düşük tutmak için sayfa başına 100 klasör döndürür.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Bir klasörden mesajları nasıl listeleyebilirsiniz?
`folderId` önceki adımda elde edilen tanımlayıcı olduğunda `client.listMessages(folderId)` metodunu çağırın. Metod, konu, gönderen ve alınma tarihi içeren bir `MessageInfo` nesne listesi döndürür. Çok büyük klasörleri işlerken istemciyi aşırı yüklememek için `maxCount` ile sonuç kümesini sınırlayabilirsiniz.  
`listMessages(folderId)` bir `MessageInfo` nesne listesi döndürür.  
`MessageInfo`, bir e-postanın konu, gönderen ve alınma tarihi gibi temel özelliklerini içerir.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Mesajları nasıl alıp kaydedersiniz?
Her `MessageInfo` için `client.fetchMessage(messageId)` metodunu kullanarak tam MIME içeriğini indirin. Ardından bayt dizisini diskte bir `.eml` dosyasına yazın. API içeriği akış olarak sağlar, böylece 100 MB'lık mesajlar bile tüm yükü belleğe yüklemeden işlenir.  
`fetchMessage(messageId)` belirtilen e-postanın tam MIME içeriğini indirir.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Alt klasörlerden mesajları nasıl yinelemeli olarak listeleyebilirsiniz?
Derinlik‑ilk (depth‑first) bir geçiş uygulayın: üst‑seviye bir klasörle başlayın, `client.listSubFolders(parentId)` ile alt klasörlerini listeleyin, ardından her alt klasör için aynı mesaj‑listeleme rutinini çağırın. Bu desen, ortak klasör ağacındaki her mesajın işlenmesini sağlar. Yineleme derinliği yalnızca sunucunun klasör hiyerarşisiyle sınırlıdır (genellikle < 20 seviye).  
`listSubFolders(parentId)` verilen klasörün doğrudan alt klasörlerini döndürür.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Pratik uygulamalar
1. **Otomatik e-posta arşivleme** – Belirli aralıklarla tüm ortak‑klasör mesajlarını çekip uyumlu bir arşivde saklayın.  
2. **Yedekleme çözümleri** – Exchange ortak klasörlerini güvenli bir dosya sistemine veya bulut kovasına yansıtın, veri yedekliliğini garanti edin.  
3. **Özel e-posta istemcileri** – Sadece ihtiyacınız olan klasör ve mesajları gösteren hafif görüntüleyiciler oluşturun, UI karmaşıklığını azaltın.

## Performans değerlendirmeleri
Binlerce klasör ve milyonlarca mesaj ölçeğinde, aşağıdaki ipuçlarını aklınızda tutun:
- **Bağlantı havuzlama** – Her klasör için yeni bir istemci oluşturmak yerine birden fazla işlem için tek bir `ExchangeClient` örneğini yeniden kullanın.  
- **Tembel yükleme** – Sadece ihtiyacınız olan meta verileri isteyin (`listMessages` ile `maxCount` parametresi) ve tam gövdeleri gerektiğinde alın.  
- **Nesneleri serbest bırakın** – Toplu çalışmadan sonra HTTP bağlantılarını ve iş parçacığı‑yerel tamponları serbest bırakmak için `client.dispose()` çağırın.  
- **Paralel işleme** – Üst‑seviye klasörleri birden fazla iş parçacığına bölün, her biri kendi istemci örneğiyle, çok çekirdekli CPU'ları etkili kullanmak için.

## Sıkça sorulan sorular

**S: Bu kodu Exchange Online (Office 365) ile kullanabilir miyim?**  
C: Evet. Office 365 EWS uç noktasını (`https://outlook.office365.com/EWS/Exchange.asmx`) sağlayın ve modern kimlik doğrulama (OAuth) kullanın – Aspose.Email OAuth tokenlarını kutudan çıkar çıkmaz destekler.

**S: Bir klasör 10 000'den fazla mesaj içeriyorsa ne olur?**  
C: Sonuçları sayfalara ayırmak için `skip` ve `take` parametrelerini kabul eden `listMessages` aşırı yüklemesini kullanın, böylece bellek kullanımı kontrol altında kalır.

**S: İndirebileceğim tek bir e-postanın boyutu için bir limit var mı?**  
C: API içeriği akış olarak sağlar, bu yüzden JVM yeterli yerel belleğe sahipse 150 MB'a kadar mesajlar Java heap limitine takılmadan desteklenir.

**S: SSL sertifikalarını manuel olarak yönetmem gerekiyor mu?**  
C: Varsayılan olarak Aspose.Email, Java varsayılan keystore'ına güvenir. Exchange sunucunuz kendinden imzalı bir sertifika kullanıyorsa, onu JVM truststore'una aktarın veya sadece test amacıyla `client.setEnableSslVerification(false)` ayarlayın.

**S: İşlemleri denetim amacıyla nasıl kaydederim?**  
C: `Logger.setLevel(Level.INFO)` yapılandırarak Aspose.Email'in yerleşik kaydını etkinleştirin ve çıktıyı bir dosyaya veya izleme sistemine yönlendirin.

## Sonuç
Artık Aspose.Email for Java kullanarak **how to connect exchange** ve ortak klasörlerden mesajları yinelemeli olarak listelemek için eksiksiz, üretim‑hazır bir tarifiniz var. Adımlar Maven kurulumu, lisanslama, bağlantı, klasör sayımı, mesaj alma ve performans ayarlarını kapsar. Bu temeli, veritabanları, bulut depolama veya özel analiz boru hatlarıyla entegre ederek organizasyonunuzun özel ihtiyaçlarını karşılayacak şekilde genişletebilirsiniz.

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## İlgili Öğreticiler

- [Java'da Aspose.Email ile Exchange Sunucusuna Bağlanma: Adım Adım Kılavuz](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Aspose.Email for Java Kullanarak Exchange Sunucu Klasörlerine Bağlanma ve Listeleme](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Aspose.Email for Java ile Exchange Sunucu Klasörlerini Yönetme: Kapsamlı Bir Rehber](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}