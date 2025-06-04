---
"date": "2025-05-30"
"description": "Leer hoe u contactbeheer kunt integreren met Exchange-servers met Aspose.Email voor .NET via EWS. Deze handleiding behandelt het efficiënt instellen, verbinden en ophalen van contacten."
"title": "Contacten ophalen met Aspose.Email en EWS in .NET&#58; een uitgebreide handleiding"
"url": "/nl/net/exchange-server-integration/retrieve-contacts-aspose-email-net-exchange-ews/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Contacten ophalen met Aspose.Email en EWS in .NET: een uitgebreide handleiding

## Invoering

Het beheren van contacten vanaf een Exchange-server integreert naadloos met uw .NET-applicaties, waardoor communicatieworkflows worden gestroomlijnd, tijd wordt bespaard en de productiviteit wordt verhoogd. Deze tutorial begeleidt u bij het gebruik van de krachtige **Aspose.Email voor .NET** API om via een webservice (EWS) verbinding te maken met een Exchange-server en een lijst met contactpersonen op te halen.

### Wat je leert:
- Aspose.Email voor .NET in uw project instellen
- Verbinding maken met een Exchange-server via EWS
- Contactgegevens programmatisch ophalen en weergeven

Met deze vaardigheden kunt u e-mailcommunicatie gemakkelijk beheren. Laten we beginnen met het begrijpen van de vereisten.

## Vereisten

Voordat u met de code-implementatie begint, moet u ervoor zorgen dat uw ontwikkelomgeving klaar is voor gebruik:

- **Bibliotheken en versies**: Zorg ervoor dat u Aspose.Email voor .NET hebt geïnstalleerd.
- **Omgevingsinstelling**: U hebt een .NET-ontwikkelomgeving nodig, zoals Visual Studio 2019 of hoger.
- **Kennisvereisten**:Een basiskennis van C# en het werken met API's is nuttig.

## Aspose.Email instellen voor .NET

Om te beginnen moet u de Aspose.Email-bibliotheek aan uw project toevoegen. Zo doet u dat:

### Installatie

**Met behulp van .NET CLI:**
```bash
dotnet add package Aspose.Email
```

**Pakketbeheerconsole gebruiken:**
```powershell
Install-Package Aspose.Email
```

**Via de NuGet Package Manager-gebruikersinterface:**
Zoek naar "Aspose.Email" en installeer de nieuwste versie.

### Licentieverwerving

Je kunt beginnen met een **gratis proefperiode** om de functies te verkennen. Voor langere projecten kunt u overwegen een licentie aan te schaffen of een tijdelijke licentie aan te vragen:
- [Gratis proefperiode](https://releases.aspose.com/email/net/)
- [Licentie kopen](https://purchase.aspose.com/buy)
- [Tijdelijke licentie](https://purchase.aspose.com/temporary-license/)

Initialiseer uw project door de benodigde using-richtlijnen toe te voegen en een exemplaar van `IEWSClient` voor het instellen van de verbinding.

## Implementatiegids

In dit gedeelte worden alle stappen voor het ophalen van contactpersonen van een Exchange-server beschreven.

### Stap 1: Maak een IEWSClient-instantie

**Overzicht**Maak een beveiligde verbinding met uw Exchange-server met behulp van de EWS-client van Aspose.Email.

```csharp
IEWSClient client = EWSClient.GetEWSClient(
    "https://outlook.office365.com/ews/exchange.asmx", 
    "testUser",    
    "pwd",         
    "domain"       
);
```

**Uitleg**: Vervangen `"testUser"`, `"pwd"`, En `"domain"` met uw daadwerkelijke Exchange-serverreferenties. Deze stap verifieert en initialiseert de verbinding.

### Stap 2: Alle contacten weergeven

**Overzicht**: Haal contacten op uit uw mailbox met behulp van EWS.

```csharp
Contact[] contacts = client.GetContacts(client.MailboxInfo.ContactsUri);
```

**Uitleg**: `client.GetContacts` Haalt alle beschikbare contacten op. De methode retourneert een array met contactobjecten, die vervolgens verwerkt kunnen worden.

### Stap 3: Contactgegevens weergeven

**Overzicht**: Loop over de opgehaalde contactpersonen om hun namen en e-mailadressen weer te geven.

```csharp
foreach (MapiContact contact in contacts)
{
    Console.WriteLine(
        "Name: " + contact.NameInfo.DisplayName + ", Email Address: " +
        contact.ElectronicAddresses.Email1
    );
}
```

**Uitleg**: Loop door elk `MapiContact` om toegang te krijgen tot belangrijke informatie, zoals uw naam en e-mailadres, en deze weer te geven.

### Tips voor probleemoplossing

- Zorg ervoor dat de server-URL, gebruikersnaam, wachtwoord en domein correct zijn geconfigureerd.
- Controleer de netwerkconnectiviteit als u geen verbinding kunt maken met de Exchange-server.
- Controleer of uw API-versie compatibel is met uw .NET Framework-versie.

## Praktische toepassingen

Hier volgen enkele praktijkscenario's waarbij het ophalen van contacten via Aspose.Email nuttig kan zijn:
1. **Geautomatiseerde e-mailcampagnes**: Automatisch contactenlijsten verzamelen en bijwerken voor marketingdoeleinden.
2. **CRM-integratie**: Synchroniseer contactgegevens tussen Exchange Server en CRM-systemen zoals Salesforce of Dynamics 365.
3. **Oplossingen voor gegevensback-up**: Maak back-ups van contactgegevens en zorg zo voor bedrijfscontinuïteit.

## Prestatieoverwegingen

Bij het werken met Aspose.Email in .NET-toepassingen:
- **Optimaliseer netwerkoproepen**: Minimaliseer het aantal API-aanroepen door alleen de vereiste velden op te halen.
- **Efficiënt geheugenbeheer**: Verwijder objecten die niet meer nodig zijn om geheugenbronnen vrij te maken.
- **Batchverwerking**:Als u met grote datasets werkt, kunt u overwegen om contacten in batches te verwerken.

## Conclusie

hebt nu geleerd hoe u verbinding kunt maken met een Exchange-server en contacten kunt ophalen met Aspose.Email voor .NET. Deze krachtige tool kan de e-mailbeheermogelijkheden van uw applicatie aanzienlijk verbeteren. Voor verdere verdieping kunt u zich verdiepen in geavanceerde functies van de API, zoals het verzenden van e-mails of het beheren van agenda's.

Onderneem vandaag nog actie en probeer deze implementatie in uw projecten!

## FAQ-sectie

1. **Wat is Aspose.Email voor .NET?**
   - Het is een bibliotheek die de interactie met e-mailservers zoals Exchange via verschillende protocollen, waaronder EWS, mogelijk maakt.
2. **Hoe ga ik om met authenticatiefouten wanneer ik verbinding maak met een Exchange-server?**
   - Controleer uw inloggegevens en zorg ervoor dat de server-URL correct is.
3. **Kan Aspose.Email offline werken?**
   - Hoewel het voornamelijk met onlinediensten communiceert, kunt u ook offline lokale bestanden bewerken, zoals PST- of MSG-indelingen.
4. **Zit er een limiet aan het aantal contacten dat ik tegelijk kan ophalen?**
   - Contactlimieten zijn afhankelijk van de configuratie van uw Exchange-server. Neem indien nodig contact op met uw systeembeheerder.
5. **Hoe werk ik de gegevens van een contactpersoon bij met Aspose.Email?**
   - Gebruik de `UpdateContact` methode na het wijzigen van eigenschappen van een `MapiContact`.

## Bronnen

- [Aspose.Email Documentatie](https://reference.aspose.com/email/net/)
- [Download Aspose.E-mail](https://releases.aspose.com/email/net/)
- [Licentie kopen](https://purchase.aspose.com/buy)
- [Gratis proefperiode](https://releases.aspose.com/email/net/)
- [Tijdelijke licentie](https://purchase.aspose.com/temporary-license/)
- [Ondersteuningsforum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}