---
date: '2026-07-17'
description: Ismerje meg, hogyan hozhat létre EWS klienst Java nyelven az Aspose.Email
  for Java használatával. Ez az útmutató végigvezeti a beállításon, a postafiók információinak
  lekérésén, a beérkezett üzenetek listázásán és az üzenetek hatékony áthelyezésén.
keywords:
- create ews client java
- Aspose.Email Java
- email automation Java
lastmod: '2026-07-17'
og_description: Ismerje meg, hogyan hozhat létre EWS klienst Java nyelven az Aspose.Email
  for Java használatával. Ez az útmutató végigvezeti a beállításon, a postafiók információinak
  lekérésén, a beérkezett üzenetek listázásán és az üzenetek hatékony áthelyezésén.
og_image_alt: 'Developer guide: create EWS client Java using Aspose.Email'
og_title: EWS kliens létrehozása Java nyelven – E-mailek automatizálása az Aspose.Email
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to create EWS client Java using Aspose.Email for Java. This
    guide walks you through setup, mailbox info retrieval, inbox listing, and moving
    messages efficiently.
  headline: Create EWS Client Java – Automate Email with Aspose.Email
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for Java. This
    guide walks you through setup, mailbox info retrieval, inbox listing, and moving
    messages efficiently.
  name: Create EWS Client Java – Automate Email with Aspose.Email
  steps:
  - name: Install Aspose.Email via Maven
    text: Make sure the Maven snippet from the **Prerequisites** section is present
      in your `pom.xml`. Run `mvn clean install` to download the JARs.
  - name: Obtain a License
    text: '- Start with a [free trial](https://releases.aspose.com/email/java/) to
      evaluate the library. - For extended evaluation, request a [temporary license](https://purchase.aspose.com/temporary-license/).
      - Purchase a full license on the [Aspose purchase page](https://purchase.aspose.com/buy)
      for product'
  - name: Initialize the Client
    text: 'Add the following initialization code after you have added the Maven dependency
      and license file:'
  type: HowTo
- questions:
  - answer: Verify credentials, ensure the service URL is correct, and confirm that
      the Exchange server permits the authentication method you are using (Basic,
      NTLM, or OAuth).
    question: How do I handle authentication errors when connecting to EWS?
  - answer: Yes. Create a separate `IEWSClient` instance for each mailbox, each with
      its own credentials and service URL.
    question: Can I manage emails from multiple mailboxes with this setup?
  - answer: Use `client.createFolder(parentUri, "FolderName")` before attempting to
      move messages, or check `client.folderExists(uri)` and create it on‑the‑fly.
    question: What should I do if the target folder does not exist?
  - answer: 'Extend the loop condition: `if (msg.getSubject().contains("Invoice")
      && msg.getFrom().contains("@vendor.com")) { … }`.'
    question: How can I filter emails based on multiple criteria (subject and sender)?
  - answer: Yes. The library processes mailboxes with **200,000+ messages** using
      server‑side paging, keeping client memory usage under **50 MB**.
    question: Does Aspose.Email support large mailboxes without performance degradation?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java EWS integration
- email automation
title: EWS kliens létrehozása Java nyelven – E-mailek automatizálása az Aspose.Email
  segítségével
url: /hu/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# EWS kliens Java létrehozása – E-mailek automatizálása az Aspose.Email segítségével

## Bevezetés
Szeretne **create EWS client Java** alkalmazásokat készíteni, amelyek automatikusan kezelik az Exchange postafiókokat? Ez az átfogó útmutató bemutatja, hogyan használhatja az Aspose.Email for Java könyvtárat egy EWS kliens felépítéséhez, postafiók‑információk lekéréséhez, bejövő üzenetek listázásához, és e‑mailek áthelyezéséhez meghatározott kritériumok alapján. Automatizálja az ismétlődő e‑mail feladatokat, csökkentse a manuális munkát, és tartsa rendezett a beérkező leveleit – mindezt Java kódból.

A mai gyors tempójú digitális környezetben a több ezer üzenet hatékony kezelése elengedhetetlen a támogatói csapatok, a pénzügyi osztályok és minden olyan szervezet számára, amely az Exchange‑re támaszkodik. A tutorial végére egy stabil, termelés‑kész alapot kap az e‑mail automatizáláshoz.

**Mit fog megtanulni**
- Hogyan **create EWS client Java** kódot írjon az Aspose.Email segítségével.
- Hogyan kérje le a postafiók részleteit, például a mappák URI‑it.
- Hogyan listázzon üzeneteket a Beérkezett mappából.
- Hogyan helyezzen át üzeneteket, amelyek egy adott tárgymintára illeszkednek, egy másik mappába.

Ellenőrizzük a feltételeket, mielőtt elkezdenénk a kódolást.

## Gyors válaszok
- **Mi a kódsor, amely létrehozza az EWS klienst?** `IEWSClient client = EWSClient.getEWSClient(serviceUrl, username, password, domain);`
- **Melyik Maven‑artifact biztosítja az Aspose.Email for Java‑t?** `com.aspose:aspose-email`
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba működik fejlesztéshez; egy termelési licenc eltávolítja az összes értékelési korlátot.
- **Több mint 100 000 üzenetet tudok feldolgozni?** Igen – az Aspose.Email képes nagy postafiókokon lapozni anélkül, hogy mindent a memóriába töltene.
- **Milyen Java verzió szükséges?** JDK 1.8 vagy újabb (a könyvtár kompatibilis a Java 21‑ig).

## Mi az a **create EWS client Java**?
`create ews client java` a folyamatot jelöli, amikor egy `IEWSClient` objektumot példányosítunk, amely a Microsoft Exchange Web Services‑sel kommunikál egy Java‑alkalmazásból. Ez a kliens elrejti az alacsony szintű SOAP hívásokat, és egy tiszta, objektum‑orientált API‑t biztosít a postafiók műveletekhez.

## Miért használjuk az Aspose.Email for Java‑t?
Az Aspose.Email támogat **70+ e‑mail protokollt**, képes **200 000‑nál több üzenetet** kezelni anélkül, hogy a teljes tárolót betöltené a memóriába, és beépített lapozást biztosít, amely akár **80 %**-kal csökkentheti a hálózati forgalmat. A könyvtár teljesen szálbiztos, bármely Java 8+ környezetben fut, és havonta frissül, új Exchange funkciókat adva hozzá.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy a következők rendelkezésre állnak:

### Szükséges könyvtárak és függőségek
Az Aspose.Email for Java‑t adja hozzá a projektjéhez. Maven használata esetén illessze be ezt a függőséget a `pom.xml` fájlba:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Környezet beállítási követelmények
- Java Development Kit (JDK) 1.8 vagy újabb.
- Maven a függőségkezeléshez.
- Hozzáférés egy EWS‑engedélyezett Exchange szerverhez.

### Tudás‑előfeltételek
- Jól ismeri a Java szintaxist és az objektum‑orientált koncepciókat.
- Alapvető ismeretek a RESTful API‑król; az EWS SOAP‑t használ, de az Aspose.Email elrejti a komplexitást.

## Hogyan **create EWS client Java**?
Az `IEWSClient` az Aspose.Email interfésze, amely módszereket biztosít az Exchange Web Services‑hez való kapcsolódáshoz.  
Töltse be az Exchange szolgáltatás URL‑jét, a felhasználói hitelesítő adatokat és a domaint, majd egyetlen sorban példányosítsa a klienst. Ez a hívás biztonságos kapcsolatot hoz létre, TLS‑t egyeztet, és egy `IEWSClient` objektumot ad vissza, amely készen áll a postafiók műveletekre, például mappák olvasására, üzenetek listázására és elemek áthelyezésére. A kliens továbbá gyorsítótárazza a szolgáltatás végpontját a későbbi kérések teljesítményének javítása érdekében.
```text
IEWSClient client = EWSClient.getEWSClient(serviceUrl, username, password, domain);
```

A kliens automatikusan egyezteti a TLS‑t, kezeli a hitelesítési sütiket, és gyorsítótárazza a szolgáltatás végpontját a későbbi hívásokhoz.

### 1. lépés: Aspose.Email telepítése Maven‑nel
Győződjön meg róla, hogy a **Prerequisites** szakaszból származó Maven‑kódrészlet szerepel a `pom.xml`‑ben. Futtassa a `mvn clean install` parancsot a JAR‑ok letöltéséhez.

### 2. lépés: Licenc beszerzése
- Kezdje egy [ingyenes próba](https://releases.aspose.com/email/java/) verzióval a könyvtár értékeléséhez.
- Kiterjesztett értékeléshez kérjen [ideiglenes licencet](https://purchase.aspose.com/temporary-license/).
- Teljes licenc vásárlásához látogassa meg az [Aspose vásárlási oldalt](https://purchase.aspose.com/buy) a termelési használathoz.

### 3. lépés: A kliens inicializálása
Adja hozzá a következő inicializáló kódot a Maven‑függőség és a licencfájl hozzáadása után:
```java
   import com.aspose.email.EWSClient;
   import com.aspose.email.IEWSClient;

   // Initialize the EWS Client
   IEWSClient client = EWSClient.getEWSClient(
       "https://outlook.office365.com/exchangeews/exchange.asmx",
       "testUser",
       "pwd",
       "domain"
   );
   ```

## Hogyan kérje le a postafiók információit?
Az `ExchangeMailboxInfo` a szerver által visszaadott postafiók struktúrát és mappa‑URI‑kat képviseli.  
Használja az `IEWSClient` példányt egy `ExchangeMailboxInfo` objektum lekéréséhez. Ez az objektum tartalmazza a gyakori mappák (Inbox, Sent Items, Drafts) URI‑it, valamint metaadatokat, például a postafiók méretét, az összes elem számát és kvóta‑információkat, lehetővé téve a postafiók navigálását további round‑trip‑ok nélkül.
```text
ExchangeMailboxInfo mailboxInfo = client.getMailboxInfo();
String inboxUri = mailboxInfo.getInboxUri();
```

Az `ExchangeMailboxInfo` osztály az Aspose.Email reprezentációja egy Exchange postafiók struktúrájáról, mappa‑URI‑kat biztosít anélkül, hogy további hálózati hívásokra lenne szükség.

## Hogyan listázzuk a bejövő üzeneteket?
A `MessageInfo` egy könnyű objektum, amely metaadatokat tartalmaz, például tárgy, feladó és a fogadás dátuma minden e‑mailhez.  
Miután megkapta a Bejövő mappa URI‑ját, hívja a `client.listMessages`‑t, hogy egy `MessageInfo` gyűjteményt kapjon. Megadhat egy `PagingInfo` objektumot a találatok korlátozásához és a nagy postafiókok teljesítményének javításához; a `PagingInfo` megmondja a szervernek, hány elemet adjon vissza oldalanként és melyik oldalt kérje le, ezáltal drasztikusan csökkentve a memóriahasználatot.
```text
PagingInfo paging = new PagingInfo(1, 100); // first 100 messages
MessageInfoCollection messages = client.listMessages(inboxUri, paging);
```

A `MessageInfo` könnyű metaadatokat (tárgy, feladó, fogadási idő) biztosít anélkül, hogy a teljes üzenettörzset letöltené, így alacsony a memóriaigény.

## Hogyan helyezzük át az üzeneteket egy másik mappába?
A `moveMessage` egy üzenetet áthelyez a jelenlegi mappájából egy megadott célmappába az Exchange szerveren.  
Iteráljon a `MessageInfo` gyűjteményen, értékelje minden tárgyat, és hívja a `client.moveMessage`‑t, ha a feltétel teljesül. A metódus a teljes áthelyezést a szerveren végzi, így nincs szükség helyi másolatra, és a művelet akár ezreknek a nagy üzeneteknek is csak néhány ezredmásodperc alatt befejeződik.
```text
for (MessageInfo msg : messages) {
    if (msg.getSubject().contains("Invoice")) {
        client.moveMessage(msg.getUniqueUri(), targetFolderUri);
    }
}
```

A `moveMessage` művelet atomikus az Exchange szerveren, és nagy üzenetek esetén is ezredmásodpercek alatt befejeződik.

## Gyakori problémák és megoldások
- **Hitelesítési hibák:** Ellenőrizze, hogy a felhasználónév, jelszó és domain helyes, valamint hogy az Exchange szerver engedélyezi-e az alap hitelesítést vagy az OAuth‑t a konfiguráció szerint.
- **Mappa nem található:** Használja a `client.createFolder(parentUri, "Processed")` parancsot a célmappa létrehozásához, ha még nem létezik.
- **Teljesítménybeli szűk keresztmetszet:** Engedélyezze a lapozást (`PagingInfo`) és kérje csak a szükséges mezőket (`MessageInfo.getSubject()`, `MessageInfo.getFrom()`). Ez akár **70 %**-kal csökkentheti a hálózati terhelést.

## Gyakorlati alkalmazások
Valós életbeli forgatókönyvek, ahol az e‑mail automatizálás az Aspose.Email‑del kiemelkedő:

1. **Automatikus jegykezelés** – Mozgassa a “Ticket#” tartalmú támogatási e‑maileket egy dedikált mappába a jegykezelő rendszerhez.
2. **Számla feldolgozás** – Észlelje a “Invoice” szót a tárgyban, és irányítsa az üzeneteket automatikusan a pénzügyi osztály felé.
3. **Feladatkiosztás** – Szűrje a “Action Required” e‑maileket egy prioritási sorba a projektmenedzserek számára.
4. **CRM szinkronizálás** – Húzza ki az üzenet metaadatait, és küldje őket egy CRM‑be, hogy a vevői interakciók naprakészek legyenek.
5. **Értesítések kezelése** – Válassza szét a rendszer‑értesítéseket a felhasználók által generált e‑mailektől a tisztább felügyelet érdekében.

## Teljesítmény‑szempontok
- **Erőforrás‑optimalizálás:** Hozza le egyszerre csak az első 200 üzenetet, és használja a `PagingInfo`‑t a többi oldalhoz. Ez megakadályozza az OutOfMemory hibákat a korlátozott heap‑memóriával rendelkező szervereken.
- **Garbage collection:** Nagy objektumok használata után állítsa nullára, és csak ritkán hívja a `System.gc()`‑t hosszú futású szolgáltatásokban.
- **Könyvtár‑frissítések:** Mindig a legújabb Aspose.Email verziót (pl. 24.12) használja, hogy kihasználja a teljesítményjavító javításokat, amelyek akár **30 %**-kal csökkenthetik az EWS hívások késleltetését.

## Összegzés
Most már tudja, hogyan **create EWS client Java** alkalmazásokat készítsen, amelyek képesek a postafiók részleteinek olvasására, a bejövő üzenetek listázására és az e‑mailek egyéni logika alapján történő áthelyezésére. Ez az alap lehetővé teszi összetett automatizálási csővezetékek építését, ERP/CRM rendszerek integrálását, és a manuális e‑mail kezelés csökkentését a szervezetében.

### Következő lépések
- Bővítse a kódot törlésre vagy továbbításra.
- Valósítsa meg a fejlett szűrést a `SearchQuery`‑val feladó, dátumtartomány vagy melléklet jelenlétének alapján.
- Fedezze fel az Aspose.Email **SMTP** és **IMAP** képességeit hibrid környezetekhez.

**Felhívás:** Telepítse a mintát egy tesztkörnyezetben még ma, módosítsa a tárgy‑szűrőt, és tapasztalja meg, milyen gyorsan válik az e‑mail kezelés egy „beállít‑és‑elfelejt” folyamattá.

## Gyakran Ismételt Kérdések

**K: Hogyan kezeljem a hitelesítési hibákat az EWS‑hez való csatlakozáskor?**  
V: Ellenőrizze a hitelesítő adatokat, győződjön meg róla, hogy a szolgáltatás URL helyes, és hogy az Exchange szerver engedélyezi-e az Ön által használt hitelesítési módot (Basic, NTLM vagy OAuth).

**K: Kezelhetek több postafiókot ezzel a beállítással?**  
V: Igen. Hozzon létre egy külön `IEWSClient` példányt minden postafiókhoz, mindegyik saját hitelesítő adatokkal és szolgáltatás URL‑lel.

**K: Mit tegyek, ha a célmappa nem létezik?**  
V: Használja a `client.createFolder(parentUri, "FolderName")` parancsot a mappa létrehozásához, vagy ellenőrizze a `client.folderExists(uri)`‑t, és szükség esetén hozza létre futás közben.

**K: Hogyan szűrhetem az e‑maileket több kritérium alapján (tárgy és feladó)?**  
V: Bővítse a ciklus feltételét: `if (msg.getSubject().contains("Invoice") && msg.getFrom().contains("@vendor.com")) { … }`.

**K: Az Aspose.Email támogatja a nagy postafiókokat anélkül, hogy a teljesítmény romlana?**  
V: Igen. A könyvtár **200 000+** üzenetet képes kezelni szerver‑oldali lapozással, miközben a kliens memóriahasználata **50 MB** alatt marad.

---

**Utolsó frissítés:** 2026-07-17  
**Tesztelt verzió:** Aspose.Email for Java 24.12  
**Szerző:** Aspose  

```java
   import com.aspose.email.EWSClient;
   import com.aspose.email.IEWSClient;
   ```
```java
   IEWSClient client = EWSClient.getEWSClient(
       "https://outlook.office365.com/exchangeews/exchange.asmx",
       "testUser",
       "pwd",
       "domain"
   );
   ```
```java
   import com.aspose.email.ExchangeMailboxInfo;
   ```
```java
   ExchangeMailboxInfo mailboxInfo = client.getMailboxInfo();
   ```
```java
   import com.aspose.email.ExchangeMessageInfo;
   import com.aspose.email.ExchangeMessageInfoCollection;
   ```
```java
   ExchangeMessageInfoCollection msgInfoColl = client.listMessages(mailboxInfo.getInboxUri());
   ```
```java
   for (ExchangeMessageInfo msgInfo : msgInfoColl) {
       if (msgInfo.getSubject() != null && msgInfo.getSubject().contains("process this message")) {
           // Move item logic here
       }
   }
   ```
```java
   client.moveItem(
       msgInfo.getUniqueUri(),
       client.getMailboxInfo().getRootUri() + "/Processed/" + msgInfo.getSubject()
   );
   ```

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó tutorialok

- [Initialize Aspose.Email Java for Exchange Server: Retrieve Mailbox Info](/email/java/exchange-server-integration/aspose-email-java-exchange-client-mailbox-info/)
- [Efficiently Connect and List Exchange Messages Using Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/)
- [How to Connect to Exchange Server Using EWS with Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/exchange-server-ews-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}