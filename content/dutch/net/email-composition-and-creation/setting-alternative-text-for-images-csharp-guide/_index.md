---
title: Alternatieve tekst voor afbeeldingen instellen - C#-handleiding
linktitle: Alternatieve tekst voor afbeeldingen instellen - C#-handleiding
second_title: Aspose.Email .NET E-mailverwerkings-API
description: Leer hoe u alternatieve tekst voor afbeeldingen in e-mails kunt instellen met Aspose.Email voor .NET. Zorg voor toegankelijkheid met duidelijke alt-tekst. Documentatie en code inbegrepen.
type: docs
weight: 15
url: /nl/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Deze handleiding begeleidt u bij het instellen van alternatieve tekst voor afbeeldingen in e-mails met behulp van Aspose.Email voor .NET. Alternatieve tekst, ook wel 'alt-tekst' genoemd, wordt gebruikt om een tekstuele beschrijving van een afbeelding te geven voor het geval de afbeelding niet kan worden weergegeven. Aspose.Email voor .NET is een krachtige bibliotheek waarmee u met e-mails en bijlagen in verschillende formaten kunt werken. In deze handleiding zullen we ons concentreren op het instellen van alternatieve tekst voor afbeeldingen in e-mailberichten met behulp van C#.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio of een compatibele C#-ontwikkelomgeving geïnstalleerd.
2. Aspose.Email voor .NET-bibliotheek. U kunt NuGet Package Manager gebruiken in Visual Studio.

## Stap 1: Maak een nieuw project

1. Start Visual Studio en maak een nieuw C#-consoletoepassingsproject.

## Stap 2: Installeer Aspose.Email via NuGet

1. Klik met de rechtermuisknop op uw project in de Solution Explorer en selecteer 'NuGet-pakketten beheren'.
2. Zoek naar "Aspose.Email" en installeer de nieuwste versie van het pakket.

## Stap 3: Voeg gebruiksverklaringen toe

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## Stap 4: Laad en wijzig het e-mailbericht

1.  Laad het e-mailbericht met behulp van de`MailMessage` klas:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Laad de HTML-inhoud van het e-mailbericht:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Stap 5: Voeg AlternativeView toe voor alternatieve tekst aan afbeeldingen

Voeg htmlview voor alternatieve tekst naar afbeelding toe als AlternateView in het bericht. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Stap 6: Bewaar en verzend de e-mail

1. Sla het gewijzigde bericht op in een bestand of verstuur het via de door u gewenste methode:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Conclusie

In deze handleiding hebt u geleerd hoe u alternatieve tekst voor afbeeldingen in e-mailberichten kunt instellen met Aspose.Email voor .NET. Door de hierboven beschreven stappen te volgen, kunt u ervoor zorgen dat uw e-mailinhoud toegankelijk en informatief blijft, zelfs als er geen afbeeldingen kunnen worden weergegeven.

## FAQ

## Hoe kan ik de Aspose.Email-bibliotheek downloaden?

U kunt de Aspose.Email-bibliotheek downloaden van de Aspose-releases of deze installeren via NuGet Package Manager in Visual Studio.

### Hoe voeg ik afbeeldingen toe als gekoppelde bronnen in een e-mail?

Om afbeeldingen als gekoppelde bronnen aan een e-mail toe te voegen, kunt u de`LinkedResource` klas. Wijs een inhouds-ID toe aan de gekoppelde bron en verwijs vervolgens naar deze inhouds-ID in de HTML-tekst met behulp van de`cid:` schema. Voor gedetailleerde informatie, zie de[LinkedResource-documentatie](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Waar kan ik meer documentatie vinden over Aspose.Email voor .NET?

 Meer gedetailleerde documentatie, tutorials en voorbeelden over het werken met Aspose.Email voor .NET vindt u in de[API-referentie](https://reference.aspose.com/email/net/).