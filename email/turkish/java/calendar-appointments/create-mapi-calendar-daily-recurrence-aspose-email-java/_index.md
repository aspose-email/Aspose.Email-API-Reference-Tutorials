---
date: '2026-03-20'
description: Outlook takvimini günlük yinelenme ve istisnalarla Java’da nasıl oluşturacağınızı
  ve takvimi Aspose.Email for Java kullanarak PST’ye nasıl kaydedeceğinizi öğrenin.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 'Java ile Outlook takvimi oluşturma: günlük tekrarlama ve istisnalar'
url: /tr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Günlük yineleme ve istisnalarla outlook calendar java nasıl oluşturulur

Yineleyen etkinlikleri verimli bir şekilde yönetmek zor olabilir, özellikle günlük yineleme desenlerini ve ara sıra istisnaları destekleyen bir **outlook calendar java**'ya ihtiyacınız olduğunda. Bu öğreticide Outlook takvim Java nesnelerini nasıl oluşturacağınızı, günlük yinelemeyi nasıl yapılandıracağınızı, istisna örneklerini nasıl ekleyeceğinizi ve sonunda Aspose.Email for Java kullanarak **save calendar to PST**'yi nasıl yapacağınızı öğreneceksiniz. Sonunda, herhangi bir Java tabanlı zamanlama hizmetine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane?** Aspose.Email for Java  
- **Ana görev?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Gereken JDK?** Java 16 or higher  
- **İstisnalara dosya ekleyebilir miyim?** Yes, using `MapiCalendarExceptionInfo`  
- **Takvim nerede depolanıyor?** In a PST file via `PersonalStorage`

## Outlook calendar java nedir?
Bir Outlook takvim Java nesnesi (MAPI takvimi olarak uygulanır) Microsoft Outlook randevuları ile aynı standartları izler. Zengin yineleme kuralları, istisna yönetimi, katılımcılar ve ekleri depolar, bu da onu kurumsal düzeyde zamanlama için mükemmel kılar.

## Aspose.Email for Java neden kullanılmalı?
Aspose.Email, Outlook yüklü olmadan MAPI nesneleriyle çalışmanıza olanak tanıyan saf Java API'si sağlar. Bu **aspose email tutorial java** yaklaşımı, sunucu tarafında PST dosyalarının oluşturulmasını, otomatik toplantı serilerini ve yineleme mantığı üzerinde tam kontrolü mümkün kılar.

## Önkoşullar

Before we begin, ensure you have the following setup:
- **Aspose.Email Kütüphanesi**: Version 25.4 (veya daha yeni) – Maven veya doğrudan indirme yoluyla kullanılabilir.  
- **Java Development Kit (JDK)**: JDK 16 veya daha yeni.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans veya herhangi bir Java uyumlu editör.

### Gerekli Kütüphaneler ve Bağımlılıklar

To integrate Aspose.Email into your project using Maven, add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Edinimi

To use Aspose.Email, you'll need a license:
- **Free Trial** – tüm özellikleri ücretsiz keşfedin.  
- **Temporary License** – daha uzun bir değerlendirme için talep edin.  
- **Full License** – üretim dağıtımları için satın alın.

## Aspose.Email for Java Kurulumu

First, set up your environment:

1. JDK 16'nın kurulu olduğunu ve `JAVA_HOME`'un yapılandırıldığını doğrulayın.  
2. Maven bağımlılığını (veya JAR'ı indirerek) projenize ekleyin.  

Here’s a tiny snippet that shows how to load a license file:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Uygulama Kılavuzu

### Günlük Yineleme ve İstisnalarla Outlook calendar java Oluşturma

#### Genel Bakış
Bu özellik, yineleyen randevuları otomatikleştirmenizi sağlar ve aynı zamanda belirli örnekleri atlamanıza veya değiştirmenize olanak tanır.

#### Adım‑Adım Uygulama

**1. Etkinlik Başlangıç Tarihini Ayarla**  
Serinin ne zaman başlayacağını belirleyin:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI Takvim Nesnesini Oluştur**  
Konum, konu ve açıklamayı sağlayın:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Günlük Yineleme Deseni Tanımla**  
Etkinliği her gün tekrarlanacak şekilde yapılandırın:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Yinelemeye Bir İstisna Ekle**  
Hariç tutulması (veya değiştirilmesi) gereken bir tarihi belirtin:

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Takvim İstisnalarına Dosya Ekleme

#### Genel Bakış
Herhangi bir istisna örneğine destekleyici belgeler (ör. gündemler) ekleyebilirsiniz.

**1. Dosya Oluştur ve Ekle**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Outlook calendar java'yı PST'ye Kaydetme (save calendar to pst)

#### Genel Bakış
Takvimi bir PST dosyasına kaydedin, böylece Outlook veya diğer istemciler okuyabilir.

**1. Takvimi Oluştur ve PST'ye Kaydet**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Pratik Uygulamalar
- **Corporate Scheduling** – toplantı serilerini otomatikleştirin, tatilleri otomatik olarak atlayın.  
- **Project Management** – ara sıra tarih değişiklikleriyle yineleyen kilometre taşlarını izleyin.  
- **Event Planning** – bazı oturumların iptal edildiği veya yeniden planlandığı çok günlük konferansları yönetin.

### Entegrasyon Olanakları
Aspose.Email'i CRM platformları, görev‑yönetimi API'leri veya özel iş akışı motorlarıyla birleştirerek uçtan uca otomasyonu sağlayın.

## Performans Düşünceleri
- **Dispose Resources** – dosya tutamaçlarını serbest bırakmak için `PersonalStorage` üzerinde her zaman `dispose()` çağırın.  
- **Stream Usage** – tüm PST'yi belleğe yüklemekten kaçınmak için `ByteArrayOutputStream` veya dosya akışlarını tercih edin.  
- **Async Operations** – toplu takvim oluşturma için, UI'nın yanıt vermesini sağlamak amacıyla oluşturma mantığını arka plan iş parçacığında çalıştırın.

## Sonuç
Bu kılavuzu izleyerek artık günlük yineleme ile **create outlook calendar java** nesnelerini nasıl oluşturacağınızı, istisnalar ekleyeceğinizi, dosya ekleyeceğinizi ve **save calendar to PST** yapacağınızı biliyorsunuz. Bu yetenekler, Outlook'a doğrudan dokunmadan sağlam zamanlama özellikleri oluşturmanıza olanak tanır.

### Sonraki Adımlar
- Haftalık veya aylık yineleme desenleriyle deney yapın.  
- Katılımcılar, hatırlatıcılar ve kategoriler gibi ek MAPI özelliklerini keşfedin.  
- Daha gelişmiş senaryolar için Aspose.Email'in kapsamlı API belgelerini inceleyin.

## Sıkça Sorulan Sorular

**Q: Kütüphane zaman dilimi duyarlı randevuları destekliyor mu?**  
A: Evet, `MapiCalendar` üzerinde `StartTimeZone` ve `EndTimeZone` özelliklerini ayarlayabilirsiniz.

**Q: Tekrarlayan bir seriden tek bir oluşumu programlı olarak silebilir miyim?**  
A: Yineleme desenindeki `DeletedInstanceDates` koleksiyonunu kullanarak belirli tarihleri kaldırılmış olarak işaretleyin.

**Q: Aspose.Email ile oluşturulan bir PST dosyasının boyutu konusunda sınırlamalar var mı?**  
A: PST dosyaları Unicode format limitlerine (varsayılan olarak 2 GB'a kadar) uyar, ancak `PersonalStorage` ayarlarıyla daha büyük boyutlar yapılandırabilirsiniz.

**Q: Bir toplantı isteğine katılımcı nasıl eklenir?**  
A: `MapiRecipient` nesneleri oluşturun, `RecipientType`'ını `MapiRecipientType.MAPI_TO` olarak ayarlayın ve `MapiMessage`'ın `Recipients` koleksiyonuna ekleyin.

**Q: Yineleyen görevler (sadece randevular değil) için destek var mı?**  
A: Evet, Aspose.Email benzer yineleme yeteneklerine sahip `MapiTask` da sağlar.

**Q: Bu kılavuzu bir aspose email tutorial java serisinin parçası olarak kullanabilir miyim?**  
A: Kesinlikle – burada gösterilen adımlar, takvim oluşturma ile ilgili herhangi bir Aspose.Email Java öğreticisinin temel bir parçasıdır.

## Kaynaklar
- [Aspose.Email for Java Belgeleri](https://reference.aspose.com/email/java/)
- [Aspose.Email'i İndir](https://releases.aspose.com/email/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.aspose.com/email/java/)
- [Geçici Lisans Talep Et](https://purchase.aspose.com/temporary-license/)
- [Aspose Destek Forumu](https://forum.aspose.com/c/email/10)

---

**Son Güncelleme:** 2026-03-20  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}