---
date: '2026-09-02'
description: تعرف على كيفية إضافة مرفق إلى ملف eml، تحويل msg إلى eml باستخدام Java،
  تحويل دفعة من msg إلى eml، ومعالجة TNEF باستخدام Aspose.Email Java.
keywords:
- add attachment to eml
- msg to eml java
- batch msg to eml
- maven aspose email dependency
- tnef handling
lastmod: '2026-09-02'
og_description: إضافة مرفق إلى ملف eml وتحويل msg إلى eml باستخدام Java عبر Aspose.Email
  Java. يتضمن تحويل دفعة، معالجة TNEF، ودليل اعتماد Maven.
og_image_alt: Guide for adding attachments to EML and converting MSG to EML with Aspose.Email
  Java
og_title: إضافة مرفق إلى ملف eml باستخدام Aspose.Email Java – تحويل MSG إلى EML
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  headline: Add attachment to eml with Aspose.Email Java – convert msg to eml and
    handle TNEF
  type: TechArticle
- description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  name: Add attachment to eml with Aspose.Email Java – convert msg to eml and handle
    TNEF
  steps:
  - name: Load the existing email message
    text: The `MailMessage` class represents an email message in memory, exposing
      headers, body, and attachments.
  - name: Add the new attachment
    text: The `Attachment` class encapsulates a file to be attached to a `MailMessage`.
  - name: Save the modified email message
    text: Calling `mail.save()` writes the updated message back to disk in EML format.
      *Pro tip:* Use try‑with‑resources to ensure streams are closed and avoid `FileNotFoundException`.
  - name: Load the MSG file
    text: The `MapiMessage` class reads Outlook MSG files and exposes their properties.
  - name: Set conversion options
    text: '`MailConversionOptions` lets you control how the conversion handles TNEF
      data.'
  - name: Convert and save
    text: Calling `msg.save()` with the appropriate options writes a TNEF‑preserving
      EML file.
  - name: Set load options
    text: '`MsgLoadOptions` instructs the loader to keep TNEF parts intact.'
  - name: Load EML file with options
    text: '`MailMessage.load()` reads the EML using the options defined above.'
  - name: Load the EML file
    text: The `MailMessage` class again serves as the entry point for reading an EML
      file.
  - name: Detect TNEF presence
    text: The boolean returned by `mail.getOriginalIsTnef()` tells you whether the
      original message contained TNEF data.
  type: HowTo
- questions:
  - answer: No. By default, TNEF data is preserved. You can control this behavior
      with `MailConversionOptions.setConvertAsTnef`.
    question: Does Aspose.Email automatically strip TNEF when converting to EML?
  - answer: Yes—use `mail.getAttachments()` which returns a collection you can iterate
      over.
    question: Can I programmatically list all attachments in a loaded message?
  - answer: Absolutely. Loop through the files, apply the conversion steps shown above,
      and save each result.
    question: Is there a way to batch convert msg files to eml in one run?
  type: FAQPage
tags:
- email conversion
- Aspose.Email
- java email processing
- attachment handling
title: إضافة مرفق إلى ملف eml باستخدام Aspose.Email Java – تحويل msg إلى eml ومعالجة
  TNEF
url: /ar/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان إضافة مرفق إلى ملف eml وتحويل msg إلى eml باستخدام Aspose.Email Java: التعامل مع TNEF ومرفقات البريد الإلكتروني  

في التطبيقات الحديثة التي تركز على البريد الإلكتروني، غالبًا ما تحتاج إلى **إضافة مرفق إلى eml**، وتحويل ملفات MSG إلى تنسيق EML القياسي، والحفاظ على الصيغ الخاصة مثل TNEF. سواءً كنت تبني خدمة أرشفة، أو أداة ترحيل، أو عارض بريد إلكتروني من جانب العميل، فإن Aspose.Email for Java يوفّر لك طريقة برمجية نظيفة للقيام بذلك. في هذا الدرس ستتعرف بالضبط على كيفية **إضافة مرفق إلى eml**، **تحويل msg إلى eml java**، العمل مع سيناريوهات دفعة msg إلى eml، ومعالجة بيانات TNEF باستخدام مكتبة Aspose.Email Java.

## إجابات سريعة
- **كيف يمكنني تحويل MSG إلى EML في Java؟** حمّل MSG باستخدام `MapiMessage`، عيّن `MailConversionOptions.convertAsTnef` إلى `true`، ثم احفظه كـ EML.  
- **هل يمكنني إضافة مرفق إلى EML مفعّل بـ TNEF؟** نعم – حمّل EML، استدعِ `mail.getAttachments().addItem(...)`، ثم احفظه.  
- **ما هي تبعية Maven المطلوبة؟** أدرج حزمة **Aspose.Email** الخاصة بـ Maven كما هو موضح أدناه.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم – النسخة التجريبية تعمل للتقييم، لكن الترخيص الكامل يزيل القيود.  
- **هل هناك طريقة لاكتشاف TNEF في رسالة موجودة؟** استدعِ `mail.getOriginalIsTnef()` بعد تحميل EML.

## ما هو “convert msg to eml java”؟
**Convert msg to eml java** هو عملية تحويل ملف Microsoft Outlook MSG إلى ملف EML متوافق مع RFC‑822 باستخدام Java. يتيح ذلك لأي عميل بريد قياسي قراءة الرسالة مع إتاحة الفرصة لمعالجة بيانات TNEF المشفرة أثناء التحويل.

## لماذا نستخدم Aspose.Email Java لهذه المهمة؟
يمكنك تحويل MSG إلى EML، إضافة مرفقات، والحفاظ على TNEF ببضع نداءات API فقط. يدعم Aspose.Email **أكثر من 30+ صيغة بريد إلكتروني** ويمكنه معالجة ملفات يصل حجمها إلى **2 GB** دون تحميل المستند بالكامل إلى الذاكرة، مما يجعله مثاليًا للترحيلات على نطاق واسع.

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
يقدّم Aspose.Email نسخة تجريبية مجانية، لكن النسخة المرخصة مطلوبة للاستخدام غير المقيد.

- **نسخة تجريبية مجانية:** حمّل ترخيصًا مؤقتًا من صفحة إصدارات Aspose.Email Java: [Aspose.Email Java releases](https://releases.aspose.com/email/java/).  
- **الشراء:** لشراء ترخيص، زر [صفحة الشراء](https://purchase.aspose.com/buy).

قم بتهيئة الترخيص في كود Java الخاص بك:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## دليل التنفيذ

### إضافة مرفق جديد إلى رسالة رئيسية تحتوي على TNEF
**كيفية إضافة مرفق إلى eml:** حمّل EML، أضف الملف، ثم احفظه.

#### الخطوة 1: تحميل رسالة البريد الإلكتروني الموجودة
تمثل الفئة `MailMessage` رسالة بريد إلكتروني في الذاكرة، وتكشف عن الرؤوس، والمحتوى، والمرفقات.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### الخطوة 2: إضافة المرفق الجديد
تغلف الفئة `Attachment` ملفًا سيتم إرفاقه بـ `MailMessage`.  
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### الخطوة 3: حفظ رسالة البريد المعدلة
استدعاء `mail.save()` يكتب الرسالة المحدثة إلى القرص بصيغة EML.  
```java
eml.save(dataDir + "test_out.eml");
```
*نصيحة احترافية:* استخدم `try‑with‑resources` لضمان إغلاق التدفقات وتجنّب `FileNotFoundException`.

### إنشاء EML مفعّل بـ TNEF من MSG
**كيفية تحويل msg إلى eml java:** عيّن `convertAsTnef` إلى `true`.

#### الخطوة 1: تحميل ملف MSG
تقرأ الفئة `MapiMessage` ملفات Outlook MSG وتكشف عن خصائصها.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### الخطوة 2: تعيين خيارات التحويل
تتيح لك `MailConversionOptions` التحكم في كيفية معالجة التحويل لبيانات TNEF.  
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### الخطوة 3: التحويل والحفظ
استدعاء `msg.save()` مع الخيارات المناسبة يكتب ملف EML يحافظ على TNEF.  
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### الحفاظ على مرفقات TNEF عند تحميل ملفات EML
**كيفية حفظ مرفق البريد مع الحفاظ على TNEF:** استخدم `MsgLoadOptions`.

#### الخطوة 1: تعيين خيارات التحميل
توجه `MsgLoadOptions` المحمل للحفاظ على أجزاء TNEF دون تعديل.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### الخطوة 2: تحميل ملف EML باستخدام الخيارات
`MailMessage.load()` يقرأ EML باستخدام الخيارات المحددة أعلاه.  
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### اكتشاف ما إذا كانت الرسالة تحتوي على TNEF
**كيفية التحقق من وجود TNEF:** استدعِ `getOriginalIsTnef()`.

#### الخطوة 1: تحميل ملف EML
تظل الفئة `MailMessage` نقطة الدخول لقراءة ملف EML.  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### الخطوة 2: اكتشاف وجود TNEF
القيمة البوليانية التي تُرجعها `mail.getOriginalIsTnef()` تخبرك ما إذا كانت الرسالة الأصلية تحتوي على بيانات TNEF.  
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## حالات الاستخدام الشائعة وسيناريوهات الدفعات
- **تحويل دفعة من msg:** كرّر عبر مجلد يحتوي على ملفات `.msg`، نفّذ خطوات التحويل أعلاه، واحفظ كل نتيجة كـ `.eml`. هذا مثالي للترحيلات على نطاق واسع.  
- **إضافة مرفق إلى eml بالجملة:** دمج كود “إضافة مرفق” مع مكرّر نظام الملفات لإثراء العديد من الرسائل دفعة واحدة.  
- **الأرشفة الآلية:** احفظ كلًا من MSG الأصلي وEML الحافظ على TNEF لتدقيق الامتثال.

## اعتبارات الأداء
- **إدارة الموارد:** غلف تدفقات الملفات بـ `try‑with‑resources` لتحرير المقابض بسرعة.  
- **المرفقات الكبيرة:** عالج الملفات الضخمة على دفعات أو بثها مباشرة لتجنّب استهلاك الذاكرة العالي.  
- **المراقبة:** استخدم أدوات تحليل Java لمراقبة استهلاك الـ heap عند معالجة العديد من المرفقات.

## الخلاصة
باتباع الخطوات أعلاه يمكنك **إضافة مرفق إلى eml**، **تحويل msg إلى eml java**، والعمل بثقة مع بيانات TNEF باستخدام Aspose.Email for Java. تُجرد المكتبة التعامل منخفض المستوى مع MIME، مما يتيح لك التركيز على منطق الأعمال. لاستكشاف أعمق، راجع الوثائق الرسمية لـ [Aspose.Email Java documentation](https://reference.aspose.com/email/java/) أو جرّب خيارات تحويل أخرى. تشمل الموارد الإضافية [Aspose Email Java Documentation](https://reference.aspose.com/email/java/)، [Aspose Email Java Releases](https://releases.aspose.com/email/java/)، وصفحة [Buy Aspose.Email for Java](https://purchase.aspose.com/buy).

## قسم الأسئلة المتكررة
**س1: ما هو ملف TNEF؟**  
ج1: TNEF هو اختصار لـ Transport Neutral Encapsulation Format ويستخدمه Microsoft Outlook للحفاظ على تنسيق النص الغني عند إرسال رسائل البريد كمرفقات.

**س2: هل يمكنني استخدام Aspose.Email دون شراء ترخيص؟**  
ج2: نعم، يمكنك البدء بنسخة تجريبية مجانية. ومع ذلك، تفرض النسخة التجريبية بعض القيود التي قد تؤثر على الاستخدام على نطاق كامل.

**س3: هل يمكن تحويل جميع صيغ البريد الإلكتروني باستخدام Aspose.Email؟**  
ج3: يدعم Aspose.Email التحويل بين معظم الصيغ الشائعة—بما في ذلك EML، MSG، وMHTML—لكن تحقق من دعم الصيغة المحددة في [الوثائق](https://reference.aspose.com/email/java/).

**س4: كيف أقوم باستكشاف أخطاء “الملف غير موجود” مع Aspose.Email؟**  
ج5: تأكد من صحة مسارات الملفات التي تمرّرها إلى الـ API، وتأكد من وجود الملفات، وأن العملية التنفيذية لديها صلاحيات القراءة/الكتابة للمجلدات المعنية.

**س5: ما هي أفضل طريقة للتعامل مع المرفقات الكبيرة باستخدام Aspose.Email؟**  
ج5: عالج المرفقات في تدفقات أو قطع أصغر، واغلق التدفقات فورًا. هذا يقلل من الضغط على الذاكرة ويمنع حدوث `OutOfMemoryError`.

## أسئلة متكررة إضافية

**س: هل يقوم Aspose.Email تلقائيًا بإزالة TNEF عند التحويل إلى EML؟**  
ج: لا. بشكل افتراضي يتم الحفاظ على بيانات TNEF. يمكنك التحكم في هذا السلوك عبر `MailConversionOptions.setConvertAsTnef`.

**س: هل يمكنني سرد جميع المرفقات في رسالة محمّلة برمجيًا؟**  
ج: نعم—استخدم `mail.getAttachments()` التي تُعيد مجموعة يمكنك التكرار عليها.

**س: هل هناك طريقة لتحويل دفعة من ملفات msg إلى eml في تشغيل واحد؟**  
ج: بالتأكيد. كرّر عبر الملفات، نفّذ خطوات التحويل الموضحة أعلاه، واحفظ كل نتيجة.

**الموارد ذات الصلة:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | حمّل ترخيصًا مؤقتًا من صفحة إصدارات Aspose.Email Java: [Aspose.Email Java releases](https://releases.aspose.com/email/java/).

---

**آخر تحديث:** 2026-09-02  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  







```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## دروس ذات صلة

- [Maven Aspose Email: Preserve TNEF Attachments in EML (Java)](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [How to Add Aspose.Email Maven Dependency and Retrieve Email Attachment Content Descriptions (Java)](/email/java/attachments-handling/retrieve-email-attachment-content-descriptions-aspose-email-java/)
- [Extract Email Attachments Java with Aspose.Email – Complete Guide](/email/java/attachments-handling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}