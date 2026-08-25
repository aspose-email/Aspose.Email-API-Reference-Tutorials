---
date: '2026-07-17'
description: 'Jak filtrovat e‑mailové zprávy pomocí Aspose.Email Java a EWS: naučte
  se techniky filtrování podle data, odesílatele a předmětu pro zefektivnění vaší
  poštovní schránky.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Jak filtrovat e‑mailové zprávy pomocí Aspose.Email Java a EWS. Objevte
  techniky filtrování podle data, odesílatele a předmětu, aby byla vaše poštovní schránka
  organizovaná.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Jak filtrovat e‑mailové zprávy pomocí Aspose.Email Java a EWS
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
title: Jak filtrovat e‑mailové zprávy pomocí Aspose.Email Java a EWS – průvodce
url: /cs/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ovládání filtrování e‑mailů s Aspose.Email Java a EWS: Kompletní průvodce

## Úvod

**Jak efektivně filtrovat e‑maily** je základní dovednost pro každého, kdo pracuje s Microsoft Exchange nebo s moderní poštovní schránkou. Ať už jste vývojář, který buduje firemní automatizaci, nebo jednotlivec, který chce udržet svou doručenou poštu přehlednou, zvládnutí správných technik filtrování může ušetřit hodiny ruční práce. V tomto průvodci si projdeme Aspose.Email pro Java spolu s Exchange Web Services (EWS) a ukážeme si, jak filtrovat podle data, odesílatele, předmětu, domény, příjemce a dokonce kombinovat více kritérií pomocí logických operátorů.

### Co se naučíte
- Techniky filtrování zpráv pomocí EWS v Javě.  
- Filtrování e‑mailů podle kritérií jako datum, odesílatel, předmět atd.  
- Implementace stránkování pro práci s velkými poštovními schránkami.  
- Praktické aplikace těchto metod filtrování v reálných scénářích.  
- Úvahy o výkonu a osvědčené postupy s Aspose.Email Java.

Na konci tohoto tutoriálu budete schopni napsat čistý, výkonný Java kód, který získá přesně ty zprávy, které potřebujete ze serveru Exchange.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Email pro Java.  
- **Jaký protokol používá?** Exchange Web Services (EWS).  
- **Mohu filtrovat podle časového období?** Ano – použijte kritéria `DateTime` ve `SearchFilter`.  
- **Je podporováno stránkování?** Rozhodně, API nabízí `ItemView` s offsetem/limitem.  
- **Potřebuji licenci pro produkci?** Ano, komerční licence odstraňuje omezení evaluační verze.

## Co je Aspose.Email pro Java?
Aspose.Email pro Java je komplexní API, které umožňuje programatický přístup k e‑mailovým serverům, MIME zprávám a Exchange Web Services bez nutnosti Outlooku nebo jiného klienta. Abstrahuje podkladové protokoly, takže se můžete soustředit na obchodní logiku. Knihovna podporuje jak lokální servery Exchange, tak Exchange Online, a poskytuje jednotné API pro různé scénáře nasazení.

## Proč použít Aspose.Email s EWS?
Aspose.Email podporuje **více než 50** e‑mailových protokolů a dokáže zpracovat **stovky tisíc zpráv** za hodinu při využití méně než **100 MB** paměti díky své streamovací architektuře. Tento kvantifikovatelný výkon jej činí ideálním pro automatizaci poštovních schránek v podnikovém měřítku. Navíc nabízí vestavěnou podporu pro OAuth a moderní autentizaci, což usnadňuje zabezpečená připojení k prostředím Office 365.

## Požadavky

- **Požadované knihovny**: Přidejte knihovnu Aspose.Email do svého projektu.  
- **Nastavení prostředí**: Je potřeba připravené vývojové prostředí pro Java aplikace.  
- **Předpoklady**: Znalost programování v Javě a e‑mailových protokolů bude výhodou.

## Nastavení Aspose.Email pro Java

### Instalace pomocí Maven
Přidejte následující závislost do souboru `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
- **Bezplatná zkušební verze**: Začněte s bezplatnou zkušební verzí a prozkoumejte možnosti Aspose.Email.  
- **Dočasná licence**: Získejte dočasnou licenci pro prodloužené hodnocení.  
- **Koupě**: Zvažte zakoupení plné licence, pokud nástroj splňuje vaše požadavky.

Inicializujte a nastavte Aspose.Email importováním potřebných balíčků a navázáním spojení s vaším e‑mailovým serverem pomocí EWS přihlašovacích údajů. Tento krok je klíčový pro programatický přístup k datům poštovní schránky.

## Jak filtrovat e‑maily pomocí EWS v Javě?

`ExchangeService` je třída Aspose.Email, která představuje spojení se serverem Exchange.  
`SearchFilter` definuje kritéria pro vyhledávání položek na serveru.  
`FindItems` provádí vyhledávání a vrací shodné položky.  
`ItemView` řídí stránkování a počet položek vrácených na jeden požadavek.

Načtěte instanci `ExchangeService` s vašimi přihlašovacími údaji, vytvořte `SearchFilter`, který odpovídá vašim kritériím, a zavolejte `FindItems` s `ItemView`, abyste získali jen požadované zprávy. Tento jednorázový vzor – připojit → filtrovat → načíst – pokrývá většinu případů a škáluje na velké poštovní schránky, když povolíte stránkování.

## Průvodce implementací

### Filtrování zpráv pomocí EWS

#### Přehled
Filtrování umožňuje získat jen e‑maily, které splňují určité podmínky, například konkrétní předmět nebo datum, přímo z vaší poštovní schránky.
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
**Vysvětlení**: Kód naváže spojení s vaší poštovní schránkou a vytvoří dotaz, který filtruje e‑maily s předmětem „Newsletter“ k určitému datu.

### Jak filtrovat e‑maily podle dnešního data?

`SearchFilter.IsEqualTo` vytváří filtr, který odpovídá položkám, kde vlastnost má zadanou hodnotu.  
`DateTimeReceived` je vlastnost udávající, kdy byl e‑mail přijat.

Načtěte aktuální datum, vytvořte `SearchFilter.IsEqualTo` na vlastnost `DateTimeReceived` a spusťte dotaz. Tento filtr vrátí jen zprávy přijaté v den, kdy spustíte kód, což usnadňuje denní zpracování. Filtr můžete kombinovat s dalšími kritérii, jako je odesílatel nebo předmět, pro ještě přesnější výběr.

### Jak filtrovat e‑maily podle časového období?

`SearchFilter.IsGreaterThanOrEqualTo` vytváří filtr, který odpovídá položkám s hodnotou vlastnosti větší nebo rovné zadané hodnotě.  
`SearchFilter.IsLessThanOrEqualTo` vytváří filtr, který odpovídá položkám s hodnotou vlastnosti menší nebo rovné zadané hodnotě.  
`SearchFilter.And` kombinuje více filtrů tak, aby byly splněny všechny podmínky.

Definujte počáteční a koncové `DateTime`, spojte je pomocí `SearchFilter.IsGreaterThanOrEqualTo` a `SearchFilter.IsLessThanOrEqualTo` a poté použijte `SearchFilter.And` k jejich sloučení. Výsledná sada obsahuje každou zprávu spadající do zadaného intervalu. Tento přístup vám umožní získat veškerou komunikaci během libovolného období, například posledního čtvrtletí nebo konkrétního projektového časového rámce.

### Jak filtrovat e‑maily podle konkrétního odesílatele?

`SearchFilter.IsEqualTo` vytváří filtr, který odpovídá položkám, kde vlastnost má zadanou hodnotu.

Vytvořte `SearchFilter.IsEqualTo` na vlastnost `From` s e‑mailovou adresou odesílatele. Tento filtr izoluje všechny zprávy od daného kontaktu, což je ideální pro priority inboxu nebo kontrolu souladu. Pro částečné shody můžete také použít `SearchFilter.ContainsSubstring`, pokud není přesná adresa známa nebo chcete filtrovat podle domény.

### Jak filtrovat e‑maily podle konkrétní domény?

`SearchFilter.ContainsSubstring` vytváří filtr, který odpovídá položkám, kde vlastnost obsahuje zadaný podřetězec.

Použijte `SearchFilter.ContainsSubstring` na vlastnost `From` s řetězcem domény (např. „@example.com“). Tento filtr načte všechny e‑maily pocházející z dané domény, což je užitečné pro sledování partnerů nebo dodavatelů. Kombinace tohoto filtru s kritérii data vám umožní sledovat komunikaci podle domény v čase, což pomáhá při bezpečnostních auditech.

### Jak filtrovat e‑maily podle konkrétního příjemce?

`SearchFilter.IsEqualTo` vytváří filtr, který odpovídá položkám, kde vlastnost má zadanou hodnotu.

Aplikujte `SearchFilter.IsEqualTo` na kolekci `ToRecipients` s cílovou adresou. To je užitečné, když potřebujete auditovat zprávy odeslané konkrétní poštovní schránce nebo distribučnímu seznamu. Pro částečné shody můžete také použít `SearchFilter.ContainsSubstring`, pokud pracujete s více příjemci sdílejícími společnou doménu.

### Jak kombinovat dotazy pomocí logiky AND?

`SearchFilter.And` kombinuje více filtrů tak, aby byly splněny všechny podmínky.

Propojte několik objektů `SearchFilter` pomocí `SearchFilter.And`. Například kombinujte filtr odesílatele s filtrem předmětu, abyste získali jen newslettery od důvěryhodného odesílatele. Operátor AND zajišťuje, že jsou vráceny jen položky splňující všechny zadané podmínky, čímž se výsledek zúží na nejrelevantnější zprávy.

### Jak kombinovat dotazy pomocí logiky OR?

`SearchFilter.Or` spojuje filtry tak, aby stačilo splnit libovolnou jednu podmínku.

Použijte `SearchFilter.Or` k sloučení filtrů, když stačí, aby odpovídala jedna z podmínek – ideální pro získání zpráv, které jsou buď od určité sady odesílatelů **nebo** obsahují konkrétní klíčová slova. Použití logiky OR rozšíří vyhledávání tak, aby zachytilo veškerou relevantní komunikaci napříč více kategoriemi, aniž by chyběly důležité informace.

## Časté úskalí a tipy

- **Stránkování je nezbytné**: Při práci s poštovními schránkami většími než 1 000 položek vždy použijte `ItemView` s nastavenou velikostí stránky, aby nedošlo k časovým limitům.  
- **Zpracování časových pásem**: EWS vrací data v UTC; před porovnáním je převedete do místního časového pásma.  
- **Vyhněte se úplnému skenování poštovní schránky**: Vždy aplikujte `SearchFilter` na straně serveru; filtrování na straně klienta plýtvá šířkou pásma i pamětí.  
- **Profesionální tip**: Cacheujte objekt `ExchangeService` po celou dobu životnosti aplikace, abyste snížili režii autentizace.

## Často kladené otázky

**Q: Můžu tento přístup použít s Office 365?**  
A: Ano, Aspose.Email funguje s Office 365 Exchange Online nastavením URL služby na `https://outlook.office365.com/EWS/Exchange.asmx`.

**Q: Podporuje Aspose.Email OAuth autentizaci?**  
A: Rozhodně – použijte `OAuthCredentials` k autentizaci bez ukládání uživatelských hesel.

**Q: Jaká je maximální velikost poštovní schránky, kterou mohu zpracovat?**  
A: API zvládne poštovní schránky o **několika gigabajtech**; díky streamování zůstává spotřeba paměti nízká.

**Q: Jak filtrovat přílohy podle typu souboru?**  
A: Přidejte `SearchFilter.ContainsSubstring` na vlastnost `AttachmentNames` a poté iterujte jen přes odpovídající položky.

**Q: Existuje způsob, jak seřadit výsledky?**  
A: Ano – předávejte `SortDirection` a vlastnost, podle které chcete řadit (např. `DateTimeReceived`) do volání `FindItems`.

---

**Poslední aktualizace:** 2026-07-17  
**Testováno s:** Aspose.Email pro Java 24.10  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit instanci EWSClient pomocí Aspose.Email pro Java: Průvodce integrací s Exchange Serverem](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Jak stáhnout e‑maily ze serveru Exchange pomocí Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Správa informací o poštovní schránce EWS pomocí Aspose.Email pro Java: Komplexní průvodce](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


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