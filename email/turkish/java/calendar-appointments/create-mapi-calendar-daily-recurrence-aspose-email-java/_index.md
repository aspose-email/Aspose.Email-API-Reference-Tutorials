---
date: '2025-12-20'
description: Aspose.Email for Java kullanarak MAPI takvim Java'sını nasıl oluşturacağınızı,
  günlük yineleme desenlerini nasıl yöneteceğinizi ve istisnaları nasıl ele alacağınızı
  öğrenin.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Java ile günlük tekrarlama ve istisnalar içeren MAPI takvimi oluştur
url: /tr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# MAPI takvim java nesnesini günlük yineleme ve istisnalarla nasıl oluşturulur

Yineleyen etkinlikleri verimli bir şekilde yönetmek zor olabilir, özellikle istisnalar veya değişiklikler gerektiğinde. Bu öğreticide **create mapi calendar java** nesnelerini oluşturacak, günlük yineleme desenlerini ayarlayacak ve Aspose.Email for Java kullanarak istisnalar ekleyeceksiniz. Uygulamalarınız içinde zamanlama görevlerini sorunsuz bir şekilde otomatikleştirmeyi öğreneceksiniz.

## Quick Answers
- **Hangi kütüphane?** Aspose.Email for Java  
- **Ana görev?** Create a MAPI calendar with daily recurrence and exceptions  
- **Gereken JDK?** Java 16 or higher  
- **İstisnalara dosya ekleyebilir miyim?** Yes, using `MapiCalendarExceptionInfo`  
- **Takvim nerede depolanıyor?** In a PST file via `PersonalStorage`

### MAPI takvimi nedir?
MAPI (Messaging Application Programming Interface) takvimi, Microsoft Outlook ve diğer e-posta istemcileri tarafından randevu verilerini depolamak için kullanılan standart bir formattır. Zengin yineleme kuralları, istisnalar ve ekleri destekler, bu da kurumsal zamanlama için ideal kılar.

### Aspose.Email for Java neden kullanılmalı?
Aspose.Email, Outlook'a bağımlı olmadan MAPI nesnelerini oluşturmanıza, değiştirmenize ve kaydetmenize olanak tanıyan saf Java API'si sağlar. Bu, sunucu tarafı zamanlama özellikleri oluşturmanızı, PST dosyaları üretmenizi ve karmaşık yineleme senaryolarını programlı olarak yönetmenizi sağlar.

## Önkoşullar

Başlamadan önce, aşağıdaki kurulumun yapıldığından emin olun:
- **Aspose.Email Kütüphanesi**: Version 25.4 (or later) – Maven veya doğrudan indirme yoluyla kullanılabilir.  
- **Java Development Kit (JDK)**: JDK 16 veya daha yeni.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans veya herhangi bir Java‑uyumlu editör.

### Gerekli Kütüphaneler ve Bağımlılıklar

Aspose.Email'i projenize Maven ile entegre etmek için `pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Edinimi

Aspose.Email'i kullanmak için bir lisansa ihtiyacınız olacak:
- **Free Trial** – tüm özellikleri ücretsiz olarak keşfedin.  
- **Temporary License** – genişletilmiş değerlendirme için talep edin.  
- **Full License** – üretim dağıtımları için satın alın.

## Aspose.Email for Java Kurulumu

İlk olarak, ortamınızı kurun:

1. JDK 16'nın kurulu olduğunu ve `JAVA_HOME`'un yapılandırıldığını doğrulayın.  
2. Maven bağımlılığını (veya JAR'ı) projenize ekleyin.  

Lisans dosyasını nasıl yükleyeceğinizi gösteren küçük bir kod parçacığı:

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

### Günlük Yineleme ve İstisnalarla MAPI Takvim Oluşturma

#### Genel Bakış
Bu özellik, belirli örnekleri atlayabilmenizi veya değiştirebilmenizi sağlarken yineleyen randevuları otomatikleştirmenize olanak tanır.

#### Adım‑Adım Uygulama

**1. Etkinlik Başlangıç Tarihini Ayarlayın**  
Serinin ne zaman başlayacağını belirleyin:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI Takvim Nesnesini Oluşturun**  
Konum, konu ve açıklamayı sağlayın:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Günlük Yineleme Deseni Tanımlayın**  
Etkinliği her gün tekrarlayacak şekilde yapılandırın:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Yinelemeye Bir İstisna Ekleyin**  
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

**1. Dosya Oluşturun ve Ekleyin**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### MAPI Takvimi PST Dosyalarına Kaydetme

#### Genel Bakış
Takvimi bir PST dosyasına kalıcı olarak kaydedin, böylece Outlook veya diğer istemciler okuyabilir.

**1. Takvimi Oluşturun ve PST'ye Kaydedin**

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
- **Project Management** – ara sıra tarih kaymalarıyla yineleyen kilometre taşlarını izleyin.  
- **Event Planning** – bazı oturumların iptal edildiği veya yeniden planlandığı çok günlük konferansları yönetin.

### Entegrasyon Olanakları
Aspose.Email'i CRM platformları, görev‑yönetimi API'leri veya özel iş akışı motorlarıyla birleştirerek uçtan uca otomasyonu sağlayabilirsiniz.

## Performans Düşünceleri
- **Dispose Resources** – dosya tutamaçlarını serbest bırakmak için `PersonalStorage` üzerinde her zaman `dispose()` çağırın.  
- **Stream Usage** – tüm PST'leri belleğe yüklemekten kaçınmak için `ByteArrayOutputStream` veya dosya akışlarını tercih edin.  
- **Async Operations** – toplu takvim oluşturma için, UI'nin yanıt vermesini sağlamak amacıyla oluşturma mantığını arka plan iş parçacığında çalıştırın.

## Sonuç
Bu kılavuzu izleyerek artık günlük yineleme ile **create mapi calendar java** nesnelerini nasıl oluşturacağınızı, istisnalar ekleyeceğinizi, dosya ekleyeceğinizi ve her şeyi bir PST dosyasında saklayacağınızı biliyorsunuz. Bu yetenekler, Outlook'a doğrudan dokunmadan sağlam zamanlama özellikleri oluşturmanıza olanak tanır.

### Sonraki Adımlar
- Haftalık veya aylık yineleme desenleriyle deney yapın.  
- Katılımcılar, hatırlatıcılar ve kategoriler gibi ek MAPI özelliklerini keşfedin.  
- Daha gelişmiş senaryolar için Aspose.Email'in kapsamlı API belgelerini inceleyin.

## Sık Sorulan Sorular

**S: Kütüphane saat‑dilimi farkında randevuları destekliyor mu?**  
C: Evet, `MapiCalendar` üzerindeki `StartTimeZone` ve `EndTimeZone` özelliklerini ayarlayabilirsiniz.

**S: Yineleyen bir seriden tek bir örneği programlı olarak silebilir miyim?**  
C: Tek tek tarihleri kaldırmak için yineleme desenindeki `DeletedInstanceDates` koleksiyonunu kullanın.

**S: Aspose.Email ile oluşturulan PST dosyasının boyutu için sınırlamalar var mı?**  
C: PST dosyaları Unicode format limitlerine (varsayılan olarak 2 GB) uyar, ancak `PersonalStorage` ayarlarıyla daha büyük boyutlar yapılandırılabilir.

**S: Toplantı isteğine katılımcı eklemek nasıl yapılır?**  
C: `MapiRecipient` nesneleri oluşturun, `RecipientType` özelliğini `MapiRecipientType.MAPI_TO` olarak ayarlayın ve `MapiMessage`'in `Recipients` koleksiyonuna ekleyin.

**S: Yineleyen görevler (sadece randevular değil) için destek var mı?**  
C: Evet, Aspose.Email benzer özelliklere sahip `MapiTask` da sağlar.

## Resources
- [Aspose.Email for Java Belgeleri](https://reference.aspose.com/email/java/)
- [Aspose.Email'i İndir](https://releases.aspose.com/email/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.aspose.com/email/java/)
- [Geçici Lisans Talep Et](https://purchase.aspose.com/temporary-license/)
- [Aspose Destek Forumu](https://forum.aspose.com/c/email/10)

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
