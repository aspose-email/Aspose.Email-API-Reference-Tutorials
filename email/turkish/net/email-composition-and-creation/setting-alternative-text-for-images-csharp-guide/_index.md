---
"description": "Aspose.Email for .NET kullanarak e-postalardaki resimler için alternatif metin ayarlamayı öğrenin. Net alternatif metinle erişilebilirliği sağlayın. Belgeler ve kod dahildir."
"linktitle": "Resimler için Alternatif Metin Ayarlama - C# Rehberi"
"second_title": "Aspose.Email .NET E-posta İşleme API'si"
"title": "Resimler için Alternatif Metin Ayarlama - C# Rehberi"
"url": "/tr/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Resimler için Alternatif Metin Ayarlama - C# Rehberi


Bu kılavuz, Aspose.Email for .NET kullanarak e-postalardaki resimler için alternatif metin ayarlama sürecinde size yol gösterecektir. Alternatif metin, "alt text" olarak da bilinir, bir resim görüntülenemediğinde resmin metinsel bir açıklamasını sağlamak için kullanılır. Aspose.Email for .NET, çeşitli biçimlerdeki e-postalar ve eklerle çalışmanıza olanak tanıyan güçlü bir kütüphanedir. Bu kılavuzda, C# kullanarak e-posta mesajlarındaki resimler için alternatif metin ayarlamaya odaklanacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. Visual Studio veya uyumlu herhangi bir C# geliştirme ortamı yüklü.
2. Aspose.Email for .NET kütüphanesi. Visual Studio'da NuGet Paket Yöneticisi'ni kullanabilirsiniz.

## Adım 1: Yeni Bir Proje Oluşturun

1. Visual Studio'yu başlatın ve yeni bir C# konsol uygulama projesi oluşturun.

## Adım 2: Aspose.Email'i NuGet aracılığıyla yükleyin

1. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet" seçeneğini seçin.
2. "Aspose.Email"i arayın ve paketin en son sürümünü yükleyin.

## Adım 3: İfadeleri Kullanarak Ekleyin

```csharp

using Aspose.Email.Mime;
```

## Adım 4: E-posta Mesajını Yükleyin ve Değiştirin

1. E-posta mesajını kullanarak yükleyin `MailMessage` sınıf:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. E-posta mesajının HTML içeriğini yükleyin:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Adım 5: Resimlere Alternatif Metin için AlternativeView ekleyin

Mesaja Alternatif Metin için htmlview'i AlternateView olarak ekleyin. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Adım 6: E-postayı Kaydedin ve Gönderin

1. Değiştirilen mesajı bir dosyaya kaydedin veya istediğiniz yöntemi kullanarak gönderin:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Çözüm

Bu kılavuzda, Aspose.Email for .NET kullanarak e-posta mesajlarındaki resimler için alternatif metin ayarlamayı öğrendiniz. Yukarıda özetlenen adımları izleyerek, resimler görüntülenemediğinde bile e-posta içeriğinizin erişilebilir ve bilgilendirici kalmasını sağlayabilirsiniz.

## SSS

## Aspose.Email kütüphanesini nasıl indirebilirim?

Aspose.Email kütüphanesini Aspose Sürümlerinden indirebilir veya Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilirsiniz.

### Bir e-postaya bağlantılı kaynak olarak görselleri nasıl eklerim?

Bir e-postada bağlantılı kaynaklar olarak görseller eklemek için şunu kullanabilirsiniz: `LinkedResource` sınıf. Bağlantılı kaynağa bir içerik kimliği atayın ve ardından bu içerik kimliğine HTML gövdesinde şu şekilde başvurun: `cid:` şeması. Ayrıntılı bilgi için bkz. [BağlantılıKaynak belgeleri](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Aspose.Email for .NET hakkında daha fazla dokümanı nerede bulabilirim?

Aspose.Email for .NET ile çalışma hakkında daha ayrıntılı belgeler, eğitimler ve örnekler bulabilirsiniz. [API Referansı](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}