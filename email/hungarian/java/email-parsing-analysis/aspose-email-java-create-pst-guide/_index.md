---
date: '2026-06-08'
description: Ismerje meg, hogyan hozhat létre PST files-t az Aspose.Email for Java
  segítségével, beleértve a folder structures hozzáadásának módját és a PST content
  hatékony keresését. Lépésről‑lépésre útmutató.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Hogyan hozhat létre PST files-t az Aspose.Email for Java segítségével
url: /hu/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Az e‑mailkezelés elsajátítása az Aspose.Email for Java segítségével

Ha **how to create pst** fájlokat szeretnél programozottan létrehozni, jó helyen jársz. Ebben az útmutatóban lépésről lépésre végigvezetünk a Unicode PST fájl generálásának, a szabványos Outlook mappák hozzáadásának, az üzenetek importálásának és a kis‑ és nagybetűket figyelmen kívül hagyó keresések végrehajtásának folyamatán – mindezt az Aspose.Email for Java használatával. A végére egy újrahasználható kódmintát kapsz, amely egy néhány e‑mailtől több gigabájtos archívumokig skálázható.

## Gyors válaszok
- **Hogyan kezdjek hozzá?** Add hozzá az Aspose.Email Maven függőséget, szerezz be egy licencet, és példányosítsd a `PersonalStorage` osztályt.
- **Hozzáadhatok bejövő mappát?** Igen – hívd a `pst.getRootFolder().addSubFolder("Inbox")` metódust.
- **Támogatott a kis‑ és nagybetűket figyelmen kívül hagyó keresés?** Használd a `PersonalStorageQueryBuilder`‑t a `StringComparison.OrdinalIgnoreCase` beállítással.
- **Mekkora fájlméretet kezelhet?** Az Aspose.Email akár 2 GB‑os PST fájlokat is feldolgoz, anélkül hogy a teljes fájlt a memóriába töltené.
- **Szükség van fizetős licencre a termeléshez?** A végleges licenc eltávolítja a próbaverzió korlátait és feloldja a teljes teljesítményű funkciókat.

## Mi az a how to create pst?
**how to create pst** a programozott módon történő Outlook Personal Storage Table (PST) fájl létrehozását jelenti kóddal, nem pedig az Outlook felhasználói felületével. Az Aspose.Email for Java teljesen kezelt API‑t biztosít, amely Unicode PST fájlokat hoz létre, mappákat ad hozzá, és `MapiMessage` objektumokat tárol anélkül, hogy az Outlook telepítve lenne.

## Miért használjuk az Aspose.Email‑t PST létrehozásához?
Az Aspose.Email **50+** e‑mailhez kapcsolódó formátumot támogat (MSG, EML, MBOX, PST, stb.) és képes **2 GB‑ig** nagy PST fájlok feldolgozására, miközben a memóriahasználat **150 MB** alatt marad a lazy‑loading architektúra köszönhetően. Ez a kvantifikált képesség ideálissá teszi vállalati archiválásra, migrációra és megfelelőségi forgatókönyvekre.

## Előfeltételek

- **Java Development Kit (JDK)** – 16‑os vagy újabb verzió.
- **Maven** – a függőségkezeléshez.
- Alapvető Java szintaxis ismerete; előzetes PST tapasztalat nem szükséges.

## Hogyan hozzunk létre PST fájlt?

A `PersonalStorage` osztály egy PST fájlt képvisel, és metódusokat biztosít a létrehozásához, megnyitásához és tartalmának manipulálásához. Unicode PST létrehozásához hívd a `PersonalStorage.create()`‑t a kívánt fájlúttal és formátumverzióval. Ez a művelet egy modern PST‑t generál, amely nagy mappákat, Unicode karaktereket és hatékony streaminget támogat, így alkalmas kis‑ és vállalati szintű archiválási feladatokra egyaránt.

### 1. lépés: Maven függőség hozzáadása

Add hozzá az Aspose.Email Maven függőséget a `pom.xml`‑hez. Ez automatikusan letölti a szükséges binárisokat.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 2. lépés: Licenc beszerzése és alkalmazása

Elérhető egy ingyenes próbaverzió, de egy végleges licenc eltávolítja a kiértékelési korlátokat és engedélyezi a teljes sebességű feldolgozást.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Hogyan adjunk hozzá mappát a PST‑hez?

Hozd létre a kívánt mappaszerkezetet a PST gyökerénél, majd hivatkozz rá az üzenetek beszúrásakor. A `FolderInfo` objektum minden mappát képvisel, és tetszőlegesen egymásba ágyazható, lehetővé téve olyan struktúrák építését, mint a Beérkezett üzenetek, Elküldött elemek vagy egyedi projektmappák. A mappák hozzáadása könnyű művelet, amely nem tölti be az üzenettartalmat, így nagy PST‑k esetén is megőrzi a teljesítményt.

### 1. lépés: PersonalStorage inicializálása

A `PersonalStorage` osztály az Aspose.Email felső szintű objektuma, amely egyetlen PST fájlt képvisel a memóriában. Példányosítás után minden olvasási és írási művelet ezen az objektumon keresztül folyik.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### 2. lépés: Könyvtárak útvonalainak meghatározása

Állítsd be a forrás‑ és cél‑útvonalakat az e‑mail fájlokhoz és a PST kimeneti helyéhez.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### 3. lépés: PST fájl létrehozása

Használd a `PersonalStorage.create()`‑t a `FileFormatVersion.Unicode` paraméterrel, hogy egy modern Unicode PST‑t hozz létre, amely nagy mappákat és Unicode karaktereket támogat.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Hogyan keressünk a PST‑ben?

A `PersonalStorageQueryBuilder` egy építőosztály, amely PST tartalom keresési lekérdezéseinek összeállítására szolgál. A builder megfelelő kritériumokkal és a `StringComparison.OrdinalIgnoreCase` beállításával gyors, kis‑ és nagybetűket figyelmen kívül hagyó kereséseket végezhetsz a tárgyak, törzsek és egyedi tulajdonságok között, anélkül hogy a teljes PST‑t a memóriába töltenéd.

### 1. lépés: Keresési lekérdezés felépítése

Állíts össze egy lekérdezést, amely egy kulcsszót keres a tárgyban vagy a törzsben, figyelmen kívül hagyva a betűkészletet.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### 2. lépés: Lekérdezés végrehajtása és üzenetek lekérése

Futtasd a lekérdezést a célmappán, és iterálj a kapott `MapiMessage` gyűjteményen.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Előre definiált mappa létrehozása a PST‑ben

Egy előre definiált mappa, például az **Inbox**, hozzáadása segít hatékonyan szervezni az e‑mail adatokat.

### 1. lépés: PersonalStorage objektum inicializálása
Feltételezzük, hogy a `PersonalStorage` objektum (`pst`) már létre lett hozva, ahogy korábban bemutattuk.

### 2. lépés: Az „Inbox” mappa létrehozása

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Üzenetek hozzáadása egy PST mappához

Töltsd fel a PST mappádat e‑mail üzenetekkel, azokat fájlokból betöltve és konvertálva.

### 1. lépés: E‑mail üzenet betöltése

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### 2. lépés: Hozzáadás a PST mappához

Konvertáld a `MailMessage`‑t `MapiMessage`‑re, majd add hozzá:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Gyakorlati alkalmazások

Az Aspose.Email for Java nem csak PST fájlok létrehozásáról szól; egy sokoldalú eszköz számos felhasználási területtel:
- **E‑mail archiválás**: Automatizáld a vállalati e‑mailek PST‑be archiválását, támogatva akár 10 éves megőrzési szabályokat is.
- **Migrációs eszközök**: Zökkenőmentesen migrálj régi levelezőtárolókból (pl. MBOX) Outlook PST‑be egyetlen API‑hívással üzenetenként.
- **Adat‑elemzés**: Nyerd ki a metaadatokat, mint feladó, címzett és időbélyeg, üzleti intelligencia folyamatokhoz.
- **Biztonsági mentés**: Építs robusztus mentőeszközöket, amelyek inkrementális e‑mail változásokat tárolnak anélkül, hogy a teljes postafiókot újra feldolgoznák.

## Teljesítménybeli szempontok

Az Aspose.Email optimális működéséhez:
- **Erőforrás‑kezelés**: Mindig hívd a `pst.dispose()`‑t vagy használd a try‑with‑resources szerkezetet a natív kezelők gyors felszabadításához.
- **Kötegelt feldolgozás**: Kezeld az e‑maileket **500** elemes kötegekben, hogy a memóriahasználat kiszámítható maradjon.
- **Párhuzamosítás**: A könyvtár szálbiztos csak olvasási műveletekhez; íráskor szinkronizáld a hozzáférést a `PersonalStorage` példányhoz.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|-------|-------|----------|
| **OutOfMemoryError** nagy PST‑k kezelésekor | A teljes PST betöltése a memóriába | Engedélyezd a `PersonalStorage.setUseUnicode(true)`‑t és dolgozz üzenet‑stream‑ekkel. |
| **Folder not found** hiba | Hibás mappaútvonal‑kisbetű/​nagybetű eltérés | Használd a `StringComparison.OrdinalIgnoreCase`‑t a lekérdezésekben vagy normalizáld a mappaneveket. |
| **License not applied** | Licencfájl nem lett betöltve az első API‑hívás előtt | Töltsd be a licencet az alkalmazás indításakor, mielőtt bármilyen `PersonalStorage` objektumot létrehoznál. |

## Gyakran feltett kérdések

**Q: Mi a minimális Java verzió?**  
A: JDK 16 vagy újabb ajánlott a teljes kompatibilitáshoz az Aspose.Email for Java‑val.

**Q: Használhatom az Aspose.Email‑t licenc nélkül?**  
A: Igen, elérhető próbaverzió, de korlátozza a PST méretét **10 MB‑ra** és letilt bizonyos optimalizációkat.

**Q: Hogyan kezeljem hatékonyan a nagy PST fájlokat?**  
A: Dolgozz üzeneteket kötegekben, gyorsan szabadítsd fel a `MapiMessage` objektumokat, és engedélyezd a lazy loading‑ot a `PersonalStorage.setUseUnicode(true)`‑val.

**Q: Lehet-e mellékleteket hozzáadni a PST‑ben lévő e‑mailekhez?**  
A: Természetesen. A `MailMessage`‑t `MapiMessage`‑re konvertálva hívd a `mapiMsg.getAttachments().add(attachment)`‑t a fájlok beágyazásához.

**Q: Milyen támogatás érhető el a hibák elhárításához?**  
A: Az Aspose dedikált támogatási fórumot, részletes dokumentációt és e‑mailes támogatást biztosít licencelt ügyfeleknek.

## Források
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Utoljára frissítve:** 2026-06-08  
**Tesztelve:** Aspose.Email for Java 24.10  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipulate PST Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extract Email Attachments Java - Using Aspose.Email for PST Files – A Step‑by‑Step Guide](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}