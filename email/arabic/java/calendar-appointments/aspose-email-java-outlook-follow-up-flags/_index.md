---
date: '2025-12-19'
description: تعلم كيفية تعيين علامات المتابعة في Outlook باستخدام Aspose.Email للغة
  Java، بما في ذلك كيفية تعيين علامة المتابعة في Outlook وإزالة علامة المتابعة في
  Outlook بكفاءة.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: كيفية تعيين علامات المتابعة في Outlook باستخدام Aspose.Email للـ Java
url: /ar/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين علامات المتابعة في Outlook باستخدام Aspose.Email for Java

## مقدمة
إذا كنت لا تستطيع صعوبة في متابعة الرسائل الإلكترونية المهمة، فعليك أن تعلم مدى قيمة علامات المتابعة في Outlook. في هذا الدليل سنوضح **كيفية تعيين المتابعة** برمجيًا باستخدام Aspose.Email لـ Java، وسنغطي أيضًا كيفية **تعيين علامة متابعة Outlook** للمستلمين، بالإضافة إلى كيفية **إزالة علامة متابعة Outlook** عندما تكتمل المهمة. في النهاية، تم حسابها من تتبع اللعبة، والتذكيرات، وحصرات التمييز من كود Java الخاص بك.

**ما ستتعلمه**
- إنشاء وتطبيق علامة متابعة على رسالة Outlook.
- تعيين علامات متابعة لم استلامين المحددين.
- وضع علامة كمنجز وإزالتها لاحقا.
- قراءة خيارات العلامة للتقارير أو.

لننظم البيئة قبل الغوص في الكود.

## إجابات سريعة
- **ماذا يعني “كيفية تجدد تحديثها”؟** إضافة علامة مع التجديد، والتذكير، والوعد النهائي إلى مفهوم Outlook.
- **ما المؤسسة الأساسية؟** Aspose.Email for Java (الإصدار 25.4 أو أحدث).
- **هل تحتاج إلى ترخيص؟** نعم، يلزم الحصول على ترخيص أو الحصول على ترخيص كامل للحصول على الوظائف.
- **هل يمكنني تعيين علامات للمستلمين فقط؟** بالتأكيد – استخدم `FollowUpManager.setFlagForRecipients`.
- **هل يمكن إزالة العلامة التجارية لاحقًا؟** نعم، بالتأكيد `FollowUpManager.clearFlag`.

## ما هو علم المتابعة؟
علامة المتابعة هي فرصة في Outlook تضع إشارة على رسالة البريد الإلكتروني كمهام، مع إمكانية استمرار الأحداث، والتذكير، والموعد النهائي. ستساعدك وفريقك على تطبيق التدابير الوقائية.

## لماذا نستخدم Aspose.Email لـ Java؟
توفر Aspose.Email واجهة برمجة تطبيقات Java Nete تعمل دون الحاجة إلى تثبيت Outlook، يتيح لك التعامل مع ملفات .msg، وتعيين العلامات، وإدارة القدرة على أي منصة—مثالية مما الخدمات، وسير العمل الفني، أو تكامل مع أدوات إدارة المشاريع.

## المتطلبات الأساسية
- **Aspose.Email for Java** الإصدار 25.4 أو أحدث.
- **JDK16+** إيجابي.
- بيئة تطوير متوافقة مع Maven (IntelliJ IDEA، Eclipse، إلخ).
- معرفة القمة بـ Java وإمام بمفاهيم البريد الإلكتروني.

## إعداد Aspose.Email لـ Java
### تكوين مخضرم
إضافة الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

قم بتهيئة الترخيص قبل أي عملية بريد إلكتروني:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## دليل التنفيذ

### كيفية تعيين علامات المتابعة (الميزة 1)
#### ملخص
يشرح هذا القسم كيفية إنشاء رسالة Outlook، وتعريف التاريخ/التذكير/الموعد النهائي، وتطبيق علامة المتابعة.

#### الخطوة الأولى: إنشاء الرسالة وتهيئتها
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*نقوم أولاً بإنشاء كائن `MailMessage`، وتحديد المرسل/المستلم، ثم تحويله إلى `MapiMessage` لتعديل العلامة.*

#### الخطوة الثانية: تحديد مواعيد المتابعة
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*هنا نحدد تواريخ البدء، والتذكير، والموعد النهائي باستخدام فئة `Calendar`.*

#### الخطوة 3: تطبيق خيارات المتابعة
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*كائن `FollowUpOptions` يحتوي على جميع تفاصيل العلامة، ونطبقه باستخدام `FollowUpManager.setOptions`.*

#### الخطوة الرابعة: حفظ الرسالة
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*يتم حفظ الرسالة كملف `.msg` مع إرفاق العلامة.*

### كيفية ضبط علامة متابعة Outlook للمستلمين (الميزة 2)
#### نظرة عامة
في بعض الأحيان تحتاج إلى وضع علامة على الرسالة للمستلمين فقط. يوضح هذا المثال كيفية وضع الرسالة كمسودة أولاً، ثم إضافة العلامة.

#### الخطوة 1: ضع علامة كمسودة
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*وضع الرسالة كغير مرسلة يضمن أن Outlook يتعامل معها كمسودة.*

#### الخطوة الثانية: تعيين علامة المستلم
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*العلامة الآن مرئية فقط للمستلمين.*

### كيفية وضع علامة "مكتمل" على رسالة متابعة في Outlook (الميزة 3)
#### نظرة عامة
عند إكمال المهمة، يمكنك برمجيًا وضع العلامة كمنجزة.

#### الخطوة 1: تحميل الرسالة

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### الخطوة 2: وضع علامة "مكتمل" وحفظها
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*يتغير حالة العلامة إلى “Completed” ويتم حفظ الملف المحدث.*

### كيفية إزالة علامة المتابعة في Outlook (الميزة 4)
#### نظرة عامة
إذا لم تعد العلامة مطلوبة، يمكنك إزالتها بالكامل.

#### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*يتم حفظ الرسالة دون أي علامة متابعة.*

### كيفية قراءة خيارات علامة المتابعة (الميزة 5)
#### نظرة عامة
للتدقيق أو إعداد التقارير، قد تحتاج إلى قراءة إعدادات العلامة الحالية.

#### الخطوة 1: استرجاع الخيارات
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*كائن `options` الآن يحتوي على تواريخ البدء، والموعد النهائي، والتذكير، بالإضافة إلى موضوع العلامة.*

## تطبيقات عملية
- **تكامل إدارة المهام:** نوبات الرسائل الموسومة مع Jira أو Trello أو Azure Boards.
- **التذكيرات الآلية:** إنشاء رسائل تذكير يومية للمتابعات المعلقة.
- **عمليات تدقيق الامتثال:** تصدير بيانات العناوين للتقارير التنظيمية.

## اعتبارات الأداء
- **حسابات التاريخ:** حسب التواريخ مرة واحدة لكل بديل من داخل الحلقات.
- **إدارة الموارد:** تسبب في أي تدفقات أو السيطرة على الملفات بعد حفظ الرسائل.
- **استخدام الذاكرة:** معالجة صناديق البريد الكبيرة على دفعات ضغط الذاكرة.

## المشكلات والحلول الشائعة
| مشكلة | السبب | الحل |
|-------|-------|-----|
| العلامة التجارية التي لا تدوم في Outlook | تم حفظ الرسالة دون `MessageFlags` بشكل صحيح | تأكد من ضبط `setMessageFlags` إلى `MSGFLAG_UNSENT` قبل تطبيق علامات المستلمين. |
| استثناء `AccessDeniedException` عند الحفظ | مسار ملف غير صحيح أو عدم وجود صلاحيات كتابة | التحقق من وجود دليل وأن التطبيق يملك قوة الكتابة. |
| التواريخ المتأخرة بيوم واحد | الاختلاف المنطقة الزمنية | استخدم `TimeZone.getTimeZone("GMT")` أو المنطقة المحلية الثابتة. |

## الأسئلة المتداولة
**س: ما هو Aspose.Email for Java؟**
ج: هو واجهة برمجة تطبيقات Java الصافية المتعددة لك إنشاء، قراءة، وتعديل ملفات البريد (MSG، EML، إلخ) دون الحاجة إلى تثبيت Outlook.

**س: كيف تريد الحصول على ترخيص شراء مجاني؟**
ج: زر موقع [Aspose](https://releases.aspose.com/email/java/) لتحميل نسخة رخيصة لمدة 30 يومًا.

**س: هل يمكنني تعيين عدة علامات تتبع على رسالة واحدة؟**
ج: يدعم Outlook علامة واحدة فقط لكل رسالة، ولكن يمكنك تخزين بيانات مهام إضافية في خصائص MAPI مخصصة.

**س: رسالتي لا تُحفظ بعد العلامة المعينة. ما الذي يجب فحصه؟**
ج: تأكد من صحة مسار `outputDir` وأن التطبيق يملك قوة الكتابة إلى ذلك الموقع.

**س: كيف يمكنني إزالة العلامات من العديد من الرسائل دفعة واحدة؟**
ج: قم بالتكرار عبر مجموعة الرسائل ويستدعِ `FollowUpManager.clearFlag` لكل `MapiMessage`.

## الموارد
- [الوثائق](https://reference.aspose.com/email/java/)
- [تنزيل Aspose.Email لجافا](https://releases.aspose.com/email/java/)
- [تجربة مجانية لـ Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**آخر تحديث:** ١٩ ديسمبر ٢٠٢٥
**تم الاختبار باستخدام:** Aspose.Email لجافا ٢٥.٤ (jdk16)
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}