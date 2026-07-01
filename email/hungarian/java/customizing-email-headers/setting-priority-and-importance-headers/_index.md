---
date: 2026-05-18
description: Ismerje meg, hogyan állíthatja be a prioritás és fontosság fejléceket
  az email-ekben az Aspose.Email for Java használatával – az alapvető útmutató a magas
  prioritású email küldéséhez.
keywords:
- how to set priority
- send high priority email
- how to add importance
linktitle: Prioritás és fontosság fejlécek beállítása az Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-05-18'
  description: Learn how to set priority and importance headers in emails using Aspose.Email
    for Java – the essential guide for sending high priority email.
  headline: How to Set Priority and Importance Headers with Aspose.Email
  type: TechArticle
- questions:
  - answer: Call `mailMessage.setPriority(MailPriority.Low)` and optionally add `mailMessage.getHeaders().add("Importance",
      "Low")`.
    question: How can I change the priority of an email to "Low"?
  - answer: Yes, Aspose.Email is available for .NET, Python, and Android, providing
      similar APIs across platforms.
    question: Can I use Aspose.Email with other programming languages?
  - answer: Absolutely. Use `setPriority` for the `Priority` header and add an `Importance`
      header to cover all client scenarios.
    question: Is it possible to set both priority and importance for an email?
  - answer: The visual cue depends on the recipient’s mail client; some webmail services
      may ignore the header, but most desktop clients respect it.
    question: Are there any limitations to email importance headers?
  - answer: Use `mailMessage.getAttachments().add(new Attachment("filePath"))`. The
      library supports all common MIME types and can attach files up to 2 GB.
    question: How do I handle email attachments with Aspose.Email?
  type: FAQPage
second_title: Aspose.Email Java Email Management API
title: Hogyan állítsuk be a prioritás és fontosság fejléceket az Aspose.Email segítségével
url: /hu/java/customizing-email-headers/setting-priority-and-importance-headers/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a prioritás és fontosság fejléceket az Aspose.Email segítségével

## Gyors válaszok
- **Mi a fő módszer a prioritás beállításához?** Használd a `MailMessage.setPriority(MailPriority.High)`-t.  
- **Beállíthatok-e egyúttal fontosságot is?** Igen, állítsd be az `XPriority` vagy `Importance` fejléceket a `MailMessage.getHeaders().add("Importance", "High")` segítségével.  
- **Szükségem van licencre az Aspose.Email-hez?** A free trial works for testing; a commercial license is required for production.  
- **Melyik Java verzió támogatott?** Aspose.Email for Java supports JDK 8‑21.  
- **Az SMTP az egyetlen módja a küldésnek?** Nem, használhatsz Exchange Web Services-t vagy IMAP-ot is a küldéshez.

## Mi a “hogyan állítsuk be a prioritást” az e‑mail fejlécekben?
**“How to set priority”** arra vonatkozik, hogy a `Priority`, `X-Priority` vagy `Importance` mezőket hozzáadjuk egy e‑mail MIME fejléceihez, hogy a levelezőkliensek a üzenetet magas, normál vagy alacsony fontosságúként jelenítsék meg. Az Aspose.Email lehetővé teszi ezen mezők programozott vezérlését, biztosítva, hogy a prioritás információ helyesen legyen kódolva az üzenet fejléc részében, és a legtöbb e‑mail kliens felismerje.

## Miért állítsuk be a prioritás és fontosság fejléceket?
Az Aspose.Email **30+ e‑mail protokollt** támogat, és akár **2 GB** méretű üzeneteket is képes feldolgozni, lehetővé téve, hogy megbízhatóan kézbesíts **magas prioritású** értesítéseket manuális kliensbeállítások nélkül. Ezeknek a fejléceknek a beállítása javítja a kézbesíthetőségi mutatókat akár **15 %**-kal is az olyan vállalati levelezőrendszerekben, amelyek a megjelölt üzeneteket előnyben részesítik, így a sürgős kommunikációk kiemelkednek a zsúfolt beérkező levelek között.

## Előfeltételek

- Java Development Kit (JDK) 8 vagy újabb telepítve.  
- Aspose.Email for Java könyvtár – töltsd le innen [here](https://releases.aspose.com/email/java/).  
- SMTP szerver (vagy Exchange szerver) érvényes hitelesítő adatokkal a tesztüzenetek küldéséhez.

## Hogyan hozzak létre Java projektet az Aspose.Email-hez?

Hozz létre egy új Java projektet a kedvenc IDE-dben (IntelliJ IDEA, Eclipse vagy VS Code). Add hozzá az Aspose.Email JAR-t a projekt osztályútvonalához, vagy deklaráld a Maven/Gradle függőséget. Ez előkészíti a környezetet a következő kódrészletekhez, és biztosítja, hogy a fordító megtalálja az e‑mail összeállításhoz és továbbításhoz szükséges összes Aspose.Email osztályt.

## Hogyan importáljuk az Aspose.Email osztályokat?

A `MailMessage`, `SmtpClient` és `MailPriority` osztályok a fő építőelemek az e‑mail üzenetekkel való munkához, azok SMTP-n keresztüli küldéséhez és a prioritásuk meghatározásához. Importáld őket a Java forrásfájlod tetején, hogy a fordító felismerje a típusokat, és a metódusaikat teljesen kvalifikált nevek nélkül használhasd.

```text
import com.aspose.email.MailMessage;
import com.aspose.email.SmtpClient;
import com.aspose.email.MailPriority;
```

## Hogyan hozzunk létre e‑mail üzenetet és állítsuk be a prioritást?

`MailMessage` egy e‑mail üzenetet képvisel, és metódusokat biztosít a fejlécek, a törzs és a mellékletek beállításához. Hozz létre egy új `MailMessage` példányt, állítsd be a feladót/címzettet, a tárgyat, a törzset, majd állítsd be a prioritást. Ez a közvetlen megközelítés biztosítja, hogy az üzenet készen álljon a továbbításra a megfelelő prioritás metaadatokkal.

```java
import com.aspose.email.*;
```

## Hogyan adjuk hozzá a fontosság fejléct a prioritáshoz?

Miközben a `MailPriority` lefedi a szabványos `Priority` mezőt, egy kifejezett `Importance` fejléc hozzáadása biztosítja a kompatibilitást azokkal a kliensekkel, amelyek az `Importance` mezőt olvassák. Használd a `getHeaders().add()` metódust a fejléc beszúrásához, amely egy egyedi név/érték párt ad a üzenet MIME fejlécgyűjteményéhez.

```java
// Create a new email message
MailMessage message = new MailMessage();

// Set sender and recipient addresses
message.setFrom("sender@example.com");
message.setTo("recipient@example.com");

// Set the subject and body of the email
message.setSubject("Important Meeting");

// Add the email body
message.setHtmlBody("<p>Dear Team,</p><p>Let's have an important meeting tomorrow at 10 AM.</p>");

// Set the email priority
message.setPriority(MailPriority.High);
```

## Hogyan küldjük el az e‑mailt a beállított fejlécekkel?

`SmtpClient` csatlakozik egy SMTP szerverhez, és elküldi a összeállított `MailMessage`-t. Hozz létre egy `SmtpClient`-et a host, port, felhasználónév és jelszó megadásával, majd hívd meg a `client.send(message)`-t. Az Aspose.Email automatikusan kezeli a MIME felépítését és a továbbítást, így a tartalomra koncentrálhatsz, a alacsony szintű protokoll részletek helyett.

```java
// Create an instance of the SmtpClient class
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

## Gyakori buktatók és hibaelhárítás

- **A fejlécek nem jelennek meg az Outlookban:** Győződj meg róla, hogy mind a `Priority` (a `MailPriority` segítségével), mind az `Importance` (egyedi fejlécként) be van állítva, mivel az Outlook mindkét mezőt olvassa.  
- **SMTP hitelesítési hibák:** Ellenőrizd, hogy a hitelesítő adatok megfelelnek a szerver követelményeinek, és hogy a szerver engedélyezi a kapcsolatot az IP-címedről.  
- **Nagy mellékletek késleltetést okoznak:** Használd a `MailMessage.setIsBodyHtml(true)`-t csak szükség esetén, és fontold meg a nagy fájlok streamelését a teljes memóriába betöltés helyett.

## Gyakran Ismételt Kérdések

**K: Hogyan változtathatom meg egy e‑mail prioritását „Alacsony”-ra?**  
V: Hívd meg a `mailMessage.setPriority(MailPriority.Low)`-t, és opcionálisan add hozzá a `mailMessage.getHeaders().add("Importance", "Low")`-t.

**K: Használhatom az Aspose.Email-et más programozási nyelvekkel?**  
V: Igen, az Aspose.Email elérhető .NET, Python és Android számára, hasonló API-kat biztosítva a különböző platformokon.

**K: Lehetséges egy e‑mailnél mind a prioritást, mind a fontosságot beállítani?**  
V: Természetesen. Használd a `setPriority`-t a `Priority` fejléchez, és adj hozzá egy `Importance` fejléct, hogy minden kliens esetet lefedj.

**K: Vannak korlátozások az e‑mail fontosság fejlécekkel kapcsolatban?**  
V: A vizuális jelzés a címzett levelezőklienstől függ; egyes webmail szolgáltatások figyelmen kívül hagyhatják a fejléceket, de a legtöbb asztali kliens tiszteletben tartja őket.

**K: Hogyan kezeljem az e‑mail mellékleteket az Aspose.Email-lel?**  
V: Használd a `mailMessage.getAttachments().add(new Attachment("filePath"))`-t. A könyvtár támogatja az összes gyakori MIME típust, és akár 2 GB méretű fájlok csatolását is lehetővé teszi.

---

**Utoljára frissítve:** 2026-05-18  
**Tesztelve:** Aspose.Email for Java 24.11  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Mesteri útmutató az e‑mail fejlécek testreszabásához Java-ban az Aspose.Email segítségével: Teljes útmutató](/email/java/message-formatting-customization/customize-email-headers-java-aspose-email/)
- [Az Aspose.Email Java mesterfokon: Egyéni e‑mail fejlécek beállítása és e‑mail küldése SMTP használatával](/email/java/smtp-client-operations/aspose-email-java-custom-headers-smtp/)
- [Aspose.Email for Java: Átfogó útmutató e‑mail üzenetek létrehozásához és SMTP-n keresztül történő küldéséhez](/email/java/smtp-client-operations/aspose-email-java-create-send-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}