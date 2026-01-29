---
date: 2026-01-29
description: Aspose.Email for Java kullanarak resim ekli e-posta nasıl eklenir, resimli
  HTML e-posta nasıl gömülür, HTML e-posta nasıl gönderilir ve SMTP Java ile e-posta
  boyutu nasıl azaltılır öğrenin.
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: Aspose.Email for Java ile E-postaya Resim Ekleme
url: /tr/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java ile E-postaya Görüntü Ekleme

Modern e-posta iletişiminde, **e-postaya görüntü eklemeörseller etkileşimi artırır ve mesajınızı anında iletmeye yardımcı olur. Bu rehberde **e-postaya görüntü ekleme** yöntemini Aspose.Email for Java kullanarak öğrenecek, resmi bir HTML gövdesine gömecek ve güvenilir teslimat için mesaj boyutunu küçük tutacaksınız.

## Hızlı Yanıtlar
- **E-posta oluşturmak için birincil sınıf nedir?** `MailMessage`
- **HTML gövdesine bir görüntüyü gö Evet, ticari bir Aspose.Email lisansı gereklültebilirim?** Eklemeye eklemeden önce görüntüyü optimize edin (ör. yeniden boyutlandırma/sıkıştırma).
- **Birden fazla görüntü gönderebilir miyim?** Kesinlikle—her biri için benzersiz bir Content‑ID ekleyin.
- **Java ile en iyi çalışan SMTP ayarları nelerdir?** Çoğu sağlayıcı için 587 portunda TLS/STARTTLS kullanın (`smtp email java`).

## Görüntüyü e-postaya eklemek ne demektir?
Bir görüntüyü eklemek, dosyayı e-postanın MIME yapıs) kullanarak gömdüğünüzde, görüntü ayrı bir ek yerine HTML gövdesinin içinde doğrudan görünür ve satır içi bir resim gibi görünür.

## Neden gömülü görüntülü HTML e-posta gönderilir?
HTML içinde görüntüleri gömmek, daha zengin bültenler, ürün duyuruları veya destek talepleri tasarlamanızı sağlar. Alıcılar görseli hemen görür, ek indirmeye gerek kalmaz; bu da açılma oranlarını ve genel etkileşimi artırır.

## Ön Koşullar
 – resmi siteden indirin: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- Geçerli bir **SMTP sunucusu** (ör. Gmail, Outlook veya kendi posta geçidiniz).
- Gömmek istediğiniz bir görüntü dosyası (JPEG, PNG, GIF vb.).

utlandırarak ve ≤100 KB'ye sıkıştırarak. Bu, yükleme süresini azaltır ve posta kutusu boyut sınırlamalarına takılmayı önler.

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

## Eklenen Görüntüyü HTML İçinde Gömme
Görüntüyü e-posta gövdesinde göstermek için, ekin akışını saran bir `LinkedResource` oluşturun. Benzersiz bir Content‑ID (ör. `image1`) atayın ve HTML içinde `cid:` URI şemasını kullanarak referans verin.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Neden `LinkedResource` kullanılır?** Bu, posta istemcisine görüntünün mesaj gövdesinin bir parçası olduğunu, ayrı bir indirme olmadığını söyler; bu, **gömülü görüntülü HTML e-posta gönderme** senaryoları için esastır.

## E-postayı Gönderme
Son olarak, `SmtpClient`'ı sunucu detaylarınızla yapılandırın ve mesajı gönderin. SMTP kimlik bilgilerinin gönderici adresi adına gönderim izni olduğundan emin olun.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

Alıcı e-postayı açtığında, HTML gövdesi görüntüyü satır içi olarak render eder ve kesintisiz bir görsel deneyim sunar.

## Görüntü ekli e-posta – adım adım kılavuz
Aşağıda, az önce gördüğünüz kodu yansıtan kısantülü e-posta ekleme** sırasında kritik bir adımı kaçırmamanızı sağlar:

1. **Görüntüyü Hazırlayın** – toplam e-posta boyutunu düşük tutmak için yeniden boyutlandırın/sıkıştırın (`reduce email size`).
2. **`MailMessage` Oluşturun** – From, To, Subject ayarlayın ve gerektiğinde düz metin yedek ekleyin.
3. **Görüntüyü `Attachment` olarak ekleyin** – bu, dosyayı MIME konteynerine kaydeder.
4. **Ek'i `LinkedResource` içinde sarın** – benzersiz bir Content‑ID atayın.
5. **HTML gövdesini oluşturun** – Content‑ID'yi `cid:` ile referans verin (ör. `<img src='cid:image1'>`).
6. **`LinkedResource`'ı mesaja ekleyin** – görüntüyü satır içi yapar.
7. **`SmtpClient`'ı yapılandırın** – TLS/STARTTLS (`smtp email java`) ve uygun kimlik doğrulama kullanın.
8. **Mesajı gönderin** – e-postanın görüntüyü doğru şekilde göstererek ulaştığını doğrulayın.

## Yaygın Sorunlar ve Çözümleme
| Sorun | Neden | Çözüm |
|-------|-------|----------|
| Görüntü gösterilmiyor | Yanlış Content‑ID veya eksik `LinkedResource` | `linkedImage.setContentId("image1")` ifadesinin HTML'deki `src='cid:image1'` ile eşleştiğini doğrulayın. |
| Büyük e-posta boyutu | Optimizasyon yapılmamış görüntü (yüksek çözünürlük) | Eklemeye eklemeden önce görüntüyü yeniden boyutlandırın/sıkıştırın; ≤100 KB hedefleyin. |
| E-posta spam olarak işaretlendi | Uygun MIME başlıkları eksik | `SmtpClient`'ın TLS/STARTTLS kullandığından emin olun ve net bir `From` adresi ayarlayın. |
| Satır içi görüntü ek olarak görünüyor | İstemci CID'yi desteklemiyor | `<img>` etiketine bir yedek URL ekleyin (`src='cid:image1' alt='Image'`). |

## Sıkça Sorulan Sorular

**S: Tek bir e-postada birden fazla görüntüyü nasıl gömebilirim?**  
C: Her görüntü için ek ve `Linkedayın, benzersiz bir Content‑ID (ör. `image2`, `image3`) atayın ve HTML içinde referans verin.

**S: Düz metin e-postalarına görüntü gömebilir miyim?**  
C: Düz metin formatı gömülü görüntüleri desteklemez. Sadece al E-posta gömme için hangi görüntü formatları güvenlidir?**  
C: JPEG, PNG ve GIF yaygın olarak desteklenir. Fotoğraflar için JPEG, şeffaflık içeren grafikler için PNG kullanın.

**S: E-postada görünt var mı?**  
C: Evet—`<img>` etiketine genişlik/yükseklik öznitelikleri ekleyin, ör. `<img src='cid:image1' width='400' height='300'>`.

**S: Gömülü görüntüler için boyut sınırlamaları var mı?**  
C: Katı bir SMTP sınırı olmasa da, çoğu posta sağlayıcısı toplam e-posta boyutunun 5 MB altında tutulmasını önerir. Görüntü boyutunu optimize etmek bu sınır içinde kalmanıza yardımcıose.Email for Java kullanarak **e-postaya** gibi en iyi uygulamaları biliyorsunuz. Bu teknik, alıcıları etkileyen ve tüm posta istemcilerinde profesyonel görünen görsel açıdan çekici mesajlar oluşturmanızı sağlar.

---

**Son Güncelleme:** 2026-01-29  
**Test Edilen:** Aspose.Email for Java 24.11 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}