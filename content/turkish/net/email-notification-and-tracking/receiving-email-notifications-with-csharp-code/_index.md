---
title: C# Koduyla E-posta Bildirimleri Alma
linktitle: C# Koduyla E-posta Bildirimleri Alma
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: Aspose.Email for .NET'i kullanarak C#'ta e-posta bildirimleri almayı öğrenin. Verimli kod örneği sağlandı.
type: docs
weight: 10
url: /tr/net/email-notification-and-tracking/receiving-email-notifications-with-csharp-code/
---

Bu kılavuz, C# kodunu ve Aspose.Email for .NET kitaplığını kullanarak e-posta bildirimlerinin nasıl alınacağına ilişkin kapsamlı, adım adım bir eğitim sağlar. Aspose.Email, .NET uygulamalarında e-posta ile ilgili çeşitli işlemleri kolaylaştırmak için tasarlanmış sağlam bir kütüphanedir. Bu eğitimde e-posta bildirimleri alma sürecine odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- C# destekli bir geliştirme ortamı (örneğin, Visual Studio).
-  Aspose.Email for .NET kitaplığı. Şuradan indirebilirsiniz[bu bağlantı](https://releases.aspose.com/email/net).
- C# programlama ve temel e-posta kavramlarına ilişkin temel bilgi.

## Adım 1: Proje Kurulumu

1. Geliştirme ortamınızda yeni bir C# projesi oluşturun.
2. Aspose.Email.dll kütüphanesine bir referans ekleyin. Bunu, DLL'yi projenizin bin dizinine kopyalayarak veya Aspose.Email paketini yüklemek için NuGet Paket Yöneticisi'ni kullanarak yapabilirsiniz.

## Adım 2: Kodu Yazma

Bu adımda bir e-posta sunucusuna bağlanmak ve e-posta bildirimlerini almak için gerekli C# kodunu yazacağız.

```csharp
using System;
using Aspose.Email.Client;
using Aspose.Email.Imap;

class Program
{
    static void Main(string[] args)
    {
        // E-posta sunucusu ayarlarını yapılandırma
        string host = "your-email-server.com";
        int port = 993; // IMAP bağlantı noktası
        string username = "your-username";
        string password = "your-password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // E-posta sunucusuna bağlanın ve gelen kutusu klasörünü seçin
            client.Connect();
            client.SelectFolder(ImapFolderInfo.InBox);

            // Arama kriterlerini tanımlayın
            ImapQueryBuilder builder = new ImapQueryBuilder();
            builder.Subject.Contains("notification"); // Arama kriterlerini özelleştirin

            // E-posta bildirimlerini arayın
            ImapMessageInfoCollection messages = client.ListMessages(builder.GetQuery());
            
            foreach (ImapMessageInfo messageInfo in messages)
            {
                Console.WriteLine("Subject: " + messageInfo.Subject);
                Console.WriteLine("Date: " + messageInfo.Date);
                // Diğer e-posta özelliklerine buradan erişebilirsiniz
            }

            // E-posta sunucusuyla bağlantıyı kesin
            client.Disconnect();
        }
    }
}
```

Yer tutucu değerlerini değiştirmeyi unutmayın (`your-email-server.com`, `your-username`, `your-password`) gerçek e-posta sunucusu ayrıntılarınızla birlikte.

## 3. Adım: Arama Kriterlerini Özelleştirme

Sağlanan kod, "bildirim" terimini içeren konulara sahip e-posta bildirimlerini bulmak için temel bir arama kriteri kullanır. gibi özellikleri değiştirerek arama kriterlerini özelleştirebilirsiniz.`From`, `To` , Ve`Date`.

## Adım 4: Kodu Çalıştırma

C# projenizi oluşturun ve çalıştırın. Doğru yapılandırılırsa kod, e-posta sunucusuyla bağlantı kuracak, e-posta bildirimlerini arayacak ve bunların konularını ve tarihlerini konsolda görüntüleyecektir.

## Sıkça Sorulan Sorular

### E-posta eklerini nasıl yönetebilirim?

 E-posta eklerini yönetmek için`Attachments` mülkiyeti`ImapMessageInfo` nesne. Ekler arasında dolaşın ve bunları istediğiniz konuma kaydedin. Ayrıntılı rehberlik için bkz.[Aspose.Email API Referansı](https://reference.aspose.com/email/net/).

## Bildirimleri tarih aralığına göre filtreleyebilir miyim?

 Kesinlikle. Belirli bir tarih aralığını kullanarak bildirimleri filtreleyebilirsiniz. kullanarak arama kriterlerini ayarlayın.`Date` içindeki mülk`ImapQueryBuilder` . Bakın[dokümantasyon](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapquerybuilder/) kapsamlı örnekler için.

## Bildirimleri işlendikten sonra okundu olarak nasıl işaretleyebilirim?

Her mesajı işledikten sonra,`MarkMessageRead` yöntemi`ImapClient` Mesajları okundu olarak işaretlemek için Danışmak[dokümantasyon](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapclient/) detaylı bilgi için.

 Gelişmiş özellikler ve seçenekler için bkz.[Aspose.Email belgeleri](https://reference.aspose.com/email/net).

## Çözüm

Bu eğitimde, C# kodunu ve Aspose.Email for .NET kütüphanesini kullanarak e-posta bildirimleri alma sürecini inceledik. Aspose.Email, .NET uygulamalarında e-postayla ilgili işlemlerle çalışmayı kolaylaştıran güçlü bir araç olduğunu kanıtladı.
