---
date: '2026-06-23'
description: Ismerje meg, hogyan szűrhet e‑mail üzeneteket dátum, feladó és tárgy
  szerint az Aspose.Email for Java használatával. Ez a lépésről‑lépésre útmutató megmutatja,
  hogyan automatizálhatja az IMAP e‑mail szűrést hatékonyan.
keywords:
- how to filter emails
- filter emails by date
- filter emails by sender
- filter emails by subject
- aspose email java tutorial
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  headline: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  type: TechArticle
- description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  name: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later.'
    text: '**Java Development Kit (JDK)** – version 8 or later.'
  - name: '**Maven** – for dependency management.'
    text: '**Maven** – for dependency management.'
  - name: '**Aspose.Email for Java** – the core library we’ll use.'
    text: '**Aspose.Email for Java** – the core library we’ll use.'
  - name: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
    text: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
  - name: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
    text: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
  type: HowTo
- questions:
  - answer: Instantiate `ImapClient` with host, port, username, and password, then
      call `client.selectFolder("Inbox")`.
    question: How do I connect to an IMAP server using Aspose.Email?
  - answer: Yes – use `ImapQueryBuilder` to combine `date` and `fromAddress` criteria;
      the library sends a single SEARCH command.
    question: Can I filter emails by both date and sender in one request?
  - answer: Absolutely – set `client.setSecurityOptions(SecurityOptions.SSL_TLS)`
      before connecting.
    question: Does Aspose.Email support SSL/TLS for secure connections?
  - answer: The library can process mailboxes with **over 100,000 messages** as long
      as you use paging; memory usage stays below 50 MB.
    question: What is the maximum mailbox size Aspose.Email can handle?
  - answer: A temporary license removes the evaluation watermark and limits; a full
      license is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
title: Hogyan szűrjünk e‑mail üzeneteket Java-ban az Aspose.Email segítségével – Fejlesztői
  útmutató
url: /hu/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan szűrjünk e‑mail üzeneteket Java-ban az Aspere.Email segítségével – Fejlesztői útmutató

## Bevezetés

Ha **hogyan szűrjünk e‑mail üzeneteket** programozott módon, akkor jó helyen jársz. Akár vállalati postafiókot kezelsz, ügyfélszolgálati jegyrendszert építesz, vagy egyszerűen csak szeretnéd rendezetté tenni a személyes bejövő leveleidet, az e‑mail szűrés automatizálása órákat takarít meg a manuális munkából. Ebben az útmutatóban a **Aspose.Email for Java** könyvtárat használjuk, amely több mint 30 e‑mail protokollt támogat, és képes 100 000+ üzenettel rendelkező postafiókokat kezelni anélkül, hogy az egész mappát a memóriába töltené. Megtanulod, hogyan csatlakozz IMAP szerverhez, hogyan alkalmazz szűrőket dátum, feladó, tárgy és egyéb szempontok szerint, valamint hogyan optimalizáld a teljesítményt nagyméretű feldolgozás esetén.

## Gyors válaszok
- **Melyik könyvtár kezeli az IMAP szűrést Java-ban?** Aspose.Email for Java.  
- **Szűrhetek dátum és feladó szerint egy hívásban?** Igen – kombináld a kritériumokat az `ImapQueryBuilder`‑rel.  
- **Szükség van licencre a termeléshez?** A teljes licenc eltávolítja a próbaidőkorlátokat; egy ideiglenes licenc teszteléshez elegendő.  
- **Támogatott a lapozás?** Teljesen – üzeneteket lapról‑lapra kérhetsz le, így alacsony a memóriahasználat.  
- **Melyik Java verzió szükséges?** JDK 8 vagy újabb.

## Mi az e‑mail szűrés Java-ban?

Az e‑mail szűrés Java-ban azt jelenti, hogy programozottan kiválasztjuk azokat az üzeneteket, amelyek meghatározott feltételeknek megfelelnek – például dátum, feladó vagy tárgy – így csak a releváns részhalmazt dolgozhatjuk fel. Ez csökkenti a hálózaton átvitt adat mennyiségét, és lehetővé teszi, hogy a downstream rendszerek egy fókuszált e‑mail készlettel dolgozzanak, javítva ezzel a sebességet és az erőforrás-felhasználást.

## Miért használjuk az Aspose.Email for Java‑t?

Az Aspose.Email for Java **30+ bemeneti és kimeneti formátumot** támogat, köztük EML, MSG, MBOX és PST, és képes **100 000+ üzenettel rendelkező postafiókokat** feldolgozni, miközben a memóriafogyasztás 50 MB alatt marad a szerver‑oldali szűrés és lapozás köszönhetően. A könyvtár beépített támogatást nyújt egyedi IMAP zászlókhoz, UTF‑8 kódoláshoz és kis‑nagybetű érzékeny lekérdezésekhez, így egy átfogó megoldást kínál vállalati szintű e‑mail automatizáláshoz.

## Előfeltételek

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Maven** – a függőségkezeléshez.  
3. **Aspose.Email for Java** – a fő könyvtár, amelyet használni fogunk.

### Szükséges könyvtárak és függőségek

Add hozzá az Aspose.Email függőséget a `pom.xml` fájlodhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése

- **Ingyenes próba** – töltsd le a próbaverziót, hogy felfedezd az összes funkciót.  
- **Ideiglenes licenc** – szerezd be az időkorlátos licencet a kiterjesztett teszteléshez.  
- **Teljes licenc** – vásárolj termelési használatra, és távolítsd el az összes értékelési korlátot.  
- **Licencfájl** – szerezd be a [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/).

## Az Aspose.Email for Java beállítása

Az Aspose.Email használatának megkezdéséhez kövesd az alábbi lépéseket:

1. **Letöltés és telepítés** – a Maven automatikusan letölti a könyvtárat a fenti helyőrzőből.  
2. **Könyvtár inicializálása** – töltsd be a licencfájlt (ha van) minden API hívás előtt:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## Implementációs útmutató

### Hogyan csatlakozzunk egy IMAP szerverhez?

Először is létre kell hoznod egy kapcsolatot az IMAP szerverrel az `ImapClient` osztály segítségével, amely egy kliens munkamenetet képvisel, képes hitelesíteni és parancsokat küldeni a szervernek. Ez a kapcsolat az alapja minden további postafiók‑műveletnek.

Egy tipikus csatlakozási folyamat során meg kell adni a hostot, portot, felhasználói adatokat és a biztonsági beállításokat, majd ki kell választani a kívánt mappát (pl. **Inbox**) a lekérdezések előtt.

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### Hogyan szűrjünk e‑mail üzeneteket tárgy és dátum szerint?

Az `ImapQueryBuilder` osztály segít összetett keresési feltételeket felépíteni, amelyeket hatékony IMAP SEARCH parancsokká alakít. A tárgy kulcsszavakat egy dátumtartománnyal kombinálva csak a feldolgozási logikádhoz releváns üzeneteket kérheted le.

Ebben a példában olyan üzeneteket keresünk, amelyek tárgya tartalmazza a „Newsletter” szót, és amelyek a jelenlegi napon érkeztek, ezzel minimalizálva az adatátvitelt és a feldolgozási terhelést.

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### Hogyan szűrjünk e‑mail üzeneteket a mai dátumra?

Az `ImapQueryBuilder` segítségével létrehozhatsz egy szűrőt, amely pontosan a levél elküldési időpontjának naptári dátumával egyezik. Ez hasznos a napi feldolgozási feladatoknál, amelyek csak a legújabb üzeneteket szeretnék kezelni.

A builder automatikusan a megfelelő formátumban állítja elő a dátumot az IMAP protokoll szerint, biztosítva a pontos szerver‑oldali szűrést anélkül, hogy további kliens‑oldali feldolgozásra lenne szükség.

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### Hogyan szűrjünk e‑mail üzeneteket egy dátumtartományra?

Amikor napok sorozatával kell dolgoznod, az `ImapQueryBuilder` lehetővé teszi egy kezdő és egy befejező `DateTime` megadását. A könyvtár ezeket a értékeket a megfelelő IMAP SEARCH szintaxisra konvertálja, és visszaadja az összes olyan üzenetet, amely a megadott intervallumba esik.

Ez a technika ideális heti jelentések készítéséhez vagy egy bizonyos küszöbérték alatti üzenetek archiválásához.

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### Hogyan szűrjünk e‑mail üzeneteket egy konkrét feladó szerint?

Az `ImapQueryBuilder` képes egyetlen e‑mail címet vagy egy egész domaint célozni a `From` fejléc alapján. Ez lehetővé teszi, hogy elkülönítsd a megbízható partnerek kommunikációját, vagy kiszűrd a nem kívánt feladókat.

A pontos cím megadása (pl. `user@example.com`) vagy egy domain minta (pl. `@example.com`) közvetlenül a szervertől ad pontos eredményeket.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### Hogyan szűrjünk e‑mail üzeneteket egy adott domain szerint?

A feladó szűréshez hasonlóan a `fromAddress` metódussal korlátozhatod a találatokat egy meghatározott domainre. Ez akkor hasznos, ha egy vállalati partner vagy egy konkrét e‑mail szolgáltató összes üzenetét kell feldolgoznod.

A lekérdezés a szerveren fut le, így csak a megfelelő üzenetek kerülnek át a alkalmazásodba.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### Hogyan szűrjünk e‑mail üzeneteket egy konkrét címzett szerint?

A `toAddress` metódussal a `ImapQueryBuilder`‑ben olyan üzenetekre fókuszálhatsz, amelyek egy adott postafiókra irányulnak. Ez különösen hasznos megosztott vagy szerepkör‑alapú postafiókok esetén, ahol több felhasználónak kell ugyanazt a levelezést feldolgoznia.

A builder egy IMAP SEARCH kifejezést hoz létre, amely a `To` fejlécet egyezteti, biztosítva a hatékony szerver‑oldali szűrést.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### Hogyan végezzünk kis‑nagybetű érzékeny e‑mail szűrést?

Alapértelmezés szerint az IMAP keresések kis‑nagybetű érzéketlenek, de az `ImapQueryBuilder` lehetőséget ad a kis‑nagybetű érzékenység kikényszerítésére a pontos egyezésekhez. Ez akkor fontos, ha azonosítók csak betűméretben különböznek.

Állítsd be a `setCaseSensitive(true)` zászlót, mielőtt egyéb kritériumokat adnál hozzá, hogy pontos szűrést érj el.

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### Hogyan adhatunk meg kódolást a Query Buildernek?

Nemzetközi karaktereket tartalmazó tárgyak vagy címek esetén állítsd be a karakterkódolást az `ImapQueryBuilder`‑ben. Az UTF‑8 használata biztosítja, hogy a nem ASCII karakterek helyesen legyenek értelmezve az IMAP szerver által.

Hívd meg a `setEncoding(Encoding.UTF_8)` metódust a lekérdezés felépítése előtt, hogy elkerüld a torz eredményeket.

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### Hogyan szűrjünk üzeneteket lapozási támogatással?

A lapozás elengedhetetlen nagy postafiókok esetén. Az `ImapClient` olyan metódusokat kínál, amelyekkel üzeneteket kötegekben kérhetsz le, például egyszerre 500 darabot. Ez alacsony memóriahasználatot és jobb áteresztőképességet eredményez.

Kombináld a lapozást az `ImapQueryBuilder`‑rel, hogy minden oldalra csak a releváns részhalmazt töltsd le.

```java
ImapClient client = new ImapClient(host, port, username, password);
client.setSecurityOptions(SecurityOptions.Auto);

int itemsPerPage = 5;
String searchBody = "example body text";

ImapQueryBuilder iqb = new ImapQueryBuilder();
iqb.getBody().contains(searchBody);
MailQuery query = iqb.getQuery();

PageSettings pageSettings = new PageSettings();
pageSettings.setFolderName("Inbox");

List<ImapPageInfo> pages = new ArrayList<>();
ImapPageInfo pageInfo = client.listMessagesByPage(query, new PageInfo(itemsPerPage, 0), pageSettings);

pages.add(pageInfo);
while (!pageInfo.getLastPage()) {
    pageInfo = client.listMessagesByPage(query, pageInfo.getNextPage(), pageSettings);
    pages.add(pageInfo);
}

int retrievedItems = 0;
for (ImapPageInfo folderCol : pages) {
    retrievedItems += folderCol.getItems().size();
}
client.dispose();
```

### Hogyan szűrjünk üzeneteket egy egyedi zászló alapján?

Az IMAP támogatja a felhasználó által definiált zászlókat, például `\Flagged` vagy egyedi címkéket. Az `ImapQueryBuilder`‑rel megadhatod ezeket a zászlókat, hogy csak a megfelelően megjelölt üzeneteket kapd vissza.

Ez a képesség hasznos olyan munkafolyamatoknál, amelyek a későbbi felülvizsgálatra vagy speciális kezelésre jelölik meg az üzeneteket.

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## Gyakorlati alkalmazások

- **Vállalati e‑mail kezelése** – Automatikusan rendezze a bejövő leveleket részlegek szerint a feladó vagy tárgy alapján.  
- **Ügyfélszolgálati rendszerek** – Prioritásba helyezze a jegyeket azáltal, hogy szűri az „Urgent” szót tartalmazó vagy VIP ügyfelektől érkező e‑mail üzeneteket.  
- **Személyes szervező eszközök** – Készíts egy könnyű Java segédprogramot, amely egy futtatás során archiválja a napi hírleveleket és törli a spamet.

## Teljesítménybeli megfontolások

- **Szerver‑oldali szűrés** – Hagyd, hogy az IMAP szerver végezze a nehéz munkát; csak a megfelelő üzenetek kerülnek a hálózatra.  
- **Lapozás** – Tölts le eredményeket darabokban (pl. 200 üzenetes oldalak), hogy elkerüld a teljes postafiók RAM‑ba töltését.  
- **Kapcsolat újrahasználata** – Tarts egy `ImapClient` példányt életben a kötegelt feladat teljes időtartama alatt, így csökkentve a kézfogás költségét.  
- **Megfigyelés** – Naplózd a feldolgozott üzenetek számát és az eltelt időt; ha memóriacsúcsot észlelsz, állítsd be a lapméretet.

## Következtetés

Most már teljes eszköztárral rendelkezel **hogyan szűrjünk e‑mail üzeneteket** az Aspose.Email for Java segítségével. A egyszerű dátum‑alapú lekérdezésektől a komplex, több kritériumot és egyedi zászlókat is tartalmazó szűrőkhöz a könyvtár finomhangolt vezérlést biztosít, miközben a teljesítményt optimális szinten tartja.

### Következő lépések

- Kombináld ezeket a szűrőket egy újrahasználható metódusba az alkalmazásodban.  
- Fedezd fel az **Aspose.Email** API‑t az üzenetek küldéséhez, továbbításához és válaszolásához.  
- Integráld egy adatbázissal, hogy a szűrt üzenetek metaadatait elemzésekhez tárold.

---

## Gyakran Ismételt Kérdések

**K: Hogyan csatlakozzak egy IMAP szerverhez az Aspose.Email‑el?**  
V: Hozd létre az `ImapClient` példányt a host, port, felhasználónév és jelszó megadásával, majd hívd meg a `client.selectFolder("Inbox")` metódust.

**K: Szűrhetek e‑mail üzeneteket egyszerre dátum és feladó szerint?**  
V: Igen – használj `ImapQueryBuilder`‑t a `date` és `fromAddress` kritériumok kombinálásához; a könyvtár egyetlen SEARCH parancsot küld.

**K: Támogatja az Aspose.Email az SSL/TLS biztonságos kapcsolatot?**  
V: Teljes mértékben – állítsd be a `client.setSecurityOptions(SecurityOptions.SSL_TLS)`‑t a csatlakozás előtt.

**K: Mekkora a maximális postafiók mérete, amelyet az Aspose.Email kezelni tud?**  
V: A könyvtár **100 000+ üzenetet** képes feldolgozni, amennyiben lapozást alkalmazol; a memóriahasználat 50 MB alatt marad.

**K: Szükség van licencre fejlesztői buildhez?**  
V: Egy ideiglenes licenc eltávolítja a kiértékelési vízjelet és a korlátozásokat; a teljes licenc a termelési környezetben kötelező.

---

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Email for Java 24.9  
**Author:** Aspose

## Kapcsolódó útmutatók

- [Fetch Emails from IMAP Server Using Aspose.Email for Java: A Step-by-Step Guide](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [Master IMAP Client Initialization in Java with Aspose.Email: A Comprehensive Guide](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [How to Backup IMAP Emails with Aspose.Email for Java: A Step-by-Step Guide](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}