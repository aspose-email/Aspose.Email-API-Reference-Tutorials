---
date: '2026-06-13'
description: Tanulja meg, hogyan olvassa be az MSG fájlokat és elemezze az MSG mellékleteket
  az Aspose.Email for Java használatával, hatékonyan kinyerve a delivery/read receipts
  és a vote results adatokat. Tartalmaz setup, code és best practices részeket.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Hogyan olvassuk be az MSG fájlokat az Aspose.Email for Java segítségével
url: /hu/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan olvassuk el az MSG fájlokat az Aspose.Email for Java segítségével

## Bevezetés

Az MSG fájlok programozott olvasása lehetővé teszi, hogy értékes nyomkövetési adatokat—kézbesítési visszaigazolásokat, olvasási megerősítéseket és szavazási eredményeket—szerezzünk meg az Outlook üzenetekből. Ebben az útmutatóban bemutatjuk, hogyan olvassuk el az MSG fájlokat az Aspose.Email for Java segítségével, áttekintjük a szükséges beállításokat, és hatékonyan demonstráljuk, hogyan nyerhetők ki a visszaigazolási és szavazási információk.

## Gyors válaszok
- **Melyik könyvtár kezeli az MSG elemzést?** Aspose.Email for Java.  
- **Kivonhatok olvasási visszaigazolásokat?** Igen, az API visszaadja a kézbesítési és olvasási időbélyegeket.  
- **Elérhetők a szavazati adatok?** Teljesen; lekérdezhető minden címzett szavazati válasza.  
- **Szükség van licencre?** A próba verzió tesztelésre működik; egy fizetett licenc eltávolítja a kiértékelési korlátokat.  
- **Melyik Java verzió szükséges?** Java 16 vagy újabb ajánlott.

## Mi az Aspose.Email for Java?

Az Aspose.Email for Java egy önálló Java könyvtár, amely lehetővé teszi e‑mail formátumok létrehozását, manipulálását és konvertálását anélkül, hogy a Microsoft Outlookra lenne szükség. Gazdag objektummodellt biztosít az MSG, EML, PST és számos egyéb formátumhoz, lehetővé téve a fejlesztők számára, hogy közvetlenül Java kódból dolgozzanak e‑mail adatokkal. (45 szó)

## Miért használjuk az Aspose.Email for Java-t MSG fájlok olvasásához?

Az Aspose.Email for Java **30+ e‑mail formátumot** támogat, és képes **500 MB**-ig terjedő MSG fájlokat feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené. A nagy teljesítményű elemző motor csökkenti a CPU és memória fogyasztást, így ideális nagy léptékű levéltár-feldolgozáshoz és valós‑idő analitikai forgatókönyvekhez. (48 szó)

## Előfeltételek

- **Könyvtárak és függőségek:** Aspose.Email for Java 25.4 vagy újabb verzió, valamint JDK 16+ futtatókörnyezet.  
- **IDE:** IntelliJ IDEA, Eclipse vagy bármely Java‑kompatibilis IDE Maven támogatással.  
- **Alapvető készségek:** Java szintaxis és objektum‑orientált koncepciók ismerete.

## Licenc megszerzése

Az Aspose.Email for Java használatához licenc szükséges:

- **Ingyenes próba:** Kezdje az ingyenes próba verzióval, amely elérhető az [Aspose weboldalán](https://releases.aspose.com/email/java/).  
- **Ideiglenes licenc:** Kérjen ideiglenes licencet a [vásárlási oldalról](https://purchase.aspose.com/temporary-license/).  
- **Vásárlás:** Ha elégedett a kiértékeléssel, vásároljon licencet a teljes funkciókhoz a [Aspose termékek vásárlása](https://purchase.aspose.com/buy) oldalon.  

## Hogyan nyerhetők ki az olvasási és kézbesítési visszaigazolási információk egy MSG fájlból?

Töltse be az MSG fájlt, iteráljon a címzettek között, és olvassa a `DeliveryTime` és `ReadTime` tulajdonságokat. Ez a megközelítés visszaadja a pontos időbélyegeket, amikor az egyes címzettek levelezőszervere kézbesítette az üzenetet és amikor a címzett megnyitotta, így pontos nyomkövetési adatokat biztosít az elemzéshez. (53 szó)

### 1. lépés: MSG fájl betöltése
A MapiMessage az Aspose.Email osztálya, amely egy Outlook MSG üzenetet képvisel.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### 2. lépés: Címzettek iterálása
A MapiRecipient egyetlen címzettet (To, CC vagy BCC) képvisel az MSG fájlban.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 3. lépés: Kézbesítési idő lekérése és kiírása
A DeliveryTime a MapiRecipient tulajdonsága, amely tartalmazza az időbélyeget, amikor az üzenet a címzett szerverére kézbesítésre került.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 4. lépés: Olvasási idő lekérése és kiírása
A ReadTime a MapiRecipient tulajdonsága, amely jelzi, mikor nyitotta meg a címzett az üzenetet, ha ez az információ elérhető.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Hogyan olvassuk el a szavazati eredményeket egy MSG fájlból?

Az üzenet betöltése után az API minden címzett szavazati válaszát és a válasz időpontját teszi elérhetővé, lehetővé téve a szavazási eredmények programozott összesítését. Ezeket az adatokat felhasználhatja összefoglaló jelentések készítésére vagy közvetlenül üzleti intelligencia irányítópultokba való betáplálásra a gyors döntéshozatal érdekében. (53 szó)

### 1. lépés: MSG fájl betöltése
A MapiMessage-et újra használjuk a MSG fájlba ágyazott szavazati információk eléréséhez.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### 2. lépés: Címzettek iterálása
A MapiRecipient hozzáférést biztosít minden résztvevő szavazati választásához és válaszidejéhez.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 3. lépés: Válasz lekérése és kiírása
A `VotingResponse` tulajdonság tartalmazza a tényleges szavazatot (pl. „Accept”, „Decline”, vagy egyedi opciók).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 4. lépés: Válasz időpontjának lekérése és kiírása
`VotingResponseTime` rögzíti, mikor adta le a címzett a szavazatát, lehetővé téve a szavazás tevékenységének időbeli elemzését.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Gyakorlati alkalmazások

1. **E‑mail kampány nyomon követése:** Nyílt arány és kézbesítési siker mérés a visszaigazolási időbélyegek elemzésével.  
2. **Felmérés elemzés:** Az Outlook szavazatok eredményeinek összegzése a gyors döntéshozatalhoz.  
3. **Ügyfél visszajelzés kezelése:** Válaszadatok átvitele CRM vagy analitikai platformokra a mélyebb betekintés érdekében.

Ezeknek az adatkinyeréseknek az adatbázisokkal vagy BI eszközökkel való integrálása növeli a nyers e‑mail adatok értékét.

## Teljesítmény szempontok

- Nagy MSG fájlok feldolgozása **darabokban** a memóriahasználat alacsonyan tartása érdekében.  
- **Streaming API-k** használata több ezer üzenet kezelésekor.  
- A címzett adatokat könnyű gyűjteményekben, például `ArrayList` vagy `HashMap` tárolása a gyors kereséshez.

## Gyakori problémák és megoldások

- **Null időbélyegek:** A hiányzó `ReadTime` általában azt jelenti, hogy a címzett még nem nyitotta meg az üzenetet.  
- **Nagy mellékletek:** Ha egy MSG hatalmas mellékleteket tartalmaz, engedélyezze a `LoadOptions.setPreserveEmbeddedResources(false)` beállítást, hogy kihagyja azok memóriába töltését.  
- **Kódolási problémák:** Győződjön meg a megfelelő kódlap beállításáról a `MailMessage.setCharset(Charset.forName("UTF-8"))` használatával nem ASCII tartalom olvasásakor.

## Gyakran ismételt kérdések

**Q: Hogyan kezeljem az 500 MB-nál nagyobb MSG fájlokat?**  
A: Ossza fel a fájlt kisebb szegmensekre, vagy használja a streaming API-t a részek beolvasásához a teljes memória betöltés nélkül.

**Q: Tárolhatom a kinyert adatokat közvetlenül egy adatbázisba?**  
A: Igen, térképezze a visszaigazolási és szavazási mezőket az adatbázis sémájára, és használjon JDBC‑t vagy ORM‑et a mentéshez.

**Q: Működik a könyvtár Linux környezetben?**  
A: Teljesen; az Aspose.Email for Java platform‑független, és bármely, támogatott JDK‑val rendelkező operációs rendszeren fut.

**Q: Van mód a mellékletek kinyerésére a visszaigazolások olvasása közben?**  
A: Használja a `MailMessage.getAttachments()` metódust az MSG betöltése után; a metódus visszaadja az összes beágyazott fájl gyűjteményét.

**Q: Milyen támogatási lehetőségek állnak rendelkezésre, ha hibákat találok?**  
A: Lépjen kapcsolatba a hivatalos Aspose Email Fórumon a közösségi segítségért, vagy nyisson egy támogatási jegyet érvényes licenccel.

## Források
- **Dokumentáció:** [Aspose Email Dokumentáció](https://reference.aspose.com/email/java/)  
- **Dokumentáció (duplikált):** [Aspose Email Dokumentáció](https://reference.aspose.com/email/java/)  
- **SDK letöltése:** [Aspose Email Letöltések](https://releases.aspose.com/email/java/)  
- **Letöltési szakasz:** [Letöltési szakasz](https://releases.aspose.com/email/java/)  
- **Licenc vásárlása:** [Aspose termékek vásárlása](https://purchase.aspose.com/buy)  
- **Ingyenes próba:** Kezdje a [Ingyenes próba verzió](https://releases.aspose.com/email/java/) verzióval  
- **Ideiglenes licenc:** [Ideiglenes licenc kérése](https://purchase.aspose.com/temporary-license/)  
- **Támogatási fórum:** [Aspose Email Fórum](https://forum.aspose.com/c/email/10)  
- **Támogatási fórum (duplikált):** [Aspose Email Fórum](https://forum.aspose.com/c/email/10)

---

**Utolsó frissítés:** 2026-06-13  
**Tesztelve a következővel:** Aspose.Email for Java 25.4  
**Szerző:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Kapcsolódó oktatóanyagok

- [Hogyan töltsünk be és elemezzünk Outlook MSG fájlokat az Aspose.Email for Java segítségével: Átfogó útmutató](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [MSG konvertálása EML-re és mellékletek kezelése az Aspose.Email for Java segítségével](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Beágyazott mellékletek kinyerése Java – MSG fájlok az Aspose.Email segítségével](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}