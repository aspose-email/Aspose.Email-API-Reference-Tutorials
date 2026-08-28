---
date: '2026-08-11'
description: Ismerje meg, hogyan mozgathatja a pst mappákat és üzeneteket az Aspose.Email
  for Java segítségével – egy step‑by‑step útmutató a pst hatékony áthelyezéséhez.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Ismerje meg, hogyan mozgathatja a pst mappákat és üzeneteket az Aspose.Email
  for Java segítségével néhány kódsorral. Ez az útmutató a setup, a subfolders áthelyezése,
  az individual items, valamint a large PST files legjobb gyakorlatait tárgyalja.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Hogyan mozgassuk a pst mappákat és üzeneteket az Aspose.Email Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Hogyan mozgassuk a pst mappákat és üzeneteket az Aspose.Email Java segítségével
url: /hu/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan mozgassuk a pst mappákat és üzeneteket az Aspose.Email Java segítségével

A hatékony e‑mail kezelés elengedhetetlen, amikor nagy Outlook PST fájlokat kell átszervezni. Ebben az útmutatóban megtanulja, hogyan **hogyan mozgassuk a pst** mappákat és üzeneteket programozott módon az Aspose.Email for Java segítségével, lehetővé téve az automatikus takarítást, migrációt és archiválást Outlook indítása nélkül. A teljes API részletekért tekintse meg a [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Gyors válaszok
- **Melyik könyvtárat használják?** Aspose.Email for Java  
- **Mozgathatok mind mappákat, mind egyedi üzeneteket?** Igen – használja a `moveItem`‑t üzenetekhez és a `moveSubfolders`‑t teljes mappákhoz  
- **Szükségem van licencre a termeléshez?** Érvényes Aspose licenc szükséges a kereskedelmi telepítésekhez  
- **Melyik Java verzió ajánlott?** Java 16 vagy újabb a legjobb teljesítményért  
- **Szükség van mintap PST fájlra?** Bármely Outlook‑által generált PST működik; létrehozhat egyet Outlooktal vagy használhat egy tesztfájlt  

## Mit jelent a pst mozgatása Java fejlesztésben?

A pst mozgatása azt jelenti, hogy programozott módon áthelyezünk mappákat vagy e‑mail elemeket egy Personal Storage Table (PST) fájlon belül. Ez lehetővé teszi a tömeges takarítás, régi levelek archiválása vagy a tartalom áthelyezése a levelező tárolók között Outlook manuális beavatkozása nélkül, növelve a hatékonyságot és csökkentve az emberi hibákat.

## Miért használja az Aspose.Email for Java‑t a pst adatok mozgatásához?

A pst adatokat az Aspose.Email segítségével mozgathatja, mert egy **pure‑Java API**‑t biztosít, amely bármely operációs rendszeren működik, **több mint 100 GB** PST fájlokat támogat, és **akár 500 000 elemet percenként** képes feldolgozni standard szerver hardveren. A könyvtár részletes kivételeket is kínál, így gyorsan megtalálhatja a problémákat.

## Előfeltételek
- Aspose.Email for Java (legújabb verzió)  
- JDK 16+ (vagy újabb)  
- Maven vagy Gradle build rendszer  
- Egy PST fájl teszteléshez (bármely Outlook‑által generált fájl)

## Az Aspose.Email for Java beállítása
Az Aspose.Email használatához adja hozzá a Maven függőséget a `pom.xml` fájlhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzési lépések
1. **Free trial** – kezdje egy ingyenes próbaverzióval, hogy felfedezze az Aspose.Email funkciókat.  
2. **Temporary license** – szerezzen be egy ideiglenes licencet a kiterjesztett használathoz az [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/).  
3. **Purchase** – fontolja meg egy teljes licenc vásárlását, ha a könyvtár megfelel a termelési igényeinek. Az ár részleteiért tekintse meg az [Aspose vásárlási lehetőségeit](https://purchase.aspose.com/buy).  

### Alap inicializálás és beállítás
Győződjön meg róla, hogy a könyvtár helyesen hivatkozott, mielőtt PST fájlokkal dolgozna:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Hogyan mozgassuk a pst mappákat és üzeneteket
Az alábbiakban a fő műveletek találhatók, amelyekre szüksége lesz, ha hatékonyan szeretné **hogyan mozgassuk a pst** elemeket.

### PST fájl inicializálása és elérése
`PersonalStorage` az Aspose.Email fő osztálya a PST fájlok megnyitásához és manipulálásához.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### 1. lépés: PST fájl betöltése
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### 2. lépés: Előre definiált mappák elérése
- **Beérkezett üzenetek mappa**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Törölt elemek mappa**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Alcsoport áthelyezése egy másik mappába a PST-ben
`FolderInfo` egy mappát képvisel egy PST fájlon belül, és módszereket biztosít az alcsoportok áthelyezéséhez.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### 1. lépés: Forrás- és célmappák elérése
```java
pst.moveItem(subfolder, deletedItems);
```

#### 2. lépés: Egy adott alcsoport lekérése a Beérkezett üzenetek mappából
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### 3. lépés: Az egész alcsoport áthelyezése
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Egyedi üzenetek áthelyezése mappák között a PST-ben
`MessageInfoCollection` egy `MessageInfo` objektumok gyűjteményét tartalmazza, amelyek mindegyike egy e‑mail üzenetet képvisel.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### 1. lépés: Üzenetek lekérése egy adott alcsoportból
```java
inbox.moveSubfolders(deletedItems);
```

#### 2. lépés: Az első üzenet áthelyezése a Törölt elemek mappába
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Minden alcsoport áthelyezése egy mappáról egy másikra a PST-ben
`moveSubfolders` egyetlen hívással áthelyezi az összes gyermekmappát egy forrásból egy célba.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### 1. lépés: Forrás- és célmappák elérése
```java
subfolder.moveContents(deletedItems);
```

#### 2. lépés: Move all subfolders
CODE_BLOCK_PLACEHOLDER_15_END

### Egy alcsoport összes tartalmának áthelyezése egy másik mappába a PST-ben
`moveAllContents` (egy egyedi ciklus a `moveItem` használatával) képes áthelyezni minden üzenetet egy alcsoporton belül.

CODE_BLOCK_PLACEHOLDER_16_END

#### 1. lépés: Forrás- és célmappák elérése
CODE_BLOCK_PLACEHOLDER_17_END

#### 2. lépés: Egy adott alcsoport lekérése a Beérkezett üzenetek mappából
CODE_BLOCK_PLACEHOLDER_18_END

#### 3. lépés: Az alcsoport összes tartalmának áthelyezése
CODE_BLOCK_PLACEHOLDER_19_END

## Gyakorlati alkalmazások
Moving pst folders and messages is useful for:
- **Adat migráció** – postafiókok áthelyezése Outlookról egy másik levelezőrendszerre.  
- **E‑mail archiválás** – régi levelek automatikus rendezése archiv mappákba.  
- **Takarítási műveletek** – a beérkezett üzenetek rendetlenségének csökkentése elavult elemek archiv vagy törlés mappákba való áthelyezésével.

## Teljesítmény szempontok
Nagy PST fájlok kezelésekor az Aspose.Email for Java használatával kövesse ezeket a tippeket:
- **Erőforrás-használat optimalizálása** – zárja be a `PersonalStorage` objektumokat gyorsan a try‑with‑resources vagy explicit `dispose` használatával.  
- **Memória-kezelés** – dolgozzon elemeket kötegekben, ahelyett, hogy egy egész mappát memóriába töltene; ez csökkenti a heap nyomást a JVM‑eken.

### Legjobb gyakorlatok
- Mindig szabadítsa fel a PST erőforrásokat a műveletek után.  
- Ellenőrizze a mappa létezését a mozgatás megkísérlése előtt, hogy elkerülje a `InvalidOperationException`‑t.

## Gyakran ismételt kérdések

**Q: Mi az a PST fájl?**  
A: A PST (Personal Storage Table) fájl az Outlook saját formátuma e‑mail üzenetek, névjegyek, naptár elemek és egyéb postafiók adatok helyi tárolására.

**Q: Használhatom az Aspose.Email for Java‑t kereskedelmi projektekben?**  
A: Igen, kereskedelmi célra is használható, amennyiben érvényes licencet szerez be a [Aspose vásárlási lehetőségein](https://purchase.aspose.com/buy) keresztül.

**Q: Hogyan kezeljem a kivételeket PST fájlokkal dolgozva az Aspose.Email használatával?**  
A: Tegye kódját `try‑catch` blokkokba, hogy elkapja a `IOException`, `InvalidOperationException` vagy Aspose‑specifikus kivételeket, majd naplózza a hiba részleteit vagy szükség szerint újra dobja.

**Q: Milyen rendszerkövetelmények vannak a kód futtatásához?**  
A: Szüksége van JDK 16 vagy újabb verzióra és egy kompatibilis IDE‑re, mint például IntelliJ IDEA vagy Eclipse. Az Aspose.Email JAR‑nak a projekt osztályútvonalán kell lennie.

**Q: Hol találok további forrásokat az Aspose.Email for Java‑ról?**  
A: Látogassa meg a hivatalos dokumentációt a [Aspose Email Java Reference](https://reference.aspose.com/email/java/) oldalon.

**Q: Támogatja az Aspose.Email a jelszóval védett PST fájlokat?**  
A: Igen, titkosított PST‑ket nyithat meg a jelszó megadásával a `PersonalStorage.fromFile` hívásakor.

**Q: Hogyan ellenőrizhetem, hogy a mozgatási művelet sikeres volt?**  
A: A `moveItem` vagy `moveSubfolders` hívása után kérdezze le a célmappát a `getContents()` vagy `getSubFolders()` metódusokkal, hogy megerősítse a mozgatott elemek jelenlétét.

## Források
- **Dokumentáció**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **API részletek**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Letöltés**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Vásárlás**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Ingyenes próba**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Ideiglenes licenc**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Utoljára frissítve:** 2026-08-11  
**Tesztelve ezzel:** Aspose.Email for Java 25.4 (JDK 16)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Tömeges PST üzenetek frissítése Aspose.Email for Java-val: Átfogó útmutató](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Hogyan vonjunk ki Outlook PST üzeneteket az Aspose.Email for Java használatával: Teljes útmutató](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Üzenetek átvitele PST fájlok között az Aspose.Email for Java-val: Átfogó útmutató](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}