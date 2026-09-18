---
date: '2026-09-17'
description: تعلم كيفية إنشاء تقويم Outlook باستخدام Java مع daily recurrence والاستثناءات،
  وحفظ التقويم إلى PST باستخدام Aspose.Email for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: إنشاء تقويم Outlook في Java باستخدام Aspose.Email. تعلم daily recurrence،
  معالجة الاستثناءات، وحفظ إلى PST في دليل خطوة بخطوة.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: إنشاء تقويم Outlook في Java مع daily recurrence والاستثناءات
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: إنشاء تقويم Outlook باستخدام Java مع daily recurrence والاستثناءات
url: /ar/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تقويم Outlook Java مع التكرار اليومي والاستثناءات

إدارة الأحداث المتكررة بكفاءة يمكن أن تكون تحديًا، خاصة عندما تحتاج إلى **outlook calendar java** يدعم أنماط التكرار اليومي والاستثناءات العرضية. في هذا الدرس ستتعلم كيفية إنشاء كائنات Outlook calendar Java، تكوين التكرار اليومي، إضافة حالات استثناء، وأخيرًا **save calendar to PST** باستخدام Aspose.Email for Java. في النهاية ستحصل على مقتطف شفرة قابل لإعادة الاستخدام يمكنك إدراجه في أي خدمة جدولة مبنية على Java.

## إجابات سريعة
- **أي مكتبة؟** Aspose.Email for Java  
- **المهمة الأساسية؟** إنشاء Outlook calendar Java مع التكرار اليومي والاستثناءات  
- **متطلبات JDK؟** Java 16 أو أحدث  
- **هل يمكنني إرفاق ملفات إلى الاستثناءات؟** نعم، باستخدام `MapiCalendarExceptionInfo`  
- **أين يتم تخزين التقويم؟** في ملف PST عبر `PersonalStorage`  

## ما هو Outlook calendar java؟
كائن Outlook calendar Java هو تمثيل برمجي لموعد Outlook، مبني على مواصفة MAPI (Messaging Application Programming Interface)، والتي تشمل خصائص مثل الموضوع، الموقع، أوقات البدء/الانتهاء، قواعد التكرار، الحضور، والمرفقات. يمكن التلاعب بهذا الكائن، تسلسله، وتخزينه في ملفات PST دون الحاجة إلى Outlook.

## لماذا تستخدم Aspose.Email for Java؟
Aspose.Email for Java يتيح لك العمل مع كائنات MAPI دون تثبيت Outlook. تدعم المكتبة **50+ MAPI properties**، ويمكنها إنشاء ملفات PST Unicode تصل إلى **2 GB** في أقل من **2 seconds** لبيانات المواعيد النموذجية، وتعمل على أي منصة تدعم Java 16+. يتيح هذا النهج النقي‑Java إنشاء تقويمات على الخادم، سلاسل اجتماعات مؤتمتة، وتحكم كامل في منطق التكرار.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:
- **Aspose.Email Library**: الإصدار 25.4 (أو أحدث) – متاح عبر Maven أو تحميل مباشر.  
- **Java Development Kit (JDK)**: JDK 16 أو أحدث.  
- **IDE**: IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر متوافق مع Java.

### المكتبات والاعتمادات المطلوبة
لدمج Aspose.Email في مشروعك باستخدام Maven، أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
لاستخدام Aspose.Email، ستحتاج إلى ترخيص:
- **Free trial** – استكشاف جميع الميزات دون تكلفة.  
- **Temporary license** – طلب لتقييم ممتد.  
- **Full license** – شراء للاستخدام في بيئات الإنتاج.

## إعداد Aspose.Email for Java
أولاً، قم بإعداد بيئتك:

1. تحقق من تثبيت JDK 16 وتكوين `JAVA_HOME`.  
2. أضف اعتماد Maven (أو قم بتحميل ملف JAR) إلى مشروعك.  

إليك مقتطف صغير يوضح كيفية تحميل ملف الترخيص:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## دليل التنفيذ

### إنشاء outlook calendar java مع التكرار اليومي والاستثناءات

#### نظرة عامة
تتيح لك هذه الميزة أتمتة المواعيد المتكررة مع القدرة على تخطي أو تعديل حالات معينة.

#### تنفيذ خطوة بخطوة

**1. إعداد تاريخ بدء الحدث**  
حدد متى يجب أن يبدأ السلسلة:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. إنشاء كائن تقويم MAPI**  
فئة `MapiCalendar` هي الكائن الأعلى مستوى الذي يمثل عنصر تقويم واحد في الذاكرة. قدم الموقع، الموضوع، والوصف:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. تعريف نمط تكرار يومي**  
فئة `MapiCalendarRecurrencePattern` تخزن القاعدة التي تكرر الموعد كل يوم. قم بتكوين الحدث ليتكرر كل يوم:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. إضافة استثناء إلى التكرار**  
`MapiCalendarExceptionInfo` يصف حدوثًا واحدًا يختلف عن النمط—إما مستبعدًا أو معدلًا. حدد تاريخًا يجب استبعاده (أو تعديله):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### إرفاق ملفات إلى استثناءات التقويم

#### نظرة عامة
يمكنك إرفاق مستندات داعمة (مثل الجداول) إلى أي حالة استثناء.

**1. إنشاء وإرفاق ملف**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## حفظ outlook calendar java إلى PST (save calendar to pst)

#### نظرة عامة
احفظ التقويم في ملف PST حتى يتمكن Outlook أو العملاء الآخرون من قراءته.

**1. إنشاء وحفظ التقويم إلى PST**  
فئة `PersonalStorage` توفر طرقًا لإنشاء ملف PST جديد وإضافة عناصر MAPI إليه.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## تطبيقات عملية
- **Corporate scheduling** – أتمتة سلاسل الاجتماعات، مع تخطي العطلات تلقائيًا.  
- **Project management** – تتبع المعالم المتكررة مع تحولات تاريخية عرضية.  
- **Event planning** – إدارة مؤتمرات متعددة الأيام حيث يتم إلغاء أو إعادة جدولة بعض الجلسات.

### إمكانيات التكامل
اجمع Aspose.Email مع منصات CRM، واجهات برمجة تطبيقات إدارة المهام، أو محركات سير العمل المخصصة لتفعيل الأتمتة من البداية إلى النهاية.

## اعتبارات الأداء
- **Dispose resources** – دائمًا استدعِ `dispose()` على `PersonalStorage` لتحرير مقابض الملفات.  
- **Stream usage** – يفضَّل `ByteArrayOutputStream` أو تدفقات الملفات لتجنب تحميل ملفات PST بالكامل في الذاكرة.  
- **Async operations** – لتوليد تقويمات جماعية، شغِّل منطق الإنشاء على خيط خلفي للحفاظ على استجابة واجهة المستخدم.

## الخلاصة
باتباعك هذا الدليل، أصبحت الآن تعرف كيفية **create outlook calendar java** الكائنات مع التكرار اليومي، إضافة الاستثناءات، إرفاق الملفات، و**save calendar to PST**. تتيح لك هذه القدرات بناء ميزات جدولة قوية دون الحاجة إلى التعامل مع Outlook مباشرة.

### الخطوات التالية
- جرّب أنماط التكرار الأسبوعية أو الشهرية.  
- استكشف خصائص MAPI إضافية مثل الحضور، التذكيرات، والفئات.  
- راجع وثائق API الشاملة لـ Aspose.Email لمزيد من السيناريوهات المتقدمة.

## الأسئلة المتكررة

**س: هل تدعم المكتبة مواعيد مع مراعاة المنطقة الزمنية؟**  
ج: نعم، يمكنك تعيين خصائص `StartTimeZone` و `EndTimeZone` على `MapiCalendar`.

**س: هل يمكنني حذف حدوث واحد برمجيًا من سلسلة متكررة؟**  
ج: استخدم مجموعة `DeletedInstanceDates` في نمط التكرار لتحديد تواريخ معينة كملغاة.

**س: هل هناك حدود لحجم ملف PST الذي يتم إنشاؤه باستخدام Aspose.Email؟**  
ج: ملفات PST تتبع حدود تنسيق Unicode (حتى 2 GB افتراضيًا)، لكن يمكنك ضبط أحجام أكبر عبر إعدادات `PersonalStorage`.

**س: كيف يمكنني إضافة الحضور إلى طلب اجتماع؟**  
ج: أنشئ كائنات `MapiRecipient`، عيّن `RecipientType` إلى `MapiRecipientType.MAPI_TO`، وأضفها إلى مجموعة `Recipients` في `MapiMessage`.

**س: هل هناك دعم للمهام المتكررة (ليس فقط المواعيد)؟**  
ج: نعم، توفر Aspose.Email أيضًا `MapiTask` بقدرات تكرار مماثلة.

**س: هل يمكنني استخدام هذا الدليل كجزء من سلسلة دروس Aspose.Email Java؟**  
ج: بالتأكيد – الخطوات المعروضة هنا هي جزء أساسي من أي درس Aspose.Email Java يتعامل مع إنشاء التقويم.

## الموارد
- [توثيق Aspose.Email for Java](https://reference.aspose.com/email/java/)
- [تحميل Aspose.Email](https://releases.aspose.com/email/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى دعم Aspose](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-09-17  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [تصدير تقويم Outlook PST باستخدام Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [كيفية إنشاء عنصر تقويم Java باستخدام Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [إنشاء دعوة مشاركة تقويم مع Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}