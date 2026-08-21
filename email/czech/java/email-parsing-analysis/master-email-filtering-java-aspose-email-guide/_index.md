---
date: '2026-06-23'
description: Naučte se, jak filtrovat e‑maily podle data, odesílatele a předmětu pomocí
  Aspose.Email pro Javu. Tento krok‑za‑krokem tutoriál vám ukáže, jak efektivně automatizovat
  filtrování e‑mailů protokolem IMAP.
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
title: Jak filtrovat e‑maily v Javě s Aspose.Email – Průvodce pro vývojáře
url: /cs/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak filtrovat e‑maily v Javě s Aspere.Email – Průvodce pro vývojáře

## Úvod

Pokud hledáte **jak filtrovat e‑maily** programově, jste na správném místě. Ať už spravujete firemní poštovní schránku, budujete systém ticketingu pro zákaznickou podporu, nebo jen chcete udržet svůj osobní inbox v pořádku, automatizace filtrování e‑mailů ušetří hodiny ruční práce. V tomto tutoriálu použijeme **Aspose.Email for Java**, knihovnu, která podporuje více než 30 e‑mailových protokolů a dokáže zpracovat poštovní schránky s 100 000 + zprávami, aniž by načítala celý adresář do paměti. Naučíte se připojit k IMAP serveru, aplikovat filtry podle data, odesílatele, předmětu a dalších kritérií a optimalizovat výkon pro zpracování ve velkém měřítku.

## Rychlé odpovědi
- **Jaká knihovna zpracovává filtrování IMAP v Javě?** Aspose.Email for Java.  
- **Mohu filtrovat podle data a odesílatele v jednom volání?** Ano – kombinujte kritéria pomocí `ImapQueryBuilder`.  
- **Potřebuji licenci pro produkci?** Plná licence odstraňuje omezení zkušební verze; dočasná licence funguje pro testování.  
- **Je podpora stránkování?** Rozhodně – načítejte zprávy po stránkách, aby se snížila spotřeba paměti.  
- **Jaká verze Javy je požadována?** JDK 8 nebo novější.

## Co je filtrování e‑mailů v Javě?

Filtrování e‑mailů v Javě znamená programově vybírat zprávy, které odpovídají konkrétním kritériím – například datu, odesílateli nebo předmětu – aby se zpracovával jen relevantní podmnožina. Tento přístup snižuje množství dat přenášených po síti a umožňuje následným systémům pracovat s cíleným souborem e‑mailů, což zlepšuje rychlost i využití zdrojů.

## Proč použít Aspose.Email pro Javu?

Aspose.Email pro Javu podporuje **30 + vstupních a výstupních formátů**, včetně EML, MSG, MBOX a PST, a dokáže zpracovat **poštovní schránky s více než 100 000 zprávami** při spotřebě paměti pod 50 MB díky server‑side filtrování a stránkování. Knihovna také poskytuje vestavěnou podporu pro vlastní IMAP příznaky, kódování UTF‑8 a dotazy citlivé na velikost písmen, což z ní činí komplexní řešení pro podnikovou automatizaci e‑mailů.

## Předpoklady

1. **Java Development Kit (JDK)** – verze 8 nebo novější.  
2. **Maven** – pro správu závislostí.  
3. **Aspose.Email for Java** – hlavní knihovna, kterou použijeme.

### Požadované knihovny a závislosti

Přidejte závislost Aspose.Email do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence

- **Free Trial** – stáhněte si zkušební verzi a vyzkoušejte všechny funkce.  
- **Temporary License** – získejte časově omezenou licenci pro rozšířené testování.  
- **Full License** – zakupte pro produkční použití a odstraňte všechna omezení zkušební verze.  
- **License File** – získáte ji na [Aspose's website](https://purchase.aspose.com/temporary-license/).

## Nastavení Aspose.Email pro Javu

Chcete‑li začít používat Aspose.Email, postupujte následovně:

1. **Download and Install** – Maven automaticky stáhne knihovnu z výše uvedeného placeholderu.  
2. **Initialize Library** – Načtěte soubor licence (pokud jej máte) před provedením jakýchkoli API volání:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## Průvodce implementací

### Jak se připojit k IMAP serveru?

Nejprve musíte navázat spojení s IMAP serverem pomocí třídy `ImapClient`, která představuje klientskou relaci schopnou autentizace a odesílání příkazů serveru. Toto spojení je základem pro všechny následné operace s poštovní schránkou.

Typická sekvence připojení zahrnuje zadání hostitele, portu, uživatelských údajů a bezpečnostních možností, následně výběr požadované složky (např. **Inbox**) před provedením jakýchkoli dotazů.

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### Jak filtrovat e‑maily podle předmětu a data?

Třída `ImapQueryBuilder` vám pomůže vytvořit složitá kritéria vyhledávání, která jsou přeložena do efektivních IMAP SEARCH příkazů. Kombinací klíčových slov předmětu s rozsahem dat můžete získat jen zprávy, které jsou relevantní pro vaši logiku zpracování.

V tomto příkladu hledáme zprávy, jejichž předmět obsahuje „Newsletter“ a které byly přijaty během aktuálního dne, čímž minimalizujeme přenos dat a zátěž zpracování.

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### Jak filtrovat e‑maily podle dnešního data?

Pomocí `ImapQueryBuilder` můžete vytvořit filtr, který odpovídá přesnému kalendářnímu datu odeslání zprávy. To je užitečné pro denní úlohy, které potřebují pracovat jen s nejnovějšími zprávami.

Builder automaticky formátuje datum podle protokolu IMAP, což zajišťuje přesné filtrování na straně serveru bez dalšího klientského parsování.

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### Jak filtrovat e‑maily v rozmezí dat?

Když potřebujete pracovat s rozsahem dnů, `ImapQueryBuilder` vám umožní definovat počáteční a koncový `DateTime`. Knihovna tyto hodnoty převede do odpovídající syntaxe IMAP SEARCH a vrátí všechny zprávy spadající do zadaného intervalu.

Tato technika je ideální pro tvorbu týdenních reportů nebo archivaci zpráv starších než určitý práh.

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### Jak filtrovat e‑maily podle konkrétního odesílatele?

`ImapQueryBuilder` může cílit na konkrétní e‑mailovou adresu nebo celou doménu porovnáním hlavičky `From`. To vám umožní izolovat komunikaci od důvěryhodných partnerů nebo odfiltrovat nechtěné odesílatele.

Zadání přesné adresy (např. `user@example.com`) nebo vzoru domény (např. `@example.com`) poskytne přesné výsledky přímo ze serveru.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### Jak filtrovat e‑maily podle konkrétní domény?

Podobně jako filtrování podle odesílatele můžete omezit výsledky na konkrétní doménu pomocí metody `fromAddress` třídy `ImapQueryBuilder`. To je užitečné, když potřebujete zpracovat všechny zprávy pocházející od firemního partnera nebo konkrétního poskytovatele e‑mailových služeb.

Dotaz je proveden na serveru, takže jsou přenášeny jen odpovídající zprávy.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### Jak filtrovat e‑maily podle konkrétního příjemce?

Pro zaměření na zprávy adresované konkrétní poštovní schránce použijte metodu `toAddress` třídy `ImapQueryBuilder`. To je zvláště užitečné pro sdílené inboxy nebo role‑based schránky, kde více uživatelů potřebuje zpracovávat stejnou sadu e‑mailů.

Builder vytvoří IMAP SEARCH klauzuli, která odpovídá hlavičce `To`, což zajišťuje efektivní filtrování na straně serveru.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### Jak provést citlivé na velikost písmen filtrování e‑mailů?

Ve výchozím nastavení jsou IMAP vyhledávání necitlivá na velikost písmen, ale `ImapQueryBuilder` nabízí možnost vynutit citlivost na velikost písmen pro přesné shody. To je důležité při rozlišování identifikátorů, které se liší jen velikostí písmen.

Před přidáním dalších kritérií zapněte příznak `setCaseSensitive(true)`, abyste dosáhli přesného filtrování.

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### Jak specifikovat kódování pro Query Builder?

Při práci s internacionalizovanými předměty nebo adresami byste měli nastavit znakové kódování na `ImapQueryBuilder`. Použití UTF‑8 zajišťuje, že ne‑ASCII znaky jsou správně interpretovány IMAP serverem.

Voláním `setEncoding(Encoding.UTF_8)` před sestavením dotazu předejdete poškozeným výsledkům.

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### Jak filtrovat zprávy s podporou stránkování?

Stránkování je nezbytné pro velké poštovní schránky. `ImapClient` poskytuje metody pro načítání zpráv po dávkách, což vám umožní zpracovávat například 500 zpráv najednou. To udržuje nízkou spotřebu paměti a zvyšuje celkovou propustnost.

Kombinujte stránkování s `ImapQueryBuilder`, abyste na každé stránce získali jen relevantní podmnožinu.

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

### Jak filtrovat zprávy podle vlastního příznaku?

IMAP podporuje uživatelem definované příznaky jako `\Flagged` nebo vlastní tagy. S `ImapQueryBuilder` můžete tyto příznaky specifikovat a získat jen zprávy, které jsou takto označeny.

Tato schopnost je užitečná pro workflow, které spoléhají na označování zpráv pro pozdější revizi nebo speciální zpracování.

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## Praktické aplikace

- **Corporate Email Management** – Automaticky řadit příchozí poštu do oddělených složek podle odesílatele nebo předmětu.  
- **Customer Support Systems** – Prioritizovat tickety filtrováním e‑mailů, které obsahují „Urgent“ nebo pocházejí od VIP zákazníků.  
- **Personal Organisation Tools** – Vytvořit lehkou Java utilitu, která archivuje dnešní newslettery a v jednom běhu smaže spam.

## Úvahy o výkonu

- **Server‑Side Filtering** – Nechte IMAP server provést těžkou práci; pouze odpovídající zprávy jsou přenášeny po síti.  
- **Paging** – Načítejte výsledky po částech (např. 200‑zprávové stránky), aby se předešlo načtení celé poštovní schránky do RAM.  
- **Connection Reuse** – Udržujte jedinou instanci `ImapClient` po dobu běhu dávkového úkolu, aby se snížila režie navazování spojení.  
- **Monitoring** – Zaznamenávejte počet zpracovaných zpráv a uplynulý čas; upravte velikost stránky, pokud zaznamenáte špičky v paměti.

## Závěr

Nyní máte kompletní sadu nástrojů **jak filtrovat e‑maily** pomocí Aspose.Email pro Javu. Od jednoduchých dotazů založených na datu až po složité multi‑kritéria s vlastními příznaky, knihovna vám poskytuje detailní kontrolu při zachování optimálního výkonu.

### Další kroky

- Kombinujte tyto filtry do jedné znovupoužitelné metody pro vaši aplikaci.  
- Prozkoumejte API **Aspose.Email** pro odesílání, přeposílání a odpovídání na zprávy.  
- Integrovat s databází pro ukládání metadat filtrovaných zpráv pro analytiku.

---

## Často kladené otázky

**Q: Jak se připojit k IMAP serveru pomocí Aspose.Email?**  
A: Vytvořte instanci `ImapClient` s hostitelem, portem, uživatelským jménem a heslem, poté zavolejte `client.selectFolder("Inbox")`.

**Q: Mohu filtrovat e‑maily podle data i odesílatele v jednom požadavku?**  
A: Ano – použijte `ImapQueryBuilder` ke kombinaci kritérií `date` a `fromAddress`; knihovna odešle jediný SEARCH příkaz.

**Q: Podporuje Aspose.Email SSL/TLS pro zabezpečená spojení?**  
A: Rozhodně – před připojením nastavte `client.setSecurityOptions(SecurityOptions.SSL_TLS)`.

**Q: Jaká je maximální velikost poštovní schránky, kterou Aspose.Email zvládne?**  
A: Knihovna dokáže zpracovat poštovní schránky s **více než 100 000 zprávami**, pokud používáte stránkování; spotřeba paměti zůstává pod 50 MB.

**Q: Potřebuji licenci pro vývojové sestavy?**  
A: Dočasná licence odstraňuje vodoznak a omezení zkušební verze; plná licence je vyžadována pro produkční nasazení.

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Email for Java 24.9  
**Author:** Aspose

## Související tutoriály

- [Stáhnout e‑maily z IMAP serveru pomocí Aspose.Email pro Java: krok za krokem](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [Mistrovství inicializace IMAP klienta v Javě s Aspose.Email: komplexní průvodce](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [Jak zálohovat IMAP e‑maily s Aspose.Email pro Java: krok za krokem](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}