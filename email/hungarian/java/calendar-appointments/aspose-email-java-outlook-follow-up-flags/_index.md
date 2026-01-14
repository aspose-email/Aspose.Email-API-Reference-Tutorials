---
date: '2025-12-19'
description: Tanulja meg, hogyan állíthat be nyomon követési zászlókat az Outlookban
  az Aspose.Email for Java használatával, beleértve, hogyan állíthat be Outlook nyomon
  követési zászlót, és hogyan távolíthatja el azt hatékonyan.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Hogyan állítsunk be nyomonkövetési jelzőket az Outlookban az Aspose.Email for
  Java használatával
url: /hu/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan állítsunk be követésjelzőket az Outlookban az Aspose.Email for Java segítségével

## Bevezetés
Ha valaha is nehézséget okozott a fontos e‑mailek nyomon követése, tudod, mennyire értékesek az Outlook követésjelzői. Ebben az útmutatóban bemutatjuk, hogyan állíthatók be programozottan a **követésjelzők** az Aspose.Email for Java segítségével, valamint azt, hogyan **állítható be Outlook követésjelző a címzetteknek**, és hogyan **távolítható el az Outlook követésjelző**, amikor egy feladat befejeződött. A végére képes leszel automatizálni a feladatkövetést, emlékeztetőket és audit nyomvonalakat közvetlenül a Java kódodból.

**Mit fogsz megtanulni**
- Követésjelző létrehozása és alkalmazása egy Outlook üzenethez.  
- Követésjelzők beállítása adott címzetteknek.  
- Jelző megjelölése befejezettként, majd későbbi eltávolítása.  
- Jelző beállításainak olvasása jelentéshez vagy megfelelőséghez.  

Készítsük elő a környezetet, mielőtt a kódba merülnénk.

## Gyors válaszok
- **Mit jelent a “hogyan állítsunk be követésjelzőt”?** Egy jelző hozzáadása kezdő, emlékeztető és határidő dátumokkal egy Outlook elemhez.  
- **Melyik könyvtár szükséges?** Aspose.Email for Java (v25.4 vagy újabb).  
- **Szükségem van licencre?** Igen, a teljes funkcionalitáshoz próba vagy megvásárolt licenc szükséges.  
- **Beállíthatok csak a címzetteknek jelzőket?** Természetesen – használd a `FollowUpManager.setFlagForRecipients` metódust.  
- **Lehet később eltávolítani egy jelzőt?** Igen, hívd a `FollowUpManager.clearFlag` metódust.

## Mi az a követésjelző?
A követésjelző egy Outlook funkció, amely egy e‑mailt feladattá jelöl, opcionálisan kezdő, emlékeztető és határidő dátumokkal. Segít neked és a csapatodnak a függőben lévő tevékenységek nyomon követésében.

## Miért használjuk az Aspose.Email for Java-t?
Az Aspose.Email egy tisztán Java API-t biztosít, amely Outlook telepítése nélkül működik, lehetővé téve .msg fájlok manipulálását, jelzők beállítását és feladatok kezelését bármilyen platformon – tökéletes backend szolgáltatásokhoz, automatizált munkafolyamatokhoz vagy projektmenedzsment eszközökkel való integrációhoz.

## Előfeltételek
- **Aspose.Email for Java** 25.4 vagy újabb verzió.  
- **JDK 16+** telepítve.  
- Maven‑kompatibilis IDE (IntelliJ IDEA, Eclipse, stb.).  
- Alapvető Java ismeretek és e‑mail fogalmak ismerete.

## Az Aspose.Email for Java beállítása

### Maven konfiguráció
Adja hozzá a következő függőséget a `pom.xml`-hez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése
Az Aspose.Email licencet igényel a termelésben való használathoz:

- **Ingyenes próba** – 30 napos értékelés.  
- **Ideiglenes licenc** – kiterjesztett tesztelés.  
- **Teljes licenc** – örökös előfizetés.

Inicializáld a licencet minden e‑mail művelet előtt:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementációs útmutató

### Hogyan állítsunk be követésjelzőket (1. funkció)

#### Áttekintés
Ez a szakasz bemutatja, hogyan hozzunk létre egy Outlook üzenetet, definiáljuk a kezdő/emlékeztető/határidő dátumokat, és alkalmazzuk a követésjelzőt.

#### 1. lépés: Üzenet létrehozása és inicializálása
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Először egy `MailMessage` objektumot építünk, beállítjuk a feladót/címzettet, majd átalakítjuk `MapiMessage`-re a jelzőkezeléshez.*

#### 2. lépés: Követés dátumainak meghatározása
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Itt a `Calendar` osztály segítségével állítjuk be a kezdő, emlékeztető és határidő dátumokat.*

#### 3. lépés: Követés opciók alkalmazása
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*A `FollowUpOptions` objektum tartalmazza a jelző összes részletét, amelyet a `FollowUpManager.setOptions` segítségével alkalmazunk.*

#### 4. lépés: Üzenet mentése
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Az üzenet `.msg` fájlként mentődik a jelzővel együtt.*

### Hogyan állítsunk be Outlook követésjelzőt a címzetteknek (2. funkció)

#### Áttekintés
Néha csak a címzetteknek kell jelzőt beállítani. Ez a példa először vázlatként jelöli az üzenetet, majd hozzáadja a jelzőt.

#### 1. lépés: Jelölés vázlatként
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Az üzenet elküldetlenként való jelölése biztosítja, hogy az Outlook vázlatként kezelje.*

#### 2. lépés: Címzett jelző beállítása
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*A jelző most már csak a címzettek számára látható.*

### Hogyan jelöljük be az Outlook követésjelzőt befejezettként (3. funkció)

#### Áttekintés
Amikor egy feladat kész, programozottan bejelölheted a jelzőt befejezettként.

#### 1. lépés: Üzenet betöltése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### 2. lépés: Befejezettként jelölés és mentés
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*A jelző állapota “Completed” (befejezett) lesz, és a frissített fájl mentésre kerül.*

### Hogyan távolítsuk el az Outlook követésjelzőt (4. funkció)

#### Áttekintés
Ha egy jelző már nincs szükség, teljesen törölhető.

#### 1. lépés: Betöltés és jelző törlése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Az üzenet jelző nélkül kerül mentésre.*

### Hogyan olvassuk ki a követésjelző opciókat (5. funkció)

#### Áttekintés
Audit vagy jelentés céljából előfordulhat, hogy ki kell olvasni a meglévő jelző beállításokat.

#### 1. lépés: Opciók lekérése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*A `options` objektum most már tartalmazza a kezdő, határidő és emlékeztető dátumokat, valamint a jelző tárgyát.*

## Gyakorlati alkalmazások
- **Feladatkezelő integráció:** Jelölt e‑mailek szinkronizálása Jira-val, Trello-val vagy Azure Boards-szal.  
- **Automatikus emlékeztetők:** Napi emlékeztető e‑mailek generálása függőben lévő követésekhez.  
- **Megfelelőségi auditok:** Jelző adatok exportálása szabályozási jelentésekhez.

## Teljesítménybeli megfontolások
- **Dátumszámítások:** Számold ki a dátumokat egyszer egy kötegben, ne cikluson belül.  
- **Erőforrás-kezelés:** Zárj le minden stream-et vagy fájlkezelőt az üzenetek mentése után.  
- **Memóriahasználat:** Nagy postafiókokat darabokban dolgozz fel a heap nyomás elkerülése érdekében.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A jelző nem jelenik meg az Outlookban | Az üzenet megfelelő `MessageFlags` nélkül lett mentve | Győződj meg róla, hogy a `setMessageFlags` `MSGFLAG_UNSENT` értékre van állítva a címzett jelzők alkalmazása előtt. |
| Mentés `AccessDeniedException` hibát dob | Helytelen fájlútvonal vagy hiányzó írási jogosultság | Ellenőrizd, hogy a kimeneti könyvtár létezik, és az alkalmazásnak van írási joga. |
| A dátumok egy nappal eltolódnak | Időzóna eltérés | Használd a `TimeZone.getTimeZone("GMT")`-t vagy a helyi zónát következetesen. |

## Gyakran feltett kérdések

**K: Mi az Aspose.Email for Java?**  
A: Ez egy tisztán Java API, amely lehetővé teszi e‑mail fájlok (MSG, EML, stb.) létrehozását, olvasását és manipulálását Outlook telepítése nélkül.

**K: Hogyan szerezhetek ingyenes próba licencet?**  
A: Látogasd meg az [Aspose weboldalt](https://releases.aspose.com/email/java/) a 30‑napos próba letöltéséhez.

**K: Beállíthatok több követésjelzőt egyetlen üzenetre?**  
A: Az Outlook csak egy jelzőt támogat üzenetenként, de további feladatadatokat tárolhatsz egyedi MAPI tulajdonságokban.

**K: Az üzenetem nem mentődik a jelző beállítása után. Mit ellenőrizhetek?**  
A: Győződj meg róla, hogy az `outputDir` útvonal érvényes, és az alkalmazásnak írási jogosultsága van a megadott helyen.

**K: Hogyan távolíthatok el jelzőket egyszerre sok üzenetből?**  
A: Iterálj a üzenetgyűjteményen, és minden `MapiMessage` esetén hívd a `FollowUpManager.clearFlag` metódust.

## Források
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}