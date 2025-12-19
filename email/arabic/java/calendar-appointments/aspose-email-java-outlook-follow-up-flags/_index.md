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

## Introduction
إذا كنت قد واجهت صعوبة في تتبع الرسائل الإلكترونية المهمة، فأنت تعلم مدى قيمة علامات المتابعة في Outlook. في هذا الدليل سنوضح **كيفية تعيين علامات المتابعة** برمجيًا باستخدام Aspose.Email for Java، وسنغطي أيضًا كيفية **تعيين علامة متابعة Outlook** للمستلمين، بالإضافة إلى كيفية **إزالة علامة متابعة Outlook** عندما يكتمل المهمة. في النهاية، ستتمكن من أتمتة تتبع المهام، والتذكيرات، وسجلات التدقيق مباشرةً من كود Java الخاص بك.

**ما ستتعلمه**
- إنشاء وتطبيق علامة متابعة على رسالة Outlook.  
- تعيين علامات متابعة لمستلمين محددين.  
- وضع علامة كمنجزة وإزالتها لاحقًا.  
- قراءة خيارات العلامة للتقارير أو الامتثال.  

لنجهز البيئة قبل الغوص في الكود.

## Quick Answers
- **ماذا يعني “كيفية تعيين متابعة”؟** إضافة علامة مع تواريخ البدء، والتذكير، والموعد النهائي إلى عنصر Outlook.  
- **ما المكتبة المطلوبة؟** Aspose.Email for Java (الإصدار 25.4 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم وجود ترخيص تجريبي أو مرخص للحصول على الوظائف الكاملة.  
- **هل يمكنني تعيين علامات للمستلمين فقط؟** بالتأكيد – استخدم `FollowUpManager.setFlagForRecipients`.  
- **هل يمكن إزالة العلامة لاحقًا؟** نعم، استدعِ `FollowUpManager.clearFlag`.

## What is a Follow‑Up Flag?
علامة المتابعة هي ميزة في Outlook تضع إشارة على رسالة البريد الإلكتروني كمهام، مع إمكانية إرفاق تواريخ البدء، والتذكير، والموعد النهائي. تساعدك أنت وفريقك على متابعة الإجراءات المعلقة.

## Why use Aspose.Email for Java?
توفر Aspose.Email واجهة برمجة تطبيقات Java صافية تعمل دون الحاجة إلى تثبيت Outlook، مما يتيح لك التعامل مع ملفات .msg، وتعيين العلامات، وإدارة المهام على أي منصة—مثالية للخدمات الخلفية، وسير العمل الآلي، أو التكامل مع أدوات إدارة المشاريع.

## Prerequisites
- **Aspose.Email for Java** الإصدار 25.4 أو أحدث.  
- **JDK 16+** مثبت.  
- بيئة تطوير متوافقة مع Maven (IntelliJ IDEA، Eclipse، إلخ).  
- معرفة أساسية بـ Java وإلمام بمفاهيم البريد الإلكتروني.

## Setting Up Aspose.Email for Java
### Maven Configuration
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
تتطلب Aspose.Email ترخيصًا للاستخدام في الإنتاج:

- **تجربة مجانية** – تقييم لمدة 30 يومًا.  
- **ترخيص مؤقت** – اختبار موسع.  
- **ترخيص كامل** – اشتراك دائم.

قم بتهيئة الترخيص قبل أي عملية بريد إلكتروني:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementation Guide

### How to Set Follow‑Up Flags (Feature 1)
#### Overview
يشرح هذا القسم كيفية إنشاء رسالة Outlook، وتعريف تواريخ البدء/التذكير/الموعد النهائي، وتطبيق علامة المتابعة.

#### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*نقوم أولاً بإنشاء كائن `MailMessage`، وتحديد المرسل/المستلم، ثم تحويله إلى `MapiMessage` لتعديل العلامة.*

#### Step 2: Define Follow‑Up Dates
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

#### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*كائن `FollowUpOptions` يحتوي على جميع تفاصيل العلامة، ونطبقه باستخدام `FollowUpManager.setOptions`.*

#### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*يتم حفظ الرسالة كملف `.msg` مع إرفاق العلامة.*

### How to Set Outlook Follow‑Up Flag for Recipients (Feature 2)
#### Overview
في بعض الأحيان تحتاج إلى وضع علامة على الرسالة للمستلمين فقط. يوضح هذا المثال كيفية وضع الرسالة كمسودة أولاً، ثم إضافة العلامة.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*وضع الرسالة كغير مرسلة يضمن أن Outlook يتعامل معها كمسودة.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*العلامة الآن مرئية فقط للمستلمين.*

### How to Mark an Outlook Follow‑Up Flag as Completed (Feature 3)
#### Overview
عند إكمال المهمة، يمكنك برمجيًا وضع العلامة كمنجزة.

#### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*يتغير حالة العلامة إلى “Completed” ويتم حفظ الملف المحدث.*

### How to Remove Outlook Follow‑Up Flag (Feature 4)
#### Overview
إذا لم تعد العلامة مطلوبة، يمكنك إزالتها بالكامل.

#### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*يتم حفظ الرسالة دون أي علامة متابعة.*

### How to Read Follow‑Up Flag Options (Feature 5)
#### Overview
للتدقيق أو إعداد التقارير، قد تحتاج إلى قراءة إعدادات العلامة الحالية.

#### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*كائن `options` الآن يحتوي على تواريخ البدء، والموعد النهائي، والتذكير، بالإضافة إلى موضوع العلامة.*

## Practical Applications
- **Task‑Management Integration:** مزامنة الرسائل الموسومة مع Jira أو Trello أو Azure Boards.  
- **Automated Reminders:** إنشاء رسائل تذكير يومية للمتابعات المعلقة.  
- **Compliance Audits:** تصدير بيانات العلامات لتقارير الامتثال التنظيمي.

## Performance Considerations
- **Date Calculations:** احسب التواريخ مرة واحدة لكل دفعة بدلاً من داخل الحلقات.  
- **Resource Management:** أغلق أي تدفقات أو مقبض ملفات بعد حفظ الرسائل.  
- **Memory Usage:** عالج صناديق البريد الكبيرة على دفعات لتجنب ضغط الذاكرة.

## Common Issues and Solutions
| المشكلة | السبب | الحل |
|-------|-------|-----|
| العلامة لا تظهر في Outlook | تم حفظ الرسالة دون `MessageFlags` صحيحة | تأكد من ضبط `setMessageFlags` إلى `MSGFLAG_UNSENT` قبل تطبيق علامات المستلمين. |
| حدوث استثناء `AccessDeniedException` عند الحفظ | مسار ملف غير صحيح أو عدم وجود أذونات كتابة | تحقق من وجود دليل الإخراج وأن التطبيق يملك صلاحية الكتابة. |
| التواريخ متأخرة بيوم واحد | اختلاف المنطقة الزمنية | استخدم `TimeZone.getTimeZone("GMT")` أو المنطقة المحلية بشكل ثابت. |

## Frequently Asked Questions
**س: ما هو Aspose.Email for Java؟**  
ج: هو واجهة برمجة تطبيقات Java صافية تتيح لك إنشاء، قراءة، وتعديل ملفات البريد (MSG، EML، إلخ) دون الحاجة إلى تثبيت Outlook.

**س: كيف أحصل على ترخيص تجريبي مجاني؟**  
ج: زر موقع [Aspose](https://releases.aspose.com/email/java/) لتحميل نسخة تجريبية لمدة 30 يومًا.

**س: هل يمكنني تعيين عدة علامات متابعة على رسالة واحدة؟**  
ج: يدعم Outlook علامة متابعة واحدة فقط لكل رسالة، لكن يمكنك تخزين بيانات مهام إضافية في خصائص MAPI مخصصة.

**س: رسالتي لا تُحفظ بعد تعيين العلامة. ما الذي يجب فحصه؟**  
ج: تأكد من صحة مسار `outputDir` وأن التطبيق يملك صلاحية الكتابة إلى ذلك الموقع.

**س: كيف يمكنني إزالة العلامات من العديد من الرسائل دفعة واحدة؟**  
ج: قم بالتكرار عبر مجموعة الرسائل واستدعِ `FollowUpManager.clearFlag` لكل `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}