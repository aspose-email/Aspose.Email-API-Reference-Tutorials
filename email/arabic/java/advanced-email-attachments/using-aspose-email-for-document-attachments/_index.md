---
date: 2026-02-14
description: تعلم كيفية إرسال بريد إلكتروني جافا مع مرفقات باستخدام Aspose.Email.
  يغطي مرفق بريد SMTP جافا، مرفق PDF جافا، ودورة Aspose.Email لجافا.
linktitle: Using Aspose.Email for Document Attachments
second_title: Aspose.Email Java Email Management API
title: إرسال بريد إلكتروني جافا مع مرفق باستخدام Aspose.Email
url: /ar/java/advanced-email-attachments/using-aspose-email-for-document-attachments/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إرسال بريد إلكتروني Java مع مرفق باستخدام Aspose.Email

## مقدمة لاستخدام Aspose.Email لمرفقات المستندات في Java

في هذا البرنامج التعليمي ستتعلم **كيفية إرسال بريد إلكتروني Java** مع مرفقات مستندات باستخدام مكتبة Aspose.Email for Java القوية. سواءً كنت تبني نظام إشعارات آلي، أداة إرسال بريد جماعي، أو خدمة تقارير، فإن التعامل مع ملفات PDF أو Word كمرفقات بريد إلكتروني هو طلب شائع. سنستعرض إعداد المكتبة، إنشاء رسالة، إرفاق الملفات، إرسال أو حفظ البريد الإلكتروني، وأخيرًا استخراج المرفقات من الرسائل الواردة.

## إجابات سريعة
- **ما المكتبة التي تسمح لي بإرسال بريد إلكتروني Java؟** Aspose.Email for Java  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** نعم، يلزم وجود ترخيص تجاري للاستخدام في بيئة الإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وما فوق.  
- **هل يمكنني إرفاق ملفات متعددة؟** بالتأكيد – فقط أضف كائنات `Attachment` إضافية.  
- **هل يدعم البث للملفات الكبيرة؟** نعم، توفر Aspose.Email واجهات برمجة تطبيقات البث للتعامل مع المرفقات الكبيرة بكفاءة.

## ما هو “إرسال بريد إلكتروني Java مع مرفق”؟

إرسال بريد إلكتروني مع مرفق في Java يعني إنشاء كائن `MailMessage`، إضافة كائن أو أكثر من `Attachment`، ثم توصيل الرسالة عبر SMTP أو حفظها في ملف. تقوم Aspose.Email بتجريد التعامل منخفض المستوى مع MIME، مما يتيح لك التركيز على منطق الأعمال بدلاً من رؤوس MIME الخام.

## لماذا تستخدم Aspose.Email لهذه المهمة؟

- **Rich API** – تحكم كامل في أجزاء MIME وأنواع المحتوى والترميز.  
- **Cross‑platform** – يعمل على Windows وLinux وmacOS دون الحاجة إلى تبعيات أصلية إضافية.  
- **Built‑in streaming** – معالجة ملفات PDF أو Word الكبيرة دون استنزاف الذاكرة.  
- **Comprehensive documentation** – الأمثلة ومرجع API تجعل التنفيذ سريعًا.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

- مجموعة تطوير Java (JDK) الإصدار 8 أو أعلى مثبتة.  
- مكتبة Aspose.Email for Java. يمكنك تنزيلها من [هنا](https://releases.aspose.com/email/java/).

## إضافة Aspose.Email إلى مشروعك

للبدء، تحتاج إلى إضافة مكتبة Aspose.Email إلى مشروع Java الخاص بك. اتبع الخطوات التالية:

1. قم بتنزيل مكتبة Aspose.Email for Java من الرابط المقدم.  
2. استخرج ملف ZIP الذي تم تنزيله إلى دليل من اختيارك.  
3. في مشروع Java الخاص بك، أضف ملفات JAR الخاصة بـ Aspose.Email إلى مسار الفئة (classpath). يمكنك القيام بذلك في بيئة التطوير المتكاملة (IDE) المفضلة لديك أو باستخدام سطر الأوامر.

## إنشاء رسالة بريد إلكتروني جديدة

لنبدأ بإنشاء رسالة بريد إلكتروني جديدة مع مرفق مستند. سنستخدم مثالًا بسيطًا لتوضيح **كيفية إرسال بريد إلكتروني Java** مع مرفق:

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

في هذا المثال نقوم بـ:

- إنشاء كائن `MailMessage`.  
- تحديد المرسل، المستلم، الموضوع، والنص.  
- إنشاء `Attachment` يشير إلى ملف PDF وإضافته إلى الرسالة.  
- حفظ الرسالة كملف EML (يمكنك أيضًا إرسالها عبر SMTP).

## استخراج مرفقات المستندات

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

الكود:

- يقوم بتحميل ملف `.eml` موجود.  
- يتجول عبر جميع المرفقات.  
- يحفظ أي مرفق ينتهي اسمه بـ `.pdf`.

## حالات الاستخدام الشائعة لإرسال بريد إلكتروني Java مع مرفقات

- **Automated reporting:** إنشاء تقارير PDF يومية وإرسالها عبر البريد الإلكتروني إلى أصحاب المصلحة.  
- **Invoice distribution:** إرفاق فواتير Word أو PDF التي تم إنشاؤها مع تأكيدات الطلب الصادرة.  
- **Document approval workflows:** إرسال العقود كمرفقات يمكن للمستلمين مراجعتها وتوقيعها.  
- **Bulk marketing campaigns:** تضمين كتيبات أو كتالوجات المنتجات كمرفقات PDF لكل مستلم.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **Attachment not received** | نوع MIME غير صحيح أو عدم استدعاء `addAttachment` | تحقق من أن `Attachment` مضاف قبل الإرسال/الحفظ. |
| **Large files cause OutOfMemoryError** | تحميل الملف بالكامل إلى الذاكرة | استخدم واجهات البث (`Attachment` constructor that accepts `InputStream`). |
| **File name corrupted** | ترميز غير صحيح لاسم الملف | عيّن `attachment.setName("myDocument.pdf")` صراحةً. |

## الأسئلة المتكررة

**س: كيف يمكنني إرسال بريد إلكتروني مع مرفقات مستندات متعددة؟**  
ج: ببساطة أنشئ كائنات `Attachment` إضافية واستدعِ `message.addAttachment()` لكل ملف.

**س: هل يمكنني العمل مع مرفقات غير مستندات PDF؟**  
ج: نعم، تدعم Aspose.Email ملفات Word وExcel والصور وأي نوع ملف متوافق مع MIME.

**س: كيف أتعامل مع مرفقات مستندات كبيرة؟**  
ج: استخدم تقنيات البث—مرّر `InputStream` إلى مُنشئ `Attachment` لتجنب تحميل الملف بالكامل إلى الذاكرة.

**س: هل هناك طريقة لتعيين أنواع محتوى مخصصة؟**  
ج: بالتأكيد. يمكنك تعديل `ContentType` لمرفق `Attachment` عبر `attachment.setContentType(...)`.

**س: هل تدعم Aspose.Email مرفقات مشفرة بـ S/MIME؟**  
ج: نعم، تتضمن المكتبة واجهات برمجة تطبيقات للتوقيع وتشفير الرسائل، بما في ذلك مرفقاتها.

## الخلاصة

في هذا البرنامج التعليمي، عرضنا **كيفية إرسال بريد إلكتروني Java** مع مرفقات مستندات باستخدام Aspose.Email. الآن تعرف كيف تُعد المكتبة، تنشئ رسائل مع ملفات PDF أو أنواع مستندات أخرى، وتستخرج تلك المرفقات من البريد الوارد. هذه القدرة أساسية لبناء أتمتة بريد إلكتروني قوية، أنظمة تقارير، أو أي تطبيق Java يحتاج لتبادل المستندات عبر البريد الإلكتروني.

---

**آخر تحديث:** 2026-02-14  
**تم الاختبار مع:** Aspose.Email for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}