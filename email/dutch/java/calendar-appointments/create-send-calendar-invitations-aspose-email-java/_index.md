---
date: '2026-09-17'
description: Hoe een agenda-uitnodiging te maken met Aspose.Email voor Java stelt
  je in staat om agenda's te delen, delegatiepermissies in te stellen en deel-e-mails
  programmatisch te verzenden.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Hoe een agenda-uitnodiging te maken met Aspose.Email voor Java stelt
  je in staat om programmatisch agenda's te delen, delegatiepermissies in te stellen
  en deel-e-mails via Exchange Web Services te verzenden, waardoor de samenwerking
  in het team verbetert.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Hoe een agenda-uitnodiging te maken met Aspose.Email voor Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Hoe een agenda-uitnodiging te maken met Aspose.Email voor Java
url: /nl/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer het delen van agenda's: Aspose.Email voor Java gids

## Introductie tot het beheren van agenda-delen
Het beheren van uitnodigingen voor het delen van agenda's kan een complexe taak zijn, vooral wanneer je met meerdere gebruikers op verschillende platforms werkt. In deze tutorial zul je **een agenda‑deeluitnodiging maken** met Aspose.Email voor Java, waarbij alles wordt behandeld van het creëren van gedelegeerde toegang tot het verzenden van agenda‑deel‑e‑mails. Aan het einde kun je gedelegeerde rechten instellen, **agenda‑rechten configureren**, en de samenwerking in je organisatie stroomlijnen.

**Wat je zult leren**
- Hoe je de EWS‑client initialiseert met Aspose.Email voor Java  
- Een gedelegeerde gebruiker aanmaken en **gedelegeerde rechten instellen**  
- **Gedelegeerde toegang maken** en agenda‑rechten configureren  
- Programma­matig een **agenda‑deel‑e‑mail** (uitnodiging) verzenden  
- Praktische scenario's waarin deze functies waarde toevoegen  

Voordat we beginnen, laten we ervoor zorgen dat je alles hebt wat je nodig hebt.

## Snelle antwoorden
- **Wat is het primaire doel van deze gids?** Om te laten zien hoe je een **agenda‑deeluitnodiging maakt** met Aspose.Email voor Java.  
- **Welke bibliotheekversie is vereist?** Aspose.Email voor Java 25.4 (JDK 16 classifier).  
- **Heb ik een licentie nodig?** Ja – een proef‑ of volledige licentie is vereist voor productiegebruik.  
- **Welke omgeving is nodig?** JDK 16+, Maven en een Exchange Online‑account.  
- **Kan ik dit gebruiken met andere Exchange‑servers?** Ja, maar je moet mogelijk de service‑URL en rechtenniveaus aanpassen.

## Wat is een agenda‑deeluitnodiging?
Een agenda‑deeluitnodiging is een e‑mailbericht dat een andere gebruiker toegang geeft om je agenda te bekijken (of te bewerken) zonder volledige mailbox‑rechten te verlenen. Het stelt teamleden in staat je planning te zien, vergaderingen voor te stellen of evenementen te beheren, terwijl je mailbox veilig blijft.

## Waarom agenda‑rechten configureren?
Het configureren van agenda‑rechten stelt je in staat precies te bepalen wat een gedelegeerde mag doen — of ze alleen gebeurtenissen kunnen lezen, nieuwe kunnen voorstellen, of bestaande items kunnen bewerken. Juiste rechteninstellingen beschermen gevoelige informatie terwijl effectieve samenwerking mogelijk wordt gemaakt. Bijvoorbeeld, alleen‑lezen toegang voorkomt per ongeluk wijzigingen, terwijl bewerkingsrechten de gedelegeerde toestaan vergaderingen te plannen of aan te passen namens jou.

## Vereisten
- **Java Development Kit (JDK):** Versie 16 of hoger.  
- **Maven:** Voor afhankelijkheidsbeheer en het bouwen van het project.  
- **Aspose.Email for Java Library:** Versie 25.4 met JDK 16‑ondersteuning.  

### Vereisten voor omgeving configuratie
1. Installeer JDK als je dat nog niet hebt gedaan. Je kunt het downloaden van [Oracle's officiële site](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. Zorg ervoor dat Maven geïnstalleerd en geconfigureerd is op je machine.  
3. Kies een IDE zoals IntelliJ IDEA of Eclipse voor gemakkelijker ontwikkelen.

### Kennisvereisten
- Basis Java‑programmeervaardigheden  
- Bekendheid met Maven‑afhankelijkheden  
- Optioneel: Ervaring met Exchange Web Services (EWS)

## Aspose.Email voor Java instellen
### Maven‑configuratie
Voeg de volgende afhankelijkheid toe aan je `pom.xml`‑bestand:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑verwerving
Aspose.Email voor Java vereist een licentie voor volledige functionaliteit. Je kunt:
- **Gratis proefversie:** Download van [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Tijdelijke licentie:** Vraag een tijdelijke sleutel aan op de Aspose‑website.  
- **Aankoop:** Verkrijg een permanente licentie voor productie‑implementaties.

### Basisinitialisatie en configuratie
Zodra Maven de afhankelijkheid heeft opgelost, initialiseert u de EWS‑client:

`ExchangeService` is de primaire klasse die wordt gebruikt om te communiceren met Exchange Web Services.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Hoe een agenda‑deeluitnodiging te maken
In deze tutorial verbinden we eerst met Exchange via de `ExchangeService`‑client, definiëren we een gedelegeerde met het gewenste rechten‑niveau, en stellen vervolgens een `MailMessage` samen die het deelverzoek bevat. De volgende stappen demonstreren deze workflow in Java.

Hieronder behandelen we twee kernfuncties: het maken en verzenden van een agenda‑deeluitnodiging, en **gedelegeerde rechten instellen** voor agenda‑toegang.

### Functie 1: agenda‑deeluitnodiging maken en verzenden
#### Overzicht
Deze functie leidt je door het initialiseren van de client, **gedelegeerde toegang maken**, en het verzenden van de uitnodigings‑e‑mail.

#### Stapsgewijze implementatie
##### 1️⃣ Initialiseert EWS‑client
`ExchangeService` vertegenwoordigt de verbinding met een Exchange‑server en wordt gebruikt om berichten te verzenden en ontvangen.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Dit verbindt je Java‑app met Exchange Online.

##### 2️⃣ Maak gedelegeerde gebruiker
`DelegateUser` definieert het e‑mailadres van de gedelegeerde en het toe te kennen rechten‑niveau.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Hier **maken we gedelegeerde toegang** en wijzen we het `Reviewer`‑niveau toe, waarmee de gedelegeerde agenda‑items kan bekijken.

##### 3️⃣ Verstuur agenda‑deeluitnodiging
`MailMessage` bouwt de e‑mail die de agenda‑deeluitnodiging bevat.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
De code bouwt een **agenda‑deel‑e‑mail** (uitnodiging) en verzendt deze via de EWS‑client.

### Functie 2: gedelegeerde agenda‑toegang rechten
#### Overzicht
Deze sectie laat zien hoe je **agenda‑rechten configureren** en ervoor zorgen dat de gedelegeerde de juiste rechten heeft.

#### Implementatiestappen
##### 1️⃣ Initialiseert EWS‑client (hergebruik)
`ExchangeService` kan na de initiële configuratie worden hergebruikt voor meerdere bewerkingen.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Maak en stel gedelegeerde rechten in
`ExchangeDelegateFolderPermissionLevel` somt de toegangs­niveaus op die een gedelegeerde kan hebben tot een agenda‑map.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Dit fragment **stelt gedelegeerde rechten in** zodat de gebruiker agenda‑items kan bekijken zonder volledige mailbox‑toegang.

## Hoe agenda‑rechten voor gedelegeerden te configureren
Wanneer een gedelegeerde meer dan alleen‑lezen toegang nodig heeft, kun je het `ExchangeDelegateFolderPermissionLevel` aanpassen om bewerkings‑, auteur‑ of eigenaarsrechten toe te kennen. Kies het minimale niveau dat voldoet aan de zakelijke behoefte om de beveiliging te behouden terwijl je de benodigde functionaliteit biedt. Bijvoorbeeld, het toekennen van het Editor‑niveau stelt de gedelegeerde in staat om gebeurtenissen te creëren, te wijzigen en te verwijderen, terwijl het Reviewer‑niveau alleen bekijken toestaat.

- `Reviewer` – alleen‑lezen toegang.  
- `Editor` – lezen/schrijven toegang.  
- `Author` – maken en lezen, maar niet verwijderen.  
- `Owner` – volledige controle, inclusief wijziging van rechten.  

**Pro tip:** Gebruik het minst‑privilege niveau dat voldoet aan de zakelijke vereiste om je agenda‑gegevens veilig te houden.

## Praktische toepassingen
Reële scenario's waarin **agenda‑delen beheren** uitblinkt:
1. **Bedrijfsvergaderingen** – Laat teamleden vergaderschema's bekijken zonder volledige mailbox‑rechten te geven.  
2. **Projectmanagement** – Projectleiders kunnen tijdlijnen monitoren terwijl ontwikkelaars controle over hun eigen agenda's behouden.  
3. **Evenementplanning** – Leveranciers ontvangen een **agenda‑deel‑e‑mail** om logistiek te coördineren zonder interne details bloot te stellen.

## Prestatie‑overwegingen
- **Geheugenbeheer:** Verwijder grote `MailMessage`‑objecten tijdig in apps met hoog volume.  
- **Foutafhandeling:** Plaats netwerk‑aanroepen in try‑catch‑blokken om verbindingsproblemen elegant af te handelen.  
- **Bibliotheek‑updates:** Aspose.Email voor Java ondersteunt meer dan 50 protocollen en kan agenda's verwerken met tot 10.000 items zonder het volledige bestand in het geheugen te laden, dus houd de bibliotheek up‑to‑date om te profiteren van prestatie‑verbeteringen en bug‑fixes.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Uitnodiging niet ontvangen | Spamfilters of onjuist e‑mailadres | Controleer het e‑mailadres van de ontvanger en voeg het verzendende domein toe aan de lijst met veilige afzenders |
| Rechten niet toegepast | Verkeerd `ExchangeDelegateFolderPermissionLevel` gebruikt | Controleer of het rechten‑niveau overeenkomt met de vereiste toegang |
| Runtime‑exception op `createCalendarSharingInvitationMessage` | Ontbrekende licentie of verouderde bibliotheek | Zorg dat een geldige licentie is geladen en dat je de nieuwste Aspose.Email‑versie gebruikt |

## Veelgestelde vragen
**V: Waar wordt Aspose.Email voor Java voor gebruikt?**  
A: Het is een uitgebreide bibliotheek voor het verwerken van e‑mails, agenda's en contactpersonen in Java‑applicaties, met ondersteuning voor Outlook, Exchange en andere protocollen.

**V: Hoe stel ik mijn omgeving in voor het gebruik van Aspose.Email?**  
A: Installeer JDK 16+, Maven, voeg de Aspose.Email‑afhankelijkheid toe aan `pom.xml`, en verkrijg een licentie (proef of volledig).

**V: Kan ik deze code gebruiken met andere versies van Exchange Online?**  
A: Ja, maar controleer of de service‑URL en rechtenniveaus overeenkomen met de configuratie van jouw server.

**V: Wat moet ik doen als de agenda‑deeluitnodiging niet verzonden wordt?**  
A: Controleer de netwerkverbinding, inloggegevens en of de gedelegeerde gebruiker geldige rechten heeft. Bekijk de details van de uitzondering voor aanwijzingen.

**V: Is het mogelijk om extra rechten toe te voegen, zoals bewerken of volledige toegang?**  
A: Absoluut – vervang `ExchangeDelegateFolderPermissionLevel.Reviewer` door `Editor`, `Author` of `Owner` naar behoefte.

## Conclusie
Je hebt nu een volledige end‑to‑end‑oplossing voor **een agenda‑deeluitnodiging maken** met Aspose.Email voor Java. Door de EWS‑client te initialiseren, **gedelegeerde toegang maken**, **gedelegeerde rechten instellen**, en een **agenda‑deel‑e‑mail** te verzenden, kun je samenwerking in je organisatie automatiseren.

**Volgende stappen**
- Experimenteer met andere rechten‑niveaus (Editor, Owner).  
- Integreer deze logica in je bestaande plannings‑ of HR‑systemen.  
- Ontdek extra Aspose.Email‑functies zoals terugkerende gebeurtenissen of vergaderverzoeken.

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Gerelateerde tutorials

- [Hoe maak je een agenda‑item Java met Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java filter Exchange-afspraken op datum](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Maak Exchange‑agenda Java met Aspose.Email – Een volledige gids](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}