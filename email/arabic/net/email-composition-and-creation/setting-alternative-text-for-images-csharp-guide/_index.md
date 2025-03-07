---
title: إعداد نص بديل للصور - دليل C#
linktitle: إعداد نص بديل للصور - دليل C#
second_title: Aspose.Email .NET واجهة برمجة تطبيقات معالجة البريد الإلكتروني
description: تعرف على كيفية تعيين نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email لـ .NET. تأكد من إمكانية الوصول بنص بديل واضح. الوثائق والكود المدرجة.
weight: 15
url: /ar/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إعداد نص بديل للصور - دليل C#


سيرشدك هذا الدليل خلال عملية إعداد نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email for .NET. يتم استخدام النص البديل، المعروف أيضًا باسم "النص البديل"، لتوفير وصف نصي للصورة في حالة تعذر عرض الصورة. Aspose.Email for .NET هي مكتبة قوية تسمح لك بالعمل مع رسائل البريد الإلكتروني والمرفقات بتنسيقات مختلفة. سنركز في هذا الدليل على إعداد نص بديل للصور في رسائل البريد الإلكتروني باستخدام لغة C#.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio أو أي بيئة تطوير متوافقة مع C#.
2. Aspose.Email لمكتبة .NET. يمكنك استخدام NuGet Package Manager في Visual Studio.

## الخطوة 1: إنشاء مشروع جديد

1. قم بتشغيل Visual Studio وقم بإنشاء مشروع تطبيق وحدة تحكم C# جديد.

## الخطوة 2: تثبيت Aspose.Email عبر NuGet

1. انقر بزر الماوس الأيمن على مشروعك في Solution Explorer وحدد "إدارة حزم NuGet".
2. ابحث عن "Aspose.Email" وقم بتثبيت أحدث إصدار من الحزمة.

## الخطوة 3: إضافة استخدام البيانات

```csharp

using Aspose.Email.Mime;
```

## الخطوة 4: تحميل وتعديل رسالة البريد الإلكتروني

1.  قم بتحميل رسالة البريد الإلكتروني باستخدام`MailMessage` فصل:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. قم بتحميل محتوى HTML لرسالة البريد الإلكتروني:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## الخطوة 5: إضافة AlternativeView للنص البديل للصور

أضف htmlview للنص البديل للصورة كـ AlternateView في الرسالة. 
```csharp
message.AlternateViews.Add(htmlView);
```

## الخطوة 6: حفظ وإرسال البريد الإلكتروني

1. احفظ الرسالة المعدلة في ملف أو أرسلها باستخدام الطريقة التي تريدها:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## خاتمة

تعلمت في هذا الدليل كيفية تعيين نص بديل للصور في رسائل البريد الإلكتروني باستخدام Aspose.Email for .NET. باتباع الخطوات الموضحة أعلاه، يمكنك التأكد من أن محتوى بريدك الإلكتروني يظل سهل الوصول إليه وغني بالمعلومات حتى عندما لا يمكن عرض الصور.

## التعليمات

## كيف يمكنني تنزيل مكتبة Aspose.Email؟

يمكنك تنزيل مكتبة Aspose.Email من إصدارات Aspose أو تثبيتها عبر NuGet Package Manager في Visual Studio.

### كيف أقوم بإضافة الصور كموارد مرتبطة في رسالة بريد إلكتروني؟

لإضافة صور كموارد مرتبطة في رسالة بريد إلكتروني، يمكنك استخدام`LinkedResource` فصل. قم بتعيين معرف محتوى للمورد المرتبط، ثم قم بالإشارة إلى معرف المحتوى هذا في نص HTML باستخدام`cid:` مخطط. للحصول على معلومات مفصلة، راجع[وثائق LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Email لـ .NET؟

 يمكنك العثور على المزيد من الوثائق التفصيلية والبرامج التعليمية والأمثلة حول العمل مع Aspose.Email لـ .NET في[مرجع واجهة برمجة التطبيقات](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
