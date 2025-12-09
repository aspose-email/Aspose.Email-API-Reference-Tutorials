---
date: 2025-12-01
description: Leer hoe u e‑mail met een ingesloten afbeelding kunt verzenden met Aspose.Email
  voor Java. Deze gids laat zien hoe u afbeeldingen in e‑mail kunt insluiten en een
  HTML‑e‑mail in Java kunt maken met inline‑bijlagen.
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Hoe e-mail met ingesloten afbeelding te verzenden met Aspose.Email voor Java
url: /nl/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hoe e‑mail met ingesloten afbeelding te verzenden met Aspose.Email voor Java

Afbeeldingen direct in een e‑mail insluiten geeft uw berichten een professionele uitstraling en zorgt ervoor dat de ontvanger de afbeeldingen ziet zonder aparte bestanden te hoeven downloaden. In deze tutorial leert u **hoe u een e‑mail met ingesloten afbeelding** verzendt met Aspose.Email voor Java, waarbij alles wordt behandeld van het instellen van de bibliotheek tot het maken van een HTML‑e‑mail, het toevoegen van inline‑bronnen en uiteindelijk het verzenden van het bericht.

## Snelle antwoorden
- **Wat is de primaire klasse voor inline‑afbeeldingen?** `LinkedResource`
- **Welke methode verwijst naar de afbeelding in HTML?** Gebruik `cid:yourContentId` in de `<img>`‑tag
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie
- **Kan ik de e‑mail via elke SMTP‑server verzenden?** Ja, configureer gewoon `SmtpClient` met uw servergegevens
- **Is deze aanpak compatibel met alle grote e‑mailclients?** De meeste moderne clients (Outlook, Gmail, Thunderbird) ondersteunen CID‑ingesloten afbeeldingen

## Wat zijn inline‑bijlagen (ingesloten afbeeldingen)?

Inline‑bijlagen—soms embedded‑ of CID‑afbeeldingen genoemd—zijn bestanden die zich binnen het MIME‑lichaam van een e‑mail bevinden. Ze worden vanuit het HTML‑deel van het bericht gerefereerd met een **Content‑ID** (CID). Deze techniek stelt u in staat **afbeeldingen in e‑mail** in te sluiten zodat ze precies op de plek verschijnen waar u de `<img>`‑tag plaatst, zonder dat ze als afzonderlijke downloadbare bijlagen verschijnen.

## Waarom ingesloten afbeeldingen gebruiken in uw Java‑e‑mails?

- **Professionele uitstraling:** Logo’s, banners en productafbeeldingen worden direct weergegeven.
- **Betere betrokkenheid:** Ontvangers lezen eerder een e‑mail die er compleet uitziet.
- **Geen extra klikken:** Gebruikers hoeven geen bijlage te downloaden om de afbeelding te zien.
- **Consistente branding:** Uw merkmaterialen blijven inline met de berichtinhoud.

## Vereisten

- Aspose.Email for Java‑bibliotheek (download van de officiële [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Java 8+ ontwikkelomgeving
- Toegang tot een SMTP‑server voor het verzenden van e‑mail
- Afbeeldingsbestand dat u wilt insluiten (bijv. `logo.png`)

## Stapsgewijze handleiding

### Stap 1: Maak een basis‑HTML‑e‑mailbericht

Eerst maakt u een eenvoudige `MailMessage` met een HTML‑body. Dit wordt het canvas waarop we later de afbeelding insluiten.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Stap 2: Voeg een inline‑afbeelding toe met `LinkedResource`

Nu sluiten we een afbeelding in. De `LinkedResource`‑klasse vertegenwoordigt de inline‑bijlage. Ken een unieke **Content‑ID** toe en verwijs er in de HTML‑body naar met `cid:`.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Pro tip:** Houd de `ContentId` eenvoudig en uniek binnen het bericht om conflicten te voorkomen.

### Stap 3: Verstuur de e‑mail via `SmtpClient`

Configureer uw SMTP‑instellingen en verzend het bericht. De ingesloten afbeelding reist mee met de e‑mail, zodat de ontvanger deze direct ziet.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Stap 4: Ontvang en extraheer inline‑afbeeldingen (optioneel)

Als u binnenkomende berichten moet verwerken die ingesloten afbeeldingen bevatten, kunt u het `.eml`‑bestand laden en toegang krijgen tot de `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Veelvoorkomende problemen & hoe ze op te lossen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Content‑ID mismatch** | De `cid:`‑referentie in HTML komt niet overeen met de `ContentId` die op `LinkedResource` is ingesteld. | Zorg dat de tekenreeksen identiek zijn (`image001` vs `cid:image001`). |
| **File not found** | Het pad naar de afbeelding is onjuist of het bestand ontbreekt. | Controleer het absolute/relatieve pad en of het bestand bestaat op de server. |
| **SMTP authentication failure** | Verkeerde inloggegevens of serverinstellingen. | Controleer host, poort, gebruikersnaam en wachtwoord. Schakel TLS/SSL in indien vereist. |
| **Image not displayed in some clients** | Bepaalde clients blokkeren externe bronnen. | Gebruik CID‑ingesloten afbeeldingen (zoals getoond) in plaats van externe URL’s. |

## Veelgestelde vragen

**Q: Hoe download ik Aspose.Email voor Java?**  
A: U kunt Aspose.Email voor Java downloaden van de [documentation](https://reference.aspose.com/email/java/). Volg de installatie‑instructies om het in uw project op te nemen.

**Q: Kan ik Aspose.Email voor Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Email integreert soepel met andere Java‑bibliotheken, zodat u e‑mailverwerking kunt combineren met PDF‑generatie, OCR of database‑toegang.

**Q: Welke bestandsformaten worden ondersteund voor inline‑bijlagen?**  
A: Veelvoorkomende afbeeldingsformaten zoals PNG, JPEG, GIF, evenals andere documenttypen (bijv. SVG) worden ondersteund als inline‑bronnen.

**Q: Hoe ga ik om met inline‑bijlagen in HTML‑e‑mails?**  
A: Gebruik de `LinkedResource`‑klasse om een `ContentId` toe te wijzen, voeg deze toe aan `message.getLinkedResources()`, en verwijs er in de HTML‑body naar met `<img src='cid:yourContentId'>`.

**Q: Is Aspose.Email voor Java compatibel met verschillende e‑mailservers?**  
A: Ja, het werkt met elke SMTP/IMAP/POP3‑server. Geef gewoon het juiste serveradres, poort en authenticatie‑details op.

---

**Last Updated:** 2025-12-01  
**Tested With:** Aspose.Email for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}