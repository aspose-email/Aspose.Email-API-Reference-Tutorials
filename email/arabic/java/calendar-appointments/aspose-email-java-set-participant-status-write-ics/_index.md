---
date: '2026-09-12'
description: تعلم كيفية إنشاء ملف iCalendar باستخدام Java عبر Aspose.Email، ضبط حالة
  الحضور، وإنشاء أحداث تقويم متعددة بكفاءة.
keywords:
- create icalendar file java
- java generate ics calendar
- aspose email java
- ics export java
lastmod: '2026-09-12'
og_description: إنشاء ملف iCalendar باستخدام Java عبر Aspose.Email. ضبط حالة الحضور،
  كتابة أحداث متعددة، والتكامل مع Outlook وGoogle Calendar والمزيد.
og_image_alt: Guide to creating iCalendar files in Java with Aspose.Email
og_title: إنشاء ملف iCalendar باستخدام Java – تصدير ملف ICS باستخدام Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  headline: How to create iCalendar file Java – export ICS with Aspose.Email
  type: TechArticle
- description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  name: How to create iCalendar file Java – export ICS with Aspose.Email
  steps:
  - name: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
    text: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
  - name: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
    text: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
  - name: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
    text: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
  - name: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
    text: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
  - name: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
    text: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
  type: HowTo
- questions:
  - answer: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide
      the UID of the appointment you wish to update.
    question: Can I update an existing ICS file instead of creating a new one?
  - answer: Absolutely. Configure recurrence patterns on the `Appointment` object
      before writing to the ICS file.
    question: Does Aspose.Email support recurring events?
  - answer: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")`
      to embed non‑standard fields.
    question: Is it possible to add custom properties to an ICS event?
  - answer: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are
      supported.
    question: What time‑zone formats are accepted?
  - answer: A temporary license removes evaluation restrictions; a full license is
      required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- create icalendar file java
- aspose.email
- java calendar integration
title: كيفية إنشاء ملف iCalendar باستخدام Java – تصدير ملف ICS باستخدام Aspose.Email
url: /ar/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء ملف iCalendar في Java – تصدير ICS باستخدام Aspose.Email

إدارة جداول الاجتماعات عبر المناطق الزمنية يمكن أن تكون مرهقة، خاصة عندما تحتاج إلى مشاركة الدعوات مع العشرات من المشاركين. في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء ملف iCalendar في Java** باستخدام Aspose.Email for Java، وتعيين حالة الحضور، وكتابة أحداث تقويم متعددة إلى ملف `.ics` واحد. مقتطفات الشيفرة خطوة بخطوة جاهزة للنسخ إلى مشروعك، والشروحات توضح سبب أهمية كل جزء.

## إجابات سريعة
- **هل يمكنني تعيين حالة الحضور باستخدام Aspose.Email for Java؟** نعم – يمكنك تعيين القيم Accepted أو Declined أو Tentative لكل مشارك.  
- **كم عدد الأحداث التي يمكنني كتابتها إلى ملف ICS واحد؟** المكتبة لا تفرض حدًا ثابتًا؛ المثال يوضح عشرة أحداث، ويمكنك التوسع إلى آلاف.  
- **هل أحتاج إلى رخصة للتطوير؟** رخصة مؤقتة مجانية تزيل قيود التقييم؛ رخصة مدفوعة مطلوبة للإنتاج.  
- **ما نسخة Java الموصى بها؟** JDK 16 (أو أحدث) تتطابق مع المصنف المقدم وتضمن توافق كامل مع API.  
- **هل معالجة المنطقة الزمنية تلقائية؟** يمكنك تحديد المنطقة الزمنية عند إنشاء التواريخ، وستقوم Aspose.Email بدمج TZID الصحيح.

## ما هو iCalendar ولماذا هو مهم؟
تنسيق iCalendar (ICS) هو المعيار العالمي لتبادل بيانات التقويم بين Outlook وGoogle Calendar وApple Calendar والعديد من العملاء الآخرين. تصدير إلى iCalendar يتيح لك توزيع دعوات الاجتماعات، إنشاء أحداث بالجملة، أو دمج الأنظمة القديمة دون فقدان حالة المشاركين أو الخصائص المخصصة.

## لماذا نستخدم Aspose.Email for Java لتصدير ملفات iCalendar؟
توفر Aspose.Email تحكمًا دقيقًا في كل عنصر من عناصر iCalendar مع الحفاظ على بساطة التنفيذ. تدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، وتتعامل مع تقاويم مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، وتعمل على أي منصة تدعم Java 16 أو أحدث. هذا يعني أنك تستطيع إنشاء ملفات `.ics` قوية تُعرض بشكل صحيح في جميع عملاء التقويم الرئيسيين.

## المتطلبات المسبقة

قبل البدء، تأكد من توفر ما يلي:

### المكتبات المطلوبة والإصدارات
- **Aspose.Email for Java** الإصدار 25.4 أو أحدث (تحتوي المكتبة على أكثر من 30 فئة لمعالجة iCalendar).  
- Maven لإدارة الاعتمادات (أو تحميل ملف JAR مباشرة من [Aspose](https://releases.aspose.com/email/java/)).

### إعداد البيئة
- JDK 16 (أو أحدث) مثبت على جهازك.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية.  
- الإلمام بـ `java.util.Calendar` و`java.util.Date` لمعالجة التاريخ والوقت.

## إعداد Aspose.Email for Java

أضف مكتبة Aspose.Email إلى مشروع Maven الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### خطوات الحصول على الرخصة

1. **Free trial** – تحميل رخصة مؤقتة لاختبار Aspose.Email بدون قيود. زر [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) للمزيد من التفاصيل.  
2. **Purchase** – للاستخدام طويل الأمد، اشترِ اشتراكًا عبر [Aspose Purchase](https://purchase.aspose.com/buy).

قم بتهيئة الرخصة في الشيفرة الخاصة بك:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

الآن أنت جاهز للغوص في المميزتين الأساسيتين لهذا الدليل.

## كيفية تصدير ملف iCalendar في Java: تعيين حالة المشاركين في مواعيد الاجتماع

### ما هي حالة المشاركين في موعد التقويم؟
تسجل حالة المشاركين كيفية استجابة الحاضر للدعوة—Accepted أو Declined أو Tentative. تعيين هذه الحالة برمجيًا أمر أساسي لأنظمة الجدولة الآلية وتتبع الاجتماعات بدقة.

يمكنك تعيين حالة المشاركين مباشرةً على كل كائن `Attendee` قبل كتابة ملف التقويم.

### تنفيذ خطوة بخطوة

#### 1️⃣ إنشاء وتكوين تواريخ الموعد
`java.util.Calendar` هي فئة Java للتعامل مع قيم التاريخ والوقت. حدد أوقات البدء والانتهاء باستخدام `java.util.Calendar`. المكتبة تحترم معرف المنطقة الزمنية المزود.

```java
String location = "Room 5";
Calendar calendar = Calendar.getInstance();

// Set start date and time
calendar.set(2011, Calendar.NOVEMBER, 10, 10, 12, 11);
Date startDate = calendar.getTime();

// Set end date and time
calendar.set(2012, Calendar.OCTOBER, 13, 13, 11, 12);
Date endDate = calendar.getTime();
```

#### 2️⃣ تعريف المنظم وقائمة الحضور
`AttendeeCollection` هي فئة تجميع تحتفظ بكائنات `Attendee` التي تمثل مشاركي الاجتماع. أنشئ `AttendeeCollection` وأضف عنوان البريد الإلكتروني لكل مشارك.

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ تعيين حالة المشاركة لكل حضور
`ResponseType` تشير إلى حالة رد الحضور مثل Accepted أو Declined أو Tentative. عيّن خاصية `ResponseType` على كل `Attendee` لتحديد الحالة المطلوبة.

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ إنشاء كائن `Appointment`
`Appointment` يمثل حدثًا تقويميًا يحتوي على تفاصيل مثل الموضوع والموقع والوقت. بعد تكوين التواريخ والمنظم والحضور، يمكنك تسلسل الكائن إلى iCalendar.

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**نصيحة احترافية:** تحقق دائمًا من صحة عناوين البريد الإلكتروني باستخدام تعبير عادي بسيط قبل إضافتها إلى التجميع؛ العناوين غير الصحيحة تسبب استثناء `ParseException`.

## كيفية تصدير ملف iCalendar في Java: كتابة أحداث متعددة إلى ملف ICS

### لماذا تصدر التقويم إلى iCalendar باستخدام Java؟
تنسيق iCalendar مفهوم عالميًا، مما يتيح لك مشاركة معلومات الاجتماعات عبر Outlook وGoogle Calendar وApple Calendar والعديد من العملاء الآخرين. عبر **java generate ics calendar** باستخدام Aspose.Email، تحتفظ بحالة المشاركين، والخصائص المخصصة، وقواعد التكرار دون خطوات تحويل إضافية.

### تنفيذ خطوة بخطوة

#### 1️⃣ تكوين خيارات الحفظ وإنشاء كاتب
`IcsSaveOptions` يحدد كيفية كتابة ملف iCalendar، بما في ذلك الترميز وخيارات التنسيق. إعادة استخدام نسخة واحدة من `IcsSaveOptions` يحسن الأداء عند معالجة عدد كبير من الأحداث.

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ تحديد الإطار الزمني لكل حدث
`java.util.Date` يمثل لحظة زمنية محددة، عادةً ما يستخدم لتواريخ البدء والانتهاء. قم بالتكرار عبر مصدر البيانات الخاص بك، وأنشئ كائنات `Date` للبدء/الانتهاء لكل موعد.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ إعداد مجموعة الحضور
أنشئ `AttendeeCollection` مرة واحدة وأرفقها بكل `Appointment` تقوم بإنشائه.

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ توليد وكتابة مواعيد متعددة
قم بالتكرار، أنشئ `Appointment` لكل سجل، واستدعِ `writer.write(appointment)`. أخيرًا، حرّر الكاتب بإغلاق الملف.

```java
try {
    for (int i = 0; i < 10; i++) {
        Appointment app = new Appointment("Room 112", startDate, endDate,
                new MailAddress("organizer@domain.com"), attendees);
        app.setDescription("Test body " + i);
        app.setSummary("Test summary:" + i);
        
        writer.write(app); // Write the appointment to ICS file
    }
} finally {
    writer.dispose(); // Clean up resources
}
```

**مشكلة شائعة:** نسيان استدعاء `writer.dispose()` يترك الملف مفتوحًا، مما يسبب أخطاء “الملف قيد الاستخدام” في التشغيلات اللاحقة.

## تطبيقات عملية

تتفوق Aspose.Email for Java في العديد من السيناريوهات الواقعية:

1. **جدولة الاجتماعات تلقائيًا** – إنشاء دعوات تقويمية في الوقت الفعلي للأدوات الداخلية أو أنظمة CRM.  
2. **دمج التقويم عبر المنصات** – تصدير المواعيد من قواعد البيانات القديمة إلى Outlook أو Google Calendar أو Apple Calendar باستخدام تنسيق iCalendar القياسي.  
3. **منصات إدارة الفعاليات** – إنشاء جداول مؤتمرات، ورش عمل، أو ندوات عبر واجهة API واحدة، مع الحفاظ على جميع ردود الحضور.

## اعتبارات الأداء

عند العمل مع **Aspose.Email for Java**، ضع في اعتبارك النصائح التالية:

- حرّر كائنات `CalendarWriter` و`Appointment` وأي كائنات `MailMessage` بمجرد الانتهاء لتفريغ الموارد الأصلية.  
- عالج المواعيد على دفعات عند التعامل مع مجموعات بيانات كبيرة؛ هذا يقلل من حمل جمع القمامة بنسبة تصل إلى 30 %.  
- أعد استخدام نسخة واحدة من `IcsSaveOptions` بدلاً من إنشاء نسخة جديدة لكل عملية كتابة.

## الأسئلة المتكررة

**س: هل يمكنني تحديث ملف ICS موجود بدلاً من إنشاء ملف جديد؟**  
ج: نعم. عيّن `saveOptions.setAction(AppointmentAction.Modify)` وقدم الـ UID للموعد الذي ترغب في تحديثه.

**س: هل تدعم Aspose.Email الأحداث المتكررة؟**  
ج: بالتأكيد. قم بتكوين أنماط التكرار على كائن `Appointment` قبل الكتابة إلى ملف ICS.

**س: هل يمكن إضافة خصائص مخصصة إلى حدث ICS؟**  
ج: نعم. استخدم `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` لإدراج حقول غير قياسية.

**س: ما صيغ المناطق الزمنية المدعومة؟**  
ج: كل من معرفات المناطق الزمنية IANA (مثل “America/New_York”) وإزاحات GMT مدعومة.

**س: هل أحتاج رخصة لبناءات التطوير؟**  
ج: رخصة مؤقتة تزيل قيود التقييم؛ رخصة كاملة مطلوبة للنشر في بيئات الإنتاج.

## الخلاصة

أنت الآن تعرف **كيفية إنشاء ملف iCalendar في Java**، وتعيين حالة المشاركين، وكتابة أحداث متعددة باستخدام Aspose.Email for Java. هذه القدرات تمكنك من بناء ميزات جدولة قوية، التكامل مع أي عميل تقويم، وتبسيط توزيع الأحداث عبر مؤسستك.

---

**آخر تحديث:** 2026-09-12  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء ملف .ics Java – إنشاء دعوة تقويم باستخدام Aspose.Email for Java – دليل كامل](/email/java/)
- [تحليل ملف ics Java – قراءة أحداث التقويم باستخدام Aspose.Email](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [إنشاء دعوة مشاركة تقويم باستخدام Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}