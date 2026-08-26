---
date: '2026-07-27'
description: Leer hoe u Outlook‑vlag in Java kunt instellen met Aspose.Email voor
  Java, inclusief het maken van vlaggen, vlaggen voor ontvangers, voltooien, verwijderen
  en leesopties.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Stel Outlook‑vlag in Java in met Aspose.Email voor Java. Deze gids
  laat zien hoe u Outlook‑follow‑up‑vlaggen efficiënt kunt maken, lezen, voltooien
  en verwijderen.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Outlook‑vlag instellen in Java – Complete Aspose.Email programmeergids
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Outlook‑vlag instellen in Java – Complete Aspose.Email programmeergids
url: /nl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook‑vlag instellen in Java met Aspose.Email voor Java

## Inleiding
Als je programmatisch **set outlook flag java** moet instellen, ben je hier aan het juiste adres. De follow‑up‑vlag van Outlook maakt van een gewone e‑mail een getraceerde taak, en Aspose.Email voor Java stelt je in staat die vlaggen te beheren zonder Outlook geïnstalleerd te hebben. In deze tutorial lopen we door het maken, lezen, voltooien en uiteindelijk verwijderen van vlaggen, plus hoe je vlaggen toepast voor specifieke ontvangers. Aan het einde heb je een herbruikbare Java‑snippet die taaktracking automatiseert direct vanuit je backend‑services.

## Snelle antwoorden
- **Wat betekent “set outlook flag java”?** Een vlag toevoegen met start-, herinnerings- en vervaldatums aan een Outlook‑item via Java‑code.  
- **Welke bibliotheek is vereist?** Aspose.Email for Java (v25.4 or newer).  
- **Heb ik een licentie nodig?** Ja – een proefversie werkt voor evaluatie, maar een aangeschafte licentie is vereist voor productie.  
- **Kan ik vlaggen alleen voor ontvangers instellen?** Absoluut – gebruik `FollowUpManager.setFlagForRecipients`.  
- **Is het later mogelijk om een vlag te verwijderen?** Ja – roep `FollowUpManager.clearFlag` aan.

## Wat is een Outlook‑follow‑up‑vlag?
De Outlook‑follow‑up‑vlag is een ingebouwde taakmarkering die een startdatum, een herinnering en een vervaldatum kan koppelen aan elk mailitem. Het maakt van een e‑mail een getraceerd actie‑item, waardoor jij en je team op de hoogte blijven van lopende werkzaamheden.

## Waarom Aspose.Email voor Java gebruiken?
Aspose.Email voor Java ondersteunt **70+ e‑mailformaten** (inclusief MSG, EML, MHTML en TNEF) en kan **meer dan 100.000 berichten per minuut** verwerken op een typische 8‑core server, allemaal zonder Outlook op de hostmachine te vereisen. Dit maakt het ideaal voor backend‑automatisering, compliance‑rapportage en integratie met project‑managementtools.

## Vereisten
- **Aspose.Email for Java** versie 25.4 of later.  
- **JDK 16+** geïnstalleerd.  
- Maven‑compatibele IDE (IntelliJ IDEA, Eclipse, enz.).  
- Basiskennis van Java en vertrouwdheid met e‑mailconcepten.

## Aspose.Email voor Java configureren
### Maven‑configuratie
Voeg de volgende afhankelijkheid toe aan je `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie
Aspose.Email vereist een licentie voor productiegebruik:
- **Gratis proefversie** – 30‑daagse evaluatie.  
- **Tijdelijke licentie** – uitgebreide testfase.  
- **Volledige licentie** – eeuwigdurende abonnement.

Initialiseer de licentie vóór enige e‑mailbewerking:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook‑vlag instellen in Java (Functie 1)
### Direct antwoord
Laad een `MailMessage`, converteer deze naar een `MapiMessage`, configureer `FollowUpOptions` en roep `FollowUpManager.setOptions` aan. Deze reeks maakt een volledig gemarkeerd Outlook‑item in slechts een paar regels Java‑code.

### Stap 1: Maak en initialiseert het bericht
`MailMessage` is de high‑level klasse van Aspose.Email die een e‑mail vertegenwoordigt. Nadat je het bericht hebt opgebouwd, converteer je het naar een `MapiMessage` voor vlagmanipulatie.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*We bouwen eerst een `MailMessage`, stellen afzender/ontvanger in, en converteren vervolgens naar een `MapiMessage` voor vlagmanipulatie.*

### Stap 2: Definieer follow‑up‑datums (Outlook‑vlagherinnering)
`FollowUpOptions` bevat de start-, herinnerings- en vervaldatums. Gebruik Java’s `Calendar` om precieze tijdstempels in te stellen.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier stellen we de start-, herinnerings‑ (de **outlook‑vlagherinnering**) en vervaldatums in met behulp van de `Calendar`‑klasse.*

### Stap 3: Pas follow‑up‑opties toe
De `FollowUpManager.setOptions`‑methode voegt de vlag toe aan de `MapiMessage`.

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Het `FollowUpOptions`‑object bevat alle vlagdetails, die we toepassen met `FollowUpManager.setOptions`.*

### Stap 4: Sla het bericht op
Sla het gemarkeerde bericht op als een `.msg`‑bestand zodat Outlook de vlag kan weergeven.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Het bericht wordt opgeslagen als een `.msg`‑bestand met de vlag eraan toegevoegd.*

## Hoe vlag voor ontvangers instellen (Functie 2)?
Gebruik `FollowUpManager.setFlagForRecipients` nadat je het bericht als concept hebt gemarkeerd. Deze methode voegt de follow‑up‑vlag alleen toe aan de kopie van de ontvanger, waardoor de weergave van de afzender ongewijzigd blijft. Het vereist dat `MessageFlags.MSGFLAG_UNSENT` wordt ingesteld vóór het toepassen van de vlag. Je kunt ook de start‑, herinnerings‑ en vervaldatums aanpassen met een `FollowUpOptions`‑object voordat je de methode aanroept.

### Direct antwoord
Markeer het bericht als concept met `MessageFlags.MSGFLAG_UNSENT`, roep vervolgens `FollowUpManager.setFlagForRecipients` aan. Outlook toont de vlag alleen aan de ontvangers, niet aan de afzender.

### Overzicht
Soms moet de vlag **alleen voor ontvangers** verschijnen. Dit voorbeeld markeert het bericht eerst als concept, en voegt vervolgens de vlag toe.

#### Stap 1: Markeer als concept
`MessageFlags` is een MAPI‑enumeratie die de status van het bericht regelt. Het instellen van `MSGFLAG_UNSENT vertelt Outlook dat het item een concept is.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Het markeren van het bericht als niet‑verzonden zorgt ervoor dat Outlook het als concept behandelt.*

#### Stap 2: Stel ontvanger‑vlag in
`FollowUpManager.setFlagForRecipients` voegt de vlag uitsluitend toe aan de kopie van de ontvanger.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*De vlag is nu alleen zichtbaar voor de ontvangers – een klassiek **vlag‑voor‑ontvangers** scenario.*

## Hoe een Outlook‑follow‑up‑vlag markeren als voltooid (Functie 3)?
Laad het .msg‑bestand in een `MapiMessage`, roep vervolgens `FollowUpManager.completeFlag` aan. Dit werkt de vlagstatus bij naar Voltooid en voegt een vinkje toe in Outlook. Na het voltooien, sla je het bericht op om de wijziging te behouden. Je kunt ook de voltooid‑tijd instellen door de `FlagCompleteTime`‑eigenschap aan te passen indien nodig voor auditdoeleinden.

### Direct antwoord
Laad het bestaande `.msg`‑bestand in een `MapiMessage`, roep `FollowUpManager.completeFlag` aan, en sla het bestand op. De vlagstatus verandert naar “Completed” en verschijnt met een vinkje in Outlook.

### Stap 1: Laad het bericht
`MapiMessage` kan een opgeslagen `.msg`‑bestand lezen, waardoor je volledige toegang krijgt tot de MAPI‑eigenschappen.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Stap 2: Markeer als voltooid en sla op
`FollowUpManager.completeFlag` werkt de vlagstatus bij, waarna je de wijzigingen opslaat.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*De vlagstatus verandert naar “Completed” en het bijgewerkte bestand wordt opgeslagen.*

## Hoe een Outlook‑follow‑up‑vlag verwijderen (Functie 4)?
Open het .msg‑bestand met `MapiMessage`, roep `FollowUpManager.clearFlag` aan, en sla vervolgens het bericht op. Dit verwijdert alle vlag‑gerelateerde MAPI‑eigenschappen, zodat Outlook geen follow‑up‑indicator meer toont. Gebruik dit wanneer een taak wordt geannuleerd of niet meer relevant is. Zorg er ook voor dat je eventuele aangepaste herinnerings‑eigenschappen wist om resterende meldingen te voorkomen.

### Direct antwoord
Open het `.msg`‑bestand met `MapiMessage`, roep `FollowUpManager.clearFlag` aan, en sla het bestand op. Het bericht zal geen enkele follow‑up‑indicator meer tonen in Outlook.

### Stap 1: Laad en verwijder vlag
`FollowUpManager.clearFlag` verwijdert alle vlag‑gerelateerde eigenschappen van het bericht.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Het bericht wordt opgeslagen zonder enige follow‑up‑vlag.*

## Hoe vlagopties lezen (Functie 5)?
Roep `FollowUpManager.getOptions` aan op een geladen `MapiMessage` om een `FollowUpOptions`‑object te verkrijgen. Dit object levert de start‑, verval‑ en herinneringsdatums, en het vlag‑onderwerp, waardoor je de vlagdetails kunt weergeven of loggen. Het is nuttig voor rapportage en compliance‑audits.

### Direct antwoord
Gebruik `FollowUpManager.getOptions` op een geladen `MapiMessage` om een `FollowUpOptions`‑object op te halen dat start‑, verval‑, herinneringsdatums en het vlag‑onderwerp bevat. Dit is nuttig voor rapportage of compliance‑audits.

### Stap 1: Opties ophalen
Het geretourneerde `options`‑object geeft je volledige inzage in de configuratie van de vlag.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Het `options`‑object bevat nu start‑, verval‑ en herinneringsdatums, plus het vlag‑onderwerp – nuttig wanneer je **vlagopties moet lezen** voor rapportage.*

## Praktische toepassingen
- **Integratie met taak‑beheer:** Synchroniseer gemarkeerde e‑mails met Jira, Trello of Azure Boards.  
- **Geautomatiseerde herinneringen:** Genereer dagelijkse herinnerings‑e‑mails voor openstaande follow‑ups.  
- **Compliance‑audits:** Exporteer vlaggegevens voor regelgeving‑rapportage, gebruikmakend van de mogelijkheid om vlagopties programmatisch te lezen.

## Prestatie‑overwegingen
- **Datum‑berekeningen:** Bereken datums één keer per batch in plaats van binnen lussen.  
- **Resource‑beheer:** Sluit alle streams of bestands‑handles na het opslaan van berichten.  
- **Geheugengebruik:** Verwerk grote mailboxen in delen om heap‑druk te vermijden; Aspose.Email kan multi‑honderd‑pagina mailboxen aan zonder het volledige bestand in het geheugen te laden.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Vlag verschijnt niet in Outlook | Bericht opgeslagen zonder juiste `MessageFlags` | Zorg ervoor dat `setMessageFlags` is ingesteld op `MSGFLAG_UNSENT` vóór het toepassen van ontvanger‑vlaggen. |
| Opslaan geeft `AccessDeniedException` | Onjuist bestandspad of ontbrekende schrijfrechten | Controleer of de uitvoermap bestaat en de applicatie schrijfrechten heeft. |
| Datums liggen één dag af | Tijdzone‑mismatch | Gebruik consequent `TimeZone.getTimeZone("GMT")` of je lokale zone. |

## Veelgestelde vragen
**V: Wat is Aspose.Email voor Java?**  
A: Het is een pure‑Java‑API die je in staat stelt e‑mailbestanden (MSG, EML, enz.) te maken, lezen en manipuleren zonder Outlook geïnstalleerd te hebben.

**V: Hoe krijg ik een gratis proeflicentie?**  
A: Bezoek de [Aspose-website](https://releases.aspose.com/email/java/) om een 30‑daagse proefversie te downloaden.

**V: Kan ik meerdere follow‑up‑vlaggen op één bericht instellen?**  
A: Outlook ondersteunt slechts één vlag per bericht, maar je kunt extra taakgegevens opslaan in aangepaste MAPI‑eigenschappen.

**V: Mijn bericht wordt niet opgeslagen na het instellen van een vlag. Wat moet ik controleren?**  
A: Controleer of het pad `outputDir` geldig is en of de applicatie toestemming heeft om naar die locatie te schrijven.

**V: Hoe kan ik vlaggen van veel berichten tegelijk verwijderen?**  
A: Loop door je berichtcollectie en roep `FollowUpManager.clearFlag` aan op elke `MapiMessage`.

## Bronnen
- [Documentatie](https://reference.aspose.com/email/java/)
- [Aspose.Email voor Java downloaden](https://releases.aspose.com/email/java/)
- [Aspose.Email gratis proefversie](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Laatst bijgewerkt:** 2026-07-27  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials
- [Outlook-categorieën beheren met Aspose.Email voor Java - Een uitgebreide gids](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Outlook-notities maken in Java met Aspose.Email – Volledige gids](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Taken maken in Microsoft Exchange met Aspose.Email voor Java: Een volledige gids](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}