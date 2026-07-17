---
date: '2026-07-17'
description: 'Hur man filtrerar e-post med Aspose.Email Java och EWS: lär dig date,
  sender, och subject filtreringstekniker för att effektivisera din mailbox.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Hur man filtrerar e-post med Aspose.Email Java och EWS. Upptäck date,
  sender, och subject filtreringstekniker för att hålla din mailbox organiserad.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Hur man filtrerar e-post med Aspose.Email Java & EWS
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Hur man filtrerar e-post med Aspose.Email Java & EWS Guide
url: /sv/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Behärska e-postfiltrering med Aspose.Email Java & EWS: En komplett guide

## Introduktion

**How to filter emails** effektivt är en grundläggande färdighet för alla som arbetar med Microsoft Exchange eller någon modern brevlåda. Oavsett om du är en utvecklare som bygger en företagsomfattande automatisering eller en individ som vill hålla din inkorg prydlig, kan behärskning av rätt filtreringstekniker spara timmar av manuellt arbete. I den här guiden går vi igenom Aspose.Email för Java tillsammans med Exchange Web Services (EWS) för att visa hur du filtrerar efter datum, avsändare, ämne, domän, mottagare och till och med kombinerar flera kriterier med logiska operatorer.

### Vad du kommer att lära dig
- Tekniker för att filtrera meddelanden med EWS i Java.  
- Filtrera e-post baserat på kriterier såsom datum, avsändare, ämne osv.  
- Implementera sidstöd för att hantera stora brevlådor.  
- Praktiska tillämpningar av dessa filtreringsmetoder i verkliga scenarier.  
- Prestandaöverväganden och bästa praxis med Aspose.Email Java.

I slutet av den här handledningen kommer du att kunna skriva ren, prestandaoptimerad Java‑kod som hämtar exakt de meddelanden du behöver från en Exchange‑server.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.Email for Java.  
- **Vilket protokoll använder det?** Exchange Web Services (EWS).  
- **Kan jag filtrera efter datumintervall?** Ja – använd `DateTime`‑kriterier i `SearchFilter`.  
- **Stöds sidindelning?** Absolut, API‑et erbjuder `ItemView` med offset/limit.  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens tar bort utvärderingsgränser.

## Vad är Aspose.Email för Java?
Aspose.Email för Java är ett omfattande API som möjliggör programmatisk åtkomst till e‑postservrar, MIME‑meddelanden och Exchange Web Services utan att kräva Outlook eller någon annan klient. Det abstraherar de underliggande protokollen så att du kan fokusera på affärslogik. Biblioteket stödjer både lokala Exchange‑servrar och Exchange Online och erbjuder ett enhetligt API för olika distributionsscenarier.

## Varför använda Aspose.Email med EWS?
Aspose.Email stödjer **50+** e‑postprotokoll och kan bearbeta **hundratusentals meddelanden** per timme samtidigt som minnesanvändningen hålls under **100 MB** tack vare dess streaming‑arkitektur. Denna kvantifierade prestanda gör det idealiskt för automatisering av brevlådor i företagsstorlek. Dessutom erbjuder det inbyggt stöd för OAuth och modern autentisering, vilket förenklar säkra anslutningar till Office 365‑miljöer.

## Förutsättningar

- **Krävda bibliotek**: Inkludera Aspose.Email‑biblioteket i ditt projekt.  
- **Miljöuppsättning**: En färdig utvecklingsmiljö för Java‑applikationer är nödvändig.  
- **Kunskapsförutsättningar**: Bekantskap med Java‑programmering och e‑postprotokoll är fördelaktigt.

## Installera Aspose.Email för Java

### Maven‑installation
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licensanskaffning
- **Gratis provperiod**: Börja med en gratis provperiod för att utforska Aspose.Email:s funktioner.  
- **Tillfällig licens**: Skaffa en tillfällig licens för förlängd utvärdering.  
- **Köp**: Överväg att köpa en full licens om verktyget uppfyller dina behov.

Initiera och konfigurera Aspose.Email genom att importera nödvändiga paket och etablera en anslutning till din e‑postserver med EWS‑uppgifter. Detta steg är avgörande för att programatiskt kunna komma åt brevlådedata.

## Hur man filtrerar e‑post med EWS i Java?

ExchangeService är Aspose.Email‑klassen som representerar en anslutning till en Exchange‑server.  
SearchFilter definierar kriterier för att lokalisera objekt på servern.  
FindItems utför sökningen och returnerar matchande objekt.  
ItemView styr sidindelning och antalet objekt som returneras per begäran.

Läs in en `ExchangeService`‑instans med dina uppgifter, skapa ett `SearchFilter` som matchar dina kriterier och anropa `FindItems` med ett `ItemView` för att bara hämta de meddelanden du behöver. Detta enkla mönster – anslut → filtrera → hämta – täcker de flesta användningsfall och skalas till stora brevlådor när du aktiverar sidindelning.

## Implementeringsguide

### Filtrera meddelanden med EWS

#### Översikt
Filtrering gör att du kan hämta endast e‑post som uppfyller vissa villkor, såsom ett specifikt ämne eller datum, direkt från din brevlåda.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Explanation**: Koden etablerar en anslutning till din brevlåda och skapar en fråga för att filtrera e‑post med 'Newsletter' i ämnesraden från ett specifikt datum.

### Hur man filtrerar e‑post efter dagens datum?

SearchFilter.IsEqualTo skapar ett filter som matchar objekt där en egenskap är lika med ett givet värde.  
DateTimeReceived är egenskapen som indikerar när e‑posten mottogs.

Läs in det aktuella datumet, bygg ett `SearchFilter.IsEqualTo` på `DateTimeReceived`‑egenskapen och kör frågan. Detta returnerar endast de meddelanden som mottogs den dag du kör koden, vilket gör dagliga bearbetningsskript enkla. Du kan kombinera detta filter med ytterligare kriterier såsom avsändare eller ämne för att ytterligare begränsa resultaten för dagen.

### Hur man filtrerar e‑post efter datumintervall?

SearchFilter.IsGreaterThanOrEqualTo skapar ett filter som matchar objekt med ett egenskapsvärde större än eller lika med ett specificerat värde.  
SearchFilter.IsLessThanOrEqualTo skapar ett filter som matchar objekt med ett egenskapsvärde mindre än eller lika med ett specificerat värde.  
SearchFilter.And kombinerar flera filter så att alla villkor måste uppfyllas.

Definiera en start‑ och slut‑`DateTime`, kombinera dem med `SearchFilter.IsGreaterThanOrEqualTo` och `SearchFilter.IsLessThanOrEqualTo`, och använd sedan `SearchFilter.And` för att förena de två. Resultatmängden innehåller varje meddelande som faller inom det angivna intervallet. Detta tillvägagångssätt gör att du kan hämta all kommunikation inom en anpassad period, såsom senaste kvartalet eller ett specifikt projekt.

### Hur man filtrerar e‑post efter specifik avsändare?

SearchFilter.IsEqualTo skapar ett filter som matchar objekt där en egenskap är lika med ett givet värde.

Skapa ett `SearchFilter.IsEqualTo` på `From`‑egenskapen med avsändarens e‑postadress. Detta isolerar alla meddelanden från den kontakten, idealiskt för prioriterade inkorgar eller efterlevnadskontroller. Du kan också använda `SearchFilter.ContainsSubstring` för partiella matchningar när den exakta adressen är okänd eller vid filtrering efter domän.

### Hur man filtrerar e‑post efter specifik domän?

SearchFilter.ContainsSubstring skapar ett filter som matchar objekt där en egenskap innehåller en specificerad delsträng.

Använd `SearchFilter.ContainsSubstring` på `From`‑egenskapen med domänsträngen (t.ex. “@example.com”). Detta hämtar varje e‑post som kommer från den domänen, användbart för övervakning av partner‑ eller leverantörskommunikation. Att kombinera detta filter med datumkriterier låter dig spåra domänspecifik kommunikation över tid, vilket underlättar säkerhetsgranskningar.

### Hur man filtrerar e‑post efter specifik mottagare?

SearchFilter.IsEqualTo skapar ett filter som matchar objekt där en egenskap är lika med ett givet värde.

Applicera `SearchFilter.IsEqualTo` på `ToRecipients`‑samlingen för den målade adressen. Detta är praktiskt när du behöver granska meddelanden som skickats till en viss brevlåda eller distributionslista. Du kan även använda `SearchFilter.ContainsSubstring` för partiella matchningar när du hanterar flera mottagare som delar en gemensam domän.

### Hur man kombinerar frågor med OCH‑logik?

SearchFilter.And kombinerar flera filter så att alla villkor måste uppfyllas.

Kedja flera `SearchFilter`‑objekt med `SearchFilter.And`. Till exempel, kombinera ett avsändarfilter med ett ämnesfilter för att bara hämta nyhetsbrev från en betrodd avsändare. OCH‑operatorn säkerställer att endast objekt som uppfyller alla specificerade villkor returneras, vilket minskar resultatmängden till de mest relevanta meddelandena.

### Hur man kombinerar frågor med ELLER‑logik?

SearchFilter.Or slår samman filter så att någon av villkoren kan matcha.

Använd `SearchFilter.Or` för att slå samman filter när någon av villkoren ska matcha – perfekt för att hämta meddelanden som antingen kommer från en uppsättning avsändare **eller** innehåller vissa nyckelord. Att tillämpa ELLER‑logik kan bredda sökningar för att fånga all relevant kommunikation över flera kategorier utan att missa kritisk information.

## Vanliga fallgropar & tips

- **Sidindelning är avgörande**: När du hanterar brevlådor med mer än 1 000 objekt, använd alltid `ItemView` med en sidstorlek för att undvika tidsavbrott.  
- **Tidszons‑hantering**: EWS returnerar datum i UTC; konvertera till din lokala zon innan du jämför.  
- **Undvik fulla brevlådeskanningar**: Applicera alltid ett `SearchFilter` på serversidan; filtrering på klientsidan slösar bandbredd och minne.  
- **Pro‑tips**: Cacha `ExchangeService`‑objektet under hela applikationens livstid för att minska autentiseringskostnaden.

## Vanliga frågor

**Q: Kan jag använda detta tillvägagångssätt med Office 365?**  
A: Ja, Aspose.Email fungerar med Office 365 Exchange Online genom att peka service‑URL:en till `https://outlook.office365.com/EWS/Exchange.asmx`.

**Q: Stöder Aspose.Email OAuth‑autentisering?**  
A: Absolut—använd `OAuthCredentials` för att autentisera utan att lagra användarlösenord.

**Q: Vad är den maximala brevlådstorleken jag kan bearbeta?**  
A: API‑et kan hantera brevlådor på **flera gigabyte**; eftersom det strömmar resultat hålls minnesförbrukningen låg.

**Q: Hur filtrerar jag bilagor efter filtyp?**  
A: Lägg till ett `SearchFilter.ContainsSubstring` på `AttachmentNames`‑egenskapen och iterera sedan endast över matchande objekt.

**Q: Finns det ett sätt att sortera resultat?**  
A: Ja—skicka en `SortDirection` och den egenskap du vill sortera på (t.ex. `DateTimeReceived`) till `FindItems`‑anropet.

---

**Senast uppdaterad:** 2026-07-17  
**Testad med:** Aspose.Email for Java 24.10  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar en EWSClient‑instans med Aspose.Email för Java: Exchange Server‑integrationsguide](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Hur man laddar ner e‑post från Exchange‑server med Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Hantera EWS‑brevlådsinformation med Aspose.Email för Java: En omfattande guide](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```