---
date: '2026-02-22'
description: Tanulja meg, hogyan állíthat be nyomon követési jelzőt az Outlookban
  az Aspose.Email for Java használatával, beleértve a jelzők beállítását, olvasását
  és eltávolítását a címzettek számára.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Hogyan állíts be Outlook követési jelzőt az Aspose.Email for Java használatával
url: /hu/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan állítsuk be az Outlook nyomon követési zászlót az Aspose.Email for Java segítségével

## Bevezetés
Ha már valaha is nehezen tudtad nyomon követni a fontos e‑maileket, tudod, mennyire értékes az Outlook **outlook follow up flag** funkciója. Ebben az útmutatóban megmutatjuk, **hogyan állítsunk be egy outlook follow up flag‑et** programozottan az Aspose.Email for Java segítségével, valamint bemutatjuk, hogyan **állíthatunk be outlook follow up flag‑et a címzetteknek**, és hogyan **távolíthatunk el egy outlook follow up flag‑et**, amikor a feladat befejeződött. A végére képes leszel automatizálni a feladatkövetést, emlékeztetőket és audit nyomvonalakat közvetlenül a Java kódból.

**Mit fogsz megtanulni**
- Követési zászló létrehozása és alkalmazása egy Outlook üzenetre.  
- Követési zászlók beállítása konkrét címzetteknek.  
- Zászló megjelölése befejezettként, majd későbbi eltávolítása.  
- Zászló beállításainak olvasása jelentéshez vagy megfelelőséghez.  

Készítsük elő a környezetet, mielőtt a kódba merülnénk.

## Gyors válaszok
- **Mit jelent a „hogyan állítsunk be follow‑up‑ot”?** Egy zászló hozzáadása kezdő dátummal, emlékeztetővel és határidővel egy Outlook elemhez.  
- **Melyik könyvtár szükséges?** Aspose.Email for Java (v25.4 vagy újabb).  
- **Szükség van licencre?** Igen, teljes funkcionalitáshoz próbaverzió vagy megvásárolt licenc szükséges.  
- **Beállíthatók csak a címzetteknek a zászlók?** Természetesen – használd a `FollowUpManager.setFlagForRecipients` metódust.  
- **Lehet később eltávolítani a zászlót?** Igen, hívd a `FollowUpManager.clearFlag` metódust.

## Mi az az Outlook Follow Up Flag?
Az Outlook follow up flag egy beépített feladatjelző, amely kezdő dátumot, emlékeztetőt és határidőt csatolhat bármely levélhez. Egy egyszerű e‑mailet nyomon követhető feladattá alakít, segítve téged és csapatodat a függőben lévő munkák nyomon követésében.

## Miért használjuk az Aspose.Email for Java‑t?
Az Aspose.Email egy tisztán Java‑alapú API, amely Outlook telepítése nélkül működik, lehetővé téve .msg fájlok manipulálását, zászlók beállítását és feladatok kezelését bármilyen platformon – tökéletes **automate outlook tasks**, háttérszolgáltatások vagy projekt‑menedzsment eszközökkel való integráció számára.

## Előfeltételek
- **Aspose.Email for Java** 25.4 vagy újabb verzió (más néven **aspose email java**).  
- **JDK 16+** telepítve.  
- Maven‑kompatibilis IDE (IntelliJ IDEA, Eclipse, stb.).  
- Alapvető Java ismeretek és e‑mail koncepciók ismerete.

## Aspose.Email for Java beállítása
### Maven konfiguráció
Add hozzá a következő függőséget a `pom.xml` fájlodhoz:

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

- **Ingyenes próba** – 30‑napos értékelés.  
- **Ideiglenes licenc** – meghosszabbított tesztelés.  
- **Teljes licenc** – örökös előfizetés.

Inicializáld a licencet minden e‑mail művelet előtt:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook Follow Up Flag beállítása (1. funkció)
### 1. lépés: Üzenet létrehozása és inicializálása
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Először egy `MailMessage`‑t építünk, beállítjuk a feladót/címzettet, majd átalakítjuk `MapiMessage`‑dé a zászlókezeléshez.*

### 2. lépés: Follow‑Up dátumok meghatározása (Outlook Flag Reminder)
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

### 3. lépés: Follow‑Up opciók alkalmazása
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*A `FollowUpOptions` objektum tartalmazza a zászló minden részletét, amelyet a `FollowUpManager.setOptions` metódussal alkalmazunk.*

### 4. lépés: Üzenet mentése
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Az üzenet `.msg` fájlként kerül mentésre a zászlóval együtt.*

## Hogyan állítsuk be a zászlót a címzetteknek (2. funkció)
### Áttekintés
Néha szükséges, hogy a zászló **csak a címzetteknek** jelenjen meg. Ez a példa először vázlatként menti az üzenetet, majd hozzáadja a zászlót.

#### 1. lépés: Vázlatként jelölés
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*A nem elküldött állapot biztosítja, hogy az Outlook vázlatként kezelje az üzenetet.*

#### 2. lépés: Címzett zászló beállítása
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*A zászló most csak a címzettek számára látható – klasszikus **flag for recipients** szituáció.*

## Hogyan jelöljük meg az Outlook Follow Up Flag-et befejezettként (3. funkció)
### 1. lépés: Üzenet betöltése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 2. lépés: Befejezettként jelölés és mentés
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*A zászló állapota „Completed”‑re változik, és a frissített fájl mentésre kerül.*

## Hogyan távolítsuk el az Outlook Follow Up Flag-et (4. funkció)
### 1. lépés: Betöltés és zászló törlése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Az üzenet a zászló nélkül kerül mentésre.*

## Hogyan olvassuk ki a zászló opciókat (5. funkció)
### 1. lépés: Opciók lekérdezése
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Az `options` objektum most tartalmazza a kezdő, határidő és emlékeztető dátumokat, valamint a zászló tárgyát – hasznos, ha **read flag options**‑t kell végezni jelentéshez.*

## Gyakorlati alkalmazások
- **Feladatkezelő integráció:** Zászlózott e‑mailek szinkronizálása Jira‑val, Trello‑val vagy Azure Boards‑szal.  
- **Automatikus emlékeztetők:** Napi emlékeztető e‑mailek generálása függőben lévő follow‑up‑okhoz.  
- **Megfelelőségi auditok:** Zászló adatok exportálása szabályozási jelentésekhez.

## Teljesítménybeli megfontolások
- **Dátumszámítások:** Számítsd ki a dátumokat egyszer egy kötegben, ne cikluson belül.  
- **Erőforrás-kezelés:** Zárd le a stream‑eket vagy fájl‑handle‑eket a mentés után.  
- **Memóriahasználat:** Nagy postafiókokat darabokban dolgozz fel, hogy elkerüld a heap nyomást.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A zászló nem jelenik meg Outlookban | Az üzenet nem megfelelő `MessageFlags`‑kel lett mentve | Győződj meg róla, hogy a `setMessageFlags` `MSGFLAG_UNSENT`‑re van állítva a címzett zászlók alkalmazása előtt. |
| Mentés `AccessDeniedException`‑t dob | Hibás fájlútvonal vagy hiányzó írási jogosultság | Ellenőrizd, hogy a kimeneti könyvtár létezik, és az alkalmazásnak van írási joga. |
| A dátumok egy nappal eltolódnak | Időzóna eltérés | Használd következetesen a `TimeZone.getTimeZone("GMT")`‑t vagy a helyi zónádat. |

## Gyakran feltett kérdések
**K: Mi az Aspose.Email for Java?**  
V: Egy tisztán Java‑alapú API, amely lehetővé teszi e‑mail fájlok (MSG, EML, stb.) létrehozását, olvasását és manipulálását Outlook telepítése nélkül.

**K: Hogyan szerezhetek be ingyenes próbalicencet?**  
V: Látogasd meg az [Aspose weboldalt](https://releases.aspose.com/email/java/) a 30‑napos próba letöltéséhez.

**K: Beállíthatok több follow‑up zászlót egyetlen üzenetre?**  
V: Az Outlook csak egy zászlót támogat üzenetenként, de további feladatadatokat tárolhatsz egyedi MAPI tulajdonságokban.

**K: Az üzenet nem mentődik a zászló beállítása után. Mit ellenőrizhetek?**  
V: Győződj meg róla, hogy az `outputDir` útvonal érvényes, és az alkalmazásnak van írási joga a megadott helyre.

**K: Hogyan távolíthatok el zászlókat sok üzenetből egyszerre?**  
V: Iterálj a üzenetgyűjteményen, és minden `MapiMessage`‑re hívd a `FollowUpManager.clearFlag` metódust.

## Források
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Utoljára frissítve:** 2026-02-22  
**Tesztelve:** Aspose.Email for Java 25.4 (jdk16)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}