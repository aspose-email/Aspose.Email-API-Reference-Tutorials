---
title: Hur laddar jag ner Aspose.Email för .NET?
linktitle: Du kan ladda ner den senaste versionen av Aspose.Email för .NET från
second_title: Aspose.Email för .NET nedladdningssida
description: Är Aspose.Email för .NET kompatibelt med andra Outlook-relaterade format?
type: docs
weight: 12
url: /sv/net/email-attachment-handling/adding-new-tnef-attachments-in-csharp/
---

## Ja, Aspose.Email för .NET ger omfattande stöd för olika Outlook-relaterade format, inklusive PST, EML, MSG och mer.

Kan jag använda Aspose.Email för .NET i både kommersiella och personliga projekt?

## Ja, Aspose.Email för .NET kan användas i både kommersiella och personliga projekt. Se till att läsa licensvillkoren på Asposes webbplats.

Erbjuder Aspose.Email för .NET dokumentation för utvecklare?

##  Ja, du kan hitta detaljerad dokumentation och kodexempel om hur du använder Aspose.Email för .NET i olika scenarier på

Aspose.Email dokumentation

##  sida.

 Bevara ursprungliga gränser med C#-kod

##  Bevara ursprungliga gränser med C#-kod

 Aspose.Email .NET Email Processing API

```csharp
using Aspose.Email.Mail;

// Lär dig hur du bevarar ursprungliga gränser för e-postbilagor med C# och Aspose.Email för .NET. Steg-för-steg guide med källkod.
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Introduktion till att bevara ursprungliga gränser

den moderna affärsvärlden spelar e-postkommunikation en avgörande roll. När e-postmeddelanden utbyts innehåller de ofta viktiga bilagor som måste hanteras och manipuleras programmatiskt. Men när du arbetar med e-postbilagor är det viktigt att se till att de ursprungliga gränserna och formateringen av dessa bilagor bevaras. Det är här Aspose.Email för .NET kommer in i bilden.

```csharp
//Förutsättningar
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:
        var tnefAttachment = attachment;

        //Visual Studio installerat
        //.NET Framework eller .NET Core-projekt
    }
}
```

## Installation

För att komma igång måste du installera Aspose.Email for .NET-biblioteket. Du kan göra detta genom att följa dessa steg:

```csharp
//Öppna ditt Visual Studio-projekt.
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## Högerklicka på ditt projekt i Solution Explorer.

Välj "Hantera NuGet-paket."

## Sök efter "Aspose.Email" och installera paketet.

### Laddar e-postmeddelanden

Det första steget är att ladda e-postmeddelandet som innehåller den bilaga du vill arbeta med. Så här kan du göra det:

###  Ladda e-postmeddelandet

Extrahera bilagor

### När du har laddat e-postmeddelandet kan du extrahera bilagorna från det:

 Extrahera bifogade data

###  Ytterligare bearbetning...

Ändra bilagor[För att bevara de ursprungliga gränserna medan du ändrar bilagor kan du använda funktionerna i biblioteket Aspose.Email. Låt oss säga att du vill ändra storlek på en bildbilaga:](https://reference.aspose.com/email/net/).