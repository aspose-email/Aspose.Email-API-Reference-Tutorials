---
date: '2026-03-20'
description: تعرّف على كيفية إنشاء تقويم Outlook باستخدام Java مع تكرار يومي واستثناءات،
  وحفظ التقويم إلى ملف PST باستخدام Aspose.Email للـ Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: إنشاء تقويم Outlook بلغة Java مع تكرار يومي واستثناءات
url: /ar/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء outlook calendar java مع التكرار اليومي والاستثناءات

إدارة الأحداث المتكررة بكفاءة يمكن أن تكون صعبة، خاصة عندما تحتاج إلى **outlook calendar java** يدعم أنماط التكرار اليومي والاستثناءات العرضية. في هذا الدرس ستتعلم كيفية إنشاء كائنات Outlook calendar Java، تكوين التكرار اليومي، إضافة حالات الاستثناء، وأخيرًا **save calendar to PST** باستخدام Aspose.Email for Java. في النهاية ستحصل على مقتطف شفرة قابل لإعادة الاستخدام يمكنك إدراجه في أي خدمة جدولة مبنية على Java.

## إجابات سريعة
- **أي مكتبة؟** Aspose.Email for Java  
- **المهمة الأساسية؟** Create an Outlook calendar Java with daily recurrence and exceptions  
- **متطلبات JDK؟** Java 16 or higher  
- **هل يمكنني إرفاق ملفات بالاستثناءات؟** Yes, using `MapiCalendarExceptionInfo`  
- **أين يتم تخزين التقويم؟** In a PST file via `PersonalStorage`

## ما هو Outlook calendar java؟
كائن Outlook calendar Java (المُنفذ كتقويم MAPI) يتبع نفس المعايير الخاصة بمواعيد Microsoft Outlook. يخزن قواعد تكرار غنية، معالجة الاستثناءات، الحضور، والمرفقات، مما يجعله مثاليًا للجدولة على مستوى المؤسسات.

## لماذا تستخدم Aspose.Email for Java؟
توفر Aspose.Email واجهة برمجة تطبيقات pure‑Java تتيح لك العمل مع كائنات MAPI دون الحاجة إلى تثبيت Outlook. يتيح هذا النهج **aspose email tutorial java** إنشاء ملفات PST من جانب الخادم، سلاسل الاجتماعات الآلية، وتحكم كامل في منطق التكرار.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:

- **Aspose.Email Library**: الإصدار 25.4 (أو أحدث) – متاح عبر Maven أو التحميل المباشر.  
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

- **Free Trial** – استكشف جميع الميزات دون تكلفة.  
- **Temporary License** – طلب لتقييم ممتد.  
- **Full License** – شراء للاستخدام في بيئات الإنتاج.  

## إعداد Aspose.Email for Java
أولاً، قم بإعداد بيئتك:

1. تحقق من تثبيت JDK 16 وتكوين `JAVA_HOME`.  
2. أضف اعتماد Maven (أو قم بتحميل ملف JAR) إلى مشروعك.  

إليك مقتطفًا صغيرًا يوضح كيفية تحميل ملف الترخيص:

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

### إنشاء Outlook calendar java مع التكرار اليومي والاستثناءات

#### نظرة عامة
تتيح لك هذه الميزة أتمتة المواعيد المتكررة مع القدرة على تخطي أو تعديل حالات معينة.

#### تنفيذ خطوة بخطوة

**1. إعداد تاريخ بدء الحدث**  
حدد متى يجب أن يبدأ السلسلة:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. إنشاء كائن MAPI Calendar**  
حدد الموقع، العنوان، والوصف:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. تعريف نمط التكرار اليومي**  
قم بتكوين الحدث ليتكرر كل يوم:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. إضافة استثناء إلى التكرار**  
حدد تاريخًا يجب استثناؤه (أو تعديله):

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

### حفظ Outlook calendar java إلى PST (save calendar to pst)

#### نظرة عامة
احفظ التقويم في ملف PST حتى يتمكن Outlook أو العملاء الآخرين من قراءته.

**1. إنشاء وحفظ التقويم إلى PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## التطبيقات العملية
- **Corporate Scheduling** – أتمتة سلاسل الاجتماعات، مع تخطي العطلات تلقائيًا.  
- **Project Management** – تتبع المراحل المتكررة مع تحولات تاريخية عرضية.  
- **Event Planning** – إدارة مؤتمرات متعددة الأيام حيث يتم إلغاء أو إعادة جدولة بعض الجلسات.

### إمكانات التكامل
اجمع Aspose.Email مع منصات CRM، واجهات برمجة تطبيقات إدارة المهام، أو محركات سير العمل المخصصة لتحقيق أتمتة شاملة من البداية إلى النهاية.

## اعتبارات الأداء
- **Dispose Resources** – دائمًا استدعِ `dispose()` على `PersonalStorage` لتحرير مقابض الملفات.  
- **Stream Usage** – يفضَّل استخدام `ByteArrayOutputStream` أو تدفقات الملفات لتجنب تحميل ملفات PST بالكامل في الذاكرة.  
- **Async Operations** – لإنشاء تقاويم جماعية، شغِّل منطق الإنشاء في خيط خلفي للحفاظ على استجابة واجهة المستخدم.

## الخلاصة
باتباعك لهذا الدليل، أصبحت الآن تعرف كيفية **create outlook calendar java** الكائنات مع التكرار اليومي، إضافة الاستثناءات، إرفاق الملفات، و**save calendar to PST**. تتيح لك هذه الإمكانيات بناء ميزات جدولة قوية دون الحاجة إلى التعامل مع Outlook مباشرة.

### الخطوات التالية
- جرب أنماط التكرار الأسبوعية أو الشهرية.  
- استكشف خصائص MAPI الإضافية مثل الحضور، التذكيرات، والفئات.  
- راجع وثائق API الشاملة لـ Aspose.Email لمزيد من السيناريوهات المتقدمة.

## الأسئلة المتكررة

**س: هل تدعم المكتبة المواعيد المدركة للمنطقة الزمنية؟**  
نعم، يمكنك تعيين خصائص `StartTimeZone` و `EndTimeZone` على `MapiCalendar`.

**س: هل يمكنني حذف حدوث واحد برمجيًا من سلسلة متكررة؟**  
استخدم مجموعة `DeletedInstanceDates` في نمط التكرار لتحديد التواريخ المحددة كحُذفت.

**س: هل هناك حدود لحجم ملف PST الذي تم إنشاؤه باستخدام Aspose.Email؟**  
تتبع ملفات PST حدود تنسيق Unicode (حتى 2 GB افتراضيًا)، لكن يمكنك ضبط أحجام أكبر عبر إعدادات `PersonalStorage`.

**س: كيف يمكنني إضافة الحضور إلى طلب اجتماع؟**  
أنشئ كائنات `MapiRecipient`، عيّن خاصية `RecipientType` إلى `MapiRecipientType.MAPI_TO`، وأضفها إلى مجموعة `Recipients` في `MapiMessage`.

**س: هل هناك دعم للمهام المتكررة (ليس فقط المواعيد)؟**  
نعم، توفر Aspose.Email أيضًا `MapiTask` بقدرات تكرار مماثلة.

**س: هل يمكنني استخدام هذا الدليل كجزء من سلسلة دروس aspose email tutorial java؟**  
بالطبع – الخطوات المعروضة هنا هي جزء أساسي من أي درس Aspose.Email Java يتعامل مع إنشاء التقويم.

## الموارد
- [وثائق Aspose.Email for Java](https://reference.aspose.com/email/java/)
- [تحميل Aspose.Email](https://releases.aspose.com/email/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى دعم Aspose](https://forum.aspose.com/c/email/10)

**آخر تحديث:** 2026-03-20  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}