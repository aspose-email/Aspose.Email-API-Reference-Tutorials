---
date: '2026-03-20'
description: Leer hoe je een Outlook-agenda in Java maakt met dagelijkse herhaling
  en uitzonderingen, en de agenda opslaat naar PST met behulp van Aspose.Email voor
  Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Maak Outlook-agenda in Java met dagelijkse herhaling en uitzonderingen
url: /nl/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je outlook calendar java met dagelijkse herhaling en uitzonderingen

Het efficiënt beheren van terugkerende gebeurtenissen kan een uitdaging zijn, vooral wanneer je een **outlook calendar java** nodig hebt die dagelijkse herhalingspatronen en occasionele uitzonderingen ondersteunt. In deze tutorial leer je hoe je Outlook calendar Java‑objecten maakt, dagelijkse herhaling configureert, uitzonderingsinstanties toevoegt, en uiteindelijk **save calendar to PST** gebruikt via Aspose.Email for Java. Aan het einde heb je een herbruikbare code‑snippet die je in elke Java‑gebaseerde planningsservice kunt gebruiken.

## Snelle antwoorden
- **Welke bibliotheek?** Aspose.Email for Java  
- **Primaire taak?** Maak een Outlook calendar Java met dagelijkse herhaling en uitzonderingen  
- **Vereiste JDK?** Java 16 of hoger  
- **Kan ik bestanden aan uitzonderingen toevoegen?** Ja, met `MapiCalendarExceptionInfo`  
- **Waar wordt de agenda opgeslagen?** In een PST‑bestand via `PersonalStorage`

## Wat is een Outlook calendar java?
Een Outlook calendar Java‑object (geïmplementeerd als een MAPI‑agenda) volgt dezelfde standaarden als Microsoft Outlook‑afspraken. Het slaat uitgebreide herhalingsregels, uitzonderingsafhandeling, deelnemers en bijlagen op, waardoor het perfect is voor enterprise‑grade planning.

## Waarom Aspose.Email voor Java gebruiken?
Aspose.Email biedt een pure‑Java‑API waarmee je met MAPI‑objecten kunt werken zonder dat Outlook geïnstalleerd hoeft te zijn. Deze **aspose email tutorial java** benadering maakt server‑side generatie van PST‑bestanden, geautomatiseerde vergaderreeksen en volledige controle over de herhalingslogica mogelijk.

## Vereisten

Before we begin, ensure you have the following setup:
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

To use Aspose.Email, you'll need a license:
- **Gratis proefversie** – verken alle functies zonder kosten.  
- **Tijdelijke licentie** – aanvraag voor verlengde evaluatie.  
- **Volledige licentie** – aankoop voor productie‑implementaties.

## Aspose.Email voor Java instellen

First, set up your environment:

1. Controleer of JDK 16 geïnstalleerd is en `JAVA_HOME` geconfigureerd is.  
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

### Een Outlook calendar java maken met dagelijkse herhaling en uitzonderingen

#### Overzicht
Deze functie stelt je in staat terugkerende afspraken te automatiseren terwijl je specifieke instanties kunt overslaan of wijzigen.

#### Stapsgewijze implementatie

**1. Stel de startdatum van het evenement in**  
Bepaal wanneer de reeks moet beginnen:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Maak het MAPI‑agenda‑object**  
Geef locatie, onderwerp en beschrijving op:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definieer een dagelijks herhalingspatroon**  
Configureer het evenement om elke dag te herhalen:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Voeg een uitzondering toe aan de herhaling**  
Geef een datum op die moet worden uitgesloten (of gewijzigd):

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

### Bestanden bij agenda‑uitzonderingen toevoegen

#### Overzicht
Je kunt ondersteunende documenten (bijv. agenda's) aan elke uitzonderingsinstantie toevoegen.

**1. Maak en voeg een bestand toe**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Outlook calendar java opslaan naar PST (save calendar to pst)

#### Overzicht
Sla de agenda op in een PST‑bestand zodat Outlook of andere clients het kunnen lezen.

**1. Maak en sla de agenda op naar PST**

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
- **Projectmanagement** – volg terugkerende mijlpalen met occasionele datumverschuivingen.  
- **Evenementplanning** – beheer meerdaagse conferenties waarbij sommige sessies worden geannuleerd of verplaatst.

### Integratiemogelijkheden
Combineer Aspose.Email met CRM‑platformen, taak‑management‑API's of aangepaste workflow‑engines om end‑to‑end automatisering te realiseren.

## Prestatie‑overwegingen
- **Resources vrijgeven** – roep altijd `dispose()` aan op `PersonalStorage` om bestands‑handles vrij te maken.  
- **Streamgebruik** – geef de voorkeur aan `ByteArrayOutputStream` of bestands‑streams om te voorkomen dat volledige PST’s in het geheugen worden geladen.  
- **Asynchrone bewerkingen** – voor bulk‑agenda‑generatie, voer de creatielogica uit op een achtergrondthread om de UI responsief te houden.

## Conclusie
Door deze gids te volgen weet je nu hoe je **create outlook calendar java** objecten maakt met dagelijkse herhaling, uitzonderingen toevoegt, bestanden bijvoegt, en **save calendar to PST**. Deze mogelijkheden stellen je in staat robuuste planningsfuncties te bouwen zonder ooit direct Outlook aan te raken.

### Volgende stappen
- Experimenteer met wekelijkse of maandelijkse herhalingspatronen.  
- Verken extra MAPI‑eigenschappen zoals deelnemers, herinneringen en categorieën.  
- Bekijk de uitgebreide API‑documentatie van Aspose.Email voor meer geavanceerde scenario's.

## Veelgestelde vragen

**Q: Ondersteunt de bibliotheek tijdzone‑bewuste afspraken?**  
A: Ja, je kunt de `StartTimeZone` en `EndTimeZone` eigenschappen instellen op `MapiCalendar`.

**Q: Kan ik programmatically een enkele instantie uit een terugkerende reeks verwijderen?**  
A: Gebruik de `DeletedInstanceDates` collectie op het herhalingspatroon om specifieke data als verwijderd te markeren.

**Q: Zijn er limieten voor de grootte van een PST‑bestand dat met Aspose.Email wordt gemaakt?**  
A: PST‑bestanden volgen de Unicode‑formaatlimieten (standaard tot 2 GB), maar je kunt grotere groottes configureren via `PersonalStorage`‑instellingen.

**Q: Hoe voeg ik deelnemers toe aan een vergaderverzoek?**  
A: Maak `MapiRecipient`‑objecten aan, stel hun `RecipientType` in op `MapiRecipientType.MAPI_TO`, en voeg ze toe aan de `Recipients`‑collectie van de `MapiMessage`.

**Q: Is er ondersteuning voor terugkerende taken (niet alleen afspraken)?**  
A: Ja, Aspose.Email biedt ook `MapiTask` met vergelijkbare herhalingsmogelijkheden.

**Q: Kan ik deze gids gebruiken als onderdeel van een aspose email tutorial java‑reeks?**  
A: Absoluut – de hier getoonde stappen vormen een kernonderdeel van elke Aspose.Email Java‑tutorial die zich bezighoudt met agenda‑creatie.

## Bronnen
- [Aspose.Email for Java Documentatie](https://reference.aspose.com/email/java/)
- [Aspose.Email downloaden](https://releases.aspose.com/email/java/)
- [Een licentie aanschaffen](https://purchase.aspose.com/buy)
- [Gratis proefversie](https://releases.aspose.com/email/java/)
- [Tijdelijke licentie aanvragen](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Laatst bijgewerkt:** 2026-03-20  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}