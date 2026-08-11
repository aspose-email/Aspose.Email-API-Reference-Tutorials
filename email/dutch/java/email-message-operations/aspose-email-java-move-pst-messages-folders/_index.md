---
date: '2026-08-11'
description: Leer hoe u pst-mappen en -berichten verplaatst met Aspose.Email voor
  Java – een step‑by‑step gids over hoe u pst efficiënt verplaatst.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Leer hoe u pst-mappen en -berichten verplaatst met Aspose.Email voor
  Java in een paar regels code. Deze gids behandelt setup, het verplaatsen van subfolders,
  individuele items en best practices voor grote PST‑bestanden.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Hoe pst-mappen en -berichten te verplaatsen met Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Hoe pst-mappen en -berichten te verplaatsen met Aspose.Email Java
url: /nl/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe pst-mappen en -berichten te verplaatsen met Aspose.Email Java

Efficiënt e‑mailbeheer is essentieel wanneer u grote Outlook‑PST‑bestanden moet reorganiseren. In deze tutorial leert u **hoe pst te verplaatsen** mappen en berichten programmatisch met Aspose.Email voor Java, waardoor geautomatiseerde opschoning, migratie en archivering mogelijk zijn zonder Outlook te starten. Voor volledige API‑details, zie de [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Email for Java  
- **Kan ik zowel mappen als individuele berichten verplaatsen?** Ja – gebruik `moveItem` voor berichten en `moveSubfolders` voor volledige mappen  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose‑licentie is vereist voor commerciële implementaties  
- **Welke Java‑versie wordt aanbevolen?** Java 16 of nieuwer voor optimale prestaties  
- **Is een voorbeeld‑PST‑bestand vereist?** Elk door Outlook gegenereerd PST‑bestand werkt; u kunt er één maken met Outlook of een testbestand gebruiken  

## Wat betekent het verplaatsen van pst in Java‑ontwikkeling?

Het verplaatsen van pst verwijst naar het programmatisch verplaatsen van mappen of e‑mailitems binnen een Personal Storage Table (PST)‑bestand. Dit stelt u in staat om bulk‑opschoning te automatiseren, oude e‑mail te archiveren of inhoud tussen mailstores te migreren zonder handmatige Outlook‑interactie, waardoor de efficiëntie stijgt en menselijke fouten afnemen.

## Waarom Aspose.Email voor Java gebruiken om pst‑gegevens te verplaatsen?

U kunt pst‑gegevens verplaatsen met Aspose.Email omdat het een **pure‑Java API** biedt die op elk besturingssysteem werkt, **meer dan 100 GB** PST‑bestanden ondersteunt en **tot 500 000 items per minuut** verwerkt op standaard serverhardware. De bibliotheek levert bovendien gedetailleerde uitzonderingen, zodat u problemen snel kunt lokaliseren.

## Prerequisites
- Aspose.Email voor Java (nieuwste versie)  
- JDK 16+ (of nieuwer)  
- Maven‑ of Gradle‑buildsysteem  
- Een PST‑bestand voor testen (elk door Outlook gegenereerd bestand)

## Setting up Aspose.Email for Java
Om Aspose.Email te gebruiken, voegt u de Maven‑dependency toe aan uw `pom.xml`‑bestand:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Stappen voor het verkrijgen van een licentie
1. **Gratis proefversie** – begin met een gratis proefversie om de functies van Aspose.Email te verkennen.  
2. **Tijdelijke licentie** – verkrijg een tijdelijke licentie voor uitgebreid gebruik via [Aspose's website](https://purchase.aspose.com/temporary-license/).  
3. **Aankoop** – overweeg een volledige licentie aan te schaffen als de bibliotheek aan uw productiebehoeften voldoet. Voor prijsdetails, zie [Aspose's purchase options](https://purchase.aspose.com/buy).  

### Basisinitialisatie en configuratie
Zorg ervoor dat de bibliotheek correct wordt verwezen voordat u met PST‑bestanden gaat werken:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Hoe pst-mappen en -berichten te verplaatsen
Hieronder staan de kernbewerkingen die u nodig heeft wanneer u **pst‑items** efficiënt wilt verplaatsen.

### Initialiseren en toegang tot PST‑bestand
`PersonalStorage` is de primaire klasse van Aspose.Email voor het openen en manipuleren van PST‑bestanden.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Stap 1: Laad het PST‑bestand
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Stap 2: Toegang tot vooraf gedefinieerde mappen
- **Inbox‑map**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Verwijderde items‑map**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Verplaats een submap naar een andere map in PST
`FolderInfo` vertegenwoordigt een map binnen een PST‑bestand en biedt methoden voor het verplaatsen van submappen.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Stap 1: Toegang tot bron- en doelmappen
```java
pst.moveItem(subfolder, deletedItems);
```

#### Stap 2: Haal een specifieke submap op uit de Inbox
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Stap 3: Verplaats de volledige submap
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Verplaats individuele berichten tussen mappen in PST
`MessageInfoCollection` bevat een verzameling `MessageInfo`‑objecten, elk een e‑mailbericht representerend.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Stap 1: Haal berichten op uit een specifieke submap
```java
inbox.moveSubfolders(deletedItems);
```

#### Stap 2: Verplaats het eerste bericht naar de map Verwijderde items
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Verplaats alle submappen van de ene map naar de andere in PST
`moveSubfolders` verplaatst elke onderliggende map van een bron naar een bestemming in één oproep.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Stap 1: Toegang tot bron- en doelmappen
```java
subfolder.moveContents(deletedItems);
```

#### Stap 2: Verplaats alle submappen
CODE_BLOCK_PLACEHOLDER_15_END

### Verplaats alle inhoud van een submap naar een andere map in PST
`moveAllContents` (een aangepaste lus met `moveItem`) kan elk bericht binnen een submap verplaatsen.

CODE_BLOCK_PLACEHOLDER_16_END

#### Stap 1: Toegang tot bron- en doelmappen
CODE_BLOCK_PLACEHOLDER_17_END

#### Stap 2: Haal een specifieke submap op uit de Inbox
CODE_BLOCK_PLACEHOLDER_18_END

#### Stap 3: Verplaats alle inhoud van de submap
CODE_BLOCK_PLACEHOLDER_19_END

## Praktische toepassingen
Verplaatsen van pst‑mappen en -berichten is nuttig voor:
- **Gegevensmigratie** – verplaats mailboxen van Outlook naar een ander mailsysteem.  
- **E‑mailarchivering** – organiseer oude e‑mail automatisch in archiefmappen.  
- **Opschoningsacties** – ruim inboxen op door verouderde items naar archief‑ of verwijderingsmappen te verplaatsen.

## Prestatieoverwegingen
Bij het verwerken van grote PST‑bestanden met Aspose.Email voor Java, volgt u deze tips:

- **Optimaliseer het gebruik van bronnen** – sluit `PersonalStorage`‑objecten direct af met try‑with‑resources of expliciete `dispose`.  
- **Geheugenbeheer** – verwerk items in batches in plaats van een volledige map in het geheugen te laden; dit vermindert de heap‑belasting op JVM's.  

### Beste praktijken
- Zorg ervoor dat PST‑bronnen na bewerkingen altijd worden vrijgegeven.  
- Controleer of een map bestaat voordat u verplaatsingen probeert om `InvalidOperationException` te voorkomen.  

## Veelgestelde vragen

**Q: Wat is een PST‑bestand?**  
A: Een PST (Personal Storage Table)‑bestand is het propriëtaire Outlook‑formaat voor het lokaal opslaan van e‑mailberichten, contacten, agenda‑items en andere mailbox‑gegevens.

**Q: Kan ik Aspose.Email voor Java gebruiken in commerciële projecten?**  
A: Ja, u kunt het commercieel gebruiken mits u een geldige licentie heeft verkregen via [Aspose's purchase options](https://purchase.aspose.com/buy).

**Q: Hoe ga ik om met uitzonderingen bij het werken met PST‑bestanden met Aspose.Email?**  
A: Omhul uw code met `try‑catch`‑blokken om `IOException`, `InvalidOperationException` of Aspose‑specifieke uitzonderingen af te vangen, log vervolgens de foutdetails of gooi ze opnieuw.

**Q: Wat zijn de systeemvereisten voor het uitvoeren van deze code?**  
A: U heeft JDK 16 of nieuwer nodig en een compatibele IDE zoals IntelliJ IDEA of Eclipse. De Aspose.Email‑JAR moet op het classpath van uw project staan.

**Q: Waar vind ik meer bronnen over Aspose.Email voor Java?**  
A: Bezoek de officiële documentatie op de [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

**Q: Ondersteunt Aspose.Email wachtwoord‑beveiligde PST‑bestanden?**  
A: Ja, u kunt versleutelde PST‑bestanden openen door het wachtwoord mee te geven bij het aanroepen van `PersonalStorage.fromFile`.

**Q: Hoe kan ik verifiëren dat een verplaatsingsoperatie geslaagd is?**  
A: Na het aanroepen van `moveItem` of `moveSubfolders`, vraag de doelmap op met `getContents()` of `getSubFolders()` om de aanwezigheid van de verplaatste items te bevestigen.

## Resources
- **Documentatie**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **API details**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Download**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Purchase**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Free trial**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Temporary license**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Laatst bijgewerkt:** 2026-08-11  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Bulkbijwerken van PST‑berichten met Aspose.Email voor Java: Een uitgebreide gids](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Hoe Outlook PST‑berichten te extraheren met Aspose.Email voor Java: Een volledige gids](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Berichten overzetten tussen PST‑bestanden met Aspose.Email voor Java: Een uitgebreide gids](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}