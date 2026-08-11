---
date: '2026-08-01'
description: Ismerje meg, hogyan exportálhatja a naptárat PST-be az Aspose.Email for
  Java segítségével, beleértve a résztvevők hozzáadását, a kezdő‑ és befejező dátumok
  beállítását, valamint a találkozók hatékony kezelését.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Naptár exportálása PST-be az Aspose.Email for Java használatával.
  Ismerje meg lépésről‑lépésre, hogyan hozhat létre találkozókat, adhat hozzá résztvevőket,
  és generálhat Outlook PST fájlokat.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Naptár exportálása PST-be – Teljes útmutató az Aspose.Email for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Naptár exportálása PST-be az Aspose.Email for Java segítségével
url: /hu/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Naptár exportálása PST-be az Aspose.Email for Java segítségével

Ha Java alkalmazást építesz, amelynek meg kell osztania az ütemezési adatokat az Outlookkal, gyakran szükséged lesz a **naptár exportálására PST-be**. Ebben az útmutatóban mindent végigvezetünk, amire szükséged van – egy egyszerű találkozó létrehozásától a résztvevők hozzáadásáig, egészen a események PST-fájlba írásáig, mindezt az Aspose.Email for Java segítségével. A végére egy termék‑kész megoldást kapsz, amely Windows, Linux és macOS rendszereken is működik.

## Gyors válaszok
- **Mi a fő cél?** Naptáresemények exportálása PST-fájlba.  
- **Melyik könyvtár szükséges?** Aspose.Email for Java (v25.4+).  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Email licenc eltávolítja a kiértékelési korlátokat.  
- **Hozzáadhatok résztvevőket?** Természetesen – használja a `MapiRecipientCollection`-t.  
- **Melyik Java verzió támogatott?** JDK 16 vagy újabb.

## Mi az a **export calendar to pst**?
`MapiCalendar` az Aspose.Email osztálya, amely egy Outlook naptárelemet modellez, beleértve a tárgyat, helyet és időpont részleteket.

A naptár PST-be exportálása azt jelenti, hogy a memóriában lévő `MapiCalendar` objektumokat Microsoft Outlook Personal Storage Table (PST) formátumba konvertáljuk. A generált PST-fájl közvetlenül megnyitható az Outlookban, megosztható kollégákkal, vagy importálható bármely olyan rendszerbe, amely érti a PST formátumot, megőrizve az összes esemény részletét, például a résztvevőket, ismétlődéseket és emlékeztetőket.

## Miért használjuk az Aspose.Email for Java-t a naptár PST-be exportálásához?
Létrehozhatsz teljesen kompatibilis PST-fájlt Outlook telepítése nélkül. Az Aspose.Email **teljes MAPI támogatást** nyújt, **minden fő operációs rendszeren** működik, és **akár 2 TB** adatot is képes kezelni Unicode PST formátumban – elegendő vállalati szintű archívumokhoz. Az API lehetővé teszi a résztvevők, ismétlődési minták, emlékeztetők és egyéni tulajdonságok kezelését néhány metódushívással, drámai módon csökkentve a fejlesztési erőfeszítést.

## Előkövetelmények
- **Könyvtárak és függőségek**: Aspose.Email for Java 25.4 vagy újabb verzió.  
- **Környezet**: JDK 16 vagy újabb, Maven a függőségkezeléshez.  
- **Tudás**: Alap Java programozás és Maven ismerete.

## Hogyan állítsuk be az Aspose.Email for Java-t
Add hozzá az Aspose.Email függőséget a `pom.xml` fájlodhoz, majd frissítsd a Maven projektet. Ez az egyetlen lépés teszi elérhetővé a teljes MAPI API-t az osztályútvonaladon.

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

### Licenc beszerzése
A Aspose.Email teljes funkcionalitásának feloldása licenc beszerzésével lehetséges, így megszűnnek a kiértékelési korlátozások:

1. **Ingyenes próba**: Látogassa meg az [Aspose letöltési oldalt](https://releases.aspose.com/email/java/) egy ideiglenes licencért.  
2. **Ideiglenes licenc**: Jelentkezzen a [vásárlási oldalon](https://purchase.aspose.com/temporary-license/).  
3. **Licenc vásárlása**: Fontolja meg a vásárlást az [Aspose vásárlási portálon](https://purchase.aspose.com/buy) hosszú távú használathoz.

Miután megvan a licenc, inicializáld azt az alkalmazásodban, hogy minden funkció elérhető legyen.

## Hogyan **hozzunk létre időpontot** (Naptáresemény létrehozása Java-ban)
Tölts be egy `MapiCalendar` objektumot, állítsd be a fő tulajdonságait, és add vissza további feldolgozásra készen. Ez a metódus egy naptárbejegyzést hoz létre tárggyal, hellyel, leírással, valamint a megadott **java calendar start date** / **java calendar end date** értékekkel.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Explanation*: A `MapiCalendar` osztály az Aspose.Email Outlook naptárelemet reprezentáló osztálya. Az alapmezők beállítása után konfigurálhatod az ismétlődést, emlékeztetőket és kategóriákat is a mentés előtt.

## Hogyan **adjunk hozzá résztvevőket** (java találkozó résztvevők hozzáadása)
Hozz létre egy `MapiRecipientCollection`-t, töltsd fel minden résztvevővel, majd csatold a találkozóhoz. Ez biztosítja, hogy minden résztvevő megkapja a megfelelő meghívót, amikor a PST megnyílik.

A `MapiRecipientCollection` egy gyűjteményosztály, amely `MapiRecipient` objektumokat tartalmaz, és a találkozó résztvevőit reprezentálja. A `MapiRecipient` egy egyedi résztvevőt jelöl e-mail címmel és címzett típussal.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Explanation*: A `MapiRecipient` egyetlen találkozó résztvevőt definiál. A típus `MAPI_TO`-ra állítása a címet elsődleges résztvevőként jelöli, míg a `MAPI_CC` vagy `MAPI_BCC` opcionális résztvevőkre használható.

## Hogyan **exportáljuk a naptárat PST-be** (PST létrehozása naptáreseményekkel)
Hozz létre egy Unicode PST-fájlt, adj hozzá egy „Calendar” mappát, és illeszd be a korábban épített `MapiCalendar` objektumokat. A PST ezután megnyitható az Outlookban vagy terjeszthető a végfelhasználók számára.

A `PersonalStorage` az Aspose.Email osztálya, amely PST-fájlok létrehozására, megnyitására és manipulálására szolgál.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Explanation*: A `PersonalStorage` a PST-manipuláció belépési pontja. Unicode formátum használatával elkerülöd a régebbi PST-verziók 2 GB-os korlátját, és nagy archívumok esetén gyorsabb I/O-t biztosít.

## Gyakorlati alkalmazások
1. **Üzleti ütemezés** – Automatizálja a belső megbeszélések létrehozását és terjesztését.  
2. **Eseménykezelés** – Kövesse a konferenciákat, workshopokat és a résztvevőlistákat.  
3. **CRM integráció** – Szinkronizálja az időpontokat az ügyfélkapcsolati eszközökkel.  
4. **Projekttervezés** – Tárolja a projekt mérföldköveket naptárbejegyzésként.  
5. **Távoli csapat együttműködés** – Generáljon PST-fájlokat offline megosztáshoz.

## Teljesítményfontosságú szempontok
- **Tegye szabadon a már nem szükséges objektumokat** a memória gyors felszabadítása érdekében.  
- **Használjon hatékony gyűjteményeket** (pl. `ArrayList` a résztvevőlistákhoz), ha több ezer résztvevőt kezel.  
- **Gyorsítótárazza a gyakran elérhető eseményeket**, ha többször lekérdezi a PST-t, ez csökkenti a lemez I/O-t.

## Gyakori problémák és megoldások
| **PST fájl nem jött létre** | Ellenőrizze a célkönyvtár írási jogosultságait, és győződjön meg arról, hogy a mappapath létezik. |
| **A résztvevők nem kapják meg a meghívókat** | Győződjön meg arról, hogy minden `MapiRecipient` a `MapiRecipientType.MAPI_TO` típust használja, és hogy a szervező e-mail címe érvényes. |
| **Dátumeltérés** | `Calendar`-t következetesen használja a kezdő/vég dátumokhoz; kerülje a `java.util.Date` és más dátumkönyvtárak keverését konverzió nélkül. |

## Gyakran Ismételt Kérdések

**K: Hogyan kezdjek hozzá az Aspose.Email for Java-hoz?**  
V: Add hozzá a fent bemutatott Maven függőséget, szerezd be a licencet, és kövesd a útmutató lépéseit a naptáresemények létrehozásához és exportálásához.

**K: Testreszabhatom a PST fájl nevét és helyét?**  
V: Igen, módosítsd a `pstFilePath` változót a `createPSTWithCalendarEvents()` metódusban bármely érvényes útvonalra a rendszereden.

**K: Lehetséges ismétlődési mintákat hozzáadni az időpontokhoz?**  
V: Természetesen – a `MapiCalendar` egy `RecurrencePattern` tulajdonságot biztosít, amelyet a mentés előtt konfigurálhatsz.

**K: Az Aspose.Email támogat más naptárformátumokat is a PST-n kívül?**  
V: Igen, exportálhatsz iCalendar (`.ics`) és más formátumokba a megfelelő API metódusok használatával.

**K: Mi a maximális PST fájlméret, amelyet létrehozhatok?**  
V: Unicode formátummal (`FileFormatVersion.Unicode`) a PST-fájlok akár 2 TB-ig is növekedhetnek, csak a rendelkezésre álló lemezterület korlátozza.

**Legutóbb frissítve:** 2026-08-01  
**Tesztelve:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Mesteri Aspose.Email for Java: Outlook PST fájlok hatékony kezelése](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Mesteri naptárelemek létrehozása és mentése Aspose.Email for Java-val](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Hogyan olvassunk több naptáreseményt egy ICS fájlból az Aspose.Email Java-val](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}