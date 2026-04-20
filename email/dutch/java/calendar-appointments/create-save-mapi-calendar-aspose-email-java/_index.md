---
date: '2026-03-20'
description: Leer hoe je een Outlook-agenda‑PST exporteert met Aspose.Email voor Java
  – maak MAPI-agenda‑items, stel herhaling in, voeg deelnemers toe en sla op in een
  PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Export Outlook-agenda PST met Aspose.Email – Java
url: /nl/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Outlook-agenda PST met Aspose.Email – Java

## Inleiding

Bent u op zoek naar een manier om de agenda‑automatisering in uw Java‑toepassingen te stroomlijnen en moet u **export Outlook calendar PST**‑bestanden exporteren? Met **Aspose.Email for Java** kunt u **create MAPI calendar Java**‑items maken, terugkeerpatronen definiëren, deelnemers toevoegen en **save calendar to PST** met slechts een paar regels code. Deze tutorial leidt u door het volledige proces — van het instellen van de bibliotheek tot het genereren van een volledig functionele agenda‑vermelding die klaar is voor distributie.

### Wat u zult leren
- Hoe **create MAPI calendar Java**‑evenementen te maken met Aspose.Email.  
- Dagelijkse, wekelijkse of aangepaste terugkeerpatronen configureren.  
- Ontvangers (organisatoren, deelnemers) toevoegen aan uw agenda‑uitnodigingen.  
- Het agenda‑item behouden door **saving calendar to PST** voor Outlook‑compatibiliteit.  
- Hoe **automate meeting scheduling** te automatiseren met herbruikbare code.

## Snelle antwoorden
- **Welke bibliotheek?** Aspose.Email for Java  
- **Primair doel?** Export Outlook calendar PST en **save calendar to PST**  
- **Voorvereisten?** Java 8+, Maven, Aspose.Email‑licentie  
- **Typische implementatietijd?** 10‑15 minuten voor een basis‑evenement  
- **Kan ik terugkeer toevoegen?** Ja – dagelijks, wekelijks, maandelijks, enz.

## Export Outlook-agenda PST

In dit gedeelte richten we ons op de end‑to‑end‑stroom die u in staat stelt **export Outlook calendar PST**‑bestanden. Na het maken van het MAPI‑agenda‑object is de laatste stap om het op te slaan in een PST‑bestand dat Outlook direct kan lezen.

## Waarom Aspose.Email gebruiken voor agenda‑automatisering?

- **Volledige Outlook‑compatibiliteit** – gegenereerde items werken in Outlook, OWA en mobiele clients.  
- **Rijke terugkeerondersteuning** – dagelijks, wekelijks, maandelijks en aangepaste patronen direct beschikbaar.  
- **Geen externe afhankelijkheden** – pure Java‑bibliotheek, geen COM‑interop vereist.  
- **Hoge prestaties** – efficiënte verwerking van grote PST‑bestanden en bulk‑bewerkingen.  
- **Automate meeting scheduling** – integreer deze logica in batch‑taken of webservices om honderden uitnodigingen automatisch te maken.

## Voorvereisten

Zorg er voordat we beginnen voor dat u het volgende heeft:

### Vereiste bibliotheken
- **Aspose.Email for Java**: Versie 25.4 of later.

### Omgevingsinstellingen
- Een Java‑IDE zoals IntelliJ IDEA of Eclipse.  
- Maven geïnstalleerd om afhankelijkheden te beheren.

### Kennisvoorvereisten
- Basis Java‑programmeervaardigheden.  
- Bekendheid met object‑georiënteerde concepten.

## Instellen van Aspose.Email voor Java

Voeg de Aspose.Email Maven‑afhankelijkheid toe aan uw `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie

Aspose.Email biedt een gratis proefversie, maar een licentie ontgrendelt alle functies:

- **Gratis proefversie**: Test zonder beperkingen gedurende 30 dagen.  
- **Tijdelijke licentie**: Vraag aan via [Aspose's website](https://purchase.aspose.com/temporary-license/) als u extra tijd nodig heeft.  
- **Aankoop**: Koop een permanente licentie via de [aankooppagina](https://purchase.aspose.com/buy).

### Basisinitialisatie

Na het toevoegen van de afhankelijkheid, initialiseert u de bibliotheek met uw licentiebestand:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Implementatie‑gids

Nu u klaar bent, laten we **create MAPI calendar Java** en **save calendar to PST**.

### Maak een MAPI‑agenda met terugkeer

#### Overzicht

We bouwen een agenda‑evenement, passen een dagelijkse terugkeer toe, voegen deelnemers toe en slaan het uiteindelijk op in een PST‑bestand.

#### Stapsgewijze implementatie

1. **Datum en terugkeerpatroon initialiseren**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Uitleg*: `MapiCalendarEventRecurrence` bevat de terugkeerdetails; we kiezen een dagelijks patroon via `MapiCalendarDailyRecurrencePattern`.

2. **Ontvangers instellen**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Uitleg*: `MapiRecipientCollection` slaat elke deelnemer op; `MAPI_TO` markeert hen als primaire ontvangers.

3. **Maak het MAPI‑agenda‑item**  

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

   *Uitleg*: De constructor verwacht organisator, onderwerp, locatie, start/eindtijden, beschrijving, ontvangerslijst en terugkeer.

4. **Opslaan naar PST‑bestand**  

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

   *Uitleg*: `PersonalStorage.create` genereert een nieuw PST‑bestand, en `addMapiMessageItem` voegt de agenda‑vermelding toe aan de map "Calendar".

### Probleemoplossingstips
- Controleer het licentiepad; een ongeldige licentie beperkt de functionaliteit.  
- Zorg ervoor dat e‑mailadressen van ontvangers correct zijn geformatteerd om uitnodigingsfouten te voorkomen.  
- Sluit de PST (`pst.dispose()`) na bewerkingen om bestands‑handles vrij te geven.

## Praktische toepassingen

Hier zijn veelvoorkomende scenario's waarin **creating MAPI calendar Java** en **saving calendar to PST** uitblinken:

1. **Automated Meeting Scheduling** – Genereer terugkerende vergaderuitnodigingen voor projectteams zonder handmatige inspanning.  
2. **Event Management Platforms** – Exporteer conferentiesessies als Outlook‑compatibele agenda‑items.  
3. **CRM Integration** – Synchroniseer klantafspraken vanuit een CRM‑systeem direct naar Outlook via PST‑bestanden.

## Prestatie‑overwegingen

- **Resource Management**: Vernietig `PersonalStorage`‑objecten na gebruik om bestandsvergrendelingen te voorkomen.  
- **Batch Processing**: Voor grote volumes, verwerk agenda‑items asynchroon of in delen om het geheugenverbruik laag te houden.  

## Conclusie

U heeft nu geleerd hoe u **export Outlook calendar PST** kunt uitvoeren door MAPI‑agenda‑Java‑objecten te maken, terugkeer te configureren, deelnemers toe te voegen en **save calendar to PST** te gebruiken met Aspose.Email. Deze aanpak stelt uw Java‑toepassingen in staat om geavanceerde plannings‑workflows te automatiseren met Outlook‑compatibiliteit.

Voor een diepere verkenning, bekijk de officiële [documentation](https://reference.aspose.com/email/java/).

## FAQ‑sectie

### Q: Kan ik wekelijkse terugkeerpatronen maken?
- **A**: Ja! Gebruik `MapiCalendarWeeklyRecurrencePattern` om wekelijkse herhalingen te definiëren.

### Q: Hoe ga ik om met uitzonderingen in de terugkeer van een evenement?
- **A**: Roep `setExceptions()` aan op het terugkeerobject om data op te geven die afwijken van het patroon.

### Q: Is het mogelijk om een bestaand agenda‑item bij te werken?
- **A**: Absoluut. Laad het item uit de PST, wijzig de eigenschappen en sla het opnieuw op.

### Q: Kan ik het PST‑bestand versleutelen?
- **A**: Ja, Aspose.Email stelt u in staat een wachtwoord in te stellen op `PersonalStorage` bij het maken van de PST.

### Q: Wat als ik bijlagen moet toevoegen aan het agenda‑evenement?
- **A**: Gebruik `calendar.getAttachments().addFileAttachment("path/to/file")` vóór het opslaan.

## Bronnen

- [Aspose.Email Documentatie](https://reference.aspose.com/email/java/)
- [Aspose.Email voor Java downloaden](https://releases.aspose.com/email/java/)
- [Licentie aanschaffen](https://purchase.aspose.com/buy)
- [Gratis proefversie](https://releases.aspose.com/email/java/)
- [Tijdelijke licentie aanvragen](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Laatst bijgewerkt:** 2026-03-20  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}