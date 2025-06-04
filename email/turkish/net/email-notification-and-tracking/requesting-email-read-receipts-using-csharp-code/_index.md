---
"description": "Aspose.Email for .NET kullanarak e-posta okundu bilgisi istemek için C# kodunun nasıl kullanılacağını öğrenin ve iletişim takibini geliştirin."
"linktitle": "C# Kodunu Kullanarak E-posta Okundu Bildirimi İsteme"
"second_title": "Aspose.Email .NET E-posta İşleme API'si"
"title": "C# Kodunu Kullanarak E-posta Okundu Bildirimi İsteme"
"url": "/tr/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# C# Kodunu Kullanarak E-posta Okundu Bildirimi İsteme


Günümüzün dijital çağında, e-posta yoluyla iletişim kişisel ve profesyonel hayatlarımızın ayrılmaz bir parçası haline geldi. Genellikle, önemli e-postalar gönderirken, alıcının mesajımızı okuduğundan ve onayladığından emin olmak isteriz. E-posta okundu bildirimleri tam da burada devreye girer. Bu adım adım eğitimde, .NET için Aspose.Email ile C# kullanarak e-posta okundu bildirimleri isteme sürecinde size rehberlik edeceğiz.

## E-posta Okundu Bildirimlerine Giriş

E-posta okundu bildirimleri, e-posta takibi veya iade bildirimleri olarak da bilinir, alıcı e-postanızı açıp okuduğunda bildirimler almanızı sağlar. Özellikle iş iletişimlerinde değerli bir özelliktir, çünkü mesaj teslimi ve etkileşimin onayını sağlar.

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde Visual Studio yüklü.
- Aspose.Email for .NET kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 1: Bir MailMessage Örneği Oluşturma

E-posta okundu bildirimlerini uygulamanın ilk adımı, bir örneğini oluşturmaktır. `MailMessage` sınıf. Bu sınıf bir e-posta mesajını temsil eder ve e-postanın çeşitli özelliklerini ayarlamanıza olanak tanır.

```csharp
MailMessage message = new MailMessage();
```

## Adım 2: Mesaj Ayrıntılarını Belirleme

Şimdi, gönderen, alıcı, HTML gövdesi ve teslimat bildirimi seçenekleri dahil olmak üzere e-posta mesajının ayrıntılarını belirtelim.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Adım 3: Bir SmtpClient Örneği Oluşturma

E-postayı göndermek için bir örnek oluşturmamız gerekiyor `SmtpClient` Mesajın gönderilmesinden sorumlu olan sınıf.

```csharp
SmtpClient client = new SmtpClient();
```

## Adım 4: SMTP Ayarlarını Yapılandırma

Ana bilgisayar sunucusunu, kullanıcı adını, parolayı ve bağlantı noktası numarasını belirterek SMTP sunucu ayarlarınızı yapılandırın.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Adım 5: E-postayı Gönderme

Son olarak, şunu kullanın: `client.Send` e-posta mesajını gönderme yöntemi. Mesaj başarıyla gönderilirse, "Mesaj Gönderildi" bildirimi görüntülenecektir.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

Bu beş basit adımla, C# ve Aspose.Email for .NET kullanarak e-posta gönderirken e-posta okundu bildirimleri isteyebilirsiniz. Bu özellik, e-posta iletişimlerinize bir güvence katmanı ekleyerek önemli mesajlarınızın ne zaman okunduğunu bilmenizi sağlar.

## Tam Kaynak Kodu
```csharp
// MailMessage sınıfının bir örneğini oluşturun
MailMessage message = new MailMessage();

// Kimden, Kime, HtmlBody, DeliveryNotificationOptions alanlarını belirtin
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// SmtpClient Sınıfının bir örneğini oluşturun
SmtpClient client = new SmtpClient();

// Posta sunucunuzu, Kullanıcı Adınızı, Parolanızı ve Port No'nuzu belirtin
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send bu mesajı gönderecek
	client.Send(message);
	// Yalnızca mesaj başarıyla gönderildiğinde 'Mesaj Gönderildi'yi görüntüle
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Çözüm

Bu eğitimde, Aspose.Email for .NET ile C# kullanarak e-posta okundu bildirimlerinin nasıl isteneceğini inceledik. E-posta izleme, özellikle profesyonel ortamlarda, mesajlarınızın iletilmesini ve amaçlanan alıcılar tarafından okunmasını sağlamak için güçlü bir araçtır. Burada özetlenen adımları izleyerek, bu işlevselliği e-posta uygulamanıza kolayca uygulayabilirsiniz.

## Sıkça Sorulan Sorular (SSS)

1. ### E-posta okundu bilgisinin amacı nedir?
   E-posta okundu bilgileri, bir e-postanın alıcı tarafından açılıp okunduğunun onayını sağlar. Genellikle önemli veya zamana duyarlı mesajları izlemek için kullanılır.

2. ### E-posta okundu bildirimleri alıcı tarafından devre dışı bırakılabilir mi?
   Evet, e-posta istemcileri kullanıcıların okundu bilgisi göndermeyi devre dışı bırakmasına sıklıkla izin verir. Bu nedenle, bunları her zaman alacağınız garanti edilmez.

3. ### E-posta okundu bildirimleri tüm e-posta istemcilerinin standart bir özelliği midir?
   Hayır, e-posta okundu bildirimleri evrensel olarak desteklenmez. Çalışıp çalışmamaları e-posta istemcisine ve alıcının ayarlarına bağlıdır.

4. ### Bir e-postanın mobil cihazda ne zaman açıldığını takip etmek mümkün müdür?
   E-posta takibi genellikle alıcının e-posta istemcisine ve ayarlarına dayanır; bu nedenle çeşitli faktörlere bağlı olarak mobil cihazlarda çalışabilir veya çalışmayabilir.

5. ### E-posta okundu bilgilerini kullanırken gizlilik hususlarına dikkat ediliyor mu?
   Evet, e-posta takibiyle ilgili gizlilik endişeleri vardır. Bazı alıcılar bunu müdahaleci olarak görebilir, bu nedenle bu özelliği sorumlu bir şekilde kullanmak ve gizlilik tercihlerine saygı göstermek önemlidir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}