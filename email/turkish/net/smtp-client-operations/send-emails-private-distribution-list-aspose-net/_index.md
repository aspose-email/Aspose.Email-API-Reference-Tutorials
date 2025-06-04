---
"date": "2025-05-30"
"description": "Aspose.Email for .NET kullanarak e-postaları doğrudan özel dağıtım listelerine nasıl etkili bir şekilde göndereceğinizi öğrenin; yapılandırmayı ve güvenli ağ kimlik bilgilerinin kurulumunu ele alın."
"title": "Aspose.Email for .NET Kullanarak Özel Dağıtım Listelerine E-postalar Nasıl Gönderilir (SMTP İstemci İşlemleri)"
"url": "/tr/net/smtp-client-operations/send-emails-private-distribution-list-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for .NET Kullanarak Özel Bir Dağıtım Listesine E-postalar Nasıl Gönderilir

## giriiş

E-posta yönetiminizi, doğrudan özel dağıtım listelerine mesaj göndererek kolaylaştırmak mı istiyorsunuz? İster ekip iletişimlerini ister müşteri güncellemelerini yönetin, doğru araçları kullanmak verimliliği önemli ölçüde artırabilir. Bu eğitim, Aspose.Email for .NET kullanarak özel dağıtım listelerine e-posta göndermeyi tanıtmaktadır.

Bu kılavuzda iki temel işlevi inceleyeceğiz:
- **Özel Dağıtım Listesine E-posta Gönder**: Exchange sunucusuna nasıl bağlanacağınızı ve e-postaları sorunsuz bir şekilde nasıl göndereceğinizi öğrenin.
- **Ağ Kimlik Bilgileri Kurulumu**Exchange sunucusuyla kimlik doğrulaması için güvenli ağ kimlik bilgilerini ayarlayın.

**Ne Öğreneceksiniz:**
- Projenizde .NET için Aspose.Email nasıl yapılandırılır
- Özel bir dağıtım listesi kullanarak e-posta gönderme adımları
- Ağ kimlik bilgilerini güvenli bir şekilde ayarlama

Bu özelliklere dalmadan önce, tüm ön koşulların karşılandığından emin olalım.

## Ön koşullar

Bu eğitimi etkili bir şekilde takip etmek için şunlara ihtiyacınız olacak:
- **.NET için Aspose.Email**:Projenizin Aspose.Email sürüm 20.4 veya üzerini içerdiğinden emin olun.
- **Geliştirme Ortamı**: .NET uygulamalarını destekleyen Visual Studio benzeri bir geliştirme ortamı.
- **Exchange Sunucu Erişimi**: Dağıtım listelerini doğrulayabileceğiniz ve yönetebileceğiniz bir Exchange sunucusuna erişim.

### Gerekli Bilgi

- C# programlamanın temel anlayışı
- E-posta protokolleri ve Exchange sunucusu kavramlarına aşinalık

## Aspose.Email'i .NET için Kurma

Aspose.Email'i kullanmaya başlamak için projenize yüklemeniz gerekir. Kullanılabilir birkaç yöntem vardır:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Email
```

**Paket Yöneticisini Kullanma:**
```powershell
Install-Package Aspose.Email
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü aracılığıyla:**
En son sürümü edinmek için "Aspose.Email" ifadesini arayın ve yükle'ye tıklayın.

### Lisans Edinimi

Ücretsiz denemeyle başlayabilir veya geçici bir lisans edinebilirsiniz. Uzun vadeli kullanım için tam lisans satın almanız önerilir:
- **Ücretsiz Deneme**: Buradan indirin [Aspose Ücretsiz Sürüm](https://releases.aspose.com/email/net/)
- **Geçici Lisans**: Başvurunuzu buradan yapabilirsiniz: [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- **Satın almak**: Ziyaret etmek [Aspose Satın Alma Sayfası](https://purchase.aspose.com/buy) Tam lisans almak için.

### Temel Başlatma

Aspose.Email kurulduktan sonra projenizi temel kurulumla başlatın:

```csharp
using Aspose.Email.Clients.Exchange;
using Aspose.Email.Clients.Exchange.WebService;

// Sunucu kimlik bilgilerini ve URI'yi tanımlayın
string mailboxUri = "https://ex2010/ews/exchange.asmx";
string username = "test.exchange";
string password = "pwd";
string domain = "ex2010.local";

NetworkCredential credentials = new NetworkCredential(username, password, domain);\IEWSClient client = EWSClient.GetEWSClient(mailboxUri, credentials);
```

## Uygulama Kılavuzu

### Özel Dağıtım Listesine E-posta Gönder

#### Genel bakış
Bu özellik, e-postaları doğrudan bir Exchange sunucusunda yönetilen özel bir dağıtım listesine göndermenize olanak tanır.

#### Adım Adım Uygulama

**1. Exchange Server'a bağlanın**

Öncelikle ağ kimlik bilgilerinizi kullanarak bir bağlantı kurun:

```csharp
NetworkCredential credentials = new NetworkCredential(username, password, domain);\IEWSClient client = EWSClient.GetEWSClient(mailboxUri, credentials);
```
- **Parametreler**: 
  - `mailboxUri`: Exchange sunucusunun URI'si.
  - `credentials`: Oturum açma bilgileriniz bir kapsül içinde yer alır `NetworkCredential` nesne.

**2. Liste Dağıtım Listeleri**

Mevcut tüm dağıtım listelerini getir:

```csharp
ExchangeDistributionList[] distributionLists = client.ListDistributionLists();
```
- **Yöntem Amaç**: Exchange sunucusundan dağıtım listesi nesnelerinin bir dizisini alır.

**3. E-posta Mesajı Oluşturun ve Gönderin**

Bir dağıtım listesi seçin ve e-posta mesajınızı hazırlayın:

```csharp
MailAddress distributionListAddress = distributionLists[0].ToMailAddress();
MailMessage message = new MailMessage("from@host.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}