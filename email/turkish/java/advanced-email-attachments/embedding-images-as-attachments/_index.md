---
date: 2026-04-21
description: Aspose.Email for Java kullanarak bir görüntüyü HTML e-postaya nasıl gömeceğinizi
  öğrenin, gömülü görüntülü HTML e-posta gönderin ve e-posta ekinin boyutunu azaltın.
keywords:
- embed image html email
- send html email java
- create email with image
- reduce email attachment size
- embed multiple images email
linktitle: Aspsoe.Email ile E-postaya Resim Ekleme
second_title: Aspose.Email Java Email Management API
title: Aspose.Email for Java ile HTML e-postaya resim nasıl gömülür
url: /tr/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java ile Görüntü HTML E-posta Gömme

Modern e-posta iletişiminde, **embed image html email** artık her zamankinden daha önemli—görseller etkileşimi artırır ve mesajınızı anında iletir. Bu öğreticide bir görüntüyü ekleme, HTML gövdesine gömme ve mesajın tüm posta istemcilerinde güzel görünmesini sağlama sürecini adım adım anlatacağız. Ayrıca **send html email java**, görüntülü e-posta oluşturma ve **reduce email attachment size** konularında en iyi uygulama ipuçlarını da ele alacağız.

## Hızlı Yanıtlar
- **E-posta oluşturmak için birincil sınıf nedir?** `MailMessage`
- **HTML gövdesine bir görüntüyü gömmeyi sağlayan sınıf hangisidir?** `LinkedResource`
- **Üretimde e-posta göndermek için lisansa ihtiyacım var mı?** Evet, ticari bir Aspose.Email lisansı gereklidir.
- **Ek boyutunu nasıl azaltabilirim?** Görüntüyü eklemeden önce optimize edin (ör. yeniden boyutlandırma/sıkıştırma).
- **Birden fazla görüntü gönderebilir miyim?** Kesinlikle—her biri için benzersiz bir Content‑ID ekleyin.

## Görüntü HTML e-posta gömme nedir?
Bir görüntüyü eklemek, dosyayı e-postanın MIME yapısına eklemek anlamına gelir, böylece alıcı görüntüyü görebilir. Görüntüyü bir Content‑ID (CID) ile gömdüğünüzde, görüntü ayrı bir ek yerine HTML gövdesinin içinde görünür ve satır içi bir resim gibi görünür.

## Neden gömülü görüntülü HTML e-posta gönderilir?
HTML içinde görüntü gömmek, daha zengin bültenler, ürün duyuruları veya destek biletleri tasarlamanızı sağlar. Alıcılar görseli anında görür, ek indirmeye gerek kalmaz; bu da açılma oranlarını ve genel etkileşimi artırır.

## Önkoşullar
Başlamadan önce şunların olduğundan emin olun:

- **Aspose.Email for Java** – resmi siteden indirin: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Geçerli bir **SMTP sunucusu** (ör. Gmail, Outlook veya kendi posta geçidiniz).
- Gömmek istediğiniz bir görüntü dosyası (JPEG, PNG, GIF vb.).

> **Pro tip:** *E-posta için görüntü boyutunu* genişliği ≤600 px ve boyutu ≤100 KB olacak şekilde yeniden boyutlandırıp sıkıştırın. Bu, yükleme süresini azaltır ve posta kutusu boyut sınırlarını aşmaz.

## E-posta Mesajı Oluşturma
İlk olarak, gerekli ad alanlarını içe aktarın ve bir `MailMessage` örneği oluşturun. Bu nesne, e-postanızın konusunu, alıcılarını ve gövdesini tutacaktır.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Görüntüyü Ek Olarak Ekleme
Sonra, disk üzerindeki görüntü dosyasına işaret edin ve mesajın ek koleksiyonuna ekleyin. Ek daha sonra bir Content‑ID ile referans verilecektir.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Eklenen Görüntüyü HTML'e Gömme
Görüntüyü e-posta gövdesinde göstermek için, ekin akışını saran bir `LinkedResource` oluşturun. Benzersiz bir Content‑ID (ör. `image1`) atayın ve HTML içinde `cid:` URI şemasıyla referans verin.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Neden `LinkedResource` kullanılır?** Bu, posta istemcisine görüntünün mesaj gövdesinin bir parçası olduğunu, ayrı bir indirme olmadığını bildirir; bu da **send HTML email with embedded image** senaryoları için kritiktir.

## E-postayı Gönderme
Son olarak, `SmtpClient`'ı sunucu ayrıntılarınızla yapılandırın ve mesajı gönderin. SMTP kimlik bilgilerinin gönderici adresi adına gönderim izni olduğundan emin olun.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Alıcı e-postayı açtığında, HTML gövdesi görüntüyü satır içi olarak render eder ve kesintisiz bir görsel deneyim sunar.

## Birden fazla görüntüyü e-postaya gömme
Birden fazla resim gerekiyorsa, her dosya için ek ve `LinkedResource` adımlarını tekrarlayın. `image2`, `image3` gibi farklı Content‑ID'ler atayın ve HTML'de (`src='cid:image2'` vb.) referans verin. Bu yaklaşım, birden çok grafik içeren bültenler için kolayca ölçeklenir.

## E-posta ek boyutunu azaltma ipuçları
- **Yeniden boyutlandır** görüntüyü e-postada ihtiyaç duyulan tam boyutlara (genellikle ≤600 px genişlik) göre ayarlayın.  
- **Sıkıştır** ImageMagick gibi araçlarla veya çevrimiçi sıkıştırıcılarla dosyayı 100 KB altında tutun.  
- **Doğru formatı seç**: Fotoğraflar için JPEG, şeffaflık gerektiren grafikler için PNG.  
- **EXIF meta verilerini kaldır** eğer gerekli değilse.

## Yaygın Sorunlar ve Sorun Giderme
| Sorun | Neden | Çözüm |
|-------|-------|----------|
| Görüntü gösterilmiyor | Yanlış Content‑ID veya eksik `LinkedResource` | `linkedImage.setContentId("image1")` ifadesinin HTML'deki `src='cid:image1'` ile eşleştiğini doğrulayın. |
| Büyük e-posta boyutu | Optimize edilmemiş görüntü (yüksek çözünürlük) | Eklemeye önce görüntüyü yeniden boyutlandırıp sıkıştırın; hedef ≤100 KB. |
| E-posta spam olarak işaretlendi | Uygun MIME başlıkları eksik | `SmtpClient` TLS/STARTTLS kullanmalı ve net bir `From` adresi ayarlamalıdır. |
| Satır içi görüntü ek olarak görünüyor | İstemci CID'yi desteklemiyor | `<img>` etiketine bir yedek URL ekleyin (`src='cid:image1' alt='Image'`). |

## Sıkça Sorulan Sorular

**S: Tek bir e-posta içinde birden fazla görüntüyü nasıl gömebilirim?**  
C: Her görüntü için ek ve `LinkedResource` adımlarını tekrarlayın, benzersiz bir Content‑ID (ör. `image2`, `image3`) atayın ve HTML'de referans verin.

**S: Görüntüleri düz metin e-postalarına gömebilir miyim?**  
C: Düz metin formatı gömülü görüntüleri desteklemez. Sadece alıcıların görüntüyü çevrimiçi olarak görebileceği URL'ler ekleyebilirsiniz.

**S: E-posta gömme için hangi görüntü formatları güvenlidir?**  
C: JPEG, PNG ve GIF yaygın olarak desteklenir. Fotoğraflar için JPEG, şeffaf grafikler için PNG kullanın.

**S: E-posta içinde görüntü boyutlarını kontrol etmenin bir yolu var mı?**  
C: Evet—`<img>` etiketine `width`/`height` nitelikleri ekleyin, ör. `<img src='cid:image1' width='400' height='300'>`.

**S: Gömülü görüntüler için boyut sınırlamaları var mı?**  
C: Kesin bir SMTP limiti olmasa da, çoğu posta sağlayıcısı toplam e-posta boyutunun 5 MB altında olmasını önerir. Görüntü boyutunu optimize etmek bu sınır içinde kalmanıza yardımcı olur.

---

**Son Güncelleme:** 2026-04-21  
**Test Edilen:** Aspose.Email for Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}