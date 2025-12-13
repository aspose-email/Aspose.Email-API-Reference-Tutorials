---
date: '2025-12-13'
description: Leer hoe je msg en eml kunt converteren met Aspose.Email voor Java, een
  nieuwe bijlage kunt toevoegen, e-mailbijlage kunt opslaan en TNEF-gegevens kunt
  verwerken.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: msg en eml converteren met Aspose.Email Java – TNEF‑bijlagen gids
url: /nl/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Beheersen van Aspose.Email Java: TNEF en e‑mailbijlagen  

In moderne e‑mail‑gerichte toepassingen moet je vaak **convert msg eml** bestanden converteren, een nieuwe bijlage toevoegen aan een bestaand bericht, en speciale formaten zoals TNEF behouden. Of je nu een archiveringsservice, een migratietool of een client‑side mailviewer bouwt, Aspose.Email for Java biedt een schone, programmeerbare manier om dit te doen. In deze tutorial zie je precies hoe je **convert msg to eml**, een nieuwe bijlage toevoegt, een e‑mailbijlage opslaat, en werkt met TNEF‑gegevens met behulp van de Aspose.Email Java‑bibliotheek.

## Quick Answers
- **Hoe converteer ik MSG naar EML?** Gebruik `MapiMessage` met `MailConversionOptions` en stel `convertAsTnef` in op `true`.  
- **Kan ik een bijlage toevoegen aan een TNEF‑ingeschakelde EML?** Ja – laad de EML, roep `getAttachments().addItem(...)` aan, en sla vervolgens op.  
- **Welke versie van Aspose.Email is vereist?** Het voorbeeld gebruikt versie 25.4 (JDK 16).  
- **Heb ik een licentie nodig voor productie?** Ja – een proefversie werkt voor evaluatie, maar een volledige licentie verwijdert beperkingen.  
- **Is er een manier om TNEF in een bestaand bericht te detecteren?** Roep `mail.getOriginalIsTnef()` aan na het laden van de EML.

## What is “convert msg eml”?
Wat is “convert msg eml”?

Het converteren van een Microsoft Outlook MSG‑bestand naar het standaard EML‑formaat maakt het mogelijk het bericht te lezen met elke RFC‑822‑compatibele e‑mailclient. De conversie biedt bovendien de mogelijkheid om TNEF‑gecodeerde gegevens te behouden of te manipuleren tijdens het proces.

## Why use Aspose.Email Java for this task?
- **Volledige formaatondersteuning** – MSG, EML, MHTML en meer.  
- **Ingebouwde TNEF‑verwerking** – geen behoefte aan parsers van derden.  
- **Eenvoudige API** – één‑regelige aanroepen voor laden, converteren en opslaan.  
- **Robuuste licentiëring** – proefversie voor testen, volledige licentie voor productie.

## Prerequisites
- **Aspose.Email for Java** (v25.4, JDK 16) – zie Maven‑dependency hieronder.  
- **Maven** of een ander build‑tool dat het Aspose‑pakket kan resolven.  
- Basiskennis van Java I/O en exception‑handling.  

## Setting Up Aspose.Email for Java
Instellen van Aspose.Email voor Java

Add the library to your Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Licentie‑acquisitie
Aspose.Email biedt een gratis proefversie, maar een gelicentieerde versie is vereist voor onbeperkt gebruik.

- **Gratis proefversie:** Download een tijdelijke licentie [hier](https://releases.aspose.com/email/java/).  
- **Aankoop:** Om een licentie te kopen, bezoek de [aankooppagina](https://purchase.aspose.com/buy).

Initialize the license in your Java code:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide
Implementatie‑gids

### Adding New Attachment to a Main Message Containing TNEF
Nieuwe bijlage toevoegen aan een hoofdbericht dat TNEF bevat
**Hoe een bijlage toe te voegen:** Laad de EML, voeg het bestand toe, en sla vervolgens op.

#### Step 1: Load the Existing Email Message
Stap 1: Laad het bestaande e‑mailbericht
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### Step 2: Add the New Attachment
Stap 2: Voeg de nieuwe bijlage toe
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### Step 3: Save the Modified Email Message
Stap 3: Sla het gewijzigde e‑mailbericht op
```java
eml.save(dataDir + "test_out.eml");
```
*Pro tip:* Gebruik try‑with‑resources om ervoor te zorgen dat streams worden gesloten en `FileNotFoundException` te vermijden.

### Creating TNEF‑Enabled EML from MSG
TNEF‑ingeschakelde EML maken vanuit MSG
**Hoe msg naar eml te converteren:** Stel `convertAsTnef` in op `true`.

#### Step 1: Load the MSG File
Stap 1: Laad het MSG‑bestand
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### Step 2: Set Conversion Options
Stap 2: Stel conversie‑opties in
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### Step 3: Convert and Save
Stap 3: Converteer en sla op
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### Preserve TNEF Attachments When Loading EML Files
TNEF‑bijlagen behouden bij het laden van EML‑bestanden
**Hoe e‑mailbijlage op te slaan terwijl TNEF behouden blijft:** Gebruik `MsgLoadOptions`.

#### Step 1: Set Load Options
Stap 1: Stel laadopties in
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### Step 2: Load EML File with Options
Stap 2: Laad EML‑bestand met opties
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### Detecting if a Message Is TNEF
Detecteren of een bericht TNEF is
**Hoe TNEF‑aanwezigheid te controleren:** Roep `getOriginalIsTnef()` aan.

#### Step 1: Load the EML File
Stap 1: Laad het EML‑bestand
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### Step 2: Detect TNEF Presence
Stap 2: Detecteer TNEF‑aanwezigheid
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## Practical Applications
Praktische toepassingen
1. **E‑mailarchivering:** Bewaar elke bijlage — inclusief TNEF‑gecodeerde — voor compliance‑audits.  
2. **Bedrijfs‑migratie:** Converteer legacy MSG‑bestanden naar EML zodat ze geïmporteerd kunnen worden in moderne mailservers.  
3. **Klantenondersteuning:** Detecteer automatisch TNEF‑gegevens wanneer gebruikers berichten doorsturen tussen Outlook en web‑mailclients.

## Performance Considerations
Prestatie‑overwegingen
- **Resource‑beheer:** Plaats bestands‑streams in try‑with‑resources om handles snel vrij te geven.  
- **Grote bijlagen:** Verwerk grote bestanden in delen of stream ze direct om hoog geheugenverbruik te vermijden.  
- **Monitoring:** Gebruik Java‑profileringstools om het heap‑verbruik te bekijken bij het verwerken van veel bijlagen.

## Conclusion
Conclusie
Door de bovenstaande stappen te volgen kun je **convert msg eml**, een nieuwe bijlage toevoegen, een e‑mailbijlage opslaan, en betrouwbaar werken met TNEF‑gegevens met Aspose.Email voor Java. De bibliotheek abstraheert de low‑level MIME‑verwerking, zodat je je kunt concentreren op de bedrijfslogica. Voor een diepere verkenning, bekijk de officiële [Aspose‑documentatie](https://reference.aspose.com/email/java/) of experimenteer met andere conversie‑opties.

## FAQ Section
FAQ‑sectie
**Q1: Wat is een TNEF‑bestand?**  
A1: TNEF staat voor Transport Neutral Encapsulation Format en wordt gebruikt door Microsoft Outlook om rich‑text‑opmaak te behouden bij het verzenden van e‑mails als bijlagen.

**Q2: Kan ik Aspose.Email gebruiken zonder een licentie aan te schaffen?**  
A2: Ja, je kunt beginnen met een gratis proefversie. De proefversie legt echter bepaalde beperkingen op die volledige schaalgebruik kunnen beïnvloeden.

**Q3: Is het mogelijk om tussen alle e‑mailformaten te converteren met Aspose.Email?**  
A3: Aspose.Email ondersteunt conversie tussen de meeste populaire formaten — inclusief EML, MSG en MHTML — maar controleer de specifieke formatondersteuning in de [documentatie](https://reference.aspose.com/email/java/).

**Q4: Hoe los ik file‑not‑found‑fouten op met Aspose.Email?**  
A4: Controleer dubbel of de bestands‑paden die je aan de API doorgeeft correct zijn, of de bestanden bestaan, en of het uitvoerende proces lees‑/schrijfrechten heeft voor die mappen.

**Q5: Wat is de beste manier om grote bijlagen te verwerken met Aspose.Email?**  
A5: Verwerk bijlagen in kleinere streams of delen, en sluit streams altijd direct. Dit vermindert geheugenbelasting en voorkomt `OutOfMemoryError`.

## Frequently Asked Questions (Additional)
Veelgestelde vragen (extra)

**Q: Verwijdert Aspose.Email automatisch TNEF bij het converteren naar EML?**  
A: Nee. Standaard worden TNEF‑gegevens behouden. Je kunt dit gedrag regelen met `MailConversionOptions.setConvertAsTnef`.

**Q: Kan ik programmatically alle bijlagen in een geladen bericht opsommen?**  
A: Ja — gebruik `mail.getAttachments()` dat een collectie retourneert die je kunt itereren.

**Q: Is er een manier om een batch MSG‑bestanden naar EML te converteren in één run?**  
A: Zeker. Loop door de bestanden, pas de conversiestappen toe zoals hierboven getoond, en sla elk resultaat op.

---

**Laatst bijgewerkt:** 2025-12-13  
**Getest met:** Aspose.Email for Java 25.4 (JDK 16)  
**Auteur:** Aspose  
**Gerelateerde bronnen:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Download een tijdelijke licentie [hier](https://releases.aspose.com/email/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}