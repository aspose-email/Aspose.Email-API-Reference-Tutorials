---
date: 2025-11-30
description: تعلم كيفية إرفاق صورة بالبريد الإلكتروني باستخدام Aspose.Email للغة Java،
  وإرسال بريد إلكتروني بصيغة HTML يحتوي على صورة مدمجة، وتحسين حجم الصورة للبريد الإلكتروني.
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: كيفية إرفاق صورة إلى البريد الإلكتروني باستخدام Aspose.Email للـ Java
url: /ar/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إرفاق صورة إلى البريد الإلكتروني باستخدام Aspose.Email for Java

في التواصل الحديث عبر البريد الإلكتروني، **كيفية إرفاق صورة إلى البريد** أصبحت أكثر أهمية من أي وقت مضى—فالصور تعزز التفاعل وتساعد على إيصال رسالتك فورًا. يشرح هذا الدليل العملية الكاملة لإرفاق صورة، تضمينها داخل جسم HTML، وضمان ظهور الرسالة بشكل جيد عبر مختلف عملاء البريد. سنغطي أيضًا نصائح أفضل الممارسات لإرسال بريد HTML مع صورة مدمجة وتحسين حجم الصورة للبريد الإلكتروني.

## إجابات سريعة
- **ما هو الصنف الأساسي لإنشاء بريد إلكتروني؟** `MailMessage`
- **أي صنف يتيح لك تضمين صورة في جسم HTML؟** `LinkedResource`
- **هل أحتاج إلى ترخيص لإرسال رسائل في بيئة الإنتاج؟** نعم، يلزم وجود ترخيص تجاري لـ Aspose.Email.
- **كيف يمكنني تقليل حجم المرفق؟** قم بتحسين الصورة قبل إضافتها (مثل تغيير الحجم/الضغط).
- **هل يمكنني إرسال عدة صور؟** بالتأكيد—ما عليك سوى إضافة معرف Content‑ID فريد لكل صورة.

## ما هو إرفاق صورة إلى بريد إلكتروني؟
إرفاق صورة يعني إضافة الملف إلى بنية MIME للبريد بحيث يمكن للمستلم عرضه. عندما تقوم بتضمين الصورة باستخدام معرف المحتوى (CID)، تظهر الصورة مباشرة داخل جسم HTML بدلاً من أن تكون مرفقًا منفصلًا، مما يعطي مظهر الصورة المضمنة.

## لماذا نرسل بريد HTML مع صورة مدمجة؟
تضمين الصور داخل HTML يتيح لك تصميم نشرات إخبارية أغنى، إعلانات منتجات، أو تذاكر دعم. يرى المستلمون الصورة فورًا دون الحاجة إلى تحميل مرفق، مما يحسن معدلات الفتح والتفاعل العام.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود:

- **Aspose.Email for Java** – حمّلها من الموقع الرسمي: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- خادم **SMTP** صالح (مثل Gmail، Outlook، أو خادم البريد الخاص بك).
- ملف صورة ترغب في تضمينه (JPEG، PNG، GIF، إلخ).

> **نصيحة احترافية:** *قم بتحسين حجم الصورة للبريد* عن طريق تغيير العرض إلى ≤600 px وضغطها إلى ≤100 KB. هذا يقلل من زمن التحميل ويتجنب تجاوز حدود حجم صندوق البريد.

## إنشاء رسالة بريد إلكتروني
أولاً، استورد المساحات الاسمية المطلوبة وأنشئ كائن `MailMessage`. سيحمل هذا الكائن موضوع الرسالة، المستلمين، وجسم البريد.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## إضافة الصورة كمرفق
بعد ذلك، حدد مسار ملف الصورة على القرص وأضفه إلى مجموعة المرفقات في الرسالة. سيُشار إلى المرفق لاحقًا بواسطة معرف Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## تضمين الصورة المرفقة في HTML
لعرض الصورة داخل جسم البريد، أنشئ `LinkedResource` يلف تدفق المرفق. عيّن معرف Content‑ID فريد (مثل `image1`) وارجع إليه في HTML باستخدام مخطط URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **لماذا نستخدم `LinkedResource`؟** يخبر عميل البريد أن الصورة جزء من جسم الرسالة، وليس تحميلًا منفصلًا، وهو أمر أساسي لسيناريو **إرسال بريد HTML مع صورة مدمجة**.

## إرسال البريد الإلكتروني
أخيرًا، اضبط `SmtpClient` بتفاصيل الخادم الخاصة بك وأرسل الرسالة. تأكد من أن بيانات اعتماد SMTP لديها صلاحية الإرسال نيابةً عن عنوان المرسل.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

عند فتح المستلم للبريد، سيعرض جسم HTML الصورة مدمجةً، مما يوفر تجربة بصرية سلسة.

## المشكلات الشائعة & استكشاف الأخطاء
| المشكلة | السبب | الحل |
|-------|-------|----------|
| الصورة لا تظهر | معرف Content‑ID غير صحيح أو `LinkedResource` مفقود | تأكد من أن `linkedImage.setContentId("image1")` يطابق `src='cid:image1'` في HTML. |
| حجم البريد كبير | صورة غير محسّنة (دقة عالية) | غيّر حجم/ضغط الصورة قبل الإرفاق؛ استهدف ≤100 KB. |
| البريد يُصنف كرسائل غير مرغوب فيها | نقص رؤوس MIME المناسبة | تأكد من أن `SmtpClient` يستخدم TLS/STARTTLS وضع عنوان `From` واضح. |
| الصورة المضمنة تظهر كمرفق | العميل لا يدعم CID | قدم عنوان URL بديل في وسم `<img>` (`src='cid:image1' alt='Image'`). |

## الأسئلة المتكررة

**س: كيف يمكنني تضمين عدة صور في بريد واحد؟**  
ج: كرّر خطوات الإرفاق و`LinkedResource` لكل صورة، مع تعيين معرف Content‑ID فريد (مثل `image2`، `image3`) وإرجاعه في HTML.

**س: هل يمكنني تضمين صور في رسائل نصية عادية؟**  
ج: تنسيق النص العادي لا يدعم الصور المدمجة. يمكنك فقط تضمين روابط URL يمكن للمستلمين النقر عليها لعرض الصورة على الويب.

**س: ما هي صيغ الصور الآمنة لتضمينها في البريد؟**  
ج: JPEG، PNG، وGIF مدعومة على نطاق واسع. استخدم JPEG للصور الفوتوغرافية وPNG للرسومات ذات الشفافية.

**س: هل هناك طريقة للتحكم بأبعاد الصورة في البريد؟**  
ج: نعم—أضف سمات `width`/`height` إلى وسم `<img>`، مثال: `<img src='cid:image1' width='400' height='300'>`.

**س: هل هناك حدود لحجم الصور المدمجة؟**  
ج: رغم عدم وجود حد صارم في SMTP، تُوصي معظم مزودي البريد بالحفاظ على حجم البريد الكلي أقل من 5 MB. يساعد تحسين حجم الصورة على البقاء ضمن هذا الحد بسهولة.

## الخلاصة
أنت الآن تعرف **كيفية إرفاق صورة إلى البريد** باستخدام Aspose.Email for Java، تضمينها داخل جسم HTML، وتطبيق أفضل الممارسات مثل **تحسين حجم الصورة للبريد**. تتيح لك هذه التقنية إنشاء رسائل بصرية جذابة تُشرك المستلمين وتظهر بمظهر احترافي عبر جميع عملاء البريد.

---

**آخر تحديث:** 2025-11-30  
**تم الاختبار مع:** Aspose.Email for Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}