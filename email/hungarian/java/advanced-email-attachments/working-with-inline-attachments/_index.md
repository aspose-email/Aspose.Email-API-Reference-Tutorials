---
date: 2025-12-01
description: Tanulja meg, hogyan küldjön e‑mailt beágyazott képpel az Aspose.Email
  for Java használatával. Ez az útmutató bemutatja, hogyan ágyazzon be képeket az
  e‑mailbe, és hogyan hozzon létre HTML e‑mailt Java‑ban beágyazott mellékletekkel.
language: hu
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Hogyan küldjünk e‑mailt beágyazott képpel az Aspose.Email for Java használatával
url: /java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan küldjünk e-mailt beágyazott képpel az Aspose.Email for Java használatával

A képek közvetlen beágyazása egy e-mailbe elegáns megjelenést kölcsönöz az üzeneteknek, és biztosítja, hogy a címzett lássa a grafikákat anélkül, hogy külön fájlokat kellene letöltenie. Ebben az útmutatóban megtanulja, **hogyan küldjen e-mailt beágyazott képpel** az Aspose.Email for Java használatával, lefedve mindent a könyvtár beállításától az HTML e-mail létrehozásáig, a beágyazott erőforrások hozzáadásáig, és végül az üzenet elküldéséig.

## Gyors válaszok
- **Mi a fő osztály a beágyazott képekhez?** `LinkedResource`
- **Melyik módszer hivatkozik a képre HTML-ben?** Használja a `cid:yourContentId` értéket a `<img>` tagben
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; licenc szükséges a termeléshez
- **Küldhetem az e-mailt bármely SMTP szerveren?** Igen, csak konfigurálja a `SmtpClient`-et a szerver adataival
- **Ez a megközelítés kompatibilis-e az összes főbb e-mail klienssel?** A legtöbb modern kliens (Outlook, Gmail, Thunderbird) támogatja a CID‑beágyazott képeket

## Mik azok a beágyazott mellékletek (Embedded Images)?

A beágyazott mellékletek – néha beágyazott vagy CID képeknek is nevezik – olyan fájlok, amelyek az e-mail MIME törzsén belül helyezkednek el. A HTML részben a **Content‑ID** (CID) segítségével hivatkoznak rájuk. Ez a technika lehetővé teszi, hogy **képeket ágyazzon be az e-mailbe**, így azok pontosan ott jelennek meg, ahol a `<img>` tagot elhelyezi, anélkül, hogy külön letölthető mellékletekként jelennek meg.

## Miért használjunk beágyazott képeket a Java e-mailekben?

- **Professzionális megjelenés:** Logók, bannerek és termékképek azonnal megjelennek.  
- **Jobb elköteleződés:** A címzettek nagyobb valószínűséggel olvasnak el egy teljesnek tűnő e-mailt.  
- **Nincs extra kattintás:** A felhasználóknak nem kell letölteniük egy mellékletet a kép megtekintéséhez.  
- **Következetes márkaépítés:** A márkaelemek a üzenet tartalmával egy vonalban maradnak.

## Előfeltételek

- Aspose.Email for Java könyvtár (letöltés a hivatalos [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/) oldalról)  
- Java 8+ fejlesztői környezet  
- Hozzáférés egy SMTP szerverhez az e-mailek küldéséhez  
- A beágyazni kívánt képfájl (például `logo.png`)

## Lépésről‑lépésre útmutató

### 1. lépés: Alap HTML e-mail üzenet létrehozása

Először állítson be egy egyszerű `MailMessage`-t HTML törzzsel. Ez lesz a vászon, ahová később beágyazzuk a képet.

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### 2. lépés: Beágyazott kép hozzáadása a `LinkedResource` használatával

Most ágyazzunk be egy képet. A `LinkedResource` osztály a beágyazott mellékletet képviseli. Rendeljen egy egyedi **Content‑ID**-t, és hivatkozzon rá a HTML törzsben a `cid:` segítségével.

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **Pro tipp:** Tartsa a `ContentId`-t egyszerűnek és egyedinek az üzeneten belül, hogy elkerülje az ütközéseket.

### 3. lépés: E-mail küldése a `SmtpClient` segítségével

Állítsa be az SMTP beállításokat, és küldje el az üzenetet. A beágyazott kép együtt utazik az e-maillel, így a címzett azonnal látja.

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### 4. lépés: Beágyazott képek fogadása és kinyerése (opcionális bejövő üzeneteket kell feldolgozni, amelyek beágyazott képeket tartalmaznak, betöltheti a `.eml` fájlt, és hozzáférhet annak `LinkedResources`-eihez.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Content‑ID eltérés** | A HTML-ben lévő `cid:` hivatkozás nem egyezik a `LinkedResource`-on beállított `ContentId`-val. | Győződjön meg róla, hogy a karakterláncok azonosak (`image001` vs `cid:image001`). |
| **Fájl nem található** | A kép elérési útja helytelen vagy a fájl hiányzik. | Ellenőrizze a abszolút/relatív útvonalat, és hogy a fájl létezik-e a szerveren. |
| **SMTP hitelesítési hiba** | Hibás hitelesítő adatok vagy szerverbeállítások. | Ellenőrizze a hostot, portot, felhasználónevet és jelszót. Engedélyezze a TLS/SSL-t, ha szükséges. |
| **Kép nem jelenik meg néhány kliensben** | Bizonyos kliensek blokkolják a külső erőforrásokat. | Használjon CID‑beágyazott képeket (ahogy bemutattuk), a külső URL-ek helyett. |

## Gyakran ismételt kérdések

**K: Hogyan tölthetem le az Aspose.Email for Java-t?**  
V: Letöltheti az Aspose.Email for Java-t a [documentation](https://reference.aspose.com/email/java/) oldalról. Kövesse a telepítési útmutatót a projektbe való beállításhoz.

**K: Használhatom az Aspose.Email for Java-t más Java könyvtárakkal?**  
V: Igen, az Aspose.Email zökkenőmentesen integrálódik más Java könyvtárakkal, lehetővé téve az e-mail feldolgozás kombinálását PDF generálással, OCR-rel vagy adatbázis hozzáféréssel.

**K: Milyen fájlformátumok támogatottak a beágyazott mellékletekhez?**  
V: Általános képformátumok, mint a PNG, JPEG, GIF, valamint egyéb dokumentumtípusok (például SVG) támogatottak beágyazott erőforrásként.

**K: Hogyan kezeljem a beágyazott mellékleteket HTML e-mailekben?**  
V: Használja a `LinkedResource` osztályt egy `ContentId` hozzárendeléséhez, adja hozzá a `message.getLinkedResources()`-hez, és hivatkozzon rá a HTML törzsben a `<img src='cid:yourContentId'>` segítségével.

**K: Az Aspose.Email for Java kompatibilis különböző e-mail szerverekkel?**  
V: Igen, működik bármely SMTP/IMAP/POP3 szerverrel. Csak adja meg a helyes szervercímet, portot és hitelesítési adatokat.

---

**Utoljára frissítve:** 2025-12-01  
**Tesztelve:** Aspose.Email for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}