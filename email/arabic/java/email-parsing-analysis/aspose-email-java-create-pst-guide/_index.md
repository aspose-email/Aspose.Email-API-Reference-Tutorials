---
date: '2026-06-08'
description: تعلم كيفية إنشاء ملفات PST باستخدام Aspose.Email للـ Java، بما في ذلك
  كيفية إضافة بنى المجلدات وكيفية البحث عن محتوى PST بكفاءة. دليل خطوة بخطوة.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: كيفية إنشاء ملفات PST باستخدام Aspose.Email للـ Java
url: /ar/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان إدارة البريد الإلكتروني باستخدام Aspose.Email للـ Java

إذا كنت بحاجة إلى **how to create pst** ملفات برمجيًا، فقد وجدت المكان المناسب. في هذا البرنامج التعليمي سنستعرض كل خطوة مطلوبة لإنشاء ملف PST Unicode، وإضافة مجلدات Outlook القياسية، واستيراد الرسائل، وإجراء بحث غير حساس لحالة الأحرف — كل ذلك باستخدام Aspose.Email للـ Java. في النهاية، ستحصل على نمط كود قابل لإعادة الاستخدام يتوسع من عدد قليل من الرسائل إلى أرشيفات متعددة الجيجابايت.

## إجابات سريعة
- **كيف أبدأ؟** أضف تبعية Aspose.Email Maven، احصل على ترخيص، وأنشئ كائن `PersonalStorage`.
- **هل يمكنني إضافة مجلد Inbox؟** نعم – استدعِ `pst.getRootFolder().addSubFolder("Inbox")`.
- **هل يدعم البحث غير حساس لحالة الأحرف؟** استخدم `PersonalStorageQueryBuilder` مع `StringComparison.OrdinalIgnoreCase`.
- **ما حجم الملف الذي يمكن معالجته؟** Aspose.Email يعالج ملفات PST حتى 2 GB دون تحميل الملف بالكامل في الذاكرة.
- **هل أحتاج إلى ترخيص مدفوع للإنتاج؟** الترخيص الدائم يزيل حدود التجربة ويفتح جميع ميزات الأداء.

## ما هو how to create pst؟
**how to create pst** يشير إلى العملية البرمجية لإنشاء ملف Outlook Personal Storage Table (PST) باستخدام الكود بدلاً من واجهة Outlook. توفر Aspose.Email للـ Java واجهة برمجة تطبيقات مُدارة بالكامل تُنشئ ملفات PST Unicode، وتضيف مجلدات، وتخزن كائنات `MapiMessage` دون الحاجة إلى تثبيت Outlook.

## لماذا نستخدم Aspose.Email لإنشاء PST؟
يدعم Aspose.Email **أكثر من 50** تنسيقًا متعلقًا بالبريد الإلكتروني (MSG، EML، MBOX، PST، إلخ) ويمكنه معالجة ملفات PST **حتى 2 GB** مع الحفاظ على استهلاك الذاكرة أقل من **150 MB** بفضل بنية التحميل الكسول. هذه القدرة المكمَّنة تجعلها مثالية لأرشفة المؤسسات، والهجرة، وسيناريوهات الامتثال.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** – الإصدار 16 أو أحدث.
- **Maven** – لإدارة التبعيات.
- إلمام أساسي بصياغة Java؛ لا يلزم أي خبرة سابقة بملفات PST.

## كيفية إنشاء ملف PST؟
تمثل الفئة `PersonalStorage` ملف PST وتوفر طرقًا لإنشاءه، فتحه، والتعامل مع محتوياته. لإنشاء PST Unicode جديد، استدعِ `PersonalStorage.create()` مع مسار الملف المطلوب وإصدار التنسيق. هذه العملية تُنشئ PST حديث يدعم المجلدات الكبيرة، الأحرف Unicode، والبث الفعال، مما يجعله مناسبًا لكل من المهام الصغيرة وعلى مستوى المؤسسات.

### الخطوة 1: إضافة تبعية Maven
أضف تبعية Aspose.Email Maven إلى ملف `pom.xml` الخاص بك. سيؤدي ذلك إلى سحب جميع الثنائيات المطلوبة تلقائيًا.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الخطوة 2: الحصول على ترخيص وتطبيقه
يتوفر نسخة تجريبية مجانية، لكن الترخيص الدائم يزيل حدود التقييم ويفعل المعالجة بأقصى سرعة.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## كيفية إضافة مجلد إلى PST؟
أنشئ هيكل المجلدات المطلوب تحت جذر PST، ثم ارجع إليه عند إدراج الرسائل. يمثل كائن `FolderInfo` كل مجلد ويمكن تعشيقه بشكل عشوائي، مما يتيح لك بناء هياكل مثل Inbox، Sent Items، أو مجلدات مشروع مخصصة. إضافة المجلدات عملية خفيفة لا تقوم بتحميل محتوى الرسائل، مما يحافظ على الأداء حتى مع ملفات PST الكبيرة.

### الخطوة 1: تهيئة PersonalStorage
الفئة `PersonalStorage` هي الكائن الأعلى مستوى في Aspose.Email الذي يمثل ملف PST واحد في الذاكرة. بعد الإنشاء، تمر جميع عمليات القراءة والكتابة عبر هذا الكائن.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### الخطوة 2: تحديد مسارات الدليل
حدد مسارات المصدر والوجهة لملفات البريد الإلكتروني وموقع إخراج ملف PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### الخطوة 3: إنشاء ملف PST
استخدم `PersonalStorage.create()` مع `FileFormatVersion.Unicode` لإنتاج PST Unicode حديث يدعم المجلدات الكبيرة والأحرف Unicode.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## كيفية البحث في PST؟
`PersonalStorageQueryBuilder` هي فئة بناء تُستخدم لإنشاء استعلامات بحث لمحتوى PST. من خلال تكوين الباني بالمعايير المطلوبة وتحديد `StringComparison.OrdinalIgnoreCase`، يمكنك إجراء بحث سريع غير حساس لحالة الأحرف عبر العناوين، النصوص، والخصائص المخصصة دون تحميل كامل PST في الذاكرة.

### الخطوة 1: بناء استعلام البحث
أنشئ استعلامًا يبحث عن كلمة مفتاحية في العنوان أو النص، متجاهلًا حالة الأحرف.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### الخطوة 2: تنفيذ الاستعلام واسترجاع الرسائل
نفّذ الاستعلام على المجلد المستهدف وتكرّر عبر مجموعة `MapiMessage` الناتجة.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## إنشاء مجلد محدد مسبقًا في PST
إضافة مجلد محدد مسبقًا مثل **Inbox** يساعد على تنظيم بيانات البريد الإلكتروني بفعالية.

### الخطوة 1: تهيئة كائن PersonalStorage
افترض أن كائن `PersonalStorage` (`pst`) تم إنشاؤه بالفعل كما هو موضح سابقًا.

### الخطوة 2: إنشاء مجلد 'Inbox'
```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## إضافة رسائل إلى مجلد PST
املأ مجلد PST الخاص بك برسائل البريد الإلكتروني عن طريق تحميلها من الملفات وتحويلها.

### الخطوة 1: تحميل رسالة البريد الإلكتروني
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### الخطوة 2: إضافة إلى مجلد PST
حوّل `MailMessage` إلى `MapiMessage` وأضفه:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## تطبيقات عملية
Aspose.Email للـ Java ليس مجرد إنشاء ملفات PST؛ إنه أداة متعددة الاستخدامات مع تطبيقات عديدة:
- **أرشفة البريد الإلكتروني**: أتمتة أرشفة رسائل البريد الإلكتروني المؤسسية إلى ملفات PST، مع دعم سياسات الاحتفاظ حتى 10 سنوات.
- **أدوات الهجرة**: هجرة سلسة من مخازن البريد القديمة (مثل MBOX) إلى Outlook PST باستدعاء API واحد لكل رسالة.
- **تحليل البيانات**: استخراج بيانات التعريف مثل المرسل، المستلم، والطوابع الزمنية لتدفقات عمل الذكاء التجاري.
- **حلول النسخ الاحتياطي**: بناء أدوات نسخ احتياطي قوية تخزن التغييرات البريدية المتزايدة دون إعادة معالجة كامل صندوق البريد.

## اعتبارات الأداء
لضمان الأداء المثالي عند استخدام Aspose.Email:
- **إدارة الموارد**: استدعِ دائمًا `pst.dispose()` أو استخدم try‑with‑resources لتحرير المقابض الأصلية بسرعة.
- **المعالجة الدفعية**: عالج الرسائل في دفعات من **500** عنصر للحفاظ على استهلاك الذاكرة متوقعًا.
- **معالجة التزامن**: المكتبة آمنة للقراءة المتعددة؛ بالنسبة للكتابة، قم بمزامنة الوصول إلى كائن `PersonalStorage`.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|----------|
| **OutOfMemoryError** عند معالجة PSTs الكبيرة | تحميل كامل PST في الذاكرة | فعّل `PersonalStorage.setUseUnicode(true)` وعالج الرسائل عبر التدفقات. |
| **خطأ Folder not found** | حالة غير صحيحة لمسار المجلد | استخدم `StringComparison.OrdinalIgnoreCase` في الاستعلامات أو قم بتطبيع أسماء المجلدات. |
| **الترخيص غير مُطبق** | ملف الترخيص لم يُحمَّل قبل أول استدعاء API | حمّل الترخيص عند بدء تشغيل التطبيق، قبل إنشاء أي كائنات `PersonalStorage`. |

## الأسئلة المتكررة
**س: ما هو الحد الأدنى لإصدار Java المطلوب؟**  
ج: يُنصح بـ JDK 16 أو أعلى للحصول على توافق كامل مع Aspose.Email للـ Java.

**س: هل يمكنني استخدام Aspose.Email بدون ترخيص؟**  
ج: نعم، يتوفر وضع تجريبي لكنه يحد من حجم PST إلى **10 MB** ويعطل بعض التحسينات.

**س: كيف يمكنني التعامل مع ملفات PST الكبيرة بكفاءة؟**  
ج: عالج الرسائل في دفعات، حرّر كائنات `MapiMessage` بسرعة، وفعل التحميل الكسول عبر `PersonalStorage.setUseUnicode(true)`.

**س: هل يمكن إضافة مرفقات إلى رسائل البريد في ملفات PST؟**  
ج: بالتأكيد. عند تحويل `MailMessage` إلى `MapiMessage`، استدعِ `mapiMsg.getAttachments().add(attachment)` لإرفاق الملفات.

**س: ما نوع الدعم المتاح لحل المشكلات؟**  
ج: تقدم Aspose منتدى دعم مخصص، وثائق مفصلة، ودعم عبر البريد الإلكتروني للعملاء المرخصين.

## الموارد
- [التوثيق](https://reference.aspose.com/email/java/)
- [التنزيل](https://releases.aspose.com/email/java/)
- [الشراء](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى الدعم](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-06-08  
**تم الاختبار مع:** Aspose.Email for Java 24.10  
**المؤلف:** Aspose

## دروس ذات صلة
- [كيفية إنشاء وإدارة ملفات Outlook PST باستخدام Aspose.Email للـ Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [معالجة ملفات PST باستخدام Aspose.Email للـ Java: دليل شامل](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [استخراج مرفقات البريد الإلكتروني Java - باستخدام Aspose.Email لملفات PST – دليل خطوة بخطوة](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}