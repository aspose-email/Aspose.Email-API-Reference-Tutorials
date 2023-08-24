---
title: تعيين حالة المشارك لحضور الموعد باستخدام C#
linktitle: تعيين حالة المشارك لحضور الموعد باستخدام C#
second_title: Aspose.Email .NET واجهة برمجة تطبيقات معالجة البريد الإلكتروني
description: تعرف على كيفية إدارة حالة الحضور في الموعد باستخدام C# وAspose.Email لـ .NET. دليل خطوة بخطوة مع كود المصدر.
type: docs
weight: 16
url: /ar/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/
---

## مقدمة إلى Aspose.Email لـ .NET

Aspose.Email for .NET هي مكتبة متعددة الاستخدامات تمكن المطورين من العمل مع رسائل البريد الإلكتروني والمواعيد وجهات الاتصال والمزيد داخل تطبيقات .NET الخاصة بهم. بفضل واجهة برمجة التطبيقات (API) البديهية، يمكن للمطورين التعامل بسهولة مع الجوانب المختلفة للاتصالات عبر البريد الإلكتروني، مما يجعلها خيارًا ممتازًا للتعامل مع المهام المتعلقة بالمواعيد.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio (أو أي C# IDE)
- Aspose.Email لمكتبة .NET
- الفهم الأساسي للبرمجة C#

## إنشاء موعد

للبدء، تحتاج إلى إنشاء مثيل موعد باستخدام Aspose.Email لـ .NET. يمثل الموعد حدثًا مجدولاً، ويمكنك تعيين خصائص مختلفة مثل وقت البدء ووقت الانتهاء والموقع والمزيد.

```csharp
// أضف عبارات الاستخدام الضرورية
using Aspose.Email;
using Aspose.Email.Appointment;

// إنشاء مثيل لفئة التعيين
var appointment = new Appointment();

// ضبط خصائص الموعد
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## إضافة الحضور

 بعد ذلك، يمكنك إضافة الحضور إلى الموعد باستخدام`Attendees` مجموعة. الحضور هم الأفراد الذين سيشاركون في الموعد. يمكنك تحديد عناوين البريد الإلكتروني والأسماء الخاصة بهم.

```csharp
// إضافة الحضور إلى الموعد
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## تحديد حالة المشارك

الآن يأتي الجزء الحاسم: تحديد حالة المشارك للحاضرين. تشير حالة المشارك إلى ما إذا كان الحاضر قد قبل دعوة الموعد أو رفضها أو قبلها مبدئيًا. يوفر Aspose.Email for .NET خيارات حالة مختلفة للاختيار من بينها.

```csharp
// تعيين حالة المشارك للحاضرين
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## كود المصدر الكامل

إليك كود المصدر الكامل الذي يوضح عملية إنشاء موعد وإضافة الحاضرين وتعيين حالة المشارك:

```csharp
// أضف عبارات الاستخدام الضرورية
using Aspose.Email;
using Aspose.Email.Appointment;

// إنشاء مثيل لفئة التعيين
var appointment = new Appointment();

// ضبط خصائص الموعد
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// إضافة الحضور إلى الموعد
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// تعيين حالة المشارك للحاضرين
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## خاتمة

في هذا الدليل، اكتشفنا عملية إدارة الحاضرين في الموعد وتعيين حالة المشارك باستخدام C# وAspose.Email لـ .NET. تجعل الميزات الشاملة للمكتبة أداة قيمة للمطورين الذين يحتاجون إلى العمل مع المهام المتعلقة بالبريد الإلكتروني بكفاءة.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Email لمكتبة .NET؟

 يمكنك تنزيل مكتبة Aspose.Email for .NET من موقع الويب:[تنزيل Aspose.Email لـ .NET](https://releases.aspose.com).

### هل يمكنني تخصيص خيارات حالة المشارك؟

 نعم، يمكنك تخصيص خيارات حالة المشارك وفقًا لاحتياجات التطبيق الخاص بك باستخدام`AppointmentParticipantStatus` التعداد المقدم من Aspose.Email لـ .NET.

### هل Aspose.Email for .NET مناسب للتعامل مع المهام الأخرى المتعلقة بالبريد الإلكتروني؟

قطعاً! يوفر Aspose.Email for .NET مجموعة واسعة من الميزات للتعامل مع رسائل البريد الإلكتروني والمرفقات والمواعيد والمزيد، مما يجعله خيارًا متعدد الاستخدامات لمختلف المهام المتعلقة بالبريد الإلكتروني.

### هل يمكنني دمج هذه الوظيفة في تطبيق .NET الموجود لدي؟

نعم، يمكنك بسهولة دمج الوظائف التي تمت مناقشتها في هذا الدليل في تطبيقات .NET الموجودة لديك من خلال الرجوع إلى مكتبة Aspose.Email لـ .NET واتباع أمثلة التعليمات البرمجية المتوفرة.

### أين يمكنني العثور على المزيد من الوثائق والموارد؟

 لمزيد من الوثائق والموارد التفصيلية، راجع Aspose.Email لوثائق .NET:[Aspose.Email لوثائق .NET](https://reference.aspose.com/email/net).