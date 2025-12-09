---
date: 2025-12-01
description: تعلم كيفية إرسال بريد إلكتروني مع صورة مدمجة باستخدام Aspose.Email للغة
  Java. يوضح هذا الدليل كيفية تضمين الصور في البريد الإلكتروني وإنشاء بريد إلكتروني
  HTML بلغة Java مع مرفقات مدمجة.
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: كيفية إرسال بريد إلكتروني مع صورة مدمجة باستخدام Aspose.Email للـ Java
url: /ar/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إرسال بريد إلكتروني مع صورة مدمجة باستخدام Aspose.Email for Java

إدراج الصور مباشرة داخل البريد الإلكتروني يجعل رسائلك تبدو مصقولة ويضمن أن المتلقي يرى الرسومات دون الحاجة إلى تنزيل ملفات منفصلة. في هذا البرنامج التعليمي ستتعلم **كيفية إرسال بريد إلكتروني مع صورة مدمجة** باستخدام Aspose.Email for Java، مع تغطية كل شيء من إعداد المكتبة إلى إنشاء بريد إلكتروني بصيغة HTML، وإضافة الموارد المضمنة، وأخيرًا إرسال الرسالة.

## إجابات سريعة
- **ما هي الفئة الأساسية للصور المضمنة؟** `LinkedResource`
- **أي طريقة تشير إلى الصورة في HTML؟** استخدم `cid:yourContentId` في وسم `<img>`
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج
- **هل يمكنني إرسال البريد عبر أي خادم SMTP؟** نعم، فقط قم بتكوين `SmtpClient` بتفاصيل خادمك
- **هل هذا النهج متوافق مع جميع عملاء البريد الإلكتروني الرئيسيين؟** معظم العملاء الحديثين (Outlook, Gmail, Thunderbird) يدعمون الصور المدمجة عبر CID

## ما هي المرفقات المضمنة (الصور المدمجة)؟

المرفقات المضمنة — تُعرف أحيانًا بالصور المدمجة أو صور CID — هي ملفات توجد داخل جسم MIME للبريد الإلكتروني. يتم الإشارة إليها من الجزء HTML للرسالة باستخدام **Content‑ID** (CID). تتيح لك هذه التقنية **إدراج صور في البريد الإلكتروني** بحيث تظهر حيثما تضع وسم `<img>`، دون أن تظهر كمرفقات قابلة للتنزيل منفصلة.

## لماذا تستخدم الصور المدمجة في رسائل Java البريدية الخاصة بك؟

- **مظهر احترافي:** الشعارات، واللافتات، وصور المنتجات تُعرض فورًا.
- **تفاعل أفضل:** المتلقون أكثر احتمالًا لقراءة بريد إلكتروني يبدو مكتملًا.
- **لا نقرات إضافية:** لا يحتاج المستخدمون إلى تنزيل مرفق لرؤية الصورة.
- **علامة تجارية متسقة:** تبقى أصول علامتك التجارية ضمن محتوى الرسالة.

## المتطلبات المسبقة

- مكتبة Aspose.Email for Java (حمّلها من [توثيق Aspose.Email for Java الرسمي](https://reference.aspose.com/email/java/))
- بيئة تطوير Java 8+
- الوصول إلى خادم SMTP لإرسال البريد
- ملف الصورة الذي تريد دمجه (مثال: `logo.png`)

## دليل خطوة بخطوة

### الخطوة 1: إنشاء رسالة بريد إلكتروني HTML أساسية

أولاً، قم بإعداد `MailMessage` بسيط مع جسم HTML. سيكون هذا القالب حيث سنقوم لاحقًا بدمج الصورة.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### الخطوة 2: إضافة صورة مدمجة باستخدام `LinkedResource`

الآن نقوم بدمج صورة. تمثل فئة `LinkedResource` المرفق المضمن. عيّن **Content‑ID** فريدًا وأشر إليه في جسم HTML باستخدام `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **نصيحة احترافية:** اجعل `ContentId` بسيطًا وفريدًا داخل الرسالة لتجنب التعارضات.

### الخطوة 3: إرسال البريد عبر `SmtpClient`

قم بتكوين إعدادات SMTP الخاصة بك وأرسل الرسالة. الصورة المدمجة تنتقل مع البريد الإلكتروني، لذا يرى المتلقي الصورة فورًا.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### الخطوة 4: استلام واستخراج الصور المدمجة (اختياري)

إذا كنت بحاجة إلى معالجة الرسائل الواردة التي تحتوي على صور مدمجة، يمكنك تحميل ملف `.eml` والوصول إلى `LinkedResources` الخاصة به.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## المشكلات الشائعة وكيفية حلها

| المشكلة | سبب حدوثه | الحل |
|-------|----------------|-----|
| **عدم تطابق Content‑ID** | الإشارة `cid:` في HTML لا تتطابق مع `ContentId` المحدد في `LinkedResource`. | تأكد من أن السلاسل متطابقة (`image001` مقابل `cid:image001`). |
| **الملف غير موجود** | مسار الصورة غير صحيح أو الملف مفقود. | تحقق من المسار المطلق/النسبي وتأكد من وجود الملف على الخادم. |
| **فشل مصادقة SMTP** | بيانات اعتماد أو إعدادات الخادم غير صحيحة. | تحقق مرة أخرى من المضيف، المنفذ، اسم المستخدم، وكلمة المرور. فعّل TLS/SSL إذا لزم الأمر. |
| **عدم عرض الصورة في بعض العملاء** | بعض العملاء يحظرون الموارد الخارجية. | استخدم صورًا مدمجة عبر CID (كما هو موضح) بدلاً من الروابط الخارجية. |

## الأسئلة المتكررة

**س: كيف يمكنني تنزيل Aspose.Email for Java؟**  
ج: يمكنك تنزيل Aspose.Email for Java من [التوثيق](https://reference.aspose.com/email/java/). اتبع تعليمات التثبيت لإعداده في مشروعك.

**س: هل يمكنني استخدام Aspose.Email for Java مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.Email بسلاسة مع مكتبات Java الأخرى، مما يتيح لك دمج معالجة البريد مع إنشاء PDF أو OCR أو الوصول إلى قواعد البيانات.

**س: ما هي صيغ الملفات المدعومة للمرفقات المضمنة؟**  
ج: صيغ الصور الشائعة مثل PNG، JPEG، GIF، بالإضافة إلى أنواع مستندات أخرى (مثل SVG) مدعومة كموارد مدمجة.

**س: كيف أتعامل مع المرفقات المضمنة في رسائل HTML؟**  
ج: استخدم فئة `LinkedResource` لتعيين `ContentId`، أضفه إلى `message.getLinkedResources()`، وأشر إليه في جسم HTML باستخدام `<img src='cid:yourContentId'>`.

**س: هل Aspose.Email for Java متوافق مع خوادم البريد المختلفة؟**  
ج: نعم، يعمل مع أي خادم SMTP/IMAP/POP3. فقط قدّم عنوان الخادم الصحيح، المنفذ، وتفاصيل المصادقة.

---

**آخر تحديث:** 2025-12-01  
**تم الاختبار مع:** Aspose.Email for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}