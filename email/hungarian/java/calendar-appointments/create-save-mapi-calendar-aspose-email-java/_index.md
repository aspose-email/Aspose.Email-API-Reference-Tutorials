---
date: '2026-09-17'
description: Ismerje meg, hogyan exportálhat Outlook naptár PST-t az Aspose.Email
  for Java használatával – hozza létre a MAPI naptárelemeket, állítson be ismétlődést,
  adjon hozzá résztvevőket, és mentse PST-be.
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Exportálja az Outlook naptár PST-t az Aspose.Email for Java segítségével.
  Tanulja meg, hogyan hozhat létre MAPI naptárelemeket, állíthat be ismétlődést, résztvevőket,
  és mentheti PST-be percek alatt.
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Outlook naptár PST exportálása az Aspose.Email segítségével – Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Outlook naptár PST exportálása az Aspose.Email segítségével – Java
url: /hu/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook naptár PST exportálása Aspose.Email segítségével – Java

## Bevezetés

Szeretné egyszerűsíteni a naptár automatizálását Java alkalmazásaiban, és **export Outlook calendar PST** fájlokra van szüksége? Az **Aspose.Email for Java** segítségével **create MAPI calendar Java** elemeket hozhat létre, meghatározhatja az ismétlődési mintákat, hozzáadhat résztvevőket, és **save calendar to PST** néhány kódsorral. Ez az útmutató végigvezeti Önt a teljes folyamaton – a könyvtár beállításától egy teljesen működő naptárelem létrehozásáig, amely készen áll a terjesztésre.

### Mit fog megtanulni
- Hogyan **create MAPI calendar Java** eseményeket hozhat létre az Aspose.Email használatával.  
- Napi, heti vagy egyéni ismétlődési minták konfigurálása.  
- Címzettek (szervezők, résztvevők) hozzáadása a naptármeghívókhoz.  
- A naptárelem megőrzése **saving calendar to PST** segítségével az Outlook kompatibilitás érdekében.  
- Hogyan **automate meeting scheduling** újrahasználható kóddal.

## Gyors válaszok
- **Melyik könyvtár?** Aspose.Email for Java  
- **Elsődleges cél?** Export Outlook calendar PST és **save calendar to PST**  
- **Előfeltételek?** Java 8+, Maven, Aspose.Email license  
- **Tipikus megvalósítási idő?** 10‑15 perc egy alap eseményhez  
- **Hozzáadhatok ismétlődést?** Igen – napi, heti, havi, stb.

## Outlook naptár PST exportálása

Ebben a szakaszban az end‑to‑end folyamatra összpontosítunk, amely lehetővé teszi, hogy **export Outlook calendar PST** fájlokat hozzon létre. A MAPI naptárobjektum létrehozása után az utolsó lépés, hogy azt egy PST fájlba tárolja, amelyet az Outlook közvetlenül olvasni tud.

## Miért használja az Aspose.Email-t a naptár automatizálásához?

Export Outlook calendar PST az Aspose.Email segítségével, mert megbízható, szerver‑oldali módot biztosít Outlook‑kompatibilis elemek előállításához COM interop nélkül. A könyvtár támogatja a **50+ input and output formats** formátumot, képes 2 GB-nál nagyobb PST fájlok kezelésére, és percenként több ezer naptáreseményt dolgoz fel a tipikus szerverhardveren. Beépített ismétlődési motorja lefedi a napi, heti, havi és egyéni mintákat, ezzel kiküszöbölve a manuális dátusszámítás szükségességét.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

### Szükséges könyvtárak
- **Aspose.Email for Java**: Version 25.4 vagy újabb (támogatja a Java 8‑21).

### Környezet beállítási követelmények
- Egy Java IDE, például IntelliJ IDEA vagy Eclipse.  
- Maven telepítve a függőségek kezelése érdekében.

### Tudás előfeltételek
- Alapvető Java programozási ismeretek.  
- Ismeret az objektum‑orientált koncepciókról.

## Az Aspose.Email for Java beállítása

Adja hozzá az Aspose.Email Maven függőséget a `pom.xml` fájlhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése

Aspose.Email offers a free trial, but a license unlocks all features:

- **Free trial**: 30 napos korlátlan tesztelés.  
- **Temporary license**: Kérje a [Aspose weboldalán](https://purchase.aspose.com/temporary-license/) ha extra időre van szüksége.  
- **Purchase**: Vásároljon állandó licencet a [purchase page](https://purchase.aspose.com/buy) oldalról.

### Alap inicializálás

A függőség hozzáadása után inicializálja a könyvtárat a licencfájljával:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Megvalósítási útmutató

Miután minden be van állítva, hozzunk létre **create MAPI calendar Java** elemet és **save calendar to PST**.

### MAPI naptár létrehozása ismétlődéssel

#### Áttekintés

Építsünk egy naptáreseményt, alkalmazzunk napi ismétlődést, adjunk hozzá résztvevőket, és végül tároljuk egy PST fájlban.

#### Lépés‑ről‑lépésre megvalósítás

1. **Dátum és ismétlődési minta inicializálása**  

   `MapiCalendarEventRecurrence` az az osztály, amely a naptárelem ismétlődési részleteit tárolja.  
   `MapiCalendarDailyRecurrencePattern` egy egyszerű napi ismétlődési ütemezést határoz meg.  

   Először határozza meg a kezdési időt, és állítson be napi ismétlődést:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **Címzettek beállítása**  

   `MapiRecipientCollection` a megbeszélésre meghívott személyek listáját képviseli.  
   `MAPI_TO` egy jelző, amely a címzettet elsődleges résztvevőként jelöli.  

   Adja hozzá a személyeket, akiknek meg kell kapniuk a meghívót:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **A MAPI naptár elem létrehozása**  

   `MapiMessage` osztály (itt naptárobjektumként használva) tartalmazza az összes esemény tulajdonságát, mint szervező, tárgy, hely, kezdő/vég időpontok, leírás, címzettlista és ismétlődés.  

   Építse fel a naptárobjektumot az összes szükséges részlettel:

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

4. **Mentés PST fájlba**  

   `PersonalStorage` az Aspose.Email felső szintű API-ja PST fájlok létrehozásához és manipulálásához.  
   `addMapiMessageItem` egy MAPI üzenetet (beleértve a naptár elemeket) helyez egy megadott mappába.  

   Végül, mentse a naptárat **saving calendar to PST** segítségével:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### Hibaelhárítási tippek
- Ellenőrizze a licenc útvonalát; egy érvénytelen licenc korlátozza a funkcionalitást.  
- Győződjön meg arról, hogy a címzettek e‑mail címei helyesen vannak formázva a meghívó hibák elkerülése érdekében.  
- Zárja be a PST‑t (`pst.dispose()`) a műveletek után, hogy felszabadítsa a fájlkezelőket.

## Gyakorlati alkalmazások

Az alábbiakban közös forgatókönyveket mutatunk be, ahol a **creating MAPI calendar Java** és a **saving calendar to PST** ragyog.

1. **Automated meeting scheduling** – Ismétlődő megbeszélés meghívók generálása projektcsapatok számára manuális munka nélkül.  
2. **Event management platforms** – Konferencia ülések exportálása Outlook‑kompatibilis naptárelemekként.  
3. **CRM integration** – Ügyfél időpontok szinkronizálása egy CRM rendszerből közvetlenül Outlookba PST fájlok segítségével.

## Teljesítmény szempontok

- **Resource management**: A `PersonalStorage` objektumok eldobása használat után a fájlzárolások megelőzése érdekében.  
- **Batch processing**: Nagy mennyiség esetén dolgozza fel a naptárelemeket aszinkron módon vagy darabokban a memóriahasználat alacsonyan tartása érdekében.  
- **Scalability**: Az Aspose.Email képes 2 GB-nál nagyobb PST fájlok írására, miközben a memóriafogyasztás 200 MB alatt marad.

## Összegzés

Most már megtanulta, hogyan **export Outlook calendar PST** MAPI naptár Java objektumok létrehozásával, ismétlődés konfigurálásával, résztvevők hozzáadásával, és **save calendar to PST** használatával az Aspose.Email segítségével. Ez a megközelítés lehetővé teszi Java alkalmazásai számára, hogy automatizálják a kifinomult ütemezési munkafolyamatokat Outlook kompatibilitással.

A mélyebb feltárásért tekintse meg a hivatalos [documentation](https://reference.aspose.com/email/java/).

## GYIK szakasz

### Q: Létrehozhatok heti ismétlődési mintákat?
- **A**: Igen! Használja a `MapiCalendarWeeklyRecurrencePattern`‑t a heti ismétlések meghatározásához.

### Q: Hogyan kezelem az esemény ismétlődés kivételeit?
- **A**: Hívja a `setExceptions()`‑t az ismétlődési objektumon, hogy megadja a mintától eltérő dátumokat.

### Q: Lehetőség van meglévő naptárelem frissítésére?
- **A**: Absolút. Töltse be az elemet a PST‑ből, módosítsa a tulajdonságait, és mentse vissza.

### Q: Titkosíthatom a PST fájlt?
- **A**: Igen, az Aspose.Email lehetővé teszi, hogy jelszót állítson be a `PersonalStorage`‑nél a PST létrehozásakor.

### Q: Mi van, ha csatolmányokat kell hozzáadni a naptáreseményhez?
- **A**: Használja a `calendar.getAttachments().addFileAttachment("path/to/file")`‑t a mentés előtt.

## Erőforrások

- [Aspose.Email dokumentáció](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java letöltése](https://releases.aspose.com/email/java/)
- [Licenc vásárlása](https://purchase.aspose.com/buy)
- [Ingyenes próbaverzió](https://releases.aspose.com/email/java/)
- [Ideiglenes licenc kérése](https://purchase.aspose.com/temporary-license/)
- [Aspose támogatási fórum](https://forum.aspose.com/c/email/10)

---

**Utoljára frissítve:** 2026-09-17  
**Tesztelve ezzel:** Aspose.Email for Java 25.4 (JDK 16)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Outlook PST fájlok létrehozása és kezelése Aspose.Email for Java használatával](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [PST fájlok létrehozása Aspose.Email for Java-val](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [Naptárelem létrehozása Java-ban Aspose.Email használatával](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}