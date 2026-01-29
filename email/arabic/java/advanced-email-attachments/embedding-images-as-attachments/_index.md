---
date: 2026-01-29
description: تعلم كيفية إرفاق صورة في البريد الإلكتروني باستخدام Aspose.Email للغة
  Java، وتضمين صورة في بريد HTML، وإرسال بريد HTML، وتقليل حجم البريد الإلكتروني باستخدام
  SMTP في Java.
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: كيفية إرفاق صورة إلى البريد الإلكتروني باستخدام Aspose.Email للـ Java
url: /ar/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إرفاق صورة إلى البريد الإلكتروني باستخدام Aspose.Email للـ Java

في التواصل الحديث عبر البريد الإلكتروني، **كيفية إرفاق صورة إلى البريد** أصبحت أكثر أهمية من أي وقت مضى—فالصور تعزز التفاعل وتساعد في إيصال رسالتك فورًا. في هذا الدليل ستتعلم **كيفية إرفاق صورة إلى البريد** باستخدام Aspose.Email للـ Java، وكيفية تضمين الصورة داخل جسم HTML، وكيفية الحفاظ على حجم الرسالة صغيرًا لضمان وصولها بشكل موثوق.

## إجابات سريعة
- **ما هو الصنف الأساسي لإنشاء بريد إلكترونيLinkedResource`
- **هل أحتاج إلى ترخيص لإرسال رسائل في بيئة الإنتاج؟** نعم، يلزم وجود ترخيص تجاري لـ Aspose.Email.
- **رفق؟** قم بتحسين الصورة قبل إضافتها (مثل تغيير الحجم/الضغط).
- **هل يمكنني إرسال صور متعددة؟** بالتأكيد—ما عليك سوى إضافة Content‑ID فريد لكل صورة.
- **ما هي إعدادات SMTP الأنسب للـ Java؟** استخدم TLS/STARTTLS على المنفذ 587 لمعظم المزودين (`smtp email java`).

## ما هو إرفاق صورة إلى بريد إلكتروني؟
إرفاق صورة يعني إضافة الملف إلى بنية MIME للبريد بحيث يستطيع المستلم عرضه. عندما تقوم بتضمين الصورة باستخدام معرف محتوى (Content‑ID أو CID)، تظهر الصورة مباشرة داخل جسم HTML بدلاً من أن تكون مرفقًا منفصلًا، مما يعطي مظهر الصورة المضمنة.

## لماذا نرسل بريدًا HTML مع صورة مدمجة؟
تضمين الصور داخل HTML يتيح لك تصميم نشرات إخبارية أغنى، إعلانات منتجات، أو تذاكر دعم. يرى المستلمون الصورة فورًا دون الحاجة إلى تنزيل مرفق، مما يحسن معدلات الفتح والتفاعل العام.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Email للـ Java** – حمّله من الموقع الرسمي: [Aspose.Email Java download](https://releases.aspose.com/email/java/).
- خادم **SMTP** صالح (مثل Gmail أو Outlook أو خادم البريد الخاص بك).
- ملف صورة ترغب في تضمينه (JPEG، PNG، GIF، إلخ).

> **نصيحة احترافية:** *قم بتحسين حجم الصورة للبريد* عن طريق تغيير العرض إلى ≤600 px وضغطها إلى ≤100 KB. هذا يقلل من زمن التحميل ويتجنب تجاوز حدود حجم صندوق البريد.

## إنشاء رسالة بريد إلكتروني
أولاً، استورد المساحات المطلوبة وأنشئ كائن `MailMessage`. سيحمل هذا الكائن الموضوع، المستلمين، وجسم البريد.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## إضافة الصورة كمرفق
بعد ذلك، حدد مسار ملف الصورة على القرص وأضفه إلى مجموعة المرفقات في الرسالة. سيُشار إلى المرفق لاحقًا باستخدام Content‑ID.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## تضمين الصورة المرفقة في HTML
لعرض الصورة داخل جسم البريد، أنشئ `LinkedResource` يلف تدفق المرفق. عيّن معرف Content‑ID فريد (مثل `image1`) واستخدمه في HTML عبر مخطط URI `cid:`.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **لماذا نستخدم `LinkedResource`؟** يخبر عميل البريد أن الصورة جزء من جسم الرسالة، وليس تحميلًا منفصلًا، وهو أمر أساسي لسيناريوهات **إرسال بريد HTML مع صورة مدمجة**.

## إرسال البريد الإلكتروني
أخيرًا، اضبط `SmtpClient` بتفاصيل الخادم الخاصة بك وأرسل الرسالة. تأكد من أن بيانات اعتماد SMTP لديها صلاحية الإرسال نيابةً عن عنوان المرسل.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

عند فتح المستلم للبريد، سيُظهر جسم HTML الصورة مدمجةً، مما يوفر تجربة بصرية سلسة.

## دليل خطوة بخطوة لإرفاق صورة إلى البريد
فيما يلي قائمة مراجعة مختصرة تعكس الشيفرة التي رأيتها للتو، لضمان عدم تفويت أي خطوة حيوية عند **إرفاق صورة إلى البريد**:

1. **تحضير الصورة** – تغيير الحجم/الضغط للحفاظ على صغر حجم البريد الكلي (`reduce email size`).
2. **إنشاء `MailMessage`** – ضبط From، To، Subject، وأي نص بديل نصي عادي.
3. **إضافة الصورة كـ `Attachment`** – هذا يسجل الملف داخل حاوية MIME.
4. **لف المرفق في `LinkedResource`** – عيّن معرف Content‑ID فريد.
5. **صياغة جسم HTML** – استخدم معرف Content‑ID مع `cid:` (مثال: `<img src='cid:image1'>`).
6. **إضافة `LinkedResource` إلى الرسالة** – يجعل الصورة مدمجة.
7. **ضبط `SmtpClient`** – استخدم TLS/STARTTLS (`smtp email java`) والمصادقة المناسبة.
8. **إرسال الرسالة** – تحقق من وصول البريد مع عرض الصورة بشكل صحيح.

## المشكلات الشائعة & استكشاف الأخطاء
| المشكلة | السبب | الحل |
|-------|-------|----------|
| الصورة لا تظهر | معرف Content‑ID خاطئ أو `LinkedResource` مفقود | تحقق من أن `linkedImage.setContentId("image1")` يطابق `src='cid:image1'` في HTML. |
| حجم البريد كبير | صورة غير مُحسّنة (دقة عالية) | قلل حجم الصورة/ضغطها قبل الإرفاق؛ استهدف ≤100 KB. |
| البريد يُصنف كرسائل غير مرغوب فيها | نقص رؤوس MIME الصحيحة | تأكد من أن `SmtpClient` يستخدم TLS/STARTTLS وضع عنوان `From` واضح. |
| الصورة المدمجة تظهر كمرفق | العميل لا يدعم CID | قدم عنوان URL بديل في وسم `<img>` (`src='cid:image1' alt='Image'`). |

## الأسئلة المتكررة

**س: كيف يمكنني تضمين عدة صور في بريد واحد؟**  
ج: كرّر خطوات الإرفاق و`LinkedResource` لكل صورة، مع تعيين معرف Content‑ID فريد (مثل `image2`، `image3`) وإدراجها في HTML.

**س: هل يمكنني تضمين صور في رسائل نصية عادية؟**  
ج: تنسيق النص العادي لا يدعم الصور المدمجة. يمكنك فقط تضمين روابط URL يمكن للمستلمين النقر عليها لعرض الصورة على الويب.

**س: ما هي صيغ الصور الآمنة لتضمينها في البريد؟**  
ج: JPEG، PNG للرسس: هل هناك طريقة للتحكم بأبعاد الصورة في البريد؟**  
ج: نعم—أضف سمات width/height إلى وسم `<img>`، مثال: `<img src='cid:image1' width='400' height='300'>`.

**س: هل توجد حدود لحجم الصور المدمجة؟**  
ج: رغم عدم وجود حد صارم في SMTP، يوصي معظم مزودي البريد بالحفاظ على حجم البريد الكلي أقل من 5 MB. تحسين حجم الصورة يساعد على البقاء ضمن هذا الحد بسهولة.

## الخلاصة
أنت الآن تعرف **كيفية إرفاق صورة إلى البريد** باستخدام Aspose.Email للـ Java، وكيفية تضمينها داخل جسم HTML، وتطبيق أفضل الممارسات مثل **تحسين حجم الصورة للبريد**. هذه التقنية تتيح لك إنشاء رسائل بصرية جذابة تشد انتباه المستلمين وتظهر بمظهر احترافي عبر جميع عملاء البريد.

---

**آخر تحديث:** 2026-01-29  
**تم الاختبار مع:** Aspose.Email للـ Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}