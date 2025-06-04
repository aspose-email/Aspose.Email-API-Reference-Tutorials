---
"date": "2025-05-30"
"description": "Aspose.Email for .NET ile haftalık tekrarlayan görevleri nasıl ayarlayacağınızı ve yöneteceğinizi öğrenin. Bu kılavuz, zamanlama çözümlerinizi oluşturmayı, yapılandırmayı ve optimize etmeyi kapsar."
"title": "Aspose.Email Kullanarak .NET'te Haftalık Tekrarlayan MapiTasks Nasıl Oluşturulur"
"url": "/tr/net/calendar-appointments/create-manage-weekly-maptasks-net-aspose-email/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email Kullanarak .NET'te Haftalık Tekrarlayan MapiTasks Nasıl Oluşturulur

## giriiş

Tekrarlayan görevleri etkin bir şekilde yönetmek, zamanlama veya takvim işlevleri içeren uygulamalar üzerinde çalışan geliştiriciler için hayati önem taşır. Görev yönetimi için dahili bir araç geliştiriyor veya takvim özelliklerini bir iş uygulamasına entegre ediyor olun, haftalık tekrarlayan görevler oluşturmak ve yönetmek üretkenliği önemli ölçüde artırabilir.

Bu eğitimde, nasıl kullanılacağını keşfedeceğiz **.NET için Aspose.Email** Belirli bir tarihten sonra sona eren haftalık yinelenen MapiTasks oluşturmak için. Bu özellik, Aspose.Email'in sağlam işlevlerini kullanarak uygulamaları içinde zamanlamayı otomatikleştirmek isteyen geliştiriciler için paha biçilmezdir.

### Ne Öğreneceksiniz:
- Aspose.Email'i .NET için kurma ve yapılandırma
- Belirtilen bitiş tarihi olan haftalık yinelenen bir MapiTask oluşturma
- Birden fazla günlük tekrarlama modellerinin uygulanması
- Özel yineleme kurallarına dayalı olarak oluşum sayılarının hesaplanması

Güçlü planlama çözümleri yaratmaya hazır mısınız? Başlayalım!

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **.NET için Aspose.Email** Kütüphane: NuGet veya diğer paket yöneticilerini kullanarak kurulumunu yapabilirsiniz.
- **.NET Framework 4.6.1 veya üzeri** veya **.NET Çekirdek/5+**: Geliştirme ortamınızın uyumlu bir .NET sürümü ile kurulduğundan emin olun.
- Temel C# bilgisi ve nesne yönelimli programlama kavramlarına aşinalık.

## Aspose.Email'i .NET için Kurma

Aspose.Email for .NET'i kullanmaya başlamak için onu projenize eklemeniz gerekir. İşte nasıl:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Email
```

**Paket Yöneticisi Konsolunu Kullanma:**
```powershell
Install-Package Aspose.Email
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü:**
- "Aspose.Email"i arayın ve en son sürümü yükleyin.

### Lisans Edinimi

Lisansı şu yollarla edinebilirsiniz:

- **Ücretsiz Deneme**: Özellikleri sınırlama olmaksızın test edin.
- **Geçici Lisans**: Genişletilmiş yetenekleri değerlendirmek için bunu kullanın.
- **Satın almak**:Tam erişim için ticari lisans satın alın.

Lisans dosyanız hazır olduğunda, lisansı kodunuza uygulayarak Aspose.Email'i başlatın:
```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("path_to_license_file.lic");
```

## Uygulama Kılavuzu

Uygulamayı iki ana özelliğe ayıracağız: tek günlük haftalık tekrarlama oluşturma ve birden fazla günlük tekrarlamalar ayarlama.

### Belirli Bir Tarihten Sonra Sonlanan Haftalık Tekrarlayan Bir MapiTask Oluşturma

#### Genel bakış
Bu özellik, belirli bir tarihten sonra sona erene kadar her hafta belirli bir günde tekrar eden görevler oluşturmanıza olanak tanır. Tekrarlayan toplantıları veya son tarihleri planlamak için mükemmeldir.

#### Uygulama Adımları
**Adım 1: Tekrarlama Desenini Yapılandırın**
Burada, tekrarlama desenini kullanarak ayarlayacağız `MapiCalendarWeeklyRecurrencePattern`.
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1, // Haftalık tekrarlama
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday, // Cuma günleri tekrarlanır
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR;INTERVAL=1")
};
```
**Adım 2: MapiTask'ı oluşturun**
Artık tekrarlama desenimizi yapılandırdığımıza göre, bir görev oluşturalım ve bu deseni ona atayalım.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;

if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1; // En azından bir oluşumun sağlanması
}

task.Recurrence = rec;
```
**Adım 3: Görevi Kaydedin**
Son olarak, kalıcı olması için görevinizi bir .msg dosyasına kaydedin.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateEveryDayRecurrence_out.msg", TaskSaveFormat.Msg);
```

### Belirli Bir Tarihten Sonra Sona Eren Birden Fazla Gün İçin Haftalık Tekrarlayan Bir MapiTask Oluşturma

#### Genel bakış
Bu özellik, her hafta birden fazla günde tekrarlanan görevlere izin vermek için önceki kurulumu genişletir ve daha karmaşık planlama ihtiyaçları için esneklik sağlar.

#### Uygulama Adımları
**Adım 1: Çok Günlük Tekrarlama Desenini Yapılandırın**
Haftada birden fazla tekrarlanan günü içeren bir desen oluşturun.
```csharp
var record = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // Her iki haftada bir gerçekleşir
    WeekStartDay = DayOfWeek.Sunday,
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday, // Cuma ve pazartesi günleri tekrarlanır
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2")
};
```
**Adım 2: MapiTask'ı Oluşturun ve Atayın**
Öncekine benzer şekilde bir görev oluşturun ve bu çok günlük deseni atayın.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;
task.Recurrence = record;
```
**Adım 3: Çok Günlük Görevi Kaydedin**
Görevinizi doğru şekilde saklandığından emin olmak için benzer şekilde kaydedin.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateMultipleDaysRecurrence_out.msg", TaskSaveFormat.Msg);
```

## Pratik Uygulamalar

Bu özelliklerin bazı pratik uygulamaları şunlardır:

1. **Haftalık Toplantıların Otomatikleştirilmesi**: Belirli günlerde, örneğin Cuma günleri, tekrarlayan ekip toplantıları planlayın.
2. **Görev Son Tarihleri**:Her Pazartesi ve Cuma tekrar eden proje görevleri için haftalık teslim tarihleri belirleyin.
3. **Etkinlik Planlaması**:Her hafta birden fazla günde takip gerektiren etkinlik planlama programlarını yönetin.

## Performans Hususları

- **Bellek Kullanımını Optimize Et**Özellikle büyük veri kümeleri veya çok sayıda yinelenen görevle uğraşırken, bellek sızıntılarını önlemek için nesneleri doğru şekilde elden çıkardığınızdan emin olun.
- **Etkin Tarih Hesaplamaları**:İşlem süresini en aza indirmek için, tekrarlama kurallarınız dahilinde tarih hesaplamaları için verimli algoritmalar kullanın.
- **Asenkron İşlemler**Görevleri diske veya ağ konumlarına kaydederken performansı artırmak için eşzamansız yöntemleri göz önünde bulundurun.

## Çözüm

Bu eğitimde, Aspose.Email for .NET kullanarak haftalık tekrarlayan MapiTasks'lerin nasıl oluşturulacağını ve yönetileceğini ele aldık. Yukarıda özetlenen adımları izleyerek, uygulamalarınızda karmaşık zamanlama özelliklerini kolayca uygulayabilirsiniz.

Aspose.Email'in yeteneklerini daha fazla keşfetmek veya daha karmaşık senaryolarla başa çıkmak için resmi belgelerini ve topluluk forumlarını incelemeyi düşünebilirsiniz.

## SSS

**S: Aspose.Email for .NET'i nasıl yüklerim?**
A: NuGet Paket Yöneticisi aracılığıyla şu komutu kullanarak yükleyebilirsiniz: `Install-Package Aspose.Email`.

**S: MapiTask nedir?**
A: MapiTask, konu, son tarih ve tekrarlama deseni gibi özelliklere sahip bir Outlook görevini temsil eder.

**S: Tekrarlama desenlerini daha da özelleştirebilir miyim?**
A: Evet, günlük veya aylık gibi farklı tekrarlama türlerini ayarlayarak kullanabilirsiniz. `PatternType` mülkiyeti `MapiCalendarRecurrencePattern`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}