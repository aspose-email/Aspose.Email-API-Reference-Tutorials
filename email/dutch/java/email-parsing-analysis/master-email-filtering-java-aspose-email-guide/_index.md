---
date: '2026-06-23'
description: Leer hoe je e‑mails kunt filteren op datum, afzender en onderwerp met
  Aspose.Email voor Java. Deze stapsgewijze tutorial laat zien hoe je IMAP‑e‑mailfiltering
  efficiënt kunt automatiseren.
keywords:
- how to filter emails
- filter emails by date
- filter emails by sender
- filter emails by subject
- aspose email java tutorial
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  headline: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  type: TechArticle
- description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  name: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later.'
    text: '**Java Development Kit (JDK)** – version 8 or later.'
  - name: '**Maven** – for dependency management.'
    text: '**Maven** – for dependency management.'
  - name: '**Aspose.Email for Java** – the core library we’ll use.'
    text: '**Aspose.Email for Java** – the core library we’ll use.'
  - name: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
    text: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
  - name: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
    text: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
  type: HowTo
- questions:
  - answer: Instantiate `ImapClient` with host, port, username, and password, then
      call `client.selectFolder("Inbox")`.
    question: How do I connect to an IMAP server using Aspose.Email?
  - answer: Yes – use `ImapQueryBuilder` to combine `date` and `fromAddress` criteria;
      the library sends a single SEARCH command.
    question: Can I filter emails by both date and sender in one request?
  - answer: Absolutely – set `client.setSecurityOptions(SecurityOptions.SSL_TLS)`
      before connecting.
    question: Does Aspose.Email support SSL/TLS for secure connections?
  - answer: The library can process mailboxes with **over 100,000 messages** as long
      as you use paging; memory usage stays below 50 MB.
    question: What is the maximum mailbox size Aspose.Email can handle?
  - answer: A temporary license removes the evaluation watermark and limits; a full
      license is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
title: Hoe e‑mails filteren in Java met Aspose.Email – Een ontwikkelaarsgids
url: /nl/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe e‑mails filteren in Java met Aspose.Email – Een ontwikkelaarsgids

## Introductie

Als je **hoe e‑mails te filteren** programmatically zoekt, ben je hier op de juiste plek. Of je nu een bedrijfs‑mailbox beheert, een klanten‑ondersteunings‑ticketingsysteem bouwt, of gewoon je persoonlijke inbox netjes wilt houden, het automatiseren van e‑mailfiltering bespaart uren handmatig werk. In deze tutorial gebruiken we **Aspose.Email for Java**, een bibliotheek die meer dan 30 e‑mailprotocollen ondersteunt en mailboxes met 100.000+ berichten kan verwerken zonder de volledige map in het geheugen te laden. Je leert een verbinding maken met een IMAP‑server, filters toepassen op datum, afzender, onderwerp en meer, en de prestaties optimaliseren voor grootschalige verwerking.

## Snelle antwoorden
- **Welke bibliotheek behandelt IMAP-filtering in Java?** Aspose.Email for Java.  
- **Kan ik filteren op datum en afzender in één oproep?** Ja – combineer criteria met `ImapQueryBuilder`.  
- **Heb ik een licentie nodig voor productie?** Een volledige licentie verwijdert proeflimieten; een tijdelijke licentie werkt voor testen.  
- **Wordt paginering ondersteund?** Absoluut – haal berichten pagina voor pagina op om het geheugenverbruik laag te houden.  
- **Welke Java‑versie is vereist?** JDK 8 of nieuwer.

## Wat is e‑mailfiltering in Java?

E‑mailfiltering in Java betekent programmatically berichten selecteren die aan specifieke criteria voldoen — zoals datum, afzender of onderwerp — zodat je alleen de relevante subset verwerkt. Deze aanpak vermindert de hoeveelheid data die over het netwerk wordt overgedragen en stelt downstream‑systemen in staat met een gerichte set e‑mails te werken, waardoor zowel snelheid als resource‑gebruik verbeteren.

## Waarom Aspose.Email voor Java gebruiken?

Aspose.Email voor Java ondersteunt **30+ invoer‑ en uitvoerformaten**, waaronder EML, MSG, MBOX en PST, en kan **mailboxes met meer dan 100.000 berichten** verwerken terwijl het geheugenverbruik onder 50 MB blijft dankzij server‑side filtering en paginering. De bibliotheek biedt ook ingebouwde ondersteuning voor aangepaste IMAP‑flags, UTF‑8‑codering en case‑sensitive queries, waardoor het een alles‑in‑één oplossing is voor enterprise‑grade e‑mailautomatisering.

## Voorvereisten

1. **Java Development Kit (JDK)** – versie 8 of later.  
2. **Maven** – voor afhankelijkheidsbeheer.  
3. **Aspose.Email for Java** – de kernbibliotheek die we gaan gebruiken.

### Vereiste bibliotheken en afhankelijkheden

Voeg de Aspose.Email‑dependency toe aan je `pom.xml`‑bestand:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licentie‑acquisitie

- **Gratis proefversie** – download een proefversie om alle functies te verkennen.  
- **Tijdelijke licentie** – verkrijg een tijdsbeperkte licentie voor uitgebreid testen.  
- **Volledige licentie** – koop voor productiegebruik en verwijder alle evaluatielimieten.  
- **Licentiebestand** – verkrijg het van [Aspose's website](https://purchase.aspose.com/temporary-license/).

## Instellen van Aspose.Email voor Java

Om Aspose.Email te gaan gebruiken, volg je deze stappen:

1. **Downloaden en installeren** – Maven haalt de bibliotheek automatisch op vanuit de placeholder hierboven.  
2. **Bibliotheek initialiseren** – Laad uw licentiebestand (indien u er een heeft) voordat u API‑aanroepen doet:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## Implementatie‑gids

### Hoe maak je verbinding met een IMAP‑server?

Om te beginnen moet je een verbinding tot stand brengen met de IMAP‑server via de `ImapClient`‑klasse, die een client‑sessie vertegenwoordigt die kan authenticeren en commando's naar de server kan sturen. Deze verbinding vormt de basis voor alle verdere mailbox‑operaties.

Een typische verbindingsreeks omvat het specificeren van host, poort, gebruikersreferenties en beveiligingsopties, waarna je de gewenste mailbox‑map (bijv. **Inbox**) selecteert voordat je queries uitvoert.

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### Hoe e‑mails filteren op onderwerp en datum?

De `ImapQueryBuilder`‑klasse helpt je complexe zoekcriteria samen te stellen die worden vertaald naar efficiënte IMAP SEARCH‑commando's. Door onderwerp‑trefwoorden te combineren met een datumbereik kun je alleen de berichten ophalen die relevant zijn voor je verwerkingslogica.

In dit voorbeeld zoeken we naar berichten waarvan het onderwerp “Newsletter” bevat en die op de huidige dag zijn ontvangen, waardoor data‑overdracht en verwerkingsbelasting worden geminimaliseerd.

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### Hoe e‑mails filteren op de datum van vandaag?

Met `ImapQueryBuilder` kun je een filter maken dat exact overeenkomt met de kalenderdatum van de verzend‑timestamp van het bericht. Dit is handig voor dagelijkse verwerkingsjobs die alleen op de nieuwste berichten moeten reageren.

De builder formatteert de datum automatisch volgens het IMAP‑protocol, waardoor nauwkeurige server‑side filtering zonder extra client‑side parsing wordt gegarandeerd.

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### Hoe e‑mails filteren op een datumbereik?

Wanneer je met een reeks dagen moet werken, laat `ImapQueryBuilder` je een start‑ en eind‑`DateTime` definiëren. De bibliotheek zet deze waarden om in de juiste IMAP SEARCH‑syntaxis en retourneert alle berichten die binnen het opgegeven interval vallen.

Deze techniek is ideaal voor het genereren van wekelijkse rapporten of het archiveren van berichten ouder dan een bepaalde drempel.

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### Hoe e‑mails filteren op specifieke afzender?

De `ImapQueryBuilder` kan een enkel e‑mailadres of een heel domein targeten door de `From`‑header te matchen. Dit stelt je in staat communicatie van vertrouwde partners te isoleren of ongewenste afzenders te filteren.

Het opgeven van het exacte adres (bijv. `user@example.com`) of een domeinpatroon (bijv. `@example.com`) levert precieze resultaten direct van de server op.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### Hoe e‑mails filteren op specifiek domein?

Net als bij afzenderfiltering kun je resultaten beperken tot een bepaald domein met de `fromAddress`‑methode van `ImapQueryBuilder`. Dit is nuttig wanneer je alle berichten van een zakelijke partner of een specifieke e‑mailserviceprovider moet verwerken.

De query wordt op de server uitgevoerd, zodat alleen overeenkomende berichten naar je applicatie worden verzonden.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### Hoe e‑mails filteren op specifieke ontvanger?

Om je te richten op berichten die aan een bepaalde mailbox zijn geadresseerd, gebruik je de `toAddress`‑methode van `ImapQueryBuilder`. Dit is vooral handig voor gedeelde inboxen of rol‑gebaseerde mailboxes waar meerdere gebruikers dezelfde set e‑mails moeten verwerken.

De builder maakt een IMAP SEARCH‑clausule die de `To`‑header matcht, waardoor efficiënte server‑side filtering wordt gegarandeerd.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### Hoe case‑gevoelige e‑mailfiltering uitvoeren?

Standaard zijn IMAP‑searches case‑insensitive, maar `ImapQueryBuilder` biedt een optie om case‑sensitivity af te dwingen voor exacte matches. Dit is belangrijk wanneer je identifiers moet onderscheiden die alleen qua hoofdletter verschillen.

Schakel de `setCaseSensitive(true)`‑vlag in voordat je andere criteria toevoegt om precieze filtering te bereiken.

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### Hoe de codering voor de Query Builder specificeren?

Bij het omgaan met internationaal getitelde onderwerpregels of adressen moet je de tekencodering op de `ImapQueryBuilder` instellen. Het gebruik van UTF‑8 zorgt ervoor dat niet‑ASCII‑tekens correct door de IMAP‑server worden geïnterpreteerd.

Roep `setEncoding(Encoding.UTF_8)` aan voordat je je query opbouwt om vervormde resultaten te vermijden.

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### Hoe berichten filteren met pagineringsondersteuning?

Paginering is essentieel voor grote mailboxes. De `ImapClient` biedt methoden om berichten in batches op te halen, zodat je bijvoorbeeld 500 berichten per keer kunt verwerken. Dit houdt het geheugenverbruik laag en verbetert de algehele doorvoersnelheid.

Combineer paginering met `ImapQueryBuilder` om alleen de relevante subset per pagina op te halen.

```java
ImapClient client = new ImapClient(host, port, username, password);
client.setSecurityOptions(SecurityOptions.Auto);

int itemsPerPage = 5;
String searchBody = "example body text";

ImapQueryBuilder iqb = new ImapQueryBuilder();
iqb.getBody().contains(searchBody);
MailQuery query = iqb.getQuery();

PageSettings pageSettings = new PageSettings();
pageSettings.setFolderName("Inbox");

List<ImapPageInfo> pages = new ArrayList<>();
ImapPageInfo pageInfo = client.listMessagesByPage(query, new PageInfo(itemsPerPage, 0), pageSettings);

pages.add(pageInfo);
while (!pageInfo.getLastPage()) {
    pageInfo = client.listMessagesByPage(query, pageInfo.getNextPage(), pageSettings);
    pages.add(pageInfo);
}

int retrievedItems = 0;
for (ImapPageInfo folderCol : pages) {
    retrievedItems += folderCol.getItems().size();
}
client.dispose();
```

### Hoe berichten filteren op een aangepaste vlag?

IMAP ondersteunt door de gebruiker gedefinieerde flags zoals `\Flagged` of aangepaste tags. Met `ImapQueryBuilder` kun je deze flags specificeren om alleen berichten op te halen die overeenkomstig gemarkeerd zijn.

Deze mogelijkheid is nuttig voor workflows die afhankelijk zijn van het markeren van berichten voor latere beoordeling of speciale verwerking.

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## Praktische toepassingen

- **Beheer van bedrijfs‑e‑mail** – Sorteer binnenkomende mail automatisch in afdelingsmappen op basis van afzender of onderwerp.  
- **Klantenondersteuningssystemen** – Prioriteer tickets door e‑mails te filteren die “Urgent” bevatten of van VIP‑klanten komen.  
- **Persoonlijke organisatietools** – Bouw een lichte Java‑utility die de nieuwsbrieven van vandaag archiveert en spam in één keer verwijdert.

## Prestatiesoverwegingen

- **Server‑side filtering** – Laat de IMAP‑server het zware werk doen; alleen overeenkomende berichten reizen over het netwerk.  
- **Paginering** – Haal resultaten op in delen (bijv. pagina’s van 200 berichten) om te voorkomen dat de volledige mailbox in RAM wordt geladen.  
- **Herbruik van verbinding** – Houd één `ImapClient`‑instantie actief gedurende de batchtaak om handshaking‑overhead te verminderen.  
- **Monitoring** – Log het aantal verwerkte berichten en de verstreken tijd; pas de paginagrootte aan als u geheugenpieken opmerkt.

## Conclusie

Je beschikt nu over een complete toolbox voor **hoe e‑mails te filteren** met Aspose.Email voor Java. Van eenvoudige datum‑gebaseerde queries tot complexe multi‑criteria filters met aangepaste flags, de bibliotheek biedt fijnmazige controle terwijl de prestaties optimaal blijven.

### Volgende stappen

- Combineer deze filters in één herbruikbare methode voor uw applicatie.  
- Verken de **Aspose.Email**‑API voor het verzenden, doorsturen en beantwoorden van berichten.  
- Integreer met een database om metadata van gefilterde berichten op te slaan voor analyses.

---

## Veelgestelde vragen

**Q: Hoe maak ik verbinding met een IMAP‑server met Aspose.Email?**  
A: Instantieer `ImapClient` met host, poort, gebruikersnaam en wachtwoord, roep vervolgens `client.selectFolder("Inbox")` aan.

**Q: Kan ik e‑mails filteren op zowel datum als afzender in één verzoek?**  
A: Ja – gebruik `ImapQueryBuilder` om `date`‑ en `fromAddress`‑criteria te combineren; de bibliotheek stuurt één SEARCH‑commando.

**Q: Ondersteunt Aspose.Email SSL/TLS voor veilige verbindingen?**  
A: Absoluut – stel `client.setSecurityOptions(SecurityOptions.SSL_TLS)` in vóór het verbinden.

**Q: Wat is de maximale mailboxgrootte die Aspose.Email aankan?**  
A: De bibliotheek kan mailboxes met **meer dan 100.000 berichten** verwerken zolang je paginering gebruikt; het geheugenverbruik blijft onder 50 MB.

**Q: Heb ik een licentie nodig voor ontwikkel‑builds?**  
A: Een tijdelijke licentie verwijdert het evaluatiewatermerk en de limieten; een volledige licentie is vereist voor productie‑implementaties.

---

**Laatst bijgewerkt:** 2026-06-23  
**Getest met:** Aspose.Email for Java 24.9  
**Auteur:** Aspose

## Gerelateerde tutorials

- [E‑mails ophalen van IMAP‑server met Aspose.Email voor Java: Een stapsgewijze handleiding](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [IMAP‑clientinitialisatie in Java met Aspose.Email beheersen: Een uitgebreide gids](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [Hoe IMAP‑e‑mails te back‑uppen met Aspose.Email voor Java: Een stapsgewijze handleiding](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}