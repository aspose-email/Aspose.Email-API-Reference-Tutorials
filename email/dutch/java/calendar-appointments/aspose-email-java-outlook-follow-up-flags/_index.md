---
date: '2025-12-19'
description: Leer hoe u follow‑up‑vlaggen in Outlook kunt instellen met Aspose.Email
  voor Java, inclusief hoe u een Outlook follow‑up‑vlag kunt instellen en efficiënt
  een Outlook follow‑up‑vlag kunt verwijderen.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Hoe follow-up vlaggen in Outlook instellen met Aspose.Email voor Java
url: /nl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe follow‑up‑vlaggen in Outlook instellen met Aspose.Email voor Java

## Inleiding
Als je ooit moeite hebt gehad om belangrijke e‑mails bij te houden, weet je hoe waardevol Outlook‑follow‑up‑vlaggen kunnen zijn. In deze gids laten we **hoe follow‑up in te stellen** vlaggen programmatisch met Aspose.Email voor Java zien, en behandelen we ook hoe je **outlook follow‑up‑vlag instelt** voor ontvangers, evenals hoe je **outlook follow‑up‑vlag verwijdert** wanneer een taak is voltooid. Aan het einde kun je taaktracking, herinneringen en audit‑trails automatiseren rechtstreeks vanuit je Java‑code.

**Wat je zult leren**
- Maak en pas een follow‑up‑vlag toe op een Outlook‑bericht.  
- Stel follow‑up‑vlaggen in voor specifieke ontvangers.  
- Markeer een vlag als voltooid en verwijder deze later.  
- Lees vlagopties voor rapportage of compliance.  

Laten we de omgeving gereedmaken voordat we in de code duiken.

## Snelle antwoorden
- **Wat betekent “how to set follow-up”?** Een vlag toevoegen met start‑, herinnerings‑ en vervaldatums aan een Outlook‑item.  
- **Welke bibliotheek is vereist?** Aspose.Email for Java (v25.4 of nieuwer).  
- **Heb ik een licentie nodig?** Ja, een proef‑ of aangeschafte licentie is vereist voor volledige functionaliteit.  
- **Kan ik vlaggen alleen voor ontvangers instellen?** Absoluut – gebruik `FollowUpManager.setFlagForRecipients`.  
- **Is het mogelijk om later een vlag te verwijderen?** Ja, roep `FollowUpManager.clearFlag` aan.

## Wat is een Follow‑Up‑vlag?
Een follow‑up‑vlag is een Outlook‑functie die een e‑mail markeert als een taak, met optioneel start‑, herinnerings‑ en vervaldatums. Het helpt jou en je team om bovenop lopende acties te blijven.

## Waarom Aspose.Email voor Java gebruiken?
Aspose.Email biedt een pure‑Java‑API die werkt zonder dat Outlook geïnstalleerd is, waardoor je .msg‑bestanden kunt manipuleren, vlaggen kunt instellen en taken kunt beheren op elk platform—perfect voor backend‑services, geautomatiseerde workflows of integratie met project‑managementtools.

## Vereisten
- **Aspose.Email for Java** versie 25.4 of later.  
- **JDK 16+** geïnstalleerd.  
- Maven‑compatibele IDE (IntelliJ IDEA, Eclipse, enz.).  
- Basiskennis van Java en vertrouwdheid met e‑mailconcepten.

## Aspose.Email voor Java instellen
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
- **Tijdelijke licentie** – uitgebreid testen.  
- **Volledige licentie** – eeuwigdurende abonnement.

Initialiseer de licentie vóór enige e‑mailbewerking:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementatie‑gids

### Hoe follow‑up‑vlaggen instellen (Feature 1)
#### Overzicht
Deze sectie leidt je door het maken van een Outlook‑bericht, het definiëren van start‑/herinnerings‑/vervaldatums en het toepassen van een follow‑up‑vlag.

#### Stap 1: Maak en initialiseert het bericht
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*We bouwen eerst een `MailMessage`, stellen afzender/ontvanger in, en converteren deze vervolgens naar een `MapiMessage` voor vlagmanipulatie.*

#### Stap 2: Definieer follow‑up‑datums
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier stellen we de start‑, herinnerings‑ en vervaldatums in met behulp van de `Calendar`‑klasse.*

#### Stap 3: Pas follow‑up‑opties toe
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Het `FollowUpOptions`‑object bevat alle vlagdetails, die we toepassen met `FollowUpManager.setOptions`.*

#### Stap 4: Sla het bericht op
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Het bericht wordt opgeslagen als een `.msg`‑bestand met de vlag eraan gekoppeld.*

### Outlook follow‑up‑vlag voor ontvangers instellen (Feature 2)
#### Overzicht
Soms moet je een bericht alleen voor de ontvangers markeren. Dit voorbeeld markeert het bericht eerst als concept en voegt vervolgens de vlag toe.

#### Stap 1: Markeer als concept
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Het bericht als niet‑verzonden markeren zorgt ervoor dat Outlook het als concept behandelt.*

#### Stap 2: Stel ontvanger‑vlag in
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*De vlag is nu alleen zichtbaar voor de ontvangers.*

### Outlook follow‑up‑vlag als voltooid markeren (Feature 3)
#### Overzicht
Wanneer een taak is voltooid, kun je de vlag programmatisch als voltooid markeren.

#### Stap 1: Laad het bericht
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Stap 2: Markeer als voltooid en sla op
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*De vlagstatus verandert naar “Completed” en het bijgewerkte bestand wordt opgeslagen.*

### Outlook follow‑up‑vlag verwijderen (Feature 4)
#### Overzicht
Als een vlag niet meer nodig is, kun je deze volledig verwijderen.

#### Stap 1: Laad en verwijder vlag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Het bericht wordt opgeslagen zonder enige follow‑up‑vlag.*

### Follow‑up‑vlagopties lezen (Feature 5)
#### Overzicht
Voor audit of rapportage moet je mogelijk de bestaande vlaginstellingen lezen.

#### Stap 1: Haal opties op
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Het `options`‑object bevat nu start‑, verval‑ en herinneringsdatums, plus het vlagonderwerp.*

## Praktische toepassingen
- **Task‑Managementintegratie:** Gesynchroniseerde gemarkeerde e‑mails met Jira, Trello of Azure Boards.  
- **Geautomatiseerde herinneringen:** Genereer dagelijkse herinnerings‑e‑mails voor openstaande follow‑ups.  
- **Compliance‑audits:** Exporteer vlaggegevens voor regelgeving‑rapportage.

## Prestatie‑overwegingen
- **Datumcalculaties:** Bereken datums één keer per batch in plaats van binnen lussen.  
- **Resource‑beheer:** Sluit alle streams of bestands‑handles na het opslaan van berichten.  
- **Geheugengebruik:** Verwerk grote mailboxen in delen om heap‑druk te vermijden.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Vlag verschijnt niet in Outlook | Bericht opgeslagen zonder juiste `MessageFlags` | Zorg ervoor dat `setMessageFlags` is ingesteld op `MSGFLAG_UNSENT` voordat ontvanger‑vlaggen worden toegepast. |
| Opslaan geeft `AccessDeniedException` | Onjuist bestandspad of ontbrekende schrijfrechten | Controleer of de uitvoermap bestaat en dat de applicatie toestemming heeft om naar die locatie te schrijven. |
| Datums liggen één dag verschoven | Tijdzone‑mismatch | Gebruik consistent `TimeZone.getTimeZone("GMT")` of je lokale zone. |

## Veelgestelde vragen
**V: Wat is Aspose.Email voor Java?**  
A: Het is een pure‑Java‑API waarmee je e‑mailbestanden (MSG, EML, enz.) kunt maken, lezen en manipuleren zonder dat Outlook geïnstalleerd hoeft te zijn.

**V: Hoe krijg ik een gratis proeflicentie?**  
A: Bezoek de [Aspose‑website](https://releases.aspose.com/email/java/) om een 30‑daagse proefversie te downloaden.

**V: Kan ik meerdere follow‑up‑vlaggen op één bericht instellen?**  
A: Outlook ondersteunt slechts één vlag per bericht, maar je kunt extra taakgegevens opslaan in aangepaste MAPI‑eigenschappen.

**V: Mijn bericht wordt niet opgeslagen na het instellen van een vlag. Wat moet ik controleren?**  
A: Controleer of het `outputDir`‑pad geldig is en dat de applicatie toestemming heeft om naar die locatie te schrijven.

**V: Hoe kan ik vlaggen van veel berichten tegelijk verwijderen?**  
A: Loop door je berichtcollectie en roep `FollowUpManager.clearFlag` aan voor elke `MapiMessage`.

## Bronnen
- [Documentatie](https://reference.aspose.com/email/java/)
- [Download Aspose.Email voor Java](https://releases.aspose.com/email/java/)
- [Aspose.Email gratis proefversie](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Laatst bijgewerkt:** 2025-12-19  
**Getest met:** Aspose.Email for Java 25.4 (jdk16)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}