---
"date": "2025-05-29"
"description": ".NET की AMP तकनीक के लिए Aspose.Email का उपयोग करके इंटरैक्टिव और आकर्षक ईमेल बनाने का तरीका जानें। एनिमेशन, कैरोसेल और फ़ॉर्म जैसी गतिशील सामग्री के साथ अपनी ईमेल मार्केटिंग रणनीति को बेहतर बनाएँ।"
"title": "Aspose.Email .NET AMP&#58; के साथ इंटरैक्टिव ईमेल बनाएं एक व्यापक गाइड"
"url": "/hi/net/message-formatting-customization/create-interactive-emails-aspose-email-net-amp/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email .NET AMP के साथ इंटरैक्टिव ईमेल बनाएं: एक व्यापक गाइड

## परिचय

क्या आप इंटरैक्टिव और आकर्षक ईमेल बनाकर अपनी ईमेल मार्केटिंग रणनीति को बेहतर बनाना चाहते हैं? पारंपरिक HTML ईमेल अक्सर इंटरैक्टिविटी में कम पड़ जाते हैं, लेकिन ईमेल के लिए एक्सेलेरेटेड मोबाइल पेज (AMP) एक आकर्षक समाधान प्रदान करते हैं। अपने वर्कफ़्लो में .NET के लिए Aspose.Email को एकीकृत करके, आप ऐसे AMP ईमेल बना सकते हैं जो आपके दर्शकों को एनिमेशन, इमेज, कैरोसेल और फ़ॉर्म जैसी गतिशील सामग्री से आकर्षित करते हैं।

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Email का उपयोग करके AMP ईमेल के भीतर विभिन्न घटकों के निर्माण की प्रक्रिया के बारे में मार्गदर्शन करेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, आपको आकर्षक ईमेल अनुभव तैयार करने में मूल्यवान जानकारी मिलेगी।

**आप क्या सीखेंगे:**
- बुनियादी AMP ईमेल संरचनाएँ कैसे बनाएँ
- एनिमेशन और छवियों जैसे इंटरैक्टिव तत्वों को जोड़ना
- कैरोसेल, फिट टेक्स्ट, अकॉर्डियन, फॉर्म और समय घटकों को लागू करना
- अपने ईमेल को प्रदर्शन के लिए अनुकूलित करना

क्या आप इसमें शामिल होने के लिए तैयार हैं? आइए गतिशील ईमेल बनाने की अपनी यात्रा शुरू करने से पहले पहले आवश्यक शर्तों को समझ लें।

## आवश्यक शर्तें

इससे पहले कि आप .NET के लिए Aspose.Email के साथ AMP ईमेल बनाना शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- **.NET लाइब्रेरी के लिए Aspose.Email:** आपको इस लाइब्रेरी की आवश्यकता होगी, जिसे विभिन्न पैकेज प्रबंधकों के माध्यम से स्थापित किया जा सकता है।
- **विकास पर्यावरण:** विज़ुअल स्टूडियो जैसे उपयुक्त IDE की अनुशंसा की जाती है।
- **C# और ईमेल प्रोटोकॉल का बुनियादी ज्ञान:** C# प्रोग्रामिंग से परिचित होना और ईमेल प्रारूपों को समझना लाभदायक होगा।

## .NET के लिए Aspose.Email सेट अप करना

.NET के लिए Aspose.Email का उपयोग शुरू करने के लिए, आपको लाइब्रेरी स्थापित करनी होगी। आप इनमें से किसी एक तरीके का उपयोग करके ऐसा कर सकते हैं:

**.NET सीएलआई**
```bash
dotnet add package Aspose.Email
```

**पैकेज प्रबंधक कंसोल**
```powershell
Install-Package Aspose.Email
```

**NuGet पैकेज मैनेजर UI**
"Aspose.Email" खोजें और अपने IDE से सीधे नवीनतम संस्करण स्थापित करें।

### लाइसेंस अधिग्रहण

Aspose.Email आज़माने के लिए, आप अनुरोध कर सकते हैं [मुफ्त परीक्षण](https://releases.aspose.com/email/net/) या एक अस्थायी लाइसेंस प्राप्त करें। यदि आपको यह उपयोगी लगता है, तो सभी सुविधाओं को अनलॉक करने के लिए पूर्ण लाइसेंस खरीदने पर विचार करें।

**मूल आरंभीकरण**
एक बार इंस्टॉल हो जाने पर, अपने प्रोजेक्ट में लाइब्रेरी को आरंभ करें:
```csharp
using Aspose.Email;

// Aspose.Email आरंभ करने के लिए मूल सेटअप कोड
```

## कार्यान्वयन मार्गदर्शिका

### बुनियादी संरचना के साथ AMP ईमेल बनाएं

#### अवलोकन
किसी भी AMP ईमेल की नींव एक बुनियादी संरचना बनाना है। यह अनुभाग दर्शाता है कि प्रारंभिक HTML बॉडी कैसे सेट अप करें।

**1. AmpMessage प्रारंभ करें**
इसका एक उदाहरण बनाकर शुरू करें `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msg = new AmpMessage();
```

**2. HTML बॉडी सेट करें**
एक सरल HTML सामग्री असाइन करें `HtmlBody`.
```csharp
msg.HtmlBody = "<html><body> Hello AMP </body></html>";
msg.Save(dataDir + "BasicAmpEmail.eml");
```

#### कुंजी कॉन्फ़िगरेशन
सुनिश्चित करें कि फ़ाइलों को सफलतापूर्वक सहेजने के लिए आपका निर्देशिका पथ सही ढंग से सेट किया गया है।

### AMP एनिम घटक जोड़ें

#### अवलोकन
अधिक सहभागिता के लिए अपने ईमेल को एनीमेशन घटक से बेहतर बनाएं।

**1. AmpMessage सेट अप करें**
आरंभ करें `AmpMessage` और बुनियादी HTML सामग्री को परिभाषित करें.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAnim = new AmpMessage();
msgWithAnim.HtmlBody = "<html><body> Hello AMP with Animation </body></html>";
```

**2. AmpAnim बनाएं और जोड़ें**
कॉन्फ़िगर करें `AmpAnim` अवयव।
```csharp
// AmpAnim घटक जोड़ें
AmpAnim anim = new AmpAnim(800, 400);
anim.Src = "https://placekitten.com/800/400";
anim.Alt = "Test alt";
anim.Attribution = "The Go gopher was designed by Reneee French";
anim.Attributes.Layout = LayoutType.Responsive;
anim.Fallback = "offline";

msgWithAnim.AddAmpComponent(anim);
msgWithAnim.Save(dataDir + "AmpEmailWithAnim.eml");
```

#### समस्या निवारण
- सुनिश्चित करें कि छवि URL पहुँच योग्य है और उत्तरदायी विशेषताएँ सही ढंग से सेट की गई हैं.

### AMP छवि घटक जोड़ें

#### अवलोकन
अपने ईमेल को दृश्यात्मक रूप से आकर्षक बनाने के लिए चित्र शामिल करें।

**1. AmpMessage प्रारंभ करें**
एक नया सेट अप करें `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithImage = new AmpMessage();
msgWithImage.HtmlBody = "<html><body> Hello AMP with Image </body></html>";
```

**2. एम्पइमेज जोड़ें**
कॉन्फ़िगर करें और जोड़ें `AmpImage`.
```csharp
// AmpImage घटक जोड़ें
AmpImage img = new AmpImage(800, 400);
img.Src = "https://placekitten.com/800/400";
img.Alt = "Test alt";
img.Attributes.Layout = LayoutType.Responsive;

msgWithImage.AddAmpComponent(img);
msgWithImage.Save(dataDir + "AmpEmailWithImage.eml");
```

### AMP कैरोसेल घटक जोड़ें

#### अवलोकन
एक ही ईमेल में अनेक छवियाँ प्रदर्शित करने के लिए कैरोसेल बनाएँ.

**1. AmpMessage सेट अप करें**
प्रारंभ `AmpMessage` मूल HTML सामग्री के साथ.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithCarousel = new AmpMessage();
msgWithCarousel.HtmlBody = "<html><body> Hello AMP with Carousel </body></html>";
```

**2. AmpCarousel को कॉन्फ़िगर करें और जोड़ें**
हिंडोला में छवियाँ जोड़ें.
```csharp
// AmpCarousel घटक जोड़ें
AmpCarousel car = new AmpCarousel(800, 400);

AmpImage carouselImg1 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_caleb_woods.jpg", Alt = "टेस्ट 2 alt", विशेषताएँ = { लेआउट = लेआउटटाइप.फिक्स्ड } };
car.Images.Add(carouselImg1);

AmpImage carouselImg2 = new AmpImage(800, 400) { Src = "https://placekitten.com/800/400", Alt = "टेस्ट alt", विशेषताएँ = { लेआउट = लेआउटटाइप.Responsive } };
car.Images.Add(carouselImg2);

AmpImage carouselImg3 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_craig_mclaclan.jpg", Alt = "टेस्ट 3 alt", विशेषताएँ = { लेआउट = लेआउटटाइप.भरण } };
car.Images.Add(carouselImg3);

msgWithCarousel.AddAmpComponent(car);
msgWithCarousel.Save(dataDir + "AmpEmailWithCarousel.eml");
```

### AMP FitText घटक जोड़ें

#### अवलोकन
टेक्स्ट आकार को गतिशील रूप से समायोजित करने के लिए फिट टेक्स्ट घटक का उपयोग करें।

**1. AmpMessage प्रारंभ करें**
एक नई शुरुआत करें `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithFitText = new AmpMessage();
msgWithFitText.HtmlBody = "<html><body> Hello AMP with Fit Text </body></html>";
```

**2. AmpFitText जोड़ें**
कॉन्फ़िगर करें और जोड़ें `AmpFitText` अवयव।
```csharp
// AmpFitText घटक जोड़ें
AmpFitText fitText = new AmpFitText(800, 400);
fitText.Text = "This is a dynamic text that fits the container.";
fitText.Attributes.Layout = LayoutType.Responsive;

msgWithFitText.AddAmpComponent(fitText);
msgWithFitText.Save(dataDir + "AmpEmailWithFitText.eml");
```

### AMP अकॉर्डियन घटक जोड़ें

#### अवलोकन
उपयोगकर्ताओं को सामग्री अनुभागों को विस्तारित और संक्षिप्त करने की अनुमति देने के लिए एक अकॉर्डियन शामिल करें।

**1. AmpMessage प्रारंभ करें**
एक नया सेट अप करें `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAccordion = new AmpMessage();
msgWithAccordion.HtmlBody = "<html><body> Hello AMP with Accordion </body></html>";
```

**2. एम्प अकॉर्डियन जोड़ें**
कॉन्फ़िगर करें और जोड़ें `AmpAccordion` अवयव।
```csharp
// AmpAccordion घटक जोड़ें
AmpAccordion accordion = new AmpAccordion();
accordion.AddSection("Introduction", "This is the introduction section.");
accordion.AddSection("Details", "Here are more details.");
accordion.AddSection("Conclusion", "This is the conclusion.");

msgWithAccordion.AddAmpComponent(accordion);
msgWithAccordion.Save(dataDir + "AmpEmailWithAccordion.eml");
```

### AMP फ़ॉर्म घटक जोड़ें

#### अवलोकन
अपने ईमेल को एक फॉर्म के साथ बेहतर बनाएं ताकि उपयोगकर्ता की प्रतिक्रियाएं सीधे ईमेल में ही एकत्रित की जा सकें।

**1. AmpMessage प्रारंभ करें**
एक नया बनाएँ `AmpMessage` उदाहरण।
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithForm = new AmpMessage();
msgWithForm.HtmlBody = "<html><body> Hello AMP with Form </body></html>";
```

**2. एम्पफॉर्म जोड़ें**
कॉन्फ़िगर करें और जोड़ें `AmpForm` अवयव।
```csharp
// AmpForm घटक जोड़ें
AmpForm form = new AmpForm();
form.AddInput("name", "text", "Your Name");
form.AddInput("email", "email", "Your Email");
form.SetAction("https://your-server.com/submit-form"); // फ़ॉर्म सबमिशन के लिए एंडपॉइंट URL सेट करें

msgWithForm.AddAmpComponent(form);
msgWithForm.Save(dataDir + "AmpEmailWithForm.eml");
```

### AMP टाइमर घटक जोड़ें

#### अवलोकन
अपने ईमेल में उल्टी गिनती या बीता हुआ समय प्रदर्शित करने के लिए टाइमर शामिल करें।

**1. AmpMessage प्रारंभ करें**
एक नया सेट अप करें `AmpMessage` उदाहरण।
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithTimer = new AmpMessage();
msgWithTimer.HtmlBody = "<html><body> Hello AMP with Timer </body></html>";
```

**2. एम्पटाइमर जोड़ें**
कॉन्फ़िगर करें और जोड़ें `AmpTimer` अवयव।
```csharp
// AmpTimer घटक जोड़ें
AmpTimer timer = new AmpTimer();
timer.SetDuration(3600); // सेकंड में अवधि निर्धारित करें (उदाहरणार्थ, 1 घंटा)

msgWithTimer.AddAmpComponent(timer);
msgWithTimer.Save(dataDir + "AmpEmailWithTimer.eml");
```

### निष्कर्ष

इस गाइड का पालन करके, आप .NET के लिए Aspose.Email का उपयोग करके इंटरैक्टिव और आकर्षक AMP ईमेल बना सकते हैं। ये गतिशील घटक अधिक इंटरैक्टिव उपयोगकर्ता अनुभव प्रदान करके आपकी ईमेल मार्केटिंग रणनीति को बढ़ाएँगे।

**अगले कदम:**
- अपने अभियानों के लिए सबसे उपयुक्त AMP घटकों को खोजने के लिए विभिन्न AMP घटकों के साथ प्रयोग करें.
- संगतता सुनिश्चित करने के लिए विभिन्न डिवाइसों और ईमेल क्लाइंटों पर अपने ईमेल का परीक्षण करें।
- अपने इंटरैक्टिव ईमेल के प्रभाव को मापने के लिए सहभागिता मीट्रिक्स पर नज़र रखें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}