---
date: '2026-02-24'
description: Lär dig hur du exporterar kalender till PST med Aspose.Email för Java,
  inklusive hur du lägger till deltagare, anger start- och slutdatum samt hanterar
  möten effektivt.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Exportera kalender till PST med Aspose.Email för Java
url: /sv/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

 placeholders remain unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportera kalender till PST med Aspose.Email för Java

Om du bygger en Java‑applikation som behöver dela schemaläggningsdata med Outlook, kommer du ofta behöva **exportera kalender till PST**. I den här handledningen går vi igenom allt du behöver – från att skapa ett enkelt möte till att lägga till deltagare och slutligen skriva händelserna till en PST‑fil, allt med Aspose.Email för Java.

## Snabba svar
- **Vad är det primära målet?** Exportera kalenderhändelser till en PST‑fil.  
- **Vilket bibliotek krävs?** Aspose.Email for Java (v25.4+).  
- **Behöver jag en licens?** Ja, en giltig Aspose.Email‑licens tar bort utvärderingsgränserna.  
- **Kan jag lägga till deltagare?** Absolut – använd `MapiRecipientCollection`.  
- **Vilken Java‑version stöds?** JDK 16 eller högre.

## Vad är **exportera kalender till pst**?
Att exportera en kalender till PST innebär att konvertera `MapiCalendar`‑objekt i minnet till en Microsoft Outlook Personal Storage Table (PST). Den resulterande filen kan öppnas direkt i Outlook, delas med kollegor eller importeras till vilket system som helst som förstår PST‑formatet.

## Varför använda Aspose.Email för Java för att exportera kalender till PST?
- **Full MAPI‑stöd** – skapa, ändra och spara möten utan att behöva Outlook installerat.  
- **Cross‑platform** – fungerar på Windows, Linux och macOS.  
- **Rich API** – hantera deltagare, återkomster, påminnelser och mer.  
- **Performance‑optimized** – hantera stora volymer av händelser med låg minnesförbrukning.

## Förutsättningar
- **Bibliotek & beroenden**: Aspose.Email for Java version 25.4 eller senare.  
- **Miljö**: JDK 16 eller högre, Maven för beroendehantering.  
- **Kunskap**: Grundläggande Java‑programmering och bekantskap med Maven.

## Hur man installerar Aspose.Email för Java
Lägg till Aspose.Email‑beroendet i din `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning
1. **Free Trial**: Besök [Aspose download page](https://releases.aspose.com/email/java/) för en tillfällig licens.  
2. **Temporary License**: Ansök via [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Överväg att köpa via [Aspose's purchase portal](https://purchase.aspose.com/buy) för långsiktig användning.

När du har din licens, initiera den i din applikation för att aktivera alla funktioner.

## Hur man **skapar möte** (Create Calendar Event Java)

### Steg 1: Definiera start‑ och slutdatum (java calendar start date / java calendar end date)
Följande metod visar hur du anger start‑ och slutdatum för ett möte och returnerar ett `MapiCalendar`‑objekt:

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

*Explanation*: Denna kodsnutt skapar ett `MapiCalendar` med en specifik plats, ämne, beskrivning och de **java calendar start date** / **java calendar end date** du definierade.

## Hur man **lägger till deltagare** (java add meeting attendees)

### Steg 2: Bygg deltagarlistan
Använd `MapiRecipientCollection` för att ange vem som ska få mötesinbjudan:

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

*Explanation*: Denna kod skapar ett möte, sätter organisatören och bifogar listan **java add meeting attendees** så att alla får en korrekt inbjudan.

## Hur man **exporterar kalender till pst** (Create PST with calendar events)

### Steg 3: Skapa en PST‑fil och lägg till händelserna
Metoden nedan demonstrerar hur man skapar en Unicode‑PST‑fil och lagrar både det enkla mötet och mötet med deltagare:

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

*Explanation*: Denna kodsnutt **exporterar kalender till PST** genom att skapa en PST‑behållare, lägga till en fördefinierad "Calendar"‑mapp och infoga de tidigare byggda `MapiCalendar`‑objekten.

## Praktiska tillämpningar
1. **Business Scheduling** – Automatisera intern möteskapning och distribution.  
2. **Event Management** – Spåra konferenser, workshops och deltagarlistor.  
3. **CRM Integration** – Synkronisera möten med verktyg för kundrelationshantering.  
4. **Project Planning** – Lagra projektmilstenar som kalenderposter.  
5. **Remote Team Collaboration** – Generera PST‑filer för offline‑delning.

## Prestandaöverväganden
- **Dispose objects** du inte längre behöver för att frigöra minne.  
- **Choose efficient collections** för stora deltagarlistor.  
- **Cache frequently accessed events** om du frågar PST‑filen upprepade gånger.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **PST file not created** | Verifiera skrivbehörigheter i mål katalogen och säkerställ att mappvägen finns. |
| **Attendees not receiving invitations** | Bekräfta att varje `MapiRecipient` använder `MapiRecipientType.MAPI_TO` och att organisatörens e‑post är giltig. |
| **Date mismatch** | Använd `Calendar` konsekvent för start/slut‑datum; undvik att blanda `java.util.Date` med andra datum‑bibliotek utan konvertering. |

## Vanliga frågor

**Q: Hur kommer jag igång med Aspose.Email för Java?**  
A: Lägg till Maven‑beroendet som visas ovan, skaffa en licens och följ stegen i den här guiden för att skapa och exportera kalenderhändelser.

**Q: Kan jag anpassa PST‑filens namn och plats?**  
A: Ja, ändra variabeln `pstFilePath` i `createPSTWithCalendarEvents()` till någon giltig sökväg på ditt system.

**Q: Är det möjligt att lägga till återkommande mönster i möten?**  
A: Absolut – `MapiCalendar` exponerar återkommande egenskaper som `RecurrencePattern` som du kan konfigurera innan du sparar.

**Q: Stöder Aspose.Email andra kalenderformat förutom PST?**  
A: Ja, du kan exportera till iCalendar (`.ics`) och andra format med hjälp av lämpliga API‑metoder.

**Q: Vad är den maximala storleken på en PST‑fil jag kan skapa?**  
A: Med Unicode‑formatet (`FileFormatVersion.Unicode`) kan PST‑filer växa upp till 2 TB, begränsat endast av tillgängligt diskutrymme.

---

**Senast uppdaterad:** 2026-02-24  
**Testad med:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}