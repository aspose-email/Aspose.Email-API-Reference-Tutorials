---
title: C# ile Teslimat Durumu Bildirimlerini Alma
linktitle: C# ile Teslimat Durumu Bildirimlerini Alma
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: C# ve Aspose.Email for .NET kullanarak e-posta Teslim Durumu Bildirimlerini nasıl alacağınızı öğrenin.
type: docs
weight: 18
url: /tr/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## giriiş

E-posta iletişiminde Teslim Durumu Bildirimleri (DSN'ler), gönderenleri e-postalarının teslim durumu hakkında bilgilendirmede çok önemli bir rol oynar. Aspose.Email for .NET, e-postalarla çalışmak için DSN'leri almak da dahil olmak üzere işlevler sağlayan güçlü bir kitaplıktır. Bu kılavuzda, C# ve Aspose.Email for .NET kütüphanesini kullanarak Teslimat Durumu Bildirimlerini alma sürecini anlatacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Visual Studio kuruldu.
2.  Aspose.Email for .NET kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/email/net).
3. C# programlamanın temel anlayışı.

## Adımlar

Aspose.Email for .NET'i kullanarak Teslimat Durumu Bildirimlerini almak için şu adımları izleyin:

### Adım 1: Yeni Bir Proje Oluşturun

Visual Studio'yu açın ve yeni bir C# konsol uygulama projesi oluşturun.

### Adım 2: Aspose.Email Referansını Ekleyin

İndirdiğiniz Aspose.Email DLL dosyasını projenizin dizinine kopyalayın. Ardından Solution Explorer'da projeye sağ tıklayın, "Ekle" > "Referans"ı seçin ve Aspose.Email DLL dosyasına göz atın. Referansı projenize eklemek için "Tamam"ı tıklayın.

### 3. Adım: DSN'leri Almak için Kod Yazma

 Aç`Program.cs` projenize dosya ekleyin ve gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 İçinde`Main` yöntemini kullanarak e-posta sunucusuna bağlanmak, DSN'leri almak ve bunları işlemek için gereken kodu yazın:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // IMAP sunucusu kimlik bilgilerinizi ve ana makinenizi ayarlayın
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Gelen Kutusu klasörünü seçin
            client.SelectFolder(ImapFolderInfo.InBox);

            // DSN'leri olan mesajları arayın
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Alınan DSN'leri işle
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // DSN ayrıntılarını işle
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Diğer DSN ayrıntılarını işleyin

                // Mesajı okundu olarak işaretleyin veya silin
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Yer değiştirmek`"your_imap_host"`, `"your_email"` , Ve`"your_password"` gerçek IMAP sunucusu ayrıntılarınızla.

### Adım 4: Uygulamayı Çalıştırın

Uygulamanızı oluşturun ve çalıştırın. E-posta sunucunuza bağlanacak, Gelen Kutusu klasöründen DSN'leri alacak, ayrıntılarını işleyecek ve isteğe bağlı olarak bunları silecek veya okundu olarak işaretleyecektir.

## SSS

### IMAP sunucusu ana bilgisayarını nasıl bulurum?

 IMAP sunucusu ana bilgisayarını e-posta servis sağlayıcınızın belgelerinden veya ayarlarından bulabilirsiniz. Genellikle şu formattadır:`imap.yourdomain.com`.

### Konu ve gönderen dışındaki DSN ayrıntılarını nasıl işleyebilirim?

 Çeşitli özelliklerine erişebilirsiniz.`MailMessage` Alıcı adresleri, teslimat durumu, zaman damgası ve daha fazlası gibi DSN ayrıntılarını almak için nesne. Bakın[Aspose.Email belgeleri](https://reference.aspose.com/email/net/) daha fazla bilgi için.

### DSN'leri silmek veya okundu olarak işaretlemek gerekli mi?

Hayır, gerekli değil. DSN'lerin silinmesi veya okundu olarak işaretlenmesi uygulamanızın gereksinimlerine bağlıdır. Sağlanan kod her iki seçeneği de gösterir, ancak bunu ihtiyaçlarınıza göre özelleştirebilirsiniz.

## Çözüm

C# ve Aspose.Email for .NET kullanarak Teslimat Durumu Bildirimlerini almak basit bir işlemdir. Aspose.Email kütüphanesi, IMAP sunucusuyla iletişimi basitleştirir ve e-posta mesajlarını işlemek için kullanımı kolay API'ler sağlar. Bu kılavuzla artık DSN alma işlevini C# uygulamalarınıza dahil edebilirsiniz.