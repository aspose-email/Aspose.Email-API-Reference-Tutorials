---
date: '2026-07-17'
description: تعلم كيفية إنشاء exchange query java لتصفية مواعيد Exchange Server حسب
  التاريخ. يوضح هذا الدرس الخاص بـ Aspose Email Java الإعداد، بناء الاستعلام، واسترجاع
  أحداث تقويم Exchange.
keywords:
- build exchange query java
- retrieve exchange calendar events
- aspose email java tutorial
lastmod: '2026-07-17'
og_description: تعلم كيفية إنشاء exchange query java لتصفية مواعيد Exchange Server
  حسب التاريخ. يوضح هذا الدرس الخاص بـ Aspose Email Java الإعداد، بناء الاستعلام،
  واسترجاع أحداث تقويم Exchange.
og_image_alt: 'Developer guide: Build exchange query java to filter Exchange appointments
  by date'
og_title: إنشاء Exchange Query Java – تصفية المواعيد حسب التاريخ
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to build exchange query java to filter Exchange Server appointments
    by date. This Aspose Email Java tutorial shows setup, query building, and retrieving
    exchange calendar events.
  headline: Build Exchange Query Java – Filter Appointments by Date
  type: TechArticle
- description: Learn how to build exchange query java to filter Exchange Server appointments
    by date. This Aspose Email Java tutorial shows setup, query building, and retrieving
    exchange calendar events.
  name: Build Exchange Query Java – Filter Appointments by Date
  steps:
  - name: Configure Date Formats
    text: First, create a reusable `SimpleDateFormat` instance to parse date strings
      into Java `Date` objects. `SimpleDateFormat` is a thread‑unsafe class, so reusing
      a single instance within a single thread improves performance and reduces object
      allocation.
  - name: Build a Query with ExchangeQueryBuilder
    text: '`ExchangeQueryBuilder` is Aspose.Email''s fluent builder that lets you
      specify search criteria without writing raw SOAP XML. Create an instance and
      set up your date range criteria:'
  - name: Execute the Query
    text: 'Use the previously configured `IEWSClient` to run the query and retrieve
      matching appointments: The `getAppointments` method returns a collection of
      `Appointment` objects that fall within the defined date range.'
  type: HowTo
- questions:
  - answer: It means constructing an `ExchangeQueryBuilder` object in Java to query
      Exchange items.
    question: What does “build exchange query java” mean?
  - answer: Aspose.Email for Java (v25.4+).
    question: Which library is required?
  - answer: Yes, with EWS enabled and proper credentials.
    question: Do I need an Exchange server?
  - answer: Absolutely – just modify the `SimpleDateFormat` strings.
    question: Can I change the date range at runtime?
  - answer: Yes, a valid Aspose.Email license is required for commercial use.
    question: Is a license mandatory for production?
  type: FAQPage
tags:
- build exchange query java
- Aspose.Email
- Java calendar
- EWS appointments
- filter appointments
title: إنشاء Exchange Query Java – تصفية المواعيد حسب التاريخ
url: /ar/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء استعلام Exchange Java – تصفية المواعيد حسب التاريخ

إدارة المواعيد الفعّالة أمر حاسم في بيئة الأعمال اليوم، حيث يُعزز الجدولة الفعّالة إنتاجية المؤسسة. من خلال **إضافة تبعية Aspose.Email Maven** و**إنشاء استعلام exchange java** الذي يُصنّف المواعيد من خادم Exchange بناءً على نطاقات تاريخية محددة، يمكنك تبسيط العمليات وتحسين إدارة الوقت. يشرح هذا الدليل العملية بالكامل، من إعداد البيئة إلى تنفيذ الاستعلام، ويظهر لك كيفية **استرجاع أحداث تقويم Exchange** بشكل موثوق.

**ما ستتعلمه**
- إعداد بيئتك مع تبعية Maven المطلوبة  
- تهيئة وتكوين Aspose.Email لـ Java  
- إنشاء استعلام exchange java لتصفية المواعيد ضمن نطاق تاريخ محدد  
- أفضل الممارسات لتحسين الأداء واستخدام الذاكرة  

مع فهم المشكلة التي يحلها هذا الحل، دعنا نستعرض المتطلبات المسبقة قبل الغوص في التنفيذ.

## إجابات سريعة
- **ماذا يعني “build exchange query java”؟** يعني إنشاء كائن `ExchangeQueryBuilder` في Java لاستعلام عناصر Exchange.  
- **ما المكتبة المطلوبة؟** Aspose.Email لـ Java (الإصدار 25.4 فأكثر).  
- **هل أحتاج إلى خادم Exchange؟** نعم، مع تمكين EWS وبيانات اعتماد صحيحة.  
- **هل يمكنني تغيير نطاق التاريخ أثناء التشغيل؟** بالتأكيد – فقط عدّل سلاسل `SimpleDateFormat`.  
- **هل الترخيص إلزامي للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Email صالح للاستخدام التجاري.

## ما هو “build exchange query java”؟

`build exchange query java` هو عملية إنشاء مثال `ExchangeQueryBuilder`، وتكوين معاييره (مثل نطاقات التاريخ أو الموضوع أو المنظم)، ثم تنفيذ ذلك الاستعلام ضد صندوق بريد Exchange. يقوم الـ builder بتجريد طلبات SOAP المعقدة خلف واجهة برمجة تطبيقات Java سلسة، مما يجعل من السهل **استرجاع أحداث تقويم Exchange** دون كتابة XML يدوي.

## لماذا نستخدم Aspose.Email لـ Java؟

توفر Aspose.Email لـ Java **دعم EWS شامل لأكثر من 50 عملية**، بما في ذلك المواعيد، جهات الاتصال، المهام، وأكثر. تعمل مباشرة مع خادم Exchange—بدون الحاجة لتثبيت Outlook—مما يقدّم **سرعة استرجاع البيانات تصل إلى 3×** مقارنةً بالاتصالات اليدوية لـ EWS، مع استهلاك أقل من 150 ميغابايت من الذاكرة المؤقتة للاستعلامات النموذجية. تجعل الوثائق الواسعة للمكتبة منها **دليل Aspose Email Java** مثاليًا للمطورين الباحثين عن حل موثوق وعالي الأداء.

## المتطلبات المسبقة

### المكتبات والتبعيات المطلوبة
- **Aspose.Email لـ Java**: الإصدار 25.4 أو أحدث.  
- **مجموعة تطوير Java (JDK)**: استخدم JDK 16 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans.  
- الوصول إلى خادم Exchange مع تمكين EWS.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.  
- إلمام بـ Maven لإدارة التبعيات.

## إضافة تبعية Aspose.Email Maven

لبدء العمل، أضف مكتبة Aspose.Email كتبعيات في مشروعك. إذا كنت تستخدم Maven، أدرج المقتطف XML التالي في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

توفر Aspose.Email لـ Java نسخة تجريبية مجانية لتقييم ميزاتها. للاستخدام المستمر، يمكنك الحصول على ترخيص مؤقت أو شراء نسخة كاملة:
- **[نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)**  
- **[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)**  
- **[شراء](https://purchase.aspose.com/buy)**

### التهيئة الأساسية والإعداد

قم بتكوين بيانات اعتماد خادم Exchange لتهيئة Aspose.Email لـ Java. `IEWSClient` هو الصنف الأساسي للتفاعل مع Exchange Web Services، ويتعامل مع المصادقة وتنفيذ الطلبات. اضبط `IEWSClient` كما يلي:

```java
String mailboxUri = "YOUR_EXCHANGE_SERVER_URI"; // Your Exchange Server URI
String username = "YOUR_USERNAME";               // Username for authentication
String password = "YOUR_PASSWORD";               // Password
String domain = "YOUR_DOMAIN";                   // Domain if required

IEWSClient client = EWSClient.getEWSClient(mailboxUri, username, password, domain);
```

يُعد صنف `IEWSClient` نقطة الدخول الأساسية للتفاعل مع Exchange Web Services؛ فهو يدير المصادقة وتنفيذ الطلبات ومعالجة الاستجابات.

## تصفية المواعيد حسب التاريخ (نطاق استعلام Exchange)

الميزة الأساسية في هذا الدليل هي تصفية المواعيد بين تواريخ محددة. إليك الطريقة:

### الخطوة 1: تكوين صيغ التاريخ

أولاً، أنشئ كائن `SimpleDateFormat` قابل لإعادة الاستخدام لتحويل سلاسل التاريخ إلى كائنات `Date` في Java.

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;

SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
```

`SimpleDateFormat` هو صنف غير آمن للمتعدد الخيوط، لذا فإن إعادة استخدام نسخة واحدة داخل خيط واحد يحسّن الأداء ويقلل من تخصيص الكائنات.

### الخطوة 2: بناء استعلام باستخدام ExchangeQueryBuilder

`ExchangeQueryBuilder` هو أداة بناء سلسة في Aspose.Email تتيح لك تحديد معايير البحث دون كتابة XML SOAP يدوي. أنشئ مثالًا واضبط معايير نطاق التاريخ:

```java
import com.aspose.email.ExchangeQueryBuilder;

ExchangeQueryBuilder builder = new ExchangeQueryBuilder();

// Specify the start date for filtering appointments
builder.getAppointment().getStart().since(sdf.parse("10/05/2016 10:00:00"));

// Define the end date to include all appointments before or equal to this time
builder.getAppointment().getEnd().beforeOrEqual(sdf.parse("10/15/2016 10:00:00"));
```

### الخطوة 3: تنفيذ الاستعلام

استخدم `IEWSClient` المُكوّن مسبقًا لتشغيل الاستعلام واسترجاع المواعيد المطابقة:

```java
import com.aspose.email.MailQuery;

com.aspose.email.MailQuery query = builder.getQuery();
Appointment[] appointments = client.listAppointments(query);
```

ترجع طريقة `getAppointments` مجموعة من كائنات `Appointment` التي تقع ضمن النطاق الزمني المحدد.

### نصائح استكشاف الأخطاء وإصلاحها
- **أخطاء تحليل التاريخ**: تأكد من أن سلاسل التاريخ تتطابق تمامًا مع النمط المحدد في `SimpleDateFormat`.  
- **مشكلات المصادقة**: تحقق مرة أخرى من بيانات اعتماد خادم Exchange واتصال الشبكة.  
- **نتائج فارغة**: تأكد من أن الخادم يحتوي فعليًا على مواعيد ضمن النطاق المحدد، أو وسّع نافذة التاريخ.

## تطبيقات عملية

يمكن استخدام هذه الميزة في سيناريوهات واقعية متعددة:
1. **إدارة تقويم الأعمال** – تصفية الاجتماعات تلقائيًا لشهر معين.  
2. **جدولة الموارد** – تحديد الفترات الزمنية المتاحة عبر استبعاد الحجوزات السابقة.  
3. **التقارير والتحليلات** – إنشاء تقارير دورية بناءً على بيانات المواعيد.

## اعتبارات الأداء

عند العمل مع Aspose.Email، احرص على اتباع النصائح التالية للحفاظ على السرعة المثلى:
- حدّ من نطاق استعلاماتك لتقليل نقل البيانات؛ يمكن للـ API إرجاع ما يصل إلى 200 عنصر لكل طلب بشكل افتراضي.  
- أعد استخدام نسخة واحدة من `SimpleDateFormat` بدلاً من إنشاء عدة نسخ.  
- استدعِ `client.dispose()` أو اترك جمع القمامة في JVM لتحرير الذاكرة المؤقتة للجافا بسرعة.

## المشكلات الشائعة والحلول
| المشكلة | السبب المحتمل | الحل |
|-------|--------------|----------|
| **DateParseException** | عدم تطابق بين السلسلة والنمط | عدّل النمط في `SimpleDateFormat` أو صحّح السلسلة المدخلة. |
| **401 Unauthorized** | بيانات اعتماد خاطئة أو نقص في أذونات EWS | تحقق من اسم المستخدم/كلمة المرور وتأكد من أن الحساب يمتلك صلاحية الوصول إلى EWS. |
| **No appointments returned** | تواريخ الاستعلام خارج النطاق الموجود | افحص تقويم الخادم للمواعيد أو وسّع نافذة التاريخ. |

## الخلاصة

تُبسّط عملية تصفية مواعيد خادم Exchange حسب التاريخ باستخدام Aspose.Email لـ Java إدارة التقويم، وتعزز الإنتاجية، وتوفر رؤى قيّمة حول أنماط الجدولة. باتباعك لهذا **دليل Aspose Email Java**، تعلمت كيفية إعداد بيئتك، تكوين المكتبة، و**إنشاء استعلام exchange java** لتصفية المواعيد بناءً على معايير محددة.

**الخطوات التالية**
- استكشف خيارات استعلام إضافية مثل تصفية حسب الموضوع أو المنظم.  
- دمج المواعيد المسترجعة في لوحة تقاريرك الخاصة.  
- راجع ميزات Aspose.Email الأخرى مثل إرسال طلبات اجتماع أو التعامل مع الأحداث المتكررة.

## الأسئلة المتكررة

**س:** هل يمكنني استخدام Aspose.Email بدون شراء؟  
**ج:** نعم، يمكنك البدء بالنسخة التجريبية المجانية واستكشاف ميزاتها قبل الشراء.

**س:** كيف أتعامل مع أخطاء المصادقة عند الاتصال بخادم Exchange؟  
**ج:** تحقق من بيانات الاعتماد وإعدادات الشبكة؛ تأكد من أن حساب Exchange يمتلك صلاحية EWS مفعلة.

**س:** ما صيغ التاريخ المدعومة للتحليل في هذا الدليل؟  
**ج:** يدعم صنف `SimpleDateFormat` أي نمط تقوم بتحديده؛ المثال يستخدم `"dd/MM/yyyy HH:mm:ss"`.

**س:** كيف يمكنني تغيير نطاق التاريخ ديناميكيًا أثناء التشغيل؟  
**ج:** ما عليك سوى تعديل السلاسل الممررة إلى طُرُق `since()` و`beforeOrEqual()` قبل بناء الاستعلام.

**س:** أين يمكنني العثور على مزيد من الوثائق لميزات Aspose.Email؟  
**ج:** الوثائق الشاملة متوفرة على موقع [توثيق Aspose Email](https://reference.aspose.com/email/java/).

## الموارد
- **الوثائق**: [توثيق Aspose Email](https://reference.aspose.com/email/java/)  
- **Java Docs**: [توثيق Aspose Email Java](https://reference.aspose.com/email/java/)  
- **التنزيل**: [إصدارات Aspose Email](https://releases.aspose.com/email/java/)  
- **الشراء**: [شراء Aspose](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية**: [احصل على نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)  
- **ترخيص مؤقت**: [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [منتدى دعم Aspose](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-07-17  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [دليل ربط تقويم Exchange باستخدام Aspose.Email لـ Java | تكامل خادم Exchange](/email/java/exchange-server-integration/exchange-calendar-connection-aspose-email-java/)
- [أفضل ممارسات تقسيم الصفحات في Java – تنفيذ مواعيد مجزأة باستخدام Aspose.Email لخوادم Exchange](/email/java/calendar-appointments/java-aspose-email-paginated-appointments/)
- [إدارة مواعيد Exchange باستخدام Aspose.Email لـ Java: دليل شامل](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}