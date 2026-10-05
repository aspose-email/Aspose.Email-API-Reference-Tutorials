---
date: '2026-10-02'
description: Tanulja meg, hogyan csatlakoztassuk az exchange-t és listázzuk az exchange
  public folders-t az Aspose.Email for Java segítségével. Ez a step‑by‑step útmutató
  bemutatja a Maven dependency-t és a code‑free setup-et.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Tanulja meg, hogyan csatlakoztassuk az exchange-t és listázzuk az
  exchange public folders-t az Aspose.Email for Java segítségével. Ez az útmutató
  bemutatja a Maven dependency-t, a licensing-et és a recursive message retrieval-t.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Hogyan csatlakoztassuk az exchange-t és listázzuk a public folders-t Java-ban
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Hogyan csatlakoztassuk az exchange-t és listázzuk a public folders-t Java-ban
url: /hu/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan csatlakoztassuk az Exchange-t és listázzuk a nyilvános mappákat Java-ban

## Bevezetés
A modern vállalatokban a Microsoft Exchange postafiókok programozott elérése lehetővé teszi az archiválás, a felügyelet és a jelentéskészítés feladatainak automatizálását. Ez az oktatóanyag bemutatja, hogyan **how to connect exchange** az Aspose.Email for Java-val, majd hogyan **list exchange public folders** rekurzívan. Megismerheted a szükséges Maven függőséget, a licencelési lépéseket és az API hívások pontos sorrendjét – további könyvtárak nélkül. A végére képes leszel bármely nyilvános mappából üzeneteket lekérni és helyben menteni.

## Gyors válaszok
- **Mi az első lépés?** Add the Aspose.Email Maven dependency to your `pom.xml`.  
- **Szükségem van licencre?** Igen—használjon ideiglenes licencet a kiértékeléshez, vagy vásároljon teljes licencet a termeléshez.  
- **Melyik osztály hozza létre a kapcsolatot?** `ExchangeClient` (or `ImapClient` for IMAP) handles authentication and server communication.  
- **Listázhatok almappákat automatikusan?** Igen—használja a rekurzív `listSubFolders` metódust, amelyet az API biztosít.  
- **Ez a megközelítés szálbiztos?** The client objects are not thread‑safe; create a separate instance per thread for concurrent workloads.

## Mi a 'how to connect exchange'?
**How to connect exchange** a Java alkalmazás hitelesítési folyamata egy helyi vagy felhőalapú Microsoft Exchange szerverrel, amely lehetővé teszi, hogy API hívásokat hajtsunk végre, például mappa felsorolást vagy üzenet lekérést. Az Aspose.Email elrejti a háttérben lévő EWS/IMAP protokollokat, egy egységes, konzisztens objektummodellt biztosítva.

## Miért listázzuk az Exchange nyilvános mappáit?
A nyilvános mappák listázása átláthatóvá teszi a hierarchikus struktúrát, amelyet a szervezetek megosztott postafiókok, terjesztőlisták és archiv tárolók számára használnak. Az Aspose.Email egyetlen hívással képes felsorolni **50+ public folders** és támogatja a több száz oldalas postafiókok feldolgozását anélkül, hogy az egész tárolót memóriába töltené, ezáltal a RAM fogyasztást akár 70 %-kal csökkentve.

## Előfeltételek
- **Aspose.Email for Java** — version 25.4 vagy újabb (a legújabb stabil kiadás).  
- **Java Development Kit (JDK)** — JDK 11 vagy újabb telepítve, és a `JAVA_HOME` beállítva.  
- **Maven** — a függőségkezeléshez és a build automatizáláshoz.  
- Alapvető Java szintaxis és Exchange koncepciók (postafiókok, mappák, EWS) ismerete.

## Az Aspose.Email for Java beállítása
A könyvtár integrálásához adja hozzá a Maven függőséget a projekt `pom.xml` fájljához. Ez a **maven dependency aspose email**, amire szüksége lesz.

### Maven függőség
Adja hozzá a következő kódrészletet a `pom.xml` `<dependencies>` eleméhez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzési lépések
Aspose.Email egy érvényes licencet igényel a teljes funkciók használatához:

- **Ingyenes próba** – Töltse le az ideiglenes licencet az [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/), hogy kiértékelje az API-t.  
- **Vásárlás** – Szerezzen be kereskedelmi licencet az Aspose portálon a termelési környezethez.

#### Alapvető inicializálás
Miután a Maven feloldotta a csomagot és rendelkezik licencfájllal, helyezze a `.lic` fájlt az osztályútvonalra, és inicializálja a könyvtárat:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Megvalósítási útmutató
Áttekintjük az egyes funkcionális blokkokat, a kulcskérdésekre közvetlen, tömör bekezdésekkel válaszolva, mielőtt a részletes lépésekhez érnénk.

### Hogyan csatlakoztassuk az Exchange-t?
Töltse be a `ExchangeClient`-et a szerver URL-jével, felhasználói hitelesítő adatokkal és a tartománnyal, majd hívja meg a `connect()` metódust. A kliens HTTPS munkamenetet hoz létre az Exchange Web Services (EWS) segítségével, és ellenőrzi a hitelesítő adatokat. Ha a kapcsolat sikertelen, az API részletes `AuthenticationException`-t dob, amely tartalmazza a HTTP állapotkódot a gyors hibaelhárításhoz.  
`ExchangeClient` az Aspose.Email osztálya, amely az Exchange Web Services kapcsolathoz kezel.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Hogyan listázzuk az Exchange nyilvános mappáit?
Hívja meg a `client.listPublicFolders()` metódust, hogy egy `FolderInfo` objektumok gyűjteményét kapja, amelyek minden felső szintű nyilvános mappát képviselik. A metódus metaadatokat ad vissza, mint a mappa neve, a teljes elemszám és egy egyedi azonosító, amely a későbbi hívásokhoz használható. Ez a hívás tipikus helyi telepítéseknél, legfeljebb 500 mappával, kevesebb mint 2 másodperc alatt befejeződik.  
`listPublicFolders()` egy `FolderInfo` objektumok gyűjteményét adja vissza.  
A `FolderInfo` metaadatokat tárol, például a megjelenített nevet és az elemszámot.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Hogyan jelenítsük meg a mappa információkat?
Iteráljon a `FolderInfo` gyűjteményen, és írja ki a `displayName` és `subFolderCount` értékeket. Ez a gyors áttekintés segít megérteni a hierarchiát, mielőtt mélyebb bejárásba kezdene. Nagy szervezetek esetén az API lapozhatja az eredményeket, oldalanként 100 mappát visszaadva, hogy alacsony maradjon a memóriahasználat.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Hogyan listázzuk egy mappa üzeneteit?
Hívja meg a `client.listMessages(folderId)` metódust, ahol a `folderId` az előző lépésben kapott azonosító. A metódus egy `MessageInfo` objektumok listáját adja vissza, amelyek tartalmazzák a tárgyat, a feladót és a fogadási dátumot. A `maxCount` paraméterrel korlátozhatja az eredményhalmazt, hogy ne terhelje túl a klienst nagyon nagy mappák feldolgozásakor.  
`listMessages(folderId)` egy `MessageInfo` objektumok listáját adja vissza.  
A `MessageInfo` alapvető e‑mail tulajdonságokat tartalmaz, például tárgy, feladó és fogadási dátum.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Hogyan töltsük le és mentsük el az üzeneteket?
Minden `MessageInfo` esetén használja a `client.fetchMessage(messageId)` metódust a teljes MIME tartalom letöltéséhez. Ezután írja a byte tömböt egy `.eml` fájlba a lemezen. Az API streameli a tartalmat, így még a 100 MB méretű üzenetek is memóriába töltés nélkül kezelhetők.  
`fetchMessage(messageId)` letölti a megadott e‑mail teljes MIME tartalmát.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Hogyan listázzuk rekurzívan az üzeneteket az almappákból?
Valósítson meg egy mélységi bejárást: kezdje egy felső szintű mappával, listázza almappáit a `client.listSubFolders(parentId)` metódussal, majd hívja meg ugyanazt az üzenet‑listázó rutinot minden gyermekre. Ez a minta biztosítja, hogy a nyilvános mappafa minden üzenete feldolgozásra kerüljön. A rekurzió mélységét csak a szerver mappahierarchiája korlátozza (általában < 20 szint).  
`listSubFolders(parentId)` visszaadja a megadott mappa közvetlen gyermekmappáit.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Gyakorlati alkalmazások
1. **Automatizált e‑mail archiválás** – Rendszeresen húzza le az összes nyilvános mappa üzenetét, és tárolja egy megfelelőségi archivumban.  
2. **Biztonsági mentési megoldások** – Tükrözze az Exchange nyilvános mappákat egy biztonságos fájlrendszerre vagy felhő tárolóba, garantálva az adat redundanciát.  
3. **Egyedi e‑mail kliensek** – Készítsen könnyű nézőket, amelyek csak a szükséges mappákat és üzeneteket jelenítik meg, csökkentve a UI komplexitását.

## Teljesítmény szempontok
- **Kapcsolat poolozás** – Használja újra egyetlen `ExchangeClient` példányt több művelethez, ahelyett, hogy minden mappához új klienst hozna létre.  
- **Lusta betöltés** – Kérje csak a szükséges metaadatokat (`listMessages` `maxCount` paraméterrel), és a teljes tartalmakat igény szerint töltse le.  
- **Objektumok felszabadítása** – Hívja meg a `client.dispose()`-t a kötegelt futás után, hogy felszabadítsa a HTTP kapcsolatokat és a szál‑lokális puffereket.  
- **Párhuzamos feldolgozás** – Ossza fel a felső szintű mappákat több szálra, mindegyik saját kliens példánnyal, a többmagos CPU-k hatékony kihasználásához.

## Gyakran ismételt kérdések

**Q: Használhatom ezt a kódot az Exchange Online (Office 365) környezetben?**  
A: Igen. Adja meg az Office 365 EWS végpontot (`https://outlook.office365.com/EWS/Exchange.asmx`) és használjon modern hitelesítést (OAuth) – az Aspose.Email alapból támogatja az OAuth tokeneket.

**Q: Mi van, ha egy mappa több mint 10 000 üzenetet tartalmaz?**  
A: Használja a `listMessages` túlterhelését, amely a `skip` és `take` paramétereket fogadja, hogy lapozzon az eredmények között, és a memóriahasználatot kontroll alatt tartsa.

**Q: Van korlátozás egyetlen letölthető e‑mail méretére?**  
A: Az API streameli a tartalmat, így akár 150 MB méretű üzenetek is támogatottak a Java heap korlátja nélkül, feltéve, hogy a JVM elegendő natív memóriával rendelkezik.

**Q: Kézzel kell kezelnem az SSL tanúsítványokat?**  
A: Alapértelmezés szerint az Aspose.Email a Java alap keystore‑t bízza meg. Ha az Exchange szerver ön‑aláírt tanúsítványt használ, importálja azt a JVM truststore‑ba, vagy a teszteléshez állítsa be a `client.setEnableSslVerification(false)` értéket.

**Q: Hogyan naplózhatom a műveleteket audit célokra?**  
A: Engedélyezze az Aspose.Email beépített naplózását a `Logger.setLevel(Level.INFO)` konfigurálásával, és irányítsa a kimenetet egy fájlba vagy megfigyelő rendszerbe.

## Összegzés
Most már rendelkezik egy teljes, termelés‑kész recepttel a **how to connect exchange** és a nyilvános mappák üzeneteinek rekurzív listázásához az Aspose.Email for Java használatával. A lépések lefedik a Maven beállítást, a licencelést, a kapcsolódást, a mappa felsorolást, az üzenet lekérést és a teljesítményhangolást. Bővítse ezt az alapot adatbázisokkal, felhő tárolóval vagy egyedi analitikai csővezetékekkel, hogy megfeleljen szervezete konkrét igényeinek.

---

**Utolsó frissítés:** 2026-10-02  
**Tesztelve a következővel:** Aspose.Email for Java 25.4  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan csatlakozzunk az Exchange Serverhez az Aspose.Email for Java használatával: Lépésről‑lépésre útmutató](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Hogyan csatlakozzunk és listázzuk az Exchange Server mappákat az Aspose.Email for Java használatával](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Exchange Server mappák kezelése az Aspose.Email for Java használatával: Átfogó útmutató](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}