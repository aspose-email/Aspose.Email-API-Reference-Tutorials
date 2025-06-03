---
"date": "2025-05-29"
"description": "تعرّف على كيفية إنشاء رسائل بريد إلكتروني تفاعلية وجذابة باستخدام تقنية AMP من Aspose.Email لـ .NET. عزّز استراتيجية التسويق عبر البريد الإلكتروني لديك بمحتوى ديناميكي مثل الرسوم المتحركة، والدوامات، والنماذج."
"title": "إنشاء رسائل بريد إلكتروني تفاعلية باستخدام Aspose.Email .NET AMP - دليل شامل"
"url": "/ar/net/message-formatting-customization/create-interactive-emails-aspose-email-net-amp/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء رسائل بريد إلكتروني تفاعلية باستخدام Aspose.Email .NET AMP: دليل شامل

## مقدمة

هل ترغب في تحسين استراتيجية التسويق عبر البريد الإلكتروني لديك من خلال إنشاء رسائل تفاعلية وجذابة؟ غالبًا ما تفتقر رسائل HTML التقليدية إلى التفاعلية، لكن صفحات الجوال المُسرّعة (AMP) للبريد الإلكتروني تُقدم حلاً مُقنعًا. بدمج Aspose.Email لـ .NET في سير عملك، يمكنك إنشاء رسائل AMP تجذب جمهورك بمحتوى ديناميكي مثل الرسوم المتحركة والصور والدوامات والنماذج.

في هذا البرنامج التعليمي، سنرشدك خلال عملية بناء مكونات مختلفة ضمن رسائل البريد الإلكتروني AMP باستخدام Aspose.Email لـ .NET. سواء كنت مطورًا محترفًا أو مبتدئًا، ستجد رؤى قيّمة حول كيفية تصميم تجارب بريد إلكتروني جذابة.

**ما سوف تتعلمه:**
- كيفية إنشاء هياكل بريد إلكتروني AMP الأساسية
- إضافة عناصر تفاعلية مثل الرسوم المتحركة والصور
- تنفيذ الدوارات، وتناسب النص، والأكورديون، والنماذج، ومكونات الوقت
- تحسين أداء بريدك الإلكتروني

هل أنت مستعد للبدء؟ لنتناول أولاً المتطلبات الأساسية قبل أن نبدأ رحلتنا في إنشاء رسائل بريد إلكتروني ديناميكية.

## المتطلبات الأساسية

قبل البدء في إنشاء رسائل البريد الإلكتروني AMP باستخدام Aspose.Email لـ .NET، تأكد من توفر ما يلي:
- **Aspose.Email لمكتبة .NET:** ستحتاج إلى هذه المكتبة، والتي يمكن تثبيتها عبر مديري الحزم المختلفة.
- **بيئة التطوير:** يوصى باستخدام بيئة تطوير متكاملة مناسبة مثل Visual Studio.
- **المعرفة الأساسية بلغة C# وبروتوكولات البريد الإلكتروني:** ستكون المعرفة بالبرمجة في C# وفهم تنسيقات البريد الإلكتروني مفيدة.

## إعداد Aspose.Email لـ .NET

لبدء استخدام Aspose.Email لـ .NET، عليك تثبيت المكتبة. يمكنك القيام بذلك بإحدى الطرق التالية:

**.NET CLI**
```bash
dotnet add package Aspose.Email
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير الحزم NuGet**
ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث مباشرةً من IDE الخاص بك.

### الحصول على الترخيص

لتجربة Aspose.Email، يمكنك طلب [نسخة تجريبية مجانية](https://releases.aspose.com/email/net/) أو احصل على ترخيص مؤقت. إذا وجدته مفيدًا، فكّر في شراء ترخيص كامل للاستفادة من جميع الميزات.

**التهيئة الأساسية**
بمجرد التثبيت، قم بتهيئة المكتبة في مشروعك:
```csharp
using Aspose.Email;

// كود الإعداد الأساسي لتهيئة Aspose.Email
```

## دليل التنفيذ

### إنشاء بريد إلكتروني AMP بهيكل أساسي

#### ملخص
إنشاء هيكل أساسي هو أساس أي بريد إلكتروني AMP. يوضح هذا القسم كيفية إعداد نص HTML أولي.

**1. تهيئة AmpMessage**
ابدأ بإنشاء مثيل لـ `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msg = new AmpMessage();
```

**2. تعيين نص HTML**
تعيين محتوى HTML بسيط إلى `HtmlBody`.
```csharp
msg.HtmlBody = "<html><body> Hello AMP </body></html>";
msg.Save(dataDir + "BasicAmpEmail.eml");
```

#### تكوين المفتاح
تأكد من إعداد مسار الدليل الخاص بك بشكل صحيح لحفظ الملفات بنجاح.

### إضافة مكون AMP Anim

#### ملخص
قم بتعزيز بريدك الإلكتروني باستخدام مكون الرسوم المتحركة لتحقيق المزيد من التفاعل.

**1. إعداد AmpMessage**
تهيئة `AmpMessage` وتحديد محتوى HTML الأساسي.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAnim = new AmpMessage();
msgWithAnim.HtmlBody = "<html><body> Hello AMP with Animation </body></html>";
```

**2. إنشاء وإضافة AmpAnim**
تكوين `AmpAnim` عنصر.
```csharp
// إضافة مكون AmpAnim
AmpAnim anim = new AmpAnim(800, 400);
anim.Src = "https://placekitten.com/800/400";
anim.Alt = "Test alt";
anim.Attribution = "The Go gopher was designed by Reneee French";
anim.Attributes.Layout = LayoutType.Responsive;
anim.Fallback = "offline";

msgWithAnim.AddAmpComponent(anim);
msgWithAnim.Save(dataDir + "AmpEmailWithAnim.eml");
```

#### استكشاف الأخطاء وإصلاحها
- تأكد من إمكانية الوصول إلى عنوان URL للصورة وتأكد من ضبط السمات المستجيبة بشكل صحيح.

### إضافة مكون صورة AMP

#### ملخص
قم بإدراج الصور لجعل رسائل البريد الإلكتروني الخاصة بك جذابة بصريًا.

**1. تهيئة AmpMessage**
إعداد جديد `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithImage = new AmpMessage();
msgWithImage.HtmlBody = "<html><body> Hello AMP with Image </body></html>";
```

**2. إضافة AmpImage**
تكوين وإضافة `AmpImage`.
```csharp
// إضافة مكون AmpImage
AmpImage img = new AmpImage(800, 400);
img.Src = "https://placekitten.com/800/400";
img.Alt = "Test alt";
img.Attributes.Layout = LayoutType.Responsive;

msgWithImage.AddAmpComponent(img);
msgWithImage.Save(dataDir + "AmpEmailWithImage.eml");
```

### إضافة مكون AMP Carousel

#### ملخص
قم بإنشاء دائرة لعرض صور متعددة في بريد إلكتروني واحد.

**1. إعداد AmpMessage**
تهيئة `AmpMessage` مع محتوى HTML الأساسي.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithCarousel = new AmpMessage();
msgWithCarousel.HtmlBody = "<html><body> Hello AMP with Carousel </body></html>";
```

**2. تكوين وإضافة AmpCarousel**
أضف الصور إلى الدوارة.
```csharp
// إضافة مكون AmpCarousel
AmpCarousel car = new AmpCarousel(800, 400);

AmpImage carouselImg1 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_caleb_woods.jpg"، Alt = "اختبار 2 alt"، السمات = { التخطيط = LayoutType.Fixed } };
car.Images.Add(carouselImg1);

AmpImage carouselImg2 = new AmpImage(800, 400) { Src = "https://placekitten.com/800/400"، Alt = "اختبار alt"، السمات = { التخطيط = LayoutType.Responsive } };
car.Images.Add(carouselImg2);

AmpImage carouselImg3 = new AmpImage(800, 400) { Src = "https://amp.dev/static/img/docs/tutorials/firstemail/photo_by_craig_mclaclan.jpg"، Alt = "اختبار 3 بديل"، السمات = { التخطيط = LayoutType.Fill } };
car.Images.Add(carouselImg3);

msgWithCarousel.AddAmpComponent(car);
msgWithCarousel.Save(dataDir + "AmpEmailWithCarousel.eml");
```

### إضافة مكون AMP FitText

#### ملخص
استخدم مكون النص المناسب لضبط حجم النص بشكل ديناميكي.

**1. تهيئة AmpMessage**
ابدأ بشئ جديد `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithFitText = new AmpMessage();
msgWithFitText.HtmlBody = "<html><body> Hello AMP with Fit Text </body></html>";
```

**2. أضف AmpFitText**
تكوين وإضافة `AmpFitText` عنصر.
```csharp
// إضافة مكون AmpFitText
AmpFitText fitText = new AmpFitText(800, 400);
fitText.Text = "This is a dynamic text that fits the container.";
fitText.Attributes.Layout = LayoutType.Responsive;

msgWithFitText.AddAmpComponent(fitText);
msgWithFitText.Save(dataDir + "AmpEmailWithFitText.eml");
```

### إضافة مكون AMP Accordion

#### ملخص
دمج الأكورديون للسماح للمستخدمين بتوسيع أقسام المحتوى وتقليصها.

**1. تهيئة AmpMessage**
إعداد جديد `AmpMessage`.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithAccordion = new AmpMessage();
msgWithAccordion.HtmlBody = "<html><body> Hello AMP with Accordion </body></html>";
```

**2. أضف AmpAccordion**
تكوين وإضافة `AmpAccordion` عنصر.
```csharp
// إضافة مكون AmpAccordion
AmpAccordion accordion = new AmpAccordion();
accordion.AddSection("Introduction", "This is the introduction section.");
accordion.AddSection("Details", "Here are more details.");
accordion.AddSection("Conclusion", "This is the conclusion.");

msgWithAccordion.AddAmpComponent(accordion);
msgWithAccordion.Save(dataDir + "AmpEmailWithAccordion.eml");
```

### إضافة مكون نموذج AMP

#### ملخص
قم بتعزيز بريدك الإلكتروني باستخدام نموذج لجمع ردود المستخدمين مباشرةً داخل البريد الإلكتروني.

**1. تهيئة AmpMessage**
إنشاء جديد `AmpMessage` مثال.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithForm = new AmpMessage();
msgWithForm.HtmlBody = "<html><body> Hello AMP with Form </body></html>";
```

**2. إضافة AmpForm**
تكوين وإضافة `AmpForm` عنصر.
```csharp
// إضافة مكون AmpForm
AmpForm form = new AmpForm();
form.AddInput("name", "text", "Your Name");
form.AddInput("email", "email", "Your Email");
form.SetAction("https://your-server.com/submit-form"); // تعيين عنوان URL لنقطة النهاية لإرسال النموذج

msgWithForm.AddAmpComponent(form);
msgWithForm.Save(dataDir + "AmpEmailWithForm.eml");
```

### إضافة مكون مؤقت AMP

#### ملخص
قم بإدراج مؤقت لعرض العد التنازلي أو الوقت المنقضي في بريدك الإلكتروني.

**1. تهيئة AmpMessage**
إعداد جديد `AmpMessage` مثال.
```csharp
using Aspose.Email.Amp;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
AmpMessage msgWithTimer = new AmpMessage();
msgWithTimer.HtmlBody = "<html><body> Hello AMP with Timer </body></html>";
```

**2. إضافة AmpTimer**
تكوين وإضافة `AmpTimer` عنصر.
```csharp
// إضافة مكون AmpTimer
AmpTimer timer = new AmpTimer();
timer.SetDuration(3600); // تعيين المدة بالثواني (على سبيل المثال، ساعة واحدة)

msgWithTimer.AddAmpComponent(timer);
msgWithTimer.Save(dataDir + "AmpEmailWithTimer.eml");
```

### خاتمة

باتباع هذا الدليل، يمكنك إنشاء رسائل بريد إلكتروني AMP تفاعلية وجذابة باستخدام Aspose.Email لـ .NET. ستعزز هذه المكونات الديناميكية استراتيجية التسويق عبر البريد الإلكتروني لديك من خلال توفير تجربة مستخدم أكثر تفاعلية.

**الخطوات التالية:**
- جرّب مكونات AMP المختلفة للعثور على المكون الأنسب لحملاتك.
- اختبر رسائل البريد الإلكتروني الخاصة بك عبر الأجهزة المختلفة وعملاء البريد الإلكتروني لضمان التوافق.
- قم بمراقبة مقاييس المشاركة لقياس تأثير رسائل البريد الإلكتروني التفاعلية الخاصة بك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}