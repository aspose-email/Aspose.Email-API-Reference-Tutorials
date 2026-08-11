---
date: '2026-08-01'
description: تعلم كيفية تصدير التقويم إلى PST باستخدام Aspose.Email for Java، بما
  في ذلك كيفية إضافة الحضور، وتحديد تواريخ البدء والانتهاء، وإدارة المواعيد بكفاءة.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: تصدير التقويم إلى PST باستخدام Aspose.Email for Java. تعلم خطوة بخطوة
  كيفية إنشاء المواعيد، وإضافة الحضور، وإنشاء ملفات Outlook PST.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: تصدير التقويم إلى PST – دليل شامل باستخدام Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: تصدير التقويم إلى PST باستخدام Aspose.Email for Java
url: /ar/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تصدير التقويم إلى PST باستخدام Aspose.Email للـ Java

إذا كنت تقوم بإنشاء تطبيق Java يحتاج إلى مشاركة بيانات الجدولة مع Outlook، فستحتاج غالبًا إلى **export calendar to PST**. في هذا البرنامج التعليمي سنستعرض كل ما تحتاجه — من إنشاء موعد بسيط إلى إضافة الحضور وأخيرًا كتابة الأحداث في ملف PST، كل ذلك باستخدام Aspose.Email للـ Java. في النهاية ستحصل على حل جاهز للإنتاج يعمل على Windows وLinux وmacOS.

## إجابات سريعة
- **What is the primary goal?** تصدير أحداث التقويم إلى ملف PST.  
- **Which library is required?** Aspose.Email للـ Java (v25.4+).  
- **Do I need a license?** نعم، ترخيص Aspose.Email صالح يزيل حدود التقييم.  
- **Can I add attendees?** بالتأكيد – استخدم `MapiRecipientCollection`.  
- **What Java version is supported?** JDK 16 أو أعلى.

## ما هو **export calendar to pst**؟
`MapiCalendar` هي فئة في Aspose.Email تمثل عنصر تقويم Outlook، بما في ذلك الموضوع والموقع وتفاصيل الوقت.

تصدير تقويم إلى PST يعني تحويل كائنات `MapiCalendar` الموجودة في الذاكرة إلى جدول تخزين شخصي في Microsoft Outlook (PST). يمكن فتح ملف PST الناتج مباشرةً في Outlook، أو مشاركته مع الزملاء، أو استيراده إلى أي نظام يفهم تنسيق PST، مع الحفاظ على جميع تفاصيل الحدث مثل الحضور، والتكرار، والتذكيرات.

## لماذا تستخدم Aspose.Email للـ Java لتصدير التقويم إلى PST؟
يمكنك إنشاء ملف PST متوافق بالكامل دون تثبيت Outlook. توفر Aspose.Email **دعم MAPI الكامل**، وتعمل على **جميع أنظمة التشغيل الرئيسية**، ويمكنها التعامل مع **ما يصل إلى 2 TB** من البيانات بتنسيق PST Unicode — وهو ما يكفي لأرشيفات على مستوى المؤسسات. كما تتيح لك الواجهة البرمجية إدارة الحضور، وأنماط التكرار، والتذكيرات، والخصائص المخصصة ببضع نداءات للطرق فقط، مما يقلل بشكل كبير من جهد التطوير.

## المتطلبات المسبقة
- **Libraries & Dependencies**: Aspose.Email للـ Java الإصدار 25.4 أو أحدث.  
- **Environment**: JDK 16 أو أعلى، Maven لإدارة الاعتمادات.  
- **Knowledge**: برمجة Java الأساسية ومعرفة بـ Maven.

## كيفية إعداد Aspose.Email للـ Java
أضف اعتماد Aspose.Email إلى ملف `pom.xml` الخاص بك وقم بتحديث مشروع Maven. هذه الخطوة الواحدة تجعل كامل واجهة MAPI API متاحة في مسار الفئات الخاص بك.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

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

1. **Free Trial**: زر [صفحة تحميل Aspose](https://releases.aspose.com/email/java/) للحصول على ترخيص مؤقت.  
2. **Temporary License**: قدّم طلبك عبر [صفحة الشراء](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: فكر في الشراء من [بوابة شراء Aspose](https://purchase.aspose.com/buy) للاستخدام طويل الأمد.

بعد حصولك على الترخيص، قم بتهيئته في تطبيقك لتمكين جميع الميزات.

## كيفية **create appointment** (إنشاء حدث تقويم Java)

حمّل كائن `MapiCalendar`، عيّن خصائصه الأساسية، وأعده جاهزًا للمعالجة الإضافية. هذه الطريقة تنشئ إدخالًا في التقويم مع موضوع وموقع ووصف، وتاريخ بدء **java calendar start date** / تاريخ انتهاء **java calendar end date** الذي حددته.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

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

*شرح*: فئة `MapiCalendar` هي تمثيل Aspose.Email لعنصر تقويم Outlook. بعد تعيين الحقول الأساسية يمكنك أيضًا تكوين التكرار، والتذكيرات، والفئات قبل الحفظ.

## كيفية **add attendees** (java add meeting attendees)

أنشئ `MapiRecipientCollection`، واملأه بكل مشارك، وأرفقه بالاجتماع. هذا يضمن أن كل حاضر يتلقى دعوة مناسبة عند فتح ملف PST.

`MapiRecipientCollection` هي فئة تجميع تحتفظ بكائنات `MapiRecipient` التي تمثل مشاركي الاجتماع. `MapiRecipient` يمثل حاضرًا فرديًا بخصائص مثل عنوان البريد الإلكتروني ونوع المستلم.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

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

*شرح*: `MapiRecipient` يحدد مشاركًا واحدًا في الاجتماع. تعيين النوع إلى `MAPI_TO` يضع العنوان كحاضر رئيسي، بينما يمكن استخدام `MAPI_CC` أو `MAPI_BCC` للمشاركين الاختياريين.

## كيفية **export calendar to pst** (إنشاء PST بأحداث التقويم)

أنشئ ملف PST Unicode، أضف مجلد "Calendar"، وأدرج كائنات `MapiCalendar` التي تم إنشاؤها مسبقًا. يمكن بعد ذلك فتح ملف PST في Outlook أو توزيعه على المستخدمين النهائيين.

`PersonalStorage` هي فئة Aspose.Email المستخدمة لإنشاء وفتح ومعالجة ملفات PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

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

*شرح*: `PersonalStorage` هي نقطة الدخول لمعالجة PST. باستخدام تنسيق Unicode تتجنب حد 2 GB لإصدارات PST القديمة وتستفيد من إدخال/إخراج أسرع في الأرشيفات الكبيرة.

## تطبيقات عملية
1. **Business Scheduling** – أتمتة إنشاء الاجتماعات الداخلية وتوزيعها.  
2. **Event Management** – تتبع المؤتمرات وورش العمل وقوائم المشاركين.  
3. **CRM Integration** – مزامنة المواعيد مع أدوات إدارة علاقات العملاء.  
4. **Project Planning** – تخزين معالم المشروع كعناصر تقويم.  
5. **Remote Team Collaboration** – إنشاء ملفات PST للمشاركة دون اتصال.

## اعتبارات الأداء
- **Dispose objects**: حرّر الكائنات التي لم تعد تحتاجها لتحرير الذاكرة بسرعة.  
- **Use efficient collections** (مثل `ArrayList` لقوائم الحضور) عند التعامل مع آلاف المشاركين.  
- **Cache frequently accessed events** إذا كنت تستعلم عن PST بشكل متكرر، لتقليل إدخال/إخراج القرص.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **لم يتم إنشاء ملف PST** | تحقق من أذونات الكتابة على الدليل المستهدف وتأكد من وجود مسار المجلد. |
| **الحضور لا يتلقون الدعوات** | تأكد من أن كل `MapiRecipient` يستخدم `MapiRecipientType.MAPI_TO` وأن بريد المنظم صالح. |
| **عدم تطابق التاريخ** | استخدم `Calendar` بشكل ثابت لتواريخ البدء/الانتهاء؛ تجنّب خلط `java.util.Date` مع مكتبات تاريخ أخرى دون تحويل. |

## الأسئلة المتكررة

**س: كيف أبدأ باستخدام Aspose.Email للـ Java؟**  
ج: أضف اعتماد Maven الموضح أعلاه، احصل على ترخيص، واتبع الخطوات في هذا الدليل لإنشاء وتصدير أحداث التقويم.

**س: هل يمكنني تخصيص اسم ملف PST وموقعه؟**  
ج: نعم، غيّر المتغير `pstFilePath` في الدالة `createPSTWithCalendarEvents()` إلى أي مسار صالح على نظامك.

**س: هل يمكن إضافة أنماط تكرار للمواعيد؟**  
ج: بالتأكيد – `MapiCalendar` يوفّر خاصية `RecurrencePattern` التي يمكنك تكوينها قبل الحفظ.

**س: هل يدعم Aspose.Email صيغ تقويم أخرى غير PST؟**  
ج: نعم، يمكنك التصدير إلى iCalendar (`.ics`) وصيغ أخرى باستخدام طرق الواجهة البرمجية المناسبة.

**س: ما هو الحد الأقصى لحجم ملف PST الذي يمكنني إنشاؤه؟**  
ج: باستخدام تنسيق Unicode (`FileFormatVersion.Unicode`)، يمكن أن يصل حجم ملفات PST إلى 2 TB، ويقتصر فقط على مساحة القرص المتاحة.

---

**آخر تحديث:** 2026-08-01  
**تم الاختبار مع:** Aspose.Email للـ Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إتقان Aspose.Email للـ Java: إدارة ملفات Outlook PST بفعالية](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [إتقان إنشاء وحفظ عناصر التقويم باستخدام Aspose.Email للـ Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [كيفية قراءة أحداث تقويم متعددة من ملف ICS باستخدام Aspose.Email في Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}