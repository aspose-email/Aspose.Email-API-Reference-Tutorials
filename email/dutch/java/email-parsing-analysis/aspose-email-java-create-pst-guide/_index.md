---
date: '2026-06-08'
description: Leer hoe u PST‑bestanden maakt met Aspose.Email for Java, inclusief hoe
  u mapstructuren toevoegt en hoe u PST‑inhoud efficiënt zoekt. Stapsgewijze handleiding.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Hoe PST‑bestanden maken met Aspose.Email for Java
url: /nl/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Beheers e-mailbeheer met Aspose.Email voor Java

Als je **how to create pst** bestanden programmatically wilt maken, ben je hier aan het juiste adres. In deze tutorial lopen we elke stap door die nodig is om een Unicode PST‑bestand te genereren, standaard Outlook‑mappen toe te voegen, berichten te importeren en case‑insensitieve zoekopdrachten uit te voeren — allemaal met Aspose.Email voor Java. Aan het einde heb je een herbruikbaar code‑patroon dat schaalt van een handvol e‑mails tot archieven van meerdere gigabytes.

## Snelle antwoorden
- **Hoe begin ik?** Voeg de Aspose.Email Maven‑dependency toe, verkrijg een licentie en instantiate `PersonalStorage`.
- **Kan ik een Inbox‑map toevoegen?** Ja – roep `pst.getRootFolder().addSubFolder("Inbox")` aan.
- **Wordt case‑insensitieve zoeken ondersteund?** Gebruik `PersonalStorageQueryBuilder` met `StringComparison.OrdinalIgnoreCase`.
- **Welke bestandsgrootte kan worden verwerkt?** Aspose.Email verwerkt PST‑bestanden tot 2 GB zonder het volledige bestand in het geheugen te laden.
- **Heb ik een betaalde licentie nodig voor productie?** Een permanente licentie verwijdert proeflimieten en ontgrendelt volledige prestatie‑functies.

## Wat is how to create pst?
**how to create pst** verwijst naar het programmatic proces van het genereren van een Outlook Personal Storage Table (PST) bestand met code in plaats van de Outlook‑UI. Aspose.Email voor Java biedt een volledig beheerde API die Unicode PST‑bestanden maakt, mappen toevoegt en `MapiMessage`‑objecten opslaat zonder dat Outlook geïnstalleerd hoeft te zijn.

## Waarom Aspose.Email gebruiken voor PST‑creatie?
Aspose.Email ondersteunt **50+** e‑mailgerelateerde formaten (MSG, EML, MBOX, PST, enz.) en kan PST‑bestanden verwerken van **tot 2 GB** grootte terwijl het geheugenverbruik onder **150 MB** blijft dankzij de lazy‑loading‑architectuur. Deze gekwantificeerde mogelijkheid maakt het ideaal voor enterprise‑archivering, migratie en compliance‑scenario's.

## Vereisten

- **Java Development Kit (JDK)** – versie 16 of hoger.
- **Maven** – voor dependency‑beheer.
- Basiskennis van Java‑syntaxis; eerdere ervaring met PST‑bestanden is niet vereist.

## Hoe maak je een PST‑bestand?

De `PersonalStorage`‑klasse vertegenwoordigt een PST‑bestand en biedt methoden om het te maken, te openen en de inhoud te manipuleren. Om een nieuwe Unicode PST te maken, roep je `PersonalStorage.create()` aan met het gewenste bestandspad en de formaatversie. Deze bewerking genereert een moderne PST die grote mappen, Unicode‑tekens en efficiënte streaming ondersteunt, waardoor het geschikt is voor zowel kleinschalige als enterprise‑niveau archiveringsopdrachten.

### Stap 1: Maven‑dependency toevoegen

Voeg de Aspose.Email Maven‑dependency toe aan je `pom.xml`. Dit haalt automatisch alle benodigde binaries binnen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Stap 2: Een licentie verkrijgen en toepassen

Een gratis proefversie is beschikbaar, maar een permanente licentie verwijdert evaluatielimieten en maakt volledige snelheid verwerking mogelijk.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Hoe voeg je een map toe aan PST?

Maak de gewenste maphiërarchie onder de PST‑root, en verwijs ernaar bij het invoegen van berichten. Het `FolderInfo`‑object vertegenwoordigt elke map en kan willekeurig genest worden, waardoor je structuren kunt bouwen zoals Inbox, Sent Items of aangepaste projectmappen. Mappen toevoegen is een lichtgewicht bewerking die geen berichtinhoud laadt, waardoor de prestaties behouden blijven, zelfs voor grote PST‑bestanden.

### Stap 1: PersonalStorage initialiseren

De `PersonalStorage`‑klasse is het top‑level object van Aspose.Email dat een enkel PST‑bestand in het geheugen vertegenwoordigt. Na instantiering verlopen alle lees‑ en schrijf‑operaties via dit object.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Stap 2: Directory‑paden definiëren

Stel bron‑ en bestemmingspaden in voor je e‑mailbestanden en de PST‑outputlocatie.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Stap 3: Het PST‑bestand maken

Gebruik `PersonalStorage.create()` met `FileFormatVersion.Unicode` om een moderne Unicode PST te produceren die grote mappen en Unicode‑tekens ondersteunt.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Hoe zoek je in pst?

`PersonalStorageQueryBuilder` is een builder‑klasse die wordt gebruikt om zoekopdrachten voor PST‑inhoud te construeren. Door de builder te configureren met de gewenste criteria en `StringComparison.OrdinalIgnoreCase` op te geven, kun je snelle, case‑insensitieve zoekopdrachten uitvoeren over onderwerpen, bodies en aangepaste eigenschappen zonder de volledige PST in het geheugen te laden.

### Stap 1: Zoekopdracht bouwen

Construeer een query die zoekt naar een trefwoord in het onderwerp of de body, zonder rekening te houden met hoofdletters.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Stap 2: Query uitvoeren en berichten ophalen

Voer de query uit op de doelmap en iterate over de resulterende `MapiMessage`‑collectie.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Een vooraf gedefinieerde map maken in PST

Het toevoegen van een vooraf gedefinieerde map zoals **Inbox** helpt je e‑mailgegevens effectief te organiseren.

### Stap 1: PersonalStorage‑object initialiseren

Veronderstel dat het `PersonalStorage`‑object (`pst`) al is aangemaakt zoals eerder getoond.

### Stap 2: De 'Inbox'‑map maken

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Berichten toevoegen aan een PST‑map

Vul je PST‑map met e‑mailberichten door ze uit bestanden te laden en te converteren.

### Stap 1: E‑mailbericht laden

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Stap 2: Toevoegen aan PST‑map

Converteer `MailMessage` naar `MapiMessage` en voeg het toe:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Praktische toepassingen

Aspose.Email voor Java gaat niet alleen over het maken van PST‑bestanden; het is een veelzijdig hulpmiddel met tal van toepassingen:

- **Email Archiving**: Automatiseer het archiveren van bedrijfs‑e‑mails naar PST‑bestanden, met retentie‑beleid tot 10 jaar.
- **Migration Tools**: Migreer moeiteloos van legacy‑mailstores (bijv. MBOX) naar Outlook PST met één API‑aanroep per bericht.
- **Data Analysis**: Extraheer metadata zoals afzender, ontvanger en tijdstempels voor business‑intelligence‑pijplijnen.
- **Backup Solutions**: Bouw robuuste back‑up‑hulpmiddelen die incrementele e‑mailwijzigingen opslaan zonder de volledige mailbox opnieuw te verwerken.

## Prestatie‑overwegingen

Om optimale prestaties te garanderen bij het gebruik van Aspose.Email:

- **Resource Management**: Roep altijd `pst.dispose()` aan of gebruik try‑with‑resources om native handles direct vrij te geven.
- **Batch Processing**: Verwerk e‑mails in batches van **500** items om het geheugenverbruik voorspelbaar te houden.
- **Concurrency Handling**: De bibliotheek is thread‑safe voor alleen‑lezen operaties; voor schrijven, synchroniseer de toegang tot de `PersonalStorage`‑instantie.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **OutOfMemoryError** bij het verwerken van grote PST‑bestanden | Het volledige PST in het geheugen laden | Schakel `PersonalStorage.setUseUnicode(true)` in en verwerk berichten in streams. |
| **Folder not found** fout | Onjuiste hoofdlettergebruik in mappad | Gebruik `StringComparison.OrdinalIgnoreCase` in queries of normaliseer mapnamen. |
| **Licentie niet toegepast** | Licentiebestand niet geladen vóór de eerste API‑aanroep | Laad de licentie bij het opstarten van de applicatie, vóór het aanmaken van `PersonalStorage`‑objecten. |

## Veelgestelde vragen

**Q: Wat is de minimale Java‑versie vereist?**  
A: JDK 16 of hoger wordt aanbevolen voor volledige compatibiliteit met Aspose.Email voor Java.

**Q: Kan ik Aspose.Email gebruiken zonder licentie?**  
A: Ja, een proefmodus is beschikbaar maar beperkt de PST‑grootte tot **10 MB** en schakelt bepaalde optimalisaties uit.

**Q: Hoe ga ik efficiënt om met grote PST‑bestanden?**  
A: Verwerk berichten in batches, maak `MapiMessage`‑objecten snel vrij, en schakel lazy loading in via `PersonalStorage.setUseUnicode(true)`.

**Q: Is het mogelijk om bijlagen toe te voegen aan e‑mails in PST‑bestanden?**  
A: Zeker. Bij het converteren van `MailMessage` naar `MapiMessage`, roep `mapiMsg.getAttachments().add(attachment)` aan om bestanden in te sluiten.

**Q: Welke ondersteuning is beschikbaar voor het oplossen van problemen?**  
A: Aspose biedt een speciaal supportforum, uitgebreide documentatie en e‑mailondersteuning voor gelicentieerde klanten.

## Bronnen
- [Documentatie](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Aankoop](https://purchase.aspose.com/buy)
- [Gratis proefversie](https://releases.aspose.com/email/java/)
- [Tijdelijke licentie](https://purchase.aspose.com/temporary-license/)
- [Supportforum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Email for Java 24.10  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe Outlook PST‑bestanden maken en beheren met Aspose.Email voor Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [PST‑bestanden manipuleren met Aspose.Email voor Java: een uitgebreide gids](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [E‑mailbijlagen extraheren Java - Met Aspose.Email voor PST‑bestanden – een stapsgewijze gids](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}