---
date: '2026-09-02'
description: تعلم كيفية استخراج المرفقات من ملفات Outlook PST باستخدام Aspose.Email
  for Java. يغطي هذا الدليل إعداد Maven، تحميل ملفات PST، واستخراج ملفات PDF وغيرها
  بكفاءة.
keywords:
- extract attachments from outlook
- how to extract pst attachments
- aspose email java tutorial
- maven dependency aspose email
- aspose email java example
lastmod: '2026-09-02'
og_description: استخراج المرفقات من ملفات Outlook PST باستخدام Aspose.Email for Java.
  اتبع هذا الدليل خطوة بخطوة لإعداد Maven، تحميل ملفات PST، واستخراج ملفات PDF وغيرها.
og_image_alt: Developer guide showing Java code to extract Outlook PST attachments
  using Aspose.Email
og_title: استخراج المرفقات من Outlook PST باستخدام Java مع Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to extract attachments from Outlook PST files using Aspose.Email
    for Java. This guide covers Maven setup, loading PSTs, and extracting PDFs and
    other files efficiently.
  headline: How to extract attachments from Outlook PST in Java
  type: TechArticle
- description: Learn how to extract attachments from Outlook PST files using Aspose.Email
    for Java. This guide covers Maven setup, loading PSTs, and extracting PDFs and
    other files efficiently.
  name: How to extract attachments from Outlook PST in Java
  steps:
  - name: define your directory path
    text: Identify where your PST file resides and set the path.
  - name: load the PST file
    text: '`PersonalStorage` is Aspose.Email’s top‑level class that represents a single
      PST or OST file in memory. After you create an instance, you can navigate folders,
      read messages, and extract data.'
  - name: access the Inbox subfolder
    text: '`MapiFolder` represents a folder inside the PST (e.g., Inbox, Sent Items).
      The `getSubFolders` method lets you drill down to the exact location you need.'
  - name: iterate through emails and extract attachments
    text: '`MapiMessage` encapsulates an individual email message. Its `getAttachments`
      collection provides every file attached to that message. `MapiAttachment` is
      the class that holds the binary data and metadata for each attachment.'
  type: HowTo
- questions:
  - answer: After retrieving each `MapiAttachment`, check the file extension with
      `attachment.getLongFileName().endsWith(".pdf")` before saving.
    question: How can I extract only PDF attachments (java extract pdf attachments)?
  - answer: The official documentation and sample repository provide extensive examples—see
      the links below.
    question: Where can I find more detailed code examples for the aspose email java
      tutorial?
  - answer: Yes, Aspose.Email for Java is forward‑compatible; just ensure you use
      the appropriate classifier (e.g., `jdk21`) when it becomes available.
    question: Is the library compatible with newer Java versions (e.g., JDK 21)?
  - answer: Absolutely. Package the code into a JAR, configure a cron job, and ensure
      the server has the required JDK and Maven runtime.
    question: Can I run this extraction as a scheduled job on a Linux server?
  type: FAQPage
tags:
- extract attachments
- Aspose.Email
- Java email processing
title: كيفية استخراج المرفقات من Outlook PST باستخدام Java
url: /ar/java/attachments-handling/extract-email-attachments-pst-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخراج المرفقات من Outlook PST باستخدام Java

## مقدمة

استخراج المرفقات من ملفات Outlook PST هو طلب شائع لهجرة البيانات، أرشفة الامتثال، ومعالجة الفواتير الآلية. في هذا البرنامج التعليمي ستكتشف كيفية **استخراج المرفقات من Outlook** باستخدام Aspose.Email for Java، إعداد تبعية Maven، تحميل ملف PST، واستخراج ملفات PDF أو الصور أو أي مستند مرفق آخر ببضع أسطر من الشيفرة.

**ما ستتعلمه**
- كيفية إضافة تبعية Maven لـ Aspose.Email (aspose email java tutorial)  
- كيفية فتح ملف PST وتصفح هيكل المجلدات الخاص به  
- كيفية استخراج مرفقات البريد الإلكتروني بكفاءة، مع الإجابة على السؤال *how to extract pst attachments*  

هل أنت مستعد لأتمتة سير عمل مرفقات البريد الإلكتروني؟ هيا نبدأ.

## إجابات سريعة
- **المكتبة الأساسية؟** Aspose.Email for Java  
- **الوقت النموذجي للتنفيذ؟** 10–15 دقيقة للاستخراج الأساسي  
- **المتطلب الأساسي؟** JDK 16+ و Maven مثبتان  
- **هل الترخيص مطلوب؟** نعم، ترخيص Aspose صالح للاستخدام الإنتاجي  
- **يدعم PST و OST؟** كلا الصيغتين مدعومتان  

## ما هو “how to extract attachments”؟

استخراج المرفقات يعني استخدام شفرة Java لقراءة ملفات Outlook PST (أو OST) وحفظ أي ملفات مرفقة—مستندات، صور، PDFs—في دليل تختاره. هذا النهج مثالي لمشاريع هجرة البيانات، معالجة الفواتير الآلية، أو بناء حلول أرشيفية. العملية تقوم بتحليل أجزاء MIME لكل رسالة، تسترجع المحتوى الثنائي لكل مرفق، وتكتبها إلى المجلد المحدد، مما يسمح بمعالجة إضافية مثل الفهرسة أو التحويل.

## لماذا نستخدم Aspose.Email لهذه المهمة؟

Aspose.Email يلغي الحاجة إلى Outlook أو MAPI على الخادم، مما يقلل وقت الإعداد حتى 80 ٪ ويخفض تكاليف الترخيص. يدعم **50+** صيغ إدخال وإخراج، يتعامل مع المخازن المشفرة، ويوفر طرق عالية المستوى مثل `extractAttachments` التي تُجرد تفاصيل التحليل منخفضة المستوى.

## المتطلبات المسبقة

- **Java Development Kit (JDK):** الإصدار 16 أو أحدث.  
- **Maven:** لإدارة التبعيات.  
- **Aspose.Email for Java library:** مضافة عبر Maven (انظر المقتطف *maven dependency aspose email* أدناه).  
- **IDE:** IntelliJ IDEA، Eclipse، أو VS Code لتحرير وتشغيل الشيفرة.  

## إعداد Aspose.Email لـ Java

### إضافة تبعية Maven (maven dependency aspose email)

أدرج XML التالي في ملف `pom.xml` الخاص بمشروعك تحت `<dependencies>`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

Aspose تقدم تجربة مجانية، لكن الترخيص الكامل يفتح جميع الميزات. يمكنك الحصول على ترخيص مؤقت عبر [temporary license page](https://purchase.aspose.com/temporary-license/).

## دليل التنفيذ (aspose email java tutorial)

### الميزة 1: تحميل ملف PST

#### الخطوة 1: تحديد مسار الدليل الخاص بك

حدد موقع ملف PST الخاص بك واضبط المسار.

```java
String pstFilePath = "YOUR_DOCUMENT_DIRECTORY/Sub.pst";
```

#### الخطوة 2: تحميل ملف PST

`PersonalStorage` هو الفئة العليا في Aspose.Email التي تمثل ملف PST أو OST واحد في الذاكرة. بعد إنشاء مثيل، يمكنك تصفح المجلدات، قراءة الرسائل، واستخراج البيانات.

```java
PersonalStorage pst = PersonalStorage.fromFile(pstFilePath);
```

### الميزة 2: استخراج المرفقات من رسائل البريد الإلكتروني

#### الخطوة 1: الوصول إلى المجلد الفرعي Inbox

`MapiFolder` يمثل مجلدًا داخل PST (مثل Inbox أو Sent Items). طريقة `getSubFolders` تتيح لك الانتقال إلى الموقع الدقيق الذي تحتاجه.

```java
FolderInfo inboxFolder = pst.getRootFolder().getSubFolder("Inbox");
```

#### الخطوة 2: التكرار عبر رسائل البريد الإلكتروني واستخراج المرفقات

`MapiMessage` يضم رسالة بريد إلكتروني فردية. مجموعة `getAttachments` الخاصة به توفر كل ملف مرفق بهذه الرسالة. `MapiAttachment` هي الفئة التي تحتفظ بالبيانات الثنائية والبيانات الوصفية لكل مرفق.

```java
for (String entryId : inboxFolder.enumerateMessagesEntryId()) {
    MapiAttachmentCollection attachments = pst.extractAttachments(entryId);
    
    if (!attachments.isEmpty()) {
        for (MapiAttachment attachment : attachments) {
            String outputFilePath = "YOUR_OUTPUT_DIRECTORY/" + attachment.getLongFileName();
            attachment.save(outputFilePath); // Save each attachment
        }
    }
}
```

### خيارات التكوين الرئيسية

- **دليل الإخراج:** تحقق من وجود المجلد وأن التطبيق يمتلك أذونات كتابة.  
- **معالجة الأخطاء:** غلف المنطق السابق في كتل `try‑catch` للتعامل بأناقة مع أخطاء الإدخال/الإخراج أو إدخالات PST الفاسدة.  

### نصائح استكشاف الأخطاء (how to extract pst attachments)

إذا واجهت مشاكل أثناء استخراج مرفقات PST، ففكر في هذه الإصلاحات السريعة:

- **الملف غير موجود:** تحقق مرة أخرى من سلسلة `pstFilePath`؛ استخدم مسارات مطلقة للموثوقية.  
- **مشكلات الأذونات:** شغّل JVM بأذونات نظام ملفات مناسبة أو اختر دليلًا داخل مجلد المستخدم الرئيسي.  
- **ملفات PST الكبيرة:** عالج الرسائل على دفعات واستدعِ `System.gc()` بعد كل دفعة لتحرير الذاكرة.  

## التطبيقات العملية

1. **نسخ احتياطي للبيانات:** سحب المرفقات دوريًا لتخزين آمن خارج الموقع.  
2. **معالجة الفواتير الآلية:** استخراج ملفات PDF من الفواتير الواردة وإدخالها في نظام ERP.  
3. **أرشفة البريد الإلكتروني:** حفظ كل مرفق كجزء من أرشيف جاهز للامتثال.  

## اعتبارات الأداء

- **إدارة الذاكرة:** بالنسبة لملفات PST التي تتجاوز 1 GB، زد حجم كومة JVM (`-Xmx2g` أو أعلى).  
- **استخراج دفعي:** عالج عددًا محدودًا من الرسائل في كل تكرار حلقة للحفاظ على استهلاك منخفض للذاكرة.  

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| `fromFile` throws `FileNotFoundException` | تحقق من المسار وتأكد من أن الملف غير مقفل بواسطة عملية أخرى. |
| Out‑of‑Memory errors on huge PSTs | زد حجم الكومة واستخراج على دفعات أصغر. |
| Attachments have duplicate names | أضف طابعًا زمنيًا أو GUID إلى `outputFilePath` قبل الحفظ. |

## الأسئلة المتكررة

**س:** *ما هو ملف PST؟*  
ج: ملف PST (Personal Storage Table) هو ملف بيانات Outlook يخزن الرسائل الإلكترونية، جهات الاتصال، عناصر التقويم، والمرفقات.

**س:** *هل يمكنني استخراج المرفقات من ملفات OST أيضًا؟*  
ج: نعم، Aspose.Email يدعم كل من صيغتي PST و OST. استخدم نفس الـ API؛ فقط وجه `PersonalStorage.fromFile` إلى ملف OST.

**س:** *كيف أتعامل مع ملفات PST المشفرة؟*  
ج: قدم كلمة المرور عند فتح المخزن: `PersonalStorage.fromFile(pstFilePath, "password")`. راجع وثائق Aspose للحصول على تفاصيل معالجة التشفير.

**س:** *هل هناك طريقة لتصفية رسائل البريد الإلكتروني التي تتم معالجتها؟*  
ج: بالتأكيد. قبل استدعاء `extractAttachments`، يمكنك فحص كل `MapiMessage` للموضوع، المرسل، أو معايير التاريخ وتخطي العناصر غير المرغوب فيها.

**س:** *هل أحتاج إلى ترخيص للتطوير؟*  
ج: الترخيص المؤقت يكفي للاختبار. للإنتاج، اشترِ ترخيصًا كاملاً لإزالة قيود التقييم.

## أسئلة إضافية (ملائمة للذكاء الاصطناعي)

**س:** *كيف يمكنني استخراج مرفقات PDF فقط (java extract pdf attachments)؟*  
ج: بعد استرجاع كل `MapiAttachment`، تحقق من امتداد الملف باستخدام `attachment.getLongFileName().endsWith(".pdf")` قبل الحفظ.

**س:** *أين يمكنني العثور على أمثلة شيفرة أكثر تفصيلاً لـ aspose email java tutorial؟*  
ج: الوثائق الرسمية ومستودع العينات يوفران أمثلة واسعة—انظر الروابط أدناه.

**س:** *هل المكتبة متوافقة مع إصدارات Java الأحدث (مثل JDK 21)؟*  
ج: نعم، Aspose.Email for Java متوافقة مع الإصدارات المستقبلية؛ فقط تأكد من استخدام المصنف المناسب (مثل `jdk21`) عندما يصبح متاحًا.

**س:** *هل يمكن تشغيل هذا الاستخراج كوظيفة مجدولة على خادم Linux؟*  
ج: بالتأكيد. احزم الشيفرة في ملف JAR، اضبط مهمة cron، وتأكد من أن الخادم يحتوي على JDK و Maven المطلوبين.

## الموارد
- **Documentation:** [توثيق Aspose Email Java](https://reference.aspose.com/email/java/)
- **Download:** [إصدار Aspose Email Java](https://releases.aspose.com/email/java/)
- **Purchase license:** [شراء Aspose Email](https://purchase.aspose.com/buy)
- **Free trial:** [ابدأ بتجربة مجانية](https://releases.aspose.com/email/java/)
- **Support forum:** [اسأل أسئلة في منتدى الدعم](https://forum.aspose.com/c/email/10)

استفد من قوة Aspose.Email لـ Java وغيّر طريقة تعاملك مع مرفقات البريد الإلكتروني!

---

**آخر تحديث:** 2026-09-02  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [تحميل ومعالجة ملفات Outlook PST بكفاءة باستخدام Aspose.Email لـ Java](/email/java/outlook-pst-ost-operations/aspose-email-java-outlook-pst-processing/)
- [كيفية استخراج رسائل Outlook PST باستخدام Aspose.Email لـ Java: دليل كامل](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [معالجة ملفات PST باستخدام Aspose.Email لـ Java: دليل شامل](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}