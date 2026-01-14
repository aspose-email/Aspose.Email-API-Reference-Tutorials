---
date: '2026-01-01'
description: تعلم كيفية إنشاء تقويم MAPI بلغة Java وحفظه إلى ملف PST باستخدام Aspose.Email
  للـ Java. دليل خطوة بخطوة مع الكود، التكرار، والمستلمين.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: كيفية إنشاء تقويم MAPI في Java باستخدام Aspose.Email – حفظ التقويم إلى ملف
  PST
url: /ar/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء تقويم MAPI Java باستخدام Aspose.Email – حفظ التقويم إلى PST

## المقدمة

هل تبحث عن تبسيط أتمتة التقويم في تطبيقات Java الخاصة بك؟ باستخدام **Aspose.Email for Java**، يمكنك **إنشاء تقويم MAPI Java**، تعريف أنماط التكرار، إضافة الحضور، و**حفظ التقويم إلى PST** ببضع أسطر من الشيفرة فقط. يوجهك هذا البرنامج التعليمي خلال العملية بالكامل — من إعداد المكتبة إلى إنشاء إدخال تقويم كامل الوظائف جاهز للتوزيع.

### ما ستتعلمه
- كيفية **إنشاء تقويم MAPI Java** باستخدام Aspose.Email.  
- تكوين أنماط التكرار اليومية أو الأسبوعية أو المخصصة.  
- إضافة المستلمين (المنظمين، الحضور) إلى دعوات التقويم الخاصة بك.  
- حفظ عنصر التقويم عن طريق **حفظ التقويم إلى PST** لضمان توافقه مع Outlook.

هيا نبدأ ونجهز بيئة التطوير الخاصة بك.

## إجابات سريعة
- **أي مكتبة؟** Aspose.Email for Java  
- **الهدف الأساسي؟** إنشاء تقويم MAPI Java و**حفظ التقويم إلى PST**  
- **المتطلبات المسبقة؟** Java 8+، Maven، ترخيص Aspose.Email  
- **الوقت المتوقع للتنفيذ؟** 10‑15 دقيقة لإنشاء حدث أساسي  
- **هل يمكن إضافة تكرار؟** نعم – يومي، أسبوعي، شهري، إلخ.

## ما هو تقويم MAPI في Java؟
كائن تقويم MAPI (واجهة برمجة تطبيقات الرسائل) يمثل اجتماعًا أو موعدًا متوافقًا مع Outlook. باستخدام Aspose.Email، يمكنك إنشاء هذه الكائنات برمجيًا، مما يتيح دمجًا سلسًا مع Exchange أو Outlook أو أي عميل يستهلك ملفات PST.

## لماذا نستخدم Aspose.Email لأتمتة التقويم؟
- **توافق كامل مع Outlook** – العناصر المُنشأة تعمل في Outlook، OWA، والعملاء المتنقلين.  
- **دعم غني للتكرار** – أنماط يومية، أسبوعية، شهرية، ومخصصة جاهزة للاستخدام.  
- **بدون تبعيات خارجية** – مكتبة Java صافية، لا تحتاج إلى COM interop.  
- **أداء عالي** – معالجة فعّالة لملفات PST الكبيرة والعمليات الضخمة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

### المكتبات المطلوبة
- **Aspose.Email for Java**: الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse.  
- Maven مثبت لإدارة التبعيات.

### المتطلبات المعرفية
- مهارات أساسية في برمجة Java.  
- إلمام بمفاهيم البرمجة الكائنية.

## إعداد Aspose.Email for Java

أضف تبعية Aspose.Email إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الحصول على الترخيص

توفر Aspose.Email نسخة تجريبية مجانية، لكن الترخيص يفتح جميع الميزات:

- **نسخة تجريبية**: اختبر بدون قيود لمدة 30 يومًا.  
- **ترخيص مؤقت**: اطلبه عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/) إذا احتجت وقتًا إضافيًا.  
- **شراء**: احصل على ترخيص دائم من [صفحة الشراء](https://purchase.aspose.com/buy).

### التهيئة الأساسية

بعد إضافة التبعية، قم بتهيئة المكتبة باستخدام ملف الترخيص الخاص بك:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## دليل التنفيذ

الآن بعد أن تم إعداد كل شيء، دعنا **ننشئ تقويم MAPI Java** و**نحفظ التقويم إلى PST**.

### إنشاء تقويم MAPI مع تكرار

#### نظرة عامة

سنقوم بإنشاء حدث تقويم، تطبيق تكرار يومي، إضافة الحضور، وأخيرًا تخزينه في ملف PST.

#### تنفيذ خطوة بخطوة

1. **تهيئة التاريخ ونمط التكرار**  

   أولاً، حدد وقت البدء وضع تكرارًا يوميًا:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *شرح*: `MapiCalendarEventRecurrence` يحمل تفاصيل التكرار؛ نختار نمطًا يوميًا عبر `MapiCalendarDailyRecurrencePattern`.

2. **إعداد المستلمين**  

   أضف الأشخاص الذين يجب أن يتلقوا دعوة الاجتماع:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *شرح*: `MapiRecipientCollection` يخزن كل حضور؛ `MAPI_TO` يحددهم كمستلمين أساسيين.

3. **إنشاء عنصر تقويم MAPI**  

   بنِ كائن التقويم مع جميع التفاصيل المطلوبة:

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

   *شرح*: المُنشئ يتوقع المنظم، العنوان، الموقع، وقت البدء/الانتهاء، الوصف، قائمة المستلمين، والتكرار.

4. **حفظ إلى ملف PST**  

   أخيرًا، احفظ التقويم عن طريق **حفظ التقويم إلى PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *شرح*: `PersonalStorage.create` ينشئ ملف PST جديد، و`addMapiMessageItem` يضيف عنصر التقويم إلى مجلد "Calendar".

### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من مسار الترخيص؛ الترخيص غير صالح سيقيد الوظائف.  
- تأكد من تنسيق عناوين البريد الإلكتروني للمستلمين لتجنب فشل الدعوات.  
- أغلق ملف PST (`pst.dispose()`) بعد الانتهاء لتحرير مقابض الملفات.

## تطبيقات عملية

إليك بعض السيناريوهات الشائعة حيث يبرز **إنشاء تقويم MAPI Java** و**حفظ التقويم إلى PST**:

1. **جدولة الاجتماعات تلقائيًا** – توليد دعوات اجتماعات متكررة لفرق المشروع دون جهد يدوي.  
2. **منصات إدارة الفعاليات** – تصدير جلسات المؤتمرات كعناصر تقويم متوافقة مع Outlook.  
3. **تكامل CRM** – مزامنة مواعيد العملاء من نظام CRM مباشرةً إلى Outlook عبر ملفات PST.

## اعتبارات الأداء

- **إدارة الموارد**: حرّر كائنات `PersonalStorage` بعد الاستخدام لتجنب حجز الملفات.  
- **المعالجة الدفعية**: للكمية الكبيرة، عالج عناصر التقويم بشكل غير متزامن أو على دفعات لتقليل استهلاك الذاكرة.  

## الخلاصة

لقد تعلمت الآن كيفية **إنشاء كائنات تقويم MAPI Java**، تكوين التكرار، إضافة الحضور، و**حفظ التقويم إلى PST** باستخدام Aspose.Email. يتيح لك هذا النهج أتمتة سير عمل جدولة متقدم في تطبيقات Java مع توافق كامل مع Outlook.

للمزيد من الاستكشاف، راجع [الوثائق الرسمية](https://reference.aspose.com/email/java/).

## قسم الأسئلة المتكررة

### س: هل يمكنني إنشاء نمط تكرار أسبوعي؟
- **ج**: نعم! استخدم `MapiCalendarWeeklyRecurrencePattern` لتحديد التكرار الأسبوعي.

### س: كيف أتعامل مع الاستثناءات في تكرار الحدث؟
- **ج**: استدعِ `setExceptions()` على كائن التكرار لتحديد التواريخ التي تختلف عن النمط.

### س: هل يمكن تحديث عنصر تقويم موجود؟
- **ج**: بالتأكيد. حمّل العنصر من PST، عدّل خصائصه، ثم احفظه مرة أخرى.

### س: هل يمكن تشفير ملف PST؟
- **ج**: نعم، يتيح لك Aspose.Email تعيين كلمة مرور على `PersonalStorage` عند إنشاء الـ PST.

### س: ماذا إذا أردت إضافة مرفقات إلى حدث التقويم؟
- **ج**: استخدم `calendar.getAttachments().addFileAttachment("path/to/file")` قبل الحفظ.

## موارد

- [توثيق Aspose.Email](https://reference.aspose.com/email/java/)  
- [تحميل Aspose.Email for Java](https://releases.aspose.com/email/java/)  
- [شراء ترخيص](https://purchase.aspose.com/buy)  
- [نسخة تجريبية مجانية](https://releases.aspose.com/email/java/)  
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)  
- [منتدى دعم Aspose](https://forum.aspose.com/c/email/10)

---

**آخر تحديث:** 2026-01-01  
**تم الاختبار مع:** Aspose.Email for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
