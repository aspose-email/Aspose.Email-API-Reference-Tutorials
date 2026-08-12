---
date: 2026-04-05
description: تعلم كيفية حفظ بريد إلكتروني بصيغة EML، وإضافة رؤوس مخصصة، وإرسال البريد
  عبر SMTP باستخدام Aspose.Email للغة Java. يتضمن خطوات استخراج الرأس المخصص وتعيين
  بيانات تعريف البريد الإلكتروني.
keywords:
- save email eml
- send email smtp
- extract custom header
- how to add x-header
- add custom header java
linktitle: إدارة رؤوس X في رسائل البريد الإلكتروني باستخدام Aspose.Email
second_title: Aspose.Email Java Email Management API
title: كيفية حفظ ملف EML للبريد الإلكتروني وإضافة رؤوس – إدارة رؤوس X باستخدام Aspose.Email
url: /ar/java/customizing-email-headers/managing-x-headers-in-email-messages/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حفظ بريد إلكتروني بصيغة EML وإضافة رؤوس – إدارة X‑Headers باستخدام Aspose.Email

## مقدمة

إذا كنت بحاجة إلى **حفظ ملفات بريد إلكتروني بصيغة EML** مع إرفاق بيانات تعريف مخصصة، فأنت في المكان المناسب. في هذا البرنامج التعليمي سنستعرض إضافة X‑Headers إلى رسالة، حفظ البريد كملف EML، ثم إرساله عبر SMTP. ستتعرف أيضًا على كيفية **استخراج قيم رؤوس مخصصة** من البريد المستلم ولماذا يمكن أن يبسط تعيين بيانات تعريف البريد المعالجة اللاحقة في تطبيقات Java.

## إجابات سريعة
- **ما هو الغرض الأساسي من X‑Headers؟** لتخزين بيانات تعريف مخصصة لا يغطيها رؤوس RFC القياسية.  
- **أي مكتبة تساعدك على إضافة رؤوس في Java؟** Aspose.Email for Java.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Email صالح.  
- **هل يمكنني قراءة X‑Headers من البريد المستلم؟** بالتأكيد—استخدم `MailMessage.getHeaders()` لاسترجاعها.  
- **هل SMTP هو الطريقة الوحيدة لإرسال البريد؟** لا، Aspose.Email يدعم أيضًا POP3 و IMAP وخدمات Exchange Web Services.

## كيفية حفظ بريد إلكتروني بصيغة EML باستخدام Aspose.Email
حفظ بريد إلكتروني كملف EML يحافظ على كل رأس — بما في ذلك X‑Headers المخصصة — تمامًا كما سيظهر على الشبكة. هذا مثالي عندما تحتاج إلى أرشفة الرسائل، أو إعادة توجيهها لاحقًا، أو تسليمها إلى نظام آخر يتوقع ملف MIME خام.

## ما هي X‑Headers؟
X‑Headers، اختصارًا لـ “eXtended Headers”، هي رؤوس بريد إلكتروني مخصصة تسمح لك بإدراج معلومات إضافية في رسالة البريد. هذه الرؤوس ليست جزءًا من أي معيار رسمي، مما يمنحك المرونة لتعريف حقول البيانات التعريفية الخاصة بك.

## لماذا نستخدم X‑Headers؟
- **بيانات تعريف مخصصة:** إرفاق بيانات خاصة بالأعمال (معرفات الطلبات، رموز المستخدم، إلخ) دون تعديل محتوى البريد.  
- **التصفية والتوجيه:** يمكن لخوادم البريد والعملاء إنشاء قواعد بناءً على القيم التي تحددها.  
- **التتبع والتدقيق:** سجل خطوات المعالجة، الطوابع الزمنية، أو فحوصات الأمان مباشرة في رأس الرسالة.  
- **تعيين بيانات تعريف البريد:** استخدم X‑Headers لنقل المعلومات التي تحتاجها الخدمات اللاحقة للتوجيه أو التحليل.

## المتطلبات المسبقة
- معرفة أساسية ببرمجة Java.  
- تثبيت Java Development Kit (JDK).  
- مكتبة Aspose.Email for Java، التي يمكنك تنزيلها من [here](https://releases.aspose.com/email/java/).  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## كيفية إضافة رؤوس إلى رسائل البريد الإلكتروني

### الخطوة 1: إعداد مشروع Java الخاص بك
أنشئ مشروع Java جديد في بيئة التطوير الخاصة بك وأضف ملف Aspose.Email JAR إلى مسار الفئات (classpath) للمشروع. سيتيح لك ذلك الوصول إلى `MailMessage` و `SmtpClient` والفئات المرتبطة.

### الخطوة 2: إنشاء رسالة بريد إلكتروني وتعيين رأس بريد مخصص
فيما يلي مثال كامل ينشئ بريدًا إلكترونيًا ترحيبيًا بسيطًا و **يحدد رؤوس بريد مخصصة** (`X‑Custom‑Header1` و `X‑Custom‑Header2`). كتلة الشيفرة لم تتغير عن البرنامج التعليمي الأصلي.

```java
// Import necessary classes
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();

// Set the sender's and recipient's email addresses
message.setFrom("your@email.com");
message.setTo("recipient@email.com");

// Set the subject and body of the email
message.setSubject("Welcome to Our Service");
message.setHtmlBody("<p>Dear User, welcome to our platform!</p>");

// Add custom X-Headers
message.getHeaders().add("X-Custom-Header1", "Value1");
message.getHeaders().add("X-Custom-Header2", "Value2");

// Save the email as an EML file
message.save("welcome_email.eml", SaveOptions.getDefaultEml());
```

> **نصيحة احترافية:** استخدم أسماء رؤوس ذات معنى (مثل `X-Order-ID`) لتسهيل المعالجة اللاحقة.

### الخطوة 3: إرسال البريد عبر SMTP
الآن أرسل الرسالة باستخدام بروتوكول SMTP. استبدل القيم النائبة بتفاصيل الخادم الفعلية الخاصة بك.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.server.com", 587, "your@email.com", "your_password");

// Send the email
client.send(message);
```

### الخطوة 4: قراءة X‑Headers من رسالة مستلمة
عند استلام بريد إلكتروني، يمكنك استخراج الرؤوس المخصصة بسهولة. يوضح هذا **كيفية إضافة قيم x-header** ثم **استخراج بيانات الرأس المخصص** لاحقًا.

```java
// Load an EML file containing the received email
MailMessage receivedMessage = MailMessage.load("received_email.eml");

// Get the value of a custom X-Header
String customHeaderValue = receivedMessage.getHeaders().get("X-Custom-Header1");
```

## المشكلات الشائعة وكيفية تجنّبها
| المشكلة | السبب | الحل |
|-------|----------------|----------|
| تعارض اسم الرأس مع رؤوس قياسية | استخدام اسم موجود بالفعل (مثل `X-Subject`) قد يسبب ارتباكًا. | أضف بادئة لأسماءك المخصصة بمعرف فريد، مثل `X-MyApp-`. |
| عدم حفظ الرؤوس عند حفظ كـ `MSG` | بعض الصيغ تتجاهل الرؤوس غير القياسية. | يفضل استخدام `EML` للحفاظ الكامل على الرؤوس، أو استخدم `MailMessage.save` مع الخيارات المناسبة. |
| مشكلات الترميز للقيم غير ASCII | قد تكون قيم الرؤوس التي تحتوي على أحرف خاصة مشوهة. | استخدم `MimeUtility.encodeText` أو حدد مجموعة الأحرف المناسبة عند إضافة الرؤوس. |

## الأسئلة المتكررة

**س: كيف أقوم بتثبيت Aspose.Email for Java؟**  
ج: قم بتنزيل المكتبة من [here](https://releases.aspose.com/email/java/)، أضف ملف JAR إلى مسار الفئات (classpath) لمشروعك، وستكون جاهزًا للبدء.

**س: هل يمكنني استخدام X‑Headers لتصفية البريد؟**  
ج: نعم. يمكن لعملاء الخوادم والبريد إنشاء قواعد تعتمد على قيم الرؤوس المخصصة، مما يتيح سيناريوهات فرز وتوجيه قوية.

**س: هل X‑Headers موحدة (معيارية)؟**  
ج: لا. هي حرة الشكل، مما يمنحك مرونة ولكنه يتطلب منك تعريف وتوثيق قواعد التسمية الخاصة بك.

**س: كيف يمكنني قراءة X‑Headers من رسائل البريد المستلمة؟**  
ج: حمّل البريد باستخدام `MailMessage.load` واستدعِ `getHeaders().get("<Header-Name>")` كما هو موضح في مثال الشيفرة.

**س: هل Aspose.Email مناسب لإدارة البريد على مستوى المؤسسات؟**  
ج: بالتأكيد. فهو يوفر API شاملة لإنشاء وإرسال واستلام ومعالجة الرسائل على نطاق واسع، مما يجعله خيارًا قويًا لتطبيقات المؤسسات.

---

**آخر تحديث:** 2026-04-05  
**تم الاختبار مع:** Aspose.Email for Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}