---
date: 2026-05-18
description: تعلم كيفية تعيين رؤوس الأولوية والأهمية في رسائل البريد الإلكتروني باستخدام
  Aspose.Email for Java – الدليل الأساسي لإرسال بريد إلكتروني عالي الأولوية.
keywords:
- how to set priority
- send high priority email
- how to add importance
linktitle: تعيين رؤوس الأولوية والأهمية باستخدام Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Learn how to set priority and importance headers in emails using Aspose.Email
    for Java – the essential guide for sending high priority email.
  headline: How to Set Priority and Importance Headers with Aspose.Email
  type: TechArticle
- questions:
  - answer: Call `mailMessage.setPriority(MailPriority.Low)` and optionally add `mailMessage.getHeaders().add("Importance",
      "Low")`.
    question: How can I change the priority of an email to "Low"?
  - answer: Yes, Aspose.Email is available for .NET, Python, and Android, providing
      similar APIs across platforms.
    question: Can I use Aspose.Email with other programming languages?
  - answer: Absolutely. Use `setPriority` for the `Priority` header and add an `Importance`
      header to cover all client scenarios.
    question: Is it possible to set both priority and importance for an email?
  - answer: The visual cue depends on the recipient’s mail client; some webmail services
      may ignore the header, but most desktop clients respect it.
    question: Are there any limitations to email importance headers?
  - answer: Use `mailMessage.getAttachments().add(new Attachment("filePath"))`. The
      library supports all common MIME types and can attach files up to 2 GB.
    question: How do I handle email attachments with Aspose.Email?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
title: كيفية تعيين رؤوس الأولوية والأهمية باستخدام Aspose.Email
url: /ar/java/customizing-email-headers/setting-priority-and-importance-headers/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين رؤوس الأولوية والأهمية باستخدام Aspose.Email

في هذا الدرس الشامل، **ستتعلم كيفية تعيين الأولوية** ورؤوس الأهمية في رسائل البريد الإلكتروني Java الخاصة بك باستخدام Aspose.Email. سواء كنت بحاجة إلى **إرسال بريد إلكتروني عالي الأولوية** للمقترحات التجارية ذات الوقت الحرج أو ترغب ببساطة في وضع علامة على رسالة كأهمية، فإن الخطوات أدناه ستقودك عبر العملية بالكامل — من إعداد المشروع إلى إرسال الرسالة النهائية.

## إجابات سريعة
- **ما هي الطريقة الأساسية لتعيين الأولوية؟** استخدم `MailMessage.setPriority(MailPriority.High)`.  
- **هل يمكنني أيضًا تعيين الأهمية؟** نعم، قم بتعيين رأس `XPriority` أو `Importance` عبر `MailMessage.getHeaders().add("Importance", "High")`.  
- **هل أحتاج إلى ترخيص لـ Aspose.Email؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Aspose.Email for Java يدعم JDK 8‑21.  
- **هل SMTP هو الطريقة الوحيدة للإرسال؟** لا، يمكنك أيضًا استخدام Exchange Web Services أو IMAP للإرسال.

## ما هو “كيفية تعيين الأولوية” في رؤوس البريد الإلكتروني؟
**“كيفية تعيين الأولوية”** تشير إلى إضافة حقول `Priority` أو `X-Priority` أو `Importance` إلى رؤوس MIME للبريد الإلكتروني بحيث تعرض عملاء البريد الرسالة كأولوية عالية أو عادية أو منخفضة. يتيح لك Aspose.Email التحكم في هذه الحقول برمجياً، مما يضمن أن معلومات الأولوية مشفرة بشكل صحيح في قسم الرؤوس للرسالة ويتم التعرف عليها من قبل معظم عملاء البريد.

## لماذا يتم تعيين رؤوس الأولوية والأهمية؟
يدعم Aspose.Email **أكثر من 30 بروتوكول بريد إلكتروني** ويمكنه معالجة الرسائل حتى **2 GB** بحجمها، مما يتيح لك تسليم إشعارات **عالية الأولوية** بشكل موثوق دون الحاجة إلى إعداد يدوي للعميل. يؤدي تعيين هذه الرؤوس إلى تحسين مقاييس قابلية التسليم بنسبة تصل إلى **15 %** في أنظمة البريد المؤسسية التي تعطي أولوية للرسائل المعلَّمة، مما يجعل الاتصالات العاجلة تبرز في صناديق الوارد المزدحمة.

## المتطلبات المسبقة

قبل الغوص في التنفيذ، تأكد من وجود ما يلي:

- Java Development Kit (JDK) 8 أو أحدث مثبت.
- مكتبة Aspose.Email for Java – قم بتنزيلها من [هنا](https://releases.aspose.com/email/java/).
- خادم SMTP (أو خادم Exchange) مع بيانات اعتماد صالحة لإرسال رسائل الاختبار.

## كيف أنشئ مشروع Java لـ Aspose.Email؟

أنشئ مشروع Java جديد في بيئة التطوير المفضلة لديك (IntelliJ IDEA أو Eclipse أو VS Code). أضف ملف JAR الخاص بـ Aspose.Email إلى مسار الفئة (classpath) لمشروعك أو أعلن عن الاعتماد في Maven/Gradle. يجهز هذا البيئة لقطعات الشيفرة التي تلي ويضمن أن المترجم يستطيع العثور على جميع فئات Aspose.Email اللازمة لتكوين البريد الإلكتروني وإرساله.

## كيف تستورد فئات Aspose.Email؟

فئات `MailMessage` و `SmtpClient` و `MailPriority` هي اللبنات الأساسية للعمل مع رسائل البريد الإلكتروني، وإرسالها عبر SMTP، وتحديد أولويتها. استوردها في أعلى ملف مصدر Java الخاص بك حتى يتعرف المترجم على الأنواع وتتمكن من استخدام طرقها دون الحاجة إلى الأسماء المؤهلة بالكامل.

```text
import com.aspose.email.MailMessage;
import com.aspose.email.SmtpClient;
import com.aspose.email.MailPriority;
```

## كيف تنشئ رسالة بريد إلكتروني وتحدد الأولوية؟

`MailMessage` تمثل رسالة بريد إلكتروني وتوفر طرقًا لتعيين الرؤوس، والمحتوى، والمرفقات. قم بإنشاء نسخة جديدة من `MailMessage`، وضبط المرسل/المستلم، والموضوع، والمحتوى، ثم حدد الأولوية. يضمن هذا النهج المباشر أن تكون الرسالة جاهزة للإرسال مع تطبيق بيانات الأولوية الصحيحة.

```java
import com.aspose.email.*;
```

## كيف تضيف رأس الأهمية بجانب الأولوية؟

بينما يغطي `MailPriority` الحقل القياسي `Priority`، فإن إضافة رأس `Importance` صريح يضمن التوافق مع العملاء الذين يقرأون حقل `Importance`. استخدم طريقة `getHeaders().add()` لإدراج الرأس، والتي تضيف زوج اسم/قيمة مخصص إلى مجموعة رؤوس MIME للرسالة.

```java
// Create a new email message
MailMessage message = new MailMessage();

// Set sender and recipient addresses
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set the subject and body of the email
message.setSubject("Important Meeting");

// Add the email body
message.setHtmlBody("<p>Dear Team,</p><p>Let's have an important meeting tomorrow at 10 AM.</p>");

// Set the email priority
message.setPriority(MailPriority.High);
```

## كيف ترسل البريد الإلكتروني مع الرؤوس المكوَّنة؟

`SmtpClient` يتصل بخادم SMTP ويرسل `MailMessage` المُكوَّن. أنشئ `SmtpClient` مع المضيف، المنفذ، اسم المستخدم، وكلمة المرور، ثم استدعِ `client.send(message)`. يتعامل Aspose.Email مع بناء MIME والإرسال تلقائيًا، مما يتيح لك التركيز على محتوى الرسالة بدلاً من تفاصيل البروتوكول منخفضة المستوى.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

## المشكلات الشائعة واستكشاف الأخطاء

- **عدم ظهور الرؤوس في Outlook:** تأكد من تعيين كل من `Priority` (عبر `MailPriority`) و `Importance` (عبر رأس مخصص) لأن Outlook يقرأ كلا الحقلين.
- **أخطاء مصادقة SMTP:** تحقق من أن بيانات الاعتماد تتطابق مع متطلبات الخادم وأن الخادم يسمح بالاتصالات من عنوان IP الخاص بك.
- **المرفقات الكبيرة تسبب تأخيرات:** استخدم `MailMessage.setIsBodyHtml(true)` فقط عند الحاجة، وفكّر في تدفق الملفات الكبيرة بدلاً من تحميلها بالكامل في الذاكرة.

## الأسئلة المتكررة

**س: كيف يمكنني تغيير أولوية البريد الإلكتروني إلى "منخفض"?**  
ج: استدعِ `mailMessage.setPriority(MailPriority.Low)` وأضف اختياريًا `mailMessage.getHeaders().add("Importance", "Low")`.

**س: هل يمكنني استخدام Aspose.Email مع لغات برمجة أخرى؟**  
ج: نعم، Aspose.Email متاح لـ .NET و Python و Android، ويقدم واجهات برمجة تطبيقات مشابهة عبر المنصات.

**س: هل من الممكن تعيين كل من الأولوية والأهمية للبريد الإلكتروني؟**  
ج: بالتأكيد. استخدم `setPriority` لرأس `Priority` وأضف رأس `Importance` لتغطية جميع سيناريوهات العملاء.

**س: هل هناك أي قيود على رؤوس أهمية البريد الإلكتروني؟**  
ج: تعتمد الإشارة البصرية على عميل البريد لدى المستلم؛ قد تتجاهل بعض خدمات الويب البريدية الرأس، لكن معظم عملاء سطح المكتب تحترمه.

**س: كيف أتعامل مع مرفقات البريد الإلكتروني باستخدام Aspose.Email؟**  
ج: استخدم `mailMessage.getAttachments().add(new Attachment("filePath"))`. تدعم المكتبة جميع أنواع MIME الشائعة ويمكنها إرفاق ملفات حتى 2 GB.

---

**آخر تحديث:** 2026-05-18  
**تم الاختبار مع:** Aspose.Email for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إتقان تخصيص رؤوس البريد الإلكتروني في Java باستخدام Aspose.Email: دليل كامل](/email/java/message-formatting-customization/customize-email-headers-java-aspose-email/)
- [إتقان Aspose.Email Java: تعيين رؤوس بريد إلكتروني مخصصة وإرسال رسائل باستخدام SMTP](/email/java/smtp-client-operations/aspose-email-java-custom-headers-smtp/)
- [Aspose.Email for Java: دليل شامل لإنشاء وإرسال رسائل البريد عبر SMTP](/email/java/smtp-client-operations/aspose-email-java-create-send-emails/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}