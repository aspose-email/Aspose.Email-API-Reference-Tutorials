---
date: '2026-09-17'
description: Ismerje meg, hogyan hozhat létre Outlook calendar Java-ban napi ismétléssel
  és kivételekkel, és mentheti a naptárat PST-be az Aspose.Email for Java segítségével.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Outlook calendar létrehozása Java-ban az Aspose.Email használatával.
  Ismerje meg a napi ismétlést, a kivételek kezelését, és a PST-be mentést lépésről
  lépésre útmutatóban.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Outlook calendar létrehozása Java-ban napi ismétléssel és kivételekkel
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
title: Outlook calendar létrehozása Java-ban napi ismétléssel és kivételekkel
url: /hu/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook naptár Java létrehozása napi ismétléssel és kivételekkel

Az ismétlődő események hatékony kezelése kihívást jelenthet, különösen akkor, amikor egy **outlook calendar java**-ra van szükség, amely támogatja a napi ismétlési mintákat és alkalmankénti kivételeket. Ebben az útmutatóban megtanulja, hogyan hozhat létre Outlook calendar Java objektumokat, konfigurálja a napi ismétlést, hozzáadja a kivétel példányokat, és végül **save calendar to PST**-t használva az Aspose.Email for Java könyvtárat. A végére egy újrahasználható kódrészletet kap, amelyet bármely Java‑alapú ütemező szolgáltatásba beilleszthet.

## Gyors válaszok
- **Melyik könyvtár?** Aspose.Email for Java  
- **Elsődleges feladat?** Outlook calendar Java létrehozása napi ismétléssel és kivételekkel  
- **Előfeltétel JDK?** Java 16 vagy újabb  
- **Csatolhatok fájlokat a kivételekhez?** Igen, a `MapiCalendarExceptionInfo` használatával  
- **Hol tárolódik a naptár?** PST fájlban a `PersonalStorage` segítségével  

## Mi az Outlook calendar java?
Az Outlook calendar Java objektum egy programozott ábrázolása egy Outlook időpontnak, amely a MAPI (Messaging Application Programming Interface) specifikáción alapul, és olyan tulajdonságokat tartalmaz, mint a tárgy, helyszín, kezdő/vég időpont, ismétlődési szabályok, résztvevők és mellékletek. Ez az objektum manipulálható, sorosítható és PST fájlokban tárolható Outlook telepítése nélkül.

## Miért használja az Aspose.Email for Java‑t?
Az Aspose.Email for Java lehetővé teszi a MAPI objektumokkal való munkát Outlook telepítése nélkül. A könyvtár **50+ MAPI tulajdonságot** támogat, Unicode PST fájlokat tud generálni akár **2 GB** méretig **2 másodperc** alatt tipikus időpont adatok esetén, és bármely, Java 16‑ot támogató platformon fut. Ez a tisztán Java megközelítés lehetővé teszi a szerver‑oldali naptárkészítést, automatizált találkozósorozatokat és a teljes ismétlődési logika ellenőrzését.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy a következő beállítások rendelkezésre állnak:
- **Aspose.Email Library**: 25.4-es verzió (vagy újabb) – Maven‑en vagy közvetlen letöltésen keresztül elérhető.  
- **Java Development Kit (JDK)**: JDK 16 vagy újabb.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans vagy bármely Java‑kompatibilis szerkesztő.

### Szükséges könyvtárak és függőségek

Az Aspose.Email integrálásához Maven‑nel adja hozzá a következő függőséget a `pom.xml`‑hez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése

Az Aspose.Email használatához licencre van szükség:
- **Ingyenes próba** – minden funkció felfedezése költség nélkül.  
- **Ideiglenes licenc** – kérhető hosszabb értékeléshez.  
- **Teljes licenc** – vásárlás termelési környezetben való használathoz.

## Az Aspose.Email for Java beállítása

Először állítsa be a környezetet:

1. Ellenőrizze, hogy a JDK 16 telepítve van, és a `JAVA_HOME` megfelelően van beállítva.  
2. Adja hozzá a Maven‑függőséget (vagy töltse le a JAR‑t) a projektjéhez.  

Az alábbi kis részlet bemutatja, hogyan tölthet be egy licencfájlt:

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

## Implementációs útmutató

### Outlook calendar Java létrehozása napi ismétléssel és kivételekkel

#### Áttekintés
Ez a funkció lehetővé teszi az ismétlődő időpontok automatizálását, miközben bizonyos példányokat kihagyhat vagy módosíthat.

#### Lépésről‑lépésre megvalósítás

**1. Set up event start date**  
Határozza meg, mikor kezdődjön a sorozat:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Create the MAPI calendar object**  
A `MapiCalendar` osztály a legfelső szintű objektum, amely egyetlen naptárelem memóriában való ábrázolását jelenti. Adja meg a helyszínt, a tárgyat és a leírást:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Define a daily recurrence pattern**  
A `MapiCalendarRecurrencePattern` osztály tárolja azt a szabályt, amely minden nap ismétli az időpontot. Állítsa be, hogy az esemény minden nap ismétlődjön:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Add an exception to the recurrence**  
A `MapiCalendarExceptionInfo` egyetlen előfordulást ír le, amely eltér a mintától – akár kizárva, akár módosítva. Adjon meg egy dátumot, amelyet ki kell zárni (vagy módosítani):

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

### Fájlok csatolása a naptárkivételhez

#### Áttekintés
Bármely kivételhez csatolhat támogató dokumentumokat (pl. napirendeket).

**1. Create and attach a file**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Outlook calendar Java mentése PST-be (save calendar to pst)

#### Áttekintés
A naptár PST fájlba mentése lehetővé teszi, hogy az Outlook vagy más kliensek olvassák azt.

**1. Create and save calendar to PST**  
A `PersonalStorage` osztály módszereket biztosít új PST fájl létrehozásához és MAPI elemek hozzáadásához.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Gyakorlati alkalmazások
- **Vállalati ütemezés** – találkozósorozatok automatizálása, ünnepnapok automatikus kihagyásával.  
- **Projektmenedzsment** – ismétlődő mérföldkövek nyomon követése alkalmankénti dátumeltérésekkel.  
- **Eseményszervezés** – többnapos konferenciák kezelése, ahol egyes ülések lemondásra vagy átszervezésre kerülnek.

### Integrációs lehetőségek
Az Aspose.Email kombinálható CRM platformokkal, feladatkezelő API‑kkal vagy egyedi munkafolyamat‑motorokkal az end‑to‑end automatizálás érdekében.

## Teljesítmény szempontok
- **Dispose resources** – mindig hívja meg a `dispose()` metódust a `PersonalStorage`‑on a fájlkezelők felszabadításához.  
- **Stream usage** – részesítse előnyben a `ByteArrayOutputStream` vagy fájl‑stream használatát, hogy elkerülje a teljes PST memóriába töltését.  
- **Async operations** – nagy mennyiségű naptár generálásakor futtassa a létrehozási logikát háttérszálon a UI válaszkészségének megőrzése érdekében.

## Következtetés
A jelen útmutató követésével most már tudja, hogyan **create outlook calendar java** objektumokat hozzon létre napi ismétléssel, adjon hozzá kivételeket, csatoljon fájlokat, és **save calendar to PST**. Ezek a képességek lehetővé teszik robusztus ütemezési funkciók építését anélkül, hogy közvetlenül az Outlook‑ot kellene használni.

### Következő lépések
- Kísérletezzen heti vagy havi ismétlődési mintákkal.  
- Fedezze fel a további MAPI tulajdonságokat, például résztvevőket, emlékeztetőket és kategóriákat.  
- Tekintse át az Aspose.Email átfogó API dokumentációját a fejlettebb forgatókönyvekhez.

## Gyakran ismételt kérdések

**Q: Támogatja a könyvtár az időzóna‑érzékeny időpontokat?**  
A: Igen, beállíthatja a `StartTimeZone` és `EndTimeZone` tulajdonságokat a `MapiCalendar`‑on.

**Q: Programozottan törölhetek egyetlen előfordulást egy ismétlődő sorozatból?**  
A: Használja a `DeletedInstanceDates` gyűjteményt az ismétlődési mintán, hogy a konkrét dátumokat eltávolítottként jelölje.

**Q: Van korlátozás a Aspose.Email‑del létrehozott PST fájl méretére?**  
A: A PST fájlok az Unicode formátum korlátait követik (alapértelmezés szerint legfeljebb 2 GB), de a `PersonalStorage` beállításokkal nagyobb méretek is konfigurálhatók.

**Q: Hogyan adhatok résztvevőket egy találkozó‑kéréshez?**  
A: Hozzon létre `MapiRecipient` objektumokat, állítsa be a `RecipientType`‑ot `MapiRecipientType.MAPI_TO`‑ra, és adja hozzá őket a `Recipients` gyűjteményhez a `MapiMessage`‑ben.

**Q: Van támogatás ismétlődő feladatokra (nem csak időpontokra)?**  
A: Igen, az Aspose.Email biztosítja a `MapiTask`‑ot hasonló ismétlődési képességekkel.

**Q: Használhatom ezt az útmutatót az Aspose.Email Java tutorial sorozat részeként?**  
A: Természetesen – a bemutatott lépések bármely Aspose.Email Java tutorial alapvető részét képezik, amely a naptárkészítéssel foglalkozik.

## Források
- [Aspose.Email for Java dokumentáció](https://reference.aspose.com/email/java/)
- [Aspose.Email letöltése](https://releases.aspose.com/email/java/)
- [Licenc vásárlása](https://purchase.aspose.com/buy)
- [Ingyenes próbaverzió](https://releases.aspose.com/email/java/)
- [Ideiglenes licenc kérése](https://purchase.aspose.com/temporary-license/)
- [Aspose támogatási fórum](https://forum.aspose.com/c/email/10)

---

**Utoljára frissítve:** 2026-09-17  
**Tesztelve:** Aspose.Email for Java 25.4 (JDK 16)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Outlook naptár PST exportálása Aspose.Email‑vel – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Hogyan hozzunk létre naptárelem Java‑ban az Aspose.Email használatával](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Naptármegosztási meghívó létrehozása Aspose.Email for Java‑val](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}