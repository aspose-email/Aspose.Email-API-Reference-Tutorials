---
"description": "تعلم كيفية تعيين نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email لـ .NET. تأكد من سهولة الوصول باستخدام نص بديل واضح. الوثائق والأكواد البرمجية مرفقة."
"linktitle": "إعداد نص بديل للصور - دليل C#"
"second_title": "واجهة برمجة تطبيقات معالجة البريد الإلكتروني Aspose.Email .NET"
"title": "إعداد نص بديل للصور - دليل C#"
"url": "/ar/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إعداد نص بديل للصور - دليل C#


سيشرح لك هذا الدليل عملية إعداد نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email لـ .NET. يُستخدم النص البديل، المعروف أيضًا باسم "النص البديل"، لتوفير وصف نصي للصورة في حال تعذر عرضها. Aspose.Email لـ .NET هي مكتبة فعّالة تتيح لك التعامل مع رسائل البريد الإلكتروني والمرفقات بتنسيقات مختلفة. في هذا الدليل، سنركز على إعداد نص بديل للصور في رسائل البريد الإلكتروني باستخدام C#.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio أو أي بيئة تطوير C# متوافقة.
2. مكتبة Aspose.Email لـ .NET. يمكنك استخدام NuGet Package Manager في Visual Studio.

## الخطوة 1: إنشاء مشروع جديد

1. قم بتشغيل Visual Studio وإنشاء مشروع تطبيق وحدة تحكم C# جديد.

## الخطوة 2: تثبيت Aspose.Email عبر NuGet

1. انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول وحدد "إدارة حزم NuGet".
2. ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث من الحزمة.

## الخطوة 3: إضافة عبارات الاستخدام

```csharp

using Aspose.Email.Mime;
```

## الخطوة 4: تحميل رسالة البريد الإلكتروني وتعديلها

1. قم بتحميل رسالة البريد الإلكتروني باستخدام `MailMessage` فصل:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. تحميل محتوى HTML لرسالة البريد الإلكتروني:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## الخطوة 5: إضافة AlternativeView للنص البديل للصور

أضف htmlview للنص البديل للصورة كـ AlternateView في الرسالة. 
```csharp
message.AlternateViews.Add(htmlView);
```

## الخطوة 6: حفظ البريد الإلكتروني وإرساله

1. احفظ الرسالة المعدلة في ملف أو أرسلها باستخدام الطريقة المطلوبة:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## خاتمة

في هذا الدليل، تعلمت كيفية تعيين نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email لـ .NET. باتباع الخطوات الموضحة أعلاه، يمكنك ضمان بقاء محتوى بريدك الإلكتروني سهل الوصول وغني بالمعلومات حتى في حال تعذر عرض الصور.

## التعليمات

## كيف يمكنني تنزيل مكتبة Aspose.Email؟

يمكنك تنزيل مكتبة Aspose.Email من إصدارات Aspose أو تثبيتها عبر NuGet Package Manager في Visual Studio.

### كيف أضيف الصور كموارد مرتبطة في البريد الإلكتروني؟

لإضافة الصور كموارد مرتبطة في البريد الإلكتروني، يمكنك استخدام `LinkedResource` الفئة. قم بتعيين معرف محتوى للمورد المرتبط، ثم قم بالإشارة إلى معرف المحتوى هذا في نص HTML باستخدام `cid:` مخطط. للحصول على معلومات مفصلة، راجع [توثيق LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Email لـ .NET؟

يمكنك العثور على المزيد من الوثائق التفصيلية والبرامج التعليمية والأمثلة حول العمل مع Aspose.Email لـ .NET في [مرجع واجهة برمجة التطبيقات](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}