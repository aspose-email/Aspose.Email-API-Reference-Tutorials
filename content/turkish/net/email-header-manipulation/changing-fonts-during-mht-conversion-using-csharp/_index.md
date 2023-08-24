---
title: C# kullanarak MHT Dönüştürme Sırasında Yazı Tiplerini Değiştirme
linktitle: C# kullanarak MHT Dönüştürme Sırasında Yazı Tiplerini Değiştirme
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: Aspose.Email for .NET'i kullanarak MHT dönüşümü sırasında yazı tiplerini nasıl değiştireceğinizi öğrenin. Kaynak koduyla adım adım kılavuz. E-posta arşivleme ve belge yönetimi için mükemmeldir.
type: docs
weight: 11
url: /tr/net/email-header-manipulation/changing-fonts-during-mht-conversion-using-csharp/
---

Yazı tipi stillerini korurken bir e-posta mesajını MHT formatına dönüştürme ihtiyacıyla hiç karşılaştınız mı? Bu kılavuz, güçlü Aspose.Email for .NET kitaplığını kullanarak MHT dönüşümü sırasında yazı tiplerini değiştirme sürecinde size yol gösterecektir. İster e-posta arşivleme, belge yönetimi veya e-posta dönüştürmeyi içeren başka bir proje üzerinde çalışıyor olun, bu adım adım kılavuz, hedefinize sorunsuz bir şekilde ulaşmanıza yardımcı olacaktır.

## MHT Dönüşümüne Giriş ve .NET için Aspose.Email

### MHT nedir?

MHT (MIME HTML), bir web sayfasını tüm kaynaklarıyla birlikte tek bir belgeye kaydetmenize olanak tanıyan bir dosya biçimidir. Orijinal içeriğin yapısını ve görünümünü koruduğu için genellikle web sayfalarını ve e-posta mesajlarını arşivlemek için kullanılır.

### Aspose.Email for .NET Hakkında

Aspose.Email for .NET, e-posta formatlarıyla çalışmak için e-postaları yükleme, ayrıştırma ve dönüştürme gibi işlevler sağlayan güçlü bir kitaplıktır. E-postayla ilgili çeşitli görevleri verimli bir şekilde ele alması gereken geliştiriciler için ideal bir seçimdir.

## Projenizi Kurma

### Aspose.Email for .NET'in Kurulumu

 Başlamak için Aspose.Email for .NET kitaplığını yüklemeniz gerekir. adresinden indirebilirsiniz.[Aspose.Release'ler](https://releases.aspose.com/email/net) veya Visual Studio'da NuGet Paket Yöneticisini kullanın.

### Yeni Bir .NET Projesi Oluşturma

1. Visual Studio'yu açın ve yeni bir .NET projesi oluşturun.
2. Aspose.Email for .NET kitaplığını NuGet Paket Yöneticisi'ni kullanarak yükleyin.
3. Artık kodlamaya başlamaya hazırsınız!

## E-posta Mesajını Yükleme ve Ayrıştırma

### E-posta Mesajı Yükleme

E-postadaki yazı tiplerini değiştirebilmemiz için önce bir e-posta mesajı yüklememiz gerekiyor. Dosya, akış ve hatta posta sunucusu gibi çeşitli kaynaklardan bir e-posta yükleyebilirsiniz.

```csharp
// E-posta mesajını yükle
var message = MailMessage.Load("sample.eml");
```

### Mesaj Gövdesini Ayrıştırma

E-posta yüklendikten sonra HTML gövdesi de dahil olmak üzere farklı bölümlerine erişebilirsiniz. HTML gövdesini ayrıştırmak yazı tipi değişiklikleri yapmamıza olanak tanır.

```csharp
// HTML gövdesini ayrıştır
var htmlBody = message.HtmlBody;
```

## E-postadaki Yazı Tiplerini Değiştirme

### Yazı Tipi Stillerini Anlamak

HTML e-postalarındaki yazı tipleri CSS stilleri kullanılarak tanımlanır. Yazı tiplerini değiştirmek için e-postanın HTML içeriğiyle ilişkili CSS stillerini değiştirmeniz gerekir.

### Yazı Tiplerini Programlı Olarak Değiştirme

Diyelim ki e-postanın HTML gövdesindeki bir paragrafın yazı tipini değiştirmek istiyorsunuz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
// Paragrafın yazı tipini değiştirme
htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");
```

## MHT Formatına Dönüştürme

### MHT Mesajı Oluşturma

E-postayı MHT formatına dönüştürmek için Aspose.Email'i kullanarak MHT formatlı bir e-posta mesajı oluşturmanız gerekir.

```csharp
// MHT biçimli e-posta mesajı oluşturun
var mhtMessage = MhtMessage.FromMailMessage(message);
```

### Mesajı MHT Formatına Kaydetme

Son olarak MHT formatlı mesajı bir dosyaya kaydedin.

```csharp
// Mesajı MHT formatında kaydedin
mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
```

## Kaynak Kodunu Tamamlayın

İşte her şeyi bir araya getiren kaynak kodun tamamı:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;

class Program
{
    static void Main()
    {
        var message = MailMessage.Load("sample.eml");
        var htmlBody = message.HtmlBody;
        htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");

        var mhtMessage = MhtMessage.FromMailMessage(message);
        mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
    }
}
```

## Çözüm

Bu kılavuzda Aspose.Email for .NET kullanarak MHT dönüşümü sırasında yazı tiplerinin nasıl değiştirileceğini araştırdık. Bu adımları izleyerek, istediğiniz yazı tipi stillerini korurken e-posta mesajlarını sorunsuz bir şekilde MHT formatına dönüştürebilirsiniz.


## SSS


### Birden fazla e-postayı tek seferde MHT formatına dönüştürebilir miyim?

Evet, bir dizi e-posta mesajı arasında geçiş yapabilir ve MHT formatına dönüştürmeden önce her mesaja aynı yazı tipi değişikliklerini uygulayabilirsiniz.

### Aspose.Email diğer e-posta formatlarını da destekliyor mu?

Evet, Aspose.Email, EML, MSG, PST ve daha fazlası dahil olmak üzere çeşitli e-posta formatlarını destekler.

### Yazı tipi değişikliklerini daha da özelleştirmek mümkün mü?

Kesinlikle! Yazı tipi boyutu, rengi ve hizalaması gibi yazı tiplerini özelleştirmek için daha fazla CSS stili keşfedebilirsiniz.

### Aspose.Email'i ticari projeler için kullanabilir miyim?

Evet, Aspose.Email lisans koşullarına göre hem kişisel hem de ticari projeler için kullanılabilir.

 Bu kılavuzun genel bir genel bakış sağladığını ve aşağıdaki bilgilere başvurarak daha fazlasını keşfedebileceğinizi unutmayın.[Aspose.Email API Referansı](https://reference.aspose.com/email/net/)ve farklı yazı tipi özelleştirme tekniklerini denemek. Mutlu kodlama!