---
date: '2026-03-20'
description: تعلم كيفية إنشاء دعوة مشاركة التقويم، وتكوين أذونات التقويم، وتعيين وصول
  المندوب باستخدام Aspose.Email للـ Java.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: إنشاء دعوة مشاركة تقويم باستخدام Aspose.Email للـ Java
url: /ar/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إدارة مشاركة التقويم: دليل Aspose.Email للـ Java

## مقدمة في إدارة مشاركة التقويم
إدارة دعوات مشاركة التقويم يمكن أن تكون مهمة معقدة، خاصةً عند التعامل مع عدة مستخدمين عبر منصات مختلفة. في هذا الدليل ستقوم **بإنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java، وستغطي كل شيء من إنشاء وصول المندوب إلى إرسال رسائل بريد مشاركة التقويم. في النهاية، ستكون قادرًا على تعيين أذونات المندوب، **تكوين أذونات التقويم**، وتبسيط التعاون في مؤسستك.

**ما ستتعلمه**
- كيفية تهيئة عميل EWS باستخدام Aspose.Email للـ Java  
- إنشاء مستخدم مندوب و **تعيين أذونات المندوب**  
- **إنشاء وصول المندوب** وتكوين أذونات التقويم  
- إرسال **رسالة بريد مشاركة تقويم** (دعوة) برمجيًا  
- سيناريوهات واقعية حيث تضيف هذه الميزات قيمة  

قبل أن نبدأ، دعنا نتأكد من أن لديك كل ما تحتاجه.

## إجابات سريعة
- **ما هو الهدف الأساسي من هذا الدليل؟** إظهار كيفية **إنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java.  
- **ما نسخة المكتبة المطلوبة؟** Aspose.Email للـ Java 25.4 (مصنف JDK 16).  
- **هل أحتاج إلى ترخيص؟** نعم – يلزم ترخيص تجريبي أو كامل للاستخدام في الإنتاج.  
- **ما البيئة المطلوبة؟** JDK 16+، Maven، وحساب Exchange Online.  
- **هل يمكنني استخدامه مع خوادم Exchange أخرى؟** نعم، لكن قد تحتاج إلى تعديل عنوان خدمة URL ومستويات الأذونات.

## ما هي دعوة مشاركة التقويم؟
دعوة مشاركة التقويم هي رسالة بريد إلكتروني تمنح مستخدمًا آخر إمكانية عرض (أو تعديل) تقويمك دون منح حقوق صندوق بريد كامل. تُستخدم عادةً لتنسيق الفرق، تخطيط المشاريع، وإدارة الفعاليات.

## لماذا نقوم بتكوين أذونات التقويم؟
تكوين أذونات التقويم يتيح لك التحكم بدقة فيما يمكن للمندوب القيام به—سواء كان يقرأ الأحداث فقط، يقترح أحداثًا جديدة، أو يحرر الإدخالات الموجودة. إعداد الأذونات بشكل صحيح يحمي المعلومات الحساسة مع تمكين التعاون الفعال.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK):** الإصدار 16 أو أحدث.  
- **Maven:** لإدارة التبعيات وبناء المشروع.  
- **مكتبة Aspose.Email للـ Java:** الإصدار 25.4 مع دعم JDK 16.  

### متطلبات إعداد البيئة
1. قم بتثبيت JDK إذا لم تقم بذلك بعد. يمكنك تنزيله من [الموقع الرسمي لأوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. تأكد من تثبيت Maven وتكوينه على جهازك.  
3. اختر بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لتسهيل التطوير.

### المتطلبات المعرفية
- مهارات برمجة Java أساسية  
- الإلمام بتبعيات Maven  
- اختياري: خبرة مع Exchange Web Services (EWS)

## إعداد Aspose.Email للـ Java
### تكوين Maven
أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
Aspose.Email للـ Java يتطلب ترخيصًا للوظائف الكاملة. يمكنك:
- **تجربة مجانية:** التحميل من [صفحة إصدارات Aspose](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت:** طلب مفتاح مؤقت عبر موقع Aspose.  
- **شراء:** الحصول على ترخيص دائم للنشر في بيئات الإنتاج.

### التهيئة الأساسية والإعداد
بعد أن يقوم Maven بحل التبعية، قم بتهيئة عميل EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## كيفية إنشاء دعوة مشاركة تقويم
فيما يلي نستعرض ميزتين أساسيتين: إنشاء وإرسال دعوة مشاركة تقويم، و **تعيين أذونات المندوب** للوصول إلى التقويم.

### الميزة 1: إنشاء وإرسال دعوة مشاركة تقويم
#### نظرة عامة
توضح هذه الميزة كيفية تهيئة العميل، **إنشاء وصول المندوب**، وإرسال رسالة الدعوة.

#### تنفيذ خطوة بخطوة
##### 1️⃣ تهيئة عميل EWS
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
هذا يربط تطبيق Java الخاص بك بـ Exchange Online.

##### 2️⃣ إنشاء مستخدم مندوب
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
هنا نقوم **بإنشاء وصول المندوب** وتعيين مستوى `Reviewer`، مما يسمح للمندوب بعرض عناصر التقويم.

##### 3️⃣ إرسال دعوة مشاركة تقويم
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
يقوم الكود بإنشاء **رسالة بريد مشاركة تقويم** (دعوة) وإرسالها عبر عميل EWS.

### الميزة 2: أذونات وصول المندوب إلى التقويم
#### نظرة عامة
توضح هذه الفقرة كيفية **تكوين أذونات التقويم** وضمان حصول المندوب على الصلاحيات المناسبة.

#### خطوات التنفيذ
##### 1️⃣ تهيئة عميل EWS (إعادة الاستخدام)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ إنشاء وتعيين أذونات المندوب
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
هذا المقتطف **يعيّن أذونات المندوب** بحيث يمكنه عرض إدخالات التقويم دون الحصول على حق وصول كامل إلى صندوق البريد.

## كيفية تكوين أذونات التقويم للمندوبين
عندما تحتاج إلى أن يقوم المندوب بأكثر من مجرد عرض الأحداث—مثل التحرير أو الحذف—يمكنك تغيير `ExchangeDelegateFolderPermissionLevel` إلى:

- `Reviewer` – وصول للقراءة فقط.  
- `Editor` – وصول للقراءة/الكتابة.  
- `Author` – إنشاء وقراءة، لكن لا يمكن الحذف.  
- `Owner` – تحكم كامل، بما في ذلك تعديل الأذونات.

**نصيحة احترافية:** استخدم أقل مستوى صلاحية يلبي المتطلبات التجارية للحفاظ على أمان بيانات التقويم.

## تطبيقات عملية
سيناريوهات واقعية حيث يبرز **إدارة مشاركة التقويم**:
1. **اجتماعات الشركات** – السماح لأعضاء الفريق بعرض جداول الاجتماعات دون منح حقوق صندوق بريد كامل.  
2. **إدارة المشاريع** – يمكن لقادة المشروع مراقبة الجداول الزمنية بينما يحتفظ المطورون بالتحكم في تقاويمهم الخاصة.  
3. **تخطيط الفعاليات** – يتلقى البائعون **رسالة بريد مشاركة تقويم** لتنسيق اللوجستيات دون كشف التفاصيل الداخلية.

## اعتبارات الأداء
- **إدارة الذاكرة:** تخلص من كائنات `MailMessage` الكبيرة فورًا في التطبيقات ذات الأحجام الكبيرة.  
- **معالجة الاستثناءات:** احط نداءات الشبكة بكتل try‑catch للتعامل مع انقطاعات الاتصال بسلاسة.  
- **تحديثات المكتبة:** حافظ على تحديث Aspose.Email للاستفادة من تحسينات الأداء وإصلاحات الأخطاء.

## المشكلات الشائعة والحلول
| المشكلة | السبب المحتمل | الحل |
|-------|--------------|----------|
| عدم استلام الدعوة | مرشحات البريد المزعج أو عنوان بريد غير صحيح | تحقق من عنوان المستلم وأضف نطاق الإرسال إلى قائمة المرسلين الآمنين |
| عدم تطبيق الإذن | استخدام `ExchangeDelegateFolderPermissionLevel` غير صحيح | تأكد من أن مستوى الإذن يتطابق مع الوصول المطلوب |
| استثناء وقت التشغيل على `createCalendarSharingInvitationMessage` | ترخيص مفقود أو مكتبة قديمة | تأكد من تحميل ترخيص صالح واستخدام أحدث نسخة من Aspose.Email |

## الأسئلة المتكررة
**س: ما هو استخدام Aspose.Email للـ Java؟**  
ج: هي مكتبة شاملة لمعالجة البريد الإلكتروني، التقويمات، وجهات الاتصال في تطبيقات Java، تدعم Outlook، Exchange، وبروتوكولات أخرى.

**س: كيف أجهز بيئتي لاستخدام Aspose.Email؟**  
ج: قم بتثبيت JDK 16+، Maven، أضف تبعية Aspose.Email إلى `pom.xml`، واحصل على ترخيص (تجريبي أو كامل).

**س: هل يمكنني استخدام هذا الكود مع إصدارات أخرى من Exchange Online؟**  
ج: نعم، لكن تحقق من عنوان خدمة URL ومستويات الأذونات لتطابق إعدادات الخادم الخاص بك.

**س: ماذا أفعل إذا فشلت دعوة مشاركة التقويم في الإرسال؟**  
ج: تحقق من اتصال الشبكة، بيانات الاعتماد، وأن المستخدم المندوب يمتلك أذونات صالحة. راجع تفاصيل الاستثناء للحصول على دلائل.

**س: هل يمكن إضافة أذونات إضافية مثل التحرير أو الوصول الكامل؟**  
ج: بالتأكيد – استبدل `ExchangeDelegateFolderPermissionLevel.Reviewer` بـ `Editor` أو `Author` أو `Owner` حسب الحاجة.

## الخلاصة
الآن لديك حل كامل من البداية إلى النهاية **لإنشاء دعوة مشاركة تقويم** باستخدام Aspose.Email للـ Java. من خلال تهيئة عميل EWS، **إنشاء وصول المندوب**، **تعيين أذونات المندوب**، وإرسال **رسالة بريد مشاركة تقويم**، يمكنك أتمتة التعاون عبر مؤسستك.

**الخطوات التالية**
- تجربة مستويات أذونات أخرى (Editor، Owner).  
- دمج هذه المنطق في أنظمة الجدولة أو الموارد البشرية الحالية.  
- استكشاف ميزات إضافية في Aspose.Email مثل الأحداث المتكررة أو طلبات الاجتماعات.

---

**آخر تحديث:** 2026-03-20  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (مصنف JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}