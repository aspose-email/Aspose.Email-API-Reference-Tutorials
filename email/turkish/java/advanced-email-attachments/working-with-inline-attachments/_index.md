---
date: 2026-04-28
description: Aspose.Email for Java kullanarak HTML e-postaya resim nasıl gömülür ve
  gömülü resimle SMTP üzerinden e-posta nasıl gönderilir öğrenin.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Aspose.Email'de Satır İçi Eklerle Çalışma
second_title: Aspose.Email Java Email Management API
title: Aspose.Email for Java ile HTML e-postaya resim nasıl gömülür
url: /tr/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java ile HTML e-postada görüntü nasıl gömülür

Bir e-postanın içine doğrudan bir görüntü gömmek, mesajlarınızın daha profesyonel görünmesini sağlar ve alıcının ayrı dosyaları indirmesine gerek kalmadan grafikleri görmesini garanti eder. Bu öğreticide, Aspose.Email for Java kullanarak **HTML e-postada görüntü nasıl gömülür** öğrenecek, kütüphane kurulumundan HTML e-posta oluşturulmasına, satır içi kaynakların eklenmesine ve son olarak mesajın SMTP üzerinden gönderilmesine kadar her şeyi kapsayacağız.

## Hızlı Yanıtlar
- **Satır içi görüntüler için birincil sınıf nedir?** `LinkedResource`
- **HTML içinde görüntüyü hangi yöntem referans alır?** `<img>` etiketinde `cid:yourContentId` kullanın
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için lisans gereklidir
- **E-postayı herhangi bir SMTP sunucusu üzerinden gönderebilir miyim?** Evet, sadece `SmtpClient`'ı sunucu detaylarınızla yapılandırın
- **Bu yaklaşım tüm büyük e-posta istemcileriyle uyumlu mu?** Çoğu modern istemci (Outlook, Gmail, Thunderbird) CID‑gömülü görüntüleri destekler

## Aspose.Email for Java kullanarak HTML e-postada görüntü nasıl gömülür

HTML e-postada **görüntü gömdüğünüzde**, görüntü MIME gövdesinin bir parçası haline gelir ve alıcının istemcisinde anında görüntülenir. Aşağıda, basit bir HTML mesajdan satır içi bir resim içeren tam özellikli bir e-postaya kadar tam süreci adım adım inceleyeceğiz.

### Satır içi Ekler (Gömülü Görüntüler) Nedir?

Satır içi ekler—bazen gömülü veya CID görüntüleri olarak adlandırılır—bir e-postanın MIME gövdesi içinde bulunan dosyalardır. Mesajın HTML bölümünden **Content‑ID** (CID) ile referans alınırlar. Bu teknik, **görüntüleri e-postaya gömmenizi** sağlar; böylece `<img>` etiketini yerleştirdiğiniz yerde görünürler ve ayrı indirilebilir ekler olarak ortaya çıkmazlar.

### Java E-postalarınızda Gömülü Görüntüleri Neden Kullanmalısınız?

- **Profesyonel görünüm:** Logolar, afişler ve ürün resimleri anında görüntülenir.
- **Daha iyi etkileşim:** Alıcılar, eksiksiz görünen bir e-postayı okuma olasılığı daha yüksektir.
- **Ek tıklama yok:** Kullanıcıların görüntüyü görmek için bir eki indirmesine gerek yoktur.
- **Tutarlı marka kimliği:** Marka varlıklarınız mesaj içeriğiyle aynı satırda kalır.

### Önkoşullar

- Aspose.Email for Java kütüphanesi (resmi [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/) adresinden indirin)
- Java 8+ geliştirme ortamı
- E-posta gönderimi için bir SMTP sunucusuna erişim
- Gömmek istediğiniz görüntü dosyası (ör. `logo.png`)

## Adım‑Adım Kılavuz

### Adım 1: Temel Bir HTML E-posta Mesajı Oluşturun

İlk olarak, HTML gövdesi olan basit bir `MailMessage` oluşturun. Bu, daha sonra görüntüyü gömeceğimiz bir tuval olacaktır.

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

### Adım 2: `LinkedResource` Kullanarak Satır İçi Görüntü Ekleyin

Şimdi bir görüntü gömüyoruz. `LinkedResource` sınıfı satır içi eki temsil eder. Benzersiz bir **Content‑ID** atayın ve HTML gövdesinde `cid:` ile referans verin.

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

> **Pro ipucu:** Çakışmaları önlemek için mesaj içinde `ContentId` değerini basit ve benzersiz tutun.

### Adım 3: `SmtpClient` ile E-postayı Gönderin

SMTP ayarlarınızı yapılandırın ve mesajı gönderin. Gömülü görüntü e-posta ile birlikte taşınır, böylece alıcı onu anında görür.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Adım 4: Satır İçi Görüntüleri Alın ve Çıkarın (İsteğe Bağlı)

Eğer gömülü görüntüler içeren gelen mesajları işlemek istiyorsanız, `.eml` dosyasını yükleyebilir ve `LinkedResources` öğesine erişebilirsiniz.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Yaygın Sorunlar ve Çözümleri

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **Content‑ID uyumsuzluğu** | `cid:` referansı HTML içinde `LinkedResource` üzerinde ayarlanan `ContentId` ile eşleşmiyor. | Dizelerin aynı olduğundan emin olun (`image001` vs `cid:image001`). |
| **Dosya bulunamadı** | Görüntünün yolu hatalı veya dosya eksik. | Mutlak/göreceli yolu ve dosyanın sunucuda mevcut olduğunu doğrulayın. |
| **SMTP kimlik doğrulama hatası** | Yanlış kimlik bilgileri veya sunucu ayarları. | Ana bilgisayar, port, kullanıcı adı ve şifreyi tekrar kontrol edin. Gerekirse TLS/SSL etkinleştirin. |
| **Bazı istemcilerde görüntü gösterilmiyor** | Bazı istemciler harici kaynakları engeller. | Harici URL'ler yerine CID‑gömülü görüntüler kullanın (gösterildiği gibi). |

## Sık Sorulan Sorular

**S: Aspose.Email for Java'ı nasıl indirebilirim?**  
C: Aspose.Email for Java'ı resmi [documentation](https://reference.aspose.com/email/java/) adresinden indirebilirsiniz. Projenize kurmak için kurulum talimatlarını izleyin.

**S: Aspose.Email for Java'ı diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Email diğer Java kütüphaneleriyle sorunsuz entegre olur ve e-posta işleme ile PDF oluşturma, OCR veya veritabanı erişimini birleştirmenizi sağlar.

**S: Satır içi ekler için hangi dosya formatları desteklenir?**  
C: PNG, JPEG, GIF gibi yaygın görüntü formatları ve diğer belge türleri (ör. SVG) satır içi kaynak olarak desteklenir.

**S: HTML e-postalarda satır içi ekleri nasıl yönetirim?**  
C: `LinkedResource` sınıfını kullanarak bir `ContentId` atayın, `message.getLinkedResources()`'a ekleyin ve HTML gövdesinde `<img src='cid:yourContentId'>` ile referans verin.

**S: Aspose.Email for Java farklı e-posta sunucularıyla uyumlu mu?**  
C: Evet, herhangi bir SMTP/IMAP/POP3 sunucusuyla çalışır. Doğru sunucu adresi, port ve kimlik doğrulama bilgilerini sağlayın.

## Sonuç

Artık Aspose.Email for Java ile **HTML e-postada görüntü gömme** için eksiksiz, üretim‑hazır bir tarifiniz var. Bir `LinkedResource` oluşturarak, benzersiz bir Content‑ID atayarak ve HTML gövdesinde `cid:` ile referans vererek, logoların, afişlerin veya ürün fotoğraflarının tam istediğiniz yerde görünmesini sağlarsınız—ek indirmeler veya kırık bağlantılar olmadan. Bu güçlü `SmtpClient` sınıfı ile mesajı herhangi bir SMTP sunucusundan gönderin ve Java uygulamalarınızdan profesyonel, marka‑uyumlu e-postalar göndermeye hazır olun.

---

**Son Güncelleme:** 2026-04-28  
**Test Edilen Versiyon:** Aspose.Email for Java 24.12 (latest at time of writing)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}