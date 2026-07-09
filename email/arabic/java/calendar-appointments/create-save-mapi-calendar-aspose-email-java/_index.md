---
date: '2026-03-20'
description: تعلم كيفية تصدير تقويم Outlook بصيغة PST باستخدام Aspose.Email للغة Java
  – إنشاء عناصر تقويم MAPI، تعيين التكرار، إضافة الحضور، وحفظها إلى ملف PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: تصدير تقويم Outlook بصيغة PST باستخدام Aspose.Email – Java
url: /ar/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تصدير ملف PST لتقويم Outlook باستخدام Aspose.Email – Java

## مقدمة

هل تبحث عن تبسيط أتمتة التقويم في تطبيقات Java الخاصة بك وتحتاج إلى **export Outlook calendar PST**؟ باستخدام **Aspose.Email for Java**، يمكنك **create MAPI calendar Java**، تعريف أنماط التكرار، إضافة الحضور، و **save calendar to PST** ببضع أسطر من الشيفرة. يشرح هذا الدليل العملية بالكامل — من إعداد المكتبة إلى إنشاء إدخال تقويم كامل الوظائف جاهز للتوزيع.

### ما ستتعلمه
- كيفية **create MAPI calendar Java** الأحداث باستخدام Aspose.Email.  
- تكوين أنماط التكرار اليومية أو الأسبوعية أو المخصصة.  
- إضافة المستلمين (المنظمين، الحضور) إلى دعوات التقويم الخاصة بك.  
- حفظ عنصر التقويم عن طريق **saving calendar to PST** لتوافق Outlook.  
- كيفية **automate meeting scheduling** باستخدام كود قابل لإعادة الاستخدام.

## إجابات سريعة
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Export Outlook calendar PST و **save calendar to PST**  
- **Prerequisites?** Java 8+, Maven, ترخيص Aspose.Email  
- **Typical implementation time?** 10‑15 دقيقة لحدث أساسي  
- **Can I add recurrence?** نعم – يوميًا، أسبوعيًا، شهريًا، إلخ.

## تصدير Outlook calendar PST

في هذا القسم نركز على تدفق شامل يتيح لك **export Outlook calendar PST**. بعد إنشاء كائن تقويم MAPI، الخطوة الأخيرة هي تخزينه داخل ملف PST يمكن لـ Outlook قراءته مباشرة.

## لماذا تستخدم Aspose.Email لأتمتة التقويم؟

- **Full Outlook compatibility** – العناصر المُنشأة تعمل في Outlook و OWA والعملاء المحمولين.  
- **Rich recurrence support** – دعم يومي، أسبوعي، شهري، وأنماط مخصصة جاهزة للاستخدام.  
- **No external dependencies** – مكتبة Java صافية، لا حاجة لتفاعل COM.  
- **High performance** – معالجة فعّالة لملفات PST الكبيرة والعمليات الضخمة.  
- **Automate meeting scheduling** – دمج هذه المنطق في وظائف دفعة أو خدمات ويب لإنشاء مئات الدعوات تلقائيًا.

## المتطلبات المسبقة

### المكتبات المطلوبة
- **Aspose.Email for Java**: الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse.  
- Maven مثبت لإدارة التبعيات.

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية.  
- الإلمام بمفاهيم البرمجة الكائنية.

## إعداد Aspose.Email لـ Java

أضف تبعية Aspose.Email Maven إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

Aspose.Email يقدم نسخة تجريبية مجانية، لكن الترخيص يفتح جميع الميزات:

- **Free Trial**: اختبار بدون قيود لمدة 30 يومًا.  
- **Temporary License**: طلب عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/) إذا كنت بحاجة إلى وقت إضافي.  
- **Purchase**: شراء ترخيص دائم من [صفحة الشراء](https://purchase.aspose.com/buy).

### التهيئة الأساسية

بعد إضافة التبعية، قم بتهيئة المكتبة بملف الترخيص الخاص بك:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## دليل التنفيذ

الآن بعد أن تم إعدادك، دعنا **create MAPI calendar Java** و **save calendar to PST**.

### إنشاء تقويم MAPI مع التكرار

#### نظرة عامة

سنقوم بإنشاء حدث تقويم، تطبيق تكرار يومي، إضافة الحضور، وأخيرًا تخزينه في ملف PST.

#### تنفيذ خطوة بخطوة

1. **Initialize Date and Recurrence Pattern**  

   أولاً، حدد وقت البدء وضع تكرارًا يوميًا:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` يحتوي على تفاصيل التكرار؛ نختار نمطًا يوميًا عبر `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   أضف الأشخاص الذين يجب أن يتلقوا دعوة الاجتماع:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` يخزن كل حاضر؛ `MAPI_TO` يحددهم كمتلقين أساسيين.

3. **Create the MAPI Calendar Item**  

   بناء كائن التقويم بجميع التفاصيل المطلوبة:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Explanation*: المُنشئ يتوقع المنظم، الموضوع، الموقع، أوقات البدء/الانتهاء، الوصف، قائمة المستلمين، والتكرار.

4. **Save to PST File**  

   أخيرًا، احفظ التقويم عن طريق **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` ينشئ ملف PST جديد، و `addMapiMessageItem` يضيف إدخال التقويم إلى مجلد "Calendar".

### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من مسار الترخيص؛ الترخيص غير الصالح سيقيد الوظائف.  
- تأكد من تنسيق عناوين البريد الإلكتروني للمستلمين بشكل صحيح لتجنب فشل الدعوات.  
- أغلق ملف PST (`pst.dispose()`) بعد العمليات لتحرير مقبض الملف.

## تطبيقات عملية

فيما يلي سيناريوهات شائعة حيث يبرز **creating MAPI calendar Java** و **saving calendar to PST**:

1. **Automated Meeting Scheduling** – إنشاء دعوات اجتماعات متكررة لفرق المشروع دون جهد يدوي.  
2. **Event Management Platforms** – تصدير جلسات المؤتمرات كعناصر تقويم متوافقة مع Outlook.  
3. **CRM Integration** – مزامنة مواعيد العملاء من نظام CRM مباشرةً إلى Outlook عبر ملفات PST.

## اعتبارات الأداء

- **Resource Management**: تخلص من كائنات `PersonalStorage` بعد الاستخدام لتجنب حجز الملفات.  
- **Batch Processing**: للأحجام الكبيرة، عالج عناصر التقويم بشكل غير متزامن أو على دفعات للحفاظ على استهلاك الذاكرة منخفضًا.  

## الخلاصة

لقد تعلمت الآن كيفية **export Outlook calendar PST** بإنشاء كائنات MAPI calendar Java، تكوين التكرار، إضافة الحضور، و **save calendar to PST** باستخدام Aspose.Email. يتيح هذا النهج لتطبيقات Java الخاصة بك أتمتة سير عمل جدولة متقدم مع توافق Outlook.

للتعمق أكثر، راجع [documentation](https://reference.aspose.com/email/java/).

## قسم الأسئلة المتكررة

### س: هل يمكنني إنشاء أنماط تكرار أسبوعية؟
- **ج**: نعم! استخدم `MapiCalendarWeeklyRecurrencePattern` لتحديد التكرار الأسبوعي.

### س: كيف أتعامل مع الاستثناءات في تكرار الحدث؟
- **ج**: استدعِ `setExceptions()` على كائن التكرار لتحديد التواريخ التي تختلف عن النمط.

### س: هل يمكن تحديث عنصر تقويم موجود؟
- **ج**: بالتأكيد. حمّل العنصر من PST، عدّل خصائصه، واحفظه مرة أخرى.

### س: هل يمكنني تشفير ملف PST؟
- **ج**: نعم، يتيح لك Aspose.Email تعيين كلمة مرور على `PersonalStorage` عند إنشاء PST.

### س: ماذا لو أردت إضافة مرفقات إلى حدث التقويم؟
- **ج**: استخدم `calendar.getAttachments().addFileAttachment("path/to/file")` قبل الحفظ.

## الموارد

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}