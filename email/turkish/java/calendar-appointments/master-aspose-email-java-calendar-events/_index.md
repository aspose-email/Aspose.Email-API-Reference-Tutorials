---
date: '2026-08-01'
description: Aspose.Email for Java ile takvimi PST'ye nasıl dışa aktaracağınızı öğrenin;
  katılımcı ekleme, başlangıç ve bitiş tarihlerini ayarlama ve randevuları verimli
  bir şekilde yönetme konularını içerir.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Aspose.Email for Java kullanarak takvimi PST'ye dışa aktarın. Randevu
  oluşturma, katılımcı ekleme ve Outlook PST dosyaları üretme adımlarını adım adım
  öğrenin.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Takvimi PST'ye Dışa Aktarma – Aspose.Email for Java ile Tam Kılavuz
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Aspose.Email for Java ile takvimi PST'ye dışa aktar
url: /tr/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java ile takvimi PST'ye dışa aktar

Java uygulaması geliştiriyor ve Outlook ile takvim verilerini paylaşmanız gerekiyorsa, genellikle **takvimi PST'ye dışa aktarmanız** gerekir. Bu öğreticide ihtiyacınız olan her şeyi adım adım göstereceğiz—basit bir randevu oluşturulmasından katılımcı eklemeye ve sonunda olayları bir PST dosyasına yazmaya kadar, tümü Aspose.Email for Java ile. Sonunda Windows, Linux ve macOS'ta çalışan üretim‑hazır bir çözümünüz olacak.

## Hızlı Yanıtlar
- **Birincil hedef nedir?** Takvim olaylarını bir PST dosyasına dışa aktarmak.  
- **Hangi kütüphane gereklidir?** Aspose.Email for Java (v25.4+).  
- **Lisans gereklimi?** Evet, geçerli bir Aspose.Email lisansı değerlendirme sınırlamalarını kaldırır.  
- **Katılımcı ekleyebilir miyim?** Kesinlikle – `MapiRecipientCollection` kullanın.  
- **Hangi Java sürümü destekleniyor?** JDK 16 veya üzeri.

## **export calendar to pst** nedir?
`MapiCalendar`, Aspose.Email'in Outlook takvim öğesini modelleyen sınıfıdır; konu, konum ve zamanlama ayrıntılarını içerir.

Takvimi PST'ye dışa aktarmak, bellekteki `MapiCalendar` nesnelerini Microsoft Outlook Personal Storage Table (PST) formatına dönüştürmek anlamına gelir. Oluşturulan PST dosyası doğrudan Outlook'ta açılabilir, meslektaşlarla paylaşılabilir veya PST formatını anlayan herhangi bir sisteme içe aktarılabilir; katılımcılar, yinelemeler ve hatırlatıcılar gibi tüm etkinlik ayrıntılarını korur.

## Aspose.Email for Java ile takvimi PST'ye dışa aktarmak için neden kullanmalı?
Outlook kurmadan tamamen uyumlu bir PST dosyası oluşturabilirsiniz. Aspose.Email **tam MAPI desteği** sunar, **tüm büyük işletim sistemlerinde** çalışır ve Unicode PST formatında **2 TB'ye kadar** veri işleyebilir—kurumsal ölçekli arşivler için yeterlidir. API ayrıca sadece birkaç metod çağrısıyla katılımcıları, yineleme desenlerini, hatırlatıcıları ve özel özellikleri yönetmenizi sağlar, geliştirme çabasını büyük ölçüde azaltır.

## Önkoşullar
- **Kütüphaneler ve Bağımlılıklar**: Aspose.Email for Java sürüm 25.4 veya üzeri.  
- **Ortam**: JDK 16 veya üzeri, bağımlılık yönetimi için Maven.  
- **Bilgi**: Temel Java programlama ve Maven'a aşinalık.

## Aspose.Email for Java nasıl kurulur
`pom.xml` dosyanıza Aspose.Email bağımlılığını ekleyin ve Maven projenizi yenileyin. Bu tek adım, tüm MAPI API'sini sınıf yolunuzda kullanılabilir hâle getirir.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Lisans Edinme
Değerlendirme sınırlamaları olmadan Aspose.Email'in tam işlevselliğini açmak için bir lisans edinin:

1. **Free Trial**: Geçici bir lisans için [Aspose indirme sayfasını](https://releases.aspose.com/email/java/) ziyaret edin.  
2. **Temporary License**: [satın alma sayfası](https://purchase.aspose.com/temporary-license/) üzerinden başvurun.  
3. **Purchase License**: Uzun vadeli kullanım için [Aspose satın alma portalından](https://purchase.aspose.com/buy) satın almayı düşünün.

Lisansınızı aldıktan sonra, tüm özellikleri etkinleştirmek için uygulamanızda başlatın.

## **create appointment** (Create Calendar Event Java) nasıl oluşturulur
`MapiCalendar` nesnesini yükleyin, temel özelliklerini ayarlayın ve daha fazla işleme hazır olarak geri döndürün. Bu yöntem, bir konu, konum, açıklama ve tanımladığınız **java calendar start date** / **java calendar end date** ile bir takvim girdisi oluşturur.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Açıklama*: `MapiCalendar` sınıfı, Aspose.Email'in Outlook takvim öğesinin temsilidir. Temel alanları ayarladıktan sonra kaydetmeden önce yineleme, hatırlatıcılar ve kategorileri de yapılandırabilirsiniz.

## **add attendees** nasıl eklenir (java toplantı katılımcılarını ekleme)
`MapiRecipientCollection` oluşturun, her katılımcı ile doldurun ve toplantıya ekleyin. Bu, PST açıldığında her katılımcının uygun bir davetiye almasını sağlar.

`MapiRecipientCollection`, toplantı katılımcılarını temsil eden `MapiRecipient` nesnelerini tutan bir koleksiyon sınıfıdır. `MapiRecipient`, e-posta adresi ve alıcı türü gibi özelliklere sahip bireysel bir katılımcıyı temsil eder.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Açıklama*: `MapiRecipient`, tek bir toplantı katılımcısını tanımlar. Türü `MAPI_TO` olarak ayarlamak adresi birincil katılımcı olarak işaretler, `MAPI_CC` veya `MAPI_BCC` ise isteğe bağlı katılımcılar için kullanılabilir.

## **export calendar to pst** nasıl dışa aktarılır (Takvim olaylarıyla PST oluşturma)
Unicode PST dosyası oluşturun, bir "Calendar" klasörü ekleyin ve önceden oluşturulmuş `MapiCalendar` nesnelerini ekleyin. PST daha sonra Outlook'ta açılabilir veya son kullanıcılara dağıtılabilir.

`PersonalStorage`, PST dosyalarını oluşturmak, açmak ve manipüle etmek için kullanılan Aspose.Email sınıfıdır.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Açıklama*: `PersonalStorage`, PST manipülasyonu için giriş noktasıdır. Unicode formatını kullanarak eski PST sürümlerinin 2 GB sınırlamasından kaçınır ve büyük arşivlerde daha hızlı I/O avantajı elde edersiniz.

## Pratik Uygulamalar
1. **Business Scheduling** – İç toplantı oluşturma ve dağıtımını otomatikleştirin.  
2. **Event Management** – Konferansları, atölyeleri ve katılımcı listelerini izleyin.  
3. **CRM Integration** – Randevuları müşteri ilişkileri araçlarıyla senkronize edin.  
4. **Project Planning** – Proje kilometre taşlarını takvim öğeleri olarak saklayın.  
5. **Remote Team Collaboration** – Çevrim dışı paylaşım için PST dosyaları oluşturun.

## Performans Düşünceleri
- **Dispose objects**: Artık ihtiyaç duymadığınız nesneleri hemen serbest bırakarak belleği temizleyin.  
- **Use efficient collections**: Binlerce katılımcı ile çalışırken (ör. katılımcı listeleri için `ArrayList`) verimli koleksiyonlar kullanın.  
- **Cache frequently accessed events**: PST'yi sık sık sorguluyorsanız, disk I/O'yu azaltmak için sık erişilen olayları önbelleğe alın.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **PST dosyası oluşturulmadı** | Hedef dizinde yazma izinlerini doğrulayın ve klasör yolunun mevcut olduğundan emin olun. |
| **Katılımcılar davetiye almıyor** | `MapiRecipient`'ın her birinin `MapiRecipientType.MAPI_TO` kullandığını ve organizatör e-posta adresinin geçerli olduğunu doğrulayın. |
| **Tarih uyumsuzluğu** | `Calendar`'ı başlangıç/bitiş tarihleri için tutarlı şekilde kullanın; `java.util.Date` ile diğer tarih kütüphanelerini dönüşüm yapmadan karıştırmayın. |

## Sıkça Sorulan Sorular

**Q: Aspose.Email for Java ile nasıl başlayabilirim?**  
A: Yukarıda gösterilen Maven bağımlılığını ekleyin, bir lisans edinin ve takvim olaylarını oluşturup dışa aktarmak için bu kılavuzdaki adımları izleyin.

**Q: PST dosyası adı ve konumunu özelleştirebilir miyim?**  
A: Evet, sisteminizde geçerli herhangi bir yola `createPSTWithCalendarEvents()` içindeki `pstFilePath` değişkenini değiştirerek ayarlayabilirsiniz.

**Q: Randevulara yineleme desenleri eklemek mümkün mü?**  
A: Kesinlikle – `MapiCalendar`, kaydetmeden önce yapılandırabileceğiniz bir `RecurrencePattern` özelliği sunar.

**Q: Aspose.Email PST dışındaki diğer takvim formatlarını destekliyor mu?**  
A: Evet, uygun API metodlarını kullanarak iCalendar (`.ics`) ve diğer formatlara dışa aktarabilirsiniz.

**Q: Oluşturabileceğim PST dosyasının maksimum boyutu nedir?**  
A: Unicode formatı (`FileFormatVersion.Unicode`) ile PST dosyaları, yalnızca mevcut disk alanı ile sınırlı olmak kaydıyla 2 TB'ye kadar büyüyebilir.

---

**Son Güncelleme:** 2026-08-01  
**Test Edilen Versiyon:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Email for Java'ı Ustalaştırın: Outlook PST Dosyalarını Verimli Yönetme](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Aspose.Email for Java ile Takvim Öğeleri Oluşturma ve Kaydetme](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose.Email kullanarak Java'da bir ICS Dosyasından Birden Çok Takvim Etkinliğini Okuma](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}