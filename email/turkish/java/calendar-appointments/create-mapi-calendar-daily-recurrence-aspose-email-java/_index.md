---
date: '2026-09-17'
description: Aspose.Email for Java kullanarak Outlook takvimini günlük yineleme ve
  istisnalarla nasıl oluşturacağınızı ve takvimi PST'ye kaydetmeyi öğrenin.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Aspose.Email kullanarak Java'da Outlook takvim oluşturun. Günlük yineleme,
  istisna yönetimi ve PST'ye kaydetme adımlarını adım adım öğrenin.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Java'da Outlook takvim oluşturma, günlük yineleme ve istisnalar
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Java ile Outlook takvim oluşturma, günlük yineleme ve istisnalar
url: /tr/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Günlük yineleme ve istisnalarla Outlook takvim java oluşturma

Yineleyen etkinlikleri verimli bir şekilde yönetmek zor olabilir, özellikle **outlook calendar java**'nın günlük yineleme desenlerini ve ara sıra ortaya çıkan istisnaları desteklemesi gerektiğinde. Bu öğreticide Outlook takvim Java nesnelerini nasıl oluşturacağınızı, günlük yinelemeyi nasıl yapılandıracağınızı, istisna örneklerini nasıl ekleyeceğinizi ve sonunda Aspose.Email for Java kullanarak **save calendar to PST** işlemini nasıl yapacağınızı öğreneceksiniz. Sonunda, herhangi bir Java tabanlı zamanlama hizmetine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı cevaplar
- **Hangi kütüphane?** Aspose.Email for Java  
- **Ana görev?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Gereken JDK?** Java 16 or higher  
- **İstisnalara dosya ekleyebilir miyim?** Yes, using `MapiCalendarExceptionInfo`  
- **Takvim nerede depolanıyor?** In a PST file via `PersonalStorage`  

## Outlook calendar java nedir?
Outlook calendar Java nesnesi, Outlook randevusunun programatik bir temsili olup, MAPI (Messaging Application Programming Interface) spesifikasyonuna dayanır ve konu, konum, başlangıç/bitiş zamanları, yineleme kuralları, katılımcılar ve ekler gibi özellikleri içerir. Bu nesne, Outlook gerektirmeden manipüle edilebilir, serileştirilebilir ve PST dosyalarına kaydedilebilir.

## Neden Aspose.Email for Java kullanmalı?
Aspose.Email for Java, Outlook kurulumuna ihtiyaç duymadan MAPI nesneleriyle çalışmanıza olanak tanır. Kütüphane **50+ MAPI özelliği** destekler, tipik randevu verileri için **2 GB**'a kadar Unicode PST dosyalarını **2 saniye** altında oluşturabilir ve Java 16+ destekleyen herhangi bir platformda çalışır. Bu saf‑Java yaklaşımı, sunucu tarafı takvim oluşturma, otomatik toplantı serileri ve yineleme mantığı üzerinde tam kontrol sağlar.

## Önkoşullar

Başlamadan önce aşağıdaki yapılandırmalara sahip olduğunuzdan emin olun:
- **Aspose.Email Kütüphanesi**: Versiyon 25.4 (veya sonrası) – Maven üzerinden veya doğrudan indirilerek temin edilebilir.  
- **Java Development Kit (JDK)**: JDK 16 veya daha yeni bir sürüm.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans veya herhangi bir Java‑uyumlu editör.

### Gerekli kütüphaneler ve bağımlılıklar

Aspose.Email'i projenize Maven ile entegre etmek için `pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans edinimi

Aspose.Email'i kullanabilmek için bir lisansa ihtiyacınız olacak:
- **Ücretsiz deneme** – tüm özellikleri ücretsiz olarak keşfedin.  
- **Geçici lisans** – uzatılmış değerlendirme için talep edin.  
- **Tam lisans** – üretim ortamları için satın alın.

## Aspose.Email for Java kurulum rehberi

İlk olarak ortamınızı hazırlayın:

1. JDK 16'nın kurulu olduğunu ve `JAVA_HOME` değişkeninin ayarlandığını doğrulayın.  
2. Maven bağımlılığını (veya JAR dosyasını) projenize ekleyin.  

Lisans dosyasını nasıl yükleyeceğinizi gösteren küçük bir kod örneği:

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

## Uygulama rehberi

### Günlük yineleme ve istisnalarla outlook calendar java oluşturma

#### Genel bakış
Bu özellik, yineleyen randevuları otomatikleştirmenize ve belirli örnekleri atlayarak ya da değiştirerek esneklik sağlar.

#### Adım‑adım uygulama

**1. Etkinlik başlangıç tarihini ayarlayın**  
Serinin ne zaman başlayacağını belirleyin:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI takvim nesnesini oluşturun**  
`MapiCalendar` sınıfı, bellekte tek bir takvim öğesini temsil eden üst‑seviye nesnedir. Konum, konu ve açıklama gibi bilgileri sağlayın:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Günlük yineleme desenini tanımlayın**  
`MapiCalendarRecurrencePattern` sınıfı, randevunun her gün tekrarlanmasını sağlayan kuralı saklar. Etkinliği her gün tekrarlayacak şekilde yapılandırın:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Yinelemeye bir istisna ekleyin**  
`MapiCalendarExceptionInfo` desenden sapma gösteren tek bir oluşumu tanımlar—ya dışlanmış ya da değiştirilmiş. Dışlanması (veya değiştirilmesi) gereken tarihi belirtin:

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

### Takvim istisnalarına dosya ekleme

#### Genel bakış
Herhangi bir istisna örneğine destekleyici belgeler (ör. gündemler) ekleyebilirsiniz.

**1. Bir dosya oluşturun ve ekleyin**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## outlook calendar java'yi PST'ye kaydetme (save calendar to pst)

#### Genel bakış
Takvimi bir PST dosyasına kalıcı olarak kaydedin, böylece Outlook veya diğer istemciler okuyabilir.

**1. Takvimi oluşturun ve PST'ye kaydedin**  
`PersonalStorage` sınıfı, yeni bir PST dosyası oluşturmak ve MAPI öğelerini eklemek için yöntemler sağlar.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Pratik uygulama alanları
- **Kurumsal zamanlama** – toplantı serilerini otomatikleştirin, tatilleri otomatik olarak atlayın.  
- **Proje yönetimi** – ara sıra tarih kaymaları olan yineleyen kilometre taşlarını izleyin.  
- **Etkinlik planlaması** – bazı oturumların iptal edildiği veya yeniden planlandığı çok‑günlü konferansları yönetin.

### Entegrasyon olanakları
Aspose.Email'i CRM platformları, görev‑yönetimi API'leri veya özel iş akışı motorlarıyla birleştirerek uçtan uca otomasyon sağlayabilirsiniz.

## Performans hususları
- **Kaynakları serbest bırakın** – dosya tutucularını serbest bırakmak için her zaman `dispose()` metodunu `PersonalStorage` üzerinde çağırın.  
- **Akış (stream) kullanımı** – tüm PST'yi belleğe yüklemekten kaçınmak için `ByteArrayOutputStream` veya dosya akışlarını tercih edin.  
- **Asenkron işlemler** – toplu takvim üretimi için oluşturma mantığını arka plan iş parçacığında çalıştırarak UI'nın yanıt vermesini sağlayın.

## Sonuç
Bu kılavuzu izleyerek **outlook calendar java** nesnelerini günlük yineleme ile nasıl oluşturacağınızı, istisnalar ekleyeceğinizi, dosya ekleyeceğinizi ve **save calendar to PST** işlemini nasıl yapacağınızı öğrendiniz. Bu yetenekler, Outlook'a hiç dokunmadan sağlam zamanlama özellikleri geliştirmenizi sağlar.

### Sonraki adımlar
- Haftalık veya aylık yineleme desenleriyle deneyler yapın.  
- Katılımcılar, hatırlatıcılar ve kategoriler gibi ek MAPI özelliklerini keşfedin.  
- Daha gelişmiş senaryolar için Aspose.Email’in kapsamlı API belgelerini inceleyin.

## Sıkça sorulan sorular

**S: Kütüphane zaman dilimi duyarlı randevuları destekliyor mu?**  
C: Evet, `MapiCalendar` üzerindeki `StartTimeZone` ve `EndTimeZone` özelliklerini ayarlayabilirsiniz.

**S: Tek bir oluşumu yineleyen bir seriden programlı olarak silebilir miyim?**  
C: Yineleme desenindeki `DeletedInstanceDates` koleksiyonunu kullanarak belirli tarihleri kaldırabilirsiniz.

**S: Aspose.Email ile oluşturulan bir PST dosyasının boyutu sınırlı mı?**  
C: PST dosyaları Unicode format limitlerine (varsayılan olarak 2 GB) uyar, ancak `PersonalStorage` ayarlarıyla daha büyük boyutlar yapılandırılabilir.

**S: Toplantı isteğine katılımcı eklemek nasıl yapılır?**  
C: `MapiRecipient` nesneleri oluşturun, `RecipientType` özelliğini `MapiRecipientType.MAPI_TO` olarak ayarlayın ve `MapiMessage`'ın `Recipients` koleksiyonuna ekleyin.

**S: Yineleyen görevler (randevular değil) destekleniyor mu?**  
C: Evet, Aspose.Email benzer yineleme yeteneklerine sahip `MapiTask` sınıfını da sunar.

**S: Bu kılavuzu Aspose.Email Java öğretici serisinin bir parçası olarak kullanabilir miyim?**  
C: Kesinlikle – burada gösterilen adımlar, takvim oluşturma ile ilgili herhangi bir Aspose.Email Java öğreticisinin temel bir parçasıdır.

## Kaynaklar
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Son güncelleme:** 2026-09-17  
**Test edildi:** Aspose.Email for Java 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Export Outlook calendar PST with Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Create Calendar Sharing Invitation with Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}