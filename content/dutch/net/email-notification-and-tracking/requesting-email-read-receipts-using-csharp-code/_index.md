---
title: Leesbevestigingen per e-mail opvragen met C#-code
linktitle: Leesbevestigingen per e-mail opvragen met C#-code
second_title: Aspose.Email .NET E-mailverwerkings-API
description: Leer hoe u C#-code gebruikt om leesbevestigingen voor e-mail aan te vragen met Aspose.Email voor .NET, waardoor het volgen van communicatie wordt verbeterd.
type: docs
weight: 11
url: /nl/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

In het huidige digitale tijdperk is communicatie via e-mail een integraal onderdeel geworden van ons persoonlijke en professionele leven. Vaak willen we er bij het verzenden van belangrijke e-mails zeker van zijn dat de ontvanger ons bericht heeft gelezen en bevestigd. Dit is waar leesbevestigingen voor e-mail een rol gaan spelen. In deze stapsgewijze zelfstudie begeleiden we u bij het aanvragen van leesbevestigingen voor e-mail met behulp van C# met Aspose.Email voor .NET.

## Inleiding tot leesbevestigingen per e-mail

Met e-mailleesbevestigingen, ook wel e-mailtracking of retourbevestigingen genoemd, kunt u meldingen ontvangen wanneer de ontvanger uw e-mail opent en leest. Het is een waardevolle functie, vooral in zakelijke communicatie, omdat het de levering en betrokkenheid van berichten bevestigt.

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Visual Studio is op uw systeem geïnstalleerd.
- Aspose.Email voor .NET-bibliotheek gedownload en waarnaar wordt verwezen in uw project.

## Stap 1: Een MailMessage-instantie maken

 De eerste stap bij het implementeren van leesbevestigingen voor e-mail is het maken van een exemplaar van het`MailMessage` klas. Deze klasse vertegenwoordigt een e-mailbericht en biedt u de mogelijkheid verschillende eigenschappen van de e-mail in te stellen.

```csharp
MailMessage message = new MailMessage();
```

## Stap 2: Berichtdetails opgeven

Laten we nu de details van het e-mailbericht opgeven, inclusief de afzender, ontvanger, HTML-tekst en opties voor bezorgingsmeldingen.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Stap 3: Een SmtpClient-instantie maken

 Om de e-mail te verzenden, moeten we een exemplaar maken van de`SmtpClient` klasse, die verantwoordelijk is voor het verzenden van het bericht.

```csharp
SmtpClient client = new SmtpClient();
```

## Stap 4: SMTP-instellingen configureren

Configureer uw SMTP-serverinstellingen door de hostserver, gebruikersnaam, wachtwoord en poortnummer op te geven.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Stap 5: De e-mail verzenden

 Gebruik ten slotte de`client.Send` methode om het e-mailbericht te verzenden. Als het bericht succesvol is verzonden, wordt de melding "Bericht verzonden" weergegeven.

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

Met deze vijf eenvoudige stappen kunt u leesbevestigingen voor e-mail opvragen wanneer u e-mails verzendt met C# en Aspose.Email voor .NET. Deze functie voegt een extra zekerheid toe aan uw e-mailcommunicatie, zodat u weet wanneer uw belangrijke berichten worden gelezen.

## Volledige broncode
```csharp
// Maak een exemplaar van de MailMessage-klasse
MailMessage message = new MailMessage();

// Geef het veld Van, Aan, HtmlBody, DeliveryNotificationOptions op
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Maak een exemplaar van de SmtpClient-klasse
SmtpClient client = new SmtpClient();

// Geef uw mailinghostserver, gebruikersnaam, wachtwoord en poortnummer op
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send verzendt dit bericht
	client.Send(message);
	// Geef 'Bericht verzonden' weer, alleen als het bericht succesvol is verzonden
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Conclusie

In deze zelfstudie hebben we onderzocht hoe u leesbevestigingen voor e-mail kunt aanvragen met C# met Aspose.Email voor .NET. Het volgen van e-mail is een krachtig hulpmiddel om ervoor te zorgen dat uw berichten worden afgeleverd en gelezen door de beoogde ontvangers, vooral in professionele omgevingen. Door de hier beschreven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw e-mailtoepassing implementeren.

## Veelgestelde vragen (FAQ's)

1. ### Wat is het doel van leesbevestigingen per e-mail?
   Leesbevestigingen voor e-mails bevestigen dat een e-mail is geopend en gelezen door de ontvanger. Ze worden vaak gebruikt voor het volgen van belangrijke of tijdgevoelige berichten.

2. ### Kunnen e-mailleesbevestigingen door de ontvanger worden uitgeschakeld?
   Ja, bij e-mailclients kunnen gebruikers vaak het verzenden van leesbevestigingen uitschakelen. Daarom is het niet gegarandeerd dat u ze altijd zult ontvangen.

3. ### Zijn leesbevestigingen voor e-mail een standaardfunctie in alle e-mailclients?
   Nee, leesbevestigingen voor e-mail worden niet universeel ondersteund. Of ze werken of niet, hangt af van de e-mailclient en de instellingen van de ontvanger.

4. ### Is het mogelijk om bij te houden wanneer een e-mail wordt geopend op een mobiel apparaat?
   Het volgen van e-mails is doorgaans gebaseerd op de e-mailclient en instellingen van de ontvanger. Het kan dus wel of niet werken op mobiele apparaten, afhankelijk van verschillende factoren.

5. ### Zijn er privacyoverwegingen bij het gebruik van leesbevestigingen voor e-mail?
   Ja, er zijn privacyproblemen met betrekking tot het volgen van e-mails. Sommige ontvangers beschouwen het als invasief, dus het is essentieel om deze functie op verantwoorde wijze te gebruiken en de privacyvoorkeuren te respecteren.