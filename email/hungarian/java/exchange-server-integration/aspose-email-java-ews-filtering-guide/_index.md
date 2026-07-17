---
date: '2026-07-17'
description: 'Hogyan szűrjünk e-maileket az Aspose.Email Java és EWS használatával:
  tanulja meg a date, sender, és subject szűrési technikákat, hogy hatékonyabbá tegye
  postafiókját.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Hogyan szűrjünk e-maileket az Aspose.Email Java és EWS használatával.
  Fedezze fel a date, sender, és subject szűrési technikákat, hogy rendezett maradjon
  a postafiókja.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Hogyan szűrjünk e-maileket az Aspose.Email Java & EWS segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Hogyan szűrjünk e-maileket az Aspose.Email Java & EWS útmutatóval
url: /hu/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Az e‑mail szűrés elsajátítása az Aspose.Email Java és EWS segítségével: Teljes útmutató

## Bevezetés

**Hogyan szűrjünk e‑mailt** hatékonyan alapvető képesség mindenki számára, aki a Microsoft Exchange‑szel vagy bármely modern postafiókkal dolgozik. Akár egy vállalati szintű automatizálást építő fejlesztő vagy, akár egy magánszemély, aki rendben szeretné tartani a beérkező leveleit, a megfelelő szűrési technikák elsajátítása órákat spórolhat meg a kézi munkában. Ebben az útmutatóban végigvezetünk az Aspose.Email for Java és az Exchange Web Services (EWS) használatán, bemutatva, hogyan szűrjünk dátum, feladó, tárgy, domain, címzett szerint, és akár több feltételt kombináljunk logikai operátorokkal.

### Mit fogsz megtanulni
- Technika az üzenetek szűrésére EWS használatával Java‑ban.  
- E‑mail szűrése dátum, feladó, tárgy stb. alapján.  
- Lapozás (paging) támogatásának megvalósítása nagy postafiókok kezeléséhez.  
- Gyakorlati alkalmazások ezeknek a szűrési módszereknek valós helyzetekben.  
- Teljesítménybeli szempontok és legjobb gyakorlatok az Aspose.Email Java‑val.

A tutorial végére képes leszel tiszta, teljesítményorientált Java kódot írni, amely pontosan azokat az üzeneteket húzza le egy Exchange szerverről, amikre szükséged van.

## Gyors válaszok
- **Mi a fő könyvtár?** Aspose.Email for Java.  
- **Melyik protokollt használja?** Exchange Web Services (EWS).  
- **Szűrhetek dátumtartomány szerint?** Igen – használja a `DateTime` kritériumot a `SearchFilter`‑ben.  
- **Támogatott a lapozás?** Teljes mértékben, az API biztosítja az `ItemView`‑t offset/limit paraméterekkel.  
- **Szükségem van licencre a termeléshez?** Igen, egy kereskedelmi licenc eltávolítja a kiértékelési korlátokat.

## Mi az Aspose.Email for Java?
Az Aspose.Email for Java egy átfogó API, amely programozott hozzáférést biztosít e‑mail szerverekhez, MIME üzenetekhez és az Exchange Web Services‑hez Outlook vagy bármely más kliens nélkül. Absztrahálja a mögöttes protokollokat, így a fejlesztő a üzleti logikára koncentrálhat. A könyvtár támogatja mind a helyi Exchange szervereket, mind az Exchange Online‑t, egységes API‑t kínálva különböző telepítési scenáriókhoz.

## Miért használjuk az Aspose.Email-et EWS‑sel?
Az Aspose.Email több mint **50** e‑mail protokollt támogat, és óránként **több százezer** üzenetet képes feldolgozni, miközben a memóriahasználat **100 MB** alatt marad a streaming architektúra köszönhetően. Ez a kvantifikált teljesítmény ideálissá teszi vállalati szintű postafiók‑automatizálásra. Emellett beépített támogatást nyújt az OAuth‑nak és a modern hitelesítésnek, egyszerűsítve a biztonságos kapcsolódást az Office 365 környezetekhez.

## Előfeltételek

- **Szükséges könyvtárak**: Az Aspose.Email könyvtárat kell a projektbe belefoglalni.  
- **Környezet beállítása**: Kész fejlesztői környezet Java alkalmazásokhoz szükséges.  
- **Tudás előfeltételek**: A Java programozás és e‑mail protokollok ismerete előnyös.

## Az Aspose.Email for Java beállítása

### Maven telepítés
Addja hozzá a következő függőséget a `pom.xml` fájlhoz:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzése
- **Ingyenes próba**: Kezdje egy ingyenes próbaverzióval, hogy felfedezze az Aspose.Email képességeit.  
- **Ideiglenes licenc**: Szerezzen be egy ideiglenes licencet a hosszabb értékeléshez.  
- **Vásárlás**: Fontolja meg egy teljes licenc megvásárlását, ha az eszköz megfelel az igényeinek.

Inicializálja és állítsa be az Aspose.Email‑et a szükséges csomagok importálásával, és hozza létre a kapcsolatot az e‑mail szerverrel EWS hitelesítő adatok használatával. Ez a lépés elengedhetetlen a postafiók adatok programozott eléréséhez.

## Hogyan szűrjünk e‑mailt EWS használatával Java‑ban?

`ExchangeService` az Aspose.Email osztálya, amely egy kapcsolatot képvisel egy Exchange szerverrel.  
`SearchFilter` határozza meg a keresési feltételeket a szerveren.  
`FindItems` végrehajtja a keresést és visszaadja a megfelelő elemeket.  
`ItemView` szabályozza a lapozást és az egy kérésben visszakapott elemek számát.

Töltsön be egy `ExchangeService` példányt a hitelesítő adataival, hozzon létre egy `SearchFilter`‑t a kívánt feltételekkel, majd hívja meg a `FindItems`‑t egy `ItemView`‑val, hogy csak a szükséges üzeneteket kapja meg. Ez az egy‑soros minta – csatlakozás → szűrés → lekérés – lefedi a legtöbb esetet, és nagy postafiókoknál a lapozás engedélyezésével skálázható.

## Implementációs útmutató

### Üzenetek szűrése EWS használatával

#### Áttekintés
A szűrés lehetővé teszi, hogy csak azokat az e‑mail üzeneteket kapja meg, amelyek bizonyos feltételeknek megfelelnek, például egy adott tárgy vagy dátum alapján, közvetlenül a postafiókjából.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Magyarázat**: A kód kapcsolatot hoz létre a postafiókjával, és egy lekérdezést hoz létre, amely a tárgyában ‘Newsletter’ szöveget tartalmazó e‑mailt szűri ki egy adott dátum alapján.

### Hogyan szűrjünk e‑mailt a mai dátum szerint?

`SearchFilter.IsEqualTo` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság egy adott értékkel egyezik.  
`DateTimeReceived` az a tulajdonság, amely azt jelzi, mikor érkezett az e‑mail.

Töltse be a jelenlegi dátumot, építsen egy `SearchFilter.IsEqualTo` szűrőt a `DateTimeReceived` tulajdonságra, és hajtsa végre a lekérdezést. Ez csak azokat az üzeneteket adja vissza, amelyeket a kód futtatásának napján kaptak, így a napi feldolgozó szkriptek egyszerűek lesznek. Kombinálhatja ezt a szűrőt további feltételekkel, például feladóval vagy tárggyal, hogy tovább szűkítse a napi eredményeket.

### Hogyan szűrjünk e‑mailt dátumtartomány szerint?

`SearchFilter.IsGreaterThanOrEqualTo` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság értéke nagyobb vagy egyenlő egy megadott értékkel.  
`SearchFilter.IsLessThanOrEqualTo` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság értéke kisebb vagy egyenlő egy megadott értékkel.  
`SearchFilter.And` több szűrőt kombinál úgy, hogy minden feltételnek teljesülnie kell.

Határozzon meg egy kezdő és egy befejező `DateTime`‑t, kombinálja őket a `SearchFilter.IsGreaterThanOrEqualTo` és a `SearchFilter.IsLessThanOrEqualTo`‑val, majd használja a `SearchFilter.And`‑t a két szűrő összekapcsolásához. Az eredményhalmaz minden olyan üzenetet tartalmaz, amely a megadott időablakon belül van. Ez a megközelítés lehetővé teszi, hogy bármilyen egyedi időszakra – például az utolsó negyedévre vagy egy konkrét projekt időtartamára – lekérje a kommunikációkat.

### Hogyan szűrjünk e‑mailt konkrét feladó szerint?

`SearchFilter.IsEqualTo` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság egy adott értékkel egyezik.

Hozzon létre egy `SearchFilter.IsEqualTo` szűrőt a `From` tulajdonságra a feladó e‑mail címével. Ez elkülöníti az összes üzenetet az adott kontaktustól, ami ideális a prioritásos bejövő levelekhez vagy megfelelőségi ellenőrzésekhez. Használhatja a `SearchFilter.ContainsSubstring`‑t is részleges egyezésekhez, ha a pontos cím nem ismert, vagy domain szerint szeretne szűrni.

### Hogyan szűrjünk e‑mailt konkrét domain szerint?

`SearchFilter.ContainsSubstring` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság tartalmaz egy megadott részkarakterláncot.

Használja a `SearchFilter.ContainsSubstring`‑t a `From` tulajdonságra a domain karakterláncával (pl. “@example.com”). Ez minden olyan e‑mailt lekér, amely az adott domainről származik, ami hasznos a partnerek vagy beszállítók monitorozásához. A domain‑specifikus szűrőt dátumkritériummal kombinálva nyomon követheti a domain‑specifikus kommunikációkat időben, ami segíti a biztonsági auditokat.

### Hogyan szűrjünk e‑mailt konkrét címzett szerint?

`SearchFilter.IsEqualTo` egy olyan szűrőt hoz létre, amely azon elemeket egyezteti, ahol egy tulajdonság egy adott értékkel egyezik.

Alkalmazza a `SearchFilter.IsEqualTo`‑t a `ToRecipients` gyűjteményre a célcímre. Ez akkor hasznos, amikor egy adott postafiókra vagy elosztólistára küldött üzeneteket kell ellenőrizni. Több címzett esetén, akik közös domaint használnak, a `SearchFilter.ContainsSubstring`‑t is használhatja részleges egyezésekhez.

### Hogyan kombináljuk a lekérdezéseket AND logikával?

`SearchFilter.And` több szűrőt kombinál úgy, hogy minden feltételnek teljesülnie kell.

Láncoljon több `SearchFilter` objektumot a `SearchFilter.And`‑val. Például kombináljon egy feladó szűrőt egy tárgy szűrővel, hogy csak a megbízható feladótól érkező hírleveleket kapja meg. Az AND operátor biztosítja, hogy csak azok az elemek kerüljenek vissza, amelyek minden megadott feltételnek megfelelnek, így a találathalmazzáshoz csak a legrelevánsabb üzenetek maradnak.

### Hogyan kombináljuk a lekérdezéseket OR logikával?

`SearchFilter.Or` egyesíti a szűrőket úgy, hogy bármelyik feltétel egyezhet.

Használja a `SearchFilter.Or`‑t, ha bármelyik feltételnek egyeznie kell – tökéletes olyan üzenetek lekéréséhez, amelyek vagy egy adott feladó **vagy** bizonyos kulcsszavakat tartalmaznak. Az OR logika szélesíti a keresést, hogy minden releváns kommunikációt lefedjen több kategóriában, anélkül, hogy kritikus információk kimaradnának.

## Gyakori buktatók és tippek

- **A lapozás elengedhetetlen**: Ha 1 000 eletnél nagyobb postafiókokkal dolgozik, mindig használjon `ItemView`‑t oldalmérettel a timeoutok elkerülése érdekében.  
- **Időzóna kezelése**: Az EWS UTC‑ben adja vissza a dátumokat; konvertálja a helyi zónájába a összehasonlítás előtt.  
- **Kerülje a teljes postafiók átvizsgálását**: Mindig alkalmazzon `SearchFilter`‑t a szerver oldalon; a kliens‑oldali szűrés sávszélességet és memóriát pazarol.  
- **Pro tipp**: Cache‑elje az `ExchangeService` objektumot az alkalmazás élettartama alatt, hogy csökkentse a hitelesítési terhet.

## Gyakran feltett kérdések

**K: Használhatom ezt a megközelítést Office 365‑tél?**  
A: Igen, az Aspose.Email működik az Office 365 Exchange Online‑nal, ha a szolgáltatás URL‑jét a `https://outlook.office365.com/EWS/Exchange.asmx` címre állítja.

**K: Támogatja az Aspose.Email az OAuth hitelesítést?**  
A: Teljes mértékben – használja az `OAuthCredentials`‑t a hitelesítéshez felhasználói jelszavak tárolása nélkül.

**K: Mi a maximális postafiók méret, amit feldolgozhatok?**  
A: Az API több **több gigabájtnyi** postafiókot is képes kezelni; mivel az eredményeket stream‑eli, a memóriahasználat alacsony marad.

**K: Hogyan szűrhetem a mellékleteket fájltípus szerint?**  
A: Adjon hozzá egy `SearchFilter.ContainsSubstring`‑t az `AttachmentNames` tulajdonságra, majd csak a megfelelő elemeket iterálja.

**K: Van mód a találatok rendezésére?**  
A: Igen – adja át egy `SortDirection`‑t és a rendezni kívánt tulajdonságot (pl. `DateTimeReceived`) a `FindItems` hívásnak.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Email for Java 24.10  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre EWSClient példányt az Aspose.Email for Java használatával: Exchange Server integrációs útmutató](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Hogyan töltsünk le e‑mailt az Exchange Serverről az Aspose.Email Java használatával](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [EWS postafiók információk kezelése az Aspose.Email for Java használatával: Átfogó útmutató](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```