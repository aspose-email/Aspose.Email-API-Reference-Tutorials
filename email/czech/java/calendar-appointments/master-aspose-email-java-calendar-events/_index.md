---
date: '2026-02-24'
description: Naučte se, jak exportovat kalendář do PST pomocí Aspose.Email pro Javu,
  včetně toho, jak přidat účastníky, nastavit počáteční a koncové datum a čas a efektivně
  spravovat schůzky.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Export kalendáře do PST pomocí Aspose.Email pro Javu
url: /cs/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export kalendáře do PST pomocí Aspose.Email pro Java

Pokud vytváříte Java aplikaci, která potřebuje sdílet plánovací data s Outlookem, často budete potřebovat **exportovat kalendář do PST**. V tomto tutoriálu projdeme vše, co potřebujete – od vytvoření jednoduché schůzky po přidání účastníků a nakonec zápis událostí do souboru PST, vše pomocí Aspose.Email pro Java.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Exportovat události kalendáře do souboru PST.  
- **Která knihovna je vyžadována?** Aspose.Email for Java (v25.4+).  
- **Potřebuji licenci?** Ano, platná licence Aspose.Email odstraňuje omezení hodnocení.  
- **Mohu přidat účastníky?** Rozhodně – použijte `MapiRecipientCollection`.  
- **Jaká verze Javy je podporována?** JDK 16 nebo vyšší.

## Co je **export calendar to pst**?
Export kalendáře do PST znamená převod objektů `MapiCalendar` v paměti do Microsoft Outlook Personal Storage Table (PST). Výsledný soubor lze otevřít přímo v Outlooku, sdílet s kolegy nebo importovat do libovolného systému, který rozumí formátu PST.

## Proč použít Aspose.Email pro Java k exportu kalendáře do PST?
- **Full MAPI support** – vytvářejte, upravujte a ukládejte schůzky bez nutnosti mít nainstalovaný Outlook.  
- **Cross‑platform** – funguje na Windows, Linuxu a macOS.  
- **Rich API** – spravujte účastníky, opakování, připomenutí a další.  
- **Performance‑optimized** – zpracovávejte velké objemy událostí s nízkou spotřebou paměti.

## Požadavky
- **Libraries & Dependencies**: Aspose.Email for Java verze 25.4 nebo novější.  
- **Environment**: JDK 16 nebo vyšší, Maven pro správu závislostí.  
- **Knowledge**: Základní programování v Javě a znalost Maven.

## Jak nastavit Aspose.Email pro Java
Add the Aspose.Email dependency to your `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
Unlock full functionality of Aspose.Email without evaluation limitations by acquiring a license:

1. **Free Trial**: Navštivte [Aspose download page](https://releases.aspose.com/email/java/) pro dočasnou licenci.  
2. **Temporary License**: Požádejte prostřednictvím [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Zvažte nákup na [Aspose's purchase portal](https://purchase.aspose.com/buy) pro dlouhodobé použití.

Jakmile máte licenci, inicializujte ji ve své aplikaci, aby byly povoleny všechny funkce.

## Jak **vytvořit schůzku** (Create Calendar Event Java)

### Krok 1: Definujte počáteční a koncová data (java calendar start date / java calendar end date)
The following method shows how to set the start and end dates for an appointment and return a `MapiCalendar` object:

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

*Explanation*: Tento úryvek vytváří `MapiCalendar` s konkrétním místem, předmětem, popisem a **java calendar start date** / **java calendar end date**, které jste definovali.

## Jak **přidat účastníky** (java add meeting attendees)

### Krok 2: Sestavte seznam účastníků
Use `MapiRecipientCollection` to specify who should receive the meeting invitation:

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

*Explanation*: Tento kód vytváří schůzku, nastavuje organizátora a připojuje seznam **java add meeting attendees**, aby všichni obdrželi řádnou pozvánku.

## Jak **exportovat kalendář do pst** (Create PST with calendar events)

### Krok 3: Vytvořte soubor PST a přidejte události
The method below demonstrates creating a Unicode PST file and storing both the simple appointment and the meeting with attendees:

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

*Explanation*: Tento úryvek **exports calendar to PST** vytvořením PST kontejneru, přidáním předdefinované složky „Calendar“ a vložením dříve vytvořených objektů `MapiCalendar`.

## Praktické aplikace
1. **Business Scheduling** – Automatizujte vytváření a distribuci interních schůzek.  
2. **Event Management** – Sledujte konference, workshopy a seznamy účastníků.  
3. **CRM Integration** – Synchronizujte schůzky s nástroji pro řízení vztahů se zákazníky.  
4. **Project Planning** – Ukládejte milníky projektů jako položky kalendáře.  
5. **Remote Team Collaboration** – Generujte soubory PST pro offline sdílení.

## Úvahy o výkonu
- **Dispose objects** objekty, které již nepotřebujete, aby se uvolnila paměť.  
- **Choose efficient collections** vyberte efektivní kolekce pro velké seznamy účastníků.  
- **Cache frequently accessed events** kešujte často přistupované události, pokud opakovaně dotazujete PST.

## Časté problémy a řešení
| Issue | Solution |
|-------|----------|
| **PST file nebyl vytvořen** | Ověřte oprávnění k zápisu do cílového adresáře a ujistěte se, že cesta ke složce existuje. |
| **Účastníci nedostávají pozvánky** | Potvrďte, že každý `MapiRecipient` používá `MapiRecipientType.MAPI_TO` a že e‑mail organizátora je platný. |
| **Neshoda dat** | Používejte `Calendar` konzistentně pro počáteční a koncová data; vyhněte se míchání `java.util.Date` s jinými knihovnami dat bez konverze. |

## Často kladené otázky

**Q: Jak začít s Aspose.Email pro Java?**  
A: Přidejte Maven závislost uvedenou výše, získejte licenci a postupujte podle kroků v tomto průvodci k vytvoření a exportu kalendářních událostí.

**Q: Mohu přizpůsobit název a umístění souboru PST?**  
A: Ano, změňte proměnnou `pstFilePath` ve funkci `createPSTWithCalendarEvents()` na libovolnou platnou cestu ve vašem systému.

**Q: Je možné přidat opakování k schůzkám?**  
A: Rozhodně – `MapiCalendar` poskytuje vlastnosti opakování jako `RecurrencePattern`, které můžete před uložením nakonfigurovat.

**Q: Podporuje Aspose.Email jiné formáty kalendářů kromě PST?**  
A: Ano, můžete exportovat do iCalendar (`.ics`) a dalších formátů pomocí odpovídajících metod API.

**Q: Jaká je maximální velikost PST souboru, který mohu vytvořit?**  
A: Při použití Unicode formátu (`FileFormatVersion.Unicode`) mohou soubory PST růst až do 2 TB, omezeno pouze dostupným místem na disku.

---

**Poslední aktualizace:** 2026-02-24  
**Testováno s:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}