---
date: '2026-05-18'
description: دليل خطوة بخطوة حول كيفية إنشاء عنصر تقويم Java باستخدام Aspose.Email
  للـ Java، يتضمن كودًا لحفظه كملف .ics، وإضافة تذكيرات، والعمل مع MAPI.
keywords:
- how to create calendar item java
- Aspose.Email Java
- calendar item Java
- ICS format Java
- MAPI calendar Java
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  headline: How to Create Calendar Item Java Using Aspose.Email
  type: TechArticle
- description: Step‑by‑step guide on how to create calendar item java with Aspose.Email
    for Java, including code to save as .ics, add reminders, and work with MAPI.
  name: How to Create Calendar Item Java Using Aspose.Email
  steps:
  - name: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
    text: '**Add Dependency:** Ensure your `pom.xml` includes the necessary dependency
      as shown above.'
  - name: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
    text: '**Download and Include JAR:** Alternatively, download the JAR file from
      [Aspose Downloads](https://releases.aspose.com/email/java/) and add it to your
      project’s classpath.'
  - name: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
    text: '**License Setup:** If you have a license file, initialize it in your code
      to unlock full features:'
  - name: '**Initialize MapiCalendar:**'
    text: '**Initialize MapiCalendar:**'
  - name: '**Set Appointment Details:**'
    text: '**Set Appointment Details:**'
  - name: '**Define Start and End Dates:**'
    text: '**Define Start and End Dates:**'
  - name: '**Add Reminders (Optional):**'
    text: '**Add Reminders (Optional):**'
  - name: '**Save the Appointment:**'
    text: '**Save the Appointment:**'
  type: HowTo
- questions:
  - answer: Yes – set the `Recurrence` property on `MapiCalendar` and define the recurrence
      pattern (daily, weekly, etc.).
    question: Can I generate recurring appointments?
  - answer: Absolutely – use `MapiCalendar.fromFile("path.ics")` to load and manipulate
      existing calendar data.
    question: Is it possible to read existing .ics files?
  - answer: It does; the library converts UTC to the target zone based on the `TimeZoneInfo`
      object you provide.
    question: Does Aspose.Email support time‑zone conversion automatically?
  - answer: Attach a `MapiReminderAudio` object to the `Reminders` collection and
      specify the path to a .wav file.
    question: How do I add an audio reminder?
  - answer: Up to **2 GB** per file without performance degradation, thanks to streaming
      APIs.
    question: What is the maximum file size Aspose.Email can handle?
  type: FAQPage
title: كيفية إنشاء عنصر تقويم Java باستخدام Aspose.Email
url: /ar/java/calendar-appointments/create-save-calendar-items-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء عنصر تقويم Java باستخدام Aspose.Email

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Email for Java (الإصدار 25.4 أو أحدث).  
- **هل يمكنني الحفظ كملف .ics؟** نعم – استدعِ `MapiCalendar.save(..., SaveOptions.getIcs())`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** ترخيص Aspose.Email صالح يزيل قيود التقييم.  
- **ما نسخة Java المدعومة؟** JDK 8 + (بما في ذلك Java 11 و 17).  
- **هل يدعم Maven؟** بالتأكيد – أضف تبعية Maven إلى `pom.xml`.

توفر الفئة `SaveOptions` خيارات الحفظ؛ تُعيد `getIcs()` إعدادات تنسيق iCalendar.

## كيفية إنشاء عنصر تقويم في Java؟

حمِّل فئة `MapiCalendar`، اضبط الخصائص المطلوبة (الموضوع، الموقع، أوقات البدء/الانتهاء)، واستدعِ `save` بصيغة ICS – يمكن تنفيذ العملية بالكامل بأقل من عشر أسطر من الشيفرة. يتعامل Aspose.Email تلقائيًا مع تحويل المنطقة الزمنية وقواعد التكرار، مما يضمن أن ملف *.ics* الناتج يتوافق مع RFC 5545.

## لماذا استخدام Aspose.Email لإدارة التقويم؟

يدعم Aspose.Email **أكثر من 70** تنسيقًا للبريد الإلكتروني والتقويم، يعالج ملفات تصل إلى **2 GB** دون تحميل المستند بالكامل في الذاكرة، ويوفر نهج **API‑واحد** لكل من معايير MAPI وiCalendar. هذه القدرة المكمَّنة تعني أنك تستطيع توليد، تعديل، وقراءة عناصر التقويم بثقة وعلى نطاق واسع.

## المتطلبات المسبقة
- **مجموعة تطوير Java (JDK):** الإصدار 8 أو أعلى.  
- **Maven:** لإدارة التبعيات.  
- **Aspose.Email for Java:** الإصدار 25.4 أو أحدث (يوصى بأحدث إصدار).

## إعداد البيئة

لإضافة Aspose.Email إلى مشروع Maven الخاص بك، أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

## الحصول على الترخيص

يقدم Aspose.Email ترخيصًا تجريبيًا مجانيًا يزيل معظم قيود التقييم. للاستخدام في الإنتاج، اشترِ اشتراكًا أو اطلب ترخيصًا مؤقتًا للاختبار.

## إعداد Aspose.Email لـ Java

1. **إضافة التبعية:** تأكد من أن `pom.xml` يحتوي على التبعية اللازمة كما هو موضح أعلاه.  
2. **تنزيل وإضافة JAR:** بدلاً من ذلك، قم بتنزيل ملف JAR من [Aspose Downloads](https://releases.aspose.com/email/java/) وأضفه إلى مسار الفئة (classpath) الخاص بمشروعك.  
3. **إعداد الترخيص:** إذا كان لديك ملف ترخيص، قم بتهيئته في الكود لفتح جميع الميزات:

   ```java
   License license = new License();
   license.setLicense("Path_to_Aspose.Email_License_File");
   ```

فئة `License` تقوم بتحميل وتطبيق ملف ترخيص Aspose.Email، مما يتيح الاستخدام الكامل للميزات.

## دليل التنفيذ

أدناه نستعرض الخطوات الأساسية المطلوبة لإنشاء كائنات **create calendar item java**، إغنائها بالتذكيرات، وحفظها كملفات *.ics*.

### إنشاء وحفظ عناصر التقويم

#### نظرة عامة
يوضح هذا القسم كيفية بناء موعد تقويم برمجيًا، إرفاق تذكيرات عرضية وصوتية، وحفظ النتيجة بصيغة iCalendar العالمية.

#### تنفيذ خطوة بخطوة

1. **تهيئة MapiCalendar:**  
   تمثل فئة `MapiCalendar` كائن تقويم بصيغة MAPI. تُعد نقطة الدخول لضبط جميع خصائص الموعد.

   ```java
   MapiCalendar appointment = new MapiCalendar();
   ```

2. **تحديد تفاصيل الموعد:**  
   قدم موضوعًا واضحًا، موقعًا، ونصًا وصفيًا للاجتماع.

   ```java
   appointment.setLocation("LAKE ARGYLE WA 6743");
   appointment.setSubject("Appointment");
   appointment.setBody("This is a very important meeting");
   ```

3. **تحديد تواريخ البدء والانتهاء:**  
   استخدم `GregorianCalendar` لتحديد طوابع زمنية دقيقة للبدء والانتهاء، مع مراعاة المنطقة الزمنية.

   ```java
   Calendar cal = GregorianCalendar.getInstance();
   cal.set(2016, 10, 2); // Month is zero-based.
   Date startDate = cal.getTime();

   cal.setTime(startDate);
   cal.add(Calendar.DAY_OF_MONTH, 1); // End date is one day later.
   Date endDate = cal.getTime();

   appointment.setStartDate(startDate);
   appointment.setEndDate(endDate);
   ```

4. **إضافة تذكيرات (اختياري):**  
   يمكنك إرفاق تذكير بصري (نافذة منبثقة) وتذكير صوتي (ملف wav) لتعزيز إشعار المشاركين.  
   *نصيحة:* اضبط `ReminderMinutesBeforeStart` إلى `15` لتذكير قبل 15 دقيقة.  
   تمثل فئة `MapiReminderAudio` تذكيرًا صوتيًا مرفقًا بعنصر التقويم.

5. **حفظ الموعد:**  
   احفظ عنصر التقويم كملف *.ics* في مجلد الإخراج المطلوب.

   ```java
   String dataDir = "YOUR_OUTPUT_DIRECTORY/";
   appointment.save(dataDir + "CalendarItem_out.ics\
   ```

## المشكلات الشائعة والنصائح

- **اختلافات المنطقة الزمنية:** دائمًا حدد المنطقة الزمنية عند ضبط `StartDate` و`EndDate` لتجنب أخطاء التوقيت الصيفي.  
- **قوائم الحضور الكبيرة:** للاجتماعات التي تضم أكثر من 200 مشارك، استخدم تجميع `MapiRecipientCollection` للبقاء ضمن حدود الذاكرة.  
  فئة `MapiRecipientCollection` تحتفظ بقائمة من حضور الاجتماع.  
- **الترخيص مفقود:** إذا لم يتم تحميل ملف الترخيص، يتحول API إلى وضع تجريبي يحد عدد العناصر المحفوظة إلى **10** لكل تنفيذ.

## الأسئلة المتكررة

**س: هل يمكنني إنشاء مواعيد متكررة؟**  
ج: نعم – اضبط خاصية `Recurrence` على `MapiCalendar` وحدد نمط التكرار (يومي، أسبوعي، إلخ).

**س: هل يمكن قراءة ملفات .ics الموجودة؟**  
ج: بالتأكيد – استخدم `MapiCalendar.fromFile("path.ics")` لتحميل ومعالجة بيانات التقويم الموجودة.

**س: هل يدعم Aspose.Email تحويل المنطقة الزمنية تلقائيًا؟**  
ج: نعم؛ المكتبة تحول UTC إلى المنطقة المستهدفة بناءً على كائن `TimeZoneInfo` الذي تزوده.

**س: كيف أضيف تذكيرًا صوتيًا؟**  
ج: أرفق كائن `MapiReminderAudio` إلى مجموعة `Reminders` وحدد مسار ملف .wav.

**س: ما هو الحد الأقصى لحجم الملف الذي يمكن لـ Aspose.Email التعامل معه؟**  
ج: حتى **2 GB** لكل ملف دون تدهور الأداء، بفضل واجهات برمجة التطبيقات المتدفقة.

**آخر تحديث:** 2026-05-18  
**تم الاختبار مع:** Aspose.Email for Java 25.4  
**المؤلف:** Aspose

## دروس ذات صلة

- [إدارة مشاركة التقويم - دليل Aspose.Email لـ Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [كيفية استخراج عناصر تقويم Outlook إلى ملف ICS باستخدام Aspose.Email لـ Java](/email/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/)
- [كيفية قراءة أحداث تقويم متعددة من ملف ICS باستخدام Aspose.Email في Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}