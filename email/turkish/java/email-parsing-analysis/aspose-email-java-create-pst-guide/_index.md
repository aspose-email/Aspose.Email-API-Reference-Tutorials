---
date: '2026-06-08'
description: Aspose.Email for Java ile PST dosyaları nasıl oluşturulur, klasör yapıları
  nasıl eklenir ve PST içeriği nasıl verimli bir şekilde aranır öğrenin. Adım adım
  rehber.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Aspose.Email for Java ile PST Dosyaları Nasıl Oluşturulur
url: /tr/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java ile E-posta Yönetimini Ustalıkla Öğrenin

Programatik olarak **how to create pst** dosyaları oluşturmanız gerekiyorsa, doğru yerdesiniz. Bu öğreticide Unicode PST dosyası oluşturmak, standart Outlook klasörleri eklemek, mesajları içe aktarmak ve büyük/küçük harfe duyarsız aramalar gerçekleştirmek için gerekli tüm adımları ele alacağız — tümü Aspose.Email for Java kullanılarak. Sonunda, birkaç e-postadan çok gigabaytlık arşivlere kadar ölçeklenebilen yeniden kullanılabilir bir kod kalıbına sahip olacaksınız.

## Hızlı Yanıtlar
- **Nasıl Başlarım?** Aspose.Email Maven bağımlılığını ekleyin, bir lisans edinin ve `PersonalStorage` nesnesini örnekleyin.
- **Inbox klasörü ekleyebilir miyim?** Evet – `pst.getRootFolder().addSubFolder("Inbox")` çağrısını yapın.
- **Büyük/küçük harfe duyarsız arama destekleniyor mu?** `PersonalStorageQueryBuilder` ile `StringComparison.OrdinalIgnoreCase` kullanın.
- **Hangi dosya boyutu işlenebilir?** Aspose.Email, tüm dosyayı belleğe yüklemeden 2 GB’a kadar PST dosyalarını işler.
- **Üretim için ücretli bir lisansa ihtiyacım var mı?** Kalıcı bir lisans deneme sınırlarını kaldırır ve tam performans özelliklerini açar.

## how to create pst nedir?
**how to create pst**, Outlook Kullanıcı Depolama Tablosu (PST) dosyasını Outlook arayüzü yerine kod kullanarak oluşturma sürecine denir. Aspose.Email for Java, Unicode PST dosyaları oluşturan, klasör ekleyen ve `MapiMessage` nesnelerini Outlook kurulu olmadan depolayan tam yönetilen bir API sağlar.

## PST Oluşturma İçin Aspose.Email Neden Kullanılmalı?
Aspose.Email, **50+** e-posta formatını (MSG, EML, MBOX, PST vb.) destekler ve **2 GB**’a kadar PST dosyalarını **150 MB**’ın altında bellek kullanımıyla işleyebilir; bu, gecikmeli yükleme mimarisi sayesinde mümkün olur. Bu ölçülen yetenek, kurumsal arşivleme, taşıma ve uyumluluk senaryoları için idealdir.

## Önkoşullar

- **Java Development Kit (JDK)** – sürüm 16 veya üzeri.
- **Maven** – bağımlılık yönetimi için.
- Java sözdizimine temel aşinalık; PST dosyalarıyla daha önce çalışmış olmanız gerekmez.

## PST Dosyası Nasıl Oluşturulur?
`PersonalStorage` sınıfı bir PST dosyasını temsil eder ve içeriğini oluşturma, açma ve yönetme yöntemleri sunar. Yeni bir Unicode PST oluşturmak için istenen dosya yolu ve format sürümüyle `PersonalStorage.create()` çağrısı yapılır. Bu işlem, büyük klasörler, Unicode karakterler ve verimli akış desteği sunan modern bir PST üretir; hem küçük ölçekli hem de kurumsal düzeyde arşivleme görevleri için uygundur.

### Adım 1: Maven Bağımlılığını Ekleyin

Aspose.Email Maven bağımlılığını `pom.xml` dosyanıza ekleyin. Bu, gerekli tüm ikili dosyaları otomatik olarak çeker.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Adım 2: Lisans Alın ve Uygulayın

Ücretsiz bir deneme mevcuttur, ancak kalıcı bir lisans değerlendirme sınırlamalarını kaldırır ve tam‑hızlı işleme olanak tanır.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## PST'ye Klasör Nasıl Eklenir?
İstenilen klasör hiyerarşisini PST kökünün altında oluşturun, ardından mesaj eklerken bu klasöre referans verin. `FolderInfo` nesnesi her klasörü temsil eder ve isteğe bağlı olarak iç içe geçirilebilir; bu sayede Inbox, Sent Items veya özel proje klasörleri gibi yapılar kurabilirsiniz. Klasör ekleme, mesaj içeriğini yüklemediği için hafif bir işlemdir ve büyük PST'lerde bile performansı korur.

### Adım 1: PersonalStorage'ı Başlatın

`PersonalStorage` sınıfı, Aspose.Email'in bellek içindeki tek PST dosyasını temsil eden üst‑seviye nesnesidir. Oluşturulduktan sonra tüm okuma ve yazma işlemleri bu nesne üzerinden gerçekleşir.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Adım 2: Dizin Yollarını Tanımlayın

E-posta dosyalarınızın kaynak ve hedef yollarını ve PST çıkış konumunu ayarlayın.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Adım 3: PST Dosyasını Oluşturun

`FileFormatVersion.Unicode` ile `PersonalStorage.create()` çağrısı yaparak büyük klasörler ve Unicode karakterler destekleyen modern bir Unicode PST üretin.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## pst Nasıl Aranır?
`PersonalStorageQueryBuilder`, PST içeriği için arama sorguları oluşturmak üzere kullanılan bir builder sınıfıdır. Builder'ı istenen kriterlerle yapılandırıp `StringComparison.OrdinalIgnoreCase` belirterek, konu, gövde ve özel özelliklerde büyük/küçük harfe duyarsız, hızlı aramalar yapabilirsiniz; tüm PST belleğe yüklenmez.

### Adım 1: Arama Sorgusunu Oluşturun

Konu veya gövde içinde anahtar kelimeyi büyük/küçük harf duyarsız olarak arayan bir sorgu oluşturun.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Adım 2: Sorguyu Çalıştır ve Mesajları Al

Sorguyu hedef klasörde çalıştırın ve elde edilen `MapiMessage` koleksiyonunu yineleyin.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## PST'de Ön Tanımlı Klasör Oluşturma
Ön tanımlı bir klasör (ör. **Inbox**) eklemek, e-posta verilerinizi etkili bir şekilde düzenlemenize yardımcı olur.

### Adım 1: PersonalStorage Nesnesini Başlatın
`PersonalStorage` nesnesinin (`pst`) daha önce gösterildiği gibi oluşturulduğunu varsayın.

### Adım 2: 'Inbox' Klasörünü Oluşturun

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## PST Klasörüne Mesaj Ekleme
PST klasörünüzü, dosyalardan yükleyip dönüştürerek e-posta mesajlarıyla doldurun.

### Adım 1: E-posta Mesajını Yükle

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Adım 2: PST Klasörüne Ekle
`MailMessage`'ı `MapiMessage`'a dönüştürün ve ekleyin:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Pratik Uygulamalar
Aspose.Email for Java sadece PST dosyası oluşturmakla sınırlı değildir; çok çeşitli uygulamalara sahiptir:
- **E-posta Arşivleme**: Kurumsal e-postaları PST dosyalarına otomatik olarak arşivleyin, 10 yıla kadar saklama politikalarını destekleyin.
- **Taşıma Araçları**: Tek bir API çağrısıyla eski posta depolarını (ör. MBOX) Outlook PST'ye sorunsuzca taşıyın.
- **Veri Analizi**: Gönderici, alıcı ve zaman damgaları gibi meta verileri iş zekası boru hatları için çıkarın.
- **Yedekleme Çözümleri**: Tüm posta kutusunu yeniden işleme almadan artımlı e-posta değişikliklerini depolayan sağlam yedekleme araçları oluşturun.

## Performans Düşünceleri
Aspose.Email kullanırken optimum performans sağlamak için:
- **Kaynak Yönetimi**: `pst.dispose()` çağrısını her zaman yapın veya try‑with‑resources kullanarak yerel tutucuları hızlıca serbest bırakın.
- **Toplu İşleme**: Bellek kullanımını öngörülebilir tutmak için e-postaları **500** öğe grupları halinde işleyin.
- **Eşzamanlılık Yönetimi**: Kütüphane yalnızca okuma‑sadece işlemler için çok iş parçacıklı güvenlidir; yazma işlemleri için `PersonalStorage` örneğine erişimi senkronize edin.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-------|
| **OutOfMemoryError** when handling large PSTs | Tüm PST belleğe yükleniyor | `PersonalStorage.setUseUnicode(true)` etkinleştirin ve mesajları akış olarak işleyin. |
| **Folder not found** error | Klasör yolu büyük/küçük harf duyarlılığı hatalı | Sorgularda `StringComparison.OrdinalIgnoreCase` kullanın veya klasör adlarını normalleştirin. |
| **License not applied** | Lisans dosyası ilk API çağrısından önce yüklenmemiş | Lisansı, herhangi bir `PersonalStorage` nesnesi oluşturmadan önce uygulama başlangıcında yükleyin. |

## Sıkça Sorulan Sorular

**S: Minimum Java sürümü nedir?**  
C: Tam uyumluluk için JDK 16 veya üzeri önerilir.

**S: Lisans olmadan Aspose.Email kullanabilir miyim?**  
C: Evet, deneme modu mevcuttur ancak PST boyutu **10 MB** ile sınırlıdır ve bazı optimizasyonlar devre dışı bırakılır.

**S: Büyük PST dosyalarını verimli şekilde nasıl yönetirim?**  
C: Mesajları toplu olarak işleyin, `MapiMessage` nesnelerini hızlıca serbest bırakın ve `PersonalStorage.setUseUnicode(true)` ile gecikmeli yüklemeyi etkinleştirin.

**S: PST dosyalarındaki e-postalara ek dosya ekleyebilir miyim?**  
C: Kesinlikle. `MailMessage`'ı `MapiMessage`'a dönüştürürken `mapiMsg.getAttachments().add(attachment)` çağrısıyla dosyaları gömebilirsiniz.

**S: Sorun giderme konusunda ne tür destek alabilirim?**  
C: Aspose, lisanslı müşteriler için özel destek forumu, kapsamlı dokümantasyon ve e‑posta desteği sunar.

## Kaynaklar
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Son Güncelleme:** 2026-06-08  
**Test Edilen Versiyon:** Aspose.Email for Java 24.10  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Email for Java Kullanarak Outlook PST Dosyaları Oluşturma ve Yönetme](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Aspose.Email for Java ile PST Dosyalarını Manipüle Etme: Kapsamlı Rehber](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Java’da E-posta Eklerini Çıkarma - Aspose.Email ile PST Dosyaları – Adım Adım Kılavuz](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}