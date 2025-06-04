---
"description": "C# ve Aspose.Email for .NET kullanarak randevu katılımcılarının durumlarını nasıl yöneteceğinizi öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama"
"second_title": "Aspose.Email .NET E-posta İşleme API'si"
"title": "C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama"
"url": "/tr/net/email-event-and-calendar-handling/setting-participant-status-for-appointment-attendees-with-csharp/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# C# ile Randevu Katılımcıları için Katılımcı Durumunu Ayarlama


## .NET için Aspose.Email'e Giriş

Aspose.Email for .NET, geliştiricilerin .NET uygulamaları içinde e-posta mesajları, randevular, kişiler ve daha fazlasıyla çalışmasını sağlayan çok yönlü bir kütüphanedir. Sezgisel API'siyle geliştiriciler e-posta iletişiminin çeşitli yönlerini zahmetsizce yönetebilir ve bu da onu randevuyla ilgili görevleri ele almak için mükemmel bir seçim haline getirir.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Visual Studio (veya herhangi bir C# IDE)
- Aspose.Email for .NET kütüphanesi
- C# programlamanın temel anlayışı

## Randevu Oluşturma

Başlamak için, Aspose.Email for .NET kullanarak bir randevu örneği oluşturmanız gerekir. Bir randevu, planlanmış bir etkinliği temsil eder ve başlangıç saati, bitiş saati, konum ve daha fazlası gibi çeşitli özellikler ayarlayabilirsiniz.

```csharp
// Gerekli using ifadelerini ekleyin
using Aspose.Email;
using Aspose.Email.Appointment;

// Randevu sınıfının bir örneğini oluşturun
var appointment = new Appointment();

// Randevu özelliklerini ayarla
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";
```

## Katılımcı Ekleme

Daha sonra, katılımcıları randevuya eklemek için şu adımları kullanabilirsiniz: `Attendees` koleksiyon. Katılımcılar, randevuya katılacak kişilerdir. E-posta adreslerini ve adlarını belirtebilirsiniz.

```csharp
// Randevuya katılımcı ekleyin
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");
```

## Katılımcı Durumunu Ayarlama

Şimdi kritik kısım geliyor: katılımcılar için katılımcı durumunu ayarlama. Katılımcı durumu, bir katılımcının randevu davetini kabul edip etmediğini, reddettiğini veya geçici olarak kabul edip etmediğini gösterir. Aspose.Email for .NET, seçebileceğiniz farklı durum seçenekleri sunar.

```csharp
// Katılımcılar için katılımcı durumunu ayarlayın
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Tam Kaynak Kodu

İşte randevu oluşturma, katılımcı ekleme ve katılımcı durumunu ayarlama sürecini gösteren tam kaynak kodu:

```csharp
// Gerekli using ifadelerini ekleyin
using Aspose.Email;
using Aspose.Email.Appointment;

// Randevu sınıfının bir örneğini oluşturun
var appointment = new Appointment();

// Randevu özelliklerini ayarla
appointment.StartTime = DateTime.Now;
appointment.EndTime = appointment.StartTime.AddHours(1);
appointment.Location = "Conference Room 101";

// Randevuya katılımcı ekleyin
appointment.Attendees.Add("john@example.com", "John Doe");
appointment.Attendees.Add("jane@example.com", "Jane Smith");

// Katılımcılar için katılımcı durumunu ayarlayın
appointment.Attendees[0].ParticipantStatus = AppointmentParticipantStatus.Accepted;
appointment.Attendees[1].ParticipantStatus = AppointmentParticipantStatus.Declined;
```

## Çözüm

Bu kılavuzda, C# ve Aspose.Email for .NET kullanarak randevu katılımcılarını yönetme ve katılımcı durumunu ayarlama sürecini inceledik. Kütüphanenin kapsamlı özellikleri, e-postayla ilgili görevlerle verimli bir şekilde çalışması gereken geliştiriciler için onu değerli bir araç haline getirir.

## SSS

### Aspose.Email for .NET kütüphanesini nasıl edinebilirim?

Aspose.Email for .NET kütüphanesini şu web sitesinden indirebilirsiniz: [.NET için Aspose.Email'i indirin](https://releases.aspose.com).

### Katılımcı durum seçeneklerini özelleştirebilir miyim?

Evet, katılımcı durum seçeneklerini uygulamanızın ihtiyaçlarına göre özelleştirebilirsiniz. `AppointmentParticipantStatus` numaralandırma Aspose.Email for .NET tarafından sağlanmıştır.

### Aspose.Email for .NET diğer e-postayla ilgili görevleri yönetmek için uygun mudur?

Kesinlikle! Aspose.Email for .NET, e-postalar, ekler, randevular ve daha fazlasıyla çalışmak için çok çeşitli özellikler sunarak çeşitli e-postayla ilgili görevler için çok yönlü bir seçim haline geliyor.

### Bu işlevselliği mevcut .NET uygulamamla bütünleştirebilir miyim?

Evet, bu kılavuzda ele alınan işlevselliği, Aspose.Email for .NET kitaplığına başvurarak ve sağlanan kod örneklerini izleyerek mevcut .NET uygulamalarınıza kolayca entegre edebilirsiniz.

### Daha fazla doküman ve kaynağı nerede bulabilirim?

Daha ayrıntılı belgeler ve kaynaklar için Aspose.Email for .NET belgelerine bakın: [Aspose.Email for .NET Belgeleri](https://reference.aspose.com/email/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}