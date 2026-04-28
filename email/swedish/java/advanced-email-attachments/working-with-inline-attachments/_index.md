---
date: 2026-04-28
description: Lär dig hur du bäddar in en bild i ett HTML‑mail med Aspose.Email för
  Java och skickar e‑post med inbäddad bild via SMTP.
keywords:
- embed image in html email
- send email with embedded image
- how to embed image java
- create html email java
- send email via smtp java
linktitle: Arbeta med inbäddade bilagor i Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Hur man bäddar in en bild i HTML‑e‑post med Aspose.Email för Java
url: /sv/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hur man bäddar in bild i html-e-post med Aspose.Email för Java

Att bädda in en bild direkt i ett e‑postmeddelande får dina meddelanden att se professionella ut och garanterar att mottagaren ser grafiken utan att behöva ladda ner separata filer. I den här handledningen lär du dig **hur man bäddar in bild i html-e‑post** med Aspose.Email för Java, och täcker allt från bibliotekskonfiguration till att skapa ett HTML‑e‑postmeddelande, lägga till inline‑resurser och slutligen skicka meddelandet via SMTP.

## Snabba svar
- **Vilken är den primära klassen för inline‑bilder?** `LinkedResource`
- **Vilken metod refererar till bilden i HTML?** Använd `cid:yourContentId` i `<img>`‑taggen
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion
- **Kan jag skicka e‑posten via vilken SMTP‑server som helst?** Ja, konfigurera bara `SmtpClient` med dina serveruppgifter
- **Är detta tillvägagångssätt kompatibelt med alla större e‑postklienter?** De flesta moderna klienter (Outlook, Gmail, Thunderbird) stödjer CID‑inbäddade bilder

## Hur man bäddar in bild i html-e‑post med Aspose.Email för Java

När du **bäddar in bild i html-e‑post** blir bilden en del av MIME‑kroppen, så den visas omedelbart i mottagarens klient. Nedan går vi igenom hela processen, från ett enkelt HTML‑meddelande till ett fullt utrustat e‑postmeddelande med en inline‑bild.

### Vad är inline‑bilagor (inbäddade bilder)?

Inline‑bilagor—ibland kallade inbäddade eller CID‑bilder—är filer som lever inuti MIME‑kroppen i ett e‑postmeddelande. De refereras från HTML‑delen av meddelandet med ett **Content‑ID** (CID). Denna teknik låter dig **bädda in bilder i e‑post** så att de visas precis där du placerar `<img>`‑taggen, utan att dyka upp som separata nedladdningsbara bilagor.

### Varför använda inbäddade bilder i dina Java‑e‑postmeddelanden?

- **Professionellt utseende:** Logotyper, bannrar och produktbilder renderas omedelbart.
- **Bättre engagemang:** Mottagare är mer benägna att läsa ett e‑post som ser komplett ut.
- **Inga extra klick:** Användare behöver inte ladda ner en bilaga för att se bilden.
- **Enhetlig varumärkesprofil:** Dina varumärkesresurser förblir i linje med meddelandets innehåll.

### Förutsättningar

- Aspose.Email för Java‑biblioteket (ladda ner från den officiella [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/))
- Java 8+ utvecklingsmiljö
- Tillgång till en SMTP‑server för att skicka e‑post
- Bildfil som du vill bädda in (t.ex. `logo.png`)

## Steg‑för‑steg‑guide

### Steg 1: Skapa ett grundläggande HTML‑e‑postmeddelande

Först skapar du ett enkelt `MailMessage` med en HTML‑kropp. Detta blir duken där vi senare bäddar in bilden.

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

Nu bäddar vi in en bild. Klassen `LinkedResource` representerar den inline‑bilaga som ska bifogas. Tilldela ett unikt **Content‑ID** och referera det i HTML‑kroppen med `cid:`.

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

Om du behöver bearbeta inkommande meddelanden som innehåller inbäddade bilder kan du läsa in `.eml`‑filen och komma åt dess `LinkedResources`.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Vanliga problem & hur man åtgärdar dem

| Problem | Varför det händer | Åtgärd |
|-------|----------------|-----|
| **Content‑ID‑mismatch** | `cid:`‑referensen i HTML matchar inte `ContentId` som satts på `LinkedResource`. | Se till att strängarna är identiska (`image001` vs `cid:image001`). |
| **Filen hittades inte** | Sökvägen till bilden är felaktig eller filen saknas. | Verifiera den absoluta/relativa sökvägen och att filen finns på servern. |
| **SMTP‑autentiseringsfel** | Felaktiga inloggningsuppgifter eller serverinställningar. | Dubbelkolla värd, port, användarnamn och lösenord. Aktivera TLS/SSL om det krävs. |
| **Bild visas inte i vissa klienter** | Vissa klienter blockerar externa resurser. | Använd CID‑inbäddade bilder (som visas här) istället för externa URL:er. |

## Vanliga frågor

**Q: Hur laddar jag ner Aspose.Email för Java?**  
A: Du kan ladda ner Aspose.Email för Java från [documentation](https://reference.aspose.com/email/java/). Följ installationsinstruktionerna för att lägga till det i ditt projekt.

**Q: Kan jag använda Aspose.Email för Java tillsammans med andra Java‑bibliotek?**  
A: Ja, Aspose.Email integreras smidigt med andra Java‑bibliotek, så att du kan kombinera e‑posthantering med PDF‑generering, OCR eller databasåtkomst.

**Q: Vilka filformat stöds för inline‑bilagor?**  
A: Vanliga bildformat som PNG, JPEG, GIF samt andra dokumenttyper (t.ex. SVG) stöds som inline‑resurser.

**Q: Hur hanterar jag inline‑bilagor i HTML‑e‑post?**  
A: Använd `LinkedResource`‑klassen för att tilldela ett `ContentId`, lägg till den i `message.getLinkedResources()`, och referera den i HTML‑kroppen med `<img src='cid:yourContentId'>`.

**Q: Är Aspose.Email för Java kompatibelt med olika e‑postservrar?**  
A: Ja, det fungerar med vilken SMTP/IMAP/POP3‑server som helst. Ange bara rätt serveradress, port och autentiseringsuppgifter.

## Slutsats

Du har nu ett komplett, produktionsklart recept för **att bädda in bild i html-e‑post** med Aspose.Email för Java. Genom att skapa en `LinkedResource`, tilldela ett unikt Content‑ID och referera det med `cid:` i din HTML‑kropp säkerställer du att logotyper, bannrar eller produktfoton visas exakt där du vill—utan extra nedladdningar eller brutna länkar. Kombinera detta med den robusta `SmtpClient`‑klassen för att skicka meddelandet via vilken SMTP‑server som helst, så är du redo att leverera polerade, varumärkeskonsekventa e‑postmeddelanden från dina Java‑applikationer.

---

**Last Updated:** 2026-04-28  
**Tested With:** Aspose.Email for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}