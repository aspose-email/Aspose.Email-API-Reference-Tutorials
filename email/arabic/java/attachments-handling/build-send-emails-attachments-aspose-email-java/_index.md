---
date: '2025-12-14'
description: تعلم كيفية إرسال بريد إلكتروني مع مرفقات باستخدام Aspose.Email للغة Java.
  يغطي هذا الدليل خطوة بخطوة الإعداد، إنشاء الرسائل، إضافة الملفات، وحفظها بصيغة MSG.
keywords:
- send emails with attachments using Aspose.Email for Java
- Aspose.Email setup for Java
- handling email attachments in Java
title: كيفية إرسال بريد إلكتروني مع مرفقات باستخدام Aspose.Email للـ Java
url: /ar/java/attachments-handling/build-send-emails-attachments-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إرسال بريد إلكتروني مع مرفقات باستخدام Aspose.Email للغة Java

## المقدمة

في المشهد الرقمي اليوم، **كيفية إرسال بريد إلكتروني** برمجياً هي مهارة أساسية لأي مطور Java يبني أدوات تقارير أو خدمات إشعارات أو تدفقات عمل مؤتمتة. يشرح هذا الدليل كيفية استخدام Aspose.Email للغة Java — مكتبة قوية تجعل إنشاء الرسائل، إرفاق الملفات، وحتى حفظ الرسائل كملفات MSG أمرًا بسيطًا. في النهاية، ستتمكن من إرسال بريد إلكتروني مع مرفق، إرفاق ملفات بالبريد، وحفظ البريد كملف MSG ببضع أسطر من الشيفرة فقط.

**ما ستتعلمه**
- إعداد Aspose.Email للغة Java في بيئة التطوير الخاصة بك  
- إنشاء رسالة بريد إلكتروني مع عناوين المرسل والمستلم  
- إرفاق أنواع ملفات متعددة (نص، صورة، مستند، أرشيف، PDF)  
- حفظ البريد الإلكتروني المُنشأ كملف MSG للاستخدام لاحقًا  

هل أنت مستعد لتعزيز قدرات أتمتة البريد الإلكتروني؟ لنبدأ بالمتطلبات المسبقة.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Email للغة Java  
- **هل يمكنني إرفاق أي نوع من الملفات؟** نعم – نصوص، صور، PDFs، أرشيفات، مستندات Word، إلخ.  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **كيف أحفظ البريد الإلكتروني؟** استخدم `message.save(..., SaveOptions.getDefaultMsg())`.  
- **هل يدعم البريد الإلكتروني بصيغة HTML؟** بالتأكيد – عيّن `message.isBodyHtml(true)` وقدم محتوى HTML.

## ما هو Aspose.Email للغة Java؟
Aspose.Email للغة Java هو API عالي الأداء يتيح لك إنشاء، تعديل، وإرسال رسائل البريد الإلكتروني دون الاعتماد على خادم بريد خارجي. يتعامل مع هياكل MIME، المرفقات، ومختلف صيغ البريد (EML، MSG، MHTML) مباشرةً.

## لماذا نستخدم Aspose.Email لإرسال بريد إلكتروني مع مرفق؟
- **لا حاجة إلى SMTP خارجي** لبناء وحفظ الرسائل.  
- **دعم مرفقات غني** – يمكنك إضافة أي نوع من الملفات، بما في ذلك الملفات الثنائية الكبيرة.  
- **توافق متعدد المنصات** – يعمل على JVMs في Windows، Linux، و macOS.  
- **حفظ مدمج** – تصدير سهل إلى MSG، EML، أو MHTML للأرشفة.

## المتطلبات المسبقة

- **مجموعة تطوير جافا (JDK):** الإصدار 16 أو أحدث.  
- **بيئة تطوير متكاملة (IDE):** IntelliJ IDEA، Eclipse، أو أي محرر متوافق مع Java.  
- **Maven:** سنُدير الاعتمادات باستخدام Maven.  

يفترض وجود فهم أساسي لجافا ومشاريع Maven.

## إعداد Aspose.Email للغة Java

### التثبيت عبر Maven

أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

يمكن استخدام Aspose.Email للغة Java برخصة تجريبية مجانية أو برخصة مُشتراة. لاختبار جميع الإمكانات، احصل على ترخيص مؤقت:

1. زر صفحة [الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).  
2. اتبع التعليمات لطلب ترخيص التجربة المجانية.  
3. طبّق الترخيص في تطبيقك كما هو موضح في وثائق Aspose.

### التهيئة الأساسية

ابدأ بإنشاء كائن `MailMessage` وتعيين العناوين الأساسية:

```java
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Initialize the MailMessage object
MailMessage message = new MailMessage();
message.setFrom(new MailAddress("sender@sender.com"));
message.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
```

## دليل التنفيذ

### كيفية إرسال بريد إلكتروني مع مرفقات باستخدام Aspose.Email للغة Java

#### تهيئة كائن `MailMessage`

```java
// Set 'From' address
message.setFrom(new MailAddress("sender@sender.com"));

// Add 'To' address
message.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
```

#### تعريف مسارات الدليل للمرفقات

استبدل `"YOUR_DOCUMENT_DIRECTORY/"` بالمسار الذي يحتوي على الملفات التي تريد إرفاقها:

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
```

#### إضافة مرفقات (attach files to email)

يمكنك إرفاق مجموعة متنوعة من أنواع الملفات. أدناه نضيف ملف نصي، صورة، مستند Word، أرشيف RAR، وملف PDF:

```java
// Adding a text file
Attachment textAttachment = new Attachment(dataDir + "1.txt");
message.getAttachments().addItem(textAttachment);

// Adding an image file (JPEG format)
message.getAttachments().addItem(new Attachment(dataDir + "1.jpg"));

// Adding a Word document
message.getAttachments().addItem(new Attachment(dataDir + "1.doc"));

// Adding a RAR archive
message.getAttachments().addItem(new Attachment(dataDir + "1.rar"));

// Adding a PDF document
message.getAttachments().addItem(new Attachment(dataDir + "1.pdf"));
```

#### تعريف مسار دليل الإخراج

حدد المجلد الذي سيُحفظ فيه ملف MSG النهائي:

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY/";
```

#### حفظ رسالة البريد الإلكتروني (save email as msg)

```java
message.save(outputDir + "AddAttachmentToANewEmailMessage_out.msg", SaveOptions.getDefaultMsg());
```

## تطبيقات عملية

يبرز Aspose.Email للغة Java في العديد من السيناريوهات الواقعية:

1. **التقارير المؤتمتة:** توليد تقارير يومية/أسبوعية وإرسالها عبر البريد مع مرفقات PDF أو Excel.  
2. **أنظمة الإشعارات:** إرسال تنبيهات مع ملفات السجلات، لقطات الشاشة، أو نسخ احتياطية للتكوين مرفقة.  
3. **حلول النسخ الاحتياطي:** إرسال تفريغ قواعد البيانات أو ملفات الأرشيف عبر البريد لتخزينها خارج الموقع بشكل دوري.  

## اعتبارات الأداء

- **تحرير الكائنات:** استدعِ `message.dispose()` عندما لا تحتاج الرسالة لتفريغ الموارد الأصلية.  
- **تدفق المرفقات:** للملفات الكبيرة، استخدم التدفقات لتجنب تحميل الملف بالكامل في الذاكرة.  
- **تجميع الخيوط:** عند إرسال عدد كبير من الرسائل بشكل متزامن، أعد استخدام مجموعة خيوط لتقليل استهلاك JVM.  

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **فشل المرفق الكبير (>25 MB)** | تحقق من أن خادم SMTP (إن استخدم) يسمح بحجم حمولة كبير؛ زد حجم heap للـ JVM إذا لزم الأمر. |
| **المرفق لا يظهر** | تأكد من صحة مسار الملف وإمكانية الوصول إليه؛ تحقق من أذونات الملف. |
| **ملف MSG المحفوظ لا يمكن فتحه** | استخدم `SaveOptions.getDefaultMsg()` وتأكد من أنك تستخدم أحدث نسخة من Aspose.Email. |

## الأسئلة المتكررة

**س: كيف أضيف عدة مستلمين إلى البريد؟**  
ج: استخدم `message.getTo().addMailAddress(new MailAddress("email@example.com"));` لكل مستلم.

**س: هل يمكن لـ Aspose.Email التعامل مع مرفقات أكبر من 25 MB؟**  
ج: نعم، لكن يجب التأكد من أن الخادم والـ JVM يمتلكان ذاكرة كافية وأن أي وسيط SMTP يسمح بالرسائل الكبيرة.

**س: هل يمكن إرسال بريد إلكتروني بصيغة HTML باستخدام Aspose.Email؟**  
ج: بالتأكيد! عيّن `message.isBodyHtml(true);` وخصص محتوى HTML عبر `message.setHtmlBody("<h1>Hello</h1>");`.

**س: كيف يمكنني تتبع الأخطاء عند إرسال البريد؟**  
ج: احطّ الشيفرة بكتلة try‑catch، سجّل تتبع الاستثناء، وفعل تسجيل Aspose.Email عبر `License.setLogFolder("path")`.

**س: ما هي ممارسات الأمان التي يجب اتباعها؟**  
ج: تحقق من صحة جميع عناوين البريد، نظّف مسارات الملفات، ولا تدمج بيانات مقدمة من المستخدم مباشرةً في محتوى البريد دون تعقيم.

## الخلاصة

أصبح لديك الآن سير عمل كامل وجاهز للإنتاج **كيفية إرسال بريد إلكتروني** مع مرفقات، إرفاق ملفات بالبريد، و**حفظ البريد كملف MSG** باستخدام Aspose.Email للغة Java. استكشف الوثائق الكاملة عبر [documentation](https://reference.aspose.com/email/java/) لتغوص أعمق في ميزات متقدمة مثل إرسال عبر SMTP، إنشاء جسم HTML، والتشفير.

## الموارد
- [توثيق Aspose.Email](https://reference.aspose.com/email/java/)
- [تحميل Aspose.Email](https://releases.aspose.com/email/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [الوصول إلى نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- [تطبيق الترخيص المؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى دعم Aspose](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2025-12-14  
**تم الاختبار مع:** Aspose.Email 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}