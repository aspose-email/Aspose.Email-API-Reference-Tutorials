---
date: '2026-09-17'
description: Lär dig hur du exporterar Outlook-kalender PST med Aspose.Email för Java
  – skapa MAPI calendar items, sätt recurrence, lägg till attendees och spara till
  PST.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Exportera Outlook-kalender PST med Aspose.Email för Java. Lär dig
  skapa MAPI calendar items, lägga till recurrence, attendees och spara till PST på
  några minuter.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Exportera Outlook-kalender PST med Aspose.Email – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Exportera Outlook-kalender PST med Aspose.Email – Java
url: /sv/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportera Outlook-kalender PST med Aspose.Email – Java

## Introduktion

Letar du efter att effektivisera kalenderautomatisering i dina Java‑applikationer och behöver **exportera Outlook‑kalender PST**‑filer? Med **Aspose.Email for Java** kan du **skapa MAPI‑kalender Java**‑objekt, definiera återkommande mönster, lägga till deltagare och **spara kalender till PST** med bara några rader kod. Denna handledning guidar dig genom hela processen – från att konfigurera biblioteket till att generera en fullt fungerande kalenderpost klar för distribution.

### Vad du kommer att lära dig
- Hur du **skapar MAPI‑kalender Java**‑händelser med Aspose.Email.  
- Konfigurering av dagliga, veckovisa eller anpassade återkommande mönster.  
- Lägga till mottagare (organisatörer, deltagare) i dina kalenderinbjudningar.  
- Spara kalenderobjektet genom att **spara kalender till PST** för Outlook‑kompatibilitet.  
- Hur du **automatiserar mötesplanering** med återanvändbar kod.

## Snabba svar
- **Vilket bibliotek?** Aspose.Email for Java  
- **Primärt mål?** Exportera Outlook‑kalender PST och **spara kalender till PST**  
- **Förutsättningar?** Java 8+, Maven, Aspose.Email‑licens  
- **Typisk implementeringstid?** 10‑15 minuter för ett grundläggande evenemang  
- **Kan jag lägga till återkommande?** Ja – dagligen, veckovis, månadsvis osv.

## Exportera Outlook‑kalender PST

I detta avsnitt fokuserar vi på flödet från början till slut som låter dig **exportera Outlook‑kalender PST**‑filer. Efter att ha skapat MAPI‑kalenderobjektet är det sista steget att lagra det i en PST‑fil som Outlook kan läsa direkt.

## Varför använda Aspose.Email för kalenderautomatisering?

Exportera Outlook‑kalender PST med Aspose.Email eftersom det ger ett pålitligt, server‑sidesätt att producera Outlook‑kompatibla objekt utan COM‑interop. Biblioteket stöder **50+ in‑ och utdataformat**, kan hantera PST‑filer som överstiger 2 GB och bearbetar tusentals kalenderposter per minut på vanlig serverhårdvara. Dess inbyggda återkommande motor täcker dagliga, veckovisa, månatliga och anpassade mönster, vilket eliminerar behovet av manuella datumberäkningar.

## Förutsättningar

Innan vi börjar, se till att du har:

### Nödvändiga bibliotek
- **Aspose.Email for Java**: Version 25.4 eller senare (stöder Java 8‑21).

### Krav för miljöinställning
- En Java‑IDE såsom IntelliJ IDEA eller Eclipse.  
- Maven installerat för att hantera beroenden.

### Kunskapsförutsättningar
- Grundläggande Java‑programmeringskunskaper.  
- Bekantskap med objekt‑orienterade koncept.

## Konfigurera Aspose.Email för Java

Lägg till Aspose.Email Maven‑beroendet i din `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning

Aspose.Email erbjuder en gratis provversion, men en licens låser upp alla funktioner:

- **Gratis prov**: Testa utan begränsningar i 30 dagar.  
- **Tillfällig licens**: Begär via [Aspose's webbplats](https://purchase.aspose.com/temporary-license/) om du behöver mer tid.  
- **Köp**: Köp en permanent licens från [köpsidan](https://purchase.aspose.com/buy).

### Grundläggande initiering

Efter att ha lagt till beroendet, initiera biblioteket med din licensfil:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Implementeringsguide

Nu när du är klar, låt oss **skapa MAPI‑kalender Java** och **spara kalender till PST**.

### Skapa en MAPI‑kalender med återkommande

#### Översikt

Vi bygger ett kalender‑evenemang, applicerar en daglig återkommande, lägger till deltagare och lagrar slutligen i en PST‑fil.

#### Steg‑för‑steg-implementering

1. **Initiera datum och återkommande mönster**  

   `MapiCalendarEventRecurrence` är klassen som lagrar återkommande detaljer för ett kalenderobjekt.  
   `MapiCalendarDailyRecurrencePattern` definierar ett enkelt dagligt repetitionsschema.  

   Först, definiera starttiden och ange en daglig återkommande:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Ställ in mottagare**  

   `MapiRecipientCollection` representerar listan med personer som bjuds in till mötet.  
   `MAPI_TO` är flaggan som markerar en mottagare som huvuddeltagare.  

   Lägg till de personer som ska få mötesinbjudan:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **Skapa MAPI‑kalenderobjektet**  

   `MapiMessage`‑klassen (använd här som ett kalenderobjekt) kapslar in alla händelseegenskaper såsom organisatör, ämne, plats, start/sluttid, beskrivning, mottagarlista och återkommande.  

   Bygg kalenderobjektet med alla nödvändiga detaljer:

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

4. **Spara till PST‑fil**  

   `PersonalStorage` är Aspose.Email:s top‑nivå‑API för att skapa och manipulera PST‑filer.  
   `addMapiMessageItem` infogar ett MAPI‑meddelande (inklusive kalenderposter) i en angiven mapp.  

   Slutligen, persistera kalendern genom att **spara kalender till PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### Felsökningstips
- Verifiera licensvägen; en ogiltig licens begränsar funktionaliteten.  
- Säkerställ att mottagarnas e‑postadresser är korrekt formaterade för att undvika inbjudningsfel.  
- Stäng PST‑filen (`pst.dispose()`) efter operationer för att frigöra filhandtag.

## Praktiska tillämpningar

Här är vanliga scenarier där **skapa MAPI‑kalender Java** och **spara kalender till PST** briljerar:

1. **Automatiserad mötesplanering** – Generera återkommande mötesinbjudningar för projektteam utan manuellt arbete.  
2. **Evenemangs‑hanteringsplattformar** – Exportera konferenssessioner som Outlook‑kompatibla kalenderposter.  
3. **CRM‑integration** – Synkronisera kundmöten från ett CRM‑system direkt till Outlook via PST‑filer.

## Prestandaöverväganden

- **Resurshantering**: Disposera `PersonalStorage`‑objekt efter användning för att undvika fil‑lås.  
- **Batch‑behandling**: För stora volymer, bearbeta kalenderposter asynkront eller i delar för att hålla minnesanvändningen låg.  
- **Skalbarhet**: Aspose.Email kan skriva till PST‑filer större än 2 GB samtidigt som minnesförbrukningen hålls under 200 MB.

## Slutsats

Du har nu lärt dig hur du **exporterar Outlook‑kalender PST** genom att skapa MAPI‑kalender Java‑objekt, konfigurera återkommande, lägga till deltagare och **spara kalender till PST** med Aspose.Email. Detta tillvägagångssätt ger dina Java‑applikationer möjlighet att automatisera avancerade schemaläggningsarbetsflöden med Outlook‑kompatibilitet.

För djupare utforskning, se den officiella [dokumentationen](https://reference.aspose.com/email/java/).

## FAQ-avsnitt

### Q: Kan jag skapa veckovisa återkommande mönster?
- **A**: Ja! Använd `MapiCalendarWeeklyRecurrencePattern` för att definiera veckovisa upprepningar.

### Q: Hur hanterar jag undantag i händelse‑återkommande?
- **A**: Anropa `setExceptions()` på återkommande‑objektet för att specificera datum som avviker från mönstret.

### Q: Är det möjligt att uppdatera ett befintligt kalenderobjekt?
- **A**: Absolut. Läs in objektet från PST, modifiera dess egenskaper och spara tillbaka.

### Q: Kan jag kryptera PST‑filen?
- **A**: Ja, Aspose.Email låter dig ange ett lösenord på `PersonalStorage` när du skapar PST‑filen.

### Q: Vad händer om jag vill lägga till bilagor till kalenderhändelsen?
- **A**: Använd `calendar.getAttachments().addFileAttachment("path/to/file")` innan du sparar.

## Resurser

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free trial version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose support forum](https://forum.aspose.com/c/email/10)

---

**Senast uppdaterad:** 2026-09-17  
**Testat med:** Aspose.Email for Java 25.4 (JDK 16)  
**Författare:** Aspose

## Relaterade handledningar

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [How to Create PST Files with Aspose.Email for Java](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}