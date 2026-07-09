---
date: '2026-03-20'
description: Lär dig hur du exporterar Outlook‑kalender till PST med Aspose.Email
  för Java – skapa MAPI‑kalenderposter, ange återkommande, lägg till deltagare och
  spara till PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Exportera Outlook‑kalender PST med Aspose.Email – Java
url: /sv/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportera Outlook‑kalender PST med Aspose.Email – Java

## Introduktion

Letar du efter att effektivisera kalenderautomatisering i dina Java‑applikationer och behöver **exportera Outlook‑kalender PST**‑filer? Med **Aspose.Email for Java** kan du **skapa MAPI‑kalender Java**‑objekt, definiera återkommande mönster, lägga till deltagare och **spara kalender till PST** med bara några rader kod. Denna handledning guidar dig genom hela processen – från att konfigurera biblioteket till att generera en fullt fungerande kalenderpost klar för distribution.

### Vad du kommer att lära dig
- Hur du **skapar MAPI‑kalender Java**‑händelser med Aspose.Email.  
- Konfigurera dagliga, veckovisa eller anpassade återkommande mönster.  
- Lägga till mottagare (organisatörer, deltagare) till dina kalenderinbjudningar.  
- Spara kalenderobjektet genom att **spara kalender till PST** för Outlook‑kompatibilitet.  
- Hur du **automatiserar mötesplanering** med återanvändbar kod.

## Snabba svar
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Exportera Outlook‑kalender PST och **save calendar to PST**  
- **Prerequisites?** Java 8+, Maven, Aspose.Email license  
- **Typical implementation time?** 10‑15 minutes for a basic event  
- **Can I add recurrence?** Ja – dagligen, veckovis, månadsvis osv.

## Exportera Outlook‑kalender PST

I det här avsnittet fokuserar vi på hela flödet som låter dig **exportera Outlook‑kalender PST**‑filer. Efter att ha skapat MAPI‑kalenderobjektet är sista steget att lagra det i en PST‑fil som Outlook kan läsa direkt.

## Varför använda Aspose.Email för kalenderautomatisering?

- **Full Outlook‑kompatibilitet** – genererade objekt fungerar i Outlook, OWA och mobila klienter.  
- **Rich recurrence support** – daily, weekly, monthly, and custom patterns out of the box.  
- **No external dependencies** – pure Java library, no COM interop required.  
- **High performance** – efficient handling of large PST files and bulk operations.  
- **Automate meeting scheduling** – embed this logic in batch jobs or web services to create hundreds of invites automatically.

## Förutsättningar

Innan vi börjar, se till att du har:

### Nödvändiga bibliotek
- **Aspose.Email for Java**: Version 25.4 or later.

### Krav för miljöinställning
- En Java‑IDE som IntelliJ IDEA eller Eclipse.  
- Maven installerat för att hantera beroenden.

### Kunskapsförutsättningar
- Grundläggande kunskaper i Java‑programmering.  
- Bekantskap med objekt‑orienterade koncept.

## Installera Aspose.Email för Java

Add the Aspose.Email Maven dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning

- **Free Trial**: Testa utan begränsningar i 30 dagar.  
- **Temporary License**: Begär via [Aspose's website](https://purchase.aspose.com/temporary-license/) om du behöver mer tid.  
- **Purchase**: Köp en permanent licens från [purchase page](https://purchase.aspose.com/buy).

### Grundläggande initiering

After adding the dependency, initialize the library with your license file:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Implementeringsguide

Now that you’re set up, let’s **create MAPI calendar Java** and **save calendar to PST**.

### Skapa en MAPI‑kalender med återkommande

#### Översikt

Vi kommer att bygga en kalenderhändelse, tillämpa en daglig återkomst, lägga till deltagare och slutligen lagra den i en PST‑fil.

#### Steg‑för‑steg‑implementering

1. **Initiera datum och återkommandemönster**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Förklaring*: `MapiCalendarEventRecurrence` innehåller återkommandedetaljer; vi väljer ett dagligt mönster via `MapiCalendarDailyRecurrencePattern`.

2. **Ställ in mottagare**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Förklaring*: `MapiRecipientCollection` lagrar varje deltagare; `MAPI_TO` markerar dem som primära mottagare.

3. **Skapa MAPI‑kalenderobjektet**  

   Build the calendar object with all required details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Förklaring*: Konstruktorn förväntar sig organisatör, ämne, plats, start/sluttider, beskrivning, mottagarlista och återkomst.

4. **Spara till PST‑fil**  

   Finally, persist the calendar by **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Förklaring*: `PersonalStorage.create` skapar en ny PST‑fil, och `addMapiMessageItem` lägger in kalenderposten i mappen "Calendar".

### Felsökningstips
- Verifiera licenssökvägen; en ogiltig licens begränsar funktionaliteten.  
- Se till att mottagarnas e‑postadresser är korrekt formaterade för att undvika inbjudningsfel.  
- Stäng PST‑filen (`pst.dispose()`) efter operationer för att frigöra filhandtag.

## Praktiska tillämpningar

Här är vanliga scenarier där **skapa MAPI‑kalender Java** och **spara kalender till PST** briljerar:

1. **Automatiserad mötesplanering** – Generera återkommande mötesinbjudningar för projektteam utan manuellt arbete.  
2. **Evenemangshanteringsplattformar** – Exportera konferenssessioner som Outlook‑kompatibla kalenderobjekt.  
3. **CRM‑integration** – Synkronisera kundmöten från ett CRM‑system direkt till Outlook via PST‑filer.

## Prestandaöverväganden

- **Resurshantering**: Frigör `PersonalStorage`‑objekt efter användning för att förhindra fil‑lås.  
- **Batch‑behandling**: För stora volymer, bearbeta kalenderobjekt asynkront eller i omgångar för att hålla minnesanvändning låg.  

## Slutsats

Du har nu lärt dig hur du **exporterar Outlook‑kalender PST** genom att skapa MAPI‑kalender Java‑objekt, konfigurera återkommande, lägga till deltagare och **spara kalender till PST** med Aspose.Email. Detta tillvägagångssätt ger dina Java‑applikationer möjlighet att automatisera avancerade schemaläggningsarbetsflöden med Outlook‑kompatibilitet.

För djupare utforskning, se den officiella [documentation](https://reference.aspose.com/email/java/).

## FAQ‑avsnitt

### Fråga: Kan jag skapa veckovisa återkommandemönster?
- **A**: Ja! Använd `MapiCalendarWeeklyRecurrencePattern` för att definiera veckovisa upprepningar.

### Fråga: Hur hanterar jag undantag i händelseåterkommandet?
- **A**: Anropa `setExceptions()` på återkommande‑objektet för att ange datum som avviker från mönstret.

### Fråga: Är det möjligt att uppdatera ett befintligt kalenderobjekt?
- **A**: Absolut. Läs in objektet från PST, ändra dess egenskaper och spara tillbaka.

### Fråga: Kan jag kryptera PST‑filen?
- **A**: Ja, Aspose.Email låter dig ange ett lösenord på `PersonalStorage` när du skapar PST‑filen.

### Fråga: Vad händer om jag behöver lägga till bilagor till kalenderhändelsen?
- **A**: Använd `calendar.getAttachments().addFileAttachment("path/to/file")` innan du sparar.

## Resurser

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Senast uppdaterad:** 2026-03-20  
**Testat med:** Aspose.Email for Java 25.4 (JDK 16)  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}