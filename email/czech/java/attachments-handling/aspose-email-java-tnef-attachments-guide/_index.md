---
date: '2025-12-13'
description: Naučte se, jak převádět soubory msg a eml pomocí Aspose.Email pro Javu,
  přidávat nové přílohy, ukládat přílohy e‑mailu a zpracovávat data TNEF.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: Převod souborů MSG a EML pomocí Aspose.Email pro Javu – Průvodce přílohami
  TNEF
url: /cs/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mistrovství Aspose.Email Java: Práce s TNEF a přílohami e‑mailu  

V moderních aplikacích zaměřených na e‑mail často potřebujete **convert msg eml** soubory, přidat novou přílohu k existující zprávě a zachovat speciální formáty jako TNEF. Ať už vytváříte archivní službu, migrační nástroj nebo klientský prohlížeč pošty, Aspose.Email pro Java vám poskytuje čistý programový způsob, jak to provést. V tomto tutoriálu uvidíte přesně, jak **convert msg to eml**, přidat novou přílohu, uložit přílohu e‑mailu a pracovat s TNEF daty pomocí knihovny Aspose.Email Java.

## Rychlé odpovědi
- **Jak převést MSG na EML?** Použijte `MapiMessage` s `MailConversionOptions` a nastavte `convertAsTnef` na `true`.  
- **Mohu přidat přílohu do EML s podporou TNEF?** Ano – načtěte EML, zavolejte `getAttachments().addItem(...)` a poté uložte.  
- **Jaká verze Aspose.Email je vyžadována?** Příklad používá verzi 25.4 (JDK 16).  
- **Potřebuji licenci pro produkci?** Ano – zkušební verze funguje pro hodnocení, ale plná licence odstraňuje omezení.  
- **Existuje způsob, jak detekovat TNEF v existující zprávě?** Zavolejte `mail.getOriginalIsTnef()` po načtení EML.

## Co je “convert msg eml”?
Převod souboru Microsoft Outlook MSG do standardního formátu EML umožňuje zprávu číst v libovolném poštovním klientu kompatibilním s RFC‑822. Převod vám také dává možnost zachovat nebo manipulovat s TNEF‑kódovanými daty během procesu.

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
Aspose.Email nabízí bezplatnou zkušební verzi, ale pro neomezené použití je vyžadována licencovaná verze.

- **Bezplatná zkušební verze:** Stáhněte dočasnou licenci [zde](https://releases.aspose.com/email/java/).  
- **Koupit:** Pro zakoupení licence navštivte [stránku nákupu](https://purchase.aspose.com/buy).

Initialize the license in your Java code:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## Průvodce implementací

### Přidání nové přílohy do hlavní zprávy obsahující TNEF
**Jak přidat přílohu:** Načtěte EML, přidejte soubor a poté uložte.

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

### Vytvoření EML s podporou TNEF z MSG
**Jak převést msg na eml:** Nastavte `convertAsTnef` na `true`.

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

## Praktické aplikace
1. **Archivace e‑mailů:** Zachovat každou přílohu – včetně TNEF‑kódovaných – pro audity souladu.  
2. **Firemní migrace:** Převést staré soubory MSG na EML, aby mohly být importovány do moderních poštovních serverů.  
3. **Zákaznická podpora:** Automaticky detekovat TNEF data, když uživatelé přeposílají zprávy mezi Outlook a webovými poštovními klienty.

## Úvahy o výkonu
- **Správa zdrojů:** Zabalte souborové streamy do try‑with‑resources, aby se rychle uvolnily handly.  
- **Velké přílohy:** Zpracovávejte velké soubory po částech nebo je streamujte přímo, aby se předešlo vysoké spotřebě paměti.  
- **Monitorování:** Použijte nástroje pro profilování Javy ke sledování spotřeby haldy při práci s mnoha přílohami.

## Závěr
Podle výše uvedených kroků můžete **convert msg eml**, přidat novou přílohu, uložit e‑mailovou přílohu a spolehlivě pracovat s TNEF daty pomocí Aspose.Email pro Java. Knihovna abstrahuje nízkoúrovňové zpracování MIME, což vám umožní soustředit se na obchodní logiku. Pro podrobnější průzkum si prohlédněte oficiální [Aspose dokumentaci](https://reference.aspose.com/email/java/) nebo experimentujte s dalšími možnostmi převodu.

## Často kladené otázky
**Q1: Co je soubor TNEF?**  
A1: TNEF znamená Transport Neutral Encapsulation Format a používá jej Microsoft Outlook k zachování formátování rich‑textu při odesílání e‑mailů jako příloh.

**Q2: Mohu používat Aspose.Email bez zakoupení licence?**  
A2: Ano, můžete začít s bezplatnou zkušební verzí. Nicméně zkušební verze ukládá určitá omezení, která mohou ovlivnit plnohodnotné používání.

**Q3: Je možné převádět mezi všemi e‑mailovými formáty pomocí Aspose.Email?**  
A3: Aspose.Email podporuje převod mezi většinou populárních formátů – včetně EML, MSG a MHTML – ale ověřte konkrétní podporu formátů v [dokumentaci](https://reference.aspose.com/email/java/).

**Q4: Jak řešit chyby „soubor nenalezen“ s Aspose.Email?**  
A4: Dvakrát zkontrolujte, že cesty k souborům, které předáváte API, jsou správné, že soubory existují a že proces má oprávnění čtení/zápisu do těchto adresářů.

**Q5: Jaký je nejlepší způsob, jak zacházet s velkými přílohami pomocí Aspose.Email?**  
A5: Zpracovávejte přílohy v menších streamech nebo částech a vždy je rychle uzavírejte. Tím se snižuje zatížení paměti a předchází se `OutOfMemoryError`.

## Často kladené otázky (další)

**Q: Odstraňuje Aspose.Email automaticky TNEF při převodu na EML?**  
A: Ne. Ve výchozím nastavení jsou TNEF data zachována. Toto chování můžete ovládat pomocí `MailConversionOptions.setConvertAsTnef`.

**Q: Mohu programově vypsat všechny přílohy ve načtené zprávě?**  
A: Ano – použijte `mail.getAttachments()`, který vrací kolekci, kterou můžete iterovat.

**Q: Existuje způsob, jak převést dávku souborů MSG na EML v jednom běhu?**  
A: Rozhodně. Procházejte soubory, aplikujte kroky převodu uvedené výše a uložte každý výsledek.


**Související zdroje:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Stáhněte dočasnou licenci [zde](https://releases.aspose.com/email/java/).
---

**Poslední aktualizace:** 2025-12-13  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}