---
title: Ställa in alternativ text för bilder - C# Guide
linktitle: Ställa in alternativ text för bilder - C# Guide
second_title: Aspose.Email .NET Email Processing API
description: Lär dig att ställa in alternativ text för bilder i e-postmeddelanden med Aspose.Email för .NET. Säkerställ tillgänglighet med tydlig alt-text. Dokumentation och kod ingår.
type: docs
weight: 15
url: /sv/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Den här guiden leder dig genom processen att ställa in alternativ text för bilder i e-postmeddelanden med Aspose.Email för .NET. Alternativ text, även känd som "alt text", används för att ge en textbeskrivning av en bild om bilden inte kan visas. Aspose.Email för .NET är ett kraftfullt bibliotek som låter dig arbeta med e-postmeddelanden och bilagor i olika format. I den här guiden kommer vi att fokusera på att ställa in alternativ text för bilder i e-postmeddelanden med C#.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar:

1. Visual Studio eller någon kompatibel C#-utvecklingsmiljö installerad.
2. Aspose.Email för .NET-biblioteket. Du kan använda NuGet Package Manager i Visual Studio.

## Steg 1: Skapa ett nytt projekt

1. Starta Visual Studio och skapa ett nytt C#-konsolapplikationsprojekt.

## Steg 2: Installera Aspose.Email via NuGet

1. Högerklicka på ditt projekt i Solution Explorer och välj "Hantera NuGet-paket."
2. Sök efter "Aspose.Email" och installera den senaste versionen av paketet.

## Steg 3: Lägg till med hjälp av uttalanden

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## Steg 4: Ladda och ändra e-postmeddelandet

1.  Ladda e-postmeddelandet med hjälp av`MailMessage` klass:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Ladda HTML-innehållet i e-postmeddelandet:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Steg 5: Lägg till AlternativeView för alternativ text till bilder

Lägg till htmlview för alternativ text till bild som AlternateView i meddelandet. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Steg 6: Spara och skicka e-postmeddelandet

1. Spara det ändrade meddelandet i en fil eller skicka det med önskad metod:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Slutsats

I den här guiden lärde du dig hur du ställer in alternativ text för bilder i e-postmeddelanden med Aspose.Email för .NET. Genom att följa stegen som beskrivs ovan kan du säkerställa att ditt e-postinnehåll förblir tillgängligt och informativt även när bilder inte kan visas.

## FAQ

## Hur kan jag ladda ner Aspose.Email-biblioteket?

Du kan ladda ner Aspose.Email-biblioteket från Aspose-versionerna eller installera det via NuGet Package Manager i Visual Studio.

### Hur lägger jag till bilder som länkade resurser i ett e-postmeddelande?

För att lägga till bilder som länkade resurser i ett e-postmeddelande kan du använda`LinkedResource` klass. Tilldela ett innehålls-ID till den länkade resursen och referera sedan till detta innehålls-ID i HTML-kroppen med hjälp av`cid:` schema. För detaljerad information, se[LinkedResource dokumentation](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Var kan jag hitta mer dokumentation om Aspose.Email för .NET?

 Du kan hitta mer detaljerad dokumentation, handledningar och exempel på hur du arbetar med Aspose.Email för .NET i[API-referens](https://reference.aspose.com/email/net/).