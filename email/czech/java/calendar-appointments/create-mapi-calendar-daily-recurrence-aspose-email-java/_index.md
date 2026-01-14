---
date: '2025-12-20'
description: Naučte se, jak vytvořit MAPI kalendář v Javě, spravovat denní opakovací
  vzory a zpracovávat výjimky pomocí Aspose.Email pro Javu.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Vytvořte MAPI kalendář v Javě s denním opakováním a výjimkami
url: /cs/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit MAPI kalendář v Javě s denní opakováním a výjimkami

Efektivní správa opakujících se událostí může být náročná, zejména když jsou potřeba výjimky nebo změny. V tomto tutoriálu **vytvoříte mapi calendar java** objekty, nastavíte denní vzory opakování a přidáte výjimky pomocí Aspose.Email pro Java. Naučíte se, jak automatizovat plánovací úkoly plynule ve svých aplikacích.

## Rychlé odpovědi
- **Která knihovna?** Aspose.Email pro Java  
- **Hlavní úkol?** Vytvořit MAPI kalendář s denním opakováním a výjimkami  
- **Požadovaný JDK?** Java 16 nebo vyšší  
- **Mohu k výjimkám připojit soubory?** Ano, pomocí `MapiCalendarExceptionInfo`  
- **Kde je kalendář uložen?** V souboru PST přes `PersonalStorage`

### Co je MAPI kalendář?
MAPI (Messaging Application Programming Interface) kalendář je standardní formát používaný Microsoft Outlook a dalšími e‑mailovými klienty k ukládání údajů o schůzkách. Podporuje bohatá pravidla opakování, výjimky a přílohy, což jej činí ideálním pro firemní plánování.

### Proč použít Aspose.Email pro Java?
Aspose.Email poskytuje čisté Java API, které vám umožní vytvářet, upravovat a ukládat MAPI objekty bez nutnosti Outlooku. To znamená, že můžete budovat server‑side plánovací funkce, generovat PST soubory a programově řešit složité scénáře opakování.

## Požadavky

Než začneme, ujistěte se, že máte následující nastavení:
- **Aspose.Email knihovna**: Verze 25.4 (nebo novější) – dostupná přes Maven nebo přímé stažení.  
- **Java Development Kit (JDK)**: JDK 16 nebo novější.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli jiný Java‑kompatibilní editor.

### Požadované knihovny a závislosti

Pro integraci Aspose.Email do vašeho projektu pomocí Maven přidejte následující závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Získání licence

Pro používání Aspose.Email budete potřebovat licenci:
- **Bezplatná zkušební verze** – prozkoumejte všechny funkce bez nákladů.  
- **Dočasná licence** – požádejte o prodloužené hodnocení.  
- **Plná licence** – zakupte pro produkční nasazení.

## Nastavení Aspose.Email pro Java

Nejprve nastavte své prostředí:

1. Ověřte, že je nainstalován JDK 16 a že je nastaveno `JAVA_HOME`.  
2. Přidejte Maven závislost (nebo stáhněte JAR) do svého projektu.  

Zde je malý úryvek, který ukazuje, jak načíst licenční soubor:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Průvodce implementací

### Vytvoření MAPI kalendáře s denním opakováním a výjimkami

#### Přehled
Tato funkce vám umožní automatizovat opakující se schůzky a zároveň mít možnost přeskočit nebo upravit konkrétní instance.

#### Krok‑za‑krokem implementace

**1. Nastavte datum zahájení události**  
Určete, kdy má série začít:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Vytvořte objekt MAPI kalendáře**  
Zadejte místo, předmět a popis:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definujte denní vzor opakování**  
Nastavte událost tak, aby se opakovala každý den:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Přidejte výjimku do opakování**  
Zadejte datum, které má být vyloučeno (nebo změněno):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Připojování souborů k výjimkám kalendáře

#### Přehled
K libovolné výjimce můžete připojit podpůrné dokumenty (např. programy).

**1. Vytvořte a připojte soubor**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Ukládání MAPI kalendáře do PST souborů

#### Přehled
Uložte kalendář do PST souboru, aby jej Outlook nebo jiní klienti mohli číst.

**1. Vytvořte a uložte kalendář do PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Praktické aplikace
- **Firemní plánování** – automatizujte sérii schůzek, automaticky přeskočte svátky.  
- **Projektové řízení** – sledujte opakující se milníky s občasnými posuny termínů.  
- **Organizace akcí** – spravujte vícedenní konference, kde jsou některé relace zrušeny nebo přeplánovány.

### Možnosti integrace
Propojte Aspose.Email s CRM platformami, API pro správu úkolů nebo vlastními workflow enginy a dosáhněte end‑to‑end automatizace.

## Úvahy o výkonu
- **Uvolňování prostředků** – vždy zavolejte `dispose()` na `PersonalStorage`, aby se uvolnily souborové handly.  
- **Použití streamů** – upřednostňujte `ByteArrayOutputStream` nebo souborové streamy, abyste se vyhnuli načítání celých PST souborů do paměti.  
- **Asynchronní operace** – při hromadném generování kalendářů spusťte logiku tvorby na pozadí, aby UI zůstalo responzivní.

## Závěr
Po přečtení tohoto průvodce nyní umíte **vytvořit mapi calendar java** objekty s denním opakováním, přidat výjimky, připojit soubory a uložit vše do PST souboru. Tyto možnosti vám umožní budovat robustní plánovací funkce, aniž byste se museli přímo dotýkat Outlooku.

### Další kroky
- Vyzkoušejte týdenní nebo měsíční vzory opakování.  
- Prozkoumejte další MAPI vlastnosti, jako jsou účastníci, připomenutí a kategorie.  
- Prohlédněte si komplexní API dokumentaci Aspose.Email pro pokročilejší scénáře.

## Často kladené otázky (FAQ)

**Q: Podporuje knihovna schůzky s časovým pásmem?**  
A: Ano, můžete nastavit vlastnosti `StartTimeZone` a `EndTimeZone` na `MapiCalendar`.

**Q: Mohu programově smazat jedinou instanci z opakující se série?**  
A: Použijte kolekci `DeletedInstanceDates` ve vzoru opakování k označení konkrétních dat jako odstraněných.

**Q: Existují limity velikosti PST souboru vytvořeného pomocí Aspose.Email?**  
A: PST soubory dodržují limity Unicode formátu (až 2 GB ve výchozím nastavení), ale můžete konfigurovat větší velikosti pomocí nastavení `PersonalStorage`.

**Q: Jak přidám účastníky do žádosti o schůzku?**  
A: Vytvořte objekty `MapiRecipient`, nastavte jejich `RecipientType` na `MapiRecipientType.MAPI_TO` a přidejte je do kolekce `Recipients` objektu `MapiMessage`.

**Q: Existuje podpora pro opakující se úkoly (ne jen schůzky)?**  
A: Ano, Aspose.Email také poskytuje `MapiTask` s podobnými schopnostmi opakování.

## Zdroje
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Email pro Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
