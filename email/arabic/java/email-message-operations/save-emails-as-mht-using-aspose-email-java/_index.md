---
date: '2026-03-02'
description: تعلم كيفية استخدام Maven Aspose.Email للغة Java لحفظ الرسائل الإلكترونية
  كملفات MHT. يغطي هذا الدليل خطوة بخطوة الإعداد والقوالب المخصصة وتحويل البريد الإلكتروني
  إلى MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email لجافا: حفظ الرسائل الإلكترونية كملفات MHT'
url: /ar/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email for Java: كيفية حفظ رسائل البريد الإلكتروني كملفات MHT

## المقدمة

إدارة بيانات البريد الإلكتروني بكفاءة يمكن أن تكون صعبة، خاصة عندما يتعلق الأمر بالمشاركة والأرشفة. في هذا الدليل سنوضح لك **كيفية حفظ ملفات MHT** باستخدام **Maven Aspose.Email for Java**، بحيث يمكنك تحويل رسائل البريد إلى MHT باستخدام قوالب مخصصة والحفاظ على أحداث التقويم كما هي. ستحصل على حل جاهز للتنفيذ يعمل في أي بيئة Java 16+.

## أسئلة سريعة
- **ما المكتبة التي أحتاجها؟** Maven Aspose.Email for Java (v25.4+).  
- **ما الصيغة التي يتم إنتاجها؟** ملف MHT (MHTML) يجمع بين HTML، الصور، وبيانات التقويم.  
- **هل يمكنني تخصيص الرأس؟** نعم – استخدم `MhtFormatOptions` وسلاسل القوالب.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص الدائم مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** JDK 16 أو أحدث.

## ما هو Maven Aspose.Email for Java؟
Maven Aspose.Email for Java هو API قوي يتيح لك إنشاء، قراءة، تحويل، ومعالجة رسائل البريد الإلكتروني مباشرةً من كود Java. يدعم مجموعة واسعة من الصيغ — بما في ذلك MSG وEML وMHT — مما يجعله مثالياً لمهام **تحويل بريد Java**.

## لماذا تحويل رسائل البريد إلى MHT؟
- **صديق للويب**: ملفات MHT تُعرض في المتصفحات دون موارد خارجية.  
- **ثبات الأرشفة**: جميع الموارد مدمجة، مما يحافظ على المظهر الأصلي.  
- **دعم التقويم**: يمكنك عرض الأحداث المتكررة باستخدام قوالب مخصصة.  

## المتطلبات المسبقة
- **Aspose.Email for Java** (حزمة Maven `com.aspose:aspose-email:25.4` مع المصنف `jdk16`).  
- **Maven** مثبت ومُكوَّن على جهازك.  
- **JDK 16+** (المكتبة تستهدف Java 16).  
- معرفة أساسية بـ Java (معالجة الملفات، تبعيات Maven).

## إعداد Aspose.Email for Java

### تبعية Maven

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

تقدم Aspose نسخة تجريبية مجانية لاستكشاف إمكانياتها، بالإضافة إلى خيارات لشراء ترخيص أو الحصول على ترخيص مؤقت.

1. **نسخة تجريبية مجانية**: قم بالتنزيل من [Releases](https://releases.aspose.com/email/java/) واستكشف الميزات دون قيود.  
2. **ترخيص مؤقت**: احصل على نسخة كاملة الوظائف بطلبها عبر [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **شراء**: فكر في الشراء إذا كان Aspose.Email يلبي احتياجات مشروعك على المدى الطويل.

### التهيئة الأساسية

بعد التثبيت، قم بتهيئة المكتبة في تطبيق Java الخاص بك:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

مع إكمال هذه الخطوات، أنت جاهز لاستخدام ميزات Aspose.Email لمعالجة البريد الإلكتروني بكفاءة.

## دليل التنفيذ

### الميزة 1: تحميل MailMessage

#### نظرة عامة
تحميل رسالة بريد إلكتروني هو الخطوة الأولى في معالجتها وحفظها كملف MHT. هنا نوضح كيفية تحميل ملف `.msg` باستخدام `MailMessage`.

#### خطوة بخطوة

**استيراد الفئات المطلوبة**

```java
import com.aspose.email.MailMessage;
```

**تحميل البريد من ملف**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

هذا المقتطف يحمل رسالة بريد إلكتروني موجودة في الدليل المحدد.

### الميزة 2: تكوين MhtSaveOptions

#### نظرة عامة
تكوين `MhtSaveOptions` أمر حاسم لتحديد كيفية حفظ بريدك كملف MHT، بما في ذلك تنسيق مخصص لأحداث التقويم.

#### خطوة بخطوة

**استيراد الفئات المطلوبة**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**تعيين خيارات الحفظ والقوالب**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

هذا التكوين يضبط رؤوس البريد وعرض أحداث التقويم في مخرجات MHT.

### الميزة 3: حفظ MailMessage كملف MHT

#### نظرة عامة
الخطوة الأخيرة هي حفظ `MailMessage` المكوَّن كملف MHT باستخدام الخيارات المحددة.

#### خطوة بخطوة

**استيراد الفئات المطلوبة**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**حفظ رسالة البريد**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

هذا الأمر يكتب البريد إلى ملف MHT، جاهز للمشاركة أو الأرشفة.

## التطبيقات العملية
- **أرشفة البريد**: تحويل وتخزين رسائل البريد المهمة بصيغة صديقة للويب.  
- **توثيق قانوني**: استخدام ملفات MHT كجزء من الأدلة القانونية حيث تحتاج تفاصيل البريد إلى الحفظ.  
- **مشاركة عبر المنصات**: مشاركة رسائل البريد عبر المنصات دون مشاكل توافق.  

دمجها مع أنظمة أخرى، مثل CRM أو أدوات إدارة المشاريع، يمكن أن يعزز التعاون عن طريق تضمين بيانات البريد الحيوية مباشرةً في سير العمل.

## اعتبارات الأداء
لضمان الأداء الأمثل:
- إدارة استخدام الذاكرة بفعالية عند معالجة دفعات كبيرة من الرسائل.  
- تحسين عمليات إدخال/إخراج الملفات لتجنب الاختناقات أثناء عملية الحفظ.  

اتباع أفضل ممارسات إدارة الذاكرة في Java سيحافظ على استجابة تطبيقك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **NullPointerException على `msg.save`** | مسار الإخراج غير صحيح | تحقق من أن `YOUR_OUTPUT_DIRECTORY` موجود وقابل للكتابة. |
| **الصور مفقودة في MHT** | `MhtFormatOptions` غير مضبوطة لتضمين الموارد | أضف `MhtFormatOptions.EmbedResources` إلى علم الخيارات. |
| **أحداث التقويم غير معروضة** | علامة `RenderCalendarEvent` مفقودة | تأكد من `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## الأسئلة المتكررة

**س: كيف يمكنني التعامل مع المرفقات عند حفظ رسائل البريد كملفات MHT؟**  
ج: تأكد من أن `MhtSaveOptions` مُكوَّنة لتشمل منطق معالجة المرفقات. المكتبة تدعم تضمين المرفقات في ملف MHT.

**س: هل يمكنني تخصيص رؤوس البريد في ملف MHT الناتج؟**  
ج: نعم، استخدم `MhtFormatOptions.WriteHeader` وعرّف قوالب مخصصة لمختلف حقول الرأس كما هو موضح في الدرس.

**س: ما هي متطلبات النظام لاستخدام Aspose.Email Java؟**  
ج: يلزم وجود JDK 16 أو أعلى. المكتبة تعمل بسلاسة مع معظم بيئات التطوير المتكاملة الحديثة التي تدعم مشاريع Maven.

**س: هل يمكن حفظ أجزاء محددة فقط من رسالة البريد؟**  
ج: على الرغم من أن صيغة MHT عادةً ما تشمل الرسائل بالكامل، يمكنك استخدام خصائص `MailMessage` لمعالجة وتضمين المحتوى بشكل انتقائي.

**س: كيف يمكنني استكشاف مشاكل تحميل أو حفظ البريد؟**  
ج: تحقق من صحة مسارات الملفات، تأكد من إعداد المكتبة بشكل صحيح في مشروعك، وراجع [منتدى الدعم](https://forum.aspose.com/c/email/10) الخاص بـ Aspose.Email للحصول على المساعدة.

**س: هل تدعم المكتبة تحويل صيغ أخرى (EML, MSG) إلى MHT؟**  
ج: بالتأكيد. يمكن لـ `MailMessage.load` قراءة EML وMSG وصيغ أخرى، ثم يمكنك حفظها كملفات MHT باستخدام نفس الخيارات.

## الموارد
- **الوثائق**: للحصول على تفاصيل أعمق حول جميع الوظائف، زر [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **التنزيل**: ابدأ النسخة التجريبية المجانية بتحميلها من [Releases](https://releases.aspose.com/email/java/).  
- **الشراء**: استكشف خيارات الشراء في [Official Purchase Page](https://purchase.aspose.com/buy) للاستخدام طويل الأمد.  
- **النسخة التجريبية والترخيص المؤقت**: احصل على جميع الميزات خلال النسخة التجريبية أو احصل على ترخيص مؤقت عبر الروابط التالية:
  - [Free Trial](https://releases.aspose.com/email/java/)
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

استكشف، نفّذ، وحوّل طريقة معالجة بريدك باستخدام Aspose.Email for Java اليوم!

---

**آخر تحديث:** 2026-03-02  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
