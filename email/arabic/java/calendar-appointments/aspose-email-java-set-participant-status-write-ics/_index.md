---
date: '2026-03-18'
description: تعلم كيفية تصدير ملفات ics باستخدام Aspose.Email للغة Java، وتعيين حالة
  الحضور، وكتابة عدة أحداث تقويمية بكفاءة.
keywords:
- Aspose.Email Java
- set participant status in Java
- write ICS files with Java
title: كيفية تصدير ملف ICS – تعيين الحالة – Aspose.Email Java
url: /ar/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

Options`, etc.

Also keep markdown links unchanged.

Proceed step by step.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تصدير ملفات ICS – تعيين الحالة – Aspose.Email Java

إدارة جداول الاجتماعات بفعالية تُعدّ تحديًا يواجهه العديد من المهنيين، خاصةً عند التعامل مع مشاركين متعددين عبر مناطق زمنية مختلفة. في هذا الدرس ستكتشف **كيفية تصدير ملفات ics** باستخدام Aspose.Email for Java، وتعيين حالات المشاركين (الحضور)، وكتابة عدة أحداث تقويم في ملف واحد—كل ذلك مع شفرة خطوة بخطوة يمكنك نسخها إلى مشروعك.

## إجابات سريعة
- **هل يمكنني تعيين حالة الحضور باستخدام Aspose.Email for Java؟** نعم – يمكنك تعيين القيم Accepted أو Declined أو Tentative.  
- **كم عدد الأحداث التي يمكنني كتابتها في ملف ICS واحد؟** المكتبة تدعم أي عدد؛ المثال يُنشئ عشرة أحداث.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت مجاني يعمل للتقييم؛ الترخيص المدفوع مطلوب للإنتاج.  
- **ما نسخة Java الموصى بها؟** JDK 16 (أو أحدث) تتطابق مع المصنف المرفق.  
- **هل معالجة المنطقة الزمنية تلقائية؟** يمكنك تحديد المنطقة الزمنية عند إنشاء التواريخ؛ المكتبة تحترمها.

## ما هو “كيفية تصدير ics” ولماذا يهم؟

صيغة ICS (iCalendar) هي المعيار الفعلي لتبادل معلومات التقويم بين Outlook، Google Calendar، Apple Calendar، والعديد من العملاء الآخرين. يسمح التصدير إلى ICS بتوزيع دعوات الاجتماعات، إنشاء أحداث بالجملة، أو دمج الأنظمة القديمة دون فقدان حالة المشاركين أو الخصائص المخصصة.

## لماذا نستخدم Aspose.Email for Java لتصدير ics؟

- **تحكم كامل** في ردود الحضور (Accepted/Declined/Tentative).  
- **بدون تبعيات خارجية** – المكتبة تتعامل مع جميع مواصفات iCalendar داخليًا.  
- **كتابة جماعية** – يمكنك توليد العشرات أو المئات من الأحداث بكتّاب واحد، مما يحافظ على كفاءة مقبض الملف.  
- **توافق متعدد المنصات** – ملفات ICS المُولدة تعمل على أي عميل تقويم يتبع معيار RFC 5545.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

### المكتبات والإصدارات المطلوبة
- **Aspose.Email for Java** الإصدار 25.4 أو أحدث.  
- Maven لإدارة التبعيات (أو تحميل مباشرة من [Aspose](https://releases.aspose.com/email/java/)).

### متطلبات إعداد البيئة
- مجموعة تطوير Java (JDK) مثبتة على جهازك، ويفضل JDK 16 لتطابق المصنف Aspose.Email المستخدم في هذا الدرس.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

### المتطلبات المعرفية
- مهارات برمجة Java أساسية.  
- الإلمام بـ `java.util.Calendar` و `java.util.Date` لمعالجة التاريخ‑الوقت.

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

### خطوات الحصول على الترخيص

1. **تجربة مجانية** – حمّل ترخيصًا مؤقتًا لاختبار Aspose.Email بدون قيود. زر [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) للمزيد من التفاصيل.  
2. **شراء** – للاستخدام طويل الأمد، اشترِ اشتراكًا عبر [Aspose Purchase](https://purchase.aspose.com/buy).

قم بتهيئة الترخيص في الشفرة:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

الآن أنت جاهز للغوص في المميزتين الرئيسيتين لهذا الدليل.

## كيفية تصدير ics: تعيين حالة المشاركين في مواعيد الاجتماع

### ما هي حالة المشاركين في موعد التقويم؟

تشير حالة المشاركين إلى كيفية استجابة الحضور لدعوة الاجتماع—Accepted أو Declined أو Tentative. باستخدام Aspose.Email for Java، يمكنك تعيين هذه القيم برمجيًا، وهو أمر أساسي لأنظمة جدولة تلقائية وإدارة **java calendar appointment**.

### تنفيذ خطوة‑بخطوة

#### 1️⃣ إنشاء وتكوين تواريخ الموعد

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

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ تعيين حالة المشاركة لكل حاضر

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

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**نصيحة احترافية:** تأكد دائمًا من تنسيق عناوين البريد الإلكتروني بشكل صحيح؛ وإلا قد تُصدر المكتبة أخطاءً في التحليل.

## كيفية تصدير ics: كتابة عدة أحداث إلى ملف ICS

### لماذا تصدر التقويم إلى ics باستخدام Java؟

صيغة ICS مفهومة عالميًا، مما يتيح لك مشاركة معلومات الاجتماعات عبر Outlook، Google Calendar، Apple Calendar، والعديد من العملاء الآخرين. عبر **write ics file java** باستخدام Aspose.Email، تحافظ على حالة المشاركين، الخصائص المخصصة، وقواعد التكرار دون خطوات تحويل إضافية.

### تنفيذ خطوة‑بخطوة

#### 1️⃣ تكوين خيارات الحفظ وإنشاء كاتب

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ تحديد الإطار الزمني لكل حدث

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ إعداد مجموعة الحضور

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ توليد وكتابة عدة مواعيد

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

**خطأ شائع:** نسيان استدعاء `writer.dispose()` قد يترك مقبض الملف مفتوحًا، مما يسبب أخطاء وصول في التشغيلات اللاحقة.

## تطبيقات عملية

يتألق Aspose.Email for Java في العديد من السيناريوهات الواقعية:

1. **جدولة الاجتماعات تلقائيًا** – توليد دعوات تقويم في الوقت الفعلي لأدوات داخلية أو أنظمة CRM.  
2. **دمج تقويم متعدد المنصات** – تصدير المواعيد من الأنظمة القديمة إلى Outlook، Google Calendar، أو Apple Calendar باستخدام صيغة ICS القياسية.  
3. **منصات إدارة الفعاليات** – إنشاء جداول مؤتمرات، ورش عمل، أو ندوات عبر واجهة برمجة تطبيقات واحدة.

## اعتبارات الأداء

عند العمل مع **aspose email java**، ضع في اعتبارك النصائح التالية:

- حرّص على التخلص من كائنات `CalendarWriter` (أو أي كائنات `MailMessage`/`Appointment`) بمجرد الانتهاء منها.  
- عالج المواعيد على دفعات عند التعامل مع مجموعات بيانات كبيرة لتقليل عبء جمع القمامة.  
- أعد استخدام كائن `IcsSaveOptions` واحد بدلاً من إنشاء جديد لكل عملية كتابة.

## الأسئلة المتكررة

**س: هل يمكنني تحديث ملف ICS موجود بدلًا من إنشاء ملف جديد؟**  
ج: نعم. اضبط `saveOptions.setAction(AppointmentAction.Modify)` وقدم الـ UID للموعد الذي تريد تحديثه.

**س: هل يدعم Aspose.Email الأحداث المتكررة؟**  
ج: بالتأكيد. اضبط نمط التكرار على كائن `Appointment` قبل الكتابة إلى ملف ICS.

**س: هل يمكن إضافة خصائص مخصصة إلى حدث ICS؟**  
ج: نعم. استخدم `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` لإدراج حقول غير قياسية.

**س: ما صيغ المناطق الزمنية المقبولة؟**  
ج: كل من معرفات IANA للمناطق الزمنية (مثل “America/New_York”) وإزاحات GMT مدعومة.

**س: هل أحتاج إلى ترخيص لبُنى التطوير؟**  
ج: الترخيص المؤقت يزيل قيود التقييم؛ الترخيص الكامل مطلوب للنشر في بيئات الإنتاج.

## الخلاصة

لقد تعلمت الآن **كيفية تصدير ملفات ics**، تعيين حالة المشاركين، وكتابة عدة أحداث باستخدام Aspose.Email for Java. هذه الإمكانيات تتيح لك بناء ميزات جدولة قوية، التكامل مع أي عميل تقويم، وتبسيط توزيع الأحداث عبر مؤسستك.

---

**آخر تحديث:** 2026-03-18  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}