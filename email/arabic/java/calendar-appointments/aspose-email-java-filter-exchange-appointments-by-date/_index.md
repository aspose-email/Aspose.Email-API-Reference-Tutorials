---
date: '2025-12-18'
description: تعلم كيفية إنشاء استعلام Exchange بلغة Java لتصفية مواعيد خادم Exchange
  حسب التاريخ باستخدام Aspose.Email للـ Java. يغطي هذا الدليل إعداد البيئة، استرجاع
  أحداث تقويم Exchange، وأفضل الممارسات.
keywords:
- filter Exchange server appointments
- Aspose.Email for Java setup
- Exchange Web Services (EWS) appointments
title: كيفية بناء استعلام Exchange في Java لتصفية المواعيد
url: /ar/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية بناء استعلام Exchange Java لتصفية المواعيد

إدارة المواعيد الفعّالة أمر حاسم في بيئة الأعمال اليوم، حيث يعزز الجدولة الفعّالة إنتاجية المؤسسة. من خلال **بناء استعلام Exchange Java** الذي يصفِّي المواعيد من خادم Exchange بناءً على نطاقات تاريخية محددة باستخدام Aspose.Email for Java، يمكنك تبسيط العمليات وتحسين إدارة الوقت. يقدّم هذا الدليل خطوة بخطوة العملية بالكامل، من إعداد البيئة إلى تنفيذ الاستعلام، ويظهر لك كيفية **استرجاع أحداث تقويم Exchange** بشكل موثوق.

**ما ستتعلمه**
- إعداد بيئتك مع الاعتماديات اللازمة  
- تهيئة وتكوين Aspose.Email for Java  
- بناء استعلام Exchange Java لتصفية المواعيد ضمن نطاق تاريخ محدد  
- أفضل الممارسات لتحسين الأداء واستخدام الذاكرة  

مع فهم المشكلة التي يحلها هذا الحل، دعنا نستعرض المتطلبات المسبقة قبل الغوص في التنفيذ.

## إجابات سريعة
- **ماذا يعني “build exchange query java”؟** يشير إلى إنشاء كائن `ExchangeQueryBuilder` في Java لاستعلام عناصر Exchange.  
- **ما المكتبة المطلوبة؟** Aspose.Email for Java (الإصدار 25.4 فما فوق).  
- **هل أحتاج إلى خادم Exchange؟** نعم، مع تمكين EWS وإدخال بيانات الاعتماد الصحيحة.  
- **هل يمكن تغيير نطاق التاريخ أثناء التشغيل؟** بالتأكيد – فقط عدّل سلاسل `SimpleDateFormat`.  
- **هل الترخيص إلزامي للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Email صالح للاستخدام التجاري.

## المتطلبات المسبقة

للتبع مع هذا الدليل، تأكد من توفر الأدوات والمعرفة التالية:

### المكتبات والاعتماديات المطلوبة
- **Aspose.Email for Java**: الإصدار 25.4 أو أحدث.  
- **مجموعة تطوير جافا (JDK)**: استخدم JDK 16 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans.  
- الوصول إلى خادم Exchange مع تمكين EWS.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.  
- إلمام بـ Maven لإدارة الاعتماديات.

## إعداد Aspose.Email for Java

لبدء العمل، أضف مكتبة Aspose.Email كاعتماد في مشروعك. إذا كنت تستخدم Maven، أدرج المقتطف XML التالي في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

توفر Aspose.Email for Java نسخة تجريبية مجانية لتقييم ميزاتها. للاستخدام المستمر، يمكنك الحصول على ترخيص مؤقت أو شراء نسخة كاملة:
- **نسخة تجريبية**: متاحة عبر صفحة [Aspose Email Download](https://releases.aspose.com/email/java/).  
- **ترخيص مؤقت**: احصل عليه من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).  
- **شراء**: للاستخدام طويل الأمد، اشترِ ترخيصًا عبر موقع [Purchase Aspose](https://purchase.aspose.com/buy).

### التهيئة الأساسية والإعداد

قم بتكوين بيانات اعتماد خادم Exchange لتهيئة Aspose.Email for Java. اضبط `IEWSClient` كما يلي:

```java
String mailboxUri = "YOUR_EXCHANGE_SERVER_URI"; // Your Exchange Server URI
String username = "YOUR_USERNAME";               // Username for authentication
String password = "YOUR_PASSWORD";               // Password
String domain = "YOUR_DOMAIN";                   // Domain if required

IEWSClient client = EWSClient.getEWSClient(mailboxUri, username, password, domain);
```

هذا يُنشئ اتصالًا بخادم Exchange الخاص بك باستخدام مكتبة Aspose.Email.

## ما هو “build exchange query java”؟

عبارة **build exchange query java** تصف عملية إنشاء مثيل `ExchangeQueryBuilder`، وتكوين معاييره (مثل نطاقات التاريخ أو الموضوع أو المنظم)، ثم تنفيذ هذا الاستعلام ضد صندوق بريد Exchange. يقوم الـ builder ب抽象 الطلبات المعقدة لـ SOAP خلف واجهة برمجة تطبيقات Java سلسة، مما يجعل من السهل **استرجاع أحداث تقويم Exchange** دون كتابة XML يدوي.

## لماذا نستخدم Aspose.Email for Java؟

- **دعم شامل لـ EWS** – يتعامل مع المواعيد، جهات الاتصال، المهام، وأكثر.  
- **لا حاجة إلى Outlook** – يعمل مباشرة مع خادم Exchange.  
- **أداء عالي** – استخدام فعال للشبكة وإدارة ذكية للذاكرة.  
- **توثيق غني** – أمثلة واسعة تساعدك على البدء بسرعة، مما يجعل هذا **aspose email java tutorial** مثالًا ممتازًا.

## دليل التنفيذ

### تصفية المواعيد حسب التاريخ

الميزة الأساسية في هذا الدليل هي تصفية المواعيد بين تواريخ محددة. إليك الطريقة:

#### الخطوة 1: تكوين صيغ التاريخ

ابدأ بإنشاء كائن `SimpleDateFormat` لتحويل سلاسل التاريخ إلى كائنات Java `Date`.

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;

SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
```

سيُستخدم هذا التنسيق لتفسير تاريخ بدء وانتهاء مواعيدك.

#### الخطوة 2: بناء استعلام باستخدام ExchangeQueryBuilder

أنشئ مثيلًا من `ExchangeQueryBuilder` واضبط معايير نطاق التاريخ:

```java
import com.aspose.email.ExchangeQueryBuilder;

ExchangeQueryBuilder builder = new ExchangeQueryBuilder();

// Specify the start date for filtering appointments
builder.getAppointment().getStart().since(sdf.parse("10/05/2016 10:00:00"));

// Define the end date to include all appointments before or equal to this time
builder.getAppointment().getEnd().beforeOrEqual(sdf.parse("10/15/2016 10:00:00"));
```

#### الخطوة 3: تنفيذ الاستعلام

استخدم كائن `IEWSClient` لتنفيذ الاستعلام واسترجاع المواعيد:

```java
import com.aspose.email.MailQuery;

com.aspose.email.MailQuery query = builder.getQuery();
Appointment[] appointments = client.listAppointments(query);
```

هذا سيسترجع جميع المواعيد ضمن نطاق التاريخ المحدد.

### نصائح استكشاف الأخطاء وإصلاحها
- **أخطاء تحليل التاريخ**: تأكد من مطابقة سلاسل التاريخ للنمط المحدد في `SimpleDateFormat`.  
- **مشكلات المصادقة**: تحقق مرة أخرى من بيانات اعتماد خادم Exchange واتصال الشبكة.  
- **نتائج فارغة**: تأكد من أن الخادم يحتوي فعليًا على مواعيد ضمن النطاق المحدد.

## تطبيقات عملية

يمكن استخدام هذه الميزة في سيناريوهات واقعية متعددة:
1. **إدارة تقويم الأعمال** – تصفية الاجتماعات تلقائيًا لشهر معين.  
2. **جدولة الموارد** – تحديد الفترات الفارغة عبر استبعاد الحجوزات السابقة.  
3. **التقارير والتحليلات** – إنشاء تقارير دورية بناءً على بيانات المواعيد.

## اعتبارات الأداء

عند العمل مع Aspose.Email، ضع في اعتبارك النصائح التالية للحفاظ على السرعة:
- قلل نطاق الاستعلام لتقليل نقل البيانات.  
- أعد استخدام كائن `SimpleDateFormat` واحد بدلاً من إنشاء عدة كائنات.  
- حرّر الكائنات غير المستخدمة لتفريغ ذاكرة Java heap.

## المشكلات الشائعة والحلول
| المشكلة | السبب المحتمل | الحل |
|-------|--------------|----------|
| **DateParseException** | عدم تطابق بين السلسلة والنمط | عدّل النمط في `SimpleDateFormat` أو صحّح السلسلة المدخلة. |
| **401 Unauthorized** | بيانات اعتماد خاطئة أو نقص في أذونات EWS | تحقق من اسم المستخدم/كلمة المرور وتأكد من أن الحساب يملك صلاحية EWS. |
| **No appointments returned** | تواريخ الاستعلام خارج النطاق الموجود | افحص تقويم الخادم للمواعيد أو وسّع نافذة التاريخ. |

## الخلاصة

تصفية مواعيد خادم Exchange حسب التاريخ باستخدام Aspose.Email for Java يبسط إدارة التقويم، يعزز الإنتاجية، ويوفر رؤى قيّمة حول أنماط الجدولة. باتباعك لهذا **aspose email java tutorial**، تعلمت كيفية إعداد بيئتك، تكوين المكتبة، و**بناء استعلام Exchange Java** لتصفية المواعيد بناءً على معايير محددة.

**الخطوات التالية**
- استكشف خيارات استعلام إضافية مثل تصفية حسب الموضوع أو المنظم.  
- دمج المواعيد المسترجعة في لوحة تقاريرك الخاصة.  
- راجع ميزات Aspose.Email الأخرى مثل إرسال طلبات اجتماع أو معالجة الأحداث المتكررة.

## قسم الأسئلة المتكررة

1. **هل يمكنني استخدام Aspose.Email دون شراء؟**  
   - نعم، يمكنك البدء بالنسخة التجريبية واستكشاف ميزاتها قبل الشراء.  
2. **كيف أتعامل مع أخطاء المصادقة عند الاتصال بخادم Exchange؟**  
   - تحقق من بيانات الاعتماد وإعدادات الشبكة؛ تأكد من أن الخادم يسمح بالوصول عبر EWS.  
3. **ما الصيغ المدعومة لتحليل التاريخ في هذه الميزة؟**  
   - تدعم فئة `SimpleDateFormat` أنماطًا متعددة؛ يجب تحديدها بدقة (مثال: `"dd/MM/yyyy HH:mm:ss"`).  
4. **كيف يمكنني تصفية المواعيد بنطاق زمني مختلف بشكل ديناميكي؟**  
   - عدّل سلاسل التاريخ الممررة إلى طريقتي `since()` و `beforeOrEqual()` حسب الحاجة.  
5. **هل هناك توثيق للوظائف الإضافية في Aspose.Email؟**  
   - الوثائق الشاملة متوفرة على موقع [Aspose Email Documentation](https://reference.aspose.com/email/java/).

## الموارد
- **التوثيق**: [Aspose Email Java Docs](https://reference.aspose.com/email/java/)  
- **التنزيل**: [Aspose Email Releases](https://releases.aspose.com/email/java/)  
- **الشراء**: [Buy Aspose Email](https://purchase.aspose.com/buy)  
- **النسخة التجريبية**: [Get a Free Trial](https://releases.aspose.com/email/java/)  
- **الترخيص المؤقت**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [Aspose Forum Support](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}