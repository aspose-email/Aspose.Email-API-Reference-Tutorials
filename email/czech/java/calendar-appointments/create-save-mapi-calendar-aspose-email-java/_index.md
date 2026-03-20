---
date: '2026-03-20'
description: Naučte se, jak exportovat kalendář Outlooku do PST pomocí Aspose.Email
  pro Javu – vytvořte položky kalendáře MAPI, nastavte opakování, přidejte účastníky
  a uložte do PST.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Export kalendáře Outlook PST pomocí Aspose.Email – Java
url: /cs/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export kalendáře Outlook PST pomocí Aspose.Email – Java

## Úvod

Hledáte způsob, jak zefektivnit automatizaci kalendáře ve svých Java aplikacích a potřebujete **exportovat Outlook kalendář PST** soubory? S **Aspose.Email for Java** můžete **vytvářet MAPI kalendářové Java** položky, definovat vzory opakování, přidávat účastníky a **uložit kalendář do PST** pomocí několika řádků kódu. Tento tutoriál vás provede celým procesem – od nastavení knihovny až po vytvoření plně funkční položky kalendáře připravené k distribuci.

### Co se naučíte
- Jak pomocí Aspose.Email **vytvářet MAPI kalendářové Java** události.  
- Konfigurace denních, týdenních nebo vlastních vzorů opakování.  
- Přidávání příjemců (organizátorů, účastníků) do vašich kalendářových pozvánek.  
- Uložení kalendářové položky pomocí **uložení kalendáře do PST** pro kompatibilitu s Outlookem.  
- Jak **automatizovat plánování schůzek** pomocí znovupoužitelného kódu.

## Rychlé odpovědi
- **Která knihovna?** Aspose.Email for Java  
- **Hlavní cíl?** Export Outlook kalendáře PST a **uložit kalendář do PST**  
- **Požadavky?** Java 8+, Maven, licence Aspose.Email  
- **Typický čas implementace?** 10‑15 minut pro základní událost  
- **Mohu přidat opakování?** Ano – denní, týdenní, měsíční atd.

## Export Outlook kalendáře PST

V této sekci se zaměříme na kompletní tok, který vám umožní **exportovat Outlook kalendář PST** soubory. Po vytvoření MAPI kalendářového objektu je posledním krokem uložit jej do PST souboru, který Outlook může číst přímo.

## Proč použít Aspose.Email pro automatizaci kalendáře?

- **Plná kompatibilita s Outlookem** – generované položky fungují v Outlooku, OWA a mobilních klientech.  
- **Bohatá podpora opakování** – denní, týdenní, měsíční a vlastní vzory přímo z krabice.  
- **Žádné externí závislosti** – čistá Java knihovna, není vyžadována COM interop.  
- **Vysoký výkon** – efektivní zpracování velkých PST souborů a hromadných operací.  
- **Automatizovat plánování schůzek** – vložte tuto logiku do dávkových úloh nebo webových služeb a automaticky vytvořte stovky pozvánek.

## Požadavky

Než začneme, ujistěte se, že máte:

### Požadované knihovny
- **Aspose.Email for Java**: Verze 25.4 nebo novější.

### Požadavky na nastavení prostředí
- Java IDE, např. IntelliJ IDEA nebo Eclipse.  
- Maven nainstalovaný pro správu závislostí.

### Předpoklady znalostí
- Základní dovednosti programování v Javě.  
- Znalost objektově orientovaných konceptů.

## Nastavení Aspose.Email pro Java

Přidejte Maven závislost Aspose.Email do vašeho `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence

Aspose.Email nabízí bezplatnou zkušební verzi, ale licence odemkne všechny funkce:

- **Bezplatná zkušební verze**: Testujte bez omezení po dobu 30 dní.  
- **Dočasná licence**: Požádejte přes [web Aspose](https://purchase.aspose.com/temporary-license/), pokud potřebujete více času.  
- **Koupit**: Zakupte trvalou licenci na [stránce nákupu](https://purchase.aspose.com/buy).

### Základní inicializace

Po přidání závislosti inicializujte knihovnu pomocí souboru licence:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Průvodce implementací

Nyní, když máte vše nastavené, vytvořme **MAPI kalendář Java** a **uložme kalendář do PST**.

### Vytvoření MAPI kalendáře s opakováním

#### Přehled

Vytvoříme kalendářovou událost, aplikujeme denní opakování, přidáme účastníky a nakonec ji uložíme do PST souboru.

#### Krok za krokem implementace

1. **Inicializace data a vzoru opakování**  

   Nejprve definujte čas zahájení a nastavte denní opakování:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Vysvětlení*: `MapiCalendarEventRecurrence` obsahuje podrobnosti o opakování; vybereme denní vzor pomocí `MapiCalendarDailyRecurrencePattern`.

2. **Nastavení příjemců**  

   Přidejte osoby, které by měly obdržet pozvánku na schůzku:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Vysvětlení*: `MapiRecipientCollection` ukládá každého účastníka; `MAPI_TO` je označuje jako hlavní příjemce.

3. **Vytvoření MAPI kalendářové položky**  

   Sestavte kalendářový objekt se všemi požadovanými údaji:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Vysvětlení*: Konstruktor očekává organizátora, předmět, místo, časy začátku/konce, popis, seznam příjemců a opakování.

4. **Uložení do PST souboru**  

   Nakonec uložte kalendář pomocí **uložení kalendáře do PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Vysvětlení*: `PersonalStorage.create` vytvoří nový PST soubor a `addMapiMessageItem` vloží kalendářovou položku do složky „Calendar“.

### Tipy pro řešení problémů
- Ověřte cestu k licenci; neplatná licence omezí funkčnost.  
- Ujistěte se, že e‑mailové adresy příjemců jsou správně formátovány, aby nedošlo k selhání pozvánek.  
- Po operacích zavřete PST (`pst.dispose()`), aby se uvolnily souborové handle.

## Praktické aplikace

Zde jsou běžné scénáře, kde **vytváření MAPI kalendář Java** a **ukládání kalendáře do PST** vyniká:

1. **Automatizované plánování schůzek** – Generujte opakující se pozvánky na schůzky pro projektové týmy bez ručního úsilí.  
2. **Platformy pro správu událostí** – Exportujte konference jako Outlook‑kompatibilní kalendářové položky.  
3. **Integrace CRM** – Synchronizujte schůzky zákazníků z CRM systému přímo do Outlooku pomocí PST souborů.

## Úvahy o výkonu

- **Správa zdrojů**: Po použití uvolněte objekty `PersonalStorage`, aby nedocházelo k zamykání souborů.  
- **Dávkové zpracování**: Pro velké objemy zpracovávejte kalendářové položky asynchronně nebo po částech, aby byl nízký odběr paměti.  

## Závěr

Nyní jste se naučili, jak **exportovat Outlook kalendář PST** vytvořením MAPI kalendářových Java objektů, konfigurací opakování, přidáním účastníků a **uložením kalendáře do PST** pomocí Aspose.Email. Tento přístup umožňuje vašim Java aplikacím automatizovat složité pracovní postupy plánování s kompatibilitou Outlooku.

Pro podrobnější průzkum si prohlédněte oficiální [dokumentaci](https://reference.aspose.com/email/java/).

## Často kladené otázky

### Otázka: Mohu vytvořit týdenní vzory opakování?
- **Odpověď**: Ano! Použijte `MapiCalendarWeeklyRecurrencePattern` k definování týdenních opakování.

### Otázka: Jak zacházet s výjimkami v opakování události?
- **Odpověď**: Zavolejte `setExceptions()` na objekt opakování a určete data, která se liší od vzoru.

### Otázka: Je možné aktualizovat existující kalendářovou položku?
- **Odpověď**: Rozhodně. Načtěte položku z PST, upravte její vlastnosti a uložte ji zpět.

### Otázka: Mohu šifrovat PST soubor?
- **Odpověď**: Ano, Aspose.Email vám umožní nastavit heslo na `PersonalStorage` při vytváření PST.

### Otázka: Co když potřebuji přidat přílohy k události v kalendáři?
- **Odpověď**: Použijte `calendar.getAttachments().addFileAttachment("path/to/file")` před uložením.

## Zdroje

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-03-20  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}