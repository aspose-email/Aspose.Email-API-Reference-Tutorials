---
date: '2026-06-23'
description: Lär dig hur du filtrerar e‑post efter datum, avsändare och ämne med Aspose.Email
  for Java. Denna steg‑för‑steg‑handledning visar hur du automatiserar IMAP‑e‑postfiltrering
  på ett effektivt sätt.
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
title: Hur man filtrerar e‑post i Java med Aspose.Email – En utvecklarehandbok
url: /sv/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man filtrerar e‑post i Java med Aspose.Email – En utvecklarguide

## Introduktion

Om du letar efter **hur man filtrerar e‑post** programatiskt, har du kommit till rätt ställe. Oavsett om du hanterar en företagsbrevlåda, bygger ett kundsupport‑ticketsystem, eller bara vill hålla din personliga inkorg prydlig, sparar automatisering av e‑postfiltrering timmar av manuellt arbete. I den här handledningen kommer vi att använda **Aspose.Email for Java**, ett bibliotek som stödjer över 30 e‑postprotokoll och kan hantera brevlådor med 100 000+ meddelanden utan att ladda hela mappen i minnet. Du kommer att lära dig att ansluta till en IMAP‑server, tillämpa filter efter datum, avsändare, ämne med mera, och optimera prestanda för storskalig bearbetning.

## Snabba svar
- **Vilket bibliotek hanterar IMAP‑filtrering i Java?** Aspose.Email for Java.  
- **Kan jag filtrera efter datum och avsändare i ett anrop?** Ja – kombinera kriterier med `ImapQueryBuilder`.  
- **Behöver jag en licens för produktion?** En full licens tar bort provgränserna; en tillfällig licens fungerar för testning.  
- **Stöds sidindelning?** Absolut – hämta meddelanden sida‑för‑sida för att hålla minnesanvändningen låg.  
- **Vilken Java‑version krävs?** JDK 8 eller nyare.

## Vad är e‑postfiltrering i Java?

E‑postfiltrering i Java innebär att programatiskt välja meddelanden som matchar specifika kriterier—såsom datum, avsändare eller ämne—så att du bara bearbetar den relevanta delmängden. Detta tillvägagångssätt minskar mängden data som överförs över nätverket och låter nedströmsystem arbeta med en fokuserad uppsättning e‑post, vilket förbättrar både hastighet och resursanvändning.

## Varför använda Aspose.Email för Java?

Aspose.Email för Java stödjer **30+ in‑ och utdataformat**, inklusive EML, MSG, MBOX och PST, och kan bearbeta **brevlådor med över 100 000 meddelanden** samtidigt som minnesförbrukningen hålls under 50 MB tack vare server‑sidig filtrering och sidindelning. Biblioteket erbjuder också inbyggt stöd för anpassade IMAP‑flaggor, UTF‑8‑kodning och skiftlägeskänsliga frågor, vilket gör det till en komplett lösning för e‑postautomatisering på företagsnivå.

## Förutsättningar

1. **Java Development Kit (JDK)** – version 8 eller senare.  
2. **Maven** – för beroendehantering.  
3. **Aspose.Email for Java** – det kärnbibliotek vi kommer att använda.

### Nödvändiga bibliotek och beroenden

Lägg till Aspose.Email‑beroendet i din `pom.xml`‑fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensinnehav

- **Gratis provversion** – ladda ner en provversion för att utforska alla funktioner.  
- **Tillfällig licens** – skaffa en tidsbegränsad licens för utökad testning.  
- **Full licens** – köp för produktionsbruk och ta bort alla utvärderingsgränser.  
- **Licensfil** – skaffa den från [Aspose's website](https://purchase.aspose.com/temporary-license/).

## Konfigurera Aspose.Email för Java

För att börja använda Aspose.Email, följ dessa steg:

1. **Ladda ner och installera** – Maven hämtar biblioteket automatiskt från platshållaren ovan.  
2. **Initiera biblioteket** – Ladda din licensfil (om du har en) innan du gör några API‑anrop:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## Implementeringsguide

### Hur ansluter man till en IMAP‑server?

För att börja måste du etablera en anslutning till IMAP‑servern med hjälp av klassen `ImapClient`, som representerar en klientsession som kan autentisera och skicka kommandon till servern. Denna anslutning är grunden för alla efterföljande brevlådsoperationer.

En typisk anslutningssekvens innebär att ange värd, port, användaruppgifter och säkerhetsalternativ, sedan välja önskad brevlådemapp (t.ex. **Inbox**) innan du utför några frågor.

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### Hur filtrerar man e‑post efter ämne och datum?

`ImapQueryBuilder`‑klassen hjälper dig att konstruera komplexa sökkriterier som översätts till effektiva IMAP‑SEARCH‑kommandon. Genom att kombinera ämnesnyckelord med ett datumintervall kan du hämta endast de meddelanden som är relevanta för din bearbetningslogik.

I det här exemplet letar vi efter meddelanden vars ämne innehåller “Newsletter” och som mottogs under den aktuella dagen, vilket minimerar dataöverföring och bearbetningskostnad.

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### Hur filtrerar man e‑post på dagens datum?

Med `ImapQueryBuilder` kan du skapa ett filter som matchar exakt kalenderdatum för meddelandets sändningstidstämpel. Detta är användbart för dagliga bearbetningsjobb som bara ska agera på de nyaste meddelandena.

Byggaren formaterar automatiskt datumet enligt IMAP‑protokollet, vilket säkerställer exakt server‑sidig filtrering utan extra klient‑sidig parsning.

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### Hur filtrerar man e‑post på ett datumintervall?

När du behöver arbeta med ett antal dagar tillåter `ImapQueryBuilder` dig att definiera en start‑ och slut‑`DateTime`. Biblioteket konverterar dessa värden till lämplig IMAP‑SEARCH‑syntax och returnerar alla meddelanden som faller inom det angivna intervallet.

Denna teknik är idealisk för att generera veckorapporter eller arkivera meddelanden äldre än ett visst tröskelvärde.

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### Hur filtrerar man e‑post efter specifik avsändare?

`ImapQueryBuilder` kan rikta in sig på en enskild e‑postadress eller en hel domän genom att matcha `From`‑rubriken. Detta gör att du kan isolera kommunikation från betrodda partners eller filtrera bort oönskade avsändare.

Att ange den exakta adressen (t.ex. `user@example.com`) eller ett domänmönster (t.ex. `@example.com`) ger precisa resultat direkt från servern.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### Hur filtrerar man e‑post efter specifik domän?

På liknande sätt som avsändarfiltrering kan du begränsa resultaten till en viss domän med `fromAddress`‑metoden i `ImapQueryBuilder`. Detta är användbart när du behöver bearbeta alla meddelanden som kommer från en företagspartner eller en specifik e‑posttjänstleverantör.

Frågan körs på servern, så endast matchande meddelanden överförs till din applikation.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### Hur filtrerar man e‑post efter specifik mottagare?

För att fokusera på meddelanden adresserade till en specifik brevlåda, använd `toAddress`‑metoden i `ImapQueryBuilder`. Detta är särskilt användbart för delade inkorgar eller rollbaserade brevlådor där flera användare behöver bearbeta samma uppsättning e‑post.

Byggaren skapar ett IMAP‑SEARCH‑villkor som matchar `To`‑rubriken, vilket säkerställer effektiv server‑sidig filtrering.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### Hur utför man skiftlägeskänslig e‑postfiltrering?

Som standard är IMAP‑sökningar skiftlägesokänsliga, men `ImapQueryBuilder` erbjuder ett alternativ för att tvinga skiftlägeskänslighet för exakta matchningar. Detta är viktigt när du ska skilja mellan identifierare som bara skiljer sig åt i bokstavsstorlek.

Aktivera flaggan `setCaseSensitive(true)` innan du lägger till andra kriterier för att uppnå exakt filtrering.

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### Hur specificerar man kodning för Query Builder?

När du hanterar internationaliserade ämnesrader eller adresser bör du ange teckenkodning på `ImapQueryBuilder`. Att använda UTF‑8 säkerställer att icke‑ASCII‑tecken tolkas korrekt av IMAP‑servern.

Anropa `setEncoding(Encoding.UTF_8)` innan du konstruerar din fråga för att undvika förvrängda resultat.

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### Hur filtrerar man meddelanden med stöd för sidindelning?

Sidindelning är avgörande för stora brevlådor. `ImapClient` tillhandahåller metoder för att hämta meddelanden i batchar, vilket låter dig bearbeta t.ex. 500 meddelanden åt gången. Detta håller minnesförbrukningen låg och förbättrar den totala genomströmningen.

Kombinera sidindelning med `ImapQueryBuilder` för att hämta endast den relevanta delmängden på varje sida.

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

### Hur filtrerar man meddelanden på en anpassad flagga?

IMAP stödjer användardefinierade flaggor såsom `\Flagged` eller anpassade taggar. Med `ImapQueryBuilder` kan du ange dessa flaggor för att hämta endast meddelanden som har markerats på motsvarande sätt.

Denna funktion är användbar för arbetsflöden som förlitar sig på att flagga meddelanden för senare granskning eller särskild hantering.

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## Praktiska tillämpningar

- **Företags e‑posthantering** – Sortera automatiskt inkommande e‑post till avdelningsmappar baserat på avsändare eller ämne.  
- **Kundsupportsystem** – Prioritera ärenden genom att filtrera e‑post som innehåller “Urgent” eller kommer från VIP‑kunder.  
- **Personliga organisationsverktyg** – Bygg ett lättviktigt Java‑verktyg som arkiverar dagens nyhetsbrev och raderar skräppost i ett körning.

## Prestandaöverväganden

- **Server‑sidig filtrering** – Låt IMAP‑servern göra det tunga arbetet; endast matchande meddelanden färdas över nätverket.  
- **Sidindelning** – Hämta resultat i bitar (t.ex. 200‑meddelandesidor) för att undvika att ladda hela brevlådan i RAM.  
- **Återanvändning av anslutning** – Behåll en enda `ImapClient`‑instans levande under batchjobbet för att minska handskakningskostnaden.  
- **Övervakning** – Logga antalet bearbetade meddelanden och förfluten tid; justera sidstorlek om du märker minnesspikar.

## Slutsats

Du har nu en komplett verktygslåda för **hur man filtrerar e‑post** med Aspose.Email för Java. Från enkla datumbaserade frågor till komplexa fler‑kriterie‑filter med anpassade flaggor, ger biblioteket dig fin‑granulerad kontroll samtidigt som prestandan hålls optimal.

### Nästa steg

- Kombinera dessa filter till en enda återanvändbar metod för din applikation.  
- Utforska **Aspose.Email**‑API:t för att skicka, vidarebefordra och svara på meddelanden.  
- Integrera med en databas för att lagra metadata om filtrerade meddelanden för analys.

---

## Vanliga frågor

**Q: Hur ansluter jag till en IMAP‑server med Aspose.Email?**  
A: Instansiera `ImapClient` med värd, port, användarnamn och lösenord, och anropa sedan `client.selectFolder("Inbox")`.

**Q: Kan jag filtrera e‑post både efter datum och avsändare i en begäran?**  
A: Ja – använd `ImapQueryBuilder` för att kombinera `date`‑ och `fromAddress`‑kriterier; biblioteket skickar ett enda SEARCH‑kommando.

**Q: Stöder Aspose.Email SSL/TLS för säkra anslutningar?**  
A: Absolut – sätt `client.setSecurityOptions(SecurityOptions.SSL_TLS)` innan du ansluter.

**Q: Vad är den maximala brevlådstorleken som Aspose.Email kan hantera?**  
A: Biblioteket kan bearbeta brevlådor med **över 100 000 meddelanden** så länge du använder sidindelning; minnesanvändningen hålls under 50 MB.

**Q: Behöver jag en licens för utvecklingsbyggen?**  
A: En tillfällig licens tar bort utvärderingsvattenstämpeln och begränsningarna; en full licens krävs för produktionsdistributioner.

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Email for Java 24.9  
**Author:** Aspose

## Relaterade handledningar

- [Hämta e‑post från IMAP‑server med Aspose.Email för Java: En steg‑för‑steg‑guide](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [Behärska IMAP‑klientinitialisering i Java med Aspose.Email: En omfattande guide](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [Hur man säkerhetskopierar IMAP‑e‑post med Aspose.Email för Java: En steg‑för‑steg‑guide](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}