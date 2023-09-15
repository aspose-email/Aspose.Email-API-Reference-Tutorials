---
title: Begär läskvitton för e-post med C#-kod
linktitle: Begär läskvitton för e-post med C#-kod
second_title: Aspose.Email .NET Email Processing API
description: Lär dig hur du använder C#-kod för att begära läskvitton via e-post med Aspose.Email för .NET, vilket förbättrar kommunikationsspårningen.
type: docs
weight: 11
url: /sv/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

I dagens digitala tidsålder har kommunikation via e-post blivit en integrerad del av vårt personliga och professionella liv. När vi skickar viktiga e-postmeddelanden vill vi ofta försäkra oss om att mottagaren har läst och bekräftat vårt meddelande. Det är här läskvitton för e-post kommer in i bilden. I denna steg-för-steg handledning guidar vi dig genom processen att begära läskvitton via e-post med C# med Aspose.Email för .NET.

## Introduktion till läskvitton för e-post

Läskvitton för e-post, även känd som e-postspårning eller returkvitton, gör att du kan få meddelanden när mottagaren öppnar och läser din e-post. Det är en värdefull funktion, särskilt inom affärskommunikation, eftersom det ger bekräftelse på meddelandeleverans och engagemang.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:

- Visual Studio installerat på ditt system.
- Aspose.Email för .NET-bibliotek laddas ner och refereras till i ditt projekt.

## Steg 1: Skapa en MailMessage-instans

 Det första steget för att implementera läskvitton för e-post är att skapa en instans av`MailMessage` klass. Den här klassen representerar ett e-postmeddelande och låter dig ställa in olika egenskaper för e-postmeddelandet.

```csharp
MailMessage message = new MailMessage();
```

## Steg 2: Ange meddelandedetaljer

Låt oss nu specificera detaljerna för e-postmeddelandet, inklusive avsändare, mottagare, HTML-text och leveransaviseringsalternativ.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Steg 3: Skapa en SmtpClient-instans

 För att skicka e-postmeddelandet måste vi skapa en instans av`SmtpClient` klass, som ansvarar för att skicka meddelandet.

```csharp
SmtpClient client = new SmtpClient();
```

## Steg 4: Konfigurera SMTP-inställningar

Konfigurera dina SMTP-serverinställningar genom att ange värdserver, användarnamn, lösenord och portnummer.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Steg 5: Skicka e-postmeddelandet

 Använd slutligen`client.Send` metod för att skicka e-postmeddelandet. Om meddelandet skickas framgångsrikt visas ett meddelande som skickats.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

Med dessa fem enkla steg kan du begära läskvitton via e-post när du skickar e-post med C# och Aspose.Email för .NET. Den här funktionen lägger till ett lager av säkerhet till din e-postkommunikation, vilket säkerställer att du vet när dina viktiga meddelanden läses.

## Komplett källkod
```csharp
// Skapa en instans av klassen MailMessage
MailMessage message = new MailMessage();

// Ange Från, Till, HtmlBody, DeliveryNotificationOptions-fältet
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Skapa en instans av SmtpClient Class
SmtpClient client = new SmtpClient();

// Ange din e-postvärdserver, användarnamn, lösenord och portnr
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send skickar detta meddelande
	client.Send(message);
	// Visa "Meddelande skickat", endast om meddelandet har skickats
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Slutsats

den här handledningen har vi utforskat hur man begär läskvitton via e-post med C# med Aspose.Email för .NET. E-postspårning är ett kraftfullt verktyg för att säkerställa att dina meddelanden levereras och läses av de avsedda mottagarna, särskilt i professionella miljöer. Genom att följa stegen som beskrivs här kan du enkelt implementera denna funktion i ditt e-postprogram.

## Vanliga frågor (FAQs)

1. ### Vad är syftet med läskvitton via e-post?
   Läskvitton för e-post ger en bekräftelse på att ett e-postmeddelande har öppnats och lästs av mottagaren. De används ofta för att spåra viktiga eller tidskänsliga meddelanden.

2. ### Kan läskvitton för e-post inaktiveras av mottagaren?
   Ja, e-postklienter tillåter ofta användare att inaktivera sändning av läskvitton. Därför är det inte garanterat att du alltid kommer att få dem.

3. ### Är läskvitton för e-post en standardfunktion i alla e-postklienter?
   Nej, läskvitton för e-post stöds inte universellt. Om de fungerar eller inte beror på e-postklienten och mottagarens inställningar.

4. ### Är det möjligt att spåra när ett e-postmeddelande öppnas på en mobil enhet?
   E-postspårning baseras vanligtvis på mottagarens e-postklient och inställningar, så det kanske fungerar eller inte fungerar på mobila enheter, beroende på olika faktorer.

5. ### Finns det integritetsfrågor när du använder läskvitton via e-post?
   Ja, det finns integritetsproblem relaterade till e-postspårning. Vissa mottagare kan anse det som invasivt, så det är viktigt att använda den här funktionen på ett ansvarsfullt sätt och respektera integritetspreferenser.