---
date: '2026-02-22'
description: تعلم كيفية تعيين علم المتابعة في Outlook باستخدام Aspose.Email للـ Java،
  بما في ذلك تعيين الأعلام، قراءتها وإزالتها للمستلمين.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: كيفية تعيين علامة المتابعة في Outlook باستخدام Aspose.Email للـ Java
url: /ar/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين Outlook Follow Up Flag باستخدام Aspose.Email للـ Java

## المقدمة
إذا واجهت صعوبة في تتبع الرسائل الإلكترونية المهمة، فأنت تعلم مدى قيمة **outlook follow up flag** في Outlook. في هذا الدليل سنوضح **كيفية تعيين outlook follow up flag** برمجيًا باستخدام Aspose.Email للـ Java، وسنغطي أيضًا كيفية **تعيين outlook follow up flag للمستلمين**، بالإضافة إلى كيفية **إزالة outlook follow up flag** عندما ينتهي المهمة. بنهاية الدليل، ستكون قادرًا على أتمتة تتبع المهام، والتذكيرات، وسجلات التدقيق مباشرةً من كود Java الخاص بك.

**ما ستتعلمه**
- إنشاء وتطبيق علم متابعة على رسالة Outlook.  
- تعيين أعلام متابعة لمستلمين محددين.  
- وضع علامة مكتملة على العلم وإزالته لاحقًا.  
- قراءة خيارات العلم للتقارير أو الامتثال.  

لنجهّز البيئة قبل الغوص في الكود.

## إجابات سريعة
- **ماذا يعني “كيفية تعيين المتابعة”؟** إضافة علم مع تاريخ البدء، وتذكير، وتاريخ الاستحقاق إلى عنصر Outlook.  
- **ما المكتبة المطلوبة؟** Aspose.Email للـ Java (الإصدار 25.4 أو أحدث).  
- **هل أحتاج إلى رخصة؟** نعم، يلزم وجود رخصة تجريبية أو مُشتراة للحصول على الوظائف الكاملة.  
- **هل يمكنني تعيين أعلام للمستلمين فقط؟** بالتأكيد – استخدم `FollowUpManager.setFlagForRecipients`.  
- **هل يمكن إزالة العلم لاحقًا؟** نعم، استدعِ `FollowUpManager.clearFlag`.

## ما هو Outlook Follow Up Flag؟
Outlook follow up flag هو علامة مهمة مدمجة يمكنها إرفاق تاريخ بدء، وتذكير، وتاريخ استحقاق إلى أي عنصر بريد. يحول البريد العادي إلى عنصر عمل متتبع، مما يساعدك وفريقك على متابعة الأعمال المعلقة.

## لماذا نستخدم Aspose.Email للـ Java؟
Aspose.Email يوفر API نقي للـ Java يعمل دون الحاجة إلى تثبيت Outlook، مما يتيح لك التعامل مع ملفات .msg، وتعيين الأعلام، وإدارة المهام على أي منصة—مثالي لـ **automate outlook tasks**، خدمات الخلفية، أو التكامل مع أدوات إدارة المشاريع.

## المتطلبات المسبقة
- **Aspose.Email للـ Java** الإصدار 25.4 أو أحدث (المعروف أيضًا باسم **aspose email java**).  
- **JDK 16+** مثبت.  
- بيئة تطوير متوافقة مع Maven (IntelliJ IDEA، Eclipse، إلخ).  
- معرفة أساسية بـ Java وإلمام بمفاهيم البريد الإلكتروني.

## إعداد Aspose.Email للـ Java
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

### الحصول على الرخصة
يتطلب Aspose.Email رخصة للاستخدام في الإنتاج:

- **تجربة مجانية** – تقييم لمدة 30 يومًا.  
- **رخصة مؤقتة** – اختبار ممتد.  
- **رخصة كاملة** – اشتراك دائم.

قم بتهيئة الرخصة قبل أي عملية بريد إلكتروني:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## تعيين Outlook Follow Up Flag (الميزة 1)
### الخطوة 1: إنشاء وتهيئة الرسالة
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*نقوم أولاً بإنشاء `MailMessage`، وتحديد المرسل/المستلم، ثم تحويله إلى `MapiMessage` لتعديل العلم.*

### الخطوة 2: تعريف تواريخ المتابعة (تذكير علم Outlook)
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
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*كائن `FollowUpOptions` يحتوي على جميع تفاصيل العلم، والتي نطبقها باستخدام `FollowUpManager.setOptions`.*

### الخطوة 4: حفظ الرسالة
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*يتم حفظ الرسالة كملف `.msg` مع العلم المرفق.*

## كيفية تعيين علم للمستلمين (الميزة 2)
### نظرة عامة
أحيانًا تحتاج إلى ظهور العلم **فقط للمستلمين**. يوضح هذا المثال كيفية وضع الرسالة كمسودة أولاً، ثم إضافة العلم.

#### الخطوة 1: وضع كمسودة
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*وضع الرسالة كغير مرسلة يضمن أن Outlook يتعامل معها كمسودة.*

#### الخطوة 2: تعيين علم للمستلم
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*الآن يصبح العلم مرئيًا فقط للمستلمين – سيناريو كلاسيكي لـ **flag for recipients**.*

## كيفية وضع Outlook Follow Up Flag كمنتهي (الميزة 3)
### الخطوة 1: تحميل الرسالة
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### الخطوة 2: وضع كمنتهي وحفظ
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*يتغير حالة العلم إلى “Completed” ويتم حفظ الملف المحدث.*

## كيفية إزالة Outlook Follow Up Flag (الميزة 4)
### الخطوة 1: تحميل وإزالة العلم
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*يتم حفظ الرسالة دون أي علم متابعة.*

## كيفية قراءة خيارات العلم (الميزة 5)
### الخطوة 1: استرجاع الخيارات
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*كائن `options` الآن يحتوي على تواريخ البدء، والاستحقاق، والتذكير، بالإضافة إلى موضوع العلم – مفيد عندما تحتاج إلى **read flag options** للتقارير.*

## تطبيقات عملية
- **تكامل إدارة المهام:** مزامنة الرسائل الموسومة مع Jira أو Trello أو Azure Boards.  
- **تذكيرات آلية:** إنشاء رسائل تذكير يومية للمتابعات المعلقة.  
- **تدقيق الامتثال:** تصدير بيانات العلم للتقارير التنظيمية.

## اعتبارات الأداء
- **حسابات التاريخ:** احسب التواريخ مرة واحدة لكل دفعة بدلاً من داخل الحلقات.  
- **إدارة الموارد:** أغلق أي تدفقات أو مقبض ملفات بعد حفظ الرسائل.  
- **استخدام الذاكرة:** عالج صناديق البريد الكبيرة على دفعات لتجنب ضغط الذاكرة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| عدم ظهور العلم في Outlook | تم حفظ الرسالة بدون `MessageFlags` المناسبة | تأكد من ضبط `setMessageFlags` إلى `MSGFLAG_UNSENT` قبل تطبيق أعلام المستلمين. |
| عملية الحفظ تُطلق استثناء `AccessDeniedException` | مسار ملف غير صحيح أو عدم وجود أذونات كتابة | تحقق من وجود دليل الإخراج وأن التطبيق يمتلك صلاحيات الكتابة. |
| التواريخ متأخرة بيوم واحد | اختلاف المنطقة الزمنية | استخدم `TimeZone.getTimeZone("GMT")` أو منطقتك المحلية بشكل ثابت. |

## الأسئلة المتكررة
**س: ما هو Aspose.Email للـ Java؟**  
ج: هو API نقي للـ Java يتيح لك إنشاء، قراءة، وتعديل ملفات البريد (MSG، EML، إلخ) دون الحاجة إلى تثبيت Outlook.

**س: كيف أحصل على رخصة تجربة مجانية؟**  
ج: زر [موقع Aspose](https://releases.aspose.com/email/java/) لتنزيل تجربة لمدة 30 يومًا.

**س: هل يمكنني تعيين عدة أعلام متابعة على رسالة واحدة؟**  
ج: Outlook يدعم علمًا واحدًا فقط لكل رسالة، لكن يمكنك تخزين بيانات مهمة إضافية في خصائص MAPI مخصصة.

**س: رسالتي لا تُحفظ بعد تعيين العلم. ماذا يجب أن أتحقق؟**  
ج: تأكد من أن مسار `outputDir` صالح وأن التطبيق يمتلك صلاحية الكتابة إلى ذلك الموقع.

**س: كيف يمكنني إزالة الأعلام من العديد من الرسائل دفعة واحدة؟**  
ج: قم بالتكرار عبر مجموعة الرسائل واستدعِ `FollowUpManager.clearFlag` على كل `MapiMessage`.

## الموارد
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**آخر تحديث:** 2026-02-22  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}