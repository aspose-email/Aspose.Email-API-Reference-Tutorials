---
date: '2026-07-27'
description: تعلم كيفية تعيين علم Outlook في Java باستخدام Aspose.Email for Java،
  مع تغطية إنشاء العلم، أعلام المستلمين، الإكمال، الإزالة، وخيارات القراءة.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: تعيين علم Outlook في Java باستخدام Aspose.Email for Java. يوضح هذا
  الدليل كيفية إنشاء، قراءة، إكمال، وإزالة أعلام المتابعة في Outlook بفعالية.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: تعيين علم Outlook Java – دليل برمجة Aspose.Email الكامل
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: تعيين علم Outlook Java – دليل برمجة Aspose.Email الكامل
url: /ar/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تعيين علم Outlook Java باستخدام Aspose.Email for Java

## مقدمة
إذا كنت بحاجة إلى **set outlook flag java** برمجيًا، فقد وصلت إلى المكان الصحيح. يحول علم المتابعة في Outlook رسالة بريد عادية إلى مهمة مُتابَعة، وتتيح لك Aspose.Email for Java إدارة هذه الأعلام دون الحاجة إلى تثبيت Outlook. في هذا الدرس سنستعرض إنشاء الأعلام، قراءتها، إكمالها، وأخيرًا إزالتها، بالإضافة إلى كيفية تطبيق الأعلام على مستلمين محددين. في النهاية ستحصل على مقتطف Java قابل لإعادة الاستخدام يُؤتمت تتبع المهام مباشرةً من خدمات الخلفية الخاصة بك.

## إجابات سريعة
- **ماذا يعني “set outlook flag java”؟** إضافة علم مع تاريخ بدء، وتذكير، وتاريخ استحقاق إلى عنصر Outlook عبر كود Java.  
- **ما المكتبة المطلوبة؟** Aspose.Email for Java (الإصدار v25.4 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** نعم – النسخة التجريبية تعمل للتقييم، لكن الترخيص المشتراة مطلوب للإنتاج.  
- **هل يمكنني تعيين الأعلام للمستلمين فقط؟** بالتأكيد – استخدم `FollowUpManager.setFlagForRecipients`.  
- **هل يمكن إزالة العلم لاحقًا؟** نعم – استدعِ `FollowUpManager.clearFlag`.

## ما هو علم المتابعة في Outlook؟
علم المتابعة في Outlook هو علامة مهمة مدمجة يمكن إرفاق تاريخ بدء، وتذكير، وتاريخ استحقاق بأي عنصر بريد. يحول البريد إلى عنصر عمل مُتابَع، مما يساعدك وفريقك على البقاء على اطلاع بالمهام المعلقة.

## لماذا نستخدم Aspose.Email for Java؟
تدعم Aspose.Email for Java **أكثر من 70 تنسيق بريدًا** (بما في ذلك MSG، EML، MHTML، وTNEF) ويمكنها معالجة **أكثر من 100,000 رسالة في الدقيقة** على خادم عادي بثمانية نوى، كل ذلك دون الحاجة إلى Outlook على الجهاز المضيف. هذا يجعلها مثالية لأتمتة الخلفية، تقارير الامتثال، والتكامل مع أدوات إدارة المشاريع.

## المتطلبات المسبقة
- **Aspose.Email for Java** الإصدار 25.4 أو أحدث.  
- **JDK 16+** مثبت.  
- بيئة تطوير متوافقة مع Maven (IntelliJ IDEA، Eclipse، إلخ).  
- معرفة أساسية بـ Java وإلمام بمفاهيم البريد الإلكتروني.

## إعداد Aspose.Email for Java
### تكوين Maven
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
تتطلب Aspose.Email ترخيصًا للاستخدام في الإنتاج:

- **نسخة تجريبية مجانية** – تقييم لمدة 30 يومًا.  
- **ترخيص مؤقت** – اختبار موسع.  
- **ترخيص كامل** – اشتراك دائم.

قم بتهيئة الترخيص قبل أي عملية بريد إلكتروني:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## تعيين علم Outlook Java (الميزة 1)
### إجابة مباشرة
حمّل كائن `MailMessage`، حوّله إلى `MapiMessage`، اضبط `FollowUpOptions`، واستدعِ `FollowUpManager.setOptions`. هذه السلسلة تنشئ عنصر Outlook معلم بالكامل في بضع أسطر من كود Java.

### الخطوة 1: إنشاء وتهيئة الرسالة
`MailMessage` هي الفئة عالية المستوى في Aspose.Email التي تمثل بريدًا إلكترونيًا. بعد بناء الرسالة، تقوم بتحويلها إلى `MapiMessage` لتعديل العلم.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*نقوم أولاً بإنشاء `MailMessage`، تعيين المرسل/المستلم، ثم تحويله إلى `MapiMessage` لتعديل العلم.*

### الخطوة 2: تعريف تواريخ المتابعة (تذكير علم Outlook)
`FollowUpOptions` يحتوي على تواريخ البدء، والتذكير، والاستحقاق. استخدم `Calendar` في Java لتعيين طوابع زمنية دقيقة.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*هنا نحدد تاريخ البدء، والتذكير (**outlook flag reminder**)، وتاريخ الاستحقاق باستخدام فئة `Calendar`.*

### الخطوة 3: تطبيق خيارات المتابعة
طريقة `FollowUpManager.setOptions` تُرفق العلم بـ `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*كائن `FollowUpOptions` يحمل جميع تفاصيل العلم، ونطبقه باستخدام `FollowUpManager.setOptions`.*

### الخطوة 4: حفظ الرسالة
احفظ الرسالة المعلَّمة كملف `.msg` حتى يتمكن Outlook من عرض العلم.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*يتم حفظ الرسالة كملف `.msg` مع العلم مرفقًا.*

## كيفية تعيين علم للمستلمين (الميزة 2)؟
استخدم `FollowUpManager.setFlagForRecipients` بعد وضع الرسالة كمسودة. هذه الطريقة تضيف علم المتابعة فقط إلى نسخة المستلم، مع ترك عرض المرسل دون تغيير. يتطلب ذلك تعيين `MessageFlags.MSGFLAG_UNSENT` قبل تطبيق العلم. يمكنك أيضًا تخصيص تواريخ البدء، والتذكير، والاستحقاق باستخدام كائن `FollowUpOptions` قبل استدعاء الطريقة.

### إجابة مباشرة
ضع الرسالة كمسودة باستخدام `MessageFlags.MSGFLAG_UNSENT`، ثم استدعِ `FollowUpManager.setFlagForRecipients`. سيظهر العلم في Outlook للمستلمين فقط، وليس للمرسل.

### نظرة عامة
أحيانًا تحتاج إلى ظهور العلم **فقط للمستلمين**. يوضح هذا المثال وضع الرسالة كمسودة أولاً، ثم إضافة العلم.

#### الخطوة 1: وضع كمسودة
`MessageFlags` هو تعداد MAPI يتحكم في حالة الرسالة. تعيين `MSGFLAG_UNSENT` يخبر Outlook أن العنصر مسودة.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*تعيين الرسالة كغير مرسلة يضمن أن Outlook يتعامل معها كمسودة.*

#### الخطوة 2: تعيين علم للمستلمين
`FollowUpManager.setFlagForRecipients` يرفق العلم حصريًا بنسخة المستلم.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*الآن يصبح العلم مرئيًا فقط للمستلمين – سيناريو **flag for recipients** كلاسيكي.*

## كيفية وضع علامة علم المتابعة في Outlook كمنجز (الميزة 3)؟
حمّل ملف `.msg` إلى `MapiMessage`، ثم استدعِ `FollowUpManager.completeFlag`. هذا يُحدّث حالة العلم إلى "مكتمل" ويضيف علامة اختيار في Outlook. بعد الإكمال، احفظ الرسالة لتثبيت التغيير. يمكنك أيضًا ضبط وقت الإكمال عبر تعديل خاصية `FlagCompleteTime` إذا كان ذلك مطلوبًا لأغراض التدقيق.

### إجابة مباشرة
حمّل ملف `.msg` الموجود إلى `MapiMessage`، استدعِ `FollowUpManager.completeFlag`، واحفظ الملف. تتغير حالة العلم إلى “Completed” وتظهر بعلامة اختيار في Outlook.

### الخطوة 1: تحميل الرسالة
`MapiMessage` يمكنه قراءة ملف `.msg` محفوظ، مما يمنحك وصولًا كاملًا إلى خصائص MAPI الخاصة به.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### الخطوة 2: وضع علامة مكتملة وحفظ
`FollowUpManager.completeFlag` يُحدّث حالة العلم، ثم تقوم بحفظ التغييرات.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*تتغير حالة العلم إلى “Completed” ويتم حفظ الملف المحدث.*

## كيفية إزالة علم المتابعة في Outlook (الميزة 4)؟
افتح ملف `.msg` باستخدام `MapiMessage`، استدعِ `FollowUpManager.clearFlag`، ثم احفظ الرسالة. هذا يزيل جميع خصائص MAPI المتعلقة بالعلم، لذا لن يعرض Outlook أي مؤشر متابعة. استخدم ذلك عندما تُلغى مهمة أو لم تعد ذات صلة. تأكد أيضًا من مسح أي خصائص تذكير مخصصة لتجنب إشعارات متبقية.

### إجابة مباشرة
افتح ملف `.msg` باستخدام `MapiMessage`، استدعِ `FollowUpManager.clearFlag`، واحفظ الملف. لن تعرض الرسالة أي مؤشر متابعة في Outlook بعد ذلك.

### الخطوة 1: تحميل وإزالة العلم
`FollowUpManager.clearFlag` يزيل جميع الخصائص المتعلقة بالعلم من الرسالة.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*يتم حفظ الرسالة دون أي علم متابعة.*

## كيفية قراءة خيارات العلم (الميزة 5)؟
استدعِ `FollowUpManager.getOptions` على `MapiMessage` محمَّل للحصول على كائن `FollowUpOptions`. يوفر هذا الكائن تواريخ البدء، والاستحقاق، والتذكير، وموضوع العلم، مما يتيح لك عرض أو تسجيل تفاصيل العلم. وهو مفيد للتقارير وتدقيق الامتثال.

### إجابة مباشرة
استخدم `FollowUpManager.getOptions` على `MapiMessage` محمَّل لاسترجاع كائن `FollowUpOptions` يحتوي على تواريخ البدء، والاستحقاق، والتذكير، وموضوع العلم. هذا مفيد للتقارير أو تدقيق الامتثال.

### الخطوة 1: استرجاع الخيارات
الكائن `options` المُعاد يمنحك رؤية كاملة لتكوين العلم.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*الآن يحتوي كائن `options` على تواريخ البدء، والاستحقاق، والتذكير، بالإضافة إلى موضوع العلم – مفيد عندما تحتاج إلى **read flag options** للتقارير.*

## تطبيقات عملية
- **تكامل إدارة المهام:** مزامنة الرسائل المعلَّمة مع Jira أو Trello أو Azure Boards.  
- **تذكيرات آلية:** توليد رسائل تذكير يومية للمتابعات المعلقة.  
- **تدقيق الامتثال:** تصدير بيانات الأعلام لتقارير تنظيمية، مستفيدًا من القدرة على قراءة خيارات العلم برمجيًا.

## اعتبارات الأداء
- **حساب التواريخ:** احسب التواريخ مرة واحدة لكل دفعة بدلاً من داخل الحلقات.  
- **إدارة الموارد:** أغلق أي تدفقات أو مقبض ملفات بعد حفظ الرسائل.  
- **استخدام الذاكرة:** عالج صناديق البريد الكبيرة على دفعات لتجنب ضغط الذاكرة؛ يمكن لـ Aspose.Email التعامل مع صناديق بريد مئات الصفحات دون تحميل الملف بالكامل إلى الذاكرة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| العلم لا يظهر في Outlook | تم حفظ الرسالة دون `MessageFlags` المناسب | تأكد من ضبط `setMessageFlags` إلى `MSGFLAG_UNSENT` قبل تطبيق أعلام المستلمين. |
| حفظ الرسالة يثير `AccessDeniedException` | مسار ملف غير صحيح أو عدم وجود أذونات كتابة | تحقق من وجود دليل الإخراج وأن التطبيق يمتلك صلاحية الكتابة. |
| التواريخ متأخرة بيوم | اختلاف المنطقة الزمنية | استخدم `TimeZone.getTimeZone("GMT")` أو منطقتك المحلية بشكل ثابت. |

## الأسئلة المتكررة
**س: ما هو Aspose.Email for Java؟**  
ج: هو API نقي‑Java يتيح لك إنشاء، قراءة، وتعديل ملفات البريد (MSG، EML، إلخ) دون الحاجة إلى Outlook مثبت.

**س: كيف أحصل على ترخيص تجريبي مجاني؟**  
ج: زر [موقع Aspose](https://releases.aspose.com/email/java/) لتنزيل نسخة تجريبية لمدة 30 يومًا.

**س: هل يمكنني تعيين عدة أعلام متابعة على رسالة واحدة؟**  
ج: يدعم Outlook علمًا واحدًا فقط لكل رسالة، لكن يمكنك تخزين بيانات مهمة إضافية في خصائص MAPI مخصصة.

**س: رسالتي لا تُحفظ بعد تعيين العلم. ماذا أفحص؟**  
ج: تأكد من صحة مسار `outputDir` وأن التطبيق يملك صلاحية الكتابة إلى ذلك الموقع.

**س: كيف يمكنني إزالة الأعلام من العديد من الرسائل دفعة واحدة؟**  
ج: قم بالتكرار عبر مجموعة الرسائل واستدعِ `FollowUpManager.clearFlag` على كل `MapiMessage`.

## موارد
- [التوثيق](https://reference.aspose.com/email/java/)
- [تحميل Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [نسخة تجريبية مجانية من Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**آخر تحديث:** 2026-07-27  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إدارة فئات Outlook باستخدام Aspose.Email for Java - دليل شامل](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [إنشاء ملاحظات Outlook Java باستخدام Aspose.Email – دليل كامل](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [إنشاء مهام في Microsoft Exchange باستخدام Aspose.Email for Java: دليل كامل](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}