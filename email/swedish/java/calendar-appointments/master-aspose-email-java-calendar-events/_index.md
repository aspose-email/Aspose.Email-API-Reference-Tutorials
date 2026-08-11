---
date: '2026-08-01'
description: Lär dig hur du exporterar kalender till PST med Aspose.Email for Java,
  inklusive hur du lägger till deltagare, anger start- och slutdatum samt hanterar
  möten effektivt.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Exportera kalender till PST med Aspose.Email for Java. Lär dig steg
  för steg hur du skapar möten, lägger till deltagare och genererar Outlook PST-filer.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Exportera kalender till PST – Komplett guide med Aspose.Email for Java
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
title: Exportera kalender till PST med Aspose.Email for Java
url: /sv/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportera kalender till PST med Aspose.Email för Java

Om du bygger ett Java‑program som behöver dela schemaläggningsdata med Outlook, kommer du ofta behöva **exportera kalender till PST**. I den här handledningen går vi igenom allt du behöver – från att skapa ett enkelt möte till att lägga till deltagare och slutligen skriva händelserna till en PST‑fil, allt med Aspose.Email för Java. När du är klar har du en produktionsklar lösning som fungerar på Windows, Linux och macOS.

## Snabba svar
- **Vad är huvudmålet?** Exportera kalenderevenemang till en PST‑fil.  
- **Vilket bibliotek krävs?** Aspose.Email för Java (v25.4+).  
- **Behöver jag en licens?** Ja, en giltig Aspose.Email‑licens tar bort utvärderingsgränserna.  
- **Kan jag lägga till deltagare?** Absolut – använd `MapiRecipientCollection`.  
- **Vilken Java‑version stöds?** JDK 16 eller högre.

## Vad är **export calendar to pst**?
`MapiCalendar` är Aspose.Email‑klassen som modellerar ett Outlook‑kalenderobjekt, inklusive ämne, plats och tidsdetaljer.

Att exportera en kalender till PST betyder att konvertera `MapiCalendar`‑objekt i minnet till en Microsoft Outlook Personal Storage Table (PST). Den genererade PST‑filen kan öppnas direkt i Outlook, delas med kollegor eller importeras till vilket system som helst som förstår PST‑formatet, och bevarar alla händelsedetaljer såsom deltagare, återkommande mönster och påminnelser.

## Varför använda Aspose.Email för Java för att exportera kalender till PST?
Du kan generera en fullt kompatibel PST‑fil utan att installera Outlook. Aspose.Email erbjuder **full MAPI‑support**, fungerar på **alla större operativsystem**, och kan hantera **upp till 2 TB** data i Unicode‑PST‑format – tillräckligt för företagsarkiv i stor skala. API‑et låter dig dessutom hantera deltagare, återkommande mönster, påminnelser och anpassade egenskaper med bara några metodanrop, vilket dramatiskt minskar utvecklingsarbetet.

## Förutsättningar
- **Bibliotek & beroenden**: Aspose.Email för Java version 25.4 eller senare.  
- **Miljö**: JDK 16 eller högre, Maven för beroendehantering.  
- **Kunskap**: Grundläggande Java‑programmering och bekantskap med Maven.

## Så här installerar du Aspose.Email för Java
Lägg till Aspose.Email‑beroendet i din `pom.xml` och uppdatera ditt Maven‑projekt. Detta enkla steg gör hela MAPI‑API‑et tillgängligt på din klassväg.

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

### Licensanskaffning
Lås upp full funktionalitet i Aspose.Email utan utvärderingsbegränsningar genom att skaffa en licens:

1. **Gratis provversion**: Besök [Aspose download page](https://releases.aspose.com/email/java/) för en tillfällig licens.  
2. **Tillfällig licens**: Ansök via [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Köp licens**: Överväg att köpa via [Aspose's purchase portal](https://purchase.aspose.com/buy) för långsiktig användning.

När du har din licens, initiera den i din applikation för att aktivera alla funktioner.

## Hur man **skapar möte** (Create Calendar Event Java)

Läs in ett `MapiCalendar`‑objekt, sätt dess grundläggande egenskaper och returnera det redo för vidare bearbetning. Denna metod skapar ett kalenderinlägg med ett ämne, en plats, en beskrivning samt **java calendar start date** / **java calendar end date** som du definierat.

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

*Förklaring*: Klassen `MapiCalendar` är Aspose.Email:s representation av ett Outlook‑kalenderobjekt. Efter att de grundläggande fälten satts kan du också konfigurera återkommande mönster, påminnelser och kategorier innan du sparar.

## Hur man **lägger till deltagare** (java add meeting attendees)

Skapa en `MapiRecipientCollection`, fyll den med varje deltagare och fäst den på mötet. Detta säkerställer att varje deltagare får en korrekt inbjudan när PST‑filen öppnas.

`MapiRecipientCollection` är en samlingsklass som innehåller `MapiRecipient`‑objekt som representerar mötesdeltagare. `MapiRecipient` representerar en enskild deltagare med egenskaper som e‑postadress och mottagartyp.

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

*Förklaring*: `MapiRecipient` definierar en enskild mötesdeltagare. Att sätta typen till `MAPI_TO` markerar adressen som huvuddeltagare, medan `MAPI_CC` eller `MAPI_BCC` kan användas för valfria deltagare.

## Hur man **exporterar kalender till pst** (Create PST with calendar events)

Skapa en Unicode‑PST‑fil, lägg till en "Calendar"-mapp och infoga de tidigare byggda `MapiCalendar`‑objekten. PST‑filen kan sedan öppnas i Outlook eller distribueras till slutanvändare.

`PersonalStorage` är Aspose.Email‑klassen som används för att skapa, öppna och manipulera PST‑filer.

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

*Förklaring*: `PersonalStorage` är ingångspunkten för PST‑manipulation. Genom att använda Unicode‑format undviker du 2 GB‑gränsen i äldre PST‑versioner och får snabbare I/O på stora arkiv.

## Praktiska tillämpningar
1. **Affärsschemaläggning** – Automatisera intern möteskapning och distribution.  
2. **Evenemangshantering** – Följ konferenser, workshops och deltagarlistor.  
3. **CRM‑integration** – Synkronisera möten med kundrelationsverktyg.  
4. **Projektplanering** – Spara projektmilstenar som kalenderobjekt.  
5. **Fjärrteamssamarbete** – Generera PST‑filer för offline‑delning.

## Prestandaöverväganden
- **Disposera objekt** du inte längre behöver för att frigöra minne omedelbart.  
- **Använd effektiva samlingar** (t.ex. `ArrayList` för deltagarlistor) när du hanterar tusentals deltagare.  
- **Cacha ofta åtkomna händelser** om du frågar PST‑filen upprepade gånger, vilket minskar disk‑I/O.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **PST‑filen skapas inte** | Verifiera skrivbehörigheter i målkatalogen och säkerställ att sökvägen existerar. |
| **Deltagare får inga inbjudningar** | Bekräfta att varje `MapiRecipient` använder `MapiRecipientType.MAPI_TO` och att organisatörens e‑post är giltig. |
| **Datumavvikelse** | Använd `Calendar` konsekvent för start/slut‑datum; undvik att blanda `java.util.Date` med andra datum‑bibliotek utan konvertering. |

## Vanliga frågor

**Q: Hur kommer jag igång med Aspose.Email för Java?**  
A: Lägg till Maven‑beroendet som visas ovan, skaffa en licens och följ stegen i den här guiden för att skapa och exportera kalenderevenemang.

**Q: Kan jag anpassa PST‑filens namn och plats?**  
A: Ja, ändra variabeln `pstFilePath` i `createPSTWithCalendarEvents()` till någon giltig sökväg på ditt system.

**Q: Är det möjligt att lägga till återkommande mönster för möten?**  
A: Absolut – `MapiCalendar` exponerar en `RecurrencePattern`‑egenskap som du kan konfigurera innan du sparar.

**Q: Stöder Aspose.Email andra kalenderformat förutom PST?**  
A: Ja, du kan exportera till iCalendar (`.ics`) och andra format med lämpliga API‑metoder.

**Q: Vad är den maximala storleken på en PST‑fil jag kan skapa?**  
A: Med Unicode‑formatet (`FileFormatVersion.Unicode`) kan PST‑filer växa upp till 2 TB, begränsat endast av tillgängligt diskutrymme.

---

**Senast uppdaterad:** 2026-08-01  
**Testat med:** Aspose.Email för Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Master Aspose.Email for Java: Efficiently Manage Outlook PST Files](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Master Creating and Saving Calendar Items with Aspose.Email for Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [How to Read Multiple Calendar Events from an ICS File Using Aspose.Email in Java](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}