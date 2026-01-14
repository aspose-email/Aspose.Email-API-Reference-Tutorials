---
date: '2025-12-20'
description: تعلم كيفية إدارة مشاركة التقويم، وتعيين أذونات المندوب، وإنشاء وصول المندوب
  باستخدام Aspose.Email للغة Java. اتبع هذا الدليل خطوة بخطوة لإرسال رسائل مشاركة
  التقويم بكفاءة.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: 'إدارة مشاركة التقويم - دليل Aspose.Email للغة Java'
url: /ar/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إدارة مشاركة التقويم: دليل Aspose.Email للـ Java

## مقدمة في إدارة مشاركة التقويم
إدارة دعوات مشاركة التقويم يمكن أن تكون مهمة معقدة، خاصةً عند التعامل مع عدة مستخدمين عبر منصات مختلفة. في هذا البرنامج التعليمي ستتعلم كيفية **إدارة مشاركة التقويم** باستخدام Aspose.Email للـ Java، مع تغطية كل شيء من إنشاء وصول المندوب إلى إرسال رسائل مشاركة التقويم. في النهاية، ستتمكن من تعيين أذونات المندوب، تكوين أذونات التقويم، وتبسيط التعاون في مؤسستك.

**ما ستتعلمه**
- كيفية تهيئة عميل EWS باستخدام Aspose.Email للـ Java  
- إنشاء مستخدم مندوب و **تعيين أذونات المندوب**  
- **إنشاء وصول المندوب** وتكوين أذونات التقويم  
- إرسال **رسالة مشاركة التقويم** (دعوة) برمجياً  
- سيناريوهات واقعية حيث تضيف هذه الميزات قيمة  

قبل أن نبدأ، دعنا نتأكد من أن لديك كل ما تحتاجه.

## إجابات سريعة
- **ما هو الهدف الأساسي من هذا الدليل؟** إظهار كيفية **إدارة مشاركة التقويم** باستخدام Aspose.Email للـ Java.  
- **ما نسخة المكتبة المطلوبة؟** Aspose.Email للـ Java 25.4 (مصنف JDK 16).  
- **هل أحتاج إلى ترخيص؟** نعم – يلزم وجود ترخيص تجريبي أو كامل للاستخدام في الإنتاج.  
- **ما البيئة المطلوبة؟** JDK 16+، Maven، وحساب Exchange Online.  
- **هل يمكنني استخدام هذا مع خوادم Exchange أخرى؟** نعم، لكن قد تحتاج إلى تعديل عنوان URL للخدمة ومستويات الأذونات.

## المتطلبات المسبقة
- **مجموعة تطوير Java (JDK):** الإصدار 16 أو أحدث.  
- **Maven:** لإدارة التبعيات وبناء المشروع.  
- **مكتبة Aspose.Email للـ Java:** الإصدار 25.4 مع دعم JDK 16.  

### متطلبات إعداد البيئة
1. قم بتثبيت JDK إذا لم تقم بذلك بعد. يمكنك تنزيله من [الموقع الرسمي لـ Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. تأكد من تثبيت Maven وتكوينه على جهازك.  
3. اختر بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لتسهيل التطوير.

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية  
- الإلمام بتبعيات Maven  
- اختياري: خبرة في خدمات الويب لـ Exchange (EWS)

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
يتطلب Aspose.Email للـ Java ترخيصاً للوظائف الكاملة. يمكنك:
- **تجربة مجانية:** تنزيلها من [صفحة إصدارات Aspose](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت:** طلب مفتاح مؤقت على موقع Aspose.  
- **شراء:** الحصول على ترخيص دائم للنشر في بيئة الإنتاج.

### التهيئة الأساسية والإعداد
بعد أن يحل Maven التبعية، قم بتهيئة عميل EWS:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## دليل التنفيذ
أدناه نغطي ميزتين أساسيتين: إنشاء وإرسال دعوة مشاركة التقويم، و **تعيين أذونات المندوب** للوصول إلى التقويم.

### الميزة 1: إنشاء وإرسال دعوة مشاركة التقويم
#### نظرة عامة
هذه الميزة ترشدك عبر تهيئة العميل، **إنشاء وصول المندوب**، وإرسال بريد الدعوة.

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
هنا نقوم **بإنشاء وصول المندوب** وتعيين المستوى `Reviewer`، الذي يسمح للمندوب بمشاهدة عناصر التقويم.

##### 3️⃣ إرسال دعوة مشاركة التقويم
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
يقوم الكود بإنشاء **رسالة مشاركة التقويم** (دعوة) وإرسالها عبر عميل EWS.

### الميزة 2: إذن وصول المندوب إلى التقويم
#### نظرة عامة
يوضح هذا القسم كيفية **تكوين أذونات التقويم** وضمان أن المندوب يمتلك الحقوق المناسبة.

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
هذا المقتطف **يعيّن أذونات المندوب** بحيث يمكن للمستخدم مشاهدة إدخالات التقويم دون الحصول على وصول كامل إلى صندوق البريد.

## التطبيقات العملية
سيناريوهات واقعية حيث **إدارة مشاركة التقويم** تتألق:
1. **الاجتماعات المؤسسية** – السماح لأعضاء الفريق بمشاهدة جداول الاجتماعات دون منحهم حقوق صندوق بريد كامل.  
2. **إدارة المشاريع** – يمكن لقادة المشروع مراقبة الجداول الزمنية بينما يحتفظ المطورون بالتحكم في تقاويمهم الخاصة.  
3. **تخطيط الفعاليات** – يتلقى البائعون **رسالة مشاركة التقويم** لتنسيق اللوجستيات دون كشف التفاصيل الداخلية.

## اعتبارات الأداء
- **إدارة الذاكرة:** التخلص من كائنات `MailMessage` الكبيرة بسرعة في التطبيقات ذات الحجم الكبير.  
- **معالجة الاستثناءات:** احط المكالمات الشبكية بكتل try‑catch للتعامل مع مشكلات الاتصال بسلاسة.  
- **تحديثات المكتبة:** حافظ على تحديث Aspose.Email للاستفادة من تحسينات الأداء وإصلاحات الأخطاء.

## الأسئلة المتكررة
**س: ما هو استخدام Aspose.Email للـ Java؟**  
ج: إنها مكتبة شاملة للتعامل مع البريد الإلكتروني، التقويمات، وجهات الاتصال في تطبيقات Java، وتدعم Outlook وExchange وبروتوكولات أخرى.

**س: كيف أقوم بإعداد بيئتي لاستخدام Aspose.Email؟**  
ج: قم بتثبيت JDK 16+، Maven، أضف تبعية Aspose.Email إلى `pom.xml`، واحصل على ترخيص (تجريبي أو كامل).

**س: هل يمكنني استخدام هذا الكود مع إصدارات أخرى من Exchange Online؟**  
ج: نعم، لكن تأكد من أن عنوان URL للخدمة ومستويات الأذونات تتطابق مع تكوين الخادم الخاص بك.

**س: ماذا أفعل إذا فشلت دعوة مشاركة التقويم في الإرسال؟**  
ج: تحقق من اتصال الشبكة، بيانات الاعتماد، وأن المستخدم المندوب لديه أذونات صالحة. راجع تفاصيل الاستثناء للحصول على دلائل.

**س: هل يمكن إضافة أذونات إضافية مثل التحرير أو الوصول الكامل؟**  
ج: بالتأكيد – استبدل `ExchangeDelegateFolderPermissionLevel.Reviewer` بـ `Editor` أو `Author` أو `Owner` حسب الحاجة.

## الخلاصة
أنت الآن تمتلك حلاً كاملاً من البداية إلى النهاية لـ **إدارة مشاركة التقويم** باستخدام Aspose.Email للـ Java. من خلال تهيئة عميل EWS، **إنشاء وصول المندوب**، **تعيين أذونات المندوب**، وإرسال **رسالة مشاركة التقويم**، يمكنك أتمتة التعاون عبر مؤسستك.

**الخطوات التالية**
- جرب مستويات أذونات أخرى (Editor، Owner).  
- دمج هذه المنطق في أنظمة الجدولة أو الموارد البشرية الحالية لديك.  
- استكشف ميزات إضافية في Aspose.Email مثل الأحداث المتكررة أو طلبات الاجتماعات.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (مصنف JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}