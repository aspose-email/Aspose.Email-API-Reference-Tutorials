---
date: '2025-12-20'
description: Leer hoe u een MAPI-agenda in Java maakt, dagelijkse terugkeerpatronen
  beheert en uitzonderingen afhandelt met Aspose.Email voor Java.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Maak een MAPI‑kalender in Java met dagelijkse herhaling en uitzonderingen
url: /nl/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je een mapi calendar java met dagelijkse herhaling en uitzonderingen

Het efficiënt beheren van terugkerende gebeurtenissen kan een uitdaging zijn, vooral wanneer uitzonderingen of wijzigingen nodig zijn. In deze tutorial **maak je mapi calendar java** objecten, stel je dagelijkse herhalingspatronen in en voeg je uitzonderingen toe met Aspose.Email for Java. Je leert hoe je plannings taken naadloos kunt automatiseren binnen je applicaties.

## Snelle Antwoorden
- **Welke bibliotheek?** Aspose.Email for Java  
- **Primaire taak?** Maak een MAPI calendar met dagelijkse herhaling en uitzonderingen  
- **Vereiste JDK?** Java 16 of hoger  
- **Kan ik bestanden aan uitzonderingen toevoegen?** Ja, met `MapiCalendarExceptionInfo`  
- **Waar wordt de agenda opgeslagen?** In een PST‑bestand via `PersonalStorage`

### Wat is een MAPI calendar?
Een MAPI (Messaging Application Programming Interface) agenda is een standaardformaat dat door Microsoft Outlook en andere e‑mailclients wordt gebruikt om afspraakgegevens op te slaan. Het ondersteunt uitgebreide herhalingsregels, uitzonderingen en bijlagen, waardoor het ideaal is voor bedrijfsplanning.

### Waarom Aspose.Email for Java gebruiken?
Aspose.Email biedt een pure‑Java API waarmee je MAPI‑objecten kunt maken, wijzigen en opslaan zonder Outlook te gebruiken. Dit betekent dat je server‑side planningsfuncties kunt bouwen, PST‑bestanden kunt genereren en complexe herhalingsscenario's programmatisch kunt afhandelen.

## Vereisten

Zorg er vóór we beginnen voor dat je de volgende configuratie hebt:

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
- **Tijdelijke licentie** – vraag aan voor uitgebreide evaluatie.  
- **Volledige licentie** – koop voor productie‑implementaties.

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

### Een MAPI calendar maken met dagelijkse herhaling en uitzonderingen

#### Overzicht
Deze functie stelt je in staat terugkerende afspraken te automatiseren terwijl je specifieke instanties kunt overslaan of wijzigen.

#### Stapsgewijze implementatie

**1. Stel de startdatum van het evenement in**  
Bepaal wanneer de reeks moet beginnen:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Maak het MAPI Calendar‑object**  
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
Geef een datum op die moet worden uitgesloten (of aangepast):

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

### Bestanden toevoegen aan agenda‑uitzonderingen

#### Overzicht
Je kunt ondersteunende documenten (bijv. agenda’s) toevoegen aan elke uitzondering.

**1. Maak een bestand aan en voeg het toe**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### MAPI Calendar opslaan in PST‑bestanden

#### Overzicht
Bewaar de agenda in een PST‑bestand zodat Outlook of andere clients het kunnen lezen.

**1. Maak en sla de agenda op in een PST**

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
- **Projectmanagement** – volg terugkerende mijlpalen met af en toe datumverschuivingen.  
- **Evenementplanning** – beheer meerdaagse conferenties waarbij sommige sessies worden geannuleerd of verplaatst.

### Integratiemogelijkheden
Combineer Aspose.Email met CRM‑platformen, taak‑management‑API’s of aangepaste workflow‑engines om end‑to‑end automatisering te realiseren.

## Prestatie‑overwegingen
- **Resources vrijgeven** – roep altijd `dispose()` aan op `PersonalStorage` om bestands‑handles vrij te maken.  
- **Streamgebruik** – geef de voorkeur aan `ByteArrayOutputStream` of bestands‑streams om te voorkomen dat volledige PST‑bestanden in het geheugen worden geladen.  
- **Async‑operaties** – voor bulk‑agenda‑generatie, voer de creatielogica uit op een achtergrondthread om de UI responsief te houden.

## Conclusie
Door deze gids te volgen weet je nu hoe je **create mapi calendar java** objecten maakt met dagelijkse herhaling, uitzonderingen toevoegt, bestanden bijvoegt en alles opslaat in een PST‑bestand. Deze mogelijkheden stellen je in staat robuuste planningsfuncties te bouwen zonder ooit direct Outlook aan te raken.

### Volgende stappen
- Experimenteer met wekelijkse of maandelijkse herhalingspatronen.  
- Verken extra MAPI‑eigenschappen zoals deelnemers, herinneringen en categorieën.  
- Bekijk de uitgebreide API‑documentatie van Aspose.Email voor meer geavanceerde scenario’s.

## FAQ‑sectie
1. **Kan ik Aspose.Email gebruiken zonder licentie?**  
   - Ja, je kunt beginnen met de gratis proefversie om de mogelijkheden te verkennen.  
2. **Hoe ga ik om met uitzonderingen in terugkerende gebeurtenissen?**  
   - Gebruik `MapiCalendarExceptionInfo` om de datum, gewijzigde tijden en eventuele bijgevoegde gegevens te definiëren.  
3. **Is het mogelijk agenda’s direct op te slaan in PST‑bestanden?**  
   - Zeker. De `PersonalStorage`‑klasse stelt je in staat PST‑bestanden te maken en agenda‑items toe te voegen.  
4. **Kan dit geïntegreerd worden met andere Java‑applicaties?**  
   - Ja, de API is pure Java, zodat je het kunt embedden in elke Java‑gebaseerde service of desktop‑applicatie.  
5. **Wat moet ik doen als mijn licentie verloopt?**  
   - Vernieuw de licentie via het Aspose‑portaal of schakel tijdelijk terug naar de proefmodus.

## Veelgestelde vragen

**Q: Ondersteunt de bibliotheek tijdzone‑bewuste afspraken?**  
A: Ja, je kunt de `StartTimeZone`‑ en `EndTimeZone`‑eigenschappen instellen op `MapiCalendar`.

**Q: Kan ik programmatically een enkele instantie uit een terugkerende reeks verwijderen?**  
A: Gebruik de `DeletedInstanceDates`‑collectie op het herhalingspatroon om specifieke data als verwijderd te markeren.

**Q: Zijn er limieten voor de grootte van een PST‑bestand dat met Aspose.Email wordt gemaakt?**  
A: PST‑bestanden volgen de Unicode‑formaatlimieten (standaard tot 2 GB), maar je kunt grotere groottes configureren via de `PersonalStorage`‑instellingen.

**Q: Hoe voeg ik deelnemers toe aan een vergaderverzoek?**  
A: Maak `MapiRecipient`‑objecten aan, stel hun `RecipientType` in op `MapiRecipientType.MAPI_TO` en voeg ze toe aan de `Recipients`‑collectie van de `MapiMessage`.

**Q: Is er ondersteuning voor terugkerende taken (niet alleen afspraken)?**  
A: Ja, Aspose.Email biedt ook `MapiTask` met vergelijkbare herhalingsmogelijkheden.

## Bronnen
- [Aspose.Email for Java Documentatie](https://reference.aspose.com/email/java/)  
- [Aspose.Email downloaden](https://releases.aspose.com/email/java/)  
- [Een licentie aanschaffen](https://purchase.aspose.com/buy)  
- [Gratis proefversie](https://releases.aspose.com/email/java/)  
- [Tijdelijke licentie aanvragen](https://purchase.aspose.com/temporary-license/)  
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose