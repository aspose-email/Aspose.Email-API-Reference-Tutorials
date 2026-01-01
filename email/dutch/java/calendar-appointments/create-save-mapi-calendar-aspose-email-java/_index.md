---
date: '2026-01-01'
description: Leer hoe je een MAPI‑agenda in Java maakt en de agenda opslaat naar PST
  met Aspose.Email voor Java. Stapsgewijze handleiding met code, terugkerende afspraken
  en ontvangers.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Hoe een MAPI-agenda in Java te maken met Aspose.Email – Agenda opslaan in PST
url: /nl/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe MAPI calendar java te maken met Aspose.Email – Agenda opslaan naar PST

## Introductie

Zoekt u naar een manier om agenda‑automatisering in uw Java‑toepassingen te stroomlijnen? Met **Aspose.Email for Java** kunt u **MAPI calendar java**‑items maken, terugkeerpatronen definiëren, deelnemers toevoegen en **agenda opslaan naar PST**‑bestanden met slechts een paar regels code. Deze tutorial leidt u door het volledige proces — van het instellen van de bibliotheek tot het genereren van een volledig functionele agenda‑vermelding die klaar is voor distributie.

### Wat u zult leren
- Hoe **MAPI calendar java**‑evenementen te maken met Aspose.Email.
- Dagelijkse, wekelijkse of aangepaste terugkeerpatronen configureren.
- Ontvangers (organisatoren, deelnemers) toevoegen aan uw agenda‑uitnodigingen.
- Het agenda‑item behouden door **agenda opslaan naar PST** voor Outlook‑compatibiliteit.

Laten we duiken en uw ontwikkelomgeving gereed maken.

## Snelle antwoorden
- **Welke bibliotheek?** Aspose.Email for Java  
- **Primair doel?** MAPI calendar java maken en **agenda opslaan naar PST**  
- **Vereisten?** Java 8+, Maven, Aspose.Email‑licentie  
- **Typische implementatietijd?** 10‑15 minuten voor een basis‑evenement  
- **Kan ik terugkeer toevoegen?** Ja – dagelijks, wekelijks, maandelijks, enz.

## Wat is een MAPI‑agenda in Java?
Een MAPI (Messaging Application Programming Interface) agenda‑object vertegenwoordigt een Outlook‑compatibele vergadering of afspraak. Met Aspose.Email kunt u deze objecten programmatisch samenstellen, waardoor naadloze integratie met Exchange, Outlook of elke client die PST‑bestanden gebruikt mogelijk is.

## Waarom Aspose.Email gebruiken voor agenda‑automatisering?
- **Volledige Outlook‑compatibiliteit** – gegenereerde items werken in Outlook, OWA en mobiele clients.  
- **Uitgebreide terugkeerondersteuning** – dagelijks, wekelijks, maandelijks en aangepaste patronen direct beschikbaar.  
- **Geen externe afhankelijkheden** – pure Java‑bibliotheek, geen COM‑interop vereist.  
- **Hoge prestaties** – efficiënte verwerking van grote PST‑bestanden en bulk‑bewerkingen.

## Vereisten

Zorg ervoor dat u het volgende heeft voordat we beginnen:

### Vereiste bibliotheken
- **Aspose.Email for Java**: Versie 25.4 of later.

### Omgevingsinstellingen
- Een Java‑IDE zoals IntelliJ IDEA of Eclipse.  
- Maven geïnstalleerd om afhankelijkheden te beheren.

### Kennisvereisten
- Basis Java‑programmeervaardigheden.  
- Bekendheid met object‑georiënteerde concepten.

## Aspose.Email voor Java instellen

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

Nu u klaar bent, laten we **MAPI calendar java** maken en **agenda opslaan naar PST**.

### Maak een MAPI‑agenda met terugkeer

#### Overzicht

We bouwen een agenda‑evenement, passen een dagelijkse terugkeer toe, voegen deelnemers toe en slaan het uiteindelijk op in een PST‑bestand.

#### Stap‑voor‑stap implementatie

1. **Initialize Date and Recurrence Pattern**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Uitleg*: `MapiCalendarEventRecurrence` bevat terugkeerdetails; we kiezen een dagelijks patroon via `MapiCalendarDailyRecurrencePattern`.

2. **Set Up Recipients**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Uitleg*: `MapiRecipientCollection` slaat elke deelnemer op; `MAPI_TO` markeert hen als primaire ontvangers.

3. **Create the MAPI Calendar Item**  

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

   *Uitleg*: De constructor verwacht organisator, onderwerp, locatie, start/eind‑tijden, beschrijving, ontvangerslijst en terugkeer.

4. **Save to PST File**  

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
- Sluit het PST (`pst.dispose()`) na bewerkingen om bestands‑handles vrij te geven.

## Praktische toepassingen

Hier zijn veelvoorkomende scenario's waarin **MAPI calendar java** maken en **agenda opslaan naar PST** uitblinkt:

1. **Geautomatiseerde vergaderplanning** – Genereer terugkerende vergaderuitnodigingen voor projectteams zonder handmatige inspanning.  
2. **Evenement‑beheersplatforms** – Exporteer conferentiesessies als Outlook‑compatibele agenda‑items.  
3. **CRM‑integratie** – Synchroniseer klantafspraken vanuit een CRM‑systeem direct naar Outlook via PST‑bestanden.

## Prestatie‑overwegingen
- **Resource‑beheer**: Vernietig `PersonalStorage`‑objecten na gebruik om bestandsvergrendelingen te voorkomen.  
- **Batchverwerking**: Verwerk voor grote volumes agenda‑items asynchroon of in delen om het geheugenverbruik laag te houden.  

## Conclusie

U heeft nu geleerd hoe u **MAPI calendar java**‑objecten kunt **maken**, terugkeer kunt configureren, deelnemers kunt toevoegen en **agenda opslaan naar PST** met Aspose.Email. Deze aanpak stelt uw Java‑toepassingen in staat om geavanceerde planningsworkflows te automatiseren met Outlook‑compatibiliteit.

Voor diepere verkenning, bekijk de officiële [documentatie](https://reference.aspose.com/email/java/).

## FAQ‑sectie

### Q: Kan ik wekelijkse terugkeerpatronen maken?
- **A**: Ja! Gebruik `MapiCalendarWeeklyRecurrencePattern` om wekelijkse herhalingen te definiëren.

### Q: Hoe ga ik om met uitzonderingen in de terugkeer van een evenement?
- **A**: Roep `setExceptions()` aan op het terugkeerobject om datums op te geven die afwijken van het patroon.

### Q: Is het mogelijk een bestaand agenda‑item bij te werken?
- **A**: Absoluut. Laad het item uit het PST, wijzig de eigenschappen en sla het opnieuw op.

### Q: Kan ik het PST‑bestand versleutelen?
- **A**: Ja, Aspose.Email stelt u in staat een wachtwoord in te stellen op `PersonalStorage` bij het aanmaken van het PST.

### Q: Wat als ik bijlagen moet toevoegen aan het agenda‑evenement?
- **A**: Gebruik `calendar.getAttachments().addFileAttachment("path/to/file")` vóór het opslaan.

## Bronnen

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-01  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose