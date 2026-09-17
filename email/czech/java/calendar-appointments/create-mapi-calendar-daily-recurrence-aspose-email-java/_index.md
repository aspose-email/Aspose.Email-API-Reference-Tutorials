---
date: '2026-09-17'
description: Naučte se, jak vytvořit kalendář outlook v Java s denním opakováním a
  výjimkami a uložit kalendář do PST pomocí Aspose.Email pro Java.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Vytvořte kalendář outlook v Java pomocí Aspose.Email. Naučte se denní
  opakování, zpracování výjimek a ukládání do PST v podrobném návodu.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Vytvořit kalendář outlook v Java s denním opakováním a výjimkami
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Vytvořit kalendář outlook v Java s denním opakováním a výjimkami
url: /cs/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte Outlook kalendář Java s denním opakováním a výjimkami

Správa opakujících se událostí efektivně může být náročná, zejména když potřebujete **outlook calendar java**, který podporuje denní opakovací vzory a občasné výjimky. V tomto tutoriálu se naučíte, jak vytvořit Outlook kalendář Java objekty, nakonfigurovat denní opakování, přidat výjimky a nakonec **save calendar to PST** pomocí Aspose.Email for Java. Na konci budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolné služby plánování založené na Javě.

## Rychlé odpovědi
- **Která knihovna?** Aspose.Email for Java  
- **Primární úkol?** Vytvořit Outlook kalendář Java s denním opakováním a výjimkami  
- **Požadovaný JDK?** Java 16 nebo vyšší  
- **Mohu k výjimkám připojit soubory?** Ano, pomocí `MapiCalendarExceptionInfo`  
- **Kde je kalendář uložen?** V souboru PST přes `PersonalStorage`  

## Co je Outlook calendar java?
Outlook calendar Java objekt je programová reprezentace schůzky Outlook, postavená na specifikaci MAPI (Messaging Application Programming Interface), která zahrnuje vlastnosti jako předmět, místo, časy začátku/konce, pravidla opakování, účastníky a přílohy. Tento objekt lze manipulovat, serializovat a ukládat do souborů PST bez nutnosti Outlooku.

## Proč používat Aspose.Email for Java?
Aspose.Email for Java vám umožní pracovat s MAPI objekty bez instalace Outlooku. Knihovna podporuje **50+ MAPI vlastností**, dokáže generovat Unicode PST soubory až do **2 GB** za méně než **2 sekundy** pro typická data schůzek a běží na jakékoli platformě, která podporuje Java 16+. Tento čistě Java přístup umožňuje server‑side tvorbu kalendářů, automatizaci sérií schůzek a plnou kontrolu nad logikou opakování.

## Požadavky

Než začneme, ujistěte se, že máte následující nastavení:
- **Aspose.Email Library**: Verze 25.4 (nebo novější) – k dispozici přes Maven nebo přímé stažení.  
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

Pro použití Aspose.Email budete potřebovat licenci:
- **Free trial** – prozkoumejte všechny funkce zdarma.  
- **Temporary license** – požádejte o rozšířené hodnocení.  
- **Full license** – zakupte pro produkční nasazení.

## Nastavení Aspose.Email pro Java

Nejprve nastavte své prostředí:

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

### Vytvoření outlook calendar java s denním opakováním a výjimkami

#### Přehled
Tato funkce vám umožní automatizovat opakující se schůzky a zároveň mít možnost vynechat nebo upravit konkrétní instance.

#### Krok‑za‑krokem implementace

**1. Nastavte počáteční datum události**  
Určete, kdy má série začít:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Vytvořte MAPI kalendářový objekt**  
Třída `MapiCalendar` je objekt nejvyšší úrovně, který představuje jedinou položku kalendáře v paměti. Zadejte místo, předmět a popis:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Definujte denní opakovací vzor**  
Třída `MapiCalendarRecurrencePattern` ukládá pravidlo, které opakuje schůzku každý den. Nakonfigurujte událost, aby se opakovala denně:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Přidejte výjimku k opakování**  
`MapiCalendarExceptionInfo` popisuje jedinou výskyt, který se liší od vzoru – buď je vynechán, nebo změněn. Zadejte datum, které má být vynecháno (nebo změněno):

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
Můžete k libovolné výjimce připojit podpůrné dokumenty (např. agendy).

**1. Vytvořte a připojte soubor**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Ukládání outlook calendar java do PST (save calendar to pst)

#### Přehled
Uložte kalendář do souboru PST, aby jej mohl číst Outlook nebo jiný klient.

**1. Vytvořte a uložte kalendář do PST**  
Třída `PersonalStorage` poskytuje metody pro vytvoření nového PST souboru a přidání MAPI položek do něj.

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
- **Corporate scheduling** – automatizujte sérii schůzek, automaticky vynechávající svátky.  
- **Project management** – sledujte opakující se milníky s občasnými posuny dat.  
- **Event planning** – spravujte vícedenní konference, kde jsou některé relace zrušeny nebo přeplánovány.

### Možnosti integrace
Kombinujte Aspose.Email s CRM platformami, API pro správu úkolů nebo vlastními workflow enginy pro end‑to‑end automatizaci.

## Úvahy o výkonu
- **Dispose resources** – vždy volejte `dispose()` na `PersonalStorage`, aby se uvolnily souborové handle.  
- **Stream usage** – upřednostňujte `ByteArrayOutputStream` nebo souborové streamy, abyste se vyhnuli načítání celých PST do paměti.  
- **Async operations** – pro hromadnou tvorbu kalendářů spusťte logiku tvorby na pozadí, aby UI zůstalo responzivní.

## Závěr
Podle tohoto průvodce nyní umíte **create outlook calendar java** objekty s denním opakováním, přidávat výjimky, připojovat soubory a **save calendar to PST**. Tyto možnosti vám umožní vytvořit robustní funkce plánování bez nutnosti přímé práce s Outlookem.

### Další kroky
- Experimentujte s týdenními nebo měsíčními opakovacími vzory.  
- Prozkoumejte další MAPI vlastnosti, jako jsou účastníci, připomenutí a kategorie.  
- Prohlédněte si podrobnou dokumentaci API Aspose.Email pro pokročilejší scénáře.

## Často kladené otázky

**Q: Podporuje knihovna schůzky s časovým pásmem?**  
A: Ano, můžete nastavit vlastnosti `StartTimeZone` a `EndTimeZone` na `MapiCalendar`.

**Q: Mohu programově smazat jediný výskyt z opakující se série?**  
A: Použijte kolekci `DeletedInstanceDates` na opakovacím vzoru k označení konkrétních dat jako odstraněných.

**Q: Existují limity velikosti PST souboru vytvořeného pomocí Aspose.Email?**  
A: PST soubory dodržují limity Unicode formátu (až 2 GB ve výchozím nastavení), ale můžete nakonfigurovat větší velikosti pomocí nastavení `PersonalStorage`.

**Q: Jak přidám účastníky k žádosti o schůzku?**  
A: Vytvořte objekty `MapiRecipient`, nastavte jejich `RecipientType` na `MapiRecipientType.MAPI_TO` a přidejte je do kolekce `Recipients` objektu `MapiMessage`.

**Q: Je podpora pro opakující se úkoly (nejen schůzky)?**  
A: Ano, Aspose.Email také poskytuje `MapiTask` s podobnými možnostmi opakování.

**Q: Mohu tento průvodce použít jako součást série tutoriálů Aspose.Email Java?**  
A: Rozhodně – kroky zde uvedené jsou jádrem každého tutoriálu Aspose.Email Java, který se zabývá tvorbou kalendářů.

## Zdroje
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Poslední aktualizace:** 2026-09-17  
**Testováno s:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Související tutoriály

- [Export Outlook calendar PST with Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Create Calendar Sharing Invitation with Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}