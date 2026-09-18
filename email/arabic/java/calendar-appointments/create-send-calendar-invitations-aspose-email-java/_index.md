---
date: '2026-09-17'
description: كيفية إنشاء calendar invitation باستخدام Aspose.Email for Java يتيح لك
  مشاركة التقويمات، وتعيين delegate permissions، وإرسال sharing emails programmatically.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: كيفية إنشاء calendar invitation باستخدام Aspose.Email for Java يتيح
  لك مشاركة التقويمات programmatically، وتعيين delegate permissions، وإرسال sharing
  emails عبر Exchange Web Services، مما يحسن التعاون بين الفرق.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: كيفية إنشاء calendar invitation باستخدام Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: كيفية إنشاء calendar invitation باستخدام Aspose.Email for Java
url: /ar/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مشاركة التقويم: دليل Aspose.Email للـ Java

## مقدمة لإدارة مشاركة التقويم
إدارة دعوات مشاركة التقويم يمكن أن تكون مهمة معقدة، خاصةً عند التعامل مع عدة مستخدمين عبر منصات مختلفة. في هذا البرنامج التعليمي ستقوم **بإنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java، مع تغطية كل شيء من إنشاء وصول المندوب إلى إرسال رسائل مشاركة التقويم. في النهاية، ستكون قادرًا على تعيين أذونات المندوب، **تكوين أذونات التقويم**، وتبسيط التعاون في مؤسستك.

**ما ستتعلمه**
- كيفية تهيئة عميل EWS باستخدام Aspose.Email للـ Java  
- إنشاء مستخدم مندوب و **تعيين أذونات المندوب**  
- **إنشاء وصول المندوب** وتكوين أذونات التقويم  
- إرسال **رسالة مشاركة تقويم** (دعوة) برمجيًا  
- سيناريوهات واقعية حيث تضيف هذه الميزات قيمة  

قبل أن نبدأ، دعنا نتأكد من أن لديك كل ما تحتاجه.

## إجابات سريعة
- **ما هو الهدف الأساسي من هذا الدليل؟** لإظهار كيفية **إنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java.  
- **ما هو إصدار المكتبة المطلوب؟** Aspose.Email للـ Java 25.4 (مصنف JDK 16).  
- **هل أحتاج إلى ترخيص؟** نعم – يلزم ترخيص تجريبي أو كامل للاستخدام في الإنتاج.  
- **ما البيئة المطلوبة؟** JDK 16+، Maven، وحساب Exchange Online.  
- **هل يمكنني استخدامه مع خوادم Exchange أخرى؟** نعم، لكن قد تحتاج إلى تعديل عنوان خدمة URL ومستويات الأذونات.

## ما هي دعوة مشاركة التقويم؟
دعوة مشاركة التقويم هي رسالة بريد إلكتروني تمنح مستخدمًا آخر إمكانية عرض (أو تعديل) تقويمك دون منح حقوق صندوق بريد كاملة. تمكن أعضاء الفريق من رؤية جدولك، اقتراح اجتماعات، أو إدارة الأحداث مع الحفاظ على أمان صندوق بريدك.

## لماذا يتم تكوين أذونات التقويم؟
تكوين أذونات التقويم يتيح لك التحكم بدقة فيما يمكن للمندوب القيام به—سواء كان يمكنه فقط قراءة الأحداث، اقتراح أحداث جديدة، أو تعديل الإدخالات الموجودة. إعدادات الأذونات الصحيحة تحمي المعلومات الحساسة مع تمكين التعاون الفعال. على سبيل المثال، منح وصول للقراءة فقط يمنع التغييرات غير المقصودة، بينما تسمح حقوق التعديل للمندوب بجدولة أو تعديل الاجتماعات نيابةً عنك.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK):** الإصدار 16 أو أحدث.  
- **Maven:** لإدارة الاعتمادات وبناء المشروع.  
- **مكتبة Aspose.Email للـ Java:** الإصدار 25.4 مع دعم JDK 16.  

### متطلبات إعداد البيئة
1. قم بتثبيت JDK إذا لم تقم بذلك بعد. يمكنك تنزيله من [الموقع الرسمي لـ Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. تأكد من تثبيت Maven وتكوينه على جهازك.  
3. اختر بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لتسهيل التطوير.

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية  
- الإلمام باعتمادات Maven  
- اختياري: خبرة في خدمات ويب Exchange (EWS)

## إعداد Aspose.Email للـ Java
### تكوين Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
يتطلب Aspose.Email للـ Java ترخيصًا للوظائف الكاملة. يمكنك:
- **تجربة مجانية:** تحميل من [صفحة إصدارات Aspose](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت:** طلب مفتاح مؤقت على موقع Aspose.  
- **شراء:** الحصول على ترخيص دائم للنشر في بيئة الإنتاج.

### التهيئة الأساسية والإعداد
بعد أن يقوم Maven بحل الاعتماد، قم بتهيئة عميل EWS:

`ExchangeService` هو الصف الأساسي المستخدم للتواصل مع Exchange Web Services.

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## كيفية إنشاء دعوة مشاركة تقويم
لإنشاء دعوة مشاركة تقويم، أولاً تتصل بـ Exchange باستخدام عميل `ExchangeService`، ثم تحدد مندوبًا بمستوى الإذن المطلوب، وأخيرًا تنشئ `MailMessage` الذي يتضمن طلب المشاركة. الخطوات التالية توضح سير العمل هذا في Java.

فيما يلي نغطي ميزتين أساسيتين: إنشاء وإرسال دعوة مشاركة تقويم، و **تعيين أذونات المندوب** للوصول إلى التقويم.

### الميزة 1: إنشاء وإرسال دعوة مشاركة تقويم
#### نظرة عامة
هذه الميزة ترشدك خلال تهيئة العميل، **إنشاء وصول المندوب**، وإرسال بريد الدعوة.

#### تنفيذ خطوة بخطوة
##### 1️⃣ تهيئة عميل EWS
`ExchangeService` يمثل الاتصال بخادم Exchange ويُستخدم لإرسال واستقبال الرسائل.

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
هذا يربط تطبيق Java الخاص بك بـ Exchange Online.

##### 2️⃣ إنشاء مستخدم مندوب
`DelegateUser` يحدد عنوان البريد الإلكتروني للمندوب ومستوى الإذن الذي سيُمنح.

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
هنا نقوم **بإنشاء وصول المندوب** وتعيين المستوى `Reviewer`، الذي يسمح للمندوب بعرض عناصر التقويم.

##### 3️⃣ إرسال دعوة مشاركة تقويم
`MailMessage` يبني البريد الإلكتروني الذي يحمل دعوة مشاركة التقويم.

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
الكود يبني **رسالة مشاركة تقويم** (دعوة) ويرسلها عبر عميل EWS.

### الميزة 2: إذن وصول المندوب إلى التقويم
#### نظرة عامة
هذا القسم يوضح كيفية **تكوين أذونات التقويم** وضمان أن المندوب يمتلك الحقوق المناسبة.

#### خطوات التنفيذ
##### 1️⃣ تهيئة عميل EWS (إعادة الاستخدام)
`ExchangeService` يمكن إعادة استخدامه للعمليات المتعددة بعد التكوين الأولي.

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ إنشاء وتعيين أذونات المندوب
`ExchangeDelegateFolderPermissionLevel` يعدد مستويات الوصول التي يمكن أن يمتلكها المندوب لمجلد التقويم.

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
هذا المقتطف **يحدد أذونات المندوب** بحيث يمكن للمستخدم عرض إدخالات التقويم دون الحصول على وصول كامل إلى صندوق البريد.

## كيفية تكوين أذونات التقويم للمندوبين
عندما يحتاج المندوب إلى أكثر من وصول للقراءة فقط، يمكنك تعديل `ExchangeDelegateFolderPermissionLevel` لمنح حقوق تعديل أو مؤلف أو مالك. اختر الحد الأدنى من المستوى الذي يلبي الحاجة التجارية للحفاظ على الأمان مع توفير الوظيفة اللازمة. على سبيل المثال، تعيين مستوى Editor يسمح للمندوب بإنشاء وتعديل وحذف الأحداث، بينما مستوى Reviewer يسمح فقط بالعرض.

- `Reviewer` – وصول للقراءة فقط.  
- `Editor` – وصول للقراءة/الكتابة.  
- `Author` – إنشاء وقراءة، لكن لا يمكن الحذف.  
- `Owner` – تحكم كامل، بما في ذلك تغييرات الأذونات.  

**نصيحة احترافية:** استخدم أقل مستوى من الامتيازات يلبي متطلبات العمل للحفاظ على أمان بيانات التقويم الخاصة بك.

## التطبيقات العملية
سيناريوهات واقعية حيث يبرز **إدارة مشاركة التقويم**:
1. **الاجتماعات المؤسسية** – السماح لأعضاء الفريق بعرض جداول الاجتماعات دون منح حقوق صندوق بريد كامل.  
2. **إدارة المشاريع** – قادة المشروع يمكنهم مراقبة الجداول الزمنية بينما يحتفظ المطورون بالتحكم في تقاويمهم الخاصة.  
3. **تخطيط الفعاليات** – يتلقى البائعون **رسالة مشاركة تقويم** لتنسيق اللوجستيات دون كشف التفاصيل الداخلية.

## اعتبارات الأداء
- **إدارة الذاكرة:** التخلص من كائنات `MailMessage` الكبيرة بسرعة في التطبيقات ذات الحجم العالي.  
- **معالجة الاستثناءات:** غلف استدعاءات الشبكة بكتل try‑catch للتعامل مع مشكلات الاتصال بسلاسة.  
- **تحديثات المكتبة:** يدعم Aspose.Email للـ Java أكثر من 50 بروتوكولًا ويمكنه معالجة التقويمات التي تحتوي على ما يصل إلى 10,000 عنصر دون تحميل الملف بالكامل في الذاكرة، لذا احرص على تحديث المكتبة للاستفادة من تحسينات الأداء وإصلاحات الأخطاء.

## المشكلات الشائعة والحلول
| المشكلة | السبب المحتمل | الحل |
|-------|--------------|----------|
| عدم استلام الدعوة | عوامل تصفية البريد المزعج أو عنوان بريد إلكتروني غير صحيح | التحقق من عنوان المستلم وإضافة نطاق الإرسال إلى قائمة المرسلين الآمنين |
| عدم تطبيق الإذن | استخدام `ExchangeDelegateFolderPermissionLevel` غير صحيح | التحقق مرة أخرى من أن مستوى الإذن يتطابق مع الوصول المطلوب |
| استثناء وقت التشغيل على `createCalendarSharingInvitationMessage` | عدم وجود ترخيص أو مكتبة قديمة | التأكد من تحميل ترخيص صالح واستخدام أحدث نسخة من Aspose.Email |

## الأسئلة المتكررة
**س: ما هو استخدام Aspose.Email للـ Java؟**  
ج: إنها مكتبة شاملة لمعالجة البريد الإلكتروني، التقويمات، والجهات الاتصال في تطبيقات Java، وتدعم Outlook وExchange وغيرها من البروتوكولات.

**س: كيف أقوم بإعداد بيئتي لاستخدام Aspose.Email؟**  
ج: قم بتثبيت JDK 16+، Maven، أضف اعتماد Aspose.Email إلى `pom.xml`، واحصل على ترخيص (تجريبي أو كامل).

**س: هل يمكنني استخدام هذا الكود مع إصدارات أخرى من Exchange Online؟**  
ج: نعم، ولكن تحقق من أن عنوان خدمة URL ومستويات الأذونات تتطابق مع تكوين خادمك.

**س: ماذا أفعل إذا فشلت دعوة مشاركة التقويم في الإرسال؟**  
ج: تحقق من اتصال الشبكة، بيانات الاعتماد، وأن مستخدم المندوب لديه أذونات صالحة. راجع تفاصيل الاستثناء للحصول على مؤشرات.

**س: هل يمكن إضافة أذونات إضافية مثل التحرير أو الوصول الكامل؟**  
ج: بالتأكيد – استبدل `ExchangeDelegateFolderPermissionLevel.Reviewer` بـ `Editor` أو `Author` أو `Owner` حسب الحاجة.

## الخلاصة
أصبحت الآن تمتلك حلاً كاملاً من البداية إلى النهاية لـ **إنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java. من خلال تهيئة عميل EWS، **إنشاء وصول المندوب**، **تعيين أذونات المندوب**، وإرسال **رسالة مشاركة تقويم**، يمكنك أتمتة التعاون عبر مؤسستك.

**الخطوات التالية**
- تجربة مستويات أذونات أخرى (Editor، Owner).  
- دمج هذه المنطق في أنظمة الجدولة أو الموارد البشرية الحالية لديك.  
- استكشاف ميزات إضافية في Aspose.Email مثل الأحداث المتكررة أو طلبات الاجتماعات.

---

**آخر تحديث:** 2026-09-17  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (مصنف JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء عنصر تقويم Java باستخدام Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java تصفية مواعيد Exchange حسب التاريخ](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [إنشاء تقويم Exchange Java باستخدام Aspose.Email – دليل كامل](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}