---
"description": "Leer hoe u ontvangersadressen opgeeft in C# met Aspose.Email voor .NET. Maak, configureer en verstuur efficiënt e-mails."
"linktitle": "Ontvangeradressen specificeren in C#"
"second_title": "Aspose.Email .NET e-mailverwerkings-API"
"title": "Ontvangeradressen specificeren in C#"
"url": "/nl/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ontvangeradressen specificeren in C#



Deze handleiding begeleidt u bij het specificeren van ontvangersadressen in C# met behulp van de Aspose.Email voor .NET-bibliotheek. Aspose.Email is een krachtige .NET API waarmee u met e-mailberichten en diverse e-mailgerelateerde taken kunt werken. In deze tutorial leggen we uit hoe u ontvangersadressen aan een e-mailbericht kunt toevoegen met behulp van de bibliotheek.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:

1. Visual Studio of een andere C#-ontwikkelomgeving geïnstalleerd.
2. Aspose.Email voor .NET-bibliotheek. U kunt het verkrijgen via de [Aspose.Email voor .NET-releases](https://releases.aspose.com/email/net/).

## Stappen

Volg deze stappen om ontvangeradressen op te geven in C# met behulp van Aspose.Email voor .NET:

### 1. Maak een nieuw C#-project

Begin met het maken van een nieuw C#-project in uw ontwikkelomgeving.

### 2. Voeg een verwijzing naar Aspose.Email toe

1. Download en installeer de Aspose.Email voor .NET-bibliotheek als u dit nog niet hebt gedaan.
2. Open uw C#-project.
3. Klik met de rechtermuisknop op 'Referenties' in Solution Explorer en selecteer 'Referentie toevoegen'.
4. Blader door en selecteer de Aspose.Email DLL-bestanden die u hebt gedownload.

### 3. Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de benodigde naamruimten voor het gebruik van Aspose.Email-klassen:

```csharp
using Aspose.Email;

```

### 4. Maak en configureer het e-mailbericht

Maak een nieuw exemplaar van de `MailMessage` klasse om uw e-mailbericht weer te geven. Configureer de afzender en het onderwerp van de e-mail:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Ontvangeradressen toevoegen

U kunt ontvangersadressen toevoegen met behulp van de `To`, `Cc`, En `Bcc` eigenschappen van de `MailMessage` klasse. Zo kunt u ontvangersadressen toevoegen:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Maak het e-mailbericht af

Voeg de e-mailtekst en eventuele andere noodzakelijke inhoud toe aan uw e-mailbericht:

```csharp
message.Body = "This is the email body.";
```

### 7. Verstuur de e-mail

Om de e-mail te versturen, kunt u de `SmtpClient` klasse geleverd door Aspose.Email. Configureer de SMTP-serverinstellingen en verstuur de e-mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Veelgestelde vragen

### Hoe kan ik meerdere ontvangers toevoegen aan de `To`, `Cc`, of `Bcc` velden?

U kunt meerdere ontvangers toevoegen door de `Add` methode meerdere keren op de respectievelijke `MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Kan ik naast mijn e-mailadres ook de naam van de ontvanger opgeven?

Ja, u kunt zowel de naam als het e-mailadres van de ontvanger opgeven bij het toevoegen van ontvangers:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Hoe ga ik om met uitzonderingen bij het versturen van een e-mail?

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

Voor meer informatie en geavanceerde functies van Aspose.Email voor .NET, raadpleeg de [Aspose API-referenties](https://reference.aspose.com/email/net/).

Dit is het einde van de handleiding over het specificeren van ontvangersadressen in C# met behulp van Aspose.Email voor .NET. U hebt geleerd hoe u een e-mailbericht maakt, ontvangersadressen toevoegt en de e-mail verzendt met behulp van de functies van de bibliotheek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}