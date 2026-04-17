---
date: '2026-03-15'
description: Naučte se, jak převést soubory MSG na EML v Javě pomocí Aspose.Email,
  přidat přílohu k EML, hromadně převádět MSG a zpracovávat data TNEF.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: převod msg na eml java – Průvodce přílohami TNEF v Aspose.Email
url: /cs/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ovládání **convert msg to eml java** s Aspose.Email Java: Práce s TNEF a přílohami e‑mailu  

V moderních aplikacích zaměřených na e‑mail často potřebujete **convert msg to eml java**, přidat novou přílohu k existující zprávě a zachovat speciální formáty jako TNEF. Ať už vytváříte archivní službu, migrační nástroj nebo klientský prohlížeč pošty, Aspose.Email pro Java vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu uvidíte přesně, jak **convert msg to eml java**, **add attachment to eml**, uložit přílohu e‑mailu a pracovat s daty TNEF pomocí knihovny Aspose.Email Java.

## Rychlé odpovědi
- **Jak převést MSG na EML v Javě?** Použijte `MapiMessage` s `MailConversionOptions` a nastavte `convertAsTnef` na `true`.  
- **Mohu přidat přílohu do EML s povoleným TNEF?** Ano – načtěte EML, zavolejte `getAttachments().addItem(...)` a poté uložte.  
- **Jaká Maven závislost je potřeba?** Zahrňte **maven aspose email dependency** uvedenou níže.  
- **Potřebuji licenci pro produkci?** Ano – zkušební verze funguje pro hodnocení, ale plná licence odstraňuje omezení.  
- **Existuje způsob, jak detekovat TNEF v existující zprávě?** Zavolejte `mail.getOriginalIsTnef()` po načtení EML.

## Co je “convert msg to eml java”?
Převod souboru Microsoft Outlook MSG do standardního formátu EML umožňuje zprávu číst v jakémkoli poštovním klientovi kompatibilním s RFC‑822. Převod vám také dává možnost zachovat nebo manipulovat s daty kódovanými jako TNEF během procesu.

## Proč použít Aspose.Email Java pro tento úkol?
- **Kompletní podpora formátů** – MSG, EML, MHTML a další.  
- **Vestavěná podpora TNEF** – není potřeba žádných třetích parserů.  
- **Jednoduché API** – jednorázové volání pro načtení, převod a uložení.  
- **Robustní licencování** – zkušební verze pro testování, plná licence pro produkci.

## Požadavky
- **Aspose.Email for Java** (v25.4, JDK 16) – viz Maven závislost níže.  
- **Maven** nebo jiný nástroj pro sestavení, který dokáže vyřešit balíček Aspose.  
- Základní znalost Java I/O a zpracování výjimek.  

## Nastavení Aspose.Email pro Java
Add the library to your Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence
Aspose.Email nabízí bezplatnou zkušební verzi, ale pro neomezené používání je vyžadována licencovaná verze.

- **Bezplatná zkušební verze:** Stáhněte dočasnou licenci [zde](https://releases.aspose.com/email/java/).  
- **Koupit:** Pro zakoupení licence navštivte [stránku nákupu](https://purchase.aspose.com/buy).

Initialize the license in your Java code:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## Průvodce implementací

### Přidání nové přílohy do hlavní zprávy obsahující TNEF
**Jak přidat přílohu do eml:** Načtěte EML, přidejte soubor a poté uložte.

#### Krok 1: Načtení existující e‑mailové zprávy
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### Krok 2: Přidání nové přílohy
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### Krok 3: Uložení upravené e‑mailové zprávy
```java
eml.save(dataDir + "test_out.eml");
```
*Tip:* Použijte try‑with‑resources k zajištění uzavření streamů a vyhněte se `FileNotFoundException`.

### Vytvoření EML s povoleným TNEF z MSG
**Jak převést msg na eml java:** Nastavte `convertAsTnef` na `true`.

#### Krok 1: Načtení souboru MSG
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### Krok 2: Nastavení možností převodu
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### Krok 3: Převod a uložení
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### Zachování TNEF příloh při načítání souborů EML
**Jak uložit e‑mailovou přílohu při zachování TNEF:** Použijte `MsgLoadOptions`.

#### Krok 1: Nastavení možností načtení
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### Krok 2: Načtení souboru EML s možnostmi
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### Detekce, zda je zpráva TNEF
**Jak zkontrolovat přítomnost TNEF:** Zavolejte `getOriginalIsTnef()`.

#### Krok 1: Načtení souboru EML
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### Krok 2: Detekce přítomnosti TNEF
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## Běžné případy použití a dávkové scénáře
- **Dávkový převod msg:** Procházejte složku s `.msg` soubory, aplikujte výše uvedené kroky převodu a uložte každý výsledek jako `.eml`. Ideální pro rozsáhlé migrace.  
- **Přidání přílohy do eml hromadně:** Kombinujte kód “add attachment” s iterátorem souborového systému pro obohacení mnoha zpráv najednou.  
- **Automatické archivování:** Uložte jak originální MSG, tak EML zachovávající TNEF pro audity souladu.

## Úvahy o výkonu
- **Správa zdrojů:** Zabalte souborové streamy do try‑with‑resources, aby se rychle uvolnily handle.  
- **Velké přílohy:** Zpracovávejte velké soubory po částech nebo je streamujte přímo, aby se předešlo vysoké spotřebě paměti.  
- **Monitorování:** Použijte nástroje pro profilování Javy ke sledování spotřeby haldy při zpracování mnoha příloh.

## Závěr
Podle výše uvedených kroků můžete **convert msg to eml java**, přidat novou přílohu, uložit e‑mailovou přílohu a spolehlivě pracovat s daty TNEF pomocí Aspose.Email pro Java. Knihovna abstrahuje nízkoúrovňové zpracování MIME, což vám umožní soustředit se na obchodní logiku. Pro podrobnější průzkum si prohlédněte oficiální [Aspose dokumentaci](https://reference.aspose.com/email/java/) nebo experimentujte s dalšími možnostmi převodu.

## Často kladené otázky
**Q1: Co je soubor TNEF?**  
A1: TNEF znamená Transport Neutral Encapsulation Format a používá jej Microsoft Outlook k zachování formátování rich‑text při odesílání e‑mailů jako příloh.

**Q2: Můžu používat Aspose.Email bez zakoupení licence?**  
A2: Ano, můžete začít s bezplatnou zkušební verzí. Nicméně zkušební verze uvaluje určitá omezení, která mohou ovlivnit plnohodnotné používání.

**Q3: Je možné převádět mezi všemi e‑mailovými formáty pomocí Aspose.Email?**  
A3: Aspose.Email podporuje převod mezi většinou populárních formátů – včetně EML, MSG a MHTML – ale ověřte konkrétní podporu formátů v [dokumentaci](https://reference.aspose.com/email/java/).

**Q4: Jak řešit chyby file‑not‑found s Aspose.Email?**  
A4: Ověřte, že cesty k souborům, které předáváte API, jsou správné, soubory existují a proces má oprávnění čtení/zápisu do těchto adresářů.

**Q5: Jaký je nejlepší způsob, jak zacházet s velkými přílohami pomocí Aspose.Email?**  
A5: Zpracovávejte přílohy v menších streamech nebo částech a vždy je rychle uzavírejte. Tím se snižuje zatížení paměti a předchází se `OutOfMemoryError`.

## Často kladené otázky (další)

**Q: Odstraňuje Aspose.Email automaticky TNEF při převodu na EML?**  
A: Ne. Ve výchozím nastavení jsou data TNEF zachována. Toto chování můžete ovládat pomocí `MailConversionOptions.setConvertAsTnef`.

**Q: Můžu programově vypsat všechny přílohy v načtené zprávě?**  
A: Ano – použijte `mail.getAttachments()`, který vrací kolekci, kterou můžete iterovat.

**Q: Existuje způsob, jak dávkově převést soubory msg na eml v jednom běhu?**  
A: Rozhodně. Procházejte soubory, aplikujte výše uvedené kroky převodu a uložte každý výsledek.

**Související zdroje:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Stáhněte dočasnou licenci [zde](https://releases.aspose.com/email/java/).

---

**Poslední aktualizace:** 2026-03-15  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}