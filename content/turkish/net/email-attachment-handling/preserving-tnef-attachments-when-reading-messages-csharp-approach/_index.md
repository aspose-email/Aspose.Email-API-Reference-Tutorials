---
title: Aspose.Email for .NET'in Kurulumu
linktitle: Başlamak için Aspose.Email for .NET kitaplığını yüklemeniz gerekir. adresinden indirebilirsiniz.
second_title: Aspose.Release'ler
description: veya Visual Studio'da NuGet Paket Yöneticisini kullanın.
type: docs
weight: 15
url: /tr/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## Yeni Bir .NET Projesi Oluşturma

Visual Studio'yu açın ve yeni bir .NET projesi oluşturun.

## Aspose.Email for .NET kitaplığını NuGet Paket Yöneticisi'ni kullanarak yükleyin.

Artık kodlamaya başlamaya hazırsınız!

1. E-posta Mesajını Yükleme ve Ayrıştırma[E-posta Mesajı Yükleme](https://releases.aspose.com/email/net)E-postadaki yazı tiplerini değiştirebilmemiz için önce bir e-posta mesajı yüklememiz gerekiyor. Dosya, akış ve hatta posta sunucusu gibi çeşitli kaynaklardan bir e-posta yükleyebilirsiniz.

2.  E-posta mesajını yükle

3. Mesaj Gövdesini Ayrıştırma

## E-posta yüklendikten sonra HTML gövdesi de dahil olmak üzere farklı bölümlerine erişebilirsiniz. HTML gövdesini ayrıştırmak yazı tipi değişiklikleri yapmamıza olanak tanır.

 HTML gövdesini ayrıştır

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//E-postadaki Yazı Tiplerini Değiştirme
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Yazı Tipi Stillerini Anlamak

HTML e-postalarındaki yazı tipleri CSS stilleri kullanılarak tanımlanır. Yazı tiplerini değiştirmek için e-postanın HTML içeriğiyle ilişkili CSS stillerini değiştirmeniz gerekir.

```csharp
//Yazı Tiplerini Programlı Olarak Değiştirme
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Diyelim ki e-postanın HTML gövdesindeki bir paragrafın yazı tipini değiştirmek istiyorsunuz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
        var tnefAttachment = attachment;

        // Paragrafın yazı tipini değiştirme
        //MHT Formatına Dönüştürme
    }
}
```

## MHT Mesajı Oluşturma

E-postayı MHT formatına dönüştürmek için Aspose.Email'i kullanarak MHT formatlı bir e-posta mesajı oluşturmanız gerekir.

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

##  MHT biçimli e-posta mesajı oluşturun

Mesajı MHT Formatına Kaydetme

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //Son olarak MHT formatlı mesajı bir dosyaya kaydedin.
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // Mesajı MHT formatında kaydedin
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//Kaynak Kodunu Tamamlayın
					var tnefAttachment = attachment;

					//İşte her şeyi bir araya getiren kaynak kodun tamamı:
					//Çözüm
				}
			}
			//Bu kılavuzda Aspose.Email for .NET kullanarak MHT dönüşümü sırasında yazı tiplerinin nasıl değiştirileceğini araştırdık. Bu adımları izleyerek, istediğiniz yazı tipi stillerini korurken e-posta mesajlarını sorunsuz bir şekilde MHT formatına dönüştürebilirsiniz.
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## SSS

- Birden fazla e-postayı tek seferde MHT formatına dönüştürebilir miyim?
- Evet, bir dizi e-posta mesajı arasında geçiş yapabilir ve MHT formatına dönüştürmeden önce her mesaja aynı yazı tipi değişikliklerini uygulayabilirsiniz.
- Aspose.Email diğer e-posta formatlarını da destekliyor mu?

## Evet, Aspose.Email, EML, MSG, PST ve daha fazlası dahil olmak üzere çeşitli e-posta formatlarını destekler.

Yazı tipi değişikliklerini daha da özelleştirmek mümkün mü?

## Kesinlikle! Yazı tipi boyutu, rengi ve hizalaması gibi yazı tiplerini özelleştirmek için daha fazla CSS stili keşfedebilirsiniz.

### Aspose.Email'i ticari projeler için kullanabilir miyim?

Evet, Aspose.Email lisans koşullarına göre hem kişisel hem de ticari projeler için kullanılabilir.[ Bu kılavuzun genel bir genel bakış sağladığını ve aşağıdaki bilgilere başvurarak daha fazlasını keşfedebileceğinizi unutmayın.](https://releases.aspose.com/email/net)

### Aspose.Email API Referansı

ve farklı yazı tipi özelleştirme tekniklerini denemek. Mutlu kodlama!

###  C# Kılavuzu - E-posta Başlıklarını Çıkarma

 C# Kılavuzu - E-posta Başlıklarını Çıkarma

###  Aspose.Email .NET E-Posta İşleme API'si

 Aspose.Email for .NET'i kullanarak C#'ta e-posta başlıklarını nasıl çıkaracağınızı öğrenin. Etkili e-posta analizi için kaynak kodlu adım adım kılavuz.