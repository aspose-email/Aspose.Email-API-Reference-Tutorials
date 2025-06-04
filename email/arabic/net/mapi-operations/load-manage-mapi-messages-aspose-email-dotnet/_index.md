---
"date": "2025-05-30"
"description": "تعرّف على كيفية تحميل رسائل MAPI وإدارتها باستخدام Aspose.Email لـ .NET. يغطي هذا الدليل الشامل تحميل رسائل MAPI، وإنشاء الملاحظات، وإدارة ملفات PST."
"title": "تحميل وإدارة رسائل MAPI باستخدام Aspose.Email لـ .NET - دليل شامل"
"url": "/ar/net/mapi-operations/load-manage-mapi-messages-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تحميل وإدارة رسائل MAPI باستخدام Aspose.Email لـ .NET: دليل شامل

## مقدمة

دمج وظائف البريد الإلكتروني في تطبيقات .NET سهل للغاية مع Aspose.Email لـ .NET. تُبسّط هذه المكتبة الفعّالة إدارة رسائل Microsoft Outlook برمجيًا. سواءً كنت تُطوّر تطبيقًا يتطلب معالجة رسائل البريد الإلكتروني أو تُؤتمت المهام في بيئة مؤسسية، يُقدّم هذا الدليل رؤىً قيّمة لمساعدتك على البدء بكفاءة.

**ما سوف تتعلمه:**
- كيفية تحميل رسائل MAPI من الملفات
- إنشاء الملاحظات وتخصيصها برمجيًا
- إدارة ملفات التخزين الشخصية (PST) بشكل فعال

قبل الغوص في البرمجة، دعنا نتأكد من أن بيئتك جاهزة بالتبعيات الضرورية.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك الإعداد التالي:

### المكتبات والإصدارات والتبعيات المطلوبة
- **Aspose.Email لـ .NET**:تأكد من التوافق مع إطار العمل المستهدف لمشروعك.

### متطلبات إعداد البيئة
- قم بتثبيت إصدار متوافق من .NET SDK على جهازك.
- استخدم محرر نصوص أو IDE مثل Visual Studio الذي يدعم تطوير C#.

### متطلبات المعرفة
- فهم أساسي لبرمجة C#.
- إن المعرفة بمفاهيم البريد الإلكتروني ورسائل MAPI مفيدة ولكنها ليست مطلوبة.

## إعداد Aspose.Email لـ .NET

للبدء، أضف مكتبة Aspose.Email إلى مشروعك. إليك الطريقة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Email
```

**استخدام مدير الحزم:**
```powershell
Install-Package Aspose.Email
```

**عبر واجهة مستخدم NuGet Package Manager:**
ابحث عن "Aspose.Email" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص
يمكنك البدء بإصدار تجريبي مجاني أو الحصول على ترخيص مؤقت لاستكشاف المزيد من الميزات:
- **نسخة تجريبية مجانية**: [تحميل](https://releases.aspose.com/email/net/)
- **رخصة مؤقتة**:متوفر على موقع Aspose الإلكتروني للوصول الموسع.
- **شراء**:خيارات الترخيص الكاملة متاحة في [شراء Aspose](https://purchase.aspose.com/buy).

**التهيئة والإعداد الأساسي**
تأكد من أن مشروعك يشير إلى مساحات الأسماء الضرورية:
```csharp
using System;
using Aspose.Email.Mapi;
```

## دليل التنفيذ

سنقوم بتقسيم التنفيذ إلى ميزتين رئيسيتين: تحميل رسائل MAPI وإدارة ملفات PST.

### الميزة 1: تحميل رسالة MAPI

#### ملخص
توضح هذه الميزة كيفية تحميل رسالة MAPI من ملف، وهو أمر ضروري لمعالجة رسائل البريد الإلكتروني أو الملاحظات المحفوظة في تطبيقك.

#### خطوات التنفيذ

**الخطوة 1: تحميل رسالة MAPI**
حدد الدليل الذي يوجد به `Note.msg` تم تحديد موقع الملف وتحميله باستخدام Aspose.Email:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
MapiMessage mess = MapiMessage.FromFile(dataDir + "Note.msg");
```

**الخطوة 2: إنشاء الملاحظات وتخصيصها**
تحويل الرسالة المحملة إلى ملاحظات متعددة ذات خصائص مختلفة:
```csharp
// إنشاء ملاحظة صفراء
MapiNote note1 = (MapiNote)mess.ToMapiMessageItem();
note1.Subject = "Yellow color note";
note1.Body = "This is a yellow color note";

// إنشاء ملاحظة وردية
MapiNote note2 = (MapiNote)mess.ToMapiMessageItem();
note2.Subject = "Pink color note";
note2.Body = "This is a pink color note";
note2.Color = NoteColor.Pink;

// إنشاء ملاحظة زرقاء ذات أبعاد
MapiNote note3 = (MapiNote)mess.ToMapiMessageItem();
note3.Subject = "Blue color note";
note3.Body = "This is a blue color note";
note3.Color = NoteColor.Blue;
note3.Height = 500;
note3.Width = 500;
```

### الميزة 2: إنشاء وإدارة ملف التخزين الشخصي (PST)

#### ملخص
تعرّف على كيفية إنشاء ملف PST، وإضافة مجلدات، وإدراج رسائل MAPI. هذا أمر بالغ الأهمية للتطبيقات التي تحتاج إلى تخزين رسائل البريد الإلكتروني محليًا.

#### خطوات التنفيذ

**الخطوة 1: إعداد مسار الإخراج**
قم بتحديد المكان الذي سيتم حفظ ملف PST الناتج فيه:
```csharp
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\AddMapiNoteToPST_out.pst";

// تأكد من عدم وجود تعارضات في الملفات الموجودة عن طريق حذفها إذا كانت موجودة.
if (File.Exists(outputPath))
{
    File.Delete(outputPath);
}
```

**الخطوة 2: إنشاء وتنظيم PST**
تهيئة ملف PST جديد وإنشاء مجلدات:
```csharp
using (PersonalStorage personalStorage = PersonalStorage.Create(outputPath, FileFormatVersion.Unicode))
{
    // قم بإنشاء مجلد "ملاحظات" لتخزين ملاحظاتك.
    FolderInfo notesFolder = personalStorage.CreatePredefinedFolder("Notes\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}