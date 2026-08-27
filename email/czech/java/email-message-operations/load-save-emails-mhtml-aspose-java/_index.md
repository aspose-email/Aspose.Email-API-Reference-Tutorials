---
date: '2026-08-27'
description: Naučte se, jak načíst soubory msg a převést je na MHTML s Aspose.Email
  for Java, včetně nastavení vlastního timezone a tipů pro batch zpracování e‑mailů.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Naučte se, jak načíst soubory msg a exportovat je jako MHTML pomocí
  Aspose.Email for Java. Obsahuje timezone handling a tipy pro batch processing.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Jak načíst msg a uložit jako MHTML s Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Jak načíst msg a uložit jako MHTML pomocí Aspose.Email for Java
url: /cs/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak načíst msg a uložit jako MHTML pomocí Aspose.Email pro Java

## Úvod

Pokud potřebujete **jak načíst msg** soubory, upravit jejich časová razítka a poté **převést msg na mhtml**, jste na správném místě. V tomto tutoriálu vás provedeme načtením e‑mailu `.msg`, aplikací vlastního posunu časového pásma a uložením výsledku jako archiv MHTML – vše pomocí Aspose.Email pro Java. Ať už pracujete s jednou zprávou nebo s **dávkovým zpracováním e‑mailů**, tyto kroky vám poskytnou solidní základ pro spolehlivé archivování a migraci.

**Co se naučíte**
- Jak načíst `MailMessage` ze souboru `.msg`.
- Jak nastavit vlastní časové pásmo a aktuální datum.
- Jak uložit zprávu jako MHTML s přesným formátováním.
- Tipy pro škálování přístupu na dávkové scénáře.

Připraven/a posílit svůj e‑mailový workflow? Nejprve připravme prostředí.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Email pro Java.
- **Mohu načíst MSG a exportovat do MHTML v jednom kroku?** Ne, načtete, upravíte a pak uložíte.
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Email.
- **Je podpora časových pásem?** Ano, pomocí `setTimeZoneOffset`.
- **Lze to použít v dávkovém zpracování?** Rozhodně – zabalte kroky do smyčky.

## Co je Aspose.Email pro Java?

Aspose.Email pro Java je komplexní API, které vám umožňuje vytvářet, číst, převádět a manipulovat s e‑mailovými zprávami bez potřeby Microsoft Outlook. Podporuje více než 30 e‑mailových formátů a dokáže zpracovat zprávy o stovkách stránek při nízké spotřebě paměti.

## Proč převádět MSG na MHTML?

Převod souborů MSG na MHTML vám poskytne web‑přátelskou, jednosouborovou reprezentaci, kterou lze otevřít v libovolném moderním prohlížeči. Tento formát zachovává původní stylování, vložené obrázky a přílohy, což ho činí ideálním pro **právní archivaci**, **sdílení napříč platformami** a **vkládání e‑mailů do webových stránek nebo dokumentace**.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

### Požadované knihovny a závislosti
- **Aspose.Email for Java** knihovna verze 25.4 (jdk16 classifier) – knihovna podporuje **více než 50** vstupních a výstupních e‑mailových formátů.
- Základní znalost Javy.
- IDE jako IntelliJ IDEA nebo Eclipse.

### Požadavky na nastavení prostředí
- Nainstalovaný JDK 16 nebo novější.
- Maven pro správu závislostí.

## Nastavení Aspose.Email pro Java

Pro přidání knihovny do Maven projektu zahrňte následující závislost:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroky získání licence

Začněte s **bezplatnou zkušební verzí** nebo získáním **dočasné licence** pro vyzkoušení plných možností knihovny bez omezení. Pro dlouhodobé používání zvažte zakoupení licence:

- [Bezplatná zkušební verze](https://releases.aspose.com/email/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)

### Základní inicializace

Třída `License` registruje vaši licenci Aspose.Email a odemkne všechny funkce.  
Po přidání závislosti inicializujte licenci ve svém Java kódu:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Jak načíst msg a uložit jako MHTML?

Načtěte soubor MSG, upravte časové razítko a uložte jej jako MHTML ve třech jednoduchých krocích. Nejprve vytvořte instanci `MailMessage` ze souboru MSG pomocí `MsgLoadOptions`. Dále nastavte požadovaný posun časového pásma pomocí `setTimeZoneOffset`. Nakonec nakonfigurujte `MhtSaveOptions` a zavolejte `save` pro vytvoření archivu MHTML.

### Funkce 1: načtení MailMessage ze souboru

Třída `MailMessage` představuje e‑mailovou zprávu s hlavičkami, tělem a přílohami.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` vám umožňuje řídit, jak je soubor MSG parsován; výchozí nastavení funguje pro většinu scénářů.

### Funkce 2: nastavení aktuálního data a vlastního posunu časového pásma

Objekt `Date` obsahuje časové razítko, které bude zapsáno do hlavičky **Date** e‑mailu.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Posun je vyjádřen v milisekundách; pro UTC+5 předáte `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Funkce 3: uložení MailMessage jako souboru MHTML

`MhtSaveOptions` určuje, jak je e‑mail zabalen do archivu MHTML, přičemž zachovává vložené obrázky a přílohy.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Výsledný soubor `.mhtml` zachovává původní formátování, obrázky a přílohy, což z něj činí věrnou vizuální kopii původního MSG.

## Jak nastavit vlastní posun časového pásma?

Můžete upravit časové pásmo voláním `setTimeZoneOffset` na instanci `MailMessage`. Metoda očekává posun v milisekundách, což umožňuje jak kladné (východně od UTC), tak záporné (západně od UTC) hodnoty. Například UTC‑3 je `-3 * 60 * 60 * 1000`.

## Jak zpracovat soubory MSG dávkově?

Zabalte tento tříkrokový postup do smyčky, která prochází adresář s `.msg` soubory. Znovu použijte jedinou instanci `License`, abyste se vyhnuli opakovanému I/O, a po uložení uvolněte každou `MailMessage`, aby se udržela nízká spotřeba paměti.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Tipy pro dávkové zpracování
1. **Znovu použijte licenci** – zavolejte `new License().setLicense(...)` jednou při spuštění aplikace.
2. **Použijte try‑with‑resources** pro automatické uvolňování streamů.
3. **Zaznamenávejte selhání** do samostatného souboru, abyste mohli později opakovat problematické zprávy.
4. **Zvažte paralelismus** s `ForkJoinPool` pro velké dávky, ale ujistěte se, že každý vlákno používá vlastní instanci `MailMessage`.

## Časté problémy a řešení

- **Nárazové zvýšení paměti u obrovských MSG souborů** – povolte streamování pomocí `MailMessage.load(InputStream, MsgLoadOptions)` a zpracovávejte stream po částech.
- **Nesprávná časová razítka** – ověřte, že systémový čas je nastaven na UTC před aplikací posunů, nebo explicitně předávejte instanci `java.util.Calendar`.
- **Chybějící přílohy v MHTML** – ujistěte se, že `MhtSaveOptions.setWriteHeader(true)`; tím se přílohy vloží jako zdroje `cid:`.

## Často kladené otázky

**Q: Mohu načíst e‑maily z formátů jiných než .msg?**  
A: Ano, Aspose.Email podporuje EML, MHT, EMLX a několik dalších formátů, celkem více než 30 vstupních typů.

**Q: Jak mohu efektivně zpracovat velmi velké e‑mailové soubory?**  
A: Použijte streamingové API (`MailMessage.load(InputStream, ...)`) pro čtení a zápis dat po částech, což udržuje spotřebu paměti pod 50 MB i pro zprávy o 500 stránkách.

**Q: Je možné upravovat přílohy v rámci MailMessage?**  
A: Rozhodně. Můžete přidávat, odstraňovat nebo nahrazovat přílohy pomocí kolekce `msg.getAttachments()`, poté zavolat `save` pro uložení změn.

**Q: Co když je můj posun časového pásma záporný (za UTC)?**  
A: Předávejte zápornou hodnotu v milisekundách metodě `setTimeZoneOffset`, např. `-3 * 60 * 60 * 1000` pro UTC‑3.

**Q: Mohu používat Aspose.Email v komerčních projektech?**  
A: Ano, pokud máte platnou komerční licenci. Bezplatná zkušební verze je omezena na 20 MB na dokument.

**Q: Jak zpracovat tisíce MSG souborů, aniž bych vyčerpával paměť?**  
A: Zpracovávejte soubory po dávkách, po uložení uvolněte každou `MailMessage` a využijte vzor `try‑with‑resources` v Javě pro automatické uvolnění zdrojů.

## Zdroje
- [dokumentace](https://reference.aspose.com/email/java/)
- [Dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout knihovnu](https://releases.aspose.com/email/java/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze](https://releases.aspose.com/email/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Fórum podpory](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-08-27  
**Testováno s:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

## Související tutoriály

- [Jak načíst a parsovat Outlook MSG soubory pomocí Aspose.Email pro Java: Kompletní průvodce](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email pro Java: Uložit e‑maily jako MHT soubory](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Jak extrahovat přílohy ze souborů msg pomocí Aspose.Email pro Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}