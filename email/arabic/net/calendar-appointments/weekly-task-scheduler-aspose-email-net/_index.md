---
"date": "2025-05-30"
"description": "تعرّف على كيفية إنشاء مُجدول مهام أسبوعي فعّال باستخدام Aspose.Email لـ .NET. يتناول هذا الدليل إعداد المهام المتكررة، وتكوين تكرارات متعددة الأيام، وحساب تكراراتها بكفاءة."
"title": "مُجدول المهام الأسبوعي مع Aspose.Email .NET - إتقان التقويم والمواعيد"
"url": "/ar/net/calendar-appointments/weekly-task-scheduler-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# مُجدول المهام الأسبوعي مع Aspose.Email .NET: إتقان التقويم والمواعيد

## مقدمة
إدارة المهام المتكررة بكفاءة أمرٌ أساسيٌّ لزيادة الإنتاجية، خاصةً عند تنفيذها في أيامٍ مُحددةٍ وعلى فتراتٍ منتظمة. يُوضّح هذا البرنامج التعليمي كيفية إعداد مهمةٍ متكررةٍ أسبوعيًا باستخدام Aspose.Email لـ .NET.

في هذا الدليل، سوف تتعلم:
- كيفية إعداد أنماط التكرار الأسبوعية.
- تنفيذ التكرارات متعددة الأيام مع إعدادات الفاصل الزمني.
- حساب الأحداث بناءً على القواعد المخصصة.

دعونا نستكشف المتطلبات الأساسية اللازمة للبدء!

## المتطلبات الأساسية
قبل تطبيق مُجدول المهام، تأكد من تهيئة بيئتك بشكل صحيح. ستحتاج إلى:
- Aspose.Email لمكتبة .NET (الإصدار 20.x أو أحدث).
- بيئة تطوير متوافقة مع إطار عمل .NET.
- المعرفة الأساسية ببرمجة C# والتعرف على مفاهيم جدولة البريد الإلكتروني.

## إعداد Aspose.Email لـ .NET
لدمج Aspose.Email في مشروعك، اختر من بين عدة طرق تثبيت:

**.NET CLI**
```shell
dotnet add package Aspose.Email
```

**مدير الحزم**
```powershell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير الحزم NuGet**
افتح NuGet في IDE الخاص بك، وابحث عن "Aspose.Email"، ثم قم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
لاستخدام Aspose.Email، ابدأ بفترة تجريبية مجانية أو احصل على ترخيص مؤقت. للمشاريع التجارية، فكّر في شراء ترخيص. تفضل بزيارة [شراء Aspose](https://purchase.aspose.com/buy) لمزيد من المعلومات حول الحصول على التراخيص.

## دليل التنفيذ
يتناول هذا القسم الخطوات اللازمة لإنشاء جدول المهام الأسبوعي الخاص بك باستخدام Aspose.Email لـ .NET.

### إعداد التكرار الأسبوعي مع أيام متعددة
#### ملخص
تعرّف على كيفية إعداد مهمة تتكرر في أيام محددة من الأسبوع على فترات زمنية محددة. يُعد هذا مثاليًا لإنشاء تقويمات أو تذكيرات لمهام مثل الاجتماعات نصف الشهرية التي تُعقد يومي الاثنين والجمعة.

#### الخطوة 1: تهيئة تفاصيل المهمة
ابدأ بتحديد تاريخ البدء وتاريخ الاستحقاق وتاريخ الانتهاء مع تطبيق إزاحة المنطقة الزمنية:
```csharp
DateTime StartDate = new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now));
DateTime DueDate = new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now));
DateTime endByDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now));

MapiTask task = new MapiTask("This is a test task", "Sample Body", StartDate, DueDate);
task.State = MapiTaskState.NotAssigned;
```
#### الخطوة 2: تكوين نمط التكرار
بعد ذلك، حدّد نمط التكرار. هنا، حدد تكرار المهمة مرتين أسبوعيًا يومي الاثنين والجمعة:
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterNOccurrences,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // فترة كل أسبوعين
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday,
};

// حساب عدد مرات الحدوث بين تاريخي البداية والنهاية
rec.OccurrenceCount = GetOccurrenceCount(StartDate, endByDate, "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2");
if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1;
}
task.Recurrence = rec;
```
#### الخطوة 3: حفظ المهمة
أخيرًا، احفظ المهمة في ملف. تضمن هذه الخطوة حفظ إعدادات التكرار وإمكانية الوصول إليها لاحقًا.
```csharp
task.Save("YOUR_OUTPUT_DIRECTORY\SetWeeklyRecurrenceMultipleDaysInWeekWithInterval_out.msg", TaskSaveFormat.Msg);
```
### حساب التكرارات من قاعدة التكرار
تحسب هذه الميزة عدد مرات حدوث قاعدة معينة بين تاريخين، مما يضمن دقة جدول المهام لديك وموثوقيته.
#### نظرة عامة على الطريقة
الطريقة `GetOccurrenceCount` يستخدم تاريخ البدء وتاريخ الانتهاء وقاعدة التكرار (RRULE) لحساب عدد المرات التي سيحدث فيها الحدث خلال الفترة المحددة:
```csharp
private static uint GetOccurrenceCount(DateTime start, DateTime endBy, string rrule)
{
    var pattern = new CalendarRecurrence(string.Format("DTSTART:{0}\r\nRRULE:{1}", start.ToString("yyyyMMdd"), rrule));
    DateCollection dateOccurrences = pattern.GenerateOccurrences(start, endBy);
    return (uint)dateOccurrences.Count;
}
```
### نصائح استكشاف الأخطاء وإصلاحها
- **مشاكل المنطقة الزمنية:** تأكد من إعدادات المنطقة الزمنية المتسقة عبر جميع كائنات DateTime.
- **أخطاء قاعدة التكرار:** تأكد من صحة بناء جملة RRULE بحثًا عن الأخطاء المطبعية أو المعلمات غير الصحيحة.

## التطبيقات العملية
يعد برنامج جدولة المهام الأسبوعي هذا متعدد الاستخدامات ويمكن استخدامه في سيناريوهات مختلفة:
1. **إدارة المشاريع:** جدولة اجتماعات المشروع المتكررة في أيام الأسبوع المحددة مع فاصل زمني محدد.
2. **تعليم:** خطط لفصول دراسية تقام كل أسبوعين في أيام محددة، مثل أيام الاثنين والجمعة.
3. **الرعاية الصحية:** تعيين تذكيرات للمرضى لتناول الدواء كل يوم اثنين وخميس.

## اعتبارات الأداء
عند تنفيذ هذا الحل:
- قم بتحسين الكود الخاص بك عن طريق تقليل العمليات الحسابية غير الضرورية داخل الحلقات.
- تأكد من استخدام الذاكرة بكفاءة عن طريق التخلص من الكائنات التي لم تعد هناك حاجة إليها.
- قم بتحديث Aspose.Email بانتظام للاستفادة من تحسينات الأداء وإصلاحات الأخطاء.

## خاتمة
باتباع الخطوات الموضحة في هذا البرنامج التعليمي، ستتعلم كيفية إعداد مُجدول مهام أسبوعي متعدد الاستخدامات باستخدام Aspose.Email لـ .NET. يُعد هذا الحل مثاليًا لإدارة المهام المتكررة في أيام محددة بفترات زمنية محددة. استكشف المزيد من خلال دمجه في أنظمتك الحالية أو تخصيصه لتلبية احتياجات الجدولة الأكثر تعقيدًا.

## قسم الأسئلة الشائعة
**س: كيف يمكنني التعامل مع المناطق الزمنية المختلفة في إعدادات التكرار الخاصة بي؟**
أ: قم دائمًا بتطبيق إزاحة المنطقة الزمنية الحالية عند تحديد كائنات DateTime لضمان الاتساق في جميع العمليات الحسابية.

**س: هل يمكنني تعديل نمط التكرار بعد حفظ المهمة؟**
ج: نعم، يمكنك إعادة تحميل كائن MapiTask وضبط إعدادات التكرار الخاصة به قبل إعادة حفظه.

**س: هل هناك حد لعدد الأحداث التي يمكنني تعيينها؟**
ج: على الرغم من أن Aspose.Email لا يفرض حدًا صارمًا، فتأكد من أن موارد نظامك قادرة على التعامل مع أعداد كبيرة من الأحداث بكفاءة.

**س: كيف يمكنني اختبار تنفيذ جدول المهام الخاص بي؟**
أ: قم بإنشاء اختبارات وحدات ذات تواريخ بداية ونهاية مختلفة، بالإضافة إلى قواعد تكرار مختلفة، للتحقق من دقة حسابات الحدوث.

**س: ما هي بعض الأخطاء الشائعة عند إعداد التكرارات؟**
أ: قد يؤدي تكوين المناطق الزمنية بشكل غير صحيح أو استخدام صيغة RRULE غير الصحيحة إلى نتائج جدولة غير متوقعة.

## موارد
- **التوثيق:** استكشف الأدلة التفصيلية في [وثائق Aspose](https://reference.aspose.com/email/net/).
- **تحميل:** احصل على أحدث إصدار من Aspose.Email من [الإصدارات](https://releases.aspose.com/email/net/).
- **الشراء والتجربة:** تعرف على المزيد حول خيارات الترخيص على [شراء Aspose](https://purchase.aspose.com/buy) وابدأ بتجربة مجانية في [نسخة تجريبية مجانية](https://releases.aspose.com/email/net/).
- **يدعم:** انضم إلى المناقشات أو اطلب المساعدة في [منتدى أسبوزي](https://forum.aspose.com/c/email/10).

باستخدام Aspose.Email لـ .NET، يمكنك إنشاء تطبيقات جدولة فعّالة تُحسّن الإنتاجية وتُسهّل إدارة المهام. برمجة ممتعة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}