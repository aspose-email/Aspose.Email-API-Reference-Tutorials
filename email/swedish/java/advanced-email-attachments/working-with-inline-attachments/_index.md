---
date: 2025-12-01
description: Lär dig hur du skickar e‑post med inbäddad bild med Aspose.Email för
  Java. Den här guiden visar hur du bäddar in bilder i e‑post och skapar HTML‑e‑post
  i Java med inline‑bilagor.
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Hur man skickar e‑post med inbäddad bild med Aspose.Email för Java
url: /sv/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skickar e‑post med inbäddad bild med Aspose.Email för Java

Att bädda in bilder direkt i ett e‑postmeddelande får dina meddelanden att se professionella ut och säkerställer att mottagaren ser grafiken utan att behöva ladda ner separata filer. I den här handledningen lär du dig **hur man skickar e‑post med inbäddad bild** med Aspose.Email för Java, och täcker allt från att konfigurera biblioteket till att skapa ett HTML‑mail, lägga till inline‑resurser och slutligen skicka meddelandet.

## Snabba svar
- **Vilken är den primära klassen för inline‑bilder?** `LinkedResource`
- **Vilken metod refererar bilden i HTML?** Använd `cid:yourContentId` i `<img>`‑taggen
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion
- **Kan jag skicka e‑posten via vilken SMTP‑server som helst?** Ja, konfigurera bara `SmtpClient` med dina serveruppgifter
- **Är detta tillvägagångssätt kompatibelt med alla större e‑postklienter?** De flesta moderna klienter (Outlook, Gmail, Thunderbird) stödjer CID‑inbäddade bilder

## Vad är inline‑bilagor (inbäddade bilder)?

Inline‑bilagor – ibland kallade inbäddade eller CID‑bilder – är filer som finns i MIME‑kroppen av ett e‑postmeddelande. De refereras från HTML‑delen av meddelandet med ett **Content‑ID** (CID). Denna teknik låter dig **bädda in bilder i e‑post** så att de visas precis där du placerar `<img>`‑taggen, utan att visas som separata nedladdningsbara bilagor.

## Varför använda inbäddade bilder i dina Java‑e‑postmeddelanden?

- **Professionellt utseende:** Logotyper, bannrar och produktbilder renderas omedelbart.
- **Bättre engagemang:** Mottagare är mer benägna att läsa ett e‑postmeddelande som ser komplett ut.
- **Inga extra klick:** Användare behöver inte ladda ner en bilaga för att se bilden.
- **Konsistent varumärkesprofil:** Dina varumärkesresurser förblir i linje med meddelandets innehåll.

## Förutsättningar

- Aspose.Email for Java‑biblioteket (ladda ner från den officiella [Aspose.Email for Java-dokumentationen](https://reference.aspose.com/email/java/))
- Java 8+ utvecklingsmiljö
- Tillgång till en SMTP‑server för att skicka e‑post
- Bildfil som du vill bädda in (t.ex. `logo.png`)

## Steg‑för‑steg‑guide

### Steg 1: Skapa ett grundläggande HTML‑e‑postmeddelande

Först, skapa ett enkelt `MailMessage` med en HTML‑kropp. Detta blir duken där vi senare bäddar in bilden.

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

### Steg 2: Lägg till en inline‑bild med `LinkedResource`

Nu bäddar vi in en bild. Klassen `LinkedResource` representerar inline‑bilagan. Tilldela ett unikt **Content‑ID** och referera till det i HTML‑kroppen med `cid:`.

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

> **Proffstips:** Håll `ContentId` enkel och unik inom meddelandet för att undvika konflikter.

### Steg 3: Skicka e‑posten via `SmtpClient`

Konfigurera dina SMTP‑inställningar och skicka meddelandet. Den inbäddade bilden följer med e‑posten, så mottagaren ser den omedelbart.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Steg 4: Ta emot och extrahera inline‑bilder (valfritt)

Om du behöver bearbeta inkommande meddelanden som innehåller inbäddade bilder kan du ladda `.eml`‑filen och komma åt dess `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Vanliga problem & hur man åtgärdar dem

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Content‑ID‑mismatch** | Referensen `cid:` i HTML matchar inte `ContentId` som satts på `LinkedResource`. | Se till att strängarna är identiska (`image001` vs `cid:image001`). |
| **Fil ej hittad** | Sökvägen till bilden är felaktig eller filen saknas. | Verifiera den absoluta/relativa sökvägen och att filen finns på servern. |
| **SMTP‑autentiseringsfel** | Fel användaruppgifter eller serverinställningar. | Dubbelkolla värd, port, användarnamn och lösenord. Aktivera TLS/SSL om det krävs. |
| **Bild visas inte i vissa klienter** | Vissa klienter blockerar externa resurser. | Använd CID‑inbäddade bilder (som visat) istället för externa URL:er. |

## Vanliga frågor

**Q: Hur laddar jag ner Aspose.Email för Java?**  
A: Du kan ladda ner Aspose.Email för Java från [dokumentationen](https://reference.aspose.com/email/java/). Följ installationsinstruktionerna för att konfigurera det i ditt projekt.

**Q: Kan jag använda Aspose.Email för Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Email integreras smidigt med andra Java‑bibliotek, vilket låter dig kombinera e‑postbehandling med PDF‑generering, OCR eller databasåtkomst.

**Q: Vilka filformat stöds för inline‑bilagor?**  
A: Vanliga bildformat som PNG, JPEG, GIF, samt andra dokumenttyper (t.ex. SVG) stöds som inline‑resurser.

**Q: Hur hanterar jag inline‑bilagor i HTML‑e‑post?**  
A: Använd `LinkedResource`‑klassen för att tilldela ett `ContentId`, lägg till det i `message.getLinkedResources()`, och referera till det i HTML‑kroppen med `<img src='cid:yourContentId'>`.

**Q: Är Aspose.Email för Java kompatibelt med olika e‑postservrar?**  
A: Ja, det fungerar med vilken SMTP/IMAP/POP3‑server som helst. Ange bara rätt serveradress, port och autentiseringsuppgifter.

---

**Senast uppdaterad:** 2025-12-01  
**Testat med:** Aspose.Email for Java 24.12 (senaste vid skrivande)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}