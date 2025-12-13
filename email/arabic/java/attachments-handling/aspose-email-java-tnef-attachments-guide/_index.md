---
date: '2025-12-13'
description: تعلم كيفية تحويل ملفات msg و eml باستخدام Aspose.Email للغة Java، إضافة
  مرفق جديد، حفظ مرفق البريد الإلكتروني ومعالجة بيانات TNEF.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: تحويل MSG و EML باستخدام Aspose.Email Java – دليل مرفقات TNEF
url: /ar/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان Aspose.Email Java: معالجة TNEF ومرفقات البريد الإلكتروني  

في التطبيقات الحديثة التي تركز على البريد الإلكتروني غالبًا ما تحتاج إلى **تحويل ملفات msg إلى eml**، إضافة مرفق جديد إلى رسالة موجودة، والحفاظ على الصيغ الخاصة مثل TNEF. سواءً كنت تبني خدمة أرشفة، أداة ترحيل، أو عارض بريد من جانب العميل، فإن Aspose.Email for Java يوفر لك طريقة برمجية نظيفة للقيام بذلك. في هذا البرنامج التعليمي ستتعرف على كيفية **تحويل msg إلى eml**، إضافة مرفق جديد، حفظ مرفق البريد الإلكتروني، والعمل مع بيانات TNEF باستخدام مكتبة Aspose.Email Java.

## إجابات سريعة
- **كيف يمكنني تحويل MSG إلى EML؟** استخدم `MapiMessage` مع `MailConversionOptions` واضبط `convertAsTnef` على `true`.  
- **هل يمكنني إضافة مرفق إلى EML مفعّل بـ TNEF؟** نعم – حمّل الـ EML، استدعِ `getAttachments().addItem(...)`، ثم احفظه.  
- **ما إصدار Aspose.Email المطلوب؟** المثال يستخدم الإصدار 25.4 (JDK 16).  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم – النسخة التجريبية تعمل للتقييم، لكن الترخيص الكامل يزيل القيود.  
- **هل هناك طريقة لاكتشاف TNEF في رسالة موجودة؟** استدعِ `mail.getOriginalIsTnef()` بعد تحميل الـ EML.

## ما هو “convert msg eml”؟
تحويل ملف Microsoft Outlook MSG إلى صيغة EML القياسية يسمح بقراءة الرسالة بواسطة أي عميل بريد متوافق مع RFC‑822. كما يمنحك التحويل الفرصة للحفاظ على بيانات TNEF المشفرة أو تعديلها أثناء العملية.

## لماذا نستخدم Aspose.Email Java لهذا الهدف؟
- **دعم كامل للصيغ** – MSG، EML، MHTML، وأكثر.  
- **معالجة مدمجة لـ TNEF** – لا حاجة لمحللات طرف ثالث.  
- **واجهة برمجة تطبيقات بسيطة** – استدعاءات سطر واحد للتحميل، التحويل، والحفظ.  
- **ترخيص موثوق** – نسخة تجريبية للاختبار، ترخيص كامل للإنتاج.

## المتطلبات المسبقة
- **Aspose.Email for Java** (الإصدار 25.4، JDK 16) – راجع تبعية Maven أدناه.  
- **Maven** أو أي أداة بناء أخرى يمكنها حل حزمة Aspose.  
- معرفة أساسية بـ Java I/O ومعالجة الاستثناءات.  

## إعداد Aspose.Email for Java
أضف المكتبة إلى ملف `pom.xml` الخاص بـ Maven:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
Aspose.Email يقدم نسخة تجريبية مجانية، لكن النسخة المرخصة مطلوبة للاستخدام غير المقيد.

- **نسخة تجريبية مجانية:** حمّل ترخيصًا مؤقتًا [هنا](https://releases.aspose.com/email/java/).  
- **الشراء:** لشراء ترخيص، زر صفحة [الشراء](https://purchase.aspose.com/buy).

قم بتهيئة الترخيص في كود Java الخاص بك:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## دليل التنفيذ

### إضافة مرفق جديد إلى رسالة رئيسية تحتوي على TNEF
**كيفية إضافة مرفق:** حمّل الـ EML، أضف الملف، ثم احفظه.

#### الخطوة 1: تحميل رسالة البريد الإلكتروني الموجودة
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### الخطوة 2: إضافة المرفق الجديد
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### الخطوة 3: حفظ رسالة البريد الإلكتروني المعدلة
```java
eml.save(dataDir + "test_out.eml");
```
*نصيحة احترافية:* استخدم `try‑with‑resources` لضمان إغلاق التدفقات وتجنب `FileNotFoundException`.

### إنشاء EML مفعّل بـ TNEF من MSG
**كيفية تحويل msg إلى eml:** اضبط `convertAsTnef` على `true`.

#### الخطوة 1: تحميل ملف MSG
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### الخطوة 2: ضبط خيارات التحويل
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### الخطوة 3: التحويل والحفظ
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### الحفاظ على مرفقات TNEF عند تحميل ملفات EML
**كيفية حفظ مرفق البريد مع الحفاظ على TNEF:** استخدم `MsgLoadOptions`.

#### الخطوة 1: ضبط خيارات التحميل
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### الخطوة 2: تحميل ملف EML مع الخيارات
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### اكتشاف ما إذا كانت الرسالة تحتوي على TNEF
**كيفية التحقق من وجود TNEF:** استدعِ `getOriginalIsTnef()`.

#### الخطوة 1: تحميل ملف EML
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### الخطوة 2: اكتشاف وجود TNEF
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## تطبيقات عملية
1. **أرشفة البريد الإلكتروني:** احفظ كل مرفق—بما في ذلك المرفقات المشفرة بـ TNEF—للتدقيقات الامتثالية.  
2. **ترحيل الشركات:** حوّل ملفات MSG القديمة إلى EML لتتمكن من استيرادها إلى خوادم بريد حديثة.  
3. **دعم العملاء:** اكتشف تلقائيًا بيانات TNEF عندما يقوم المستخدمون بإعادة توجيه الرسائل بين Outlook وعملاء الويب.

## اعتبارات الأداء
- **إدارة الموارد:** غلف تدفقات الملفات بـ `try‑with‑resources` لتحرير المقابض بسرعة.  
- **المرفقات الكبيرة:** عالج الملفات الضخمة على دفعات أو بثها مباشرة لتجنب استهلاك الذاكرة العالي.  
- **المراقبة:** استخدم أدوات تحليل Java لمراقبة استهلاك الـ heap عند التعامل مع عدد كبير من المرفقات.

## الخلاصة
باتباع الخطوات أعلاه يمكنك **تحويل msg إلى eml**، إضافة مرفق جديد، حفظ مرفق البريد الإلكتروني، والعمل بثقة مع بيانات TNEF باستخدام Aspose.Email for Java. المكتبة تُجردك من التعامل منخفض المستوى مع MIME، لتتمكن من التركيز على منطق الأعمال. للمزيد من الاستكشاف، راجع الوثائق الرسمية لـ [Aspose documentation](https://reference.aspose.com/email/java/) أو جرب خيارات تحويل أخرى.

## قسم الأسئلة المتكررة
**س1: ما هو ملف TNEF؟**  
ج1: TNEF هو اختصار لـ Transport Neutral Encapsulation Format ويستخدمه Microsoft Outlook للحفاظ على تنسيق النص الغني عند إرسال رسائل كملفات مرفقة.

**س2: هل يمكنني استخدام Aspose.Email دون شراء ترخيص؟**  
ج2: نعم، يمكنك البدء بنسخة تجريبية مجانية. ومع ذلك، تفرض النسخة التجريبية بعض القيود التي قد تؤثر على الاستخدام على نطاق واسع.

**س3: هل يمكن التحويل بين جميع صيغ البريد باستخدام Aspose.Email؟**  
ج3: يدعم Aspose.Email التحويل بين معظم الصيغ الشائعة—بما في ذلك EML، MSG، وMHTML—لكن تحقق من دعم الصيغة المحددة في [الوثائق](https://reference.aspose.com/email/java/).

**س4: كيف أقوم باستكشاف أخطاء “file‑not‑found” مع Aspose.Email؟**  
ج4: تأكد من صحة مسارات الملفات التي تمررها إلى الـ API، وأن الملفات موجودة، وأن العملية التنفيذية لديها صلاحيات القراءة/الكتابة لتلك الأدلة.

**س5: ما هي أفضل طريقة للتعامل مع المرفقات الكبيرة باستخدام Aspose.Email؟**  
ج5: عالج المرفقات في تدفقات أو دفعات أصغر، واغلق التدفقات دائمًا بسرعة. هذا يقلل من ضغط الذاكرة ويمنع حدوث `OutOfMemoryError`.

## أسئلة متكررة إضافية

**س: هل يقوم Aspose.Email بحذف TNEF تلقائيًا عند التحويل إلى EML؟**  
ج: لا. بشكل افتراضي يتم الحفاظ على بيانات TNEF. يمكنك التحكم في هذا السلوك عبر `MailConversionOptions.setConvertAsTnef`.

**س: هل يمكنني سرد جميع المرفقات في رسالة تم تحميلها برمجيًا؟**  
ج: نعم—استخدم `mail.getAttachments()` التي تُعيد مجموعة يمكنك التكرار عليها.

**س: هل هناك طريقة لتحويل مجموعة من ملفات MSG إلى EML في عملية واحدة؟**  
ج: بالتأكيد. قم بالتكرار عبر الملفات، نفّذ خطوات التحويل الموضحة أعلاه، واحفظ كل نتيجة.

---

**آخر تحديث:** 2025-12-13  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  
**موارد ذات صلة:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | حمّل ترخيصًا مؤقتًا [هنا](https://releases.aspose.com/email/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}