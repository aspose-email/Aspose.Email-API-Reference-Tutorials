---
"description": "تعرّف على كيفية إدارة حالة المشاركين في المواعيد باستخدام C# وAspose.Email لـ .NET. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "تعيين حالة المشارك لحضور الموعد باستخدام C#"
"second_title": "واجهة برمجة تطبيقات معالجة البريد الإلكتروني Aspose.Email .NET"
"title": "تعيين حالة المشارك لحضور الموعد باستخدام C#"
"url": "/ar/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين حالة المشارك لحضور الموعد باستخدام C#


## مقدمة إلى Aspose.Email لـ .NET

Aspose.Email لـ .NET هي مكتبة متعددة الاستخدامات تُمكّن المطورين من التعامل مع رسائل البريد الإلكتروني والمواعيد وجهات الاتصال وغيرها ضمن تطبيقات .NET. بفضل واجهة برمجة التطبيقات سهلة الاستخدام، يُمكن للمطورين التعامل بسهولة مع مختلف جوانب التواصل عبر البريد الإلكتروني، مما يجعلها خيارًا ممتازًا لإدارة المهام المتعلقة بالمواعيد.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio (أو أي بيئة تطوير متكاملة لـ C#)
- مكتبة Aspose.Email لـ .NET
- فهم أساسي لبرمجة C#

## إنشاء موعد

للبدء، عليك إنشاء مثيل موعد باستخدام Aspose.Email لـ .NET. يمثل الموعد حدثًا مُجدولًا، ويمكنك تعيين خصائص مُختلفة مثل وقت البدء ووقت الانتهاء والموقع وغيرها.

```csharp
// أضف عبارات الاستخدام الضرورية
using Aspose.Email;
using Aspose.Email.Appointment;

// إنشاء مثيل لفئة الموعد
var appointment = new Appointment();

// تعيين خصائص الموعد
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## إضافة الحضور

بعد ذلك، يمكنك إضافة الحضور إلى الموعد باستخدام `Attendees` الحضور هم الأفراد الذين سيشاركون في الموعد. يمكنك تحديد عناوين بريدهم الإلكتروني وأسمائهم.

```csharp
// إضافة الحضور إلى الموعد
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## تحديد حالة المشارك

الآن يأتي الجزء الأهم: تحديد حالة المشارك للحضور. تشير حالة المشارك إلى ما إذا كان قد قبل دعوة الموعد، أو رفضها، أو قبلها مبدئيًا. يوفر Aspose.Email لـ .NET خيارات حالة مختلفة للاختيار من بينها.

```csharp
// تعيين حالة المشارك للحضور
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## الكود المصدر الكامل

فيما يلي الكود المصدر الكامل الذي يوضح عملية إنشاء موعد وإضافة الحاضرين وتعيين حالة المشارك:

```csharp
// أضف عبارات الاستخدام الضرورية
using Aspose.Email;
using Aspose.Email.Appointment;

// إنشاء مثيل لفئة الموعد
var appointment = new Appointment();

// تعيين خصائص الموعد
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// إضافة الحضور إلى الموعد
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// تعيين حالة المشارك للحضور
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## خاتمة

في هذا الدليل، استكشفنا عملية إدارة حضور المواعيد وتحديد حالة المشارك باستخدام C# وAspose.Email لـ .NET. الميزات الشاملة للمكتبة تجعلها أداة قيّمة للمطورين الذين يحتاجون إلى العمل بكفاءة مع مهام البريد الإلكتروني.

## الأسئلة الشائعة

### كيف يمكنني الحصول على مكتبة Aspose.Email لـ .NET؟

يمكنك تنزيل مكتبة Aspose.Email لـ .NET من موقع الويب: [تنزيل Aspose.Email لـ .NET](https://releases.aspose.com).

### هل يمكنني تخصيص خيارات حالة المشارك؟

نعم، يمكنك تخصيص خيارات حالة المشارك وفقًا لاحتياجات تطبيقك باستخدام `AppointmentParticipantStatus` تم توفير التعداد بواسطة Aspose.Email لـ .NET.

### هل Aspose.Email لـ .NET مناسب للتعامل مع المهام الأخرى المتعلقة بالبريد الإلكتروني؟

بالتأكيد! يوفر Aspose.Email لـ .NET مجموعة واسعة من الميزات للتعامل مع رسائل البريد الإلكتروني والمرفقات والمواعيد وغيرها، مما يجعله خيارًا متعدد الاستخدامات لمختلف مهام البريد الإلكتروني.

### هل يمكنني دمج هذه الوظيفة في تطبيق .NET الحالي الخاص بي؟

نعم، يمكنك بسهولة دمج الوظيفة التي تمت مناقشتها في هذا الدليل في تطبيقات .NET الموجودة لديك من خلال الرجوع إلى مكتبة Aspose.Email لـ .NET واتباع أمثلة التعليمات البرمجية المقدمة.

### أين يمكنني العثور على مزيد من الوثائق والموارد؟

للحصول على وثائق وموارد أكثر تفصيلاً، راجع وثائق Aspose.Email لـ .NET: [توثيق Aspose.Email لـ .NET](https://reference.aspose.com/email/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}