---
date: '2026-02-22'
description: Leer hoe u een follow‑up‑vlag in Outlook instelt met Aspose.Email voor
  Java, inclusief het instellen, lezen en verwijderen van vlaggen voor ontvangers.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Hoe een Outlook Follow‑up‑vlag in te stellen met Aspose.Email voor Java
url: /nl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een Outlook Follow Up Flag in te stellen met Aspose.Email voor Java

## Introductie
Als je ooit moeite hebt gehad om belangrijke e‑mails bij te houden, weet je hoe waardevol de **outlook follow up flag** van Outlook kan zijn. In deze gids laten we zien **hoe een outlook follow up flag** programmatisch in te stellen met Aspose.Email voor Java, en behandelen we ook hoe **een outlook follow up flag voor ontvangers** in te stellen, evenals hoe **een outlook follow up flag** te **verwijderen** wanneer een taak is voltooid. Aan het einde kun je taaktracking, herinneringen en audit‑trails automatiseren rechtstreeks vanuit je Java‑code.

**Wat je zult leren**
- Maak en pas een follow‑up flag toe op een Outlook‑bericht.  
- Stel follow‑up flags in voor specifieke ontvangers.  
- Markeer een flag als voltooid en verwijder deze later.  
- Lees flag‑opties voor rapportage of compliance.  

Laten we de omgeving gereedmaken voordat we in de code duiken.

## Snelle antwoorden
- **Wat betekent “how to set follow‑up”?** Een flag toevoegen met start‑, herinnerings‑ en vervaldatum aan een Outlook‑item.  
- **Welke bibliotheek is vereist?** Aspose.Email for Java (v25.4 of nieuwer).  
- **Heb ik een licentie nodig?** Ja, een proef‑ of aangekochte licentie is vereist voor volledige functionaliteit.  
- **Kan ik flags alleen voor ontvangers instellen?** Absoluut – gebruik `FollowUpManager.setFlagForRecipients`.  
- **Is het mogelijk om later een flag te verwijderen?** Ja, roep `FollowUpManager.clearFlag` aan.

## Wat is een Outlook Follow Up Flag?
Een Outlook follow up flag is een ingebouwde taakmarkering die een startdatum, een herinnering en een vervaldatum kan koppelen aan elk mail‑item. Het verandert een gewone e‑mail in een getraceerd actie‑item, waardoor jij en je team op de hoogte blijven van lopende werkzaamheden.

## Waarom Aspose.Email voor Java gebruiken?
Aspose.Email biedt een pure‑Java API die werkt zonder dat Outlook geïnstalleerd is, waardoor je .msg‑bestanden kunt manipuleren, flags kunt instellen en taken kunt beheren op elk platform—perfect voor **automate outlook tasks**, backend‑services, of integratie met project‑management tools.

## Voorvereisten
- **Aspose.Email for Java** versie 25.4 of later (ook bekend als **aspose email java**).  
- **JDK 16+** geïnstalleerd.  
- Maven‑compatibele IDE (IntelliJ IDEA, Eclipse, etc.).  
- Basiskennis van Java en bekendheid met e‑mailconcepten.

## Setting Up Aspose.Email for Java
### Maven Configuration
Voeg de volgende afhankelijkheid toe aan uw `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email requires a license for production use:

- **Gratis proefversie** – 30‑daagse evaluatie.  
- **Tijdelijke licentie** – uitgebreide test.  
- **Volledige licentie** – eeuwigdurende abonnement.

Initialiseer de licentie vóór enige e‑mailbewerking:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*We bouwen eerst een `MailMessage`, stellen afzender/ontvanger in, en converteren deze vervolgens naar een `MapiMessage` voor flag‑manipulatie.*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier stellen we de start‑, herinnerings‑ (de **outlook flag reminder**) en vervaldatums in met behulp van de `Calendar`‑klasse.*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Het `FollowUpOptions`‑object bevat alle flag‑details, die we toepassen met `FollowUpManager.setOptions`.*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Het bericht wordt opgeslagen als een `.msg`‑bestand met de flag eraan bevestigd.*

## How to Set Flag for Recipients (Feature 2)
### Overview
Soms moet de flag alleen **voor ontvangers** verschijnen. In dit voorbeeld wordt het bericht eerst gemarkeerd als concept, waarna de flag wordt toegevoegd.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Het markeren van het bericht als niet‑verzonden zorgt ervoor dat Outlook het als een concept behandelt.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*De flag is nu alleen zichtbaar voor de ontvangers – een klassiek **flag for recipients**‑scenario.*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*De flag‑status verandert naar “Completed” en het bijgewerkte bestand wordt opgeslagen.*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Het bericht wordt opgeslagen zonder enige follow‑up flag.*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Het `options`‑object bevat nu start‑, verval‑ en herinneringsdatums, plus het flag‑onderwerp – handig wanneer u **read flag options** moet lezen voor rapportage.*

## Practical Applications
- **Task‑Management Integratie:** Gesynchroniseerde gemarkeerde e‑mails met Jira, Trello of Azure Boards.  
- **Geautomatiseerde herinneringen:** Genereer dagelijkse herinnerings‑e‑mails voor openstaande follow‑ups.  
- **Compliance‑audits:** Exporteer flag‑gegevens voor regelgeving‑rapportage.

## Performance Considerations
- **Datumcalculaties:** Bereken datums één keer per batch in plaats van binnen lussen.  
- **Resource‑beheer:** Sluit eventuele streams of bestands‑handles na het opslaan van berichten.  
- **Geheugengebruik:** Verwerk grote mailboxen in delen om heap‑druk te vermijden.

## Common Issues and Solutions
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Flag verschijnt niet in Outlook | Bericht opgeslagen zonder juiste `MessageFlags` | Zorg ervoor dat `setMessageFlags` is ingesteld op `MSGFLAG_UNSENT` voordat u ontvanger‑flags toepast. |
| Opslaan geeft `AccessDeniedException` | Onjuist bestandspad of ontbrekende schrijfrechten | Controleer of de uitvoermap bestaat en de applicatie schrijfrechten heeft. |
| Datums liggen één dag af | Tijdzone‑mismatch | Gebruik consistent `TimeZone.getTimeZone("GMT")` of uw lokale zone. |

## Frequently Asked Questions
**V: Wat is Aspose.Email voor Java?**  
A: Het is een pure‑Java API waarmee u e‑mailbestanden (MSG, EML, etc.) kunt maken, lezen en manipuleren zonder dat Outlook geïnstalleerd hoeft te zijn.

**V: Hoe krijg ik een gratis proeflicentie?**  
A: Bezoek de [Aspose-website](https://releases.aspose.com/email/java/) om een 30‑daagse proefversie te downloaden.

**V: Kan ik meerdere follow‑up flags op één bericht instellen?**  
A: Outlook ondersteunt slechts één flag per bericht, maar u kunt extra taakgegevens opslaan in aangepaste MAPI‑eigenschappen.

**V: Mijn bericht wordt niet opgeslagen na het instellen van een flag. Wat moet ik controleren?**  
A: Controleer of het pad `outputDir` geldig is en of de applicatie toestemming heeft om naar die locatie te schrijven.

**V: Hoe kan ik flags van veel berichten tegelijk verwijderen?**  
A: Loop door uw berichtcollectie en roep `FollowUpManager.clearFlag` aan voor elke `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Laatst bijgewerkt:** 2026-02-22  
**Getest met:** Aspose.Email for Java 25.4 (jdk16)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}