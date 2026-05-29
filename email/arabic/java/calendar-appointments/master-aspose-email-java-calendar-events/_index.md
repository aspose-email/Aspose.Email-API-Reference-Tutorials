---
date: '2026-02-24'
description: تعلم كيفية تصدير التقويم إلى ملف PST باستخدام Aspose.Email للغة Java،
  بما في ذلك كيفية إضافة الحضور، وتحديد تاريخ البدء وتاريخ الانتهاء، وإدارة المواعيد
  بفعالية.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: تصدير التقويم إلى PST باستخدام Aspose.Email للـ Java
url: /ar/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تصدير التقويم إلى PST باستخدام Aspose.Email للـ Java

إذا كنت تقوم بإنشاء تطبيق Java يحتاج إلى مشاركة بيانات الجدولة مع Outlook، فستحتاج غالبًا إلى **تصدير التقويم إلى PST**. في هذا البرنامج التعليمي سنستعرض كل ما تحتاجه — من إنشاء موعد بسيط إلى إضافة الحضور وأخيرًا كتابة الأحداث في ملف PST، كل ذلك باستخدام Aspose.Email للـ Java.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** تصدير أحداث التقويم إلى ملف PST.  
- **ما المكتبة المطلوبة؟** Aspose.Email للـ Java (الإصدار 25.4 وما فوق).  
- **هل أحتاج إلى ترخيص؟** نعم، ترخيص Aspose.Email صالح يزيل حدود التقييم.  
- **هل يمكنني إضافة الحضور؟** بالتأكيد – استخدم `MapiRecipientCollection`.  
- **ما نسخة Java المدعومة؟** JDK 16 أو أعلى.

## ما هو **تصدير التقويم إلى pst**؟
يعني تصدير التقويم إلى PST تحويل كائنات `MapiCalendar` الموجودة في الذاكرة إلى جدول تخزين شخصي (PST) في Microsoft Outlook. يمكن فتح الملف الناتج مباشرةً في Outlook، أو مشاركته مع الزملاء، أو استيراده إلى أي نظام يفهم تنسيق PST.

## لماذا تستخدم Aspose.Email للـ Java لتصدير التقويم إلى PST؟
- **دعم كامل لـ MAPI** – إنشاء وتعديل وحفظ المواعيد دون الحاجة إلى تثبيت Outlook.  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.  
- **API غني** – إدارة الحضور، التكرار، التذكيرات، وأكثر.  
- **محسن للأداء** – التعامل مع كميات كبيرة من الأحداث بذاكرة منخفضة.

## المتطلبات المسبقة
- **المكتبات والاعتمادات**: Aspose.Email للـ Java الإصدار 25.4 أو أحدث.  
- **البيئة**: JDK 16 أو أعلى، Maven لإدارة الاعتمادات.  
- **المعرفة**: برمجة Java الأساسية ومعرفة بـ Maven.

## كيفية إعداد Aspose.Email للـ Java
أضف اعتماد Aspose.Email إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص
افتح جميع وظائف Aspose.Email دون قيود التقييم عن طريق الحصول على ترخيص:

1. **نسخة تجريبية مجانية**: زر [صفحة تنزيل Aspose](https://releases.aspose.com/email/java/) للحصول على ترخيص مؤقت.  
2. **ترخيص مؤقت**: قدِّم طلبًا عبر [صفحة الشراء](https://purchase.aspose.com/temporary-license/).  
3. **شراء ترخيص**: فكر في الشراء من [بوابة شراء Aspose](https://purchase.aspose.com/buy) للاستخدام طويل الأمد.

بمجرد حصولك على الترخيص، قم بتهيئته في تطبيقك لتمكين جميع الميزات.

## كيفية **إنشاء موعد** (Create Calendar Event Java)

### الخطوة 1: تحديد تاريخ البدء وتاريخ الانتهاء (java calendar start date / java calendar end date)
الطريقة التالية توضح كيفية تعيين تواريخ البدء والانتهاء لموعد وإرجاع كائن `MapiCalendar`:

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*شرح*: هذا المقتطف ينشئ `MapiCalendar` بموقع محدد، موضوع، وصف، و**java calendar start date** / **java calendar end date** التي حددتها.

## كيفية **إضافة الحضور** (java add meeting attendees)

### الخطوة 2: بناء قائمة الحضور
استخدم `MapiRecipientCollection` لتحديد من يجب أن يتلقى دعوة الاجتماع:

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*شرح*: هذا الكود ينشئ اجتماعًا، يحدد المنظم، ويربط قائمة **java add meeting attendees** بحيث يتلقى الجميع دعوة مناسبة.

## كيفية **تصدير التقويم إلى pst** (Create PST with calendar events)

### الخطوة 3: إنشاء ملف PST وإضافة الأحداث
الطريقة أدناه توضح إنشاء ملف PST Unicode وتخزين كل من الموعد البسيط والاجتماع مع الحضور:

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*شرح*: هذا المقتطف **يصدر التقويم إلى PST** بإنشاء حاوية PST، إضافة مجلد "Calendar" مُعرّف مسبقًا، وإدراج كائنات `MapiCalendar` التي تم بناؤها مسبقًا.

## تطبيقات عملية
1. **جدولة الأعمال** – أتمتة إنشاء الاجتماعات الداخلية وتوزيعها.  
2. **إدارة الفعاليات** – تتبع المؤتمرات، الورش، وقوائم المشاركين.  
3. **تكامل CRM** – مزامنة المواعيد مع أدوات إدارة علاقات العملاء.  
4. **تخطيط المشاريع** – تخزين معالم المشروع كعناصر تقويم.  
5. **تعاون الفرق عن بُعد** – إنشاء ملفات PST للمشاركة دون اتصال.

## اعتبارات الأداء
- **تحرير الكائنات** التي لم تعد بحاجة إليها لتحرير الذاكرة.  
- **اختيار مجموعات فعّالة** لقوائم الحضور الكبيرة.  
- **تخزين الأحداث المتكررة في الذاكرة المؤقتة** إذا كنت تستعلم عن PST بشكل متكرر.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **لم يتم إنشاء ملف PST** | تحقق من أذونات الكتابة على الدليل المستهدف وتأكد من وجود مسار المجلد. |
| **عدم تلقي الحضور للدعوات** | تأكد من أن كل `MapiRecipient` يستخدم `MapiRecipientType.MAPI_TO` وأن بريد المنظم صالح. |
| **عدم تطابق التاريخ** | استخدم `Calendar` بشكل ثابت لتواريخ البدء/الانتهاء؛ تجنّب خلط `java.util.Date` مع مكتبات تاريخ أخرى دون تحويل. |

## الأسئلة المتكررة

**س: كيف أبدأ باستخدام Aspose.Email للـ Java؟**  
ج: أضف اعتماد Maven الموضح أعلاه، احصل على ترخيص، واتبع الخطوات في هذا الدليل لإنشاء وتصدير أحداث التقويم.

**س: هل يمكنني تخصيص اسم ملف PST وموقعه؟**  
ج: نعم، غيّر المتغيّر `pstFilePath` في `createPSTWithCalendarEvents()` إلى أي مسار صالح على نظامك.

**س: هل يمكن إضافة نمط تكرار للمواعيد؟**  
ج: بالتأكيد – `MapiCalendar` يوفّر خصائص التكرار مثل `RecurrencePattern` التي يمكنك ضبطها قبل الحفظ.

**س: هل يدعم Aspose.Email صيغ تقويم أخرى غير PST؟**  
ج: نعم، يمكنك التصدير إلى iCalendar (`.ics`) وصيغ أخرى باستخدام طرق API المناسبة.

**س: ما هو الحد الأقصى لحجم ملف PST الذي يمكنني إنشاؤه؟**  
ج: باستخدام صيغة Unicode (`FileFormatVersion.Unicode`)، يمكن أن يصل حجم ملفات PST إلى 2 TB، محدودًا فقط بمساحة القرص المتاحة.

---

**آخر تحديث:** 2026-02-24  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}