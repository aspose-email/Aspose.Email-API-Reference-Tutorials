---
date: '2026-02-27'
description: تعلم كيفية تحميل ملفات MSG وتحويلها إلى MHTML باستخدام Aspose.Email للغة
  Java، بما في ذلك إعدادات المنطقة الزمنية المخصصة ونصائح معالجة البريد الإلكتروني
  دفعةً.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: كيفية تحميل ملف MSG وحفظه كملف MHTML باستخدام Aspose.Email للـ Java
url: /ar/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تحميل MSG وحفظه كـ MHTML باستخدام Aspose.Email للـ Java

## المقدمة

إذا كنت بحاجة إلى **how to load msg** ملفات، وضبط الطوابع الزمنية الخاصة بها، ثم **convert msg to mhtml**، فأنت في المكان الصحيح. في هذا الدرس سنستعرض تحميل بريد إلكتروني بامتداد `.msg`، تطبيق إزاحة منطقة زمنية مخصصة، وحفظ النتيجة كأرشيف MHTML — كل ذلك باستخدام Aspose.Email للـ Java. سواءً كنت تتعامل مع رسالة واحدة أو **batch email processing**، ستوفر لك هذه الخطوات أساسًا قويًا.

**ما ستتعلمه**
- كيفية تحميل `MailMessage` من ملف `.msg`.
- كيفية تعيين منطقة زمنية مخصصة وتاريخ الحالي.
- كيفية حفظ الرسالة كـ MHTML مع تنسيق دقيق.
- نصائح لتوسيع النهج إلى سيناريوهات الدفعات.

هل أنت مستعد لتعزيز سير عمل البريد الإلكتروني الخاص بك؟ لنجهّز البيئة أولاً.

## إجابات سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Email للـ Java.
- **هل يمكنني تحميل MSG وتصديره إلى MHTML في خطوة واحدة؟** لا، تقوم بالتحميل، ثم الضبط، ثم الحفظ.
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Email.
- **هل يتم دعم معالجة المنطقة الزمنية؟** نعم، عبر `setTimeZoneOffset`.
- **هل يمكن استخدام هذا في معالجة الدفعات؟** بالتأكيد – غلف الخطوات داخل حلقة.

## المتطلبات المسبقة

### المكتبات والاعتمادات المطلوبة
- **Aspose.Email للـ Java** الإصدار 25.4 (مصنف jdk16)
- معرفة أساسية بـ Java.
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.

### متطلبات إعداد البيئة
- JDK 16 أو أحدث مثبت.
- Maven لإدارة الاعتمادات.

## إعداد Aspose.Email للـ Java

لإضافة المكتبة إلى مشروع Maven، أدرج الاعتماد التالي:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### خطوات الحصول على الترخيص

ابدأ بـ **نسخة تجريبية مجانية** أو احصل على **ترخيص مؤقت** لتقييم كامل قدرات المكتبة دون قيود. للاستخدام طويل الأمد، فكر في شراء ترخيص:

- [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [شراء ترخيص](https://purchase.aspose.com/buy)

### التهيئة الأساسية

بعد إضافة الاعتماد، قم بتهيئة الترخيص في كود Java الخاص بك:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## دليل التنفيذ

سنقسم التنفيذ إلى ثلاث ميزات واضحة.

### الميزة 1: تحميل MailMessage من ملف

#### نظرة عامة
تحميل ملف `.msg` يمنحك وصولًا برمجيًا كاملًا إلى محتوى البريد، المرفقات، والبيانات الوصفية.

#### خطوة بخطوة

**استيراد الفئات المطلوبة**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**تحميل البريد الإلكتروني**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` يتيح لك التحكم في طريقة تفسير ملف MSG؛ الإعدادات الافتراضية تعمل لمعظم السيناريوهات.

### الميزة 2: ضبط التاريخ الحالي وإزاحة المنطقة الزمنية المخصصة

#### نظرة عامة
الطوابع الزمنية الدقيقة ضرورية عندما تتعامل مع مستخدمين في مناطق جغرافية مختلفة.

**ضبط التاريخ الحالي**

```java
import java.util.Date;

msg.setDate(new Date());
```

**تطبيق إزاحة منطقة زمنية مخصصة (مثال: UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

الإزاحة تُعبّر بالميليثانية، لذا يمكنك أيضًا تمرير قيم سلبية للمناطق الواقعة غرب UTC.

### الميزة 3: حفظ MailMessage كملف MHTML

#### نظرة عامة
MHTML يجمع محتوى HTML والموارد المدمجة في ملف واحد، وهو مثالي للأرشفة أو المشاركة.

**تهيئة خيارات الحفظ**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**حفظ البريد الإلكتروني**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

ملف `.mhtml` الناتج يحتفظ بالتنسيق الأصلي، الصور، والمرفقات.

## لماذا تحويل MSG إلى MHTML؟

تحويل ملفات MSG إلى MHTML يمنحك تمثيلًا صديقًا للويب، ملفًا واحدًا يمكن فتحه في أي متصفح حديث. هذا مفيد خصوصًا لـ:

- **الأرشفة القانونية** حيث يلزم نسخة بصرية دقيقة.
- **المشاركة عبر المنصات** دون الحاجة إلى Outlook.
- **دمج الرسائل الإلكترونية** في صفحات الويب أو الوثائق.

## نصائح معالجة البريد الإلكتروني على دفعات

إذا كنت بحاجة إلى **batch email processing**، غلف خطوات التحميل، ضبط المنطقة الزمنية، والحفظ داخل حلقة تتنقل عبر دليل يحتوي على ملفات `.msg`. تذكر أن:

1. أعد استخدام كائن `License` واحد لتجنب الحمل الزائد.
2. حرّر الموارد بعد كل تكرار (`msg.dispose()` إذا كان ذلك مناسبًا).
3. سجّل أي فشل في ملف منفصل للمراجعة لاحقًا.

## تطبيقات عملية

1. **أرشفة البريد الإلكتروني:** حفظ الاتصالات بصيغة محمولة للامتثال.
2. **جدولة عالمية:** ضبط الطوابع الزمنية إلى منطقة زمنية موحدة قبل إرسال الإشعارات.
3. **تكامل CRM:** استيراد الرسائل المؤرشفة تلقائيًا إلى نظام CRM كمرفقات MHTML.

## اعتبارات الأداء

- **إدارة الذاكرة:** عالج الدفعات الكبيرة على أجزاء للحفاظ على استهلاك الذاكرة منخفضًا.
- **تحسين I/O:** استخدم تدفقات مخزنة إذا كنت تقرأ/تكتب العديد من الملفات.
- **التنفيذ المتوازي:** فكر في `ForkJoinPool` في Java للمعالجة المتوازية، لكن تأكد من أمان الخيوط لكائنات Aspose.

## الخلاصة

أنت الآن تعرف **how to load msg** ملفات، تطبيق إزاحات منطقة زمنية مخصصة، و**convert msg to mhtml** باستخدام Aspose.Email للـ Java. يمكن توسيع هذه التقنيات للتعامل مع مهام **batch email processing**، مما يمنحك حلًا قويًا لأرشفة البريد، الهجرة، والأتمتة.

**الخطوات التالية**  
استكشف ميزات إضافية في Aspose.Email مثل معالجة المرفقات، استخراج عناصر التقويم، أو إرسال عبر SMTP بزيارة [التوثيق الرسمي](https://reference.aspose.com/email/java/).

## الأسئلة المتكررة

**س: هل يمكنني تحميل رسائل من صيغ غير .msg؟**  
ج: نعم، يدعم Aspose.Email صيغ EML، MSG، MHT، والعديد من الصيغ الأخرى.

**س: كيف يمكنني التعامل مع ملفات بريد إلكتروني ضخمة جدًا بكفاءة؟**  
ج: استخدم واجهات البرمجة المتدفقة (streaming APIs) التي توفرها Aspose.Email لقراءة/كتابة البيانات على دفعات، مما يقلل من الضغط على الذاكرة.

**س: هل يمكن تعديل المرفقات داخل MailMessage؟**  
ج: بالتأكيد. يمكنك إضافة، إزالة، أو استبدال المرفقات عبر مجموعة `MailMessage.getAttachments()`.

**س: ماذا لو كانت إزاحة المنطقة الزمنية سلبية (خلف UTC)؟**  
ج: مرّر قيمة ميليثانية سلبية إلى `setTimeZoneOffset`، مثال: `-3 * 60 * 60 * 1000` لـ UTC‑3.

**س: هل يمكنني استخدام Aspose.Email في مشاريع تجارية؟**  
ج: نعم، بشرط امتلاك ترخيص تجاري صالح.

**س: كيف أعالج آلاف ملفات MSG دون نفاد الذاكرة؟**  
ج: عالج الملفات على دفعات، حرّر كل `MailMessage` بعد الحفظ، وفكّر في نمط `try‑with‑resources` في Java لتنظيف تلقائي.

---

**Last Updated:** 2026-02-27  
**Tested With:** Aspose.Email للـ Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

## الموارد
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}