---
date: '2026-09-17'
description: Lär dig hur du skapar en Outlook-kalender i Java med daglig återkommande
  och undantag, och sparar kalendern till PST med Aspose.Email for Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Skapa Outlook-kalender i Java med Aspose.Email. Lär dig om daglig
  återkommande, hantering av undantag och hur du sparar till PST i en steg‑för‑steg‑guide.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Skapa Outlook-kalender i Java med daglig återkommande och undantag
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
title: Skapa Outlook-kalender i Java med daglig återkommande och undantag
url: /sv/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Outlook calendar Java med daglig återkommande och undantag

Att hantera återkommande händelser effektivt kan vara utmanande, särskilt när du behöver ett **outlook calendar java** som stödjer dagliga återkommande mönster och tillfälliga undantag. I den här handledningen kommer du att lära dig hur man skapar Outlook calendar Java‑objekt, konfigurerar daglig återkommande, lägger till undantagsinstanser och slutligen **save calendar to PST** med Aspose.Email för Java. I slutet har du ett återanvändbart kodsnutt som du kan lägga in i vilken Java‑baserad schemaläggningstjänst som helst.

## Snabba svar
- **Vilket bibliotek?** Aspose.Email for Java  
- **Primär uppgift?** Skapa en Outlook calendar Java med daglig återkommande och undantag  
- **Förkunskaps‑JDK?** Java 16 eller högre  
- **Kan jag bifoga filer till undantag?** Ja, med `MapiCalendarExceptionInfo`  
- **Var lagras kalendern?** I en PST‑fil via `PersonalStorage`  

## Vad är en Outlook calendar java?
Ett Outlook calendar Java‑objekt är en programmatisk representation av ett Outlook‑möte, byggt på MAPI‑specifikationen (Messaging Application Programming Interface), som inkluderar egenskaper såsom ämne, plats, start/sluttider, återkommanderegler, deltagare och bilagor. Detta objekt kan manipuleras, serialiseras och lagras i PST‑filer utan att kräva Outlook.

## Varför använda Aspose.Email för Java?
Aspose.Email för Java låter dig arbeta med MAPI‑objekt utan att installera Outlook. Biblioteket stödjer **50+ MAPI‑egenskaper**, kan generera Unicode‑PST‑filer upp till **2 GB** på under **2 sekunder** för typisk mötesdata, och körs på alla plattformar som stödjer Java 16+. Detta rena Java‑tillvägagångssätt möjliggör server‑sidig kalender‑skapande, automatiserade mötesserier och full kontroll över återkommandelogik.

## Förutsättningar

Innan vi börjar, se till att du har följande uppsättning:
- **Aspose.Email Library**: Version 25.4 (eller senare) – tillgänglig via Maven eller direkt nedladdning.  
- **Java Development Kit (JDK)**: JDK 16 eller nyare.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans eller någon Java‑kompatibel editor.

### Nödvändiga bibliotek och beroenden

För att integrera Aspose.Email i ditt projekt med Maven, lägg till följande beroende i din `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning

För att använda Aspose.Email behöver du en licens:
- **Free trial** – utforska alla funktioner utan kostnad.  
- **Temporary license** – begär för förlängd utvärdering.  
- **Full license** – köp för produktionsdistributioner.

## Konfigurera Aspose.Email för Java

Först, konfigurera din miljö:

1. Verifiera att JDK 16 är installerat och att `JAVA_HOME` är konfigurerad.  
2. Lägg till Maven‑beroendet (eller ladda ner JAR‑filen) i ditt projekt.  

Här är ett litet kodexempel som visar hur man laddar en licensfil:

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

## Implementeringsguide

### Skapa outlook calendar java med daglig återkommande och undantag

#### Översikt
Denna funktion låter dig automatisera återkommande möten samtidigt som du kan hoppa över eller ändra specifika instanser.

#### Steg‑för‑steg-implementering

**1. Ställ in händelsens startdatum**  
Bestäm när serien ska börja:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Skapa MAPI‑kalenderobjektet**  
Klassen `MapiCalendar` är top‑nivå‑objektet som representerar ett enskilt kalenderobjekt i minnet. Ange plats, ämne och beskrivning:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definiera ett dagligt återkommandemönster**  
Klassen `MapiCalendarRecurrencePattern` lagrar regeln som upprepar mötet varje dag. Konfigurera händelsen att upprepas varje dag:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Lägg till ett undantag till återkommandet**  
`MapiCalendarExceptionInfo` beskriver en enskild förekomst som avviker från mönstret—antingen exkluderad eller ändrad. Specificera ett datum som ska exkluderas (eller ändras):

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

### Bifoga filer till kalenderundantag

#### Översikt
Du kan bifoga stödjande dokument (t.ex. dagordningar) till vilken undantagsinstans som helst.

**1. Skapa och bifoga en fil**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Spara outlook calendar java till PST (save calendar to pst)

#### Översikt
Persistera kalendern till en PST‑fil så att Outlook eller andra klienter kan läsa den.

**1. Skapa och spara kalender till PST**  
Klassen `PersonalStorage` tillhandahåller metoder för att skapa en ny PST‑fil och lägga till MAPI‑objekt i den.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Praktiska tillämpningar
- **Corporate scheduling** – automatisera mötesserier, automatiskt hoppa över helgdagar.  
- **Project management** – spåra återkommande milstolpar med tillfälliga datumförskjutningar.  
- **Event planning** – hantera flerdagarskonferenser där vissa sessioner avbokas eller omplaneras.

### Integrationsmöjligheter
Kombinera Aspose.Email med CRM‑plattformar, task‑management API:er eller anpassade arbetsflödesmotorer för att driva end‑to‑end‑automation.

## Prestandaöverväganden
- **Dispose resources** – anropa alltid `dispose()` på `PersonalStorage` för att frigöra filhandtag.  
- **Stream usage** – föredra `ByteArrayOutputStream` eller filströmmar för att undvika att ladda hela PST‑filer i minnet.  
- **Async operations** – för massgenerering av kalendrar, kör skaplogiken på en bakgrundstråd för att hålla UI responsivt.

## Slutsats
Genom att följa den här guiden vet du nu hur man **create outlook calendar java** objekt med daglig återkommande, lägger till undantag, bifogar filer och **save calendar to PST**. Dessa möjligheter låter dig bygga robusta schemaläggningsfunktioner utan att någonsin behöva röra Outlook direkt.

### Nästa steg
- Experimentera med veckovisa eller månatliga återkommandemönster.  
- Utforska ytterligare MAPI‑egenskaper såsom deltagare, påminnelser och kategorier.  
- Granska Aspose.Email:s omfattande API‑dokumentation för mer avancerade scenarier.

## Vanliga frågor

**Q: Stöder biblioteket tidszonsmedvetna möten?**  
A: Ja, du kan sätta `StartTimeZone` och `EndTimeZone` egenskaperna på `MapiCalendar`.

**Q: Kan jag programatiskt radera en enskild förekomst från en återkommande serie?**  
A: Använd `DeletedInstanceDates`‑samlingen på återkommandemönstret för att markera specifika datum som borttagna.

**Q: Finns det begränsningar för storleken på en PST‑fil som skapas med Aspose.Email?**  
A: PST‑filer följer Unicode‑formatets begränsningar (upp till 2 GB som standard), men du kan konfigurera större storlekar via `PersonalStorage`‑inställningarna.

**Q: Hur lägger jag till deltagare i en mötesförfrågan?**  
A: Skapa `MapiRecipient`‑objekt, sätt deras `RecipientType` till `MapiRecipientType.MAPI_TO`, och lägg till dem i `Recipients`‑samlingen på `MapiMessage`.

**Q: Finns det stöd för återkommande uppgifter (inte bara möten)?**  
A: Ja, Aspose.Email tillhandahåller även `MapiTask` med liknande återkommandefunktioner.

**Q: Kan jag använda den här guiden som en del av en Aspose.Email Java‑handledningsserie?**  
A: Absolut – stegen som visas här är en kärnkomponent i alla Aspose.Email Java‑handledningar som behandlar kalender‑skapande.

## Resurser
- [Aspose.Email för Java-dokumentation](https://reference.aspose.com/email/java/)
- [Ladda ner Aspose.Email](https://releases.aspose.com/email/java/)
- [Köp en licens](https://purchase.aspose.com/buy)
- [Gratis provversion](https://releases.aspose.com/email/java/)
- [Begär tillfällig licens](https://purchase.aspose.com/temporary-license/)
- [Aspose supportforum](https://forum.aspose.com/c/email/10)

---

**Senast uppdaterad:** 2026-09-17  
**Testad med:** Aspose.Email for Java 25.4 (JDK 16)  
**Författare:** Aspose

## Relaterade handledningar

- [Exportera Outlook-kalender PST med Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Hur man skapar kalenderobjekt Java med Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Skapa kalenderdelningsinbjudan med Aspose.Email för Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}