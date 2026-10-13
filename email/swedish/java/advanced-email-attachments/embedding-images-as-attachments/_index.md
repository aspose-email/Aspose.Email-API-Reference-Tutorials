---
date: 2026-10-12
description: Lär dig hur du bäddar in bilder i HTML‑e‑post med Aspose.Email för Java,
  skickar HTML‑e‑post med inbäddade bilder och minskar storleken på e‑postbilagor.
keywords:
- reduce email attachment size
- create email with image
- optimize image for email
- send html email java
- embed cid image email
lastmod: 2026-10-12
linktitle: Hur man bifogar bild till e‑post med Aspsoe.Email
og_description: Minska storleken på e‑postbilagor och bädda in bilder i HTML‑e‑post
  med Aspose.Email för Java. Följ denna steg‑för‑steg‑guide för att skicka rik HTML‑e‑post
  effektivt.
og_image_alt: 'Developer guide: embed images in HTML email while reducing attachment
  size with Aspose.Email for Java'
og_title: Minska storleken på e‑postbilagor med Aspose.Email för Java
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to embed images in HTML email using Aspose.Email for Java,
    send HTML email with embedded images, and reduce email attachment size.
  headline: Reduce email attachment size with Aspose.Email for Java
  type: TechArticle
- questions:
  - answer: Repeat the attachment and `LinkedResource` steps for each image, assigning
      a unique Content‑ID (e.g., `image2`, `image3`) and referencing them in the HTML.
    question: How can I embed multiple images in a single email?
  - answer: Plain‑text format does not support embedded images. You can only include
      URLs that recipients can click to view the image online.
    question: Can I embed images in plain‑text emails?
  - answer: JPEG, PNG, and GIF are widely supported. Use JPEG for photographs and
      PNG for graphics with transparency.
    question: What image formats are safe for email embedding?
  - answer: Yes—add `width`/`height` attributes to the `<img>` tag, e.g., `<img src='cid:image1'
      width='400' height='300'>`.
    question: Is there a way to control image dimensions in the email?
  - answer: While there’s no strict SMTP limit, most mail providers recommend keeping
      total email size under 5 MB. Optimizing image size helps stay well within this
      limit.
    question: Are there size limits for embedded images?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
tags:
- email attachment size
- Aspose.Email
- Java email API
- embed images email
- HTML email
title: Minska storleken på e‑postbilagor med Aspose.Email för Java
url: /sv/java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Minska e‑postbilagans storlek med Aspose.Email för Java

Att bädda in bilder direkt i ett HTML‑e‑postmeddelande gör inte bara att meddelandet ser polerat ut, det **minskar också e‑postbilagans storlek** eftersom bilden är en del av MIME‑kroppen snarare än en separat fil. I den här handledningen kommer du att lära dig hur du skapar e‑post med bild, bäddar in bilden med en CID‑referens och tillämpar bästa praxis‑tips för att **optimera bilden för e‑post** så att det slutliga meddelandet förblir lättviktigt. Du kommer också att se hur du skickar HTML‑e‑post i Java‑stil med Aspose.Email och håller den totala belastningen väl under vanliga brevlådestak.

## Snabba svar
- **Vilken klass skapar e‑postmeddelandet?** `MailMessage` – den centrala behållaren för ämne, mottagare och innehåll.  
- **Vilket objekt låter dig bädda in en bild i HTML‑kroppen?** `LinkedResource` – det omsluter bildströmmen och tilldelar ett Content‑ID.  
- **Behöver jag en licens för produktionsanvändning?** Ja – en kommersiell Aspose.Email‑licens krävs för att ta bort evalueringsbegränsningar.  
- **Hur kan jag minska bilagans storlek?** Optimera bilden (ändra storlek till ≤600 px, komprimera under 100 KB) innan du lägger till den.  
- **Kan jag bädda in flera bilder?** Absolut – lägg till ett unikt Content‑ID för varje bild och referera dem med `cid:`‑URI:er.

## Vad är inbäddad bild i HTML‑e‑post?
Att bädda in en bild innebär att infoga bilden i e‑postens MIME‑struktur så att mottagaren ser den inline. Bilden refereras med ett **Content‑ID (CID)**, som HTML‑taggen `<img>` laddar direkt från meddelandekroppen, vilket eliminerar separata bilagor och håller den totala storleken mindre.

## Varför skicka HTML‑e‑post med inbäddad bild?
Att bädda in bilder i HTML låter dig skapa rikare nyhetsbrev, produktmeddelanden eller supportärenden. Mottagarna ser den visuella delen omedelbart, utan att behöva ladda ner en bilaga, vilket förbättrar öppningsfrekvensen och engagemanget. De flesta e‑postklienter stödjer CID‑bilder, och inbäddning undviker extra nedladdningssteg, vilket leder till snabbare rendering och lägre bandbreddsanvändning.

## Förutsättningar
- **Aspose.Email för Java** – ladda ner från den officiella webbplatsen: [Aspose.Email Java download](https://releases.aspose.com/email/java/).  
- Tillgång till en SMTP‑server (Gmail, Outlook eller din egen relay).  
- En bildfil (JPEG, PNG eller GIF) som du vill bädda in.

> **Pro tip:** *Optimera bildstorleken för e‑post* genom att ändra bredden till ≤600 px och komprimera till ≤100 KB. Detta minskar laddningstiden och undviker att nå brevlådestak.

## Skapa ett e‑postmeddelande
`MailMessage` är Aspose.Email:s objekt på högsta nivå som representerar ett enskilt e‑postmeddelande. Det innehåller ämnet, avsändaren, mottagarna och kroppen (vanlig text eller HTML).  

`MailMessage`‑klassen är den centrala modellen för att bygga och skicka e‑postmeddelanden i Aspose.Email för Java.

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## Lägga till bild som bilaga
`LinkedResource` representerar en MIME‑del som kan bäddas in inline i ett e‑postmeddelande.  
Innan inbäddning lägger du till bildfilen i meddelandets bilagakollektion. Bilagan blir en ström som `LinkedResource` senare kan referera till.

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## Bädda in den bifogade bilden i HTML
`LinkedResource` används för att binda en bildström till ett Content‑ID för inline‑visning.  
För att visa bilden i HTML‑kroppen, skapa ett `LinkedResource` som pekar på den bifogade bilden och sätt dess Content‑ID (t.ex. `image1`). Referera sedan till det ID:t i HTML med `cid:`‑URI‑schemat.

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **Varför använda `LinkedResource`?** Det signalerar till klienten att bilden är en del av meddelandekroppen, vilket är avgörande för scenarier med **send html email java** som kräver inline‑grafik.

## Skicka e‑posten
`SmtpClient` är klassen som hanterar SMTP‑kommunikation för att skicka meddelanden.  
`SmtpClient` hanterar den faktiska överföringen. Konfigurera den med din servervärd, port och autentiseringsuppgifter, och anropa sedan `send` för att skicka `MailMessage`.  

`SmtpClient` är Aspose.Email:s SMTP‑transportklass som säkert skickar det sammansatta `MailMessage` till målmailservern.

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

När mottagaren öppnar e‑posten renderar HTML‑kroppen bilden inline, vilket ger en sömlös visuell upplevelse samtidigt som den totala belastningen hålls liten.

## Hur man bäddar in flera bilder i e‑post
`LinkedResource` representerar en MIME‑del som kan bäddas in inline i ett e‑postmeddelande.  
Lägg till varje bild som en separat bilaga, skapa ett eget `LinkedResource` för varje och tilldela ett unikt Content‑ID såsom `image2`, `image3` osv. Referera dem i HTML med `src='cid:image2'`. Detta mönster skalar till nyhetsbrev med dussintals grafik utan att öka meddelandets storlek.

## Tips för att minska e‑postbilagans storlek
- **Ändra storlek** på bilden till de exakta dimensionerna som behövs (vanligtvis ≤600 px i bredd).  
- **Komprimera** med verktyg som ImageMagick eller online‑komprimerare för att hålla filen under 100 KB.  
- **Välj rätt format**: JPEG för foton, PNG för grafik med transparens.  
- **Ta bort EXIF‑metadata** om den inte behövs.  
- **Använd progressiv JPEG** för snabbare progressiv rendering i klienter som stödjer det.

## Vanliga problem & felsökning
| Problem | Orsak | Lösning |
|-------|-------|----------|
| Bild visas inte | Fel Content‑ID eller saknad `LinkedResource` | Verifiera att `linkedImage.setContentId("image1")` matchar `src='cid:image1'` i HTML. |
| Stor e‑poststorlek | Ooptimerad bild (hög upplösning) | Ändra storlek/komprimera bilden innan du bifogar; sikta på ≤100 KB. |
| E‑post markerad som skräppost | Saknar korrekta MIME‑rubriker | Se till att `SmtpClient` använder TLS/STARTTLS och ange en tydlig `From`‑adress. |
| Inline‑bild visas som bilaga | Klienten stödjer inte CID | Tillhandahåll en reserv‑URL i `<img>`‑taggen (`src='cid:image1' alt='Image'`). |

## Vanliga frågor

**Q: Hur kan jag bädda in flera bilder i ett enda e‑postmeddelande?**  
A: Upprepa bilage‑ och `LinkedResource`‑stegen för varje bild, tilldela ett unikt Content‑ID (t.ex. `image2`, `image3`) och referera dem i HTML.

**Q: Kan jag bädda in bilder i vanliga text‑e‑postmeddelanden?**  
A: Vanligt text‑format stödjer inte inbäddade bilder. Du kan bara inkludera URL:er som mottagarna kan klicka på för att se bilden online.

**Q: Vilka bildformat är säkra för e‑postinbäddning?**  
A: JPEG, PNG och GIF stöds brett. Använd JPEG för fotografier och PNG för grafik med transparens.

**Q: Finns det ett sätt att kontrollera bilddimensioner i e‑posten?**  
A: Ja—lägg till `width`/`height`‑attribut i `<img>`‑taggen, t.ex. `<img src='cid:image1' width='400' height='300'>`.

**Q: Finns det storleksgränser för inbäddade bilder?**  
A: Även om det inte finns någon strikt SMTP‑gräns, rekommenderar de flesta e‑postleverantörer att hålla total e‑poststorlek under 5 MB. Att optimera bildstorleken hjälper dig att hålla dig väl inom denna gräns.

**Last Updated:** 2026-10-12  
**Tested with:** Aspose.Email för Java 24.11 (senaste vid skrivande stund)  
**Author:** Aspose

## Relaterade handledningar

- [Hantera e‑postbilagans storleksgräns med Aspose.Email](/email/java/advanced-email-attachments/managing-large-attachments/)
- [Bygg och skicka e‑postbilagor med Aspose Email Java](/email/java/attachments-handling/build-send-emails-attachments-aspose-email-java/)
- [Hur man extraherar bilagor från msg‑filer med Aspose.Email för Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}