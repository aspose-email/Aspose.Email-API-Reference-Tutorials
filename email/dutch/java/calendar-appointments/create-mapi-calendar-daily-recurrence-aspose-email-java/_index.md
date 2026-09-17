---
date: '2026-09-17'
description: Leer hoe u een Outlook-agenda in Java maakt met daily recurrence en exceptions,
  en de agenda opslaat naar PST met Aspose.Email voor Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Maak een Outlook-agenda in Java met Aspose.Email. Leer over daily
  recurrence, exception handling en het opslaan naar PST in een stapsgewijze handleiding.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Maak Outlook-agenda in Java met daily recurrence en exceptions
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
title: Maak Outlook-agenda in Java met daily recurrence en exceptions
url: /nl/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak outlook calendar java met dagelijkse herhaling en uitzonderingen

Het efficiënt beheren van terugkerende gebeurtenissen kan een uitdaging zijn, vooral wanneer je een **outlook calendar java** nodig hebt die dagelijkse herhalingspatronen en occasionele uitzonderingen ondersteunt. In deze tutorial leer je hoe je Outlook calendar Java‑objecten maakt, dagelijkse herhaling configureert, uitzonderingsinstanties toevoegt, en uiteindelijk **save calendar to PST** gebruikt met Aspose.Email for Java. Aan het einde heb je een herbruikbare code‑snippet die je in elke Java‑gebaseerde planningsservice kunt gebruiken.

## Snelle antwoorden
- **Welke bibliotheek?** Aspose.Email for Java  
- **Primaire taak?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Vereiste JDK?** Java 16 or higher  
- **Kan ik bestanden aan uitzonderingen toevoegen?** Yes, using `MapiCalendarExceptionInfo`  
- **Waar wordt de kalender opgeslagen?** In a PST file via `PersonalStorage`  

## Wat is een Outlook calendar java?
Een Outlook calendar Java‑object is een programmatische weergave van een Outlook‑afspraak, gebouwd op de MAPI (Messaging Application Programming Interface)‑specificatie, die eigenschappen bevat zoals onderwerp, locatie, start/eindtijd, herhalingsregels, deelnemers en bijlagen. Dit object kan worden gemanipuleerd, geserialiseerd en opgeslagen in PST‑bestanden zonder dat Outlook vereist is.

## Waarom Aspose.Email for Java gebruiken?
Aspose.Email for Java stelt je in staat om met MAPI‑objecten te werken zonder Outlook te installeren. De bibliotheek ondersteunt **50+ MAPI‑eigenschappen**, kan Unicode‑PST‑bestanden tot **2 GB** genereren in minder dan **2 seconden** voor typische afspraakgegevens, en draait op elk platform dat Java 16+ ondersteunt. Deze pure‑Java‑aanpak maakt server‑side kalendercreatie, geautomatiseerde vergaderreeksen en volledige controle over herhalingslogica mogelijk.

## Vereisten

Voordat we beginnen, zorg ervoor dat je de volgende configuratie hebt:
- **Aspose.Email Library**: Versie 25.4 (of later) – beschikbaar via Maven of directe download.  
- **Java Development Kit (JDK)**: JDK 16 of nieuwer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, of een andere Java‑compatibele editor.

### Vereiste bibliotheken en afhankelijkheden

Om Aspose.Email in je project te integreren met Maven, voeg je de volgende afhankelijkheid toe aan je `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie

Om Aspose.Email te gebruiken, heb je een licentie nodig:
- **Gratis proefversie** – verken alle functies zonder kosten.  
- **Tijdelijke licentie** – aanvraag voor verlengde evaluatie.  
- **Volledige licentie** – aanschaf voor productie‑implementaties.

## Aspose.Email voor Java instellen

Eerst, stel je omgeving in:

1. Controleer of JDK 16 is geïnstalleerd en `JAVA_HOME` is geconfigureerd.  
2. Voeg de Maven‑afhankelijkheid (of download de JAR) toe aan je project.  

Hier is een klein fragment dat laat zien hoe je een licentiebestand laadt:

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

## Implementatie‑gids

### Outlook calendar java maken met dagelijkse herhaling en uitzonderingen

#### Overzicht
Deze functie stelt je in staat om terugkerende afspraken te automatiseren terwijl je toch specifieke instanties kunt overslaan of wijzigen.

#### Stapsgewijze implementatie

**1. Stel de startdatum van het evenement in**  
Bepaal wanneer de reeks moet beginnen:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Maak het MAPI‑kalenderobject**  
De `MapiCalendar`‑klasse is het bovenliggende object dat een enkel kalenderitem in het geheugen vertegenwoordigt. Geef locatie, onderwerp en beschrijving op:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definieer een dagelijks herhalingspatroon**  
De `MapiCalendarRecurrencePattern`‑klasse slaat de regel op die de afspraak elke dag herhaalt. Configureer het evenement om elke dag te herhalen:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Voeg een uitzondering toe aan de herhaling**  
`MapiCalendarExceptionInfo` beschrijft een enkele gebeurtenis die afwijkt van het patroon — ofwel uitgesloten of gewijzigd. Geef een datum op die moet worden uitgesloten (of gewijzigd):

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

### Bestanden bijvoegen aan kalenderuitzonderingen

#### Overzicht
Je kunt ondersteunende documenten (bijv. agenda's) aan elke uitzonderingsinstantie toevoegen.

**1. Maak een bestand aan en voeg het toe**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Outlook calendar java opslaan naar PST (save calendar to pst)

#### Overzicht
Bewaar de kalender in een PST‑bestand zodat Outlook of andere clients het kunnen lezen.

**1. Maak en sla de kalender op naar PST**  
De `PersonalStorage`‑klasse biedt methoden om een nieuw PST‑bestand te maken en MAPI‑items toe te voegen.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Praktische toepassingen
- **Bedrijfsplanning** – automatiseer vergaderreeksen, automatisch feestdagen overslaan.  
- **Projectmanagement** – houd terugkerende mijlpalen bij met occasionele datumverschuivingen.  
- **Evenementplanning** – beheer meerdaagse conferenties waarbij sommige sessies geannuleerd of verplaatst worden.

### Integratiemogelijkheden
Combineer Aspose.Email met CRM‑platforms, taak‑management API's of aangepaste workflow‑engines om end‑to‑end automatisering te realiseren.

## Prestatie‑overwegingen
- **Resources vrijgeven** – roep altijd `dispose()` aan op `PersonalStorage` om bestands‑handles vrij te maken.  
- **Streamgebruik** – geef de voorkeur aan `ByteArrayOutputStream` of bestands‑streams om te voorkomen dat volledige PST‑bestanden in het geheugen worden geladen.  
- **Async‑operaties** – voor bulk‑kalendergeneratie, voer de creatielogica uit op een achtergrondthread om de UI responsief te houden.

## Conclusie
Door deze gids te volgen weet je nu hoe je **outlook calendar java**‑objecten maakt met dagelijkse herhaling, uitzonderingen toevoegt, bestanden bijvoegt, en **save calendar to PST**. Deze mogelijkheden stellen je in staat robuuste planningsfuncties te bouwen zonder ooit direct Outlook aan te raken.

### Volgende stappen
- Experimenteer met wekelijkse of maandelijkse herhalingspatronen.  
- Verken extra MAPI‑eigenschappen zoals deelnemers, herinneringen en categorieën.  
- Bekijk de uitgebreide API‑documentatie van Aspose.Email voor meer geavanceerde scenario's.

## Veelgestelde vragen

**Q: Ondersteunt de bibliotheek tijdzone‑bewuste afspraken?**  
A: Ja, je kunt de `StartTimeZone` en `EndTimeZone` eigenschappen instellen op `MapiCalendar`.

**Q: Kan ik programmatically een enkele gebeurtenis uit een terugkerende reeks verwijderen?**  
A: Gebruik de `DeletedInstanceDates`‑collectie op het herhalingspatroon om specifieke data als verwijderd te markeren.

**Q: Zijn er limieten voor de grootte van een PST‑bestand dat met Aspose.Email wordt gemaakt?**  
A: PST‑bestanden volgen de Unicode‑formaatlimieten (standaard tot 2 GB), maar je kunt grotere groottes configureren via `PersonalStorage`‑instellingen.

**Q: Hoe voeg ik deelnemers toe aan een vergaderverzoek?**  
A: Maak `MapiRecipient`‑objecten aan, stel hun `RecipientType` in op `MapiRecipientType.MAPI_TO`, en voeg ze toe aan de `Recipients`‑collectie van de `MapiMessage`.

**Q: Is er ondersteuning voor terugkerende taken (niet alleen afspraken)?**  
A: Ja, Aspose.Email biedt ook `MapiTask` met vergelijkbare herhalingsmogelijkheden.

**Q: Kan ik deze gids gebruiken als onderdeel van een Aspose.Email Java‑tutorialreeks?**  
A: Absoluut – de hier getoonde stappen vormen een kernonderdeel van elke Aspose.Email Java‑tutorial die zich richt op kalendercreatie.

## Bronnen
- [Aspose.Email voor Java Documentatie](https://reference.aspose.com/email/java/)
- [Aspose.Email downloaden](https://releases.aspose.com/email/java/)
- [Een licentie aanschaffen](https://purchase.aspose.com/buy)
- [Gratis proefversie](https://releases.aspose.com/email/java/)
- [Tijdelijke licentie aanvragen](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Laatst bijgewerkt:** 2026-09-17  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Outlook‑kalender PST exporteren met Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Hoe een kalenderitem maken in Java met Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Kalenderdeeluitnodiging maken met Aspose.Email voor Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}