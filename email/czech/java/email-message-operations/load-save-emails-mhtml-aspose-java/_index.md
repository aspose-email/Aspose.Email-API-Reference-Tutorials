---
date: '2026-02-27'
description: Naučte se načítat soubory MSG a převádět je do formátu MHTML pomocí Aspose.Email
  pro Javu, včetně nastavení vlastního časového pásma a tipů pro dávkové zpracování
  e‑mailů.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Jak načíst MSG a uložit jako MHTML pomocí Aspose.Email pro Javu
url: /cs/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak načíst MSG a uložit jako MHTML pomocí Aspose.Email pro Java

## Úvod

Pokud potřebujete **jak načíst msg** soubory, upravit jejich časová razítka a poté **převést msg na mhtml**, jste na správném místě. V tomto tutoriálu vás provedeme načtením e‑mailu ve formátu `.msg`, aplikací vlastního posunu časové zóny a uložením výsledku jako archiv MHTML – vše pomocí Aspose.Email pro Java. Ať už pracujete s jednou zprávou nebo s **pipeline pro dávkové zpracování e‑mailů**, tyto kroky vám poskytnou pevný základ.

**Co se naučíte**
- Jak načíst `MailMessage` ze souboru `.msg`.
- Jak nastavit vlastní časovou zónu a aktuální datum.
- Jak uložit zprávu jako MHTML s přesným formátováním.
- Tipy, jak rozšířit přístup pro dávkové scénáře.

Připraveni zefektivnit svůj e‑mailový workflow? Nejprve připravme prostředí.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Email pro Java.
- **Mohu načíst MSG a exportovat do MHTML v jednom kroku?** Ne, nejprve načtete, upravíte a pak uložíte.
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Email.
- **Je podpora časových zón?** Ano, pomocí `setTimeZoneOffset`.
- **Lze to použít v dávkovém zpracování?** Rozhodně – zabalte kroky do smyčky.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

### Požadované knihovny a závislosti
- **Aspose.Email pro Java** knihovna verze 25.4 (jdk16 classifier)
- Základní znalost Javy.
- IDE, např. IntelliJ IDEA nebo Eclipse.

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

### Kroky získání licence

Začněte s **bezplatnou zkušební verzí** nebo získáním **dočasné licence** pro vyzkoušení plných možností knihovny bez omezení. Pro dlouhodobé používání zvažte zakoupení licence:

- [Bezplatná zkušební verze](https://releases.aspose.com/email/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)

### Základní inicializace

Po přidání závislosti inicializujte licenci ve svém Java kódu:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Průvodce implementací

Rozdělíme implementaci do tří jasných funkcí.

### Funkce 1: Načtení MailMessage ze souboru

#### Přehled
Načtení souboru `.msg` vám poskytuje plný programový přístup k obsahu e‑mailu, přílohám a metadatům.

#### Krok za krokem

**Importujte požadované třídy**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Načtěte e‑mail**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` vám umožňuje řídit, jak je soubor MSG interpretován; výchozí nastavení funguje pro většinu scénářů.

### Funkce 2: Nastavení aktuálního data a vlastního posunu časové zóny

#### Přehled
Přesná časová razítka jsou nezbytná, když pracujete s uživateli v různých regionech.

**Nastavte aktuální datum**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Aplikujte vlastní posun časové zóny (např. UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Posun je vyjádřen v milisekundách, takže můžete také zadat záporné hodnoty pro zóny západně od UTC.

### Funkce 3: Uložení MailMessage jako souboru MHTML

#### Přehled
MHTML spojuje HTML obsah a vložené zdroje do jediného souboru, ideální pro archivaci nebo sdílení.

**Nastavte možnosti uložení**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Uložte e‑mail**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Výsledný soubor `.mhtml` zachovává původní formátování, obrázky a přílohy.

## Proč převádět MSG na MHTML?

Převod souborů MSG na MHTML vám poskytne web‑přátelskou, jednosouborovou reprezentaci, kterou lze otevřít v libovolném moderním prohlížeči. To je zvláště užitečné pro:

- **Právní archivaci**, kde je vyžadována věrná vizuální kopie.
- **Sdílení napříč platformami** bez nutnosti Outlooku.
- **Vkládání e‑mailů** do webových stránek nebo dokumentace.

## Tipy pro dávkové zpracování e‑mailů

Pokud potřebujete **dávkové zpracování e‑mailů**, zabalte kroky načítání, úpravy časové zóny a ukládání do smyčky, která prochází adresář s `.msg` soubory. Nezapomeňte:

1. Znovu použijte jedinou instanci `License`, abyste se vyhnuli režii.
2. Uvolněte zdroje po každé iteraci (`msg.dispose()`, pokud je to relevantní).
3. Zaznamenejte případné selhání do samostatného souboru pro pozdější kontrolu.

## Praktické aplikace

- **Archivace e‑mailů:** Uchovávejte komunikaci v přenosném formátu pro soulad s předpisy.
- **Globální plánování:** Přizpůsobte časová razítka jednotné časové zóně před odesláním upozornění.
- **Integrace do CRM:** Automaticky importujte archivované e‑maily do CRM systému jako MHTML přílohy.

## Úvahy o výkonu

- **Správa paměti:** Zpracovávejte velké dávky po částech, aby byl nízký odběr paměti.
- **Optimalizace I/O:** Používejte bufferované proudy, pokud čtete/zapisujete mnoho souborů.
- **Paralelní provádění:** Zvažte `ForkJoinPool` v Javě pro paralelní zpracování, ale zajistěte vlákno‑bezpečnost objektů Aspose.

## Závěr

Nyní víte, **jak načíst msg** soubory, aplikovat vlastní posuny časových zón a **převést msg na mhtml** pomocí Aspose.Email pro Java. Tyto techniky lze rozšířit pro **dávkové zpracování e‑mailů**, což vám poskytne robustní řešení pro archivaci, migraci a automatizaci e‑mailů.

**Další kroky**  
Prozkoumejte další funkce Aspose.Email, jako je práce s přílohami, extrakce položek kalendáře nebo odesílání SMTP, návštěvou oficiální [dokumentace](https://reference.aspose.com/email/java/).

## Často kladené otázky

**Q: Mohu načíst e‑maily z formátů jiných než .msg?**  
A: Ano, Aspose.Email podporuje EML, MSG, MHT a několik dalších formátů.

**Q: Jak mohu efektivně zpracovat velmi velké soubory e‑mailů?**  
A: Použijte streamingové API poskytované Aspose.Email pro čtení/zápis dat po částech, čímž snížíte zatížení paměti.

**Q: Je možné upravovat přílohy v MailMessage?**  
A: Rozhodně. Můžete přidávat, odstraňovat nebo nahrazovat přílohy pomocí kolekce `MailMessage.getAttachments()`.

**Q: Co když je můj posun časové zóny záporný (za UTC)?**  
A: Předávejte zápornou hodnotu v milisekundách funkci `setTimeZoneOffset`, např. `-3 * 60 * 60 * 1000` pro UTC‑3.

**Q: Mohu používat Aspose.Email v komerčních projektech?**  
A: Ano, pokud máte platnou komerční licenci.

**Q: Jak mohu zpracovat tisíce souborů MSG, aniž bych vyčerpával paměť?**  
A: Zpracovávejte soubory po dávkách, po uložení uvolněte každý `MailMessage` a zvažte použití vzoru Java `try‑with‑resources` pro automatické čištění.

---

**Poslední aktualizace:** 2026-02-27  
**Testováno s:** Aspose.Email pro Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

## Zdroje
- [Dokumentace](https://reference.aspose.com/email/java/)
- [Stáhnout knihovnu](https://releases.aspose.com/email/java/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze](https://releases.aspose.com/email/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Fórum podpory](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}