---
date: '2026-03-20'
description: Naučte se, jak vytvořit kalendář Outlook v Javě s denním opakováním a
  výjimkami a uložit kalendář do souboru PST pomocí Aspose.Email pro Javu.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Vytvořte Outlook kalendář v Javě s denním opakováním a výjimkami
url: /cs/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit Outlook calendar Java s denní opakovatelností a výjimkami

Správa opakujících se událostí efektivně může být náročná, zejména když potřebujete **outlook calendar java**, který podporuje denní opakovací vzory a občasné výjimky. V tomto tutoriálu se naučíte, jak vytvořit Outlook calendar Java objekty, nakonfigurovat denní opakování, přidat výjimky a nakonec **save calendar to PST** pomocí Aspose.Email pro Java. Na konci budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolné služby plánování založené na Javě.

## Rychlé odpovědi
- **Která knihovna?** Aspose.Email for Java  
- **Hlavní úkol?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Požadovaný JDK?** Java 16 or higher  
- **Mohu k výjimkám připojit soubory?** Yes, using `MapiCalendarExceptionInfo`  
- **Kde je kalendář uložen?** In a PST file via `PersonalStorage`

## Co je Outlook calendar java?
Objekt Outlook calendar Java (implementovaný jako MAPI kalendář) dodržuje stejné standardy jako schůzky Microsoft Outlook. Uchovává bohatá pravidla opakování, zpracování výjimek, účastníky a přílohy, což z něj činí ideální řešení pro podnikové plánování.

## Proč používat Aspose.Email pro Java?
Aspose.Email poskytuje čisté Java API, které vám umožňuje pracovat s MAPI objekty, aniž byste potřebovali nainstalovaný Outlook. Tento **aspose email tutorial java** přístup umožňuje generování PST souborů na straně serveru, automatizované série schůzek a plnou kontrolu nad logikou opakování.

## Požadavky

Before we begin, ensure you have the following setup:
- **Aspose.Email Library**: Verze 25.4 (nebo novější) – dostupná přes Maven nebo přímé stažení.  
- **Java Development Kit (JDK)**: JDK 16 nebo novější.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli editor kompatibilní s Javou.

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

To use Aspose.Email, you'll need a license:
- **Free Trial** – vyzkoušejte všechny funkce zdarma.  
- **Temporary License** – požádejte o prodloužené hodnocení.  
- **Full License** – zakupte pro produkční nasazení.

## Nastavení Aspose.Email pro Java

First, set up your environment:

1. Ověřte, že je nainstalován JDK 16 a že je nastaven `JAVA_HOME`.  
2. Přidejte Maven závislost (nebo stáhněte JAR) do svého projektu.  

Zde je malý úryvek, který ukazuje, jak načíst soubor licence:

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

### Vytvoření Outlook calendar Java s denním opakováním a výjimkami

#### Přehled
Tato funkce vám umožní automatizovat opakující se schůzky a zároveň přeskočit nebo upravit konkrétní instance.

#### Krok‑za‑krokem implementace

**1. Nastavení počátečního data události**  
Určete, kdy by měla série začít:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Vytvoření MAPI kalendářového objektu**  
Zadejte místo, předmět a popis:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definování denního opakovacího vzoru**  
Nastavte událost tak, aby se opakovala každý den:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Přidání výjimky k opakování**  
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
Můžete připojit podpůrné dokumenty (např. agendy) k libovolné výjimkové instanci.

**1. Vytvoření a připojení souboru**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Ukládání Outlook calendar Java do PST (save calendar to pst)

#### Přehled
Uložte kalendář do PST souboru, aby jej mohl číst Outlook nebo jiní klienti.

**1. Vytvoření a uložení kalendáře do PST**

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
- **Corporate Scheduling** – automatizujte série schůzek, automaticky přeskočte svátky.  
- **Project Management** – sledujte opakující se milníky s občasnými posuny termínů.  
- **Event Planning** – spravujte vícedenní konference, kde jsou některé relace zrušeny nebo přeplánovány.

### Možnosti integrace
Kombinujte Aspose.Email s CRM platformami, API pro správu úkolů nebo vlastními workflow enginy pro kompletní automatizaci.

## Úvahy o výkonu
- **Dispose Resources** – vždy zavolejte `dispose()` na `PersonalStorage`, aby se uvolnily souborové handly.  
- **Stream Usage** – upřednostněte `ByteArrayOutputStream` nebo souborové proudy, aby se nepřetěžovalo načítání celých PST do paměti.  
- **Async Operations** – při hromadném generování kalendářů spusťte logiku tvorby na pozadí, aby UI zůstalo responzivní.

## Závěr
Po přečtení tohoto průvodce nyní víte, jak **create outlook calendar java** objekty s denním opakováním, přidávat výjimky, připojovat soubory a **save calendar to PST**. Tyto možnosti vám umožní vytvořit robustní funkce plánování, aniž byste se museli přímo dotýkat Outlooku.

### Další kroky
- Experimentujte s týdenními nebo měsíčními opakovacími vzory.  
- Prozkoumejte další MAPI vlastnosti, jako jsou účastníci, připomenutí a kategorie.  
- Prohlédněte si komplexní API dokumentaci Aspose.Email pro pokročilejší scénáře.

## Často kladené otázky

**Q: Podporuje knihovna schůzky s časovým pásmem?**  
A: Ano, můžete nastavit vlastnosti `StartTimeZone` a `EndTimeZone` na `MapiCalendar`.

**Q: Mohu programově smazat jednu instanci z opakující se série?**  
A: Použijte kolekci `DeletedInstanceDates` v opakovacím vzoru k označení konkrétních dat jako odstraněných.

**Q: Existují limity velikosti PST souboru vytvořeného pomocí Aspose.Email?**  
A: PST soubory dodržují limity Unicode formátu (standardně až 2 GB), ale můžete nastavit větší velikosti pomocí nastavení `PersonalStorage`.

**Q: Jak přidám účastníky do žádosti o schůzku?**  
A: Vytvořte objekty `MapiRecipient`, nastavte jejich `RecipientType` na `MapiRecipientType.MAPI_TO` a přidejte je do kolekce `Recipients` objektu `MapiMessage`.

**Q: Existuje podpora pro opakující se úkoly (nejen schůzky)?**  
A: Ano, Aspose.Email také poskytuje `MapiTask` s podobnými možnostmi opakování.

**Q: Mohu tento průvodce použít jako součást série aspose email tutorial java?**  
A: Rozhodně – kroky zde uvedené jsou základní součástí jakéhokoli Aspose.Email Java tutoriálu, který se zabývá tvorbou kalendáře.

## Zdroje
- [Dokumentace Aspose.Email pro Java](https://reference.aspose.com/email/java/)
- [Stáhnout Aspose.Email](https://releases.aspose.com/email/java/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Verze zdarma](https://releases.aspose.com/email/java/)
- [Požádat o dočasnou licenci](https://purchase.aspose.com/temporary-license/)
- [Fórum podpory Aspose](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-03-20  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}