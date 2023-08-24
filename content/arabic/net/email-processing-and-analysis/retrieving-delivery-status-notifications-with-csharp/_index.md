---
title: استرداد إخطارات حالة التسليم باستخدام C#
linktitle: استرداد إخطارات حالة التسليم باستخدام C#
second_title: Aspose.Email .NET واجهة برمجة تطبيقات معالجة البريد الإلكتروني
description: تعرف على كيفية استرداد إشعارات حالة تسليم البريد الإلكتروني باستخدام C# وAspose.Email لـ .NET.
type: docs
weight: 18
url: /ar/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## مقدمة

في اتصالات البريد الإلكتروني، تلعب إشعارات حالة التسليم (DSNs) دورًا حاسمًا في إعلام المرسلين بحالة تسليم رسائل البريد الإلكتروني الخاصة بهم. Aspose.Email for .NET هي مكتبة قوية توفر وظائف للعمل مع رسائل البريد الإلكتروني، بما في ذلك استرداد DSNs. في هذا الدليل، سنتعرف على عملية استرداد إشعارات حالة التسليم باستخدام C# ومكتبة Aspose.Email for .NET.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio.
2.  Aspose.Email لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/email/net).
3. الفهم الأساسي للبرمجة C#.

## خطوات

اتبع هذه الخطوات لاسترداد إشعارات حالة التسليم باستخدام Aspose.Email لـ .NET:

### الخطوة 1: إنشاء مشروع جديد

افتح Visual Studio وقم بإنشاء مشروع تطبيق وحدة تحكم C# جديد.

### الخطوة 2: إضافة مرجع Aspose.Email

انسخ ملف Aspose.Email DLL الذي تم تنزيله إلى دليل مشروعك. بعد ذلك، انقر بزر الماوس الأيمن على المشروع في Solution Explorer، واختر "إضافة" > "مرجع"، واستعرض بحثًا عن Aspose.Email DLL. انقر فوق "موافق" لإضافة المرجع إلى مشروعك.

### الخطوة 3: كتابة التعليمات البرمجية لاسترداد DSNs

 افتح ال`Program.cs` ملف في مشروعك واستيراد مساحات الأسماء اللازمة:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 داخل`Main` الطريقة، اكتب الكود للاتصال بخادم البريد الإلكتروني، واسترجاع DSNs، ومعالجتها:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // قم بتعيين بيانات اعتماد خادم IMAP والمضيف
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // حدد مجلد علبة الوارد
            client.SelectFolder(ImapFolderInfo.InBox);

            // البحث عن الرسائل باستخدام DSNs
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // عملية استرداد DSNs
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // معالجة تفاصيل DSN
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... معالجة تفاصيل DSN الأخرى

                // قم بوضع علامة على الرسالة كمقروءة أو قم بحذفها
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 يستبدل`"your_imap_host"`, `"your_email"` ، و`"your_password"` مع تفاصيل خادم IMAP الفعلية الخاصة بك.

### الخطوة 4: تشغيل التطبيق

بناء وتشغيل التطبيق الخاص بك. سيتم الاتصال بخادم البريد الإلكتروني الخاص بك، واسترداد DSNs من مجلد Inbox، ومعالجة تفاصيلها، وحذفها اختياريًا أو وضع علامة عليها كمقروءة.

## الأسئلة الشائعة

### كيف يمكنني العثور على مضيف خادم IMAP؟

 يمكنك العثور على مضيف خادم IMAP من وثائق أو إعدادات مزود خدمة البريد الإلكتروني الخاص بك. وعادة ما يكون بصيغة`imap.yourdomain.com`.

### كيف يمكنني معالجة تفاصيل DSN بخلاف الموضوع والمرسل؟

 يمكنك الوصول إلى خصائص مختلفة من`MailMessage` كائن لاسترداد تفاصيل DSN مثل عناوين المستلمين وحالة التسليم والطابع الزمني والمزيد. الرجوع إلى[Aspose.وثائق البريد الإلكتروني](https://reference.aspose.com/email/net/) للمزيد من المعلومات.

### هل من الضروري حذف أو وضع علامة DSNs كمقروءة؟

لا، انها ليست ضرورية. يعتمد ما إذا كان سيتم حذف DSNs أو وضع علامة عليها كمقروءة على متطلبات التطبيق الخاص بك. يوضح الكود المقدم كلا الخيارين، ولكن يمكنك تخصيصه وفقًا لاحتياجاتك.

## خاتمة

يعد استرداد إشعارات حالة التسليم باستخدام C# وAspose.Email لـ .NET عملية مباشرة. تعمل مكتبة Aspose.Email على تبسيط الاتصال مع خادم IMAP وتوفر واجهات برمجة التطبيقات سهلة الاستخدام لمعالجة رسائل البريد الإلكتروني. باستخدام هذا الدليل، يمكنك الآن دمج وظيفة استرداد DSN في تطبيقات C# الخاصة بك.