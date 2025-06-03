---
"date": "2025-05-30"
"description": "تعلّم كيفية إدارة ملفات PST بكفاءة عن طريق نقل المجلدات الفرعية والرسائل باستخدام Aspose.Email لـ .NET. نظّم بريدك الإلكتروني بسهولة باستخدام أمثلة عملية على التعليمات البرمجية."
"title": "إتقان إدارة PST - نقل مجلدات Outlook الفرعية والرسائل باستخدام Aspose.Email لـ .NET"
"url": "/ar/net/outlook-pst-ost-operations/master-pst-management-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان إدارة PST: نقل المجلدات الفرعية والرسائل في Outlook باستخدام Aspose.Email لـ .NET

## مقدمة

تُعد إدارة بيانات البريد الإلكتروني بكفاءة أمرًا بالغ الأهمية، خاصةً عند التعامل مع كميات كبيرة من رسائل البريد الإلكتروني في ملفات PST. سواءً كنت تُنظّم صناديق البريد المُكدّسة أو تُزيل الرسائل غير المرغوب فيها، فإن إمكانية نقل المجلدات الفرعية والرسائل داخل ملفات Outlook PST تُوفّر الوقت وتُحسّن الإنتاجية. سيُرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Email لـ .NET لتبسيط مهام إدارة بريدك الإلكتروني.

**ما سوف تتعلمه:**
- نقل المجلدات الفرعية للبريد الوارد إلى العناصر المحذوفة باستخدام Aspose.Email
- نقل رسائل البريد الإلكتروني الفردية عبر المجلدات
- نقل كافة المحتويات داخل مجلد معين
- تحسين الأداء عند إدارة ملفات PST

تأكد من أن لديك الأدوات والفهم اللازمين قبل البدء في هذا الدليل.

## المتطلبات الأساسية

قبل الخوض في تفاصيل التنفيذ، دعنا نحدد ما تحتاجه:

### المكتبات المطلوبة:
- **Aspose.Email لـ .NET** (v21.3 أو أحدث) - مكتبة شاملة تدعم إدارة ملفات PST من بين التنسيقات الأخرى.

### إعداد البيئة:
- قم بإعداد بيئة التطوير الخاصة بك باستخدام Visual Studio أو أي IDE متوافق يدعم مشاريع .NET.

### المتطلبات المعرفية:
- فهم أساسي لبرمجة C# ومفاهيم إطار عمل .NET.
- التعرف على هياكل ملفات Outlook PST.

## إعداد Aspose.Email لـ .NET

للبدء، قم بدمج مكتبة Aspose.Email في مشروعك. إليك بعض الطرق:

**استخدام .NET CLI:**
```shell
dotnet add package Aspose.Email
```

**استخدام Package Manager Console في Visual Studio:**
```powershell
Install-Package Aspose.Email
```

**عبر واجهة مستخدم NuGet Package Manager:**
- ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص:
- **نسخة تجريبية مجانية:** ابدأ بفترة تجريبية مجانية لمدة 30 يومًا لاستكشاف الميزات.
- **رخصة مؤقتة:** احصل على ترخيص مؤقت إذا كنت بحاجة إلى مزيد من الوقت.
- **شراء:** فكر في شراء ترخيص كامل للاستخدام على المدى الطويل.

لتهيئة Aspose.Email في مشروعك، قم بإعداد الترخيص على النحو التالي:

```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("Aspose.Total.lic");
```

## دليل التنفيذ

### نقل مجلد فرعي محدد من البريد الوارد إلى العناصر المحذوفة

#### ملخص
تتيح لك هذه الميزة نقل مجلد فرعي كامل داخل ملف Outlook PST مباشرة إلى مجلد العناصر المحذوفة.

**الخطوة 1: الوصول إلى المجلدات المحددة مسبقًا**
```csharp
using Aspose.Email.Storage.Pst;
string dataDir = @"YOUR_DOCUMENT_DIRECTORY"; // استبدله بمسار الدليل الفعلي الخاص بك

using (PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir + "/Outlook_1.pst"))
{
    FolderInfo inbox = personalStorage.GetPredefinedFolder(StandardIpmFolder.Inbox);
    FolderInfo deleted = personalStorage.GetPredefinedFolder(StandardIpmFolder.DeletedItems);

    // تأكد من وجود المجلد الفرعي
    if (inbox != null && deleted != null)
    {
        FolderInfo subfolder = inbox.GetSubFolder("YourSubfolderName");
```

**الخطوة 2: نقل المجلد الفرعي**
```csharp
        if (subfolder != null)
        {
            personalStorage.MoveItem(subfolder, deleted);
        }
    }
}
```
- **لماذا نقل مجلد فرعي؟**:يساعدك هذا على تنظيم صندوق الوارد الخاص بك عن طريق عزل رسائل البريد الإلكتروني المحددة في مجلد العناصر المحذوفة.

### نقل رسالة فردية

#### ملخص
توضح هذه الميزة إمكانية نقل بريد إلكتروني واحد من أي مجلد فرعي مباشرة إلى مجلد العناصر المحذوفة، مما يتيح إدارة دقيقة للرسائل الفردية.

**الخطوة 1: استرداد الرسائل**
```csharp
using Aspose.Email.Storage.Pst;
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";

using (PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir + "/Outlook_1.pst"))
{
    FolderInfo inbox = personalStorage.GetPredefinedFolder(StandardIpmFolder.Inbox);
    FolderInfo deleted = personalStorage.GetPredefinedFolder(StandardIpmFolder.DeletedItems);

    if (inbox != null && deleted != null)
    {
        FolderInfo subfolder = inbox.GetSubFolder("YourSubfolderName");
```

**الخطوة 2: نقل الرسالة**
```csharp
        if (subfolder != null)
        {
            MessageInfoCollection contents = subfolder.GetContents();
            
            // انقل الرسالة الأولى كمثال
            personalStorage.MoveItem(contents[0], deleted);
        }
    }
}
```
- **لماذا نقل الرسائل الفردية؟**:يعد هذا مثاليًا لإزالة رسائل البريد الإلكتروني المحددة أو أرشفتها بسرعة دون حذف المجلد بأكمله.

### نقل جميع المجلدات الفرعية

#### ملخص
تتيح لك هذه الميزة نقل كافة المجلدات الفرعية داخل مجلد محدد مسبقًا مثل البريد الوارد إلى مجلد العناصر المحذوفة مرة واحدة.

**الخطوة 1: الوصول والتحضير**
```csharp
using Aspose.Email.Storage.Pst;
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";

using (PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir + "/Outlook_1.pst"))
{
    FolderInfo inbox = personalStorage.GetPredefinedFolder(StandardIpmFolder.Inbox);
    FolderInfo deleted = personalStorage.GetPredefinedFolder(StandardIpmFolder.DeletedItems);

    if (inbox != null && deleted != null)
```

**الخطوة 2: تنفيذ النقل**
```csharp
    {
        // نقل جميع المجلدات الفرعية من البريد الوارد إلى العناصر المحذوفة
        inbox.MoveSubfolders(deleted);
    }
}
```
- **لماذا نقل كافة المجلدات الفرعية؟**:يُعد هذا مفيدًا للعمليات المجمعة عندما تحتاج إلى مسح مجلدات متعددة بكفاءة.

### نقل كافة محتويات المجلد الفرعي

#### ملخص
ترتكز هذه الميزة على نقل كل عنصر داخل مجلد فرعي محدد إلى مجلد العناصر المحذوفة، والحفاظ على التنظيم دون تحديد يدوي.

**الخطوة 1: الوصول إلى المجلد الفرعي المستهدف**
```csharp
using Aspose.Email.Storage.Pst;
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";

using (PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir + "/Outlook_1.pst"))
{
    FolderInfo inbox = personalStorage.GetPredefinedFolder(StandardIpmFolder.Inbox);
    FolderInfo deleted = personalStorage.GetPredefinedFolder(StandardIpmFolder.DeletedItems);

    if (inbox != null && deleted != null)
    {
        FolderInfo subfolder = inbox.GetSubFolder("YourSubfolderName");
```

**الخطوة 2: نقل كافة المحتويات**
```csharp
        if (subfolder != null)
        {
            // نقل كافة المحتويات إلى العناصر المحذوفة
            subfolder.MoveContents(deleted);
        }
    }
}
```
- **لماذا نقل محتوى المجلد الفرعي بأكمله؟**:يعتبر هذا النهج مثاليًا عندما تحتاج إلى مسح مجلد دون ترك أي رسائل خلفك.

## التطبيقات العملية

1. **تنظيف البريد الإلكتروني:** أرشفة رسائل البريد الإلكتروني العشوائية أو غير ذات الصلة تلقائيًا في العناصر المحذوفة.
2. **نقل البيانات:** نقل البيانات التنظيمية بكفاءة أثناء ترقيات النظام أو عمليات الترحيل.
3. **أغراض النسخ الاحتياطي:** نقل رسائل البريد الإلكتروني الأساسية إلى مواقع النسخ الاحتياطي أثناء مسح الرسائل المكررة من المجلدات النشطة.
4. **إدارة الامتثال:** قم بتنظيم رسائل البريد الإلكتروني استعدادًا للتدقيق عن طريق نقلها إلى مجلدات الامتثال المخصصة.

## اعتبارات الأداء

- **معالجة الدفعات:** عند التعامل مع كميات كبيرة من البيانات، فكر في المعالجة على دفعات لتجنب تجاوز سعة الذاكرة.
- **مراقبة الموارد:** قم بمراقبة استخدام موارد التطبيق بانتظام وقم بتحسين الكود حسب الحاجة.
- **جمع القمامة:** استخدم مجموعة القمامة الخاصة بـ .NET بشكل فعال لإدارة الذاكرة عند التعامل مع ملفات PST كبيرة الحجم.

## خاتمة

يُحسّن إتقان نقل المجلدات الفرعية والرسائل داخل ملفات Outlook PST باستخدام Aspose.Email لـ .NET من قدرات إدارة بريدك الإلكتروني. باتباع هذا الدليل، ستتعلم تقنيات متنوعة لتنظيم صندوق بريدك بكفاءة. واصل استكشاف ميزات Aspose.Email الشاملة، وفكّر في دمجها في مشاريع أكبر لتحسين الإنتاجية.

## قسم الأسئلة الشائعة

**س1: ما هي الميزة الرئيسية لاستخدام Aspose.Email لـ .NET؟**
ج1: يوفر وظائف قوية لإدارة بيانات البريد الإلكتروني برمجيًا، مما يوفر المرونة والكفاءة في التعامل مع ملفات Outlook PST.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}