---
date: '2026-09-22'
description: Zjistěte, jak pomocí licence Aspose.Email a Maven ukládat e‑maily jako
  soubory MHT v Javě. Obsahuje nastavení, vlastní šablony a zpracování kalendářních
  událostí.
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Zjistěte, jak pomocí licence Aspose.Email a Maven ukládat e‑maily
  jako soubory MHT v Javě. Obsahuje nastavení, vlastní šablony a podporu kalendáře.
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Jak použít licenci Aspose.Email k uložení e‑mailů jako MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Jak použít licenci Aspose.Email k uložení e‑mailů jako MHT
url: /cs/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít licenci Aspose.Email k uložení e‑mailů jako MHT

## Úvod

Efektivní správa e‑mailových dat může být náročná, zejména pokud jde o sdílení a archivaci. V tomto průvodci vám ukážeme **jak uložit soubory MHT pomocí Maven Aspose.Email pro Java s licencí Aspose.Email**, abyste mohli převádět e‑maily do MHT s vlastními šablonami a zachovat kalendářní události. Získáte připravené řešení, které funguje v jakémkoli prostředí Java 16+ a splňuje licenční požadavky pro produkční použití.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Maven Aspose.Email pro Java (v25.4+).  
- **Jaký formát je vytvářen?** Soubor MHT (MHTML), který obsahuje HTML, obrázky a kalendářní data.  
- **Mohu přizpůsobit hlavičku?** Ano – použijte `MhtFormatOptions` a řetězce šablon.  
- **Potřebuji licenci?** Licence Aspose.Email je vyžadována pro produkci; pro hodnocení stačí bezplatná zkušební verze.  
- **Jaká verze Javy je požadována?** JDK 16 nebo novější.  

## Co je Maven Aspose.Email pro Java?

Maven Aspose.Email pro Java je knihovna, která poskytuje komplexní API pro vytváření, čtení, převod a manipulaci s e‑mailovými zprávami přímo z Java kódu. Podporuje více než 30 formátů e‑mailů – včetně MSG, EML a MHT – což vám umožní pracovat prakticky s jakýmkoli e‑mailovým souborem.

## Proč převádět e‑maily do MHT?

Soubory MHT vkládají všechny zdroje (HTML, obrázky, kalendářní data) do jediného souboru, což umožňuje jejich okamžité zobrazení v libovolném moderním prohlížeči bez externích souborů. Tento formát zachovává původní vzhled, podporuje opakující se kalendářní události a snižuje riziko chybějících příloh při sdílení.

## Požadavky
- **Aspose.Email pro Java** (Maven artefakt `com.aspose:aspose-email:25.4` s klasifikátorem `jdk16`).  
- **Maven** nainstalovaný a nakonfigurovaný na vašem počítači.  
- **JDK 16+** (knihovna cílí na Java 16).  
- Platný soubor **licence Aspose.Email** pro produkční použití.  
- Základní znalost Javy (práce se soubory, Maven závislosti).

## Nastavení Aspose.Email pro Java

### Maven závislost

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

Aspose nabízí bezplatnou zkušební verzi pro vyzkoušení funkcí, spolu s možnostmi zakoupení licence nebo získání dočasné licence.

1. **Bezplatná zkušební verze** – stáhněte z [Releases](https://releases.aspose.com/email/java/) a prozkoumejte funkce bez omezení.  
2. **Dočasná licence** – požádejte o plně funkční verzi prostřednictvím [Temporary License Page](https://purchase.aspose.com/temporary-license/).  
3. **Zakoupení** – získejte trvalou licenci pro dlouhodobé projekty.

### Základní inicializace

Po instalaci inicializujte knihovnu ve vaší Java aplikaci:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## Průvodce implementací

### Funkce 1: načtení MailMessage

#### Přehled

`MailMessage` je hlavní objekt Aspose.Email, který představuje e‑mail, včetně jeho hlaviček, těla, příloh a kalendářních událostí.

#### Krok za krokem

**Importujte požadované třídy**

```java
import com.aspose.email.MailMessage;
```

**Načtěte e‑mail ze souboru**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

### Funkce 2: konfigurace MhtSaveOptions

#### Přehled

`MhtSaveOptions` konfiguruje, jak Aspose.Email ukládá `MailMessage` jako soubor MHT, řízení příznaků formátu, šablon a vkládání zdrojů. Správná konfigurace vám umožní vložit hlavičky, vykreslit kalendářní události a vložit všechny obrázky.

#### Krok za krokem

**Importujte požadované třídy**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Nastavte možnosti uložení a šablony**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

### Funkce 3: uložení MailMessage jako MHT

#### Přehled

Uložení nakonfigurovaného `MailMessage` jako souboru MHT vytvoří jediný, samostatný dokument, který lze otevřít v prohlížečích nebo e‑mailových klientech. Metoda `save` respektuje dříve definované možnosti.

#### Krok za krokem

**Importujte požadované třídy**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**Uložte e‑mailovou zprávu**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

## Praktické aplikace
- **Archivace e‑mailů** – Převádějte a ukládejte důležité e‑maily do web‑přátelského formátu pro dlouhodobé uchování.  
- **Právní dokumentace** – Používejte soubory MHT jako součást právních důkazů, kde je vyžadována věrnost e‑mailu.  
- **Sdílení napříč platformami** – Sdílejte e‑maily mezi platformami bez problémů s kompatibilitou, protože MHT obsahuje vše v jednom souboru.  

Integrace s jinými systémy – například CRM nebo nástroji pro řízení projektů – může zlepšit spolupráci vložením důležitých e‑mailových dat přímo do pracovních postupů.

## Úvahy o výkonu
Aspose.Email pro Java dokáže zpracovat soubory až do 500 MB, aniž by načítal celý dokument do paměti, a typicky převádí 100‑stránkový e‑mail s vloženými obrázky za méně než 2 sekundy na standardním serveru. Pro zachování odezvy aplikace pečlivě spravujte využití paměti a kde je to možné seskupujte I/O operace.

## Časté problémy a řešení
`MhtFormatOptions` je výčtový typ, který určuje, které prvky (hlavičky, zdroje, kalendářní události) jsou zahrnuty při ukládání zprávy jako MHT.

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **NullPointerException při `msg.save`** | Nesprávná výstupní cesta | Ověřte, že `YOUR_OUTPUT_DIRECTORY` existuje a je zapisovatelný. |
| **Chybějící obrázky v MHT** | `MhtFormatOptions` není nastaveno na vkládání zdrojů | Přidejte `MhtFormatOptions.EmbedResources` do příznaku možností. |
| **Kalendářní události nejsou vykresleny** | Příznak `RenderCalendarEvent` byl vynechán | Zajistěte `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## Často kladené otázky

**Q: Jak zacházet s přílohami při ukládání e‑mailů jako MHT?**  
A: Nakonfigurujte `MhtSaveOptions` pro vložení příloh; knihovna je automaticky zahrne do balíčku MHT.

**Q: Mohu přizpůsobit hlavičky e‑mailu ve výstupním souboru MHT?**  
A: Ano – použijte `MhtFormatOptions.WriteHeader` a poskytněte vlastní řetězce šablon pro každé pole hlavičky.

**Q: Jaké jsou systémové požadavky pro používání Aspose.Email Java?**  
A: Je vyžadován JDK 16 nebo vyšší. Knihovna funguje s jakýmkoli IDE, které podporuje Maven projekty.

**Q: Je možné uložit jen konkrétní části e‑mailové zprávy?**  
A: Přestože MHT obvykle obsahuje celou zprávu, můžete před uložením upravit vlastnosti `MailMessage` a vynechat nechtěné sekce.

**Q: Jak mohu řešit problémy s načítáním nebo ukládáním e‑mailů?**  
A: Ověřte cesty k souborům, ujistěte se, že licence je správně aplikována, a konzultujte Aspose.Email [support forum](https://forum.aspose.com/c/email/10) pro podrobnější pomoc.

**Q: Podporuje knihovna převod dalších formátů (EML, MSG) na MHT?**  
A: Rozhodně. `MailMessage.load` dokáže číst EML, MSG a další podporované formáty, po kterých je můžete uložit jako MHT pomocí stejných možností.

## Zdroje
- **Dokumentace**: Pro podrobnější přehled všech funkcí navštivte [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Stáhnout**: Začněte s bezplatnou zkušební verzí stažením z [Releases](https://releases.aspose.com/email/java/).  
- **Zakoupit**: Prozkoumejte možnosti nákupu na [Official Purchase Page](https://purchase.aspose.com/buy) pro dlouhodobé používání.  
- **Bezplatná zkušební verze a dočasná licence**: Získejte přístup k úplným funkcím během bezplatné zkušební verze nebo získáte dočasnou licenci prostřednictvím těchto odkazů:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Prozkoumejte, implementujte a transformujte své zpracování e‑mailů s Aspose.Email pro Java ještě dnes!

---

**Last Updated:** 2026-09-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

## Související tutoriály

- [Mistrovství Aspose.Email pro Java: Průvodce licencí a zpracováním e‑mailů](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Jak převést MSG na MHT pomocí Aspose.Email pro Java – Průvodce krok za krokem](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Jak uložit MSG e‑maily pomocí Aspose.Email pro Java](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}