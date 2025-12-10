---
date: 2025-12-10
description: تعلم كيفية إرسال بريد إلكتروني مع مرفق باستخدام Aspose.Email في Java.
  إدارة وإنشاء واستخراج مرفقات المستندات في Java بكفاءة.
linktitle: Using Aspose.Email for Document Attachments
second_title: Aspose.Email Java Email Management API
title: إرسال بريد إلكتروني مع مرفق باستخدام Java و Aspose.Email
url: /ar/java/advanced-email-attachments/using-aspose-email-for-document-attachments/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إرسال بريد إلكتروني مع مرفق Java باستخدام Aspose.Email

## مقدمة لاستخدام Aspose.Email لمرفقات المستندات في Java

في هذا الدليل سنرشدك إلى **how to send email with attachment java** باستخدام مكتبة Aspose.Email for Java القوية. سواءً كنت تبني نظام إشعارات آلي أو أداة إرسال بريد جماعي، فإن معالجة مرفقات المستندات هي متطلب شائع. سنغطي كل شيء بدءًا من إعداد المكتبة إلى إنشاء الرسائل، وإرسالها، واستخراج ملفات PDF أو Word المرفقة.

## إجابات سريعة
- **ما المكتبة التي تسمح لي بإرسال بريد إلكتروني مع مرفق java؟** Aspose.Email for Java  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري للاستخدام في بيئة الإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وأحدث.  
- **هل يمكنني إرفاق ملفات متعددة؟** بالتأكيد – فقط أضف كائنات `Attachment` إضافية.  
- **هل يدعم البث للملفات الكبيرة؟** نعم، توفر Aspose.Email واجهات برمجة تطبيقات البث للتعامل مع المرفقات الكبيرة بكفاءة.

## ما هو “send email with attachment java”

إرسال بريد إلكتروني مع مرفق في Java يعني إنشاء `MailMessage`، وإضافة كائن أو أكثر من كائنات `Attachment`، ثم تسليم الرسالة عبر SMTP أو حفظها في ملف. تقوم Aspose.Email بتجريد معالجة MIME منخفضة المستوى، مما يتيح لك التركيز على منطق الأعمال.

## لماذا تستخدم Aspose.Email لهذه المهمة؟

- **واجهة برمجة تطبيقات غنية** – تحكم كامل في أجزاء MIME، وأنواع المحتوى، والترميز.  
- **متعددة المنصات** – تعمل على Windows وLinux وmacOS دون تبعيات أصلية إضافية.  
- **بث مدمج** – التعامل مع ملفات PDF أو Word الكبيرة دون استنزاف الذاكرة.  
- **توثيق شامل** – الأمثلة ومرجع API يجعل التنفيذ سريعًا.

## المتطلبات المسبقة

- Java Development Kit (JDK) 8 أو أعلى مثبت.  
- مكتبة Aspose.Email for Java. يمكنك تنزيلها من [here](https://releases.aspose.com/email/java/).

## إضافة Aspose.Email إلى مشروعك

للبدء، تحتاج إلى إضافة مكتبة Aspose.Email إلى مشروع Java الخاص بك. اتبع الخطوات التالية:

1. قم بتنزيل مكتبة Aspose.Email for Java من الرابط المقدم.  
2. فك ضغط ملف ZIP الذي تم تنزيله إلى دليل من اختيارك.  
3. في مشروع Java الخاص بك، أضف ملفات JAR الخاصة بـ Aspose.Email إلى classpath. يمكنك القيام بذلك في بيئة التطوير المتكاملة (IDE) المفضلة لديك أو باستخدام سطر الأوامر.

## إنشاء رسالة بريد إلكتروني جديدة

لنبدأ بإنشاء رسالة بريد إلكتروني جديدة مع مرفق مستند. سنستخدم مثالًا بسيطًا لتوضيح **how to send email with attachment java**:

> **نصيحة:** ضع مقتطف الشيفرة أدناه بعد شرح المتطلبات المسبقة حتى يفهم القراء السياق قبل رؤية التنفيذ الفعلي.

```java
import com.aspose.email.Attachment;
import com.aspose.email.MailMessage;

public class CreateEmailWithAttachment {
    public static void main(String[] args) {
        // Create a new email message
        MailMessage message = new MailMessage();

        // Set the sender and recipient email addresses
        message.setFrom("sender@example.com");
        message.setTo("recipient@example.com");

        // Set the subject and body of the email
        message.setSubject("Document Attachment Example");
        message.setBody("Please find the attached document.");

        // Attach a document file to the email
        Attachment attachment = new Attachment("path/to/your/document.pdf");
        message.addAttachment(attachment);

        // Save the email message to a file or send it using SMTP
        message.save("attachment_email.eml");
    }
}
```

في هذا المثال نحن:

- إنشاء كائن `MailMessage`.  
- تحديد المرسل، المستلم، الموضوع، والنص.  
- إنشاء `Attachment` يشير إلى ملف PDF وإضافته إلى الرسالة.  
- حفظ الرسالة كملف EML (يمكنك أيضًا إرسالها عبر SMTP).

## استرجاع مرفقات المستندات

قد تحتاج إلى استخراج والعمل مع مرفقات المستندات من رسائل البريد الواردة. إليك كيفية تحميل بريد إلكتروني واستخراج ملفات PDF:

> **نصيحة احترافية:** استخدم الفحص `getContentType().getName()` لتصفية أنواع الملفات التي تهمك فقط.

```java
import com.aspose.email.Attachment;
import com.aspose.email.MailMessage;

public class ExtractAttachments {
    public static void main(String[] args) {
        // Load an email message from a file or receive it using SMTP
        MailMessage message = MailMessage.load("received_email.eml");

        // Iterate through attachments and save document attachments
        for (Attachment attachment : message.getAttachments()) {
            if (attachment.getContentType().getName().endsWith("pdf")) {
                attachment.save("document_attachment.pdf");
            }
        }
    }
}
```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **لم يتم استلام المرفق** | نوع MIME غير صحيح أو عدم استدعاء `addAttachment` | تأكد من إضافة `Attachment` قبل الإرسال/الحفظ. |
| **الملفات الكبيرة تسبب OutOfMemoryError** | تحميل الملف بالكامل في الذاكرة | استخدم واجهات البث (`Attachment` constructor الذي يقبل `InputStream`). |
| **اسم الملف فاسد** | ترميز غير صحيح لاسم الملف | عيّن `attachment.setName("myDocument.pdf")` صراحةً. |

## الأسئلة المتكررة

**س: كيف يمكنني إرسال بريد إلكتروني مع مرفقات مستندات متعددة؟**  
ج: ببساطة أنشئ كائنات `Attachment` إضافية واستدعِ `message.addAttachment()` لكل ملف.

**س: هل يمكنني العمل مع مرفقات غير ملفات PDF؟**  
ج: نعم، يدعم Aspose.Email ملفات Word وExcel والصور وأي نوع ملف متوافق مع MIME.

**س: كيف أتعامل مع مرفقات المستندات الكبيرة؟**  
ج: استخدم تقنيات البث—مرّر `InputStream` إلى مُنشئ `Attachment` لتجنب تحميل الملف بالكامل في الذاكرة.

**س: هل هناك طريقة لتعيين أنواع محتوى مخصصة؟**  
ج: بالتأكيد. يمكنك تعديل `ContentType` لمرفق `Attachment` عبر `attachment.setContentType(...)`.

**س: هل يدعم Aspose.Email مرفقات S/MIME المشفرة؟**  
ج: نعم، تتضمن المكتبة واجهات برمجة تطبيقات لتوقيع وتشفير الرسائل، بما في ذلك مرفقاتها.

## الخلاصة

في هذا الدليل، عرضنا **how to send email with attachment java** باستخدام Aspose.Email. الآن تعرف كيف تُعد المكتبة، وتُنشئ رسائل مع مرفقات PDF أو مستندات أخرى، وتستخرج تلك المرفقات من البريد الوارد. هذه القدرة أساسية لبناء أتمتة بريد إلكتروني قوية، وأنظمة تقارير، أو أي تطبيق Java يحتاج إلى تبادل المستندات عبر البريد الإلكتروني.

---

**آخر تحديث:** 2025-12-10  
**تم الاختبار مع:** Aspose.Email for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}