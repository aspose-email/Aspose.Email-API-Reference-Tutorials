---
date: '2026-01-17'
description: Naučte se, jak převést MSG na MHT pomocí Aspose.Email pro Javu. Tento
  krok‑za‑krokem tutoriál pokrývá načítání, ukládání a přizpůsobování šablon pro reálnou
  konverzi e‑mailů.
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 'Jak převést MSG na MHT pomocí Aspose.Email pro Javu: komplexní průvodce'
url: /cs/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Převod MSG na MHT pomocí Aspose.Email pro Java: Komplexní průvodce

## Úvod

Převod **MSG na MHT** je častý požadavek, když potřebujete archivovat nebo zobrazit Outlook zprávy ve web‑přátelském formátu. V tomto tutoriálu uvidíte, jak Aspose.Email pro Java usnadňuje převod – načtete soubor MAPI (MSG), upravíte výstup pomocí vlastních HTML šablon a uložíte jej jako soubor MHT připravený pro prohlížeče nebo archivní systémy.

**Co se naučíte:**
- Jak efektivně načíst a parsovat MSG soubory.  
- Jak nakonfigurovat `MhtSaveOptions` pro optimální výstup MHT.  
- Jak použít vlastní šablony ke zlepšení čitelnosti.  
- Reálné scénáře, kde převod MSG na MHT přináší hodnotu.

Připravíme prostředí a ponoříme se do kódu.

## Rychlé odpovědi
- **Co znamená „převod MSG na MHT“?** Převádí Outlook `.msg` soubory do web‑kompatibilního formátu `.mht` (MHTML).  
- **Která knihovna se používá?** Aspose.Email pro Java (aspose email tutorial).  
- **Potřebuji licenci?** Bezplatná 30‑denní zkušební verze stačí pro hodnocení; licence je vyžadována pro produkci.  
- **Podporovaná verze Javy?** Java 16 nebo novější (classifier `jdk16`).  
- **Typický případ použití?** Archivace e‑mailů pro soulad s předpisy nebo jejich zobrazování v prohlížečích bez Outlooku.

## Co je „převod MSG na MHT“?
Proces převodu načte binární Outlook zprávu (`.msg`) a přepíše její obsah, přílohy a metadata do jediného HTML‑založeného souboru MHTML (`.mht`). Tento jednosouborový formát zachovává původní rozvržení a lze jej zobrazit v libovolném moderním prohlížeči.

## Proč použít Aspose.Email pro Java?
- **Kompletní API:** Zpracovává všechny MAPI vlastnosti, přílohy i vložené objekty.  
- **Bez závislosti na Outlooku:** Funguje v jakémkoli server‑side Java prostředí.  
- **Přizpůsobitelné šablony:** Upravte HTML výstup tak, aby odpovídal vaší značce nebo standardům reportování.  
- **Vysoký výkon:** Optimalizováno pro velké dávky a asynchronní zpracování.

## Předpoklady

- **Aspose.Email knihovna:** Verze 25.4 nebo novější (classifier `jdk16`).  
- **Vývojové prostředí Javy:** Maven nainstalovaný pro správu závislostí.  
- **Základní znalost Javy:** Zkušenosti se souborovým I/O a Maven projekty.

## Nastavení Aspose.Email pro Java

Pro přidání Aspose.Email do Maven projektu zahrňte následující závislost:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence (aspose email tutorial)

Aspose.Email je komerční produkt, ale můžete začít s **bezplatnou zkušební verzí**:

- **Bezplatná zkušební verze:** Plná funkčnost po 30 dnů.  
- **Dočasná licence:** Prodloužení zkušebního období podle potřeby.  
- **Koupě:** Získání trvalé licence pro produkční použití.

### Základní inicializace

Po přidání Maven závislosti inicializujte knihovnu ve vašem Java kódu:

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## Jak převést MSG na MHT pomocí Aspose.Email pro Java

### Načtení MSG souboru

**Krok 1 – Import požadované třídy**

```java
import com.aspose.email.MapiMessage;
```

**Krok 2 – Načtení zprávy z disku**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

Metoda `MapiMessage.fromFile()` načte soubor `.msg` a vytvoří manipulovatelný objekt `MapiMessage`.

### Konfigurace MHT možností uložení

**Krok 1 – Import tříd pro nastavení uložení**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**Krok 2 – Nastavení možností**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` zajistí zahrnutí polí specifických pro úkol, zatímco `WriteHeader` přidá standardní e‑mailové hlavičky do MHT výstupu.

### Definice vlastních HTML šablon (volitelné)

**Krok 1 – Import výčtu šablon**

```java
import com.aspose.email.MhtTemplateName;
```

**Krok 2 – Přizpůsobení šablon**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

Tyto šablony vám umožní řídit, jak se každá vlastnost úkolu zobrazí ve výsledném MHT souboru, což usnadní čtení koncovým uživatelům.

### Uložení zprávy jako MHT souboru

**Krok 1 – Definice výstupního adresáře**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**Krok 2 – Provedení operace uložení**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

Metoda `save` zapíše přizpůsobený MHT soubor na disk. Před spuštěním kódu ověřte, že cesta `outputDir` existuje.

## Praktické aplikace (Proč převádět MSG na MHT?)

- **Archivace:** Uložte e‑maily v jediném přenosném formátu, který prohlížeče zobrazí bez Outlooku.  
- **Migrace:** Přesuňte staré Outlook archivy na web‑založené e‑mailové platformy.  
- **Reportování a analytika:** Parsujte MHT soubory pomocí HTML parserů pro extrakci dat a business intelligence.  
- **Právní soulad:** Zachovejte původní obsah zprávy a metadata v formátu odolném proti manipulaci.

## Úvahy o výkonu

- **Dávkové zpracování:** Při práci s tisíci MSG soubory je vhodné je zpracovávat po dávkách, aby nedošlo k výkyvům paměti.  
- **Asynchronní provádění:** Využijte `CompletableFuture` nebo executor služby Javy pro paralelní převod souborů.  
- **Uvolňování zdrojů:** Explicitně zavírejte streamy, pokud otevřete vlastní streamy mimo API Aspose.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| **NullPointerException při `msg.save`** | Výstupní adresář neexistuje | Vytvořte adresář nebo použijte `Files.createDirectories(Paths.get(outputDir));` |
| **Chybějící přílohy v MHT** | `MhtSaveOptions` není nastaveno na vložení zdrojů | Použijte `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **Nesprávný formát data** | Nastavení locale se liší | Upravit `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## Často kladené otázky

**Q: Jaký je rozdíl mezi MSG a MHT?**  
A: MSG je proprietární binární formát Outlooku, který ukládá e‑mail, přílohy a metadata. MHT (MHTML) je HTML‑založený jednosouborový formát, který balí tělo e‑mailu, obrázky a CSS, takže jej lze zobrazit v libovolném prohlížeči.

**Q: Mohu převádět i jiné MAPI položky, jako jsou schůzky nebo kontakty?**  
A: Ano. Aspose.Email podporuje převod schůzek, kontaktů i úkolů do MHT pomocí odpovídajících `Mapi*` tříd a úpravou názvů šablon.

**Q: Potřebuji pro převod internetové připojení?**  
A: Ne. Veškeré zpracování probíhá lokálně v Java runtime; pouze kontrola licence může jednou kontaktovat server Aspose.

**Q: Je převod thread‑safe?**  
A: API je thread‑safe pro operace jen pro čtení. Při souběžném převodu mnoha souborů vytvořte samostatné `MapiMessage` instance pro každý vlákno.

**Q: Jak velký MSG soubor Aspose.Email zvládne?**  
A: Knihovna dokáže zpracovat soubory až na několik stovek megabajtů, ale je třeba sledovat velikost heapu JVM a případně streamovat velké přílohy.

## Závěr

Nyní máte kompletní, připravený workflow pro **převod MSG na MHT** pomocí Aspose.Email pro Java. Využitím vlastních šablon můžete přizpůsobit HTML výstup tak, aby odpovídal značce nebo standardům vaší organizace, zatímco knihovna se postará o těžkou práci s binárním formátem Outlooku.

**Další kroky:**  
- Experimentujte s různými hodnotami `MhtTemplateName` pro stylování dalších typů MAPI položek.  
- Integrujte převod do dávkového úkolu nebo REST služby pro on‑demand zpracování.  
- Prozkoumejte další funkce Aspose.Email, jako je práce s PST, odesílání e‑mailů a parsování MIME.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-17  
**Testováno s:** Aspose.Email pro Java 25.4 (classifier `jdk16`)  
**Autor:** Aspose