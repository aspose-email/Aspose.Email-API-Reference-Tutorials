---
date: '2026-01-17'
description: تعلم كيفية تحويل MSG إلى MHT باستخدام Aspose.Email للغة Java. يغطي هذا
  الدليل خطوة بخطوة تحميل وحفظ وتخصيص القوالب لتحويل البريد الإلكتروني في الواقع.
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 'كيفية تحويل MSG إلى MHT باستخدام Aspose.Email للغة Java: دليل شامل'
url: /ar/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تحويل MSG إلى MHT باستخدام Aspose.Email للـ Java: دليل شامل

## المقدمة

تحويل **MSG إلى MHT** هو طلب شائع عندما تحتاج إلى أرشفة أو عرض رسائل Outlook بتنسيق صديق للويب. في هذا الدرس ستتعرف على كيفية جعل Aspose.Email للـ Java عملية التحويل سهلة، حيث يمكنك تحميل ملف MAPI (MSG)، تعديل المخرجات باستخدام قوالب HTML مخصصة، وحفظه كملف MHT جاهز للمتصفحات أو أنظمة الأرشفة.

**ما ستتعلمه:**
- كيفية تحميل وتحليل ملفات MSG بكفاءة.  
- كيفية تكوين `MhtSaveOptions` للحصول على مخرجات MHT مثالية.  
- كيفية تطبيق قوالب مخصصة لتحسين قابلية القراءة.  
- سيناريوهات واقعية حيث يضيف تحويل MSG إلى MHT قيمة.

لنجهز البيئة ونغوص في الكود.

## إجابات سريعة
- **ما معنى “تحويل MSG إلى MHT”؟** يحول ملفات Outlook `.msg` إلى تنسيق `.mht` (MHTML) المتوافق مع الويب.  
- **أي مكتبة تُستخدم؟** Aspose.Email للـ Java (دروس Aspose Email).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية لمدة 30 يومًا تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **إصدار Java المدعوم؟** Java 16 أو أحدث (المُصنِّف `jdk16`).  
- **حالة الاستخدام النموذجية؟** أرشفة الرسائل للامتثال أو عرضها في المتصفحات دون الحاجة إلى Outlook.

## ما هو “تحويل MSG إلى MHT”؟
عملية التحويل تقرأ رسالة Outlook الثنائية (`.msg`) وتعيد كتابة محتواها، مرفقاتها، وبيانات التعريف إلى ملف MHTML واحد قائم على HTML (`.mht`). هذا التنسيق أحادي الملف يحافظ على التخطيط الأصلي مع إمكانية عرضه في أي متصفح حديث.

## لماذا نستخدم Aspose.Email للـ Java؟
- **واجهة برمجة تطبيقات كاملة:** تدعم جميع خصائص MAPI، المرفقات، والكائنات المدمجة.  
- **بدون اعتماد على Outlook:** يعمل على أي بيئة Java من جانب الخادم.  
- **قوالب قابلة للتخصيص:** صمم مخرجات HTML لتتناسب مع علامتك التجارية أو معايير التقارير.  
- **أداء عالي:** مُحسّن للدفعات الكبيرة والمعالجة غير المتزامنة.

## المتطلبات المسبقة

- **مكتبة Aspose.Email:** الإصدار 25.4 أو أحدث (المُصنِّف `jdk16`).  
- **بيئة تطوير Java:** Maven مثبت لإدارة الاعتمادات.  
- **معرفة أساسية بـ Java:** إلمام بعمليات I/O للملفات ومشاريع Maven.

## إعداد Aspose.Email للـ Java

لإضافة Aspose.Email إلى مشروع Maven الخاص بك، أدرج الاعتماد التالي:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص (دروس Aspose Email)

Aspose.Email هو منتج تجاري، لكن يمكنك البدء بـ **نسخة تجريبية مجانية**:

- **نسخة تجريبية مجانية:** جميع الوظائف لمدة 30 يومًا.  
- **ترخيص مؤقت:** تمديد التقييم إذا لزم الأمر.  
- **شراء:** الحصول على ترخيص دائم للاستخدام في الإنتاج.

### التهيئة الأساسية

بعد إضافة اعتماد Maven، قم بتهيئة المكتبة في كود Java الخاص بك:

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## كيفية تحويل MSG إلى MHT باستخدام Aspose.Email للـ Java

### تحميل ملف MSG

**الخطوة 1 – استيراد الفئة المطلوبة**

```java
import com.aspose.email.MapiMessage;
```

**الخطوة 2 – تحميل الرسالة من القرص**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

طريقة `MapiMessage.fromFile()` تقرأ ملف `.msg` وتُنشئ كائن `MapiMessage` يمكن التلاعب به.

### تكوين خيارات حفظ MHT

**الخطوة 1 – استيراد فئات خيارات الحفظ**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**الخطوة 2 – إعداد الخيارات**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` يضمن تضمين الحقول الخاصة بالمهمة، بينما `WriteHeader` يضيف رؤوس البريد الإلكتروني القياسية إلى مخرجات MHT.

### تعريف قوالب HTML مخصصة (اختياري)

**الخطوة 1 – استيراد تعداد القالب**

```java
import com.aspose.email.MhtTemplateName;
```

**الخطوة 2 – تخصيص القوالب**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

تتيح لك هذه القوالب التحكم في كيفية ظهور كل خاصية مهمة في ملف MHT النهائي، مما يجعل المخرجات أوضح للمستخدم النهائي.

### حفظ الرسالة كملف MHT

**الخطوة 1 – تحديد دليل الإخراج**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**الخطوة 2 – تنفيذ عملية الحفظ**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

طريقة `save` تكتب ملف MHT المخصص إلى القرص. تأكد من صحة مسار `outputDir` قبل تشغيل الكود.

## التطبيقات العملية (لماذا تحويل MSG إلى MHT؟)

- **الأرشفة:** تخزين الرسائل في تنسيق محمول واحد يمكن للمتصفحات عرضه دون الحاجة إلى Outlook.  
- **الهجرة:** نقل أرشيفات Outlook القديمة إلى منصات بريد إلكتروني قائمة على الويب.  
- **التقارير والتحليلات:** تحليل ملفات MHT باستخدام محللات HTML لاستخراج البيانات واستخدامها في ذكاء الأعمال.  
- **الامتثال القانوني:** الحفاظ على محتوى الرسالة الأصلي وبيانات التعريف في تنسيق يصعب التلاعب به.

## اعتبارات الأداء

- **معالجة الدفعات:** عند التعامل مع آلاف ملفات MSG، قم بمعالجتها على دفعات لتجنب ارتفاع استهلاك الذاكرة.  
- **التنفيذ غير المتزامن:** استفد من `CompletableFuture` أو خدمات التنفيذ في Java لتحويل الملفات بشكل متوازي.  
- **تنظيف الموارد:** أغلق التدفقات صراحةً إذا فتحت أي تدفقات مخصصة بخلاف API الخاصة بـ Aspose.

## المشكلات الشائعة & استكشاف الأخطاء

| العَرَض | السبب المحتمل | الحل |
|---------|---------------|-----|
| **NullPointerException على `msg.save`** | دليل الإخراج غير موجود | أنشئ الدليل أو استخدم `Files.createDirectories(Paths.get(outputDir));` |
| **الملفات المرفقة مفقودة في MHT** | `MhtSaveOptions` غير مُضبط لتضمين الموارد | استخدم `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **تنسيق التاريخ غير صحيح** | إعدادات اللغة مختلفة | قم بتعديل `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## الأسئلة المتكررة

**س: ما الفرق بين MSG و MHT؟**  
ج: MSG هو تنسيق ثنائي مملوك لـ Outlook يخزن البريد الإلكتروني، المرفقات، وبيانات التعريف. MHT (MHTML) هو تنسيق واحد قائم على HTML يجمع جسم البريد، الصور، وCSS، مما يجعله قابلاً للعرض في أي متصفح.

**س: هل يمكنني تحويل عناصر MAPI أخرى مثل المواعيد أو جهات الاتصال؟**  
ج: نعم. يدعم Aspose.Email تحويل المواعيد، جهات الاتصال، والمهام إلى MHT باستخدام الفئات `Mapi*` المقابلة وتعديل أسماء القوالب.

**س: هل أحتاج إلى اتصال بالإنترنت لإجراء التحويل؟**  
ج: لا. جميع المعالجة تتم محليًا في بيئة تشغيل Java؛ قد يتصل فحص الترخيص بخادم Aspose مرة واحدة فقط.

**س: هل التحويل آمن للاستخدام في بيئات متعددة الخيوط؟**  
ج: API نفسه آمن للقراءة المتزامنة. عند تحويل ملفات متعددة بشكل متوازي، أنشئ كائنات `MapiMessage` منفصلة لكل خيط.

**س: ما الحد الأقصى لحجم ملف MSG الذي يمكن لـ Aspose.Email التعامل معه؟**  
ج: يمكن للمكتبة معالجة ملفات تصل إلى عدة مئات من الميغابايت، لكن يجب مراقبة حجم heap في JVM والنظر في تدفق المرفقات الكبيرة.

## الخاتمة

أنت الآن تمتلك سير عمل كامل وجاهز للإنتاج **لتحويل MSG إلى MHT** باستخدام Aspose.Email للـ Java. من خلال الاستفادة من القوالب المخصصة، يمكنك تعديل مخرجات HTML لتتناسب مع هوية مؤسستك أو معايير التقارير، بينما تتولى المكتبة عبء تحليل تنسيق Outlook الثنائي.

**الخطوات التالية:**  
- جرب قيمًا مختلفة لـ `MhtTemplateName` لتنسيق أنواع عناصر MAPI أخرى.  
- دمج التحويل في وظيفة دفعة أو خدمة REST للمعالجة عند الطلب.  
- استكشف ميزات Aspose.Email الأخرى مثل معالجة PST، إرسال البريد، وتحليل MIME.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-17  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (المُصنِّف `jdk16`)  
**المؤلف:** Aspose