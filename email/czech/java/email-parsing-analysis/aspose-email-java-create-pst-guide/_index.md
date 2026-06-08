---
date: '2026-06-08'
description: Naučte se, jak vytvořit soubory PST pomocí Aspose.Email pro Java, včetně
  toho, jak přidávat struktury složek a jak efektivně vyhledávat obsah PST. Průvodce
  krok za krokem.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Jak vytvořit soubory PST pomocí Aspose.Email pro Java
url: /cs/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ovládání správy e‑mailů pomocí Aspose.Email pro Java

Pokud potřebujete **how to create pst** soubory programově, jste na správném místě. V tomto tutoriálu projdeme každý krok potřebný k vytvoření Unicode PST souboru, přidání standardních Outlook složek, importu zpráv a provedení vyhledávání bez rozlišení velkých a malých písmen – vše pomocí Aspose.Email pro Java. Na konci budete mít znovupoužitelný kódový vzor, který škáluje od několika e‑mailů po archiv s více gigabajty.

## Rychlé odpovědi
- **Jak začít?** Přidejte Maven závislost Aspose.Email, získejte licenci a vytvořte instanci `PersonalStorage`.
- **Mohu přidat složku Inbox?** Ano – zavolejte `pst.getRootFolder().addSubFolder("Inbox")`.
- **Je podporáno vyhledávání bez rozlišení velkých a malých písmen?** Použijte `PersonalStorageQueryBuilder` s `StringComparison.OrdinalIgnoreCase`.
- **Jakou velikost souboru lze zpracovat?** Aspose.Email zpracovává PST soubory až do 2 GB, aniž by načítal celý soubor do paměti.
- **Potřebuji placenou licenci pro produkci?** Trvalá licence odstraňuje omezení zkušební verze a odemyká plné výkonnostní funkce.

## Co je how to create pst?
**how to create pst** označuje programový proces generování souboru Outlook Personal Storage Table (PST) pomocí kódu místo uživatelského rozhraní Outlooku. Aspose.Email pro Java poskytuje plně spravované API, které vytváří Unicode PST soubory, přidává složky a ukládá objekty `MapiMessage` bez nutnosti instalace Outlooku.

## Proč použít Aspose.Email pro tvorbu PST?
Aspose.Email podporuje **50+** formátů souvisejících s e‑mailem (MSG, EML, MBOX, PST atd.) a může zpracovávat PST soubory až do **2 GB** velikosti při využití paměti pod **150 MB** díky architektuře lazy‑loading. Tato kvantifikovaná schopnost jej činí ideálním pro podnikovou archivaci, migraci a scénáře související s dodržováním předpisů.

## Požadavky

- **Java Development Kit (JDK)** – verze 16 nebo novější.
- **Maven** – pro správu závislostí.
- Základní znalost syntaxe Javy; předchozí zkušenost se soubory PST není vyžadována.

## Jak vytvořit PST soubor?

Třída `PersonalStorage` představuje PST soubor a poskytuje metody pro jeho vytvoření, otevření a manipulaci s obsahem. Pro vytvoření nového Unicode PST zavolejte `PersonalStorage.create()` s požadovanou cestou k souboru a verzí formátu. Tato operace generuje moderní PST, který podporuje velké složky, Unicode znaky a efektivní streamování, což jej činí vhodným jak pro malé, tak pro podnikově‑úrovňové archivní úlohy.

### Krok 1: Přidat Maven závislost

Přidejte Maven závislost Aspose.Email do svého `pom.xml`. Tím se automaticky stáhnou všechny potřebné binární soubory.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Krok 2: Získat a použít licenci

Je k dispozici bezplatná zkušební verze, ale trvalá licence odstraňuje omezení zkušební verze a umožňuje plno‑rychlostní zpracování.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Jak přidat složku do PST?

Vytvořte požadovanou hierarchii složek pod kořenem PST a poté na ni odkazujte při vkládání zpráv. Objekt `FolderInfo` představuje každou složku a může být libovolně vnořen, což vám umožní budovat struktury jako Inbox, Sent Items nebo vlastní projektové složky. Přidávání složek je lehká operace, která nenačítá obsah zpráv, čímž zachovává výkon i u velkých PST souborů.

### Krok 1: Inicializovat PersonalStorage

Třída `PersonalStorage` je hlavní objekt Aspose.Email, který představuje jeden PST soubor v paměti. Po vytvoření instance probíhají všechny operace čtení a zápisu přes tento objekt.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Krok 2: Definovat cesty adresářů

Nastavte zdrojové a cílové cesty pro své e‑mailové soubory a umístění výstupního PST.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Krok 3: Vytvořit PST soubor

Použijte `PersonalStorage.create()` s `FileFormatVersion.Unicode` k vytvoření moderního Unicode PST, který podporuje velké složky a Unicode znaky.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Jak vyhledávat v PST?

`PersonalStorageQueryBuilder` je builder třída používaná k sestavení vyhledávacích dotazů pro obsah PST. Konfigurací builderu s požadovanými kritérii a specifikací `StringComparison.OrdinalIgnoreCase` můžete provádět rychlé vyhledávání bez rozlišení velkých a malých písmen napříč předměty, těly a vlastními vlastnostmi, aniž byste načítali celý PST do paměti.

### Krok 1: Sestavit vyhledávací dotaz

Sestavte dotaz, který hledá klíčové slovo v předmětu nebo těle, ignorujíc velikost písmen.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Krok 2: Spustit dotaz a získat zprávy

Spusťte dotaz na cílové složce a iterujte přes výslednou kolekci `MapiMessage`.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Vytvoření předdefinované složky v PST

Přidání předdefinované složky jako **Inbox** pomáhá efektivně organizovat vaše e‑mailové údaje.

### Krok 1: Inicializovat objekt PersonalStorage
Předpokládejte, že objekt `PersonalStorage` (`pst`) je již vytvořen, jak bylo ukázáno dříve.

### Krok 2: Vytvořit složku 'Inbox'

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Přidání zpráv do složky PST

Naplněte svou PST složku e‑mailovými zprávami načtením z souborů a jejich konverzí.

### Krok 1: Načíst e‑mailovou zprávu

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Krok 2: Přidat do složky PST

Převeďte `MailMessage` na `MapiMessage` a přidejte ji:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Praktické aplikace

Aspose.Email pro Java není jen o tvorbě PST souborů; je to všestranný nástroj s mnoha aplikacemi:
- **Archivace e‑mailů**: Automatizujte archivaci firemních e‑mailů do PST souborů, podporující zásady uchování až 10 let.
- **Migrační nástroje**: Bez problémů migrujte ze starých úložišť pošty (např. MBOX) do Outlook PST jedním API voláním na zprávu.
- **Analýza dat**: Extrahujte metadata jako odesílatel, příjemce a časové razítka pro datové toky business intelligence.
- **Zálohovací řešení**: Vytvořte robustní nástroje pro zálohování, které ukládají inkrementální změny e‑mailů bez opětovného zpracování celé poštovní schránky.

## Úvahy o výkonu

- **Správa zdrojů**: Vždy zavolejte `pst.dispose()` nebo použijte try‑with‑resources k okamžitému uvolnění nativních handle.
- **Dávkové zpracování**: Zpracovávejte e‑maily v dávkách po **500** položkách, aby byl využití paměti předvídatelné.
- **Zpracování souběžnosti**: Knihovna je bezpečná pro více vláken při operacích jen pro čtení; pro zápisy synchronizujte přístup k instanci `PersonalStorage`.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **OutOfMemoryError** při zpracování velkých PST | Načítání celého PST do paměti | Povolte `PersonalStorage.setUseUnicode(true)` a zpracovávejte zprávy ve streamu. |
| **Folder not found** chyba | Nesprávná velikost písmen v cestě složky | Použijte `StringComparison.OrdinalIgnoreCase` v dotazech nebo normalizujte názvy složek. |
| **License not applied** | Licenční soubor nebyl načten před prvním voláním API | Načtěte licenci při startu aplikace, před vytvořením jakýchkoli objektů `PersonalStorage`. |

## Často kladené otázky

**Otázka: Jaká je minimální verze Javy požadovaná?**  
Odpověď: JDK 16 nebo vyšší se doporučuje pro plnou kompatibilitu s Aspose.Email pro Java.

**Otázka: Mohu používat Aspose.Email bez licence?**  
Odpověď: Ano, je k dispozici zkušební režim, ale omezuje velikost PST na **10 MB** a vypíná některá optimalizační vylepšení.

**Otázka: Jak efektivně zpracovávat velké PST soubory?**  
Odpověď: Zpracovávejte zprávy v dávkách, rychle uvolňujte objekty `MapiMessage` a povolte lazy loading pomocí `PersonalStorage.setUseUnicode(true)`.

**Otázka: Je možné přidávat přílohy k e‑mailům v PST souborech?**  
Odpověď: Ano. Při konverzi `MailMessage` na `MapiMessage` zavolejte `mapiMsg.getAttachments().add(attachment)` pro vložení souborů.

**Otázka: Jaký typ podpory je k dispozici pro řešení problémů?**  
Odpověď: Aspose nabízí dedikované fórum podpory, podrobnou dokumentaci a e‑mailovou podporu pro licencované zákazníky.

## Zdroje
- [Dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout](https://releases.aspose.com/email/java/)
- [Koupit](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze](https://releases.aspose.com/email/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Fórum podpory](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-06-08  
**Testováno s:** Aspose.Email for Java 24.10  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit a spravovat Outlook PST soubory pomocí Aspose.Email pro Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipulace s PST soubory pomocí Aspose.Email pro Java: Kompletní průvodce](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extrahování e‑mailových příloh v Javě – Použití Aspose.Email pro PST soubory – Průvodce krok za krokem](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}