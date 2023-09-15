---
title: C# Kodunu Kullanarak E-posta Okundu Bilgilerini İsteme
linktitle: C# Kodunu Kullanarak E-posta Okundu Bilgilerini İsteme
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: İletişim izlemeyi geliştiren Aspose.Email for .NET'i kullanarak e-posta okundu bilgilerini istemek için C# kodunu nasıl kullanacağınızı öğrenin.
type: docs
weight: 11
url: /tr/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

Günümüzün dijital çağında e-posta yoluyla iletişim, kişisel ve profesyonel hayatımızın ayrılmaz bir parçası haline geldi. Çoğu zaman önemli e-postalar gönderirken alıcının mesajımızı okuyup onayladığından emin olmak isteriz. E-posta okundu bilgilerinin devreye girdiği yer burasıdır. Bu adım adım eğitimde, Aspose.Email for .NET ile C# kullanarak e-posta okundu bilgisi isteme sürecinde size rehberlik edeceğiz.

## E-posta Okundu Bilgilerine Giriş

E-posta izleme veya iade alındı bilgileri olarak da bilinen e-posta okundu bilgileri, alıcı e-postanızı açıp okuduğunda bildirim almanızı sağlar. Mesaj tesliminin ve etkileşimin onaylanmasını sağladığı için özellikle iş iletişimlerinde değerli bir özelliktir.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Visual Studio yüklü.
- Aspose.Email for .NET kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## 1. Adım: MailMessage Örneği Oluşturma

 E-posta okundu bilgilerini uygulamanın ilk adımı, e-posta okundu bilgilerinin bir örneğini oluşturmaktır.`MailMessage` sınıf. Bu sınıf bir e-posta mesajını temsil eder ve e-postanın çeşitli özelliklerini ayarlamanıza olanak tanır.

```csharp
MailMessage message = new MailMessage();
```

## Adım 2: Mesaj Ayrıntılarını Belirleme

Şimdi gönderen, alıcı, HTML gövdesi ve teslimat bildirimi seçenekleri de dahil olmak üzere e-posta mesajının ayrıntılarını belirtelim.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## 3. Adım: SmtpClient Örneği Oluşturma

 E-postayı göndermek için bir örneğini oluşturmamız gerekir.`SmtpClient` Mesajın gönderilmesinden sorumlu olan sınıf.

```csharp
SmtpClient client = new SmtpClient();
```

## Adım 4: SMTP Ayarlarını Yapılandırma

Ana sunucuyu, kullanıcı adını, parolayı ve bağlantı noktası numarasını belirterek SMTP sunucu ayarlarınızı yapılandırın.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Adım 5: E-postayı Gönderme

 Son olarak şunu kullanın:`client.Send` e-posta mesajını gönderme yöntemi. Mesaj başarılı bir şekilde gönderilirse "Mesaj Gönderildi" bildirimi görüntülenecektir.

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

Bu beş basit adımla, C# ve Aspose.Email for .NET kullanarak e-posta gönderirken e-posta okundu bilgisi talep edebilirsiniz. Bu özellik, e-posta iletişimlerinize bir güvence katmanı ekleyerek önemli mesajlarınızın ne zaman okunduğunu bilmenizi sağlar.

## Kaynak Kodunu Tamamlayın
```csharp
// MailMessage sınıfının bir örneğini oluşturun
MailMessage message = new MailMessage();

// Kimden, Kime, HtmlBody, DeliveryNotificationOptions alanını belirtin
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// SmtpClient Sınıfının bir örneğini oluşturun
SmtpClient client = new SmtpClient();

// Posta ana makine sunucunuzu, Kullanıcı Adınızı, Parolanızı ve Bağlantı Noktası No'nuzu belirtin
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send bu mesajı gönderecek
	client.Send(message);
	// 'Mesaj Gönderildi' seçeneğini yalnızca mesaj başarıyla gönderildiyse görüntüle
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Çözüm

Bu eğitimde, Aspose.Email for .NET ile C# kullanarak e-posta okundu bilgilerinin nasıl talep edileceğini araştırdık. E-posta izleme, özellikle profesyonel ortamlarda mesajlarınızın hedeflenen alıcılara iletilmesini ve okunmasını sağlamak için güçlü bir araçtır. Burada özetlenen adımları izleyerek bu işlevi e-posta uygulamanıza kolayca uygulayabilirsiniz.

## Sıkça Sorulan Sorular (SSS)

1. ### E-posta okundu bilgilerinin amacı nedir?
   E-posta okundu bilgileri, bir e-postanın alıcı tarafından açıldığı ve okunduğuna dair onay sağlar. Genellikle önemli veya zamana duyarlı mesajları izlemek için kullanılırlar.

2. ### E-posta okundu bilgileri alıcı tarafından devre dışı bırakılabilir mi?
   Evet, e-posta istemcileri genellikle kullanıcıların okundu bilgilerinin gönderilmesini devre dışı bırakmasına olanak tanır. Bu nedenle bunları her zaman alacağınız garanti edilmez.

3. ### E-posta okundu bilgileri tüm e-posta istemcilerinde standart bir özellik midir?
   Hayır, e-posta okundu bilgileri evrensel olarak desteklenmez. Çalışıp çalışmamaları e-posta istemcisine ve alıcının ayarlarına bağlıdır.

4. ### Mobil cihazda bir e-postanın ne zaman açıldığını takip etmek mümkün müdür?
   E-posta izleme genellikle alıcının e-posta istemcisine ve ayarlarına bağlıdır, dolayısıyla çeşitli faktörlere bağlı olarak mobil cihazlarda çalışabilir veya çalışmayabilir.

5. ### E-posta okundu bilgilerini kullanırken gizlilik hususları var mı?
   Evet, e-posta izlemeyle ilgili gizlilik endişeleri vardır. Bazı alıcılar bunun istilacı olduğunu düşünebilir, bu nedenle bu özelliğin sorumlu bir şekilde kullanılması ve gizlilik tercihlerine saygı gösterilmesi önemlidir.