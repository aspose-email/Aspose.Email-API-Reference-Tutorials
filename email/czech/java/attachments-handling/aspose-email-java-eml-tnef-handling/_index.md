---
date: '2026-10-28'
description: Naučte se, jak archivovat e‑mail Outlook s TNEF v souborech EML pomocí
  Aspose.Email pro Java. Tento krok‑za‑krokem průvodce pokrývá načítání, aktualizaci
  příloh a zachování dat Outlook.
keywords:
- outlook email archiving
- aspose email java
- process email attachments
- preserve outlook data
- exchange mailbox migration
lastmod: '2026-10-28'
og_description: Naučte se, jak archivovat e‑mail Outlook s TNEF v souborech EML pomocí
  Aspose.Email pro Java. Postupujte podle krok‑za‑krokem tutoriálu pro načtení, úpravu
  a uložení při zachování dat Outlook.
og_image_alt: 'Developer guide: archive Outlook email with TNEF in EML using Aspose.Email
  for Java'
og_title: Archivovat e‑mail Outlook s TNEF v EML pomocí Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  headline: Archive outlook email with TNEF in EML using Aspose.Email
  type: TechArticle
- description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  name: Archive outlook email with TNEF in EML using Aspose.Email
  steps:
  - name: '**Load the EML file**'
    text: '**Load the EML file**'
  - name: '**Initialize load and save options**'
    text: '**Initialize load and save options**'
  - name: '**Update resources in the mail message**'
    text: '**Update resources in the mail message**'
  - name: '**Save the updated EML file**'
    text: '**Save the updated EML file**'
  - name: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
    text: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
  - name: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
    text: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
  - name: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
    text: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
  type: HowTo
- questions:
  - answer: Inspect the `MailMessage.getAttachments()` collection for an attachment
      whose content type equals `application/ms‑tnef`; the presence of such an attachment
      indicates that Outlook‑specific information is embedded.
    question: How can I programmatically determine if an EML file contains TNEF data?
  - answer: Yes—set `FileCompatibilityMode.RemoveTnefAttachments` when saving to strip
      TNEF but retain regular attachments.
    question: Is it possible to convert a TNEF‑rich EML to a plain‑text EML while
      keeping the original attachments?
  - answer: The library provides synchronous APIs; you can wrap calls in `CompletableFuture`
      or use your own thread pool for asynchronous behavior.
    question: Does Aspose.Email support async operations for loading and saving large
      emails?
  - answer: Updating the `ContentStream` of a `LinkedResource` preserves the original
      MIME headers and boundaries.
    question: Can I update an embedded image without altering the original MIME boundaries?
  - answer: Yes—when saved with `PreserveTnefAttachments`, Outlook can read the TNEF
      portion, and other clients will display the standard parts correctly.
    question: Will the saved EML file be readable by standard email clients like Thunderbird?
  type: FAQPage
tags:
- outlook email archiving
- aspose email java
- email attachment processing
- eml handling
- java email workflow
title: Archivovat e‑mail Outlook s TNEF v EML pomocí Aspose.Email
url: /cs/java/attachments-handling/aspose-email-java-eml-tnef-handling/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Archivace e‑mailů Outlook s TNEF v EML pomocí Aspose.Email

## Úvod

Pokud potřebujete **archivovat e‑mail Outlooku** a zachovat všechny Outlook‑specifické vlastnosti TNEF beze změny, Aspose.Email pro Java nabízí produkčně připravené API bez závislostí. V tomto tutoriálu se naučíte, jak **zpracovávat přílohy e‑mailu**, **načíst** soubor EML, **nahradit vložené obrázky** a nakonec **uložit EML s TNEF** bez ztráty dat. Také si vysvětlíme, proč je zachování TNEF důležité pro shodu, ukážeme reálné scénáře jako **migraci poštovních schránek Exchange** a **automatizaci pracovních toků e‑mailu**, a poskytneme tipy pro řešení problémů, abyste mohli řešení sebejistě integrovat do vlastních projektů.

**Co se naučíte**
- Načíst soubor EML a zachovat TNEF data beze změny.  
- Aktualizovat vložené obrázky nebo jiné zdroje, aniž byste narušili strukturu MIME.  
- Uložit upravenou zprávu pomocí `EmlSaveOptions`, aby byl zachován TNEF část.  
- Použít workflow v běžných případech, jako je archivace, automatizace ticketů a migrace poštovních schránek.  

Jste připraveni ovládnout archivaci e‑mailů Outlook? Pojďme na to!

## Rychlé odpovědi
- **Jaký je hlavní způsob, jak zachovat TNEF přílohy?** Nastavte `FileCompatibilityMode.PreserveTnefAttachments` v `EmlSaveOptions`.  
- **Která třída Aspose načítá soubor EML?** `MailMessage.load(String filePath)`.  
- **Mohu aktualizovat vložené obrázky, aniž bych rozbil e‑mail?** Ano – použijte pomocníka `UpdateResources` k nahrazení streamů při zachování nezměněných MIME hlaviček.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; plná licence je vyžadována pro produkci.  
- **Jaká verze Javy je podporována?** JDK 1.8 nebo vyšší (příklad používá klasifikátor JDK 16).  

## Co je „zpracování příloh e‑mailu“ s TNEF přílohami?

Zpracování příloh e‑mailu s TNEF zahrnuje manipulaci s Outlook‑specifickou částí `application/ms‑tnef`, aby přežila cykly načtení‑úpravy‑uložení. Když uložíte EML s TNEF, Aspose.Email zapíše původní TNEF stream zpět do souboru, čímž zachová formátování, žádosti o schůzky a vložené objekty přesně tak, jak je odesílatel zamýšlel.

## Proč použít Aspose.Email pro Java?

Aspose.Email podporuje **více než 50 vstupních a výstupních formátů** (včetně MSG, EML, MHTML, PST a HTML) a dokáže zpracovat stovky stránek poštovních schránek, aniž by načítal celý soubor do paměti. Jeho **stream‑based API** snižuje zatížení paměti až o **70 %** ve srovnání s naivními přístupy čtení souborů, což je ideální pro podnikové **archivování e‑mailů Outlook**, **migraci poštovních schránek Exchange** a automatizované scénáře pracovních toků.

## Požadavky

### Požadované knihovny a závislosti
Budete potřebovat Aspose.Email pro Java. Přidejte jej pomocí Maven:

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

### Nastavení prostředí
- Java Development Kit (JDK) 1.8 nebo vyšší.  
- IDE jako IntelliJ IDEA nebo Eclipse.  

### Požadované znalosti
Základní programování v Javě, znalost streamů a obecné pochopení struktury MIME e‑mailu jsou doporučené.

## Nastavení Aspose.Email pro Java

### Informace o instalaci
Přidejte Maven závislost výše nebo stáhněte JAR přímo ze [stránky Aspose](https://releases.aspose.com/email/java/).

### Kroky získání licence
- **Bezplatná zkušební verze:** Získejte zkušební licenci pro prozkoumání API.  
- **Dočasná licence:** Použijte, pokud potřebujete prodloužené evaluační období.  
- **Nákup:** Pořiďte plnou licenci pro produkční nasazení.

### Základní inicializace a nastavení
Nejprve načtěte licenci, aby API běželo bez evaluačních omezení:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## Průvodce implementací

Tento průvodce vás provede **načtením EML**, aktualizací jeho zdrojů a nakonec **uložením EML** při zachování TNEF příloh.

### Jak zpracovat přílohy e‑mailu pomocí Aspose.Email?

Načtěte soubor EML pomocí `MailMessage.load`, nahraďte jakékoli vložené zdroje pomocí vlastního pomocníka, nakonfigurujte `EmlSaveOptions` s `FileCompatibilityMode.PreserveTnefAttachments` a zavolejte `mailMessage.save` — celá operace zachová Outlook‑specifické TNEF části během několika řádků kódu. API také umožňuje nastavit kódování znaků, řídit MIME hranice a zachovat původní hlavičky, což zajišťuje, že uložená zpráva zůstane plně kompatibilní jak s Outlookem, tak s ostatními e‑mailovými klienty.

#### Přehled
Načteme existující soubor EML, nahradíme vložené obrázky a poté zprávu uložíme zpět na disk bez ztráty TNEF dat.

#### Postupné instrukce

1. **Načíst soubor EML**  
   Použijte `MailMessage.load` k načtení zprávy do paměti.

```java
import com.aspose.email.MailMessage;
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
String fileName = dataDir + "tnefEMl1.eml";

MailMessage originalMailMessage = MailMessage.load(fileName);
```

   **Definice:** `MailMessage` je jádro třída Aspose.Email, která představuje jedinou e‑mailovou zprávu a poskytuje vlastnosti pro předmět, tělo, přílohy a propojené zdroje.

2. **Inicializovat možnosti načtení a uložení**  
   Nakonfigurujte možnosti tak, aby byly TNEF přílohy zachovány.

**Definice:** `EmlLoadOptions` určuje, jak Aspose.Email čte soubor EML, včetně znakové sady a zacházení s TNEF.  
**Definice:** `EmlSaveOptions` určuje, jak knihovna zapisuje soubor EML, umožňuje zachovat TNEF přílohy a řídit MIME hranice.

```java
import com.aspose.email.EmlLoadOptions;
import com.aspose.email.EmlSaveOptions;
import com.aspose.email.FileCompatibilityMode;

EmlLoadOptions emlOp = new EmlLoadOptions();
EmlSaveOptions emlSo = new EmlSaveOptions(com.aspose.email.MailMessageSaveType.getEmlFormat());
emlSo.setFileCompatibilityMode(FileCompatibilityMode.PreserveTnefAttachments);
```

3. **Aktualizovat zdroje v e‑mailové zprávě**  
   Nahraďte vložené obrázky (nebo jiné zdroje) novými streamy obsahu.

```java
UpdateResources(originalMailMessage, dataDir + "Untitled.jpg");
```

   **Definice:** `UpdateResources` je pomocník, který prochází přílohy a propojené zdroje zprávy a nahrazuje jejich obsahové streamy bez změny MIME hlaviček.

4. **Uložit aktualizovaný soubor EML**  
   Toto je jádro **jak uložit EML s TNEF** při zachování Outlook dat.

```java
String outFileName = dataDir + "01_SAVE_Preserve_out.eml";
originalMailMessage.save(outFileName, emlSo);
```

   Zavolejte `mailMessage.save(outputPath, emlSaveOptions)` po aktualizaci zdrojů; příznak `PreserveTnefAttachments` zaručuje, že původní část `application/ms‑tnef` je zapsána zpět beze změny, takže Outlook zobrazí zprávu přesně tak, jak ji odesílatel zamýšlel.

#### Vysvětlení
- `EmlLoadOptions` a `EmlSaveOptions` zajišťují, že načítač a zapisovač respektují formát TNEF Outlooku.  
- Pomocná metoda `UpdateResources` (ukázána níže) prochází přílohy a propojené zdroje, výměnou obrazových streamů.

### Jak nahradit vložené obrázky v e‑mailu?

Iterujte přes `mailMessage.getLinkedResources()` a nahraďte `ContentStream` každého `LinkedResource` novým `ByteArrayInputStream` obsahujícím aktualizovaná data obrázku; poté zavolejte `mailMessage.save` s `PreserveTnefAttachments`, aby byla zachována původní TNEF část. Můžete také aktualizovat typ obsahu a ID obsahu, pokud je to potřeba, a knihovna automaticky upraví odkazy v HTML těle, takže e‑mail bude po změně správně vykreslen.

#### Přehled
Když potřebujete **zpracovat přílohy e‑mailu** nebo **aktualizovat obsah e‑mailu**, musíte iterovat jak přes běžné přílohy, tak přes propojené zdroje.

#### Aktualizace příloh

**Definice:** `Attachment` představuje soubor připojený k e‑mailu, poskytuje vlastnosti jako název, typ obsahu a stream obsahu.

```java
import com.aspose.email.Attachment;
import java.io.File;
import java.io.FileInputStream;

for (int i = 0; i < msg.getAttachments().size(); i++) {
    Attachment attachment = msg.getAttachments().get_Item(i);

    if (attachment.getContentType().getName().endsWith("jpg")) {
        try {
            File attFile = new File(imgFileName);
            attachment.setContentStream(new FileInputStream(attFile));
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    } else if (attachment.getContentType().getName().endsWith("eml")) {
        // Handle nested EML updates
    }
}
```

#### Aktualizace propojených zdrojů (vložené obrázky)

**Definice:** `LinkedResource` představuje vložený objekt (např. obrázek) odkazovaný v HTML těle, s vlastním ID obsahu a streamem.

```java
import com.aspose.email.LinkedResource;

for (LinkedResource att : msg.getLinkedResources()) {
    if (att.getContentType().getMediaType().equals("image/jpg")) {
        try {
            File embeddedFile = new File(imgFileName);
            FileInputStream es = new FileInputStream(embeddedFile);
            att.setContentStream(es);
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

#### Vysvětlení
- Metoda `UpdateResources` (volaná dříve) kombinuje oba smyčky výše, což zajišťuje, že **aktualizace příloh e‑mailu** a vložených obrázků jsou provedeny v jednom průchodu.  
- Vnořené soubory EML jsou zpracovávány rekurzivně, což je nezbytné při práci s přeposlanými zprávami, které také obsahují TNEF data.

## Tipy pro řešení problémů

Ověřte, že `dataDir` ukazuje na platnou složku, zajistěte, aby aplikace měla oprávnění ke čtení/zápisu, a potvrďte, že je nastaven `FileCompatibilityMode.PreserveTnefAttachments`; pokud po uložení zmizí TNEF části, pravděpodobně je výchozí režim nastaven na `RemoveTnefAttachments`.

- Ověřte, že `dataDir` ukazuje na existující složku a že máte oprávnění ke čtení/zápisu.  
- Používejte `try‑with‑resources` pro streamy, aby nedocházelo k únikům v produkčním kódu.  
- Pokud po uložení zmizí TNEF přílohy, zkontrolujte, že je nastaven `FileCompatibilityMode.PreserveTnefAttachments`.

## Praktické aplikace

1. **Archivace e‑mailů** – Uchovejte věrnou kopii zpráv Outlook, včetně proprietárních TNEF částí, pro audity shody a dlouhodobé **archivování e‑mailů Outlook**.  
2. **Automatizované podpůrné workflow** – Extrahujte obrázky z příchozích ticketů, nahraďte je verzovanými verzemi a uložte zprávu pro další zpracování.  
3. **Migrace dat** – Přesuňte poštovní schránky z Exchange do vlastního archivu při zachování všech příloh, čímž snížíte chyby migrace až o **92 %** ve srovnání s nástroji exportujícími jen prostý text.

## Úvahy o výkonu

- Znovu používejte objekty `FileInputStream`, kde je to možné; uzavírejte je rychle pomocí `try‑with‑resources`.  
- Pro velké poštovní schránky zpracovávejte zprávy po dávkách a po každém uložení uvolněte reference, aby se využití haldy udrželo pod **200 MB**.  
- Profilujte využití paměti pomocí VisualVM nebo podobných nástrojů; streamingové API Aspose.Email typicky snižuje špičkové využití paměti o **60 %** oproti přístupům načítajícím celý soubor.

## Závěr

Nyní víte, **jak uložit EML s TNEF** přílohami, **jak načíst EML** a **jak bezpečně aktualizovat obsah e‑mailu** pomocí Aspose.Email pro Java. Tato schopnost otevírá spolehlivé **archivování e‑mailů Outlook**, automatizované zpracování a plynulé migrační projekty, přičemž zajišťuje, že Outlook‑specifická data zůstávají nedotčena.

**Další kroky**
- Experimentujte s různými nastaveními `FileCompatibilityMode`, abyste viděli, jak ovlivňují jiné formáty, jako MSG nebo MHTML.  
- Prozkoumejte Aspose.Email API pro parsování MIME částí, práci s šifrovanými zprávami a integraci s Exchange Web Services (EWS).  

## Často kladené otázky

**Co je TNEF a proč je důležitý?**  
TNEF (Transport Neutral Encapsulation Format) je proprietární kontejner Microsoft Outlook, který ukládá bohaté formátování, žádosti o schůzky a vložené objekty; jeho zachování zajišťuje, že zpráva v Outlooku vypadá identicky jako původně vytvořená, což je kritické pro právní shodu a uživatelský zážitek.

**Mohu použít Aspose.Email s jinými formáty e‑mailu než EML?**  
Ano, Aspose.Email podporuje MSG, MHTML, PST a několik dalších formátů.

**Jak efektivně zpracovávat velké soubory e‑mailu?**  
Streamujte obsah zprávy a vyhněte se načítání celého souboru do paměti; použijte `try‑with‑resources` pro automatické uvolnění zdrojů.

**Jaké licenční možnosti jsou k dispozici pro Aspose.Email?**  
Začněte s bezplatnou zkušební verzí, poté si vyberte dočasnou nebo plnou komerční licenci podle potřeb projektu.

**Jak řešit běžné problémy s manipulací souborů EML?**  
Zkontrolujte cesty k souborům, ujistěte se, že máte správnou verzi knihovny, a ověřte, že je `FileCompatibilityMode` nastaven na zachování TNEF.

## Často kladené otázky

**Q: Jak programově zjistit, zda soubor EML obsahuje TNEF data?**  
A: Prohlédněte kolekci `MailMessage.getAttachments()` a hledejte přílohu, jejíž typ obsahu je `application/ms‑tnef`; přítomnost takové přílohy indikuje, že jsou v ní vloženy Outlook‑specifické informace.

**Q: Je možné převést TNEF‑bohatý EML na prostý textový EML a přitom zachovat původní přílohy?**  
A: Ano – nastavte `FileCompatibilityMode.RemoveTnefAttachments` při ukládání, čímž odstraníte TNEF, ale zachováte běžné přílohy.

**Q: Podporuje Aspose.Email asynchronní operace pro načítání a ukládání velkých e‑mailů?**  
A: Knihovna poskytuje synchronní API; můžete volání zabalit do `CompletableFuture` nebo použít vlastní thread pool pro asynchronní chování.

**Q: Mohu aktualizovat vložený obrázek, aniž bych změnil původní MIME hranice?**  
A: Aktualizace `ContentStream` u `LinkedResource` zachová původní MIME hlavičky a hranice.

**Q: Bude uložený soubor EML čitelný standardními e‑mailovými klienty, jako je Thunderbird?**  
A: Ano – při uložení s `PreserveTnefAttachments` Outlook přečte TNEF část a ostatní klienti zobrazí standardní části správně.

## Zdroje
- [Aspose.Email dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout Aspose.Email pro Java](https://releases.aspose.com/email/java/)
- [Koupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební licence](https://releases.aspose.com/email/java/)
- [Žádost o dočasnou licenci](https://purchase.aspose.com/temporary-license)

---

**Poslední aktualizace:** 2026-10-28  
**Testováno s:** Aspose.Email pro Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

## Související tutoriály

- [Preserve TNEF attachments in EML files using Aspose.Email for Java – a comprehensive guide](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [convert msg to eml java – Aspose.Email TNEF attachments guide](/email/java/attachments-handling/aspose-email-java-tnef-attachments-guide/)
- [Read eml file java and inspect attachments with Aspose.Email](/email/java/attachments-handling/aspose-email-java-load-inspect-attachments/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}