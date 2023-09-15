---
title: Installera Aspose.Email för .NET
linktitle: För att komma igång måste du installera Aspose.Email for .NET-biblioteket. Du kan ladda ner den från
second_title: Aspose.Releases
description: eller använd NuGet Package Manager i Visual Studio.
type: docs
weight: 15
url: /sv/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## Skapa ett nytt .NET-projekt

Öppna Visual Studio och skapa ett nytt .NET-projekt.

## Installera Aspose.Email for .NET-biblioteket med NuGet Package Manager.

Du är nu redo att börja koda!

1. Laddar och analyserar ett e-postmeddelande[Laddar ett e-postmeddelande](https://releases.aspose.com/email/net)Innan vi kan ändra typsnitten i e-postmeddelandet måste vi ladda ett e-postmeddelande. Du kan ladda ett e-postmeddelande från olika källor, till exempel en fil, stream eller till och med en e-postserver.

2.  Ladda e-postmeddelandet

3. Parsar meddelandetexten

## När e-postmeddelandet har laddats kan du komma åt dess olika delar, inklusive HTML-kroppen. Genom att analysera HTML-kroppen kan vi göra teckensnittsändringar.

 Analysera HTML-kroppen

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//Ändra teckensnitt i e-postmeddelandet
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Förstå teckensnittsstilar

Teckensnitt i HTML-e-postmeddelanden definieras med CSS-stilar. För att ändra teckensnitt måste du ändra CSS-stilarna som är kopplade till e-postmeddelandets HTML-innehåll.

```csharp
//Ändra teckensnitt programmerat
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Låt oss säga att du vill ändra teckensnittet för ett stycke i e-postmeddelandets HTML-text. Så här kan du göra det:
        var tnefAttachment = attachment;

        // Ändra teckensnitt för ett stycke
        //Konvertera till MHT-format
    }
}
```

## Skapar MHT-meddelande

För att konvertera e-postmeddelandet till MHT-format måste du skapa ett MHT-formaterat e-postmeddelande med Aspose.Email.

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

##  Skapa MHT-formaterat e-postmeddelande

Spara meddelandet i MHT-format

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //Slutligen, spara det MHT-formaterade meddelandet till en fil.
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // Spara meddelandet i MHT-format
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//Komplett källkod
					var tnefAttachment = attachment;

					//Här är den kompletta källkoden som sätter ihop allt:
					//Slutsats
				}
			}
			//den här guiden utforskade vi hur man ändrar teckensnitt under MHT-konvertering med Aspose.Email för .NET. Genom att följa dessa steg kan du sömlöst konvertera e-postmeddelanden till MHT-format samtidigt som du behåller önskade teckensnittsstilar.
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## Vanliga frågor

- Kan jag konvertera flera e-postmeddelanden till MHT-format på en gång?
- Ja, du kan gå igenom en samling e-postmeddelanden och tillämpa samma teckensnittsändringar på varje meddelande innan du konverterar dem till MHT-format.
- Stöder Aspose.Email även andra e-postformat?

## Ja, Aspose.Email stöder olika e-postformat, inklusive EML, MSG, PST och mer.

Är det möjligt att anpassa teckensnittsändringarna ytterligare?

## Absolut! Du kan utforska fler CSS-stilar för att anpassa teckensnitt, som teckenstorlek, färg och justering.

### Kan jag använda Aspose.Email för kommersiella projekt?

Ja, Aspose.Email kan användas för både personliga och kommersiella projekt, enligt licensvillkoren.[ Kom ihåg att den här guiden ger en allmän översikt och att du kan utforska vidare genom att hänvisa till](https://releases.aspose.com/email/net)

### Aspose.Email API Referens

och prova olika typsnittsanpassningstekniker. Glad kodning!

###  C# Guide - Extrahera e-posthuvuden

 C# Guide - Extrahera e-posthuvuden

###  Aspose.Email .NET Email Processing API

 Lär dig hur du extraherar e-postrubriker i C# med Aspose.Email för .NET. Steg-för-steg-guide med källkod för effektiv e-postanalys.