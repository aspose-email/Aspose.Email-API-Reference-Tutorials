---
date: '2026-08-27'
description: Ismerje meg, hogyan tölthet be MSG fájlokat és konvertálhatja őket MHTML
  formátumba az Aspose.Email for Java segítségével, beleértve az egyéni időzóna beállításokat
  és a kötegelt e‑mail feldolgozási tippeket.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Ismerje meg, hogyan tölthet be MSG fájlokat és exportálhatja őket
  MHTML formátumba az Aspose.Email for Java segítségével. Tartalmazza az időzóna kezelését
  és a kötegelt feldolgozási tippeket.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Hogyan töltsünk be MSG fájlokat és mentsük MHTML formátumban az Aspose.Email
  for Java használatával
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Hogyan töltsünk be MSG fájlokat és mentsük MHTML formátumban az Aspose.Email
  for Java használatával
url: /hu/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan töltsünk be msg fájlt és mentsük MHTML formátumban az Aspose.Email for Java segítségével

## Bevezetés

Ha **msg fájlok betöltésére** van szükséged, módosítani szeretnéd az időbélyegeket, majd **msg‑t mhtml‑re konvertálni**, jó helyen jársz. Ebben az oktatóanyagban végigvezetünk egy `.msg` e‑mail betöltésén, egy egyedi időzóna eltolás alkalmazásán, és az eredmény MHTML archívumként való mentésén – mindezt az Aspose.Email for Java segítségével. Akár egyetlen üzenetet, akár egy **kötegelt e‑mail feldolgozó** csővezetékben dolgozol, ezek a lépések szilárd alapot adnak a megbízható archiváláshoz és migrációhoz.

**Amit megtanulsz**
- Hogyan tölts be egy `MailMessage`‑t egy `.msg` fájlból.
- Hogyan állíts be egy egyedi időzónát és aktuális dátumot.
- Hogyan mentsd az üzenetet MHTML‑ként pontos formázással.
- Tippek a megközelítés kötegelt szcenáriókra való skálázásához.

Készen állsz az e‑mail munkafolyamatod felgyorsítására? Először állítsuk be a környezetet.

## Gyors válaszok
- **Mi a fő könyvtár?** Aspose.Email for Java.
- **Betölthetem a MSG‑t és exportálhatom MHTML‑re egy lépésben?** Nem, először betöltöd, majd módosítod, végül mented.
- **Szükség van licencre a termeléshez?** Igen, érvényes Aspose.Email licenc szükséges.
- **Támogatott az időzóna kezelése?** Igen, a `setTimeZoneOffset`‑on keresztül.
- **Használható kötegelt feldolgozásra?** Teljesen – csomagold a lépéseket egy ciklusba.

## Mi az Aspose.Email for Java?

Az Aspose.Email for Java egy átfogó API, amely lehetővé teszi e‑mail üzenetek létrehozását, olvasását, konvertálását és manipulálását anélkül, hogy a Microsoft Outlookra lenne szükség. Több mint 30 e‑mail formátumot támogat, és több száz oldalas üzeneteket is képes feldolgozni alacsony memóriahasználat mellett.

## Miért konvertáljuk az MSG-t MHTML-re?

Az MSG fájlok MHTML‑re konvertálása egy web‑barát, egyetlen fájlbeli ábrázolást biztosít, amely bármely modern böngészőben megnyitható. Ez a formátum megőrzi az eredeti stílusokat, beágyazott képeket és mellékleteket, így ideális **jogi archiváláshoz**, **platformok közötti megosztáshoz**, valamint **e‑mail-ek weboldalakba vagy dokumentációba ágyazásához**.

## Előfeltételek

Mielőtt elkezdenénk, győződj meg róla, hogy a következők rendelkezésre állnak:

### Szükséges könyvtárak és függőségek
- **Aspose.Email for Java** könyvtár verzió 25.4 (jdk16 classifier) – a könyvtár **50+** bemeneti és kimeneti e‑mail formátumot támogat.
- Alapvető Java ismeretek.
- Egy IDE, például IntelliJ IDEA vagy Eclipse.

### Környezet beállítási követelmények
- JDK 16 vagy újabb telepítve.
- Maven a függőségkezeléshez.

## Az Aspose.Email for Java beállítása

A könyvtár Maven projektbe való felvételéhez add hozzá a következő függőséget:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licenc beszerzési lépések

Kezdd egy **ingyenes próbaverzióval** vagy szerezz **ideiglenes licencet**, hogy a könyvtár teljes képességeit korlátozás nélkül tesztelhesd. Hosszú távú használathoz fontold meg a licenc megvásárlását:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Alapvető inicializálás

A `License` osztály regisztrálja az Aspose.Email licencet, így feloldja a teljes funkcionalitást.  
A függőség hozzáadása után inicializáld a licencet a Java kódban:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Hogyan töltsük be a msg-t és mentsük MHTML-ként?

Töltsd be az MSG fájlt, módosítsd az időbélyeget, és mentsd MHTML‑ként három egyszerű lépésben. Először egy `MailMessage`‑t hozunk létre az MSG fájlból a `MsgLoadOptions` használatával. Ezután a kívánt időzóna eltolást állítjuk be a `setTimeZoneOffset`‑tal. Végül konfiguráljuk a `MhtSaveOptions`‑t és meghívjuk a `save`‑t, hogy létrejöjjön az MHTML archívum.

### 1. funkció: MailMessage betöltése fájlból

A `MailMessage` osztály egy e‑mail üzenetet képvisel fejléc, törzs és mellékletek formájában.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

A `MsgLoadOptions` lehetővé teszi az MSG fájl elemzésének finomhangolását; az alapértelmezett beállítások a legtöbb esetben megfelelőek.

### 2. funkció: aktuális dátum és egyedi időzóna eltolás beállítása

A `Date` objektum tartalmazza azt az időbélyeget, amely az e‑mail **Date** fejlécébe kerül.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Az eltolás milliszekundumban van megadva; UTC+5 esetén `5 * 60 * 60 * 1000`‑t adunk meg.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### 3. funkció: MailMessage mentése MHTML fájlként

Az `MhtSaveOptions` határozza meg, hogyan csomagolja az e‑mailt egy MHTML archívumba, megőrizve a beágyazott képeket és mellékleteket.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Az eredményül kapott `.mhtml` fájl megtartja az eredeti formázást, képeket és mellékleteket, így hű vizuális másolata az eredeti MSG‑nek.

## Hogyan állítsunk be egyedi időzóna eltolást?

Az időzónát a `MailMessage` példányon a `setTimeZoneOffset` meghívásával módosíthatod. A metódus milliszekundumban várja az eltolást, pozitív (UTC kelete) és negatív (UTC nyugata) értékek egyaránt megengedettek. Például UTC‑3 esetén `-3 * 60 * 60 * 1000`‑t kell megadni.

## Hogyan dolgozzuk fel az MSG fájlokat kötegben?

A háromlépéses munkafolyamatot egy ciklusba ágyazhatod, amely egy `.msg` fájlokból álló könyvtárat iterál. Egyetlen `License` példányt újrahasználva elkerülheted az ismételt I/O‑t, és minden `MailMessage` mentése után felszabadíthatod azt, hogy alacsony maradjon a memóriahasználat.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Kötegelt feldolgozási tippek
1. **Licenc újrahasználata** – hívj egyszer `new License().setLicense(...)`-t az alkalmazás indításakor.
2. **Használj try‑with‑resources‑t** az automatikus erőforrás‑takarításért.
3. **Naplózd a hibákat** egy külön fájlba, hogy később újra próbálhass problémás üzeneteket.
4. **Gondolj párhuzamosságra** a `ForkJoinPool`‑al nagy kötegek esetén, de biztosítsd, hogy minden szál saját `MailMessage` példányt használjon.

## Gyakori problémák és megoldások

- **Memóriacsúcsok hatalmas MSG fájloknál** – engedélyezd a streaminget a `MailMessage.load(InputStream, MsgLoadOptions)` használatával, és dolgozd fel a streamet darabokban.
- **Helytelen időbélyegek** – ellenőrizd, hogy a rendszeróra UTC‑re van állítva az eltolás alkalmazása előtt, vagy adj meg explicit `java.util.Calendar` példányt.
- **Hiányzó mellékletek MHTML‑ben** – győződj meg róla, hogy `MhtSaveOptions.setWriteHeader(true)` van beállítva; ez beágyazza a mellékleteket `cid:` erőforrásként.

## Gyakran feltett kérdések

**Q: Betölthetek e‑mailt más formátumokból, mint a .msg?**  
A: Igen, az Aspose.Email támogatja az EML, MHT, EMLX és több más formátumot, összesen több mint 30 bemeneti típust.

**Q: Hogyan kezelhetem nagyon nagy e‑mail fájlokat hatékonyan?**  
A: Használd a streaming API‑kat (`MailMessage.load(InputStream, ...)`) az adatok darabokban történő olvasásához és írásához, így a memóriafogyasztás 50 MB alatt marad még 500 oldalas üzeneteknél is.

**Q: Lehet-e módosítani a mellékleteket egy MailMessage‑ben?**  
A: Teljesen. Hozzáadhatsz, eltávolíthatsz vagy cserélhetsz mellékleteket a `msg.getAttachments()` gyűjteményen keresztül, majd a `save`‑el mentheted a változásokat.

**Q: Mi van, ha az időzóna eltolás negatív (UTC mögött) van?**  
A: Adj meg negatív milliszekundum értéket a `setTimeZoneOffset`‑nek, például `-3 * 60 * 60 * 1000` UTC‑3‑hoz.

**Q: Használhatom az Aspose.Email‑t kereskedelmi projektekben?**  
A: Igen, amennyiben érvényes kereskedelmi licencet vásároltál. Az ingyenes próba 20 MB‑ra korlátozott dokumentumonként.

**Q: Hogyan dolgozzak fel több ezer MSG fájlt anélkül, hogy kifogyok a memóriából?**  
A: Dolgozd fel a fájlokat kötegekben, minden `MailMessage`‑t a mentés után szabadíts fel, és alkalmazd a Java `try‑with‑resources` mintáját az automatikus tisztításhoz.

## Resources
- [documentation](https://reference.aspose.com/email/java/)
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-08-27  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [How to Load and Parse Outlook MSG Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email for Java: Save Emails as MHT Files](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [How to extract attachments from msg files using Aspose.Email for Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}