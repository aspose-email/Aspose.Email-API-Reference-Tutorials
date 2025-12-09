---
date: 2025-12-01
description: Aspose.Email for Java kullanarak gömülü resimli e-posta göndermeyi öğrenin.
  Bu kılavuz, e-postaya resim eklemeyi ve satır içi eklerle HTML e-posta oluşturmayı
  gösterir.
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Aspose.Email for Java ile Gömülü Görsel İçeren E-posta Nasıl Gönderilir
url: /tr/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java kullanarak Gömülü Görüntülü E-posta Nasıl Gönderilir

Görselleri doğrudan bir e-postanın içine gömmek, mesajlarınızın daha profesyonel görünmesini sağlar ve alıcının grafikleri ayrı dosyalar indirmesine gerek kalmadan görmesini garantiler. Bu öğreticide Aspose.Email for Java kullanarak **gömülü görselli e-posta nasıl gönderilir** öğrenecek, kütüphanenin kurulumu, HTML e-posta oluşturma, satır içi kaynak ekleme ve son olarak mesajı gönderme konularını kapsayacaksınız.

## Hızlı Yanıtlar
- **Satır içi görseller için birincil sınıf nedir?** `LinkedResource`
- **HTML içinde görsele hangi yöntem referans verir?** `<img>` etiketinde `cid:yourContentId` kullanın
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için lisans gereklidir
- **E-postayı herhangi bir SMTP sunucusu üzerinden gönderebilir miyim?** Evet, sadece `SmtpClient`'ı sunucu detaylarınızla yapılandırın
- **Bu yaklaşım tüm büyük e-posta istemcileriyle uyumlu mu?** Çoğu modern istemci (Outlook, Gmail, Thunderbird) CID‑gömülü görselleri destekler

## Satır İçi Ekler (Gömülü Görseller) Nedir?

Satır içi ekler—bazen gömülü veya CID görselleri olarak adlandırılır—bir e-postanın MIME gövdesi içinde yer alan dosyalardır. Mesajın HTML kısmından **Content‑ID** (CID) ile referans verilir. Bu teknik, **görselleri e-postaya gömmenizi** sağlar; böylece `<img>` etiketini yerleştirdiğiniz yerde görünürler ve ayrı indirilebilir ekler olarak ortaya çıkmazlar.

## Java E-postalarınızda Gömülü Görselleri Neden Kullanmalısınız?

- **Profesyonel görünüm:** Logolar, afişler ve ürün resimleri anında görüntülenir.
- **Daha iyi etkileşim:** Alıcılar, eksiksiz görünen bir e-postayı okuma olasılığı daha yüksektir.
- **Ek tıklama yok:** Kullanıcıların görseli görmek için ek indirmesine gerek yoktur.
- **Tutarlı marka:** Marka varlıklarınız mesaj içeriğiyle aynı satırda kalır.

## Önkoşullar

- Aspose.Email for Java kütüphanesi (resmi [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/) adresinden indirin)
- Java 8+ geliştirme ortamı
- E-posta göndermek için bir SMTP sunucusuna erişim
- Gömmek istediğiniz görüntü dosyası (ör. `logo.png`)

## Adım Adım Kılavuz

### Adım 1: Temel Bir HTML E-posta Mesajı Oluşturun

İlk olarak, HTML gövdesiyle basit bir `MailMessage` oluşturun. Bu, daha sonra görseli gömeceğimiz tuval olacaktır.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Adım 2: `LinkedResource` Kullanarak Satır İçi Görsel Ekleyin

Şimdi bir görsel gömüyoruz. `LinkedResource` sınıfı satır içi eki temsil eder. Benzersiz bir **Content‑ID** atayın ve HTML gövdesinde `cid:` ile referans verin.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Pro ipucu:** `ContentId`'yi mesaj içinde basit ve benzersiz tutarak çakışmaları önleyin.

### Adım 3: `SmtpClient` ile E-postayı Gönderin

SMTP ayarlarınızı yapılandırın ve mesajı gönderin. Gömülü görsel e-posta ile birlikte taşınır, böylece alıcı onu anında görür.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Adım 4: Satır İçi Görselleri Alın ve Çıkarın (İsteğe Bağlı)

Eğer gömülü görseller içeren gelen mesajları işlemek istiyorsanız, `.eml` dosyasını yükleyebilir ve `LinkedResources`'ına erişebilirsiniz.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Yaygın Sorunlar ve Çözüm Yolları

| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| **Content‑ID eşleşmemesi** | `cid:` referansı HTML içinde `LinkedResource`'a ayarlanan `ContentId` ile eşleşmiyor. | Dizelerin aynı olduğundan emin olun (`image001` vs `cid:image001`). |
| **Dosya bulunamadı** | Görselin yolu yanlış veya dosya eksik. | Mutlak/göreli yolu ve dosyanın sunucuda mevcut olduğunu doğrulayın. |
| **SMTP kimlik doğrulama hatası** | Yanlış kimlik bilgileri veya sunucu ayarları. | Sunucu, port, kullanıcı adı ve şifreyi tekrar kontrol edin. Gerekirse TLS/SSL etkinleştirin. |
| **Bazı istemcilerde görsel gösterilmiyor** | Bazı istemciler dış kaynakları engeller. | Dış URL'ler yerine CID‑gömülü görseller kullanın (gösterildiği gibi). |

## Sıkça Sorulan Sorular

**S: Aspose.Email for Java'ı nasıl indiririm?**  
C: Aspose.Email for Java'ı [documentation](https://reference.aspose.com/email/java/) adresinden indirebilirsiniz. Projenize kurmak için kurulum talimatlarını izleyin.

**S: Aspose.Email for Java'ı diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Email diğer Java kütüphaneleriyle sorunsuz entegre olur, e-posta işleme ile PDF oluşturma, OCR veya veritabanı erişimini birleştirmenizi sağlar.

**S: Satır içi ekler için hangi dosya formatları desteklenir?**  
C: PNG, JPEG, GIF gibi yaygın görüntü formatları ve diğer belge türleri (ör. SVG) satır içi kaynak olarak desteklenir.

**S: HTML e-postalarında satır içi ekleri nasıl yönetirim?**  
C: `LinkedResource` sınıfını kullanarak bir `ContentId` atayın, `message.getLinkedResources()`'a ekleyin ve HTML gövdesinde `<img src='cid:yourContentId'>` ile referans verin.

**S: Aspose.Email for Java farklı e-posta sunucularıyla uyumlu mu?**  
C: Evet, herhangi bir SMTP/IMAP/POP3 sunucusuyla çalışır. Doğru sunucu adresi, port ve kimlik doğrulama bilgilerini sağlayın.

**Son Güncelleme:** 2025-12-01  
**Test Edilen Sürüm:** Aspose.Email for Java 24.12 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}