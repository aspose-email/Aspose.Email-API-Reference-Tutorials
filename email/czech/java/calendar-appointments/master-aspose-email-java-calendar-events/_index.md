---
date: '2026-08-01'
description: Zjistěte, jak exportovat kalendář do PST pomocí Aspose.Email for Java,
  včetně toho, jak přidat attendees, nastavit start and end dates a efektivně manage
  appointments.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Export kalendáře do PST pomocí Aspose.Email for Java. Zjistěte krok
  za krokem, jak vytvořit appointments, přidat attendees a generate Outlook PST files.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Export kalendáře do PST – Kompletní průvodce s Aspose.Email for Java
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
title: Export kalendáře do PST s Aspose.Email for Java
url: /cs/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export kalendáře do PST pomocí Aspose.Email pro Java

Pokud vytváříte Java aplikaci, která potřebuje sdílet plánovací data s Outlookem, často budete potřebovat **exportovat kalendář do PST**. V tomto tutoriálu vás provedeme vším, co potřebujete – od vytvoření jednoduché schůzky po přidání účastníků a nakonec zápis událostí do souboru PST, vše pomocí Aspose.Email pro Java. Na konci budete mít řešení připravené do produkce, které funguje na Windows, Linuxu i macOS.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Exportovat události kalendáře do souboru PST.  
- **Která knihovna je vyžadována?** Aspose.Email pro Java (v25.4+).  
- **Potřebuji licenci?** Ano, platná licence Aspose.Email odstraňuje omezení hodnocení.  
- **Mohu přidávat účastníky?** Rozhodně – použijte `MapiRecipientCollection`.  
- **Jaká verze Javy je podporována?** JDK 16 nebo vyšší.

## Co je **export kalendáře do pst**?
`MapiCalendar` je třída Aspose.Email, která modeluje položku kalendáře Outlook, včetně předmětu, místa a časových údajů.

Export kalendáře do PST znamená převod objektů `MapiCalendar` v paměti do Microsoft Outlook Personal Storage Table (PST). Vygenerovaný soubor PST lze otevřít přímo v Outlooku, sdílet s kolegy nebo importovat do libovolného systému, který rozumí formátu PST, přičemž zachovává všechny podrobnosti událostí, jako jsou účastníci, opakování a připomenutí.

## Proč použít Aspose.Email pro Java k exportu kalendáře do PST?
Můžete vygenerovat plně kompatibilní soubor PST bez instalace Outlooku. Aspose.Email poskytuje **plnou podporu MAPI**, funguje na **všech hlavních operačních systémech** a dokáže zpracovat **až 2 TB** dat ve formátu Unicode PST – dostatečné pro archivaci v podnikovém měřítku. API vám také umožňuje spravovat účastníky, vzory opakování, připomenutí a vlastní vlastnosti pomocí několika volání metod, což dramaticky snižuje vývojové úsilí.

## Požadavky
- **Knihovny a závislosti**: Aspose.Email pro Java verze 25.4 nebo novější.  
- **Prostředí**: JDK 16 nebo vyšší, Maven pro správu závislostí.  
- **Znalosti**: Základní programování v Javě a znalost Maven.

## Jak nastavit Aspose.Email pro Java
Přidejte závislost Aspose.Email do svého `pom.xml` a obnovte svůj Maven projekt. Tento jediný krok zpřístupní celé MAPI API na vaší classpath.

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

### Získání licence
Odblokujte plnou funkčnost Aspose.Email bez omezení hodnocení získáním licence:

1. **Free Trial**: Navštivte [Aspose download page](https://releases.aspose.com/email/java/) pro dočasnou licenci.  
2. **Temporary License**: Požádejte přes [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Zvažte nákup na [Aspose's purchase portal](https://purchase.aspose.com/buy) pro dlouhodobé použití.

Jakmile máte licenci, inicializujte ji ve své aplikaci, aby byly povoleny všechny funkce.

## Jak **vytvořit schůzku** (Create Calendar Event Java)

Načtěte objekt `MapiCalendar`, nastavte jeho základní vlastnosti a vraťte jej připravený k dalšímu zpracování. Tato metoda vytvoří položku kalendáře s předmětem, místem, popisem a **java kalendářním datem začátku** / **java kalendářním datem konce**, které jste definovali.

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

*Vysvětlení*: Třída `MapiCalendar` je reprezentací položky kalendáře Outlook v Aspose.Email. Po nastavení základních polí můžete také nakonfigurovat opakování, připomenutí a kategorie před uložením.

## Jak **přidat účastníky** (java add meeting attendees)

Vytvořte `MapiRecipientCollection`, naplňte jej každým účastníkem a připojte jej k schůzce. Tím zajistíte, že každý účastník obdrží řádnou pozvánku při otevření PST.

`MapiRecipientCollection` je třída kolekce, která obsahuje objekty `MapiRecipient` představující účastníky schůzky. `MapiRecipient` představuje jednotlivého účastníka s vlastnostmi jako e‑mailová adresa a typ příjemce.

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

*Vysvětlení*: `MapiRecipient` definuje jednoho účastníka schůzky. Nastavením typu na `MAPI_TO` označíte adresu jako hlavního účastníka, zatímco `MAPI_CC` nebo `MAPI_BCC` lze použít pro volitelné účastníky.

## Jak **exportovat kalendář do pst** (Create PST with calendar events)

Vytvořte Unicode PST soubor, přidejte složku „Calendar“ a vložte dříve vytvořené objekty `MapiCalendar`. PST pak může být otevřen v Outlooku nebo distribuován koncovým uživatelům.

`PersonalStorage` je třída Aspose.Email používaná k vytváření, otevírání a manipulaci se soubory PST.

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

*Vysvětlení*: `PersonalStorage` je vstupní bod pro manipulaci s PST. Použitím Unicode formátu se vyhnete limitu 2 GB starších verzí PST a získáte výhodu rychlejšího I/O u velkých archivů.

## Praktické aplikace
1. **Obchodní plánování** – Automatizujte vytváření a distribuci interních schůzek.  
2. **Řízení akcí** – Sledujte konference, workshopy a seznamy účastníků.  
3. **Integrace CRM** – Synchronizujte schůzky s nástroji pro řízení vztahů se zákazníky.  
4. **Projektové plánování** – Ukládejte milníky projektu jako položky kalendáře.  
5. **Spolupráce vzdálených týmů** – Generujte PST soubory pro offline sdílení.

## Úvahy o výkonu
- **Uvolňujte objekty**, které již nepotřebujete, aby se rychle uvolnila paměť.  
- **Používejte efektivní kolekce** (např. `ArrayList` pro seznamy účastníků) při zpracování tisíců účastníků.  
- **Ukládejte do mezipaměti často přistupované události**, pokud PST dotazujete opakovaně, čímž snížíte diskové I/O.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Soubor PST nebyl vytvořen** | Ověřte oprávnění k zápisu do cílového adresáře a ujistěte se, že cesta ke složce existuje. |
| **Účastníci nedostávají pozvánky** | Potvrďte, že každý `MapiRecipient` používá `MapiRecipientType.MAPI_TO` a že e‑mail organizátora je platný. |
| **Neshoda dat** | Používejte `Calendar` konzistentně pro data začátku/konce; vyhněte se míchání `java.util.Date` s jinými knihovnami datumů bez konverze. |

## Často kladené otázky

**Q:** Jak začít s Aspose.Email pro Java?  
**A:** Přidejte Maven závislost uvedenou výše, získejte licenci a postupujte podle kroků v tomto průvodci k vytvoření a exportu kalendářních událostí.

**Q:** Mohu přizpůsobit název a umístění souboru PST?  
**A:** Ano, změňte proměnnou `pstFilePath` v metodě `createPSTWithCalendarEvents()` na libovolnou platnou cestu ve vašem systému.

**Q:** Je možné přidat vzory opakování k schůzkám?  
**A:** Rozhodně – `MapiCalendar` poskytuje vlastnost `RecurrencePattern`, kterou můžete před uložením nakonfigurovat.

**Q:** Podporuje Aspose.Email jiné formáty kalendářů kromě PST?  
**A:** Ano, můžete exportovat do iCalendar (`.ics`) a dalších formátů pomocí příslušných metod API.

**Q:** Jaká je maximální velikost PST souboru, který mohu vytvořit?  
**A:** Ve formátu Unicode (`FileFormatVersion.Unicode`) mohou soubory PST růst až do 2 TB, omezeno pouze dostupným místem na disku.

---

**Poslední aktualizace:** 2026-08-01  
**Testováno s:** Aspose.Email pro Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Ovládněte Aspose.Email pro Java: Efektivně spravujte Outlook PST soubory](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Ovládněte vytváření a ukládání položek kalendáře s Aspose.Email pro Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Jak číst více kalendářních událostí z souboru ICS pomocí Aspose.Email v Javě](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}