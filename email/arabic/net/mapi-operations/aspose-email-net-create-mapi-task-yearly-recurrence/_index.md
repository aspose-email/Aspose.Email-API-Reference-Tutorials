---
"date": "2025-05-30"
"description": "تعرّف على كيفية أتمتة إنشاء مهام MAPI السنوية المتكررة باستخدام Aspose.Email لـ .NET. يغطي هذا الدليل الإعداد، وخصائص المهام، وأنماط التكرار، والحفظ كملفات MSG."
"title": "إنشاء مهام MAPI متكررة سنويًا باستخدام Aspose.Email لـ .NET"
"url": "/ar/net/mapi-operations/aspose-email-net-create-mapi-task-yearly-recurrence/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مهام MAPI متكررة سنويًا باستخدام Aspose.Email لـ .NET

## مقدمة
إدارة المهام بكفاءة أمرٌ بالغ الأهمية في كلٍّ من البيئات المهنية والشخصية، خاصةً عند التعامل مع الأحداث المتكررة أو المواعيد النهائية. أتمتة إنشاء ملفات المهام التي تتكامل بسلاسة مع أنظمة البريد الإلكتروني تُوفّر الوقت وتُقلّل الأخطاء. سيُرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Email لـ .NET لإنشاء مهام MAPI وحفظها مع تكرارها سنويًا، وهو متطلب شائع في برامج إدارة المشاريع والإنتاجية.

**ما سوف تتعلمه:**
- كيفية إعداد Aspose.Email لـ .NET.
- إنشاء بسيط `MapiTask` مع خصائص محددة.
- إعداد أنماط التكرار السنوية للمهام.
- حفظ هذه المهام كـ `.msg` الملفات.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **Aspose.Email لـ .NET**المكتبة الأساسية للوصول إلى وظائف مهام MAPI. ثبّتها في مشروعك.
- **بيئة التطوير**:يوصى باستخدام Visual Studio 2022 أو إصدار أحدث على Windows أو Linux مع تثبيت .NET SDK.
- **المعرفة الأساسية بلغة C#**:المعرفة ببرمجة C# وفهم معالجة التاريخ والوقت.

## إعداد Aspose.Email لـ .NET
### تثبيت
لتثبيت Aspose.Email، استخدم إحدى الطرق التالية:

**.NET CLI:**
```shell
dotnet add package Aspose.Email
```

**وحدة تحكم مدير الحزمة:**
```shell
Install-Package Aspose.Email
```

**واجهة مستخدم مدير الحزم NuGet**:ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.
### الحصول على الترخيص
- **نسخة تجريبية مجانية**:ابدأ بفترة تجريبية مجانية لاستكشاف إمكانيات المكتبة.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) لإجراء اختبارات واسعة النطاق دون قيود.
- **شراء**:للاستخدام الإنتاجي، قم بشراء ترخيص من [أسبوزي](https://purchase.aspose.com/buy).

## دليل التنفيذ
يتناول هذا القسم إنشاء مهمة MAPI بخصائص محددة وإعداد التكرار السنوي.
### إنشاء وحفظ MapiTask
#### ملخص
يتضمن إنشاء مهمة تحديد خصائصها، مثل الموضوع، والنص، وتاريخ البدء، وتاريخ الاستحقاق، والحالة. سنحفظها كملف `.msg` الملف هو المعيار لمهام Outlook.
#### خطوات التنفيذ
**1. إعداد الدلائل**
قم بتحديد المسارات إلى مستندك ومجلدات الإخراج:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
string outputDir = "YOUR_OUTPUT_DIRECTORY";
```
**2. تكوين المنطقة الزمنية**
ضبط التواريخ بناءً على المنطقة الزمنية المحلية:
```csharp
TimeZone localZone = TimeZone.CurrentTimeZone;
TimeSpan timeSpan = localZone.GetUtcOffset(DateTime.Now);
DateTime StartDate = new DateTime(2023, 1, 1).Add(timeSpan);
DateTime DueDate = new DateTime(2023, 12, 31).Add(timeSpan);
```
**3. إنشاء MapiTask**
إنشاء مثيل `MapiTask` مع الخصائص المحددة:
```csharp
MapiTask task = new MapiTask("Yearly Review Task", "Annual review of project milestones.", StartDate, DueDate);
task.State = MapiTaskState.NotStarted;
```
**4. احفظ المهمة كملف .msg**
احفظ المهمة التي تم إنشاؤها في دليل الإخراج:
```csharp
string filePath = outputDir + "/YearlyReviewTask_out.msg";
task.Save(filePath, TaskSaveFormat.Msg);
```
### تعيين التكرار السنوي لـ MapiTask
#### ملخص
أنماط التكرار ضرورية للمهام التي تتكرر مع مرور الوقت. سنُنشئ هنا نمط تكرار سنوي.
#### خطوات التنفيذ
**1. تحديد نمط التكرار**
إنشاء `MapiCalendarYearlyRecurrencePattern`:
```csharp
MapiCalendarYearlyRecurrencePattern rec = new MapiCalendarYearlyRecurrencePattern
{
    DayOfMonth = 15,
    MonthOfYear = MapiMonth.January, // ابدأ في يناير
    Type = MapiCalendarRecurrenceType.Month,
    EndType = MapiCalendarRecurrenceEndType.NeverEnding,
};
```
**2. تعيين التكرار للمهمة**
تعيين نمط التكرار للمهمة:
```csharp
MapiTask task = new MapiTask("Yearly Review Task", "Annual review of project milestones.", DateTime.Now, DateTime.Now.AddDays(1));
task.Recurrence = rec;
```
**3. حفظ المهمة المتكررة**
احفظ المهمة المتكررة بنفس طريقة حفظ المهمة غير المتكررة:
```csharp
string filePath = outputDir + "/YearlyReviewTask_out.msg";
task.Save(filePath, TaskSaveFormat.Msg);
```
### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من المسارات في `dataDir` و `outputDir` هي صحيحة.
- تأكد من أن Aspose.Email مرخص بشكل صحيح لتجنب القيود.
- تحقق من إعدادات المنطقة الزمنية إذا ظهرت المهام بتواريخ غير صحيحة.
## التطبيقات العملية
ضع في اعتبارك السيناريوهات التالية لاستخدام مهام MAPI المتكررة سنويًا:
1. **إدارة المشاريع**:أتمتة إنشاء المهام لمراجعات المشروع السنوية أو المعالم البارزة.
2. **تخطيط الفعاليات**:إعداد تذكيرات للأحداث السنوية، مثل المؤتمرات أو الاجتماعات.
3. **تطبيقات الإنتاجية الشخصية**:التكامل مع التطبيقات التي تدير الجداول الشخصية وقوائم المهام سنويًا.
## اعتبارات الأداء
- تحسين مسارات الملفات لتقليل عمليات الإدخال/الإخراج على القرص.
- إدارة استخدام الذاكرة عن طريق التخلص من الكائنات بشكل مناسب باستخدام `Dispose()` بعد إنشاء المهمة.
- استخدم الطرق غير المتزامنة عند الحاجة لتحقيق أداء أفضل في التطبيقات ذات الأحمال الثقيلة.
## خاتمة
لقد تعلمتَ الآن كيفية إنشاء مهام MAPI وحفظها بتكرار سنوي باستخدام Aspose.Email لـ .NET. تُحسّن هذه الميزة الإنتاجية من خلال أتمتة المهام المتكررة، مما يضمن الاتساق في مشاريعك أو جداولك الشخصية.
**الخطوات التالية:**
- تجربة عن طريق تغيير أنماط التكرار.
- استكشف المزيد من الوظائف التي يوفرها Aspose.Email لـ .NET في إدارة المهام وما بعد ذلك.
**دعوة إلى العمل**:حاول تنفيذ هذا الحل في مشروعك القادم لتبسيط جدولة المهام!
## قسم الأسئلة الشائعة
1. **ما هو Aspose.Email لـ .NET؟**
   - مكتبة قوية تسمح بالتعامل مع رسائل البريد الإلكتروني والتقويمات والمهام داخل تطبيقات .NET.
2. **كيف أتعامل مع مشكلات الترخيص مع Aspose.Email؟**
   - ابدأ بإصدار تجريبي مجاني أو احصل على ترخيص مؤقت للاستفادة من الوظائف الكاملة أثناء مراحل الاختبار.
3. **هل يمكنني استخدام هذا في بيئات غير Windows؟**
   - نعم، Aspose.Email متعدد المنصات ويعمل على Linux وكذلك Windows.
4. **ماذا لو لم ينطبق نمط التكرار الخاص بي كما هو متوقع؟**
   - تأكد مرة أخرى `DayOfMonth` و `MonthOfYear` الإعدادات للتأكد من أنها تتطابق مع الجدول الزمني المقصود.
5. **أين يمكنني العثور على المزيد من الموارد على MapiTasks؟**
   - قم بزيارة [توثيق Aspose.Email](https://reference.aspose.com/email/net/) للحصول على أدلة شاملة ومراجع API.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}