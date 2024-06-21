---
title: Ontvangeradressen opgeven in C#
linktitle: Ontvangeradressen opgeven in C#
second_title: Aspose.Email .NET E-mailverwerkings-API
description: Leer hoe u ontvangersadressen kunt opgeven in C# met behulp van Aspose.Email voor .NET. E-mails efficiënt maken, configureren en verzenden.
type: docs
weight: 19
url: /nl/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Deze handleiding leidt u door het proces van het opgeven van ontvangersadressen in C# met behulp van de Aspose.Email voor .NET-bibliotheek. Aspose.Email is een krachtige .NET API waarmee u kunt werken met e-mailberichten en verschillende e-mailgerelateerde taken. In deze zelfstudie bespreken we hoe u ontvangersadressen kunt toevoegen aan een e-mailbericht met behulp van de bibliotheek.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Visual Studio of een andere C#-ontwikkelomgeving geïnstalleerd.
2.  Aspose.Email voor .NET-bibliotheek. U kunt deze verkrijgen bij de[Aspose.Email voor .NET-releases](https://releases.aspose.com/email/net/).

## Stappen

Volg deze stappen om ontvangersadressen in C# op te geven met Aspose.Email voor .NET:

### 1. Maak een nieuw C#-project

Begin met het maken van een nieuw C#-project in uw ontwikkelomgeving.

### 2. Voeg een verwijzing toe naar Aspose.Email

1. Download en installeer de Aspose.Email voor .NET-bibliotheek als u dat nog niet heeft gedaan.
2. Open uw C#-project.
3. Klik met de rechtermuisknop op de "Referenties" in de Solution Explorer en selecteer "Referentie toevoegen".
4. Blader en selecteer de Aspose.Email DLL-bestanden die u hebt gedownload.

### 3. Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de benodigde naamruimten voor het gebruik van Aspose.Email-klassen:

```csharp
using Aspose.Email;

```

### 4. Maak en configureer het e-mailbericht

 Maak een nieuw exemplaar van de`MailMessage` klasse om uw e-mailbericht weer te geven. Configureer de afzender en het onderwerp van de e-mail:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Voeg ontvangersadressen toe

 kunt ontvangersadressen toevoegen met behulp van de`To`, `Cc` , En`Bcc` eigenschappen van de`MailMessage` klas. Zo kunt u adressen van ontvangers toevoegen:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Voltooi het e-mailbericht

Voeg de hoofdtekst van de e-mail en eventuele andere noodzakelijke inhoud toe aan uw e-mailbericht:

```csharp
message.Body = "This is the email body.";
```

### 7. Verstuur de e-mail

 Om de e-mail te verzenden, kunt u de`SmtpClient` klasse aangeboden door Aspose.Email. Configureer de SMTP-serverinstellingen en verzend de e-mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Veelgestelde vragen

###  Hoe kan ik meerdere ontvangers toevoegen aan het`To`, `Cc`, or `Bcc` fields?

 U kunt meerdere ontvangers toevoegen door te bellen naar`Add` methode meerdere keren op de betreffende`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Kan ik de namen van ontvangers opgeven samen met hun e-mailadressen?

Ja, u kunt zowel de naam als het e-mailadres van de ontvanger opgeven wanneer u ontvangers toevoegt:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Hoe ga ik om met uitzonderingen bij het verzenden van een e-mail?

U kunt try-catch-blokken gebruiken om uitzonderingen af te handelen die kunnen optreden tijdens het verzenden van e-mail:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 Voor meer informatie en geavanceerde functies van Aspose.Email voor .NET raadpleegt u de[Stel API-referenties voor](https://reference.aspose.com/email/net/).

Hiermee wordt de handleiding afgesloten over het opgeven van ontvangersadressen in C# met behulp van Aspose.Email voor .NET. U hebt geleerd hoe u een e-mailbericht maakt, adressen van ontvangers toevoegt en de e-mail verzendt met behulp van de functies van de bibliotheek.