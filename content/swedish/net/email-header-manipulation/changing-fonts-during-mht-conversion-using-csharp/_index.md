---
title: Ändra teckensnitt under MHT-konvertering med C#
linktitle: Ändra teckensnitt under MHT-konvertering med C#
second_title: Aspose.Email .NET Email Processing API
description: Lär dig hur du ändrar teckensnitt under MHT-konvertering med Aspose.Email för .NET. Steg-för-steg guide med källkod. Perfekt för e-postarkivering och dokumenthantering.
type: docs
weight: 11
url: /sv/net/email-header-manipulation/changing-fonts-during-mht-conversion-using-csharp/
---

Har du någonsin stött på behovet av att konvertera ett e-postmeddelande till MHT-format samtidigt som du bevarar dess teckensnitt? Den här guiden leder dig genom processen att ändra teckensnitt under MHT-konvertering med hjälp av det kraftfulla Aspose.Email for .NET-biblioteket. Oavsett om du arbetar med e-postarkivering, dokumenthantering eller något annat projekt som involverar e-postkonvertering, hjälper den här steg-för-steg-guiden dig att nå ditt mål sömlöst.

## Introduktion till MHT Conversion och Aspose.Email för .NET

### Vad är MHT?

MHT (MIME HTML) är ett filformat som låter dig spara en webbsida, inklusive alla dess resurser, i ett enda dokument. Det används ofta för att arkivera webbsidor och e-postmeddelanden, eftersom det behåller strukturen och utseendet på det ursprungliga innehållet.

### Om Aspose.Email för .NET

Aspose.Email för .NET är ett robust bibliotek som tillhandahåller funktioner för att arbeta med e-postformat, inklusive att ladda, analysera och konvertera e-postmeddelanden. Det är ett idealiskt val för utvecklare som behöver hantera olika e-postrelaterade uppgifter effektivt.

## Konfigurera ditt projekt

### Installera Aspose.Email för .NET

 För att komma igång måste du installera Aspose.Email for .NET-biblioteket. Du kan ladda ner den från[Aspose.Releases](https://releases.aspose.com/email/net) eller använd NuGet Package Manager i Visual Studio.

### Skapa ett nytt .NET-projekt

1. Öppna Visual Studio och skapa ett nytt .NET-projekt.
2. Installera Aspose.Email for .NET-biblioteket med NuGet Package Manager.
3. Du är nu redo att börja koda!

## Laddar och analyserar ett e-postmeddelande

### Laddar ett e-postmeddelande

Innan vi kan ändra typsnitten i e-postmeddelandet måste vi ladda ett e-postmeddelande. Du kan ladda ett e-postmeddelande från olika källor, till exempel en fil, stream eller till och med en e-postserver.

```csharp
// Ladda e-postmeddelandet
var message = MailMessage.Load("sample.eml");
```

### Parsar meddelandetexten

När e-postmeddelandet har laddats kan du komma åt dess olika delar, inklusive HTML-kroppen. Genom att analysera HTML-kroppen kan vi göra teckensnittsändringar.

```csharp
// Analysera HTML-kroppen
var htmlBody = message.HtmlBody;
```

## Ändra teckensnitt i e-postmeddelandet

### Förstå teckensnittsstilar

Teckensnitt i HTML-e-postmeddelanden definieras med CSS-stilar. För att ändra teckensnitt måste du ändra CSS-stilarna som är kopplade till e-postmeddelandets HTML-innehåll.

### Ändra teckensnitt programmerat

Låt oss säga att du vill ändra teckensnittet för ett stycke i e-postmeddelandets HTML-text. Så här kan du göra det:

```csharp
// Ändra teckensnitt för ett stycke
htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");
```

## Konvertera till MHT-format

### Skapar MHT-meddelande

För att konvertera e-postmeddelandet till MHT-format måste du skapa ett MHT-formaterat e-postmeddelande med Aspose.Email.

```csharp
// Skapa MHT-formaterat e-postmeddelande
var mhtMessage = MhtMessage.FromMailMessage(message);
```

### Spara meddelandet i MHT-format

Slutligen, spara det MHT-formaterade meddelandet till en fil.

```csharp
// Spara meddelandet i MHT-format
mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
```

## Komplett källkod

Här är den kompletta källkoden som sätter ihop allt:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;

class Program
{
    static void Main()
    {
        var message = MailMessage.Load("sample.eml");
        var htmlBody = message.HtmlBody;
        htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");

        var mhtMessage = MhtMessage.FromMailMessage(message);
        mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
    }
}
```

## Slutsats

den här guiden utforskade vi hur man ändrar teckensnitt under MHT-konvertering med Aspose.Email för .NET. Genom att följa dessa steg kan du sömlöst konvertera e-postmeddelanden till MHT-format samtidigt som du behåller önskade teckensnittsstilar.


## Vanliga frågor


### Kan jag konvertera flera e-postmeddelanden till MHT-format på en gång?

Ja, du kan gå igenom en samling e-postmeddelanden och tillämpa samma teckensnittsändringar på varje meddelande innan du konverterar dem till MHT-format.

### Stöder Aspose.Email även andra e-postformat?

Ja, Aspose.Email stöder olika e-postformat, inklusive EML, MSG, PST och mer.

### Är det möjligt att anpassa teckensnittsändringarna ytterligare?

Absolut! Du kan utforska fler CSS-stilar för att anpassa teckensnitt, som teckenstorlek, färg och justering.

### Kan jag använda Aspose.Email för kommersiella projekt?

Ja, Aspose.Email kan användas för både personliga och kommersiella projekt, enligt licensvillkoren.

 Kom ihåg att den här guiden ger en allmän översikt och att du kan utforska vidare genom att hänvisa till[Aspose.Email API Referens](https://reference.aspose.com/email/net/)och prova olika typsnittsanpassningstekniker. Glad kodning!