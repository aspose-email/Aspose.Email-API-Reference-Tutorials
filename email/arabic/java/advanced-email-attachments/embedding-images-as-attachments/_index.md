---
date: 2026-04-21
description: تعلم كيفية تضمين صورة في بريد إلكتروني HTML باستخدام Aspose.Email للغة
  Java، وإرسال بريد إلكتروني HTML مع صورة مدمجة، وتقليل حجم مرفق البريد الإلكتروني.
keywords:
- embed image html email
- send html email java
- create email with image
- reduce email attachment size
- embed multiple images email
linktitle: كيفية إرفاق صورة إلى البريد الإلكتروني باستخدام Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: كيفية تضمين صورة في بريد إلكتروني HTML باستخدام Aspose.Email للغة Java
url: /ar/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تضمين صورة بريد إلكتروني HTML باستخدام Aspose.Email للـ Java

في التواصل الحديث عبر البريد الإلكتروني، **تضمين صورة بريد إلكتروني HTML** أصبح أكثر أهمية من أي وقت مضى—فالصور تعزز التفاعل وتساعد على إيصال رسالتك فورًا. يوضح هذا البرنامج التعليمي العملية الكاملة لإرفاق صورة، وتضمينها داخل جسم HTML، وضمان ظهور الرسالة بشكل جيد عبر مختلف عملاء البريد. سنغطي أيضًا نصائح أفضل الممارسات لـ **send html email java**، إنشاء بريد إلكتروني بالصورة، و **reduce email attachment size**.

## إجابات سريعة
- **ما هو الصنف الأساسي لإنشاء بريد إلكتروني؟** `MailMessage`
- **أي صنف يتيح لك تضمين صورة في جسم HTML؟** `LinkedResource`
- **هل أحتاج إلى ترخيص لإرسال البريد في بيئة الإنتاج؟** نعم، يلزم وجود ترخيص تجاري لـ Aspose.Email.
- **كيف يمكنني تقليل حجم المرفق؟** تحسين الصورة قبل إضافتها (مثلاً، تغيير الحجم/الضغط).
- **هل يمكنني إرسال عدة صور؟** بالتأكيد—فقط أضف معرف Content‑ID فريد لكل صورة.

## ما هو تضمين صورة بريد إلكتروني HTML؟
إرفاق صورة يعني إضافة الملف إلى بنية MIME للبريد حتى يتمكن المستلم من رؤيته. عندما تقوم بتضمين الصورة باستخدام معرف المحتوى (CID)، تظهر الصورة مباشرة داخل جسم HTML بدلاً من أن تكون مرفقًا منفصلًا، مما يعطي مظهر الصورة المدمجة.

## لماذا إرسال بريد إلكتروني HTML مع صورة مدمجة؟
تضمين الصور داخل HTML يتيح لك تصميم نشرات إخبارية أغنى، إعلانات منتجات، أو تذاكر دعم. يرى المستلمون الصورة فورًا دون الحاجة إلى تنزيل مرفق، مما يحسن معدلات الفتح والتفاعل العام.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Email for Java** – حمّله من الموقع الرسمي: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- خادم **SMTP** صالح (مثل Gmail، Outlook، أو خادم البريد الخاص بك).
- ملف صورة ترغب في تضمينه (JPEG، PNG، GIF، إلخ).

> **نصيحة احترافية:** *حسّن حجم الصورة للبريد* عن طريق تغيير العرض إلى ≤600 px وضغطها إلى ≤100 KB. هذا يقلل من زمن التحميل ويتجنب تجاوز حدود حجم صندوق البريد.

## إنشاء رسالة بريد إلكتروني
أولاً، استورد المساحات الاسمية المطلوبة وأنشئ كائن `MailMessage`. سيحمل هذا الكائن الموضوع، المستلمين، وجسم بريدك.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## إضافة الصورة كمرفق
بعد ذلك، حدد مسار ملف الصورة على القرص وأضفه إلى مجموعة مرفقات الرسالة. سيُشار إلى المرفق لاحقًا بواسطة معرف Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## تضمين الصورة المرفقة في HTML
لعرض الصورة داخل جسم البريد، أنشئ `LinkedResource` يلف تدفق المرفق. عيّن معرف Content‑ID فريد (مثال: `image1`) وأشر إليه في HTML باستخدام مخطط URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **لماذا نستخدم `LinkedResource`؟** يخبر عميل البريد أن الصورة جزء من جسم الرسالة، وليس تنزيلًا منفصلًا، وهو أمر أساسي لسيناريوهات **send HTML email with embedded image**.

## إرسال البريد الإلكتروني
أخيرًا، اضبط `SmtpClient` بتفاصيل الخادم الخاصة بك وأرسل الرسالة. تأكد من أن بيانات اعتماد SMTP لديها صلاحية الإرسال نيابةً عن عنوان المرسل.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

عند فتح المستلم للبريد، سيقوم جسم HTML بعرض الصورة مدمجة، مما يوفر تجربة بصرية سلسة.

## كيفية تضمين عدة صور في البريد
إذا كنت بحاجة إلى أكثر من صورة واحدة، كرّر خطوات المرفق و`LinkedResource` لكل ملف. عيّن معرفات Content‑ID مميزة مثل `image2`، `image3`، وأشر إليها في HTML (`src='cid:image2'`، إلخ). هذا النهج يتوسع بسهولة للنشرات التي تحتوي على عدة رسومات.

## نصائح لتقليل حجم مرفق البريد
- **غيّر حجم** الصورة إلى الأبعاد الدقيقة المطلوبة في البريد (عادةً ≤600 px عرض).  
- **ضغط** الصورة باستخدام أدوات مثل ImageMagick أو مضغّطات الإنترنت للحفاظ على حجم الملف تحت 100 KB.  
- **اختر الصيغة المناسبة**: JPEG للصور الفوتوغرافية، PNG للرسومات ذات الشفافية.  
- **أزل بيانات EXIF** إذا لم تكن ضرورية.

## المشكلات الشائعة & استكشاف الأخطاء
| المشكلة | السبب | الحل |
|-------|-------|----------|
| الصورة غير معروضة | معرف Content‑ID خاطئ أو عدم وجود `LinkedResource` | تحقق من أن `linkedImage.setContentId("image1")` يطابق `src='cid:image1'` في HTML. |
| حجم البريد كبير | صورة غير مُحسّنة (دقة عالية) | غيّر حجم/ضغط الصورة قبل الإرفاق؛ استهدف ≤100 KB. |
| البريد يُصنّف كرسائل غير مرغوب فيها | نقص رؤوس MIME الصحيحة | تأكد من أن `SmtpClient` يستخدم TLS/STARTTLS وضع عنوان `From` واضح. |
| الصورة المدمجة تظهر كمرفق | العميل لا يدعم CID | قدّم عنوان URL احتياطي في وسم `<img>` (`src='cid:image1' alt='Image'`). |

## الأسئلة المتكررة

**س: كيف يمكنني تضمين عدة صور في بريد واحد؟**  
ج: كرّر خطوات المرفق و`LinkedResource` لكل صورة، مع تعيين معرف Content‑ID فريد (مثل `image2`، `image3`) وإشارته في HTML.

**س: هل يمكنني تضمين صور في رسائل نصية عادية؟**  
ج: تنسيق النص العادي لا يدعم الصور المدمجة. يمكنك فقط تضمين روابط URL يمكن للمستلمين النقر عليها لعرض الصورة عبر الإنترنت.

**س: ما هي صيغ الصور الآمنة لتضمينها في البريد؟**  
ج: JPEG، PNG، وGIF مدعومة على نطاق واسع. استخدم JPEG للصور الفوتوغرافية وPNG للرسومات ذات الشفافية.

**س: هل هناك طريقة للتحكم بأبعاد الصورة في البريد؟**  
ج: نعم—أضف سمات العرض/الارتفاع إلى وسم `<img>`، مثال: `<img src='cid:image1' width='400' height='300'>`.

**س: هل هناك حدود لحجم الصور المدمجة؟**  
ج: رغم عدم وجود حد صارم في SMTP، توصي معظم مزودي البريد بالحفاظ على حجم البريد الكلي تحت 5 MB. تحسين حجم الصورة يساعد على البقاء ضمن هذا الحد بسهولة.

---

**آخر تحديث:** 2026-04-21  
**تم الاختبار مع:** Aspose.Email for Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}