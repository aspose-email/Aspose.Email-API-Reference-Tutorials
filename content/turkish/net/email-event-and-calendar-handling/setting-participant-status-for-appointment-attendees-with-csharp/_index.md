---
title: C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama
linktitle: C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama
second_title: Aspose.Email .NET E-Posta İşleme API'si
description: Randevu katılımcılarının durumunu C# ve Aspose.Email for .NET kullanarak nasıl yöneteceğinizi öğrenin. Kaynak koduyla adım adım kılavuz.
type: docs
weight: 16
url: /tr/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/
---

## Aspose.Email for .NET'e giriş

Aspose.Email for .NET, geliştiricilerin .NET uygulamalarında e-posta mesajları, randevular, kişiler ve daha fazlasıyla çalışmasına olanak tanıyan çok yönlü bir kütüphanedir. Sezgisel API'si sayesinde geliştiriciler, e-posta iletişiminin çeşitli yönlerini zahmetsizce yönetebilir, bu da onu randevuyla ilgili görevlerin yerine getirilmesi için mükemmel bir seçim haline getirir.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio (veya herhangi bir C# IDE)
- Aspose.Email for .NET kütüphanesi
- C# programlamanın temel anlayışı

## Randevu Oluşturma

Başlamak için Aspose.Email for .NET'i kullanarak bir randevu örneği oluşturmanız gerekir. Randevu, planlanmış bir etkinliği temsil eder ve başlangıç zamanı, bitiş zamanı, konum ve daha fazlası gibi çeşitli özellikleri ayarlayabilirsiniz.

```csharp
// Gerekli kullanım ifadelerini ekleyin
using Aspose.Email;
using Aspose.Email.Appointment;

// Randevu sınıfının bir örneğini oluşturun
var appointment = new Appointment();

// Randevu özelliklerini ayarlama
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## Katılımcı Ekleme

 Daha sonra, randevuya katılımcıları kullanarak ekleyebilirsiniz.`Attendees` Toplamak. Katılımcılar, randevuya katılacak kişilerdir. E-posta adreslerini ve adlarını belirtebilirsiniz.

```csharp
// Randevuya katılımcı ekleme
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## Katılımcı Durumunun Ayarlanması

Şimdi en önemli kısım geliyor: katılımcılar için katılımcı statüsünün ayarlanması. Katılımcı durumu, katılımcının randevu davetini kabul ettiğini, reddettiğini veya geçici olarak kabul ettiğini gösterir. Aspose.Email for .NET, aralarından seçim yapabileceğiniz farklı durum seçenekleri sunar.

```csharp
// Katılımcılar için katılımcı durumunu ayarlama
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Kaynak Kodunu Tamamlayın

Randevu oluşturma, katılımcı ekleme ve katılımcı durumunu ayarlama sürecini gösteren kaynak kodun tamamı burada verilmiştir:

```csharp
// Gerekli kullanım ifadelerini ekleyin
using Aspose.Email;
using Aspose.Email.Appointment;

// Randevu sınıfının bir örneğini oluşturun
var appointment = new Appointment();

// Randevu özelliklerini ayarlama
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// Randevuya katılımcı ekleme
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// Katılımcılar için katılımcı durumunu ayarlama
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Çözüm

Bu kılavuzda, C# ve Aspose.Email for .NET kullanarak randevu katılımcılarını yönetme ve katılımcı durumunu ayarlama sürecini inceledik. Kitaplığın kapsamlı özellikleri, onu e-postayla ilgili görevlerle verimli bir şekilde çalışması gereken geliştiriciler için değerli bir araç haline getiriyor.

## SSS'ler

### Aspose.Email for .NET kütüphanesini nasıl edinebilirim?

 Aspose.Email for .NET kütüphanesini web sitesinden indirebilirsiniz:[.NET için Aspose.Email'i indirin](https://releases.aspose.com).

### Katılımcı durumu seçeneklerini özelleştirebilir miyim?

 Evet, katılımcı durumu seçeneklerini uygulamanızın ihtiyaçlarına göre özelleştirebilirsiniz.`AppointmentParticipantStatus` numaralandırma Aspose.Email for .NET tarafından sağlanmıştır.

### Aspose.Email for .NET e-postayla ilgili diğer görevleri yerine getirmeye uygun mu?

Kesinlikle! Aspose.Email for .NET, e-postalar, ekler, randevular ve daha fazlasıyla çalışmak için çok çeşitli özellikler sunarak, onu e-postayla ilgili çeşitli görevler için çok yönlü bir seçim haline getiriyor.

### Bu işlevselliği mevcut .NET uygulamama entegre edebilir miyim?

Evet, Aspose.Email for .NET kütüphanesine başvurarak ve verilen kod örneklerini takip ederek bu kılavuzda tartışılan işlevselliği mevcut .NET uygulamalarınıza kolayca entegre edebilirsiniz.

### Daha fazla belge ve kaynağı nerede bulabilirim?

 Daha ayrıntılı belgeler ve kaynaklar için Aspose.Email for .NET belgelerine bakın:[Aspose.Email for .NET Belgelendirmesi](https://reference.aspose.com/email/net).