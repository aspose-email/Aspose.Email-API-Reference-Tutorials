---
"date": "2025-05-30"
"description": "تعلّم كيفية تحميل رسائل MAPI برمجيًا من الملفات وتحويلها إلى صيغة MHT باستخدام Aspose.Email لـ .NET. اتبع هذا الدليل خطوة بخطوة."
"title": "كيفية تحميل رسائل MAPI وحفظها بتنسيق MHTML باستخدام Aspose.Email لـ .NET"
"url": "/ar/net/mapi-operations/load-save-mapi-messages-as-mhtml-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تحميل رسائل MAPI وحفظها بتنسيق MHTML باستخدام Aspose.Email لـ .NET

## مقدمة
قد تُشكّل إدارة رسائل البريد الإلكتروني برمجيًا تحديًا، خاصةً مع التنسيقات المعقدة مثل MAPI. مع ذلك، باستخدام Aspose.Email لـ .NET، يُمكنك بسهولة تحميل هذه الرسائل من الملفات وحفظها بتنسيق MHT (MIME HTML) سهل الاستخدام على الويب.

سيرشدك هذا الدليل إلى كيفية استخدام Aspose.Email لـ .NET لتحويل رسائل MAPI إلى صيغة MHTML. ستتعلم كيفية تكوين خيارات الحفظ وتنفيذ عمليات الملفات بكفاءة.

**ما سوف تتعلمه:**
- إعداد Aspose.Email لـ .NET في بيئة التطوير الخاصة بك.
- تحميل رسائل MAPI باستخدام `MapiMessage` فصل.
- تكوين قوالب HTML مخصصة للحفظ بتنسيق MHT.
- حفظ رسائل MAPI كملفات MHTML مع خيارات مخصصة.

## المتطلبات الأساسية

### المكتبات والإصدارات والتبعيات المطلوبة
لمتابعة هذا البرنامج التعليمي، ستحتاج إلى:
- **Aspose.Email لـ .NET**:تأكد من تثبيت الإصدار 22.10 أو إصدار أحدث.
- **.NET Framework أو .NET Core/5+/6+**:اعتمادًا على إعداد مشروعك.

### متطلبات إعداد البيئة
تأكد من أن بيئة التطوير لديك تدعم مشاريع .NET. يمكنك استخدام Visual Studio، أو VS Code مع امتداد C#، أو أي بيئة تطوير متكاملة تدعم تطوير .NET.

### متطلبات المعرفة
فهم أساسي لـ:
- برمجة C#.
- التعامل مع الملفات والمجلدات في .NET.
- العمل مع مكتبات الطرف الثالث.

## إعداد Aspose.Email لـ .NET
بدء استخدام Aspose.Email سهل للغاية. إليك كيفية تثبيته:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Email
```

**استخدام وحدة تحكم إدارة الحزم:**
```powershell
Install-Package Aspose.Email
```

**استخدام واجهة مستخدم NuGet Package Manager:**
1. افتح مدير الحزم NuGet.
2. ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
لبدء استخدام Aspose.Email، يمكنك:
- **نسخة تجريبية مجانية**:قم بتنزيل ترخيص تجريبي لاختبار كافة الميزات.
- **رخصة مؤقتة**:احصل على ترخيص مؤقت للوصول إلى الميزات الكاملة دون قيود التقييم.
- **شراء**:قم بشراء اشتراك إذا كنت مستعدًا لدمجه في بيئة الإنتاج الخاصة بك.

بمجرد التثبيت، قم بتهيئة المكتبة عن طريق تضمين المساحات الأساسية الضرورية في مشروعك:
```csharp
using Aspose.Email;
using System;
```

## دليل التنفيذ

### الميزة 1: تحميل رسالة MAPI من الملف

#### ملخص
توضح هذه الميزة كيفية تحميل رسالة MAPI من مسار ملف محدد باستخدام Aspose.Email، وهو أمر بالغ الأهمية لمعالجة رسائل البريد الإلكتروني المخزنة كرسائل MAPI.

#### خطوات التنفيذ
**الخطوة 1**:تحديد مسار الدليل
يستبدل `"YOUR_DOCUMENT_DIRECTORY"` مع الدليل الفعلي الخاص بك حيث `MapiTask.msg` تم العثور على الملف.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // استبدل بمسار دليل المستند الخاص بك
```
**الخطوة 2**:تحميل رسالة MAPI
استخدم `MapiMessage.FromFile()` طريقة تحميل الرسالة وإنشاء `MapiMessage` اعترض عليه.
```csharp
// قم بتحميل MapiMessage من الملف المحدد
dynamic msg = MapiMessage.FromFile(dataDir + "MapiTask.msg");
```

### الميزة 2: تكوين خيارات حفظ MHT

#### ملخص
يتيح لك تكوين خيارات الحفظ تخصيص كيفية حفظ رسالة MAPI بتنسيق MHTML. تتضمن هذه الخطوة إعداد القوالب وخيارات التنسيق.

#### خطوات التنفيذ
**الخطوة 1**:التهيئة `MhtSaveOptions`
قم بإعداد خيارات حفظ MHTML الافتراضية، والتي سيتم تعديلها للحصول على إخراج مخصص.
```csharp
dynamic opt = SaveOptions.DefaultMhtml;
```
**الخطوة 2**:تعيين خيارات التنسيق
تمكين عرض حقول المهام ومعلومات الرأس في ملف MHTML المحفوظ لديك.
```csharp
opt.MhtFormatOptions = MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader;
```
**الخطوة 3**:تخصيص القوالب
قم بتحديد قوالب HTML لخصائص المهام المختلفة للتحكم في مظهرها في ملف الإخراج.
```csharp
// مسح القوالب الموجودة
opt.FormatTemplates.Clear();

// إضافة قوالب HTML مخصصة لخصائص مهمة محددة
opt.FormatTemplates.Add(MhtTemplateName.Task.Subject, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.ActualWork, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.TotalWork, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Status, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Owner, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Priority, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

### الميزة 3: حفظ رسالة MAPI كملف MHTML

#### ملخص
بعد التهيئة، احفظ رسالة MAPI المُحمَّلة في ملف MHTML. تُنهي هذه الخطوة عملية التحويل باستخدام الخيارات المُحدَّدة مُسبقًا.

#### خطوات التنفيذ
**الخطوة 1**:تحديد مسار ملف الإخراج
حدد المكان الذي تريد حفظ ملف MHTML المحول فيه.
```csharp
string outputFile = dataDir + "MapiTask_out.mht";
```
**الخطوة 2**:احفظ الرسالة
استخدم `Save()` الطريقة مع الخيارات التي قمت بتكوينها لتحويل الرسالة وتخزينها بتنسيق MHTML.
```csharp
// حفظ الرسالة في ملف MHT باستخدام الخيارات التي تم تكوينها مسبقًا
dynamic msg.Save(outputFile, opt);
```

## التطبيقات العملية
1. **أرشفة البريد الإلكتروني**:أرشفة رسائل البريد الإلكتروني من الأنظمة القديمة عن طريق تحويلها إلى تنسيق MHTML سهل الاستخدام على الويب.
2. **التكامل مع أنظمة إدارة المهام**:تحويل رسائل MAPI المرتبطة بالمهام لاستخدامها في تطبيقات إدارة المشاريع الحديثة التي تدعم تنسيقات HTML.
3. **التوثيق والمشاركة**:إنشاء تقارير قابلة للمشاركة لمهام البريد الإلكتروني بتنسيق يمكن الوصول إليه، وهو مثالي للتوثيق أو التعاون.

## اعتبارات الأداء
### تحسين الأداء
- قم بتحميل الملفات الضرورية فقط لتقليل استخدام الذاكرة.
- استخدم الطرق غير المتزامنة عندما يكون ذلك ممكنًا لتجنب عمليات الحظر.

### إرشادات استخدام الموارد
- راقب حجم ذاكرة التطبيق عند التعامل مع كميات كبيرة من الرسائل.
- تخلص من الأشياء بشكل صحيح بعد استخدامها لتحرير الموارد.

### أفضل الممارسات لإدارة ذاكرة .NET باستخدام Aspose.Email
- يستخدم `using` عبارات للتخلص من الكائنات تلقائيًا.
- قم بتحديث Aspose.Email بانتظام للاستفادة من التحسينات والتحسينات في الإصدارات الأحدث.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية تحميل رسائل MAPI من الملفات وحفظها بتنسيق MHTML باستخدام Aspose.Email لـ .NET. أنت الآن مزوّد بالمعرفة اللازمة لتطبيق هذه الميزات في تطبيقاتك، مما يُحسّن قدرات إدارة البريد الإلكتروني.

**الخطوات التالية:**
- تجربة مع مختلف `MhtSaveOptions` إعدادات.
- استكشف الوظائف الإضافية التي يوفرها Aspose.Email لـ .NET.

## قسم الأسئلة الشائعة
1. **هل يمكنني استخدام Aspose.Email مجانًا؟**
   - نعم، يمكنك البدء بإصدار تجريبي مجاني لمدة 30 يومًا لاختبار الإمكانيات الكاملة دون قيود.
2. **ما هي التنسيقات التي يدعمها Aspose.Email بالإضافة إلى MAPI وMHTML؟**
   - إنه يدعم تنسيقات البريد الإلكتروني المختلفة بما في ذلك EML وMSG وPST والمزيد.
3. **كيف أتعامل مع الملفات الكبيرة في Aspose.Email؟**
   - استخدم تقنيات فعالة للذاكرة مثل البث لقراءة/كتابة الملفات الكبيرة.
4. **هل يمكنني دمج هذه الميزة في تطبيق الويب؟**
   - بالتأكيد! هذه الميزة مثالية لتطبيقات الويب التي تتطلب ميزات إدارة البريد الإلكتروني.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}