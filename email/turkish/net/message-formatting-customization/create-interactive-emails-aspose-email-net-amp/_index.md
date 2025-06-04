---
"date": "2025-05-29"
"description": "Aspose.Email for .NET'in AMP teknolojisini kullanarak etkileşimli ve ilgi çekici e-postalar oluşturmayı öğrenin. Animasyonlar, dönen reklamlar ve formlar gibi dinamik içeriklerle e-posta pazarlama stratejinizi geliştirin."
"title": "Aspose.Email ile Etkileşimli E-postalar Oluşturun .NET AMP&#58; Kapsamlı Bir Kılavuz"
"url": "/tr/net/message-formatting-customization/create-interactive-emails-aspose-email-net-amp/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email ile Etkileşimli E-postalar Oluşturun .NET AMP: Kapsamlı Bir Kılavuz

## giriiş

Etkileşimli ve ilgi çekici e-postalar oluşturarak e-posta pazarlama stratejinizi geliştirmek mi istiyorsunuz? Geleneksel HTML e-postaları etkileşim açısından genellikle yetersiz kalır, ancak e-posta için Hızlandırılmış Mobil Sayfalar (AMP) ilgi çekici bir çözüm sunar. Aspose.Email for .NET'i iş akışınıza entegre ederek, animasyonlar, resimler, dönen reklamlar ve formlar gibi dinamik içeriklerle hedef kitlenizi büyüleyen AMP e-postaları oluşturabilirsiniz.

Bu eğitimde, Aspose.Email for .NET kullanarak AMP e-postalarında çeşitli bileşenler oluşturma sürecinde size rehberlik edeceğiz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, ilgi çekici e-posta deneyimleri oluşturma konusunda değerli içgörüler bulacaksınız.

**Ne Öğreneceksiniz:**
- Temel AMP e-posta yapıları nasıl oluşturulur
- Animasyonlar ve resimler gibi etkileşimli öğeler ekleme
- Dönme dolapları, uygun metin, akordeonlar, formlar ve zaman bileşenlerini uygulama
- Performans için e-postanızı optimize etme

Başlamaya hazır mısınız? Dinamik e-postalar oluşturma yolculuğumuza başlamadan önce ön koşulları ele alalım.

## Ön koşullar

Aspose.Email for .NET ile AMP e-postaları oluşturmaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Aspose.Email for .NET Kütüphanesi:** Çeşitli paket yöneticileri aracılığıyla yüklenebilen bu kütüphaneye ihtiyacınız olacak.
- **Geliştirme Ortamı:** Visual Studio gibi uygun bir IDE önerilir.
- **C# ve E-posta Protokollerinin Temel Bilgileri:** C# dilinde programlamaya aşinalık ve e-posta formatlarını anlamak faydalı olacaktır.

## Aspose.Email'i .NET için Kurma

Aspose.Email for .NET'i kullanmaya başlamak için kütüphaneyi yüklemeniz gerekir. Bunu şu yöntemlerden birini kullanarak yapabilirsiniz:

**.NET Komut Satırı Arayüzü**
```bash
dotnet add package Aspose.Email
```

**Paket Yöneticisi Konsolu**
```powershell
Install-Package Aspose.Email
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü**
"Aspose.Email"i arayın ve en son sürümü doğrudan IDE'nizden yükleyin.

### Lisans Edinimi

Aspose.Email'i denemek için bir talepte bulunabilirsiniz [ücretsiz deneme](https://releases.aspose.com/email/net/) veya geçici bir lisans edinin. Eğer faydalı bulursanız, tüm özelliklerin kilidini açmak için tam bir lisans satın almayı düşünün.

**Temel Başlatma**
Kurulum tamamlandıktan sonra projenizde kütüphaneyi başlatın:
```csharp
using Aspose.Email;

// Aspose.Email'i başlatmak için temel kurulum kodu
```

## Uygulama Kılavuzu

### Temel Yapı ile AMP E-postası Oluşturun

#### Genel bakış
Herhangi bir AMP e-postasının temeli temel bir yapı oluşturmaktır. Bu bölüm, ilk HTML gövdesinin nasıl kurulacağını gösterir.

**1. AmpMessage'ı başlatın**
Bir örnek oluşturarak başlayın `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msg = new AmpMessage();
```

**2. HTML Gövdesini Ayarlayın**
Basit bir HTML içeriği atayın `HtmlBody`.
```csharp
msg.HtmlBody = "<html><body> Hello AMP </body></html>";
msg.Save(dataDir + "BasicAmpEmail.eml");
```

#### Anahtar Yapılandırması
Dosyaları başarılı bir şekilde kaydetmek için dizin yolunuzun doğru şekilde ayarlandığından emin olun.

### AMP Animasyon Bileşeni Ekle

#### Genel bakış
Daha fazla etkileşim için e-postanızı bir animasyon bileşeniyle geliştirin.

**1. AmpMessage'ı Ayarlayın**
Başlat `AmpMessage` ve temel HTML içeriğini tanımlayın.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAnim = new AmpMessage();
msgWithAnim.HtmlBody = "<html><body> Hello AMP with Animation </body></html>";
```

**2. AmpAnim'i Oluşturun ve Ekleyin**
Yapılandırın `AmpAnim` bileşen.
```csharp
// AmpAnim bileşenini ekleyin
AmpAnim anim = new AmpAnim(800, 400);
anim.Src = "https://placekitten.com/800/400";
anim.Alt = "Test alt";
anim.Attribution = "The Go gopher was designed by Reneee French";
anim.Attributes.Layout = LayoutType.Responsive;
anim.Fallback = "offline";

msgWithAnim.AddAmpComponent(anim);
msgWithAnim.Save(dataDir + "AmpEmailWithAnim.eml");
```

#### Sorun giderme
- Resim URL'sinin erişilebilir olduğundan ve duyarlı özniteliklerin doğru şekilde ayarlandığından emin olun.

### AMP Görüntü Bileşeni Ekle

#### Genel bakış
E-postalarınızı görsel olarak çekici hale getirmek için görseller kullanın.

**1. AmpMessage'ı başlatın**
Yeni bir tane kurun `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithImage = new AmpMessage();
msgWithImage.HtmlBody = "<html><body> Hello AMP with Image </body></html>";
```

**2. AmpImage'ı ekleyin**
Yapılandırın ve ekleyin `AmpImage`.
```csharp
// AmpImage bileşenini ekleyin
AmpImage img = new AmpImage(800, 400);
img.Src = "https://placekitten.com/800/400";
img.Alt = "Test alt";
img.Attributes.Layout = LayoutType.Responsive;

msgWithImage.AddAmpComponent(img);
msgWithImage.Save(dataDir + "AmpEmailWithImage.eml");
```

### AMP Carousel Bileşeni Ekle

#### Genel bakış
Tek bir e-postada birden fazla görsel görüntülemek için bir dönen resim oluşturun.

**1. AmpMessage'ı Ayarlayın**
Başlat `AmpMessage` temel HTML içeriğiyle.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithCarousel = new AmpMessage();
msgWithCarousel.HtmlBody = "<html><body> Hello AMP with Carousel </body></html>";
```

**2. AmpCarousel'i Yapılandırın ve Ekleyin**
Resimleri karusele ekleyin.
```csharp
// AmpCarousel bileşenini ekleyin
AmpCarousel car = new AmpCarousel(800, 400);

AmpImage carouselImg1 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_caleb_woods.jpg", Alt = "Test 2 alt", Nitelikler = { Düzen = DüzenTipi.Sabit } };
car.Images.Add(carouselImg1);

AmpImage carouselImg2 = new AmpImage(800, 400) { Src = "https://placekitten.com/800/400", Alt = "Alt testi", Nitelikler = { Düzen = DüzenTipi.Duyarlı } };
car.Images.Add(carouselImg2);

AmpImage carouselImg3 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_craig_mclaclan.jpg", Alt = "Test 3 alt", Nitelikler = { Düzen = DüzenTipi.Doldur } };
car.Images.Add(carouselImg3);

msgWithCarousel.AddAmpComponent(car);
msgWithCarousel.Save(dataDir + "AmpEmailWithCarousel.eml");
```

### AMP FitText Bileşenini Ekle

#### Genel bakış
Metin boyutunu dinamik olarak ayarlamak için metin uydurma bileşenini kullanın.

**1. AmpMessage'ı başlatın**
Yeni bir başlangıç yapın `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithFitText = new AmpMessage();
msgWithFitText.HtmlBody = "<html><body> Hello AMP with Fit Text </body></html>";
```

**2. AmpFitText'i ekleyin**
Yapılandırın ve ekleyin `AmpFitText` bileşen.
```csharp
// AmpFitText bileşenini ekleyin
AmpFitText fitText = new AmpFitText(800, 400);
fitText.Text = "This is a dynamic text that fits the container.";
fitText.Attributes.Layout = LayoutType.Responsive;

msgWithFitText.AddAmpComponent(fitText);
msgWithFitText.Save(dataDir + "AmpEmailWithFitText.eml");
```

### AMP Akordeon Bileşeni Ekle

#### Genel bakış
Kullanıcıların içerik bölümlerini genişletip daraltmasına olanak sağlamak için bir akordeon ekleyin.

**1. AmpMessage'ı başlatın**
Yeni bir tane kurun `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAccordion = new AmpMessage();
msgWithAccordion.HtmlBody = "<html><body> Hello AMP with Accordion </body></html>";
```

**2. AmpAccordion'u ekleyin**
Yapılandırın ve ekleyin `AmpAccordion` bileşen.
```csharp
// AmpAccordion bileşenini ekleyin
AmpAccordion accordion = new AmpAccordion();
accordion.AddSection("Introduction", "This is the introduction section.");
accordion.AddSection("Details", "Here are more details.");
accordion.AddSection("Conclusion", "This is the conclusion.");

msgWithAccordion.AddAmpComponent(accordion);
msgWithAccordion.Save(dataDir + "AmpEmailWithAccordion.eml");
```

### AMP Form Bileşeni Ekle

#### Genel bakış
E-postanızı, kullanıcı yanıtlarını doğrudan e-posta içerisinde toplayacak bir formla geliştirin.

**1. AmpMessage'ı başlatın**
Yeni bir tane oluştur `AmpMessage` misal.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithForm = new AmpMessage();
msgWithForm.HtmlBody = "<html><body> Hello AMP with Form </body></html>";
```

**2. AmpForm'u ekleyin**
Yapılandırın ve ekleyin `AmpForm` bileşen.
```csharp
// AmpForm bileşenini ekle
AmpForm form = new AmpForm();
form.AddInput("name", "text", "Your Name");
form.AddInput("email", "email", "Your Email");
form.SetAction("https://your-server.com/submit-form"); // Form gönderimi için uç nokta URL'sini ayarlayın

msgWithForm.AddAmpComponent(form);
msgWithForm.Save(dataDir + "AmpEmailWithForm.eml");
```

### AMP Zamanlayıcı Bileşeni Ekle

#### Genel bakış
E-postanızda geri sayımları veya geçen süreyi görüntülemek için bir zamanlayıcı ekleyin.

**1. AmpMessage'ı başlatın**
Yeni bir tane kurun `AmpMessage` misal.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithTimer = new AmpMessage();
msgWithTimer.HtmlBody = "<html><body> Hello AMP with Timer </body></html>";
```

**2. AmpTimer'ı ekleyin**
Yapılandırın ve ekleyin `AmpTimer` bileşen.
```csharp
// AmpTimer bileşenini ekle
AmpTimer timer = new AmpTimer();
timer.SetDuration(3600); // Süreyi saniye cinsinden ayarlayın (örneğin, 1 saat)

msgWithTimer.AddAmpComponent(timer);
msgWithTimer.Save(dataDir + "AmpEmailWithTimer.eml");
```

### Çözüm

Bu kılavuzu izleyerek, Aspose.Email for .NET kullanarak etkileşimli ve ilgi çekici AMP e-postaları oluşturabilirsiniz. Bu dinamik bileşenler, daha etkileşimli bir kullanıcı deneyimi sağlayarak e-posta pazarlama stratejinizi geliştirecektir.

**Sonraki Adımlar:**
- Kampanyalarınız için en uygun olanı bulmak amacıyla farklı AMP bileşenlerini deneyin.
- Uyumluluğu sağlamak için e-postalarınızı farklı cihazlarda ve e-posta istemcilerinde test edin.
- Etkileşimli e-postalarınızın etkisini ölçmek için etkileşim ölçümlerini izleyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}