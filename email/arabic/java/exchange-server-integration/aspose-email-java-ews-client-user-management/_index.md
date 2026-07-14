---
date: '2026-07-08'
description: تعلم كيفية إنشاء عميل EWS Java باستخدام Aspose.Email لإدارة البريد الإلكتروني
  بفعالية، بما في ذلك message deletion، appending، و user impersonation على Exchange
  Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: تعلم كيفية إنشاء عميل EWS Java باستخدام Aspose.Email لإدارة البريد
  الإلكتروني بفعالية، بما في ذلك message deletion، appending، و user impersonation
  على Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: إنشاء عميل EWS Java باستخدام Aspose.Email – إدارة المستخدمين
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: إنشاء عميل EWS Java باستخدام Aspose.Email – إدارة المستخدمين
url: /ar/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان إدارة البريد الإلكتروني: Aspose.Email Java لعميل EWS المستخدم والتمثيل

## المقدمة

في هذا البرنامج التعليمي ستقوم **بإنشاء تطبيقات EWS client Java** باستخدام Aspose.Email، مما يتيح لك إدارة عدة صناديق بريد على خادم Exchange من قاعدة شفرة Java واحدة. سنستعرض إنشاء كائنات `EWSClient`، حذف الرسائل، إلحاق رسائل بريد جديدة، وتمثيل مستخدمين آخرين—مهام توفر ساعات من العمل اليدوي في بيئات المؤسسات.

### ما ستتعلمه
- كيف تُنشئ كائنات **create EWS client Java** باستخدام بيانات اعتماد متميزة.  
- تقنيات فعّالة لحذف كل رسالة من مجلد مختار.  
- خطوات لإلحاق بريد إلكتروني جاهز إلى صندوق بريد المستخدم.  
- كيفية تمثيل صندوق بريد آخر لسيناريوهات الصناديق المشتركة.

الآن بعد أن عرفت ما سنغطيه، دعنا نجهّز بيئة التطوير.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** أضف تبعية Aspose.Email Maven إلى ملف `pom.xml` الخاص بك.  
- **أي فئة تمثل اتصال Exchange؟** `EWSClient` (أو واجهتها `IEWSClient`).  
- **هل يمكنني حذف جميع الرسائل في استدعاء واحد؟** نعم—قم بالتكرار باستخدام `listMessages` واستدعِ `deleteMessage` على كل URI.  
- **كيف أرسل بريدًا إلكترونيًا دون SMTP؟** استخدم `appendMessage` لوضع `MailMessage` مباشرةً في مجلد.  
- **هل التمثيل آمن؟** يعمل تحت بيانات الاعتماد الأصلية ويحترم سياسات تفويض Exchange.

## ما هو create EWS client Java؟
`create ews client java` يشير إلى إنشاء كائن `EWSClient` في تطبيق Java بحيث يمكنك استدعاء عمليات Exchange Web Services (EWS) برمجيًا. يزيل هذا النهج الحاجة إلى التفاعل اليدوي مع Outlook ويمكّن من معالجة الصناديق البريدية تلقائيًا. من خلال إنشاء عميل مخصص لكل مستخدم، يمكنك عزل بيانات الاعتماد، فرض سياسات على مستوى كل صندوق بريد، وتوسيع الحل عبر عشرات الحسابات دون تكرار الشفرة.

## لماذا نستخدم Aspose.Email لتكامل EWS؟
يدعم Aspose.Email **أكثر من 50** عملية EWS، ويتعامل مع صناديق بريد **متعددة المئات من الصفحات** دون تحميل المتجر بالكامل في الذاكرة، ويعالج **حتى 10,000** رسالة في الدقيقة على عتاد الخادم النموذجي. تجعل هذه القدرات الم quantified منه خيارًا رئيسيًا لأتمتة البريد الإلكتروني على نطاق واسع. كما أن المكتبة تج abstracts تفاصيل SOAP منخفضة المستوى، وتوفر API نظيفًا وآمنًا من الناحية النوعية يقلل من وقت التطوير ويقلل الأخطاء.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** لإدارة التبعيات.  
- **Aspose.Email for Java** المكتبة (أضفها عبر Maven).  
- معرفة أساسية بمفاهيم Exchange Web Services (EWS).

## إعداد Aspose.Email لـ Java
أضف المكتبة إلى ملف Maven `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
يوفر Aspose.Email نسخة تجريبية مجانية، مع خيار طلب ترخيص مؤقت للحصول على جميع القدرات. للاستخدام طويل الأمد، فكر في شراء ترخيص من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

## كيف تُنشئ EWS client Java؟
حمّل خدمة Exchange باستخدام بيانات الاعتماد المناسبة واحصل على نسخة `IEWSClient`—هذا النمط ذو الخطوتين هو جوهر كل عملية لاحقة. يمكنك إعادة استخدام نفس العميل للعديد من الإجراءات أو إنشاء نسخ منفصلة لكل مستخدم للعزل. **`IEWSClient` هي الواجهة التي تكشف جميع عمليات EWS، بينما `EWSClient` توفر طريقة المصنع الثابتة للحصول على تنفيذ.**

عادةً ما يتضمن إنشاء عميل تزويده بعنوان URL للخدمة، اسم المستخدم، كلمة المرور، وربما معلومات النطاق. بمجرد إنشاءه، يتولى العميل المصادقة، توقيع الطلب، وتحليل الاستجابة تلقائيًا.

### إنشاء نسخ EWSClient
**التعريف:** `EWSClient` (المعروض عبر واجهة `IEWSClient`) هو الكائن الأساسي في Aspose.Email للتواصل مع خادم Exchange عبر EWS.

#### استيراد الفئات المطلوبة
ابدأ باستيراد الفئات المطلوبة من Aspose.Email:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### تهيئة نسخ EWSClient
أنشئ كائنات `IEWSClient` لكل صندوق بريد تريد إدارته:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*شرح:* يساعد `getEWSClient` على الاتصال بـ Exchange باستخدام بيانات الاعتماد المقدمة، ويعيد عميلًا جاهزًا للاستخدام يحترم أذونات المستخدم الحالي.

## كيف تحذف الرسائل من مجلد؟
استرجع جميع العناصر في المجلد المستهدف واحذف كل واحدة نهائيًا في تمريرة واحدة. تتجنب هذه الطريقة عبء فتح كل رسالة على حدة. **`listMessages` تُرجع مجموعة من كائنات `MessageInfo` التي تحتوي على URI الفريد لكل رسالة، والتي تمررها بعد ذلك إلى `deleteMessage` لإزالة العنصر من الخادم.**

المعالجة على دفعات تقلل من جولات الشبكة وتمنع انتهاء المهلة عند التعامل مع مجلدات كبيرة. تأكد دائمًا من أن المجلد المستهدف صحيح، حيث إن الحذف لا يمكن عكسه بدون نسخة احتياطية.

### سرد وحذف الرسائل
تكرّر على كل URI للرسالة واستدعِ عملية الحذف:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*شرح:* `listMessages` تُرجع مجموعة من كائنات `MessageInfo`؛ قيم `getUniqueUri()` الخاصة بها تُمرَّر إلى `deleteMessage`، الذي يزيل العناصر نهائيًا من الخادم.

## كيف تُلحق رسالة بمجلد؟
أنشئ كائن `MailMessage` محليًا وخزّنه مباشرةً في مجلد صندوق البريد—دون الحاجة إلى خادم SMTP. **`MailMessage` تمثل بريدًا إلكترونيًا يحتوي على رؤوس، جسم، ومرفقات؛ يمكن بناؤه بالكامل في الذاكرة قبل حفظه في Exchange.**

الإلحاق يتجاوز مسار الإرسال، مما يجعله مثاليًا للمسودات، القوالب، أو إنشاء الرسائل برمجيًا حيث تريد ظهور الرسالة فورًا في صندوق بريد المستخدم.

### إنشاء وإرسال الرسائل
أنشئ البريد الإلكتروني وألحقه بمجلد المسودات:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*شرح:* `appendMessage` يأخذ `MailMessage` و`FolderInfo` (مثل Drafts) ويكتب العنصر إلى صندوق البريد، مما يجعله متاحًا فورًا للمستخدم.

## كيف تمثل مستخدمًا في EWS؟
غيّر سياق أمان العميل إلى صندوق بريد آخر، نفّذ الإجراءات، ثم عد إلى الحساب الأصلي. هذا ضروري لإدارة الصناديق المشتركة. **`impersonateUser` يحدد `ImpersonatedUserId` في طلب EWS الأساسي، مما يسمح للخادم بمعاملة الاستدعاء كما لو كان من صندوق البريد المستهدف.**

بعد إكمال العمليات المطلوبة، استدعِ `resetImpersonation` لاستعادة بيانات الاعتماد الأصلية، مما يضمن تنفيذ الاستدعاءات اللاحقة تحت سياق الأمان الصحيح.

### تنفيذ تمثيل المستخدم
غيّر مؤقتًا سياق العميل للتصرف كمستخدم آخر:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*شرح:* `impersonateUser` يحدد `ImpersonatedUserId` في طلب EWS الأساسي، مما يتيح لك القراءة أو الكتابة كما لو كنت المستخدم المستهدف. استدعاء `resetImpersonation` يعيد بيانات الاعتماد الأصلية.

## تطبيقات عملية
استخدام Aspose.Email Java يتيح حلول أتمتة بريد إلكتروني قوية:
1. **تنظيف البريد الإلكتروني تلقائيًا:** جدولة مهمة ليلية تقوم بمسح مجلدات المسودات القديمة عبر عشرات الصناديق البريدية.  
2. **توزيع بريد جماعي:** إلحاق إعلان قالب إلى صندوق الوارد لكل موظف باستخدام حلقة واحدة.  
3. **إدارة الصناديق المشتركة:** تمثيل صندوق بريد قسم لأرشفة الرسائل القديمة دون منح كل مستخدم وصولًا كاملاً.

## اعتبارات الأداء
للحفاظ على استجابة تطبيقك عند معالجة صناديق بريد كبيرة:
- **استدعاءات API على دفعات** حيثما أمكن (مثال: حذف 500 رسالة لكل طلب).  
- **تدفق الرسائل** بدلاً من تحميل النص الكامل في الذاكرة.  
- **تخلص من كائنات العميل** بسرعة لتحرير مقابس الشبكة واتصالات HTTP.

## المشكلات الشائعة والحلول
- **أخطاء الاتصال:** تحقق من عنوان URL لنقطة نهاية EWS، تأكد من تمكين TLS 1.2، وتأكد من أن قواعد الجدار الناري تسمح بـ HTTPS الصادر.  
- **رفض الإذن للتمثيل:** يجب أن يكون لحساب الخدمة دور “ApplicationImpersonation” مُعين في Exchange.  
- **انتهاء مهلة المجلد الكبير:** زد مهلة `HttpWebRequest` أو عالج المجلد على أجزاء أصغر.

## الأسئلة المتكررة

**س: كيف أقوم باستكشاف أخطاء الاتصال مع EWS؟**  
ج: تحقق من عنوان URL لنقطة النهاية، بيانات الاعتماد، وجدران الشبكة؛ فعّل تسجيل تفصيلي في Aspose.Email لالتقاط بيانات طلب/استجابة HTTP.

**س: هل يمكن لـ Aspose.Email التعامل مع أحجام كبيرة من الرسائل بكفاءة؟**  
ج: نعم—تتيح لك واجهات برمجة التطبيقات الدفعة معالجة **أكثر من 10,000** رسالة في الدقيقة مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت.

**س: ما هي حالات الاستخدام النموذجية لتمثيل المستخدم في EWS؟**  
ج: إدارة الصناديق المشتركة، تنفيذ أرشفة جماعية، وتشغيل تقارير مجدولة نيابةً عن عدة مستخدمين دون تخزين كلمات مرورهم.

**س: هل هناك حدود على استدعاءات API تفرضها Aspose.Email؟**  
ج: لا تفرض Aspose.Email نفسها أي حدود على الاستدعاءات؛ ومع ذلك قد يفرض Exchange سياسات تخفيض السرعة التي يجب الالتزام بها.

**س: كيف يمكنني الحفاظ على أمان بيانات الاعتماد في شفرة Java الخاصة بي؟**  
ج: احفظها في ملفات إعداد مشفرة أو استخدم Azure Key Vault / AWS Secrets Manager، واستخدم دائمًا HTTPS لنقاط نهاية EWS.

---

**آخر تحديث:** 2026-07-08  
**تم الاختبار مع:** Aspose.Email for Java 23.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء نسخة EWSClient باستخدام Aspose.Email لـ Java: دليل دمج خادم Exchange](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [كيفية الاتصال بخادم Microsoft Exchange باستخدام Aspose.Email لـ Java وEWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [أتمتة إدارة البريد الإلكتروني باستخدام Aspose.Email وعميل Java EWS: دليل شامل](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}