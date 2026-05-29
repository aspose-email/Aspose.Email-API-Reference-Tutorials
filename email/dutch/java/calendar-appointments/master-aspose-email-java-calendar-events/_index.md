---
date: '2026-02-24'
description: Leer hoe u agenda exporteert naar PST met Aspose.Email voor Java, inclusief
  hoe u deelnemers toevoegt, start- en einddatums instelt en afspraken efficiënt beheert.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Agenda exporteren naar PST met Aspose.Email voor Java
url: /nl/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export kalender naar PST met Aspose.Email voor Java

Als je een Java‑applicatie bouwt die planningsgegevens moet delen met Outlook, moet je vaak **export calendar to PST**. In deze tutorial lopen we alles door wat je nodig hebt — van het maken van een eenvoudige afspraak tot het toevoegen van deelnemers en uiteindelijk het schrijven van de gebeurtenissen naar een PST‑bestand, allemaal met Aspose.Email voor Java.

## Snelle antwoorden
- **Wat is het primaire doel?** Export calendar events to a PST file.  
- **Welke bibliotheek is vereist?** Aspose.Email for Java (v25.4+).  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Email‑licentie verwijdert evaluatielimieten.  
- **Kan ik deelnemers toevoegen?** Absoluut – gebruik `MapiRecipientCollection`.  
- **Welke Java‑versie wordt ondersteund?** JDK 16 of hoger.

## Wat is **export calendar to pst**?
Een kalender exporteren naar PST betekent dat in‑memory `MapiCalendar`‑objecten worden geconverteerd naar een Microsoft Outlook Personal Storage Table (PST). Het resulterende bestand kan direct in Outlook worden geopend, gedeeld met collega's, of geïmporteerd in elk systeem dat het PST‑formaat begrijpt.

## Waarom Aspose.Email voor Java gebruiken om een kalender naar PST te exporteren?
- **Full MAPI support** – maak, wijzig en sla afspraken op zonder dat Outlook geïnstalleerd hoeft te zijn.  
- **Cross‑platform** – werkt op Windows, Linux en macOS.  
- **Rich API** – beheer deelnemers, terugkerende afspraken, herinneringen en meer.  
- **Performance‑optimized** – verwerk grote hoeveelheden gebeurtenissen met een lage geheugengebruik.

## Vereisten
- **Libraries & Dependencies**: Aspose.Email for Java versie 25.4 of later.  
- **Environment**: JDK 16 of hoger, Maven voor afhankelijkheidsbeheer.  
- **Knowledge**: Basis Java‑programmering en bekendheid met Maven.

## Hoe Aspose.Email voor Java in te stellen
Voeg de Aspose.Email‑afhankelijkheid toe aan je `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie
Ontgrendel de volledige functionaliteit van Aspose.Email zonder evaluatielimieten door een licentie aan te schaffen:

1. **Free Trial**: Bezoek de [Aspose download page](https://releases.aspose.com/email/java/) voor een tijdelijke licentie.  
2. **Temporary License**: Vraag aan via de [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Overweeg aankoop via [Aspose's purchase portal](https://purchase.aspose.com/buy) voor langdurig gebruik.

Zodra je je licentie hebt, initialiseert je deze in je applicatie om alle functies in te schakelen.

## Hoe **create appointment** (Create Calendar Event Java)

### Stap 1: Definieer start‑ en einddatums (java calendar start date / java calendar end date)
De volgende methode toont hoe je de start‑ en einddatums voor een afspraak instelt en een `MapiCalendar`‑object retourneert:

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

*Uitleg*: Deze code maakt een `MapiCalendar` met een specifieke locatie, onderwerp, beschrijving, en de **java calendar start date** / **java calendar end date** die je hebt gedefinieerd.

## Hoe **add attendees** (java add meeting attendees)

### Stap 2: Bouw de deelnemerslijst
Gebruik `MapiRecipientCollection` om op te geven wie de vergaderuitnodiging moet ontvangen:

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

*Uitleg*: Deze code maakt een vergadering, stelt de organisator in, en voegt de **java add meeting attendees**‑lijst toe zodat iedereen een juiste uitnodiging ontvangt.

## Hoe **export calendar to pst** (Create PST with calendar events)

### Stap 3: Maak een PST‑bestand en voeg de gebeurtenissen toe
De onderstaande methode toont het maken van een Unicode PST‑bestand en het opslaan van zowel de eenvoudige afspraak als de vergadering met deelnemers:

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

*Uitleg*: Deze code **exports calendar to PST** door een PST‑container te maken, een vooraf gedefinieerde "Calendar"‑map toe te voegen, en de eerder gebouwde `MapiCalendar`‑objecten in te voegen.

## Praktische toepassingen
- **Business Scheduling** – Automatiseer interne vergadercreatie en distributie.  
- **Event Management** – Volg conferenties, workshops en deelnemerslijsten.  
- **CRM Integration** – Synchroniseer afspraken met klantrelatie‑tools.  
- **Project Planning** – Sla projectmijlpalen op als kalenderitems.  
- **Remote Team Collaboration** – Genereer PST‑bestanden voor offline delen.

## Prestatie‑overwegingen
- **Dispose objects** die je niet meer nodig hebt om geheugen vrij te maken.  
- **Choose efficient collections** voor grote deelnemerslijsten.  
- **Cache frequently accessed events** als je de PST herhaaldelijk opvraagt.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **PST file not created** | Controleer de schrijfrechten op de doelmap en zorg ervoor dat het mappad bestaat. |
| **Attendees not receiving invitations** | Bevestig dat elke `MapiRecipient` `MapiRecipientType.MAPI_TO` gebruikt en dat het e‑mailadres van de organisator geldig is. |
| **Date mismatch** | Gebruik `Calendar` consistent voor start‑/einddatums; vermijd het mengen van `java.util.Date` met andere datum‑bibliotheken zonder conversie. |

## Veelgestelde vragen

**Q: Hoe begin ik met Aspose.Email voor Java?**  
A: Voeg de Maven‑afhankelijkheid toe die hierboven wordt getoond, verkrijg een licentie, en volg de stappen in deze gids om kalendergebeurtenissen te maken en te exporteren.

**Q: Kan ik de PST‑bestandsnaam en -locatie aanpassen?**  
A: Ja, wijzig de `pstFilePath`‑variabele in `createPSTWithCalendarEvents()` naar een geldig pad op je systeem.

**Q: Is het mogelijk om terugkeerpatronen aan afspraken toe te voegen?**  
A: Absoluut – `MapiCalendar` biedt terugkeer‑eigenschappen zoals `RecurrencePattern` die je kunt configureren vóór het opslaan.

**Q: Ondersteunt Aspose.Email andere kalenderformaten naast PST?**  
A: Ja, je kunt exporteren naar iCalendar (`.ics`) en andere formaten met behulp van de juiste API‑methoden.

**Q: Wat is de maximale grootte van een PST‑bestand dat ik kan maken?**  
A: Met het Unicode‑formaat (`FileFormatVersion.Unicode`) kunnen PST‑bestanden groeien tot 2 TB, alleen beperkt door beschikbare schijfruimte.

---

**Laatst bijgewerkt:** 2026-02-24  
**Getest met:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}