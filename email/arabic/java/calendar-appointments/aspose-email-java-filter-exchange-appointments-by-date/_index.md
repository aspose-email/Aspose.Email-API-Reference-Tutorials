---
date: '2026-02-17'
description: تعلم كيفية إضافة تبعية Aspose.Email لـ Maven وبناء استعلام Exchange بلغة
  Java لتصفية مواعيد خادم Exchange حسب التاريخ. يغطي هذا الدرس التعليمي لـ Aspose
  Email بلغة Java الإعداد، واسترجاع أحداث تقويم Exchange، وأفضل الممارسات.
keywords:
- filter Exchange server appointments
- Aspose.Email for Java setup
- Exchange Web Services (EWS) appointments
title: اعتماد Aspose Email في Maven – بناء استعلام Exchange بلغة Java لتصفية المواعيد
url: /ar/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/
weight: 1
---

 content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Email Maven Dependency – بناء استعلام Exchange Java لتصفية المواعيد

إدارة المواعيد الفعّالة أمر حاسم في بيئة الأعمال اليوم، حيث تعزز الجدولة الفعّالة إنتاجية المؤسسة. من خلال **إضافة Aspose.Email Maven dependency** و**بناء استعلام exchange Java** الذي يصفِّي المواعيد من خادم Exchange بناءً على نطاقات تاريخية محددة، يمكنك تبسيط العمليات وتحسين إدارة الوقت. يوجهك هذا البرنامج التعليمي خلال العملية بالكامل، من إعداد البيئة إلى تنفيذ الاستعلام، ويظهر لك كيفية **استرجاع أحداث تقويم Exchange** بشكل موثوق.

**ما ستتعلمه**
- إعداد بيئتك مع الاعتماد المطلوب في Maven  
- تهيئة وتكوين Aspose.Email لـ Java  
- بناء استعلام exchange Java لتصفية المواعيد ضمن نطاق تاريخ محدد  
- أفضل الممارسات لتحسين الأداء واستخدام الذاكرة  

مع فهم المشكلة التي يحلها هذا الحل، دعنا نستعرض المتطلبات المسبقة قبل الغوص في التنفيذ.

## إجابات سريعة
- **ماذا يعني “build exchange query java”؟** يشير إلى إنشاء كائن `ExchangeQueryBuilder` في Java لاستعلام عناصر Exchange.  
- **أي مكتبة مطلوبة؟** Aspose.Email لـ Java (الإصدار 25.4 فما فوق).  
- **هل أحتاج إلى خادم Exchange؟** نعم، مع تمكين EWS وبيانات اعتماد صحيحة.  
- **هل يمكن تغيير نطاق التاريخ أثناء التشغيل؟** بالطبع – فقط عدّل سلاسل `SimpleDateFormat`.  
- **هل الترخيص إلزامي للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Email صالح للاستخدام التجاري.

## المتطلبات المسبقة

لمتابعة هذا البرنامج التعليمي، تأكد من توفر الأدوات والمعارف التالية:

### المكتبات والاعتمادات المطلوبة
- **Aspose.Email لـ Java**: الإصدار 25.4 أو أحدث.  
- **مجموعة تطوير جافا (JDK)**: استخدم JDK 16 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans.  
- الوصول إلى خادم Exchange مع تمكين EWS.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.  
- إلمام بـ Maven لإدارة الاعتمادات.

## إضافة Aspose.Email Maven Dependency

للبدء، أضف مكتبة Aspose.Email كاعتماد في مشروعك. إذا كنت تستخدم Maven، أدرج هذا المقتطف XML في ملف `pom.xml` الخاص بك:

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
- **نسخة تجريبية مجانية**: متاحة عبر صفحة [تحميل Aspose Email](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت**: احصل عليه من صفحة [الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).  
- **شراء**: للاستخدام طويل الأمد، اشترِ ترخيصًا عبر موقع [شراء Aspose](https://purchase.aspose.com/buy).

### التهيئة الأساسية والإعداد

قم بتكوين بيانات اعتماد خادم Exchange لتهيئة Aspose.Email لـ Java. اضبط `IEWSClient` كما يلي:

```java
String mailboxUri = "YOUR_EXCHANGE_SERVER_URI"; // Your Exchange Server URI
String username = "YOUR_USERNAME";               // Username for authentication
String password = "YOUR_PASSWORD";               // Password
String domain = "YOUR_DOMAIN";                   // Domain if required

IEWSClient client = EWSClient.getEWSClient(mailboxUri, username, password, domain);
```

هذا يُنشئ اتصالًا بخادم Exchange الخاص بك باستخدام مكتبة Aspose.Email.

## ما هو “build exchange query java”؟

عبارة **build exchange query java** تصف عملية إنشاء مثيل `ExchangeQueryBuilder`، وتكوين معاييره (مثل نطاقات التاريخ أو الموضوع أو المنظم)، ثم تنفيذ ذلك الاستعلام ضد صندوق بريد Exchange. يقوم الـ builder بتجريد طلبات SOAP المعقدة خلف واجهة برمجة تطبيقات Java سلسة، مما يجعل من السهل **استرجاع أحداث تقويم Exchange** دون كتابة XML يدوي.

## لماذا نستخدم Aspose.Email لـ Java؟

- **دعم شامل لـ EWS** – يتعامل مع المواعيد، جهات الاتصال، المهام، وأكثر.  
- **لا حاجة لـ Outlook** – يعمل مباشرة مع خادم Exchange.  
- **أداء عالي** – استخدام فعال للشبكة وإدارة ذكية للذاكرة.  
- **توثيق غني** – أمثلة واسعة تساعدك على البدء بسرعة، مما يجعل هذا **aspose email java tutorial** ممتازًا.

## تصفية المواعيد حسب التاريخ (نطاق تاريخ استعلام Exchange)

الميزة الأساسية في هذا الدرس هي تصفية المواعيد بين تواريخ محددة. إليك كيفية تحقيق ذلك:

### الخطوة 1: تكوين صيغ التاريخ

ابدأ بإعداد كائن `SimpleDateFormat` لتحويل سلاسل التاريخ إلى كائنات Java `Date`.

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;

SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
```

سيُستخدم هذا التنسيق لتفسير تاريخ البدء والانتهاء لمواعيدك.

### الخطوة 2: بناء استعلام باستخدام ExchangeQueryBuilder

أنشئ مثيلًا من `ExchangeQueryBuilder` واضبط معايير نطاق التاريخ:

```java
import com.aspose.email.ExchangeQueryBuilder;

ExchangeQueryBuilder builder = new ExchangeQueryBuilder();

// Specify the start date for filtering appointments
builder.getAppointment().getStart().since(sdf.parse("10/05/2016 10:00:00"));

// Define the end date to include all appointments before or equal to this time
builder.getAppointment().getEnd().beforeOrEqual(sdf.parse("10/15/2016 10:00:00"));
```

### الخطوة 3: تنفيذ الاستعلام

استخدم مثيل `IEWSClient` لتنفيذ الاستعلام واسترجاع المواعيد:

```java
import com.aspose.email.MailQuery;

com.aspose.email.MailQuery query = builder.getQuery();
Appointment[] appointments = client.listAppointments(query);
```

هذا يسترجع جميع المواعيد ضمن نطاق التاريخ المحدد.

### نصائح استكشاف الأخطاء وإصلاحها
- **أخطاء تحليل التاريخ**: تأكد من أن سلاسل التاريخ تتطابق مع النمط المحدد في `SimpleDateFormat`.  
- **مشكلات المصادقة**: تحقق مرة أخرى من بيانات اعتماد خادم Exchange واتصال الشبكة.  
- **نتائج فارغة**: تأكد من أن الخادم يحتوي فعليًا على مواعيد ضمن النطاق المحدد.

## تطبيقات عملية

يمكن استخدام هذه الميزة في سيناريوهات واقعية متعددة:
1. **إدارة تقويم الأعمال** – تصفية الاجتماعات تلقائيًا لشهر معين.  
2. **جدولة الموارد** – تحديد الفترات الفارغة عبر استبعاد الحجوزات السابقة.  
3. **التقارير والتحليلات** – إنشاء تقارير دورية بناءً على بيانات المواعيد.

## اعتبارات الأداء

عند العمل مع Aspose.Email، ضع في اعتبارك النصائح التالية للحفاظ على السرعة:
- قلل نطاق استعلاماتك لتقليل نقل البيانات.  
- أعد استخدام كائن `SimpleDateFormat` واحد بدلاً من إنشاء عدة كائنات.  
- حرّر الكائنات التي لم تعد بحاجة إليها لتفريغ ذاكرة Java heap.

## المشكلات الشائعة والحلول
| المشكلة | السبب المحتمل | الحل |
|-------|--------------|----------|
| **DateParseException** | عدم تطابق بين السلسلة والنمط | عدّل النمط في `SimpleDateFormat` أو صحّح السلسلة المدخلة. |
| **401 Unauthorized** | بيانات اعتماد خاطئة أو أذونات EWS مفقودة | تحقق من اسم المستخدم/كلمة المرور وتأكد من أن الحساب يمتلك صلاحية EWS. |
| **لا توجد مواعيد مسترجعة** | تواريخ الاستعلام خارج النطاق الموجود | افحص تقويم الخادم للمواعيد أو وسّع نافذة التاريخ. |

## الخلاصة

تصفية مواعيد خادم Exchange حسب التاريخ باستخدام Aspose.Email لـ Java يبسط إدارة التقويم، يعزز الإنتاجية، ويوفر رؤى قيّمة حول أنماط الجدولة. باتباعك لهذا **aspose email java tutorial**، تعلمت كيفية إعداد بيئتك، تكوين المكتبة، و**build exchange query java** لتصفية المواعيد بناءً على معايير محددة.

**الخطوات التالية**
- استكشف خيارات استعلام إضافية مثل تصفية حسب الموضوع أو المنظم.  
- دمج المواعيد المسترجعة في لوحة تقاريرك الخاصة.  
- راجع ميزات Aspose.Email الأخرى مثل إرسال طلبات اجتماع أو معالجة الأحداث المتكررة.

## الأسئلة المتكررة

**س:** هل يمكنني استخدام Aspose.Email بدون شراء؟  
**ج:** نعم، يمكنك البدء بالنسخة التجريبية المجانية واستكشاف ميزاتها قبل الشراء.

**س:** كيف أتعامل مع أخطاء المصادقة عند الاتصال بخادم Exchange؟  
**ج:** تحقق من بيانات الاعتماد وإعدادات الشبكة؛ تأكد من أن حساب Exchange يمتلك صلاحية EWS مفعلة.

**س:** ما صيغ التاريخ المدعومة للتحليل في هذا الدرس؟  
**ج:** تدعم فئة `SimpleDateFormat` أي نمط تقوم بتعريفه؛ المثال يستخدم `"dd/MM/yyyy HH:mm:ss"`.

**س:** كيف يمكنني تغيير نطاق التاريخ ديناميكيًا أثناء التشغيل؟  
**ج:** ما عليك سوى تعديل السلاسل الممررة إلى طريقتي `since()` و `beforeOrEqual()` قبل بناء الاستعلام.

**س:** أين يمكنني العثور على مزيد من الوثائق لميزات Aspose.Email؟  
**ج:** الوثائق الشاملة متاحة على موقع [توثيق Aspose Email](https://reference.aspose.com/email/java/).

## الموارد
- **التوثيق**: [Aspose Email Java Docs](https://reference.aspose.com/email/java/)  
- **التحميل**: [Aspose Email Releases](https://releases.aspose.com/email/java/)  
- **الشراء**: [Buy Aspose](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية**: [Get a Free Trial](https://releases.aspose.com/email/java/)  
- **ترخيص مؤقت**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [Aspose Forum Support](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-02-17  
**تم الاختبار مع:** Aspose.Email لـ Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}