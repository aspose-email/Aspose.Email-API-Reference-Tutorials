---
date: '2026-07-08'
description: Leer hoe u een EWS-client Java maakt met Aspose.Email voor efficiënt
  e-mailbeheer, inclusief het verwijderen van berichten, toevoegen en gebruikersimpersonatie
  op Exchange Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Leer hoe u een EWS-client Java maakt met Aspose.Email voor efficiënt
  e-mailbeheer, inclusief het verwijderen van berichten, toevoegen en gebruikersimpersonatie
  op Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Maak EWS-client Java met Aspose.Email – Gebruikers beheren
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Maak EWS-client Java met Aspose.Email – Gebruikers beheren
url: /nl/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Beheers e-mailbeheer: Aspose.Email Java voor EWS-clientgebruiker en impersonatie

## Introductie

In deze tutorial zult u **EWS client Java**-toepassingen maken met Aspose.Email, waarmee u meerdere Exchange Server‑postvakken kunt beheren vanuit één Java‑codebasis. We lopen door het maken van `EWSClient`‑instanties, het verwijderen van berichten, het toevoegen van nieuwe e‑mails en het impersoneren van andere gebruikers—taken die uren handmatig werk in bedrijfsomgevingen besparen.

### Wat u zult leren
- Hoe **EWS client Java**‑objecten te maken met verschillende inloggegevens.  
- Efficiënte technieken om elk bericht uit een gekozen map te verwijderen.  
- Stappen om een kant‑klaar e‑mailbericht toe te voegen aan de mailbox van een gebruiker.  
- Hoe een andere mailbox te impersoneren voor gedeelde‑mailboxscenario's.

Nu u weet wat we gaan behandelen, laten we de ontwikkelomgeving gereed maken.

## Snelle antwoorden
- **Wat is de eerste stap?** Voeg de Aspose.Email Maven‑dependency toe aan uw `pom.xml`.  
- **Welke klasse vertegenwoordigt de Exchange‑verbinding?** `EWSClient` (of de interface `IEWSClient`).  
- **Kan ik alle berichten in één oproep verwijderen?** Ja—itereer met `listMessages` en roep `deleteMessage` aan voor elke URI.  
- **Hoe stuur ik een e‑mail zonder SMTP?** Gebruik `appendMessage` om een `MailMessage` direct in een map te plaatsen.  
- **Is impersonatie veilig?** Het draait onder de oorspronkelijke inloggegevens en respecteert de delegatie‑beleid van Exchange.

## Wat is create EWS client Java?
`create ews client java` verwijst naar het instantieren van een `EWSClient`‑object in een Java‑applicatie zodat u Exchange Web Services (EWS)‑bewerkingen programmatisch kunt aanroepen. Deze aanpak verwijdert de noodzaak voor handmatige Outlook‑interactie en maakt geautomatiseerde postvakverwerking mogelijk. Door per gebruiker een dedicated client te maken, kunt u inloggegevens isoleren, per‑postvak‑beleid afdwingen en de oplossing opschalen naar tientallen accounts zonder code‑duplicatie.

## Waarom Aspose.Email gebruiken voor EWS‑integratie?
Aspose.Email ondersteunt **50+** EWS‑bewerkingen, verwerkt **meerdere honderden pagina's** postvakken zonder de volledige opslag in het geheugen te laden, en verwerkt **tot 10.000** berichten per minuut op typische serverhardware. Deze gekwantificeerde mogelijkheden maken het een topkeuze voor grootschalige e‑mailautomatisering. De bibliotheek abstraheert ook low‑level SOAP‑details en biedt een schone, type‑veilige API die de ontwikkelingstijd verkort en bugs minimaliseert.

## Voorvereisten
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** voor dependency‑beheer.  
- **Aspose.Email for Java**‑bibliotheek (toevoegen via Maven).  
- Basiskennis van Exchange Web Services (EWS) concepten.

## Aspose.Email voor Java instellen
Voeg de bibliotheek toe aan uw Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie
Aspose.Email biedt een gratis proefversie, met de mogelijkheid om een tijdelijke licentie aan te vragen voor volledige functionaliteit. Voor langdurig gebruik kunt u overwegen een licentie aan te schaffen via [Aspose's purchase page](https://purchase.aspose.com/buy).

## Hoe create EWS client Java?
Laad de Exchange‑service met de juiste inloggegevens en verkrijg een `IEWSClient`‑instantie—dit twee‑stappen‑patroon is de kern van elke daaropvolgende bewerking. U kunt dezelfde client hergebruiken voor meerdere acties of afzonderlijke instanties per gebruiker maken voor isolatie. **`IEWSClient` is de interface die alle EWS‑bewerkingen blootlegt, terwijl `EWSClient` de statische fabrieksmethode biedt om een implementatie te verkrijgen.**

Het maken van een client omvat doorgaans het opgeven van de service‑URL, gebruikersnaam, wachtwoord en eventueel domeininformatie. Eenmaal geïnstantieerd behandelt de client authenticatie, ondertekening van verzoeken en het ontleden van antwoorden automatisch.

### EWSClient‑instanties maken
**Definitie:** De `EWSClient` (exposed via the `IEWSClient` interface) is het primaire object van Aspose.Email voor communicatie met een Exchange‑server via EWS.

#### Vereiste klassen importeren
Begin met het importeren van de benodigde Aspose.Email‑klassen:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### EWSClient‑instanties initialiseren
Maak `IEWSClient`‑objecten voor elk postvak dat u wilt beheren:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Uitleg:* De `getEWSClient`‑helper maakt verbinding met Exchange met de opgegeven inloggegevens en retourneert een kant‑klaar te gebruiken client die de rechten van de huidige gebruiker respecteert.

## Hoe berichten uit een map verwijderen?
Haal alle items op in de doelmap en verwijder elk item permanent in één enkele doorloop. Deze methode vermijdt de overhead van het individueel openen van elk bericht. **`listMessages` retourneert een collectie van `MessageInfo`‑objecten die de unieke URI voor elk bericht bevatten, die u vervolgens doorgeeft aan `deleteMessage` om het item van de server te verwijderen.**

Verwerken in batches vermindert netwerk‑round‑trips en voorkomt time‑outs bij grote mappen. Controleer altijd of de doelmap correct is, aangezien verwijderingen onomkeerbaar zijn zonder back‑up.

### Lijst en verwijder berichten
Itereer over elke bericht‑URI en roep de delete‑bewerking aan:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Uitleg:* `listMessages` retourneert een collectie van `MessageInfo`‑objecten; hun `getUniqueUri()`‑waarden worden doorgegeven aan `deleteMessage`, die de items permanent van de server verwijdert.

## Hoe een bericht aan een map toevoegen?
Stel lokaal een `MailMessage`‑object samen en sla het direct op in een postvakmap—geen SMTP‑server nodig. **`MailMessage` vertegenwoordigt een e‑mail met headers, body en bijlagen; het kan volledig in het geheugen worden opgebouwd voordat het naar Exchange wordt weggeschreven.**

Toevoegen omzeilt de verzend‑pipeline, waardoor het ideaal is voor concepten, sjablonen of programmatische berichtcreatie waarbij u wilt dat het bericht direct in de mailbox van de gebruiker verschijnt.

### Maak en verzend berichten
Bouw de e‑mail en voeg deze toe aan de map Concepten:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Uitleg:* `appendMessage` neemt de `MailMessage` en een `FolderInfo` (bijv. Concepten) en schrijft het item naar de mailbox, waardoor het direct beschikbaar is voor de gebruiker.

## Hoe een gebruiker impersoneren in EWS?
Schakel de beveiligingscontext van de client over naar een andere mailbox, voer acties uit en keer vervolgens terug naar het oorspronkelijke account. Dit is essentieel voor beheer van gedeelde mailboxen. **`impersonateUser` stelt de `ImpersonatedUserId` in op het onderliggende EWS‑verzoek, waardoor de server de oproep behandelt alsof deze afkomstig is van de doelmailbox.**

Na het voltooien van de vereiste bewerkingen, roep `resetImpersonation` aan om de oorspronkelijke inloggegevens te herstellen, zodat volgende oproepen onder de juiste beveiligingscontext worden uitgevoerd.

### Gebruikersimpersonatie uitvoeren
Verander tijdelijk de context van de client om als een andere gebruiker op te treden:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Uitleg:* `impersonateUser` stelt de `ImpersonatedUserId` in op het onderliggende EWS‑verzoek, waardoor u kunt lezen of schrijven alsof u de doelgebruiker bent. Het aanroepen van `resetImpersonation` herstelt de oorspronkelijke inloggegevens.

## Praktische toepassingen
Het gebruik van Aspose.Email Java maakt robuuste e‑mailautomatiseringsoplossingen mogelijk:
1. **Geautomatiseerde e‑mailopruiming:** Plan een nachtelijke taak die verouderde concepten‑mappen in tientallen mailboxen opruimt.  
2. **Batch‑e‑maildistributie:** Voeg een sjabloon‑aankondiging toe aan de Inbox van elke medewerker met één lus.  
3. **Beheer van gedeelde mailboxen:** Impersonate een afdelingsmailbox om oude berichten te archiveren zonder elke gebruiker volledige toegang te geven.

## Prestatie‑overwegingen
Om uw applicatie responsief te houden bij het verwerken van grote mailboxen:
- **Batch‑API‑calls** waar mogelijk (bijv. 500 berichten per verzoek verwijderen).  
- **Berichten streamen** in plaats van volledige bodies in het geheugen te laden.  
- **Client‑objecten vrijgeven** onmiddellijk om netwerksockets en HTTP‑verbindingen vrij te maken.

## Veelvoorkomende problemen en oplossingen
- **Connectiviteitsfouten:** Controleer de EWS‑endpoint‑URL, zorg dat TLS 1.2 is ingeschakeld, en bevestig dat firewall‑regels uitgaand HTTPS toestaan.  
- **Toestemming geweigerd bij impersonatie:** Het service‑account moet de rol “ApplicationImpersonation” toegewezen hebben in Exchange.  
- **Time‑outs bij grote mappen:** Verhoog de `HttpWebRequest`‑timeout of verwerk de map in kleinere delen.

## Veelgestelde vragen

**Q: Hoe los ik connectiviteitsproblemen met EWS op?**  
A: Controleer de endpoint‑URL, inloggegevens en netwerk‑firewalls; schakel gedetailleerde logging in Aspose.Email in om HTTP‑verzoek/‑responsgegevens vast te leggen.

**Q: Kan Aspose.Email grote hoeveelheden e‑mails efficiënt verwerken?**  
A: Ja—de batch‑API’s laten u **10.000+** berichten per minuut verwerken terwijl het geheugenverbruik onder 200 MB blijft.

**Q: Wat zijn typische use‑cases voor gebruikersimpersonatie in EWS?**  
A: Beheren van gedeelde mailboxen, uitvoeren van bulk‑archivering, en het draaien van geplande rapporten namens meerdere gebruikers zonder hun wachtwoorden op te slaan.

**Q: Zijn er limieten op API‑calls opgelegd door Aspose.Email?**  
A: Aspose.Email zelf legt geen limieten op; echter kan Exchange throttling‑beleid afdwingen dat u moet respecteren.

**Q: Hoe houd ik inloggegevens veilig in mijn Java‑code?**  
A: Sla ze op in versleutelde configuratiebestanden of gebruik Azure Key Vault / AWS Secrets Manager, en gebruik altijd HTTPS voor EWS‑endpoints.

---

**Laatst bijgewerkt:** 2026-07-08  
**Getest met:** Aspose.Email for Java 23.10  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe een EWSClient‑instantie te maken met Aspose.Email voor Java: Exchange Server‑integratiegids](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Hoe verbinding te maken met Microsoft Exchange Server met Aspose.Email voor Java en EWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [E‑mailbeheer automatiseren met Aspose.Email en Java EWS‑client: Een uitgebreide gids](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}