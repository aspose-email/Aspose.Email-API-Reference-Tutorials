---
date: '2025-12-20'
description: تعلم كيفية إنشاء تقويم MAPI في Java، وإدارة أنماط التكرار اليومية، ومعالجة
  الاستثناءات باستخدام Aspose.Email للـ Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: إنشاء تقويم MAPI في Java مع تكرار يومي واستثناءات
url: /ar/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء mapi calendar java مع تكرار يومي واستثناءات

إدارة الأحداث المتكررة بفعالية يمكن أن تكون تحديًا، خاصةً عندما تكون هناك حاجة إلى استثناءات أو تغييرات. في هذا الدرس ستقوم **بإنشاء mapi calendar java**، وضبط نمط التكرار اليومي، وإضافة استثناءات باستخدام Aspose.Email for Java. ستتعلم كيفية أتمتة مهام الجدولة بسلاسة داخل تطبيقاتك.

## إجابات سريعة
- **أي مكتبة؟** Aspose.Email for Java  
- **المهمة الأساسية؟** إنشاء تقويم MAPI مع تكرار يومي واستثناءات  
- **متطلبات JDK؟** Java 16 أو أعلى  
- **هل يمكن إرفاق ملفات بالاستثناءات؟** نعم، باستخدام `MapiCalendarExceptionInfo`  
- **أين يُخزن التقويم؟** في ملف PST عبر `PersonalStorage`

### ما هو تقويم MAPI؟
تقويم MAPI (Messaging Application Programming Interface) هو تنسيق قياسي يستخدمه Microsoft Outlook والعملاء البريدية الآخرين لتخزين بيانات المواعيد. يدعم قواعد تكرار غنية، واستثناءات، ومرفقات، مما يجعله مثاليًا للجدولة المؤسسية.

### لماذا نستخدم Aspose.Email for Java؟
Aspose.Email توفر واجهة برمجة تطبيقات pure‑Java تتيح لك إنشاء وتعديل وحفظ كائنات MAPI دون الاعتماد على Outlook. هذا يعني أنه يمكنك بناء ميزات جدولة على الخادم، وإنشاء ملفات PST، ومعالجة سيناريوهات التكرار المعقدة برمجيًا.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:
- **مكتبة Aspose.Email**: الإصدار 25.4 (أو أحدث) – متاحة عبر Maven أو تحميل مباشر.  
- **مجموعة تطوير جافا (JDK)**: JDK 16 أو أحدث.  
- **بيئة تطوير متكاملة (IDE)**: IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر يدعم جافا.

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
- **نسخة تجريبية مجانية** – استكشف جميع الميزات دون تكلفة.  
- **ترخيص مؤقت** – اطلبه لتقييم ممتد.  
- **ترخيص كامل** – اشترِه للنشر في بيئات الإنتاج.

## إعداد Aspose.Email for Java

أولاً، قم بإعداد بيئتك:

1. تحقق من تثبيت JDK 16 وتكوين المتغير `JAVA_HOME`.  
2. أضف اعتماد Maven (أو حمّل ملف JAR) إلى مشروعك.  

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

### إنشاء تقويم MAPI مع تكرار يومي واستثناءات

#### نظرة عامة
تتيح لك هذه الميزة أتمتة المواعيد المتكررة مع القدرة على تخطي أو تعديل حالات معينة.

#### تنفيذ خطوة بخطوة

**1. ضبط تاريخ بدء الحدث**  
حدد متى يجب أن يبدأ السلسلة:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. إنشاء كائن تقويم MAPI**  
حدد الموقع، والموضوع، والوصف:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. تعريف نمط تكرار يومي**  
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
حدد تاريخًا يجب استبعاده (أو تعديله):

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
يمكنك إرفاق مستندات داعمة (مثل جداول الأعمال) إلى أي حالة استثناء.

**1. إنشاء وإرفاق ملف**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### حفظ تقويم MAPI في ملفات PST

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
- **جدولة الشركات** – أتمتة سلاسل الاجتماعات، وتخطي العطلات تلقائيًا.  
- **إدارة المشاريع** – تتبع المعالم المتكررة مع تحولات تاريخية عرضية.  
- **تخطيط الفعاليات** – إدارة مؤتمرات متعددة الأيام حيث يتم إلغاء أو إعادة جدولة بعض الجلسات.

### إمكانات التكامل
اجمع Aspose.Email مع منصات CRM، أو واجهات برمجة تطبيقات إدارة المهام، أو محركات سير العمل المخصصة لتقود الأتمتة من البداية إلى النهاية.

## اعتبارات الأداء
- **تحرير الموارد** – استدعِ دائمًا `dispose()` على `PersonalStorage` لتحرير مقابض الملفات.  
- **استخدام التدفقات** – فضل `ByteArrayOutputStream` أو تدفقات الملفات لتجنب تحميل ملفات PST بالكامل في الذاكرة.  
- **العمليات غير المتزامنة** – لإنشاء تقاويم جماعية، شغّل منطق الإنشاء في خيط خلفي للحفاظ على استجابة واجهة المستخدم.

## الخلاصة
باتباع هذا الدليل، أصبحت الآن تعرف كيفية **إنشاء mapi calendar java** مع تكرار يومي، وإضافة استثناءات، وإرفاق ملفات، وتخزين كل ذلك في ملف PST. هذه القدرات تتيح لك بناء ميزات جدولة قوية دون الحاجة إلى التعامل مع Outlook مباشرة.

### الخطوات التالية
- جرب أنماط التكرار الأسبوعية أو الشهرية.  
- استكشف خصائص MAPI إضافية مثل الحضور، والتذكيرات، والفئات.  
- راجع وثائق Aspose.Email الشاملة للحصول على سيناريوهات أكثر تقدمًا.

## قسم الأسئلة المتكررة
1. **هل يمكنني استخدام Aspose.Email بدون ترخيص؟**  
   - نعم، يمكنك البدء بالنسخة التجريبية المجانية لاستكشاف إمكاناتها.  
2. **كيف أتعامل مع الاستثناءات في الأحداث المتكررة؟**  
   - استخدم `MapiCalendarExceptionInfo` لتحديد التاريخ، والأوقات المعدلة، وأي بيانات مرفقة.  
3. **هل يمكن حفظ التقويمات مباشرةً في ملفات PST؟**  
   - بالتأكيد. تسمح لك فئة `PersonalStorage` بإنشاء ملفات PST وإضافة عناصر التقويم.  
4. **هل يمكن دمج هذا مع تطبيقات جافا أخرى؟**  
   - نعم، الواجهة برمجة التطبيقات pure Java، لذا يمكنك تضمينها في أي خدمة أو تطبيق سطح مكتب مبني على جافا.  
5. **ماذا أفعل إذا انتهى ترخيصي؟**  
   - جدد الترخيص عبر بوابة Aspose أو عد إلى وضع التجربة مؤقتًا.

## الأسئلة المتكررة الشائعة

**س: هل تدعم المكتبة مواعيد مع مراعاة المنطقة الزمنية؟**  
ج: نعم، يمكنك ضبط خصائص `StartTimeZone` و `EndTimeZone` على `MapiCalendar`.

**س: هل يمكنني حذف حدوث واحد من سلسلة متكررة برمجيًا؟**  
ج: استخدم مجموعة `DeletedInstanceDates` في نمط التكرار لتحديد التواريخ التي يجب إزالتها.

**س: هل هناك حدود لحجم ملف PST الذي يتم إنشاؤه باستخدام Aspose.Email؟**  
ج: ملفات PST تتبع حدود تنسيق Unicode (حتى 2 GB افتراضيًا)، لكن يمكنك ضبط أحجام أكبر عبر إعدادات `PersonalStorage`.

**س: كيف أضيف الحضور إلى طلب اجتماع؟**  
ج: أنشئ كائنات `MapiRecipient`، واضبط `RecipientType` إلى `MapiRecipientType.MAPI_TO`، ثم أضفها إلى مجموعة `Recipients` في `MapiMessage`.

**س: هل هناك دعم للمهام المتكررة (ليس فقط المواعيد)؟**  
ج: نعم، توفر Aspose.Email أيضًا `MapiTask` مع قدرات تكرار مماثلة.

## الموارد
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose