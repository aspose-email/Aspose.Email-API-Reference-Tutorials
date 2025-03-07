---
title: Görseller için Alternatif Metin Ayarlama - C# Kılavuzu
linktitle: Görseller için Alternatif Metin Ayarlama - C# Kılavuzu
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: Aspose.Email for .NET kullanarak e-postalardaki görseller için alternatif metin ayarlamayı öğrenin. Net alternatif metinle erişilebilirliği sağlayın. Belgeler ve kod dahildir.
weight: 15
url: /tr/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görseller için Alternatif Metin Ayarlama - C# Kılavuzu


Bu kılavuz, Aspose.Email for .NET kullanarak e-postalardaki görseller için alternatif metin ayarlama sürecinde size yol gösterecektir. "Alternatif metin" olarak da bilinen alternatif metin, görselin görüntülenememesi durumunda görselin metinsel açıklamasını sağlamak için kullanılır. Aspose.Email for .NET, çeşitli formatlardaki e-postalar ve eklerle çalışmanıza olanak tanıyan güçlü bir kütüphanedir. Bu kılavuzda C# kullanarak e-posta iletilerindeki görseller için alternatif metin ayarlamaya odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Visual Studio veya herhangi bir uyumlu C# geliştirme ortamı yüklü.
2. Aspose.Email for .NET kütüphanesi. NuGet Paket Yöneticisini Visual Studio'da kullanabilirsiniz.

## Adım 1: Yeni Bir Proje Oluşturun

1. Visual Studio'yu başlatın ve yeni bir C# konsol uygulaması projesi oluşturun.

## Adım 2: Aspose.Email'i NuGet aracılığıyla yükleyin

1. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet"i seçin.
2. "Aspose.Email"i arayın ve paketin en son sürümünü yükleyin.

## 3. Adım: Kullanarak İfadeleri Ekleme

```csharp

using Aspose.Email.Mime;
```

## Adım 4: E-posta Mesajını Yükleyin ve Değiştirin

1.  E-posta mesajını kullanarak yükleyin.`MailMessage` sınıf:

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

## Adım 5: Görsellere Alternatif Metin için Alternatif Görünüm Ekleme

Mesaja AlternateView olarak Resme Alternatif Metin için htmlview ekleyin. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Adım 6: E-postayı Kaydedin ve Gönderin

1. Değiştirilen mesajı bir dosyaya kaydedin veya istediğiniz yöntemi kullanarak gönderin:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Çözüm

Bu kılavuzda Aspose.Email for .NET kullanarak e-posta mesajlarındaki görseller için alternatif metni nasıl ayarlayacağınızı öğrendiniz. Yukarıda özetlenen adımları izleyerek, e-posta içeriğinizin, resimler görüntülenemediğinde bile erişilebilir ve bilgilendirici kalmasını sağlayabilirsiniz.

## SSS

## Aspose.Email kütüphanesini nasıl indirebilirim?

Aspose.Email kütüphanesini Aspose Sürümlerinden indirebilir veya Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla kurabilirsiniz.

### Resimleri bir e-postaya bağlantılı kaynaklar olarak nasıl eklerim?

Resimleri bir e-postaya bağlantılı kaynaklar olarak eklemek için`LinkedResource` sınıf. Bağlantılı kaynağa bir içerik kimliği atayın ve ardından HTML gövdesinde bu içerik kimliğine başvuruda bulunun.`cid:` şeması. Ayrıntılı bilgi için bkz.[LinkedResource belgeleri](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Aspose.Email for .NET hakkında daha fazla belgeyi nerede bulabilirim?

 Aspose.Email for .NET ile çalışmaya ilişkin daha ayrıntılı belgeleri, eğitimleri ve örnekleri şu adreste bulabilirsiniz:[API Referansı](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
