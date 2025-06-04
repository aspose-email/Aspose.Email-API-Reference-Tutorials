---
"date": "2025-05-30"
"description": "تعرّف على كيفية إعداد وإدارة المهام الأسبوعية المتكررة باستخدام Aspose.Email لـ .NET. يغطي هذا الدليل إنشاء حلول الجدولة وتكوينها وتحسينها."
"title": "كيفية إنشاء مهام MapiTask أسبوعية متكررة في .NET باستخدام Aspose.Email"
"url": "/ar/net/calendar-appointments/create-manage-weekly-maptasks-net-aspose-email/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مهام MapiTask أسبوعية متكررة في .NET باستخدام Aspose.Email

## مقدمة

تُعد إدارة المهام المتكررة بكفاءة أمرًا بالغ الأهمية للمطورين الذين يعملون على تطبيقات تتضمن وظائف الجدولة أو التقويم. سواء كنت تُطوّر أداة داخلية لإدارة المهام أو تُدمج ميزات التقويم في تطبيق أعمال، فإن إنشاء وإدارة المهام المتكررة أسبوعيًا يُمكن أن يُعزز الإنتاجية بشكل كبير.

في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام **Aspose.Email لـ .NET** إنشاء مهام MapiTask أسبوعية متكررة تنتهي بعد تاريخ محدد. هذه الميزة قيّمة للمطورين الذين يتطلعون إلى أتمتة الجدولة داخل تطبيقاتهم باستخدام وظائف Aspose.Email القوية.

### ما سوف تتعلمه:
- إعداد وتكوين Aspose.Email لـ .NET
- إنشاء مهمة MapiTask أسبوعية متكررة بتاريخ انتهاء محدد
- تنفيذ أنماط التكرار لعدة أيام
- حساب عدد مرات الظهور استنادًا إلى قواعد التكرار المخصصة

هل أنت مستعد للبدء في ابتكار حلول فعّالة للجدولة؟ هيا بنا!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **Aspose.Email لـ .NET** المكتبة: يمكنك تثبيتها باستخدام NuGet أو مديري الحزم الآخرين.
- **.NET Framework 4.6.1 أو أحدث** أو **.NET Core/5+**:تأكد من إعداد بيئة التطوير الخاصة بك باستخدام إصدار .NET متوافق.
- المعرفة الأساسية بلغة C# والتعرف على مفاهيم البرمجة الموجهة للكائنات.

## إعداد Aspose.Email لـ .NET

لبدء استخدام Aspose.Email لـ .NET، عليك إضافته إلى مشروعك. إليك الطريقة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Email
```

**استخدام وحدة تحكم إدارة الحزم:**
```powershell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير حزمة NuGet:**
- ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص

يمكنك الحصول على الترخيص من خلال:

- **نسخة تجريبية مجانية**:اختبار الميزات دون قيود.
- **رخصة مؤقتة**:استخدم هذا لتقييم القدرات الموسعة.
- **شراء**:للحصول على الوصول الكامل، قم بشراء ترخيص تجاري.

بمجرد حصولك على ملف الترخيص، قم بتهيئة Aspose.Email عن طريق تطبيق الترخيص في الكود الخاص بك:
```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("path_to_license_file.lic");
```

## دليل التنفيذ

سنقوم بتقسيم التنفيذ إلى ميزتين رئيسيتين: إنشاء تكرار أسبوعي ليوم واحد وإعداد تكرارات لعدة أيام.

### إنشاء مهمة MapiTask أسبوعية متكررة تنتهي بعد تاريخ محدد

#### ملخص
تتيح لك هذه الميزة إنشاء مهام تتكرر في يوم محدد كل أسبوع حتى تنتهي بعد تاريخ محدد. إنها مثالية لجدولة الاجتماعات المتكررة أو المواعيد النهائية.

#### خطوات التنفيذ
**الخطوة 1: تكوين نمط التكرار**
هنا، سنقوم بإعداد نمط التكرار باستخدام `MapiCalendarWeeklyRecurrencePattern`.
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1, // التكرار الأسبوعي
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday, // تتكرر يوم الجمعة
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR;INTERVAL=1")
};
```
**الخطوة 2: إنشاء MapiTask**
الآن بعد أن قمنا بتكوين نمط التكرار الخاص بنا، فلنقم بإنشاء مهمة وتعيين هذا النمط لها.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;

if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1; // تأكد من حدوث حدث واحد على الأقل
}

task.Recurrence = rec;
```
**الخطوة 3: حفظ المهمة**
وأخيرًا، احفظ مهمتك في ملف .msg للاحتفاظ بها.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateEveryDayRecurrence_out.msg", TaskSaveFormat.Msg);
```

### إنشاء مهمة MapiTask أسبوعية متكررة في أيام متعددة تنتهي بعد تاريخ محدد

#### ملخص
تعمل هذه الميزة على توسيع الإعداد السابق للسماح بالمهام التي تتكرر في أيام متعددة كل أسبوع، مما يوفر المرونة لاحتياجات الجدولة الأكثر تعقيدًا.

#### خطوات التنفيذ
**الخطوة 1: تكوين نمط التكرار متعدد الأيام**
قم بإعداد نمط يتضمن أيام تكرار متعددة في الأسبوع.
```csharp
var record = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // يحدث كل اسبوعين
    WeekStartDay = DayOfWeek.Sunday,
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday, // تتكرر أيام الجمعة والاثنين
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2")
};
```
**الخطوة 2: إنشاء MapiTask وتعيينه**
على غرار ما سبق، قم بإنشاء مهمة وتعيين هذا النمط متعدد الأيام.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;
task.Recurrence = record;
```
**الخطوة 3: حفظ المهمة التي تستغرق عدة أيام**
احفظ مهمتك بنفس الطريقة للتأكد من تخزينها بشكل صحيح.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateMultipleDaysRecurrence_out.msg", TaskSaveFormat.Msg);
```

## التطبيقات العملية

وفيما يلي بعض التطبيقات العملية لهذه الميزات:

1. **أتمتة الاجتماعات الأسبوعية**:جدولة اجتماعات الفريق المتكررة في أيام محددة، مثل أيام الجمعة.
2. **مواعيد نهائية للمهام**:قم بإعداد مواعيد نهائية أسبوعية لمهام المشروع التي تتكرر كل يوم اثنين وجمعة.
3. **تخطيط الفعاليات**:إدارة جداول التخطيط للأحداث التي تتطلب المتابعة في أيام متعددة كل أسبوع.

## اعتبارات الأداء

- **تحسين استخدام الذاكرة**:تأكد من التخلص من الكائنات بشكل صحيح لتجنب تسرب الذاكرة، وخاصة عند التعامل مع مجموعات بيانات كبيرة أو مهام متكررة عديدة.
- **حسابات التاريخ الفعالة**:استخدم خوارزميات فعالة لحسابات التاريخ ضمن قواعد التكرار لتقليل وقت المعالجة.
- **العمليات غير المتزامنة**:عند حفظ المهام على القرص أو مواقع الشبكة، ضع في اعتبارك الطرق غير المتزامنة لتحسين الأداء.

## خاتمة

في هذا البرنامج التعليمي، تناولنا كيفية إنشاء وإدارة مهام MapiTasks أسبوعية متكررة باستخدام Aspose.Email لـ .NET. باتباع الخطوات الموضحة أعلاه، يمكنك بسهولة تنفيذ ميزات جدولة متطورة في تطبيقاتك.

لمزيد من استكشاف قدرات Aspose.Email أو معالجة السيناريوهات الأكثر تعقيدًا، فكر في مراجعة وثائقهم الرسمية ومنتديات المجتمع.

## الأسئلة الشائعة

**س: كيف أقوم بتثبيت Aspose.Email لـ .NET؟**
ج: يمكنك تثبيته عبر NuGet Package Manager باستخدام الأمر `Install-Package Aspose.Email`.

**س: ما هو MapiTask؟**
ج: يمثل MapiTask مهمة Outlook مع خصائص مثل الموضوع وتاريخ الاستحقاق ونمط التكرار.

**س: هل يمكنني تخصيص أنماط التكرار بشكل أكبر؟**
ج: نعم، يمكنك استخدام أنواع تكرار مختلفة مثل اليومي أو الشهري عن طريق تعديل `PatternType` ممتلكات `MapiCalendarRecurrencePattern`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}