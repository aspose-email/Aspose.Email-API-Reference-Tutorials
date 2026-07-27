---
date: '2026-07-27'
description: Ismerje meg, hogyan állíthat be Outlook flag Java-t az Aspose.Email for
  Java segítségével, beleértve a flag létrehozását, a címzett flag-eket, a befejezést,
  az eltávolítást és az olvasási lehetőségeket.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Állítson be Outlook flag Java-t az Aspose.Email for Java segítségével.
  Ez az útmutató bemutatja, hogyan hozhat létre, olvashat, fejezhet be és távolíthat
  el Outlook follow‑up flag-eket hatékonyan.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Outlook jelző beállítása Java – Teljes Aspose.Email programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Outlook jelző beállítása Java – Teljes Aspose.Email programozási útmutató
url: /hu/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook jelző beállítása Java-ban az Aspose.Email for Java használatával

## Bevezetés
Ha programozott módon szeretnél **set outlook flag java** beállítani, jó helyen jársz. Az Outlook nyomonkövetési jelző egy egyszerű e‑mailt feladatként követhetővé tesz, és az Aspose.Email for Java lehetővé teszi ezen jelzők kezelését Outlook telepítése nélkül. Ebben az útmutatóban végigvezetünk a jelzők létrehozásán, olvasásán, befejezésén és végül eltávolításán, valamint arról, hogyan alkalmazhatók a jelzők konkrét címzettekre. A végére egy újrahasználható Java kódrészletet kapsz, amely automatikusan nyomon követi a feladatokat közvetlenül a háttérszolgáltatásaidból.

## Gyors válaszok
- **Mi jelent a “set outlook flag java”?** Egy jelző hozzáadása kezdő, emlékeztető és határidő dátumokkal egy Outlook elemhez Java kóddal.  
- **Melyik könyvtár szükséges?** Aspose.Email for Java (v25.4 vagy újabb).  
- **Szükségem van licencre?** Igen – a próbaverzió értékelésre használható, de a termeléshez megvásárolt licenc szükséges.  
- **Beállíthatok csak a címzetteknek szóló jelzőket?** Természetesen – használd a `FollowUpManager.setFlagForRecipients` metódust.  
- **Lehet később eltávolítani egy jelzőt?** Igen – hívd a `FollowUpManager.clearFlag` metódust.

## Mi az Outlook nyomonkövetési jelző?
Az Outlook nyomonkövetési jelző egy beépített feladatjelző, amely bármely e‑mail elemhez csatolhat kezdő dátumot, emlékeztetőt és határidőt. Egy e‑mailt nyomon követhető feladattá alakít, segítve téged és csapatodat a függőben lévő munkák nyomon követésében.

## Miért használjuk az Aspose.Email for Java-t?
Az Aspose.Email for Java **70+ e‑mail formátumot** támogat (beleértve a MSG, EML, MHTML és TNEF formátumokat), és egy tipikus 8‑magos szerveren **több mint 100 000 üzenetet percenként** képes feldolgozni, mindezt Outlook nélkül a gépen. Ez ideálissá teszi háttér‑automatizáláshoz, megfelelőségi jelentésekhez és projekt‑menedzsment eszközökkel való integrációhoz.

## Előkövetelmények
- **Aspose.Email for Java** verzió 25.4 vagy újabb.  
- **JDK 16+** telepítve.  
- Maven‑kompatibilis IDE (IntelliJ IDEA, Eclipse, stb.).  
- Alapvető Java ismeretek és e‑mail koncepciók ismerete.

## Az Aspose.Email for Java beállítása
### Maven konfiguráció
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése
Aspose.Email licencet igényel a termelési használathoz:
- **Free trial** – 30‑napos értékelés.  
- **Temporary license** – kiterjesztett tesztelés.  
- **Full license** – örökös előfizetés.

Hozd létre a licencet bármely e‑mail művelet előtt:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook jelző beállítása Java (1. funkció)
### Közvetlen válasz
Tölts be egy `MailMessage`‑t, konvertáld `MapiMessage`‑re, állítsd be a `FollowUpOptions`‑t, és hívd a `FollowUpManager.setOptions`‑t. Ez a sorozat néhány Java sorban teljesen jelölt Outlook elemet hoz létre.

### 1. lépés: Üzenet létrehozása és inicializálása
`MailMessage` az Aspose.Email magas szintű osztálya, amely egy e‑mailt képvisel. Miután felépítetted az üzenetet, konvertálod `MapiMessage`‑re a jelzőkezeléshez.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Először egy `MailMessage`‑t építünk, beállítjuk a feladót/címzettet, majd konvertáljuk `MapiMessage`‑re a jelzőkezeléshez.*

### 2. lépés: Nyomonkövetési dátumok meghatározása (Outlook jelző emlékeztető)
`FollowUpOptions` tárolja a kezdő, emlékeztető és határidő dátumokat. Használd a Java `Calendar`‑t a pontos időbélyegek beállításához.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Itt állítjuk be a kezdő, emlékeztető (a **outlook flag reminder**) és határidő dátumokat a `Calendar` osztály segítségével.*

### 3. lépés: Nyomonkövetési beállítások alkalmazása
A `FollowUpManager.setOptions` metódus a jelzőt a `MapiMessage`‑hez csatolja.

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*A `FollowUpOptions` objektum tartalmazza a jelző összes részletét, amelyet a `FollowUpManager.setOptions`‑szel alkalmazunk.*

### 4. lépés: Üzenet mentése
Mentsd a jelölt üzenetet `.msg` fájlként, hogy az Outlook megjeleníthesse a jelzőt.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Az üzenet `.msg` fájlként kerül mentésre a csatolt jelzővel.*

## Hogyan állítsuk be a jelzőt a címzetteknek (2. funkció)?
Használd a `FollowUpManager.setFlagForRecipients`‑t a levél vázlatként jelölése után. Ez a metódus csak a címzett másolatához adja hozzá a nyomonkövetési jelzőt, a feladó nézetét változatlanul hagyva. A jelző alkalmazása előtt be kell állítani a `MessageFlags.MSGFLAG_UNSENT` értéket. A `FollowUpOptions` objektummal testreszabhatod a kezdő, emlékeztető és határidő dátumokat a metódus hívása előtt.

### Közvetlen válasz
Jelöld a levelet vázlatként a `MessageFlags.MSGFLAG_UNSENT` használatával, majd hívd a `FollowUpManager.setFlagForRecipients`‑t. Az Outlook csak a címzetteknek mutatja a jelzőt, a feladónak nem.

### Áttekintés
Néha szükséges, hogy a jelző **csak a címzetteknek** jelenjen meg. Ez a példa először vázlatként jelöli a levelet, majd hozzáadja a jelzőt.

#### 1. lépés: Vázlatként jelölés
`MessageFlags` egy MAPI felsorolás, amely az üzenet állapotát szabályozza. A `MSGFLAG_UNSENT` beállítása azt jelzi az Outlooknak, hogy az elem vázlat.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Az üzenet elküldetlenként való jelölése biztosítja, hogy az Outlook vázlatként kezelje.*

#### 2. lépés: Címzett jelző beállítása
`FollowUpManager.setFlagForRecipients` a jelzőt kizárólag a címzett másolatához csatolja.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*A jelző most csak a címzettek számára látható – egy klasszikus **flag for recipients** szituáció.*

## Hogyan jelöljük meg az Outlook nyomonkövetési jelzőt befejezettként (3. funkció)?
Töltsd be a .msg fájlt egy `MapiMessage`‑be, majd hívd a `FollowUpManager.completeFlag`‑et. Ez a jelző állapotát Befejezettre állítja, és egy pipa jelenik meg az Outlookban. A befejezés után mentsd az üzenetet a változás megőrzéséhez. Szükség esetén a `FlagCompleteTime` tulajdonság módosításával beállíthatod a befejezési időt audit célokra.

### Közvetlen válasz
Töltsd be a meglévő `.msg` fájlt egy `MapiMessage`‑be, hívd a `FollowUpManager.completeFlag`‑et, és mentsd a fájlt. A jelző állapota „Completed” lesz, és egy pipa jelenik meg az Outlookban.

### 1. lépés: Üzenet betöltése
`MapiMessage` képes beolvasni egy mentett `.msg` fájlt, teljes hozzáférést biztosítva annak MAPI tulajdonságaihoz.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 2. lépés: Befejezettként jelölés és mentés
`FollowUpManager.completeFlag` frissíti a jelző állapotát, majd elmented a változásokat.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*A jelző állapota „Completed” lesz, és a frissített fájl mentésre kerül.*

## Hogyan távolítsuk el az Outlook nyomonkövetési jelzőt (4. funkció)?
Nyisd meg a .msg fájlt `MapiMessage`‑vel, hívd a `FollowUpManager.clearFlag`‑et, majd mentsd az üzenetet. Ez eltávolítja az összes jelzőhöz kapcsolódó MAPI tulajdonságot, így az Outlook már nem jelenít meg nyomonkövetési jelzőt. Használd ezt, ha egy feladat törlésre vagy már nem releváns. Győződj meg róla, hogy minden egyedi emlékeztető tulajdonságot is törölsz, hogy elkerüld a maradék értesítéseket.

### Közvetlen válasz
Nyisd meg a `.msg` fájlt `MapiMessage`‑vel, hívd a `FollowUpManager.clearFlag`‑et, és mentsd a fájlt. Az üzenet már nem jelenít meg nyomonkövetési jelzőt az Outlookban.

### 1. lépés: Betöltés és jelző törlése
`FollowUpManager.clearFlag` eltávolítja az összes jelzőhöz kapcsolódó tulajdonságot az üzenetből.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Az üzenet jelző nélkül kerül mentésre.*

## Hogyan olvassuk ki a jelző beállításait (5. funkció)?
Hívd a `FollowUpManager.getOptions`‑t egy betöltött `MapiMessage`‑en, hogy egy `FollowUpOptions` objektumot kapj. Ez az objektum tartalmazza a kezdő, határidő, emlékeztető dátumokat és a jelző tárgyát, lehetővé téve a részletek megjelenítését vagy naplózását. Hasznos jelentésekhez és megfelelőségi auditokhoz.

### Közvetlen válasz
Használd a `FollowUpManager.getOptions`‑t egy betöltött `MapiMessage`‑en, hogy egy `FollowUpOptions` objektumot kapj, amely tartalmazza a kezdő, határidő, emlékeztető dátumokat és a jelző tárgyát. Ez hasznos jelentésekhez vagy megfelelőségi auditokhoz.

### 1. lépés: Beállítások lekérése
A visszakapott `options` objektum teljes betekintést nyújt a jelző konfigurációjába.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*A `options` objektum most már tartalmazza a kezdő, határidő és emlékeztető dátumokat, valamint a jelző tárgyát – hasznos, ha **read flag options**‑ra van szükség jelentéshez.*

## Gyakorlati alkalmazások
- **Task‑Management Integration:** Jelölt e‑mailek szinkronizálása Jira‑val, Trello‑val vagy Azure Boards‑szal.  
- **Automated Reminders:** Napi emlékeztető e‑mailek generálása függő nyomonkövetésekhez.  
- **Compliance Audits:** Jelző adatok exportálása szabályozási jelentésekhez, a jelző beállításainak programozott olvasásának lehetőségét kihasználva.

## Teljesítmény szempontok
- **Date Calculations:** Számold ki a dátumokat egyszer egy kötegben, ne cikluson belül.  
- **Resource Management:** Zárj le minden streamet vagy fájlkezelőt az üzenetek mentése után.  
- **Memory Usage:** Nagy postafiókokat darabokban dolgozz fel a heap nyomás elkerülése érdekében; az Aspose.Email képes több száz oldalas postafiókokat kezelni anélkül, hogy az egész fájlt a memóriába töltené.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A jelző nem jelenik meg az Outlookban | Az üzenet megfelelő `MessageFlags` nélkül lett mentve | Győződj meg róla, hogy a `setMessageFlags` `MSGFLAG_UNSENT`‑re van állítva a címzett jelzők alkalmazása előtt. |
| Mentés `AccessDeniedException`‑t dob | Helytelen fájlútvonal vagy hiányzó írási jogosultság | Ellenőrizd, hogy a kimeneti könyvtár létezik és az alkalmazásnak írási jogai vannak. |
| A dátumok egy nappal eltolódnak | Időzóna eltérés | Használd következetesen a `TimeZone.getTimeZone("GMT")`‑t vagy a helyi időzónádat. |

## Gyakran Ismételt Kérdések
**Q: Mi az Aspose.Email for Java?**  
A: Ez egy tiszta Java API, amely lehetővé teszi e‑mail fájlok (MSG, EML stb.) létrehozását, olvasását és manipulálását Outlook telepítése nélkül.

**Q: Hogyan szerezhetek ingyenes próbaverzió licencet?**  
A: Látogasd meg az [Aspose weboldalt](https://releases.aspose.com/email/java/) a 30‑napos próba letöltéséhez.

**Q: Beállíthatok több nyomonkövetési jelzőt egyetlen üzenethez?**  
A: Az Outlook csak egy jelzőt támogat üzenetenként, de további feladatadatokat tárolhatsz egyedi MAPI tulajdonságokban.

**Q: Az üzenet nem mentődik a jelző beállítása után. Mit ellenőrizhetek?**  
A: Ellenőrizd, hogy az `outputDir` útvonal érvényes-e, és hogy az alkalmazásnak van-e írási joga a megadott helyen.

**Q: Hogyan távolíthatok el jelzőket egyszerre sok üzenetről?**  
A: Iterálj a üzenetgyűjteményeden, és hívd a `FollowUpManager.clearFlag`‑t minden `MapiMessage`‑re.

## Források
- [Documentation](https://reference.aspose.com/email/java/)  
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)  
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Legutóbb frissítve:** 2026-07-27  
**Tesztelve:** Aspose.Email for Java 25.4 (JDK 16)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Outlook kategóriák kezelése Aspose.Email for Java-val – átfogó útmutató](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Outlook jegyzetek létrehozása Java-val az Aspose.Email segítségével – teljes útmutató](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Feladatok létrehozása a Microsoft Exchange-ben Aspose.Email for Java-val: teljes útmutató](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}