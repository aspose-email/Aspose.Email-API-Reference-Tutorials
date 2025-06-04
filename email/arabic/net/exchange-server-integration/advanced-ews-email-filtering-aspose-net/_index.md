---
"date": "2025-05-30"
"description": "تعلّم تقنيات متقدمة لتصفية البريد الإلكتروني باستخدام Aspose.Email لـ .NET وEWS. أدر رسائل البريد الإلكتروني بكفاءة حسب التاريخ، والمرسل، والمستلم، والإشعارات، والحجم، والمزيد."
"title": "إتقان تصفية البريد الإلكتروني المتقدمة في EWS باستخدام Aspose.Email .NET للتكامل مع Exchange Server"
"url": "/ar/net/exchange-server-integration/advanced-ews-email-filtering-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تصفية البريد الإلكتروني المتقدمة في EWS باستخدام Aspose.Email .NET

## مقدمة
في عالمنا الرقمي سريع الخطى، تُعدّ إدارة البريد الإلكتروني بكفاءة أمرًا بالغ الأهمية. مع وصول عدد لا يُحصى من الرسائل يوميًا، يُمكن لفرزها بسرعة للعثور على المعلومات ذات الصلة أن يُعزز الإنتاجية بشكل كبير. سيُرشدك هذا البرنامج التعليمي إلى تقنيات التصفية المتقدمة باستخدام Aspose.Email لـ .NET وخدمات Exchange Web Services (EWS). ستتعلم كيفية الاتصال بخدمات Exchange Web Services وتصفية رسائل البريد الإلكتروني بناءً على معايير مثل التاريخ، والمُرسِل، والمستلم، وإشعارات التسليم، والحجم، وغيرها.

**ما سوف تتعلمه:**
- الاتصال بـ EWS باستخدام Aspose.Email لـ .NET.
- تصفية رسائل البريد الإلكتروني حسب التاريخ والمرسل والمستلم والسمات الأخرى.
- تنفيذ دعم الترقيم لترشيح الرسائل بكفاءة.
- تحسين الأداء عند التعامل مع كميات كبيرة من بيانات البريد الإلكتروني.

دعونا نراجع المتطلبات الأساسية قبل الخوض في تفاصيل التنفيذ.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **Aspose.Email لـ .NET** المكتبة المُثبّتة في مشروعك. هذا البرنامج التعليمي مُوجّه للإصدار 22.x وما فوق.
- فهم أساسي لبرمجة C#.
- الوصول إلى خادم Exchange مع تمكين EWS (على سبيل المثال، Microsoft Outlook).
- Visual Studio أو أي IDE متوافق.

تأكد من إعداد هذه الأدوات قبل الانتقال إلى قسم التنفيذ.

## إعداد Aspose.Email لـ .NET
أولاً، قم بتثبيت Aspose.Email في مشروعك باستخدام إحدى الطرق التالية:

**.NET CLI:**
```bash
dotnet add package Aspose.Email
```

**وحدة تحكم مدير الحزمة:**
```powershell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير حزمة NuGet:**
ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
يمكنك الحصول على الترخيص بثلاث طرق:
- **نسخة تجريبية مجانية:** قم بتنزيل ترخيص مؤقت لتقييم الميزات الكاملة.
- **رخصة مؤقتة:** اطلب ترخيصًا مؤقتًا مجانيًا لمدة 30 يومًا من Aspose.
- **شراء:** قم بشراء اشتراك إذا وجدت أن الأداة مفيدة للمشاريع طويلة الأمد.

بعد التثبيت والترخيص، انتقل إلى تهيئة اتصالك بـ EWS.

## دليل التنفيذ

### الميزة: الاتصال بـ EWS
**ملخص:** إنشاء اتصال بخدمات Exchange Web Services (EWS) باستخدام Aspose.Email لـ .NET.

#### الخطوة 1: تهيئة الاتصال
```csharp
using Aspose.Email.Clients.Exchange.WebService;
using System;

const string mailboxUri = "https://outlook.office365.com/ews/exchange.asmx";
const string username = "username";
const string password = "password";
const string domain = "domain";                        

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**توضيح:** يتصل هذا الرمز بخادم Exchange باستخدام بيانات الاعتماد المُقدّمة. استبدل العناصر النائبة بمعرف URI لصندوق بريدك الإلكتروني وتفاصيل المصادقة.

### الميزة: تصفية رسائل البريد الإلكتروني حسب التاريخ
**ملخص:** تعرف على كيفية تصفية رسائل البريد الإلكتروني التي تلقيتها اليوم وخلال الأيام السبعة الماضية.

#### الخطوة 1: استرداد رسائل البريد الإلكتروني اليوم
```csharp
using Aspose.Email.Tools.Search;
using System;

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.On(DateTime.Now);
    
    MailQuery query = builder.GetQuery();
    var messagesToday = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### الخطوة 2: استرداد رسائل البريد الإلكتروني من الأيام السبعة الماضية
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.Before(DateTime.Now);
    builder.InternalDate.Since(DateTime.Now.AddDays(-7));
    
    MailQuery query = builder.GetQuery();
    var messagesLastWeek = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**توضيح:** استخدم `MailQueryBuilder` إنشاء استعلامات بناءً على تواريخ البريد الإلكتروني. يتيح ذلك تصفية رسائل البريد الإلكتروني الواردة اليوم أو خلال فترة زمنية محددة.

### الميزة: تصفية رسائل البريد الإلكتروني حسب المرسل أو المجال
**ملخص:** توضح هذه الميزة كيفية تصفية رسائل البريد الإلكتروني من مرسل ونطاق محددين.

#### الخطوة 1: استرداد رسائل البريد الإلكتروني من مرسل محدد
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderSender = new MailQueryBuilder();
    builderSender.From.Contains("saqib.razzaq@127.0.0.1");
    
    MailQuery querySender = builderSender.GetQuery();
    var senderMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySender);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### الخطوة 2: استرداد رسائل البريد الإلكتروني من نطاق محدد
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderDomain = new MailQueryBuilder();
    builderDomain.From.Contains("SpecificHost.com");
    
    MailQuery queryDomain = builderDomain.GetQuery();
    var domainMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryDomain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**توضيح:** يستخدم `MailQueryBuilder` لتصفية رسائل البريد الإلكتروني حسب عنوان البريد الإلكتروني للمُرسِل أو نطاقه. يُساعد هذا على تحديد الرسائل المهمة من مصادر مُحددة.

### الميزة: تصفية رسائل البريد الإلكتروني حسب المستلم أو معرف الرسالة
**ملخص:** تعرف على كيفية تصفية رسائل البريد الإلكتروني المرسلة إلى مستلم محدد وبمعرف رسالة محدد.

#### الخطوة 1: استرداد رسائل البريد الإلكتروني المرسلة إلى مستلم محدد
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderRecipient = new MailQueryBuilder();
    builderRecipient.To.Contains("recipient@example.com");
    
    MailQuery queryRecipient = builderRecipient.GetQuery();
    var recipientMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryRecipient);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### الخطوة 2: استرداد رسائل البريد الإلكتروني حسب معرف الرسالة المحدد
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMessageId = new ExchangeQueryBuilder();
    builderMessageId.MessageId.Equals("Specific-Message-ID");
    
    MailQuery queryMessageId = builderMessageId.GetQuery();
    var messageIdMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMessageId);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**توضيح:** تساعد عملية التصفية حسب المستلم أو معرف الرسالة في التركيز على رسائل البريد الإلكتروني ذات الاهتمام استنادًا إلى المستلم المقصود أو معرف فريد.

### الميزة: تصفية رسائل البريد الإلكتروني حسب إشعارات التسليم والحجم
**ملخص:** تُظهر هذه الميزة كيفية تصفية رسائل البريد الإلكتروني استنادًا إلى إشعارات التسليم وحجم الرسالة.

#### الخطوة 1: استرداد إشعارات تسليم البريد
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMDN = new ExchangeQueryBuilder();
    builderMDN.ContentClass.Equals(ContentClassType.MDN.ToString());
    
    MailQuery queryMDN = builderMDN.GetQuery();
    var mdnMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMDN);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### الخطوة 2: تصفية الرسائل حسب الحجم
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderSize = new ExchangeQueryBuilder();
    builderSize.ItemSize.Greater(80000); // مثال على الحجم بالبايت
    
    MailQuery querySize = builderSize.GetQuery();
    var sizeMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySize);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**توضيح:** استخدم هذه المرشحات لإدارة رسائل البريد الإلكتروني بشكل فعال استنادًا إلى حالة التسليم وحجمها.

## خاتمة
تناول هذا البرنامج التعليمي تقنيات متقدمة لتصفية البريد الإلكتروني باستخدام Aspose.Email لـ .NET مع EWS. بإتقان هذه المهارات، يمكنك إدارة صندوق الوارد بكفاءة، مما يُحسّن إنتاجيتك في التعامل مع كميات كبيرة من رسائل البريد الإلكتروني.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}