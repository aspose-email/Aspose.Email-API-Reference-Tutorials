---
title: تثبيت Aspose.Email لـ .NET
linktitle: للبدء، تحتاج إلى تثبيت Aspose.Email لمكتبة .NET. يمكنك تنزيله من
second_title: Aspose.Releases
description: أو استخدم NuGet Package Manager في Visual Studio.
type: docs
weight: 15
url: /ar/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## إنشاء مشروع .NET جديد

افتح Visual Studio وقم بإنشاء مشروع .NET جديد.

## قم بتثبيت Aspose.Email لمكتبة .NET باستخدام NuGet Package Manager.

أنت الآن جاهز لبدء البرمجة!

1. تحميل وتحليل رسالة البريد الإلكتروني[تحميل رسالة بريد إلكتروني](https://releases.aspose.com/email/net)قبل أن نتمكن من تعديل الخطوط في البريد الإلكتروني، نحتاج إلى تحميل رسالة بريد إلكتروني. يمكنك تحميل بريد إلكتروني من مصادر مختلفة، مثل ملف أو دفق أو حتى خادم بريد.

2.  قم بتحميل رسالة البريد الإلكتروني

3. تحليل نص الرسالة

## بمجرد تحميل البريد الإلكتروني، يمكنك الوصول إلى أجزائه المختلفة، بما في ذلك نص HTML. يتيح لنا تحليل نص HTML إجراء تغييرات على الخط.

 تحليل نص HTML

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//تعديل الخطوط في البريد الإلكتروني
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## فهم أنماط الخطوط

يتم تعريف الخطوط في رسائل البريد الإلكتروني بتنسيق HTML باستخدام أنماط CSS. لتغيير الخطوط، تحتاج إلى تعديل أنماط CSS المرتبطة بمحتوى HTML الخاص بالبريد الإلكتروني.

```csharp
//تغيير الخطوط برمجيا
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //لنفترض أنك تريد تغيير خط الفقرة في نص HTML للبريد الإلكتروني. وإليك كيف يمكنك القيام بذلك:
        var tnefAttachment = attachment;

        // تغيير خط الفقرة
        //التحويل إلى تنسيق MHT
    }
}
```

## إنشاء رسالة MHT

لتحويل البريد الإلكتروني إلى تنسيق MHT، تحتاج إلى إنشاء رسالة بريد إلكتروني بتنسيق MHT باستخدام Aspose.Email.

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

##  إنشاء رسالة بريد إلكتروني بتنسيق MHT

حفظ الرسالة بتنسيق MHT

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //وأخيرًا، احفظ الرسالة بتنسيق MHT في ملف.
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // احفظ الرسالة بتنسيق MHT
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//كود المصدر الكامل
					var tnefAttachment = attachment;

					//إليك كود المصدر الكامل الذي يجمع كل شيء معًا:
					//خاتمة
				}
			}
			//في هذا الدليل، اكتشفنا كيفية تغيير الخطوط أثناء تحويل MHT باستخدام Aspose.Email لـ .NET. باتباع هذه الخطوات، يمكنك تحويل رسائل البريد الإلكتروني بسلاسة إلى تنسيق MHT مع الحفاظ على أنماط الخط المطلوبة.
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## الأسئلة الشائعة

- هل يمكنني تحويل عدة رسائل بريد إلكتروني إلى تنسيق MHT دفعة واحدة؟
- نعم، يمكنك التنقل عبر مجموعة من رسائل البريد الإلكتروني وتطبيق نفس تغييرات الخط على كل رسالة قبل تحويلها إلى تنسيق MHT.
- هل يدعم Aspose.Email تنسيقات البريد الإلكتروني الأخرى أيضًا؟

## نعم، يدعم Aspose.Email تنسيقات البريد الإلكتروني المختلفة، بما في ذلك EML وMSG وPST والمزيد.

هل من الممكن تخصيص تغييرات الخط بشكل أكبر؟

## قطعاً! يمكنك استكشاف المزيد من أنماط CSS لتخصيص الخطوط، مثل حجم الخط واللون والمحاذاة.

### هل يمكنني استخدام Aspose.Email للمشاريع التجارية؟

نعم، يمكن استخدام Aspose.Email لكل من المشاريع الشخصية والتجارية، وفقًا لشروط الترخيص.[ تذكر أن هذا الدليل يقدم نظرة عامة، ويمكنك استكشاف المزيد من خلال الرجوع إلى](https://releases.aspose.com/email/net)

### مرجع Aspose.Email API

وتجربة تقنيات تخصيص الخطوط المختلفة. ترميز سعيد!

###  دليل C# - استخراج رؤوس البريد الإلكتروني

 دليل C# - استخراج رؤوس البريد الإلكتروني

###  Aspose.Email .NET واجهة برمجة تطبيقات معالجة البريد الإلكتروني

 تعرف على كيفية استخراج رؤوس البريد الإلكتروني في لغة C# باستخدام Aspose.Email لـ .NET. دليل خطوة بخطوة مع الكود المصدري لتحليل البريد الإلكتروني بكفاءة.