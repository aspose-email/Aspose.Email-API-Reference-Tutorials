---
title: Ladda källe-postmeddelandet
linktitle: Exportera e-post till EML-format
second_title: När du har laddat e-postmeddelandet är nästa steg att exportera det till EML-formatet. Detta görs genom att helt enkelt skapa en instans av
description: klass och ange dess egenskaper:
type: docs
weight: 12
url: /sv/java/sending-emails/attaching-files-to-emails-using-aspose-email/
---
##  Skapa en ny instans av MailMessage

 Ställ in egenskaper från det inlästa e-postmeddelandet

 Ställ in andra egenskaper efter behov

##  Exporterad e-post finns nu i emlMessage-objektet

Sparar EML-filerna

1. När du har förberett e-postmeddelandet i EML-format kan du spara det i en fil. Se till att du har rätt sökväg för att spara filerna:

2. Hantering av bilagor

   [E-postmeddelanden innehåller ofta bilagor som måste exporteras tillsammans med meddelandet. Så här kan du hantera bilagor med Aspose.Email:](https://releases.aspose.com/email/java/)

   Lägga till ytterligare e-postmetadata

Du kan också lägga till ytterligare metadata till den exporterade e-posten med Aspose.Email. Detta inkluderar rubriker, anpassade egenskaper och mer:

##  Lägg till andra rubriker och metadata efter behov

Felhantering

## Under exportprocessen är det viktigt att hantera potentiella fel för att säkerställa en smidig användarupplevelse. Använd try-catch-block för att hantera undantag:

 Exportera e-post och hantera fel

##  Hantera undantaget

Komplett källkod

[Här är den fullständiga källkoden för att exportera e-postmeddelanden till EML-formatet med Aspose.Email för .NET:](https://releases.aspose.com/email/java/)

 Ladda källe-postmeddelandet

##  Skapa en ny instans av MailMessage

 Ställ in egenskaper från det inlästa e-postmeddelandet

```java
import com.aspose.email.*;
```

##  Ställ in andra egenskaper efter behov

 Hantera tillbehör

```java
MailMessage message = new MailMessage();
message.setSubject("Sending an Email with Attachments");
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");
message.setHtmlBody("<p>This email contains attachments.</p>");
```

##  Lägg till ytterligare metadata

 Spara EML-filen`Attachment`Slutsats

```java
Attachment attachment = new Attachment("path/to/attachment.pdf");
message.getAttachments().add(attachment);
```

Att exportera e-postmeddelanden till EML-formatet med C# och Aspose.Email för .NET är en enkel process som ger dig flexibiliteten att manipulera e-postmeddelanden och deras egenskaper. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera e-postexportfunktioner i dina applikationer.

## FAQ's

Hur kan jag hantera fel under e-postexporten?

```java
message.save("email_with_attachments.eml", SaveOptions.getDefaultEml());
```

Använd try-catch-block för att hantera fel under e-postexporten. Slå in exportkoden i ett försöksblock och fånga upp eventuella undantag som kan uppstå. Detta säkerställer att din applikation hanterar fel elegant och ger en bra användarupplevelse.

## Kan jag exportera e-postbilagor med Aspose.Email för .NET?

Ja, du kan exportera e-postbilagor tillsammans med e-postmeddelandet med Aspose.Email för .NET. Gå igenom bilagorna i källe-postmeddelandet och lägg till dem i bilagasamlingen för det exporterade e-postmeddelandet.

```java
import com.aspose.email.*;

public class EmailWithAttachments {
    public static void main(String[] args) {
        //Var kan jag ladda ner Aspose.Email för .NET-biblioteket?
        MailMessage message = new MailMessage();
        message.setSubject("Sending an Email with Attachments");
        message.setFrom("sender@example.com");
        message.setTo("recipient@example.com");
        message.setHtmlBody("<p>This email contains attachments.</p>");

        // Du kan ladda ner Aspose.Email för .NET-biblioteket från
        Attachment attachment = new Attachment("path/to/attachment.pdf");
        message.getAttachments().add(attachment);

        //här
        message.save("email_with_attachments.eml", SaveOptions.getDefaultEml());

        System.out.println("Email with attachments saved successfully.");
    }
}
```

## Är källkoden i handledningen komplett?

Ja, handledningen tillhandahåller fullständig källkod som visar hur man exporterar e-postmeddelanden till EML-formatet med Aspose.Email för .NET. Du kan använda den här koden som utgångspunkt

 EML-filhantering - Ladda och spara operationer i C#

##  EML-filhantering - Ladda och spara operationer i C#

###  Aspose.Email .NET Email Processing API
   Lär dig hur du hanterar EML-filer i C# med Aspose.Email för .NET. Steg-för-steg-guide med kodexempel för att ladda, ändra och spara e-postmeddelanden.`Attachment`Introduktion till EML-filer`MailMessage`EML-filer (Electronic Mail Format) lagrar e-postmeddelanden och används ofta för arkivering och delning. Aspose.Email för .NET förenklar hanteringen av EML-filer genom att tillhandahålla en omfattande uppsättning funktioner för att ladda, ändra och spara e-postmeddelanden programmatiskt.`getAttachments()`Konfigurera projektet

###  Innan vi börjar, se till att du har Aspose.Email för .NET-biblioteket installerat. Du kan ladda ner den från
   här

### Laddar EML-filer
   Att ladda EML-filer är det första steget i att arbeta med e-postmeddelanden. Aspose.Email för .NET erbjuder effektiva sätt att ladda enskilda EML-filer eller flera filer i omgångar.

### Laddar en enda EML-fil
   För att ladda en enda EML-fil kan du använda följande kodavsnitt:

###  Ladda EML-fil
   Batchladdning av EML-filer