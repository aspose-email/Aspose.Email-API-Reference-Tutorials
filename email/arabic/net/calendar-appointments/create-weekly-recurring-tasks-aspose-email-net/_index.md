---
"date": "2025-05-30"
"description": "تعرّف على كيفية أتمتة المهام الأسبوعية المتكررة باستخدام Aspose.Email لـ .NET. اتبع دليلنا الشامل لإعداد MapiTasks وتكوينها وتنفيذها مع أنماط التكرار."
"title": "إنشاء مهام متكررة أسبوعيًا باستخدام Aspose.Email .NET للتقويم والمواعيد"
"url": "/ar/net/calendar-appointments/create-weekly-recurring-tasks-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مهام متكررة أسبوعيًا باستخدام Aspose.Email .NET للتقويم والمواعيد

## مقدمة

قد تكون إدارة المهام المتكررة أمرًا صعبًا، خاصةً عندما تتطلب تكرارها أسبوعيًا ودمجها بسلاسة في سير عملك. يرشدك هذا البرنامج التعليمي إلى كيفية إنشاء مهام متكررة أسبوعيًا باستخدام مكتبة Aspose.Email القوية لـ .NET، وهي مثالية لأتمتة التذكيرات أو جدولة التحديثات الدورية.

**ما سوف تتعلمه:**
- كيفية إنشاء MapiTask مع التكرار الأسبوعي.
- إعداد وتكوين Aspose.Email لـ .NET.
- حساب تكرارات المهام بين التواريخ باستخدام قواعد التكرار.
- التطبيقات الواقعية لدمج المهام المتكررة في العمليات التجارية.

دعونا نبسط عملية إدارة المهام الخاصة بك!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:
- **Aspose.Email لـ .NET** تم التثبيت. تعليمات التثبيت موجودة أدناه.
- بيئة تطوير متكاملة متوافقة (على سبيل المثال، Visual Studio) لتطوير C#.
- فهم أساسي لبرمجة C# والتعرف على التعامل مع البيانات.

### إعداد Aspose.Email لـ .NET

للبدء، قم بتثبيت مكتبة Aspose.Email في مشروعك:

**.NET CLI**
```bash
dotnet add package Aspose.Email
```

**مدير الحزم**
```powershell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير حزمة NuGet:**
ابحث عن "Aspose.Email" وحدد الإصدار الأحدث للتثبيت.

#### الحصول على الترخيص
- **نسخة تجريبية مجانية:** تنزيل نسخة تجريبية مجانية من [تنزيلات Aspose](https://releases.aspose.com/email/net/).
- **رخصة مؤقتة:** اطلب ترخيصًا مؤقتًا في [ترخيص Aspose المؤقت](https://purchase.aspose.com/temporary-license/) لإجراء اختبار موسع.
- **شراء:** للاستخدام طويل الأمد، فكر في شراء ترخيص من خلال [شراء Aspose](https://purchase.aspose.com/buy).

بمجرد تثبيت الحزمة وإعداد الترخيص الخاص بك، قم بتهيئة Aspose.Email على النحو التالي:
```csharp
// مثال على التهيئة الأساسية (ليس إلزاميًا في جميع السياقات)
var license = new Aspose.Email.License();
license.SetLicense("path_to_your_license_file.lic");
```

## دليل التنفيذ

يغطي هذا القسم ميزتين رئيسيتين: إنشاء مهمة متكررة أسبوعيًا وحساب عدد مرات حدوثها.

### الميزة 1: إنشاء المهام الأسبوعية مع التكرار

**ملخص:**
تعرف على كيفية إنشاء MapiTask يتكرر أسبوعيًا باستخدام Aspose.Email `MapiCalendarWeeklyRecurrencePattern`، أتمتة إنشاء المهام دون تدخل يدوي لكل حدوث.

#### الخطوة 1: تحديد التواريخ وتعديلها حسب المنطقة الزمنية
```csharp
// تحديد تواريخ البدء والاستحقاق والنهاية للمهمة
DateTime StartDate = new DateTime(2015, 7, 16);
DateTime DueDate = new DateTime(2015, 7, 16);
DateTime EndByDate = new DateTime(2015, 9, 1);

// ضبط التواريخ بناءً على إزاحة المنطقة الزمنية المحلية
timeZone localZone = TimeZone.CurrentTimeZone;
TimeSpan ts = localZone.GetUtcOffset(DateTime.Now);
StartDate = StartDate.Add(ts);
DueDate = DueDate.Add(ts);
EndByDate = EndByDate.Add(ts);
```
**توضيح:**
يتم ضبط تواريخ بدء المهمة واستحقاقها ونهايتها وفقًا لإزاحة المنطقة الزمنية الحالية لضمان الدقة عبر المناطق المختلفة.

#### الخطوة 2: إنشاء وتكوين MapiTask
```csharp
// إنشاء MapiTask جديد بالتفاصيل المحددة
MapiTask task = new MapiTask("This is a test task", "Sample Body", StartDate, DueDate);
task.State = MapiTaskState.NotAssigned;
```
**توضيح:**
تهيئة `MapiTask` كائن بعنوان ونص وتاريخ بدء واستحقاق. اضبط حالة المهمة على `NotAssigned`، ووضع علامة عليه كمعلق.

#### الخطوة 3: تعيين نمط التكرار الأسبوعي
```csharp
// تكوين نمط التكرار الأسبوعي للمهمة
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterNOccurrences,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1,
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday,
    OccurrenceCount = GetOccurrenceCount(StartDate, EndByDate, "FREQ=WEEKLY;BYDAY=FR"),
};

// تأكد من وجود حالة واحدة على الأقل
if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1;
}
task.Recurrence = rec;
```
**توضيح:**
يقوم هذا المقطع بتكوين المهمة لتتكرر أسبوعيًا يوم الجمعة. `GetOccurrenceCount` تحسب الوظيفة عدد المرات التي تقع بين تاريخ البداية وتاريخ النهاية.

#### الخطوة 4: حفظ المهمة
```csharp
// حفظ المهمة في ملف في دليل الإخراج المحدد
string outputPath = "@YOUR_OUTPUT_DIRECTORY/Weekly_out.msg";
task.Save(outputPath, TaskSaveFormat.Msg);
```
**توضيح:**
تم حفظ المهمة المكتملة كملف MSG. تأكد من استبدال `@YOUR_OUTPUT_DIRECTORY` مع مسارك الفعلي.

### الميزة 2: حساب التكرارات بين تاريخين باستخدام قاعدة التكرار

**ملخص:**
تحديد عدد المرات التي يحدث فيها حدث متكرر بين تاريخين باستخدام Aspose.Email's `CalendarRecurrence` فصل.

#### الخطوة 1: تحديد التواريخ وقاعدة التكرار
```csharp
// تعيين تواريخ البدء والانتهاء لحساب مرات الظهور
DateTime Start = new DateTime(2015, 7, 16);
DateTime EndBy = new DateTime(2015, 9, 1);
string RRule = "FREQ=WEEKLY;BYDAY=FR";
```
**توضيح:**
تعمل هذه المتغيرات على إعداد نطاق التاريخ وتحديد قاعدة للأحداث الأسبوعية يوم الجمعة.

#### الخطوة 2: حساب التكرارات
```csharp
// احصل على عدد مرات حدوث الحدث بين التاريخين استنادًا إلى قاعدة التكرار
uint occurrenceCount = GetOccurrenceCount(Start, EndBy, RRule);
```
**توضيح:**
تقوم الوظيفة بحساب عدد المرات التي تتكرر فيها المهمة خلال الفترة المحددة.

#### الخطوة 3: التنفيذ `GetOccurrenceCount` طريقة
```csharp
private static uint GetOccurrenceCount(DateTime start, DateTime endBy, string rrule)
{
    // إنشاء كائن CalendarRecurrence باستخدام تنسيق DTSTART وRRULE
    CalendarRecurrence pattern = new CalendarRecurrence(string.Format("DTSTART:{0}\r\nRRULE:{1}", start.ToString("yyyyMMdd"), rrule));

    // إنشاء الأحداث ضمن نطاق التاريخ المحدد
    DateCollection dates = pattern.GenerateOccurrences(start, endBy);

    // إرجاع عدد مرات حدوث الأحداث المولدة
    return (uint)dates.Count;
}
```
**توضيح:**
ال `CalendarRecurrence` يتم تهيئة الكائن باستخدام تاريخ البدء وقاعدة التكرار، مما يؤدي إلى إنشاء حالات تقع ضمن النطاق المحدد.

## التطبيقات العملية

استكشف السيناريوهات الواقعية حيث يمكن دمج المهام المتكررة الأسبوعية:
1. **إدارة المشاريع:** أتمتة تذكيرات تحديث الحالة المنتظمة لأعضاء الفريق وفقًا لجدول زمني محدد.
2. **تمويل:** جدولة إنشاء التقارير المالية الأسبوعية وتوزيعها على أصحاب المصلحة.
3. **دعم العملاء:** إعداد مكالمات متابعة أسبوعية أو رسائل بريد إلكتروني للعملاء الرئيسيين للحصول على تعليقات حول الخدمة.
4. **إدارة الموارد البشرية:** تنفيذ جداول مراجعة الأداء الدورية للموظفين.
5. **الرعاية الصحية:** أتمتة جدولة الفحوصات الروتينية للمرضى أو تذكيرهم بالأدوية.

## اعتبارات الأداء

عند العمل مع Aspose.Email في .NET، ضع هذه النصائح في الاعتبار:
- راقب استخدام الذاكرة لضمان إدارة الموارد بكفاءة.
- تحسين معالجة البيانات وتكوينات المهام لتحقيق السرعة.
- قم بمراجعة مقاييس الأداء بشكل منتظم وضبط الإعدادات حسب الحاجة.

**أفضل الممارسات:**
- التخلص من الأشياء بطريقة سليمة باستخدام `using` البيانات أو التخلص اليدوي من الموارد لتحريرها على الفور.
- اختبر الحل في بيئة مؤقتة قبل نشره في الإنتاج.

## خاتمة

باتباع هذا الدليل، ستتعلم كيفية أتمتة المهام الأسبوعية المتكررة بكفاءة باستخدام Aspose.Email لـ .NET. تُحسّن هذه الأداة قدرتك على إدارة المهام المتكررة وتضمن عدم إهمال أي منها.

### الخطوات التالية:
- تجربة أنماط التكرار المختلفة.
- استكشف الميزات الأخرى لـ Aspose.Email للحصول على وظائف إضافية.
- شارك هذا الحل ضمن فريقك أو مؤسستك لتوسيع نطاق تأثيره.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}