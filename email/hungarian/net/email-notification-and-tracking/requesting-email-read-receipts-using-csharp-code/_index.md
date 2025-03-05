---
title: E-mail olvasási visszaigazolások kérése C# kóddal
linktitle: E-mail olvasási visszaigazolások kérése C# kóddal
second_title: Aspose.Email .NET Email Processing API
description: Ismerje meg, hogyan használhatja a C# kódot az e-mailek olvasási visszaigazolásainak kérésére az Aspose.Email for .NET használatával, javítva a kommunikáció nyomon követését.
type: docs
weight: 11
url: /hu/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

A mai digitális korban az e-mailen keresztüli kommunikáció személyes és szakmai életünk szerves részévé vált. Gyakran fontos e-mailek küldésekor meg akarunk győződni arról, hogy a címzett elolvasta és visszaigazolta üzenetünket. Itt lépnek életbe az e-mailek olvasási visszaigazolásai. Ebben a lépésenkénti oktatóanyagban végigvezetjük az e-mailek olvasási visszaigazolásának kérésén a C# használatával az Aspose.Email for .NET-hez.

## Az e-mail olvasási visszaigazolások bemutatása

Az e-mail olvasási visszaigazolások, más néven e-mail-követés vagy visszatérési nyugták, lehetővé teszik, hogy értesítést kapjon, amikor a címzett megnyitja és elolvassa az e-mailt. Ez egy értékes funkció, különösen az üzleti kommunikációban, mivel megerősíti az üzenetek kézbesítését és az elkötelezettséget.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- A Visual Studio telepítve van a rendszerére.
- Aspose.Email for .NET könyvtár letöltve és hivatkozva a projektben.

## 1. lépés: MailMessage példány létrehozása

 Az e-mailek olvasási visszaigazolásának megvalósításának első lépése a példány létrehozása`MailMessage` osztály. Ez az osztály egy e-mail üzenetet képvisel, és lehetővé teszi az e-mail különféle tulajdonságainak beállítását.

```csharp
MailMessage message = new MailMessage();
```

## 2. lépés: Az üzenet részleteinek megadása

Most pedig határozzuk meg az e-mail üzenet részleteit, beleértve a feladót, a címzettet, a HTML törzsét és a kézbesítési értesítési beállításokat.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## 3. lépés: SmtpClient példány létrehozása

 Az e-mail elküldéséhez létre kell hoznunk egy példányt a`SmtpClient` osztály, amely az üzenet elküldéséért felelős.

```csharp
SmtpClient client = new SmtpClient();
```

## 4. lépés: SMTP beállítások konfigurálása

Konfigurálja az SMTP-kiszolgáló beállításait a gazdagép, a felhasználónév, a jelszó és a portszám megadásával.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## 5. lépés: E-mail küldése

 Végül használja a`client.Send` az e-mail üzenet küldésének módja. Ha az üzenetet sikeresen elküldte, az „Üzenet elküldve” értesítés jelenik meg.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

Ezzel az öt egyszerű lépéssel e-mail-olvasási visszaigazolást kérhet, amikor C# és Aspose.Email for .NET használatával küld e-maileket. Ez a funkció egy bizonyos réteget ad az e-mail kommunikációjához, és biztosítja, hogy tudja, mikor olvassák el fontos üzeneteit.

## Teljes forráskód
```csharp
// Hozzon létre egy példányt a MailMessage osztályból
MailMessage message = new MailMessage();

// Adja meg a From, To, HtmlBody, DeliveryNotificationOptions mezőt
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Hozzon létre egy példányt az SmtpClient osztályból
SmtpClient client = new SmtpClient();

// Adja meg a levelezési kiszolgálót, a felhasználónevet, a jelszót és a portszámot
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// A Client.Send elküldi ezt az üzenetet
	client.Send(message);
	// Csak akkor jelenítse meg az „Üzenet elküldve” üzenetet, ha az üzenet sikeresen el lett küldve
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan kérhet e-mailek olvasási visszaigazolását C# használatával az Aspose.Email for .NET-hez. Az e-mail nyomon követés hatékony eszköz annak biztosítására, hogy üzeneteit a címzettek kézbesítsék és elolvassák, különösen professzionális környezetben. Az itt vázolt lépések követésével könnyedén megvalósíthatja ezt a funkciót az e-mail alkalmazásában.

## Gyakran Ismételt Kérdések (GYIK)

1. ### Mi a célja az e-mailek olvasási visszaigazolásának?
   Az e-mail olvasási visszaigazolások megerősítik, hogy a címzett megnyitotta és elolvasta az e-mailt. Gyakran használják fontos vagy időérzékeny üzenetek nyomon követésére.

2. ### Letilthatja a címzett az e-mail olvasási visszaigazolásokat?
   Igen, az e-mail kliensek gyakran lehetővé teszik a felhasználók számára, hogy letiltsák az olvasási visszaigazolások küldését. Ezért nem garantált, hogy mindig megkapja őket.

3. ### Az e-mailek olvasási visszaigazolása minden levelezőprogramban alapfunkció?
   Nem, az e-mail olvasási visszaigazolások nem támogatottak általánosan. Az, hogy működnek-e vagy sem, az e-mail klienstől és a címzett beállításaitól függ.

4. ### Nyomon követhető, hogy mikor nyílik meg egy e-mail mobileszközön?
   Az e-mailek követése általában a címzett e-mail kliensén és beállításain alapul, így különböző tényezőktől függően előfordulhat, hogy mobileszközökön működik, vagy nem.

5. ### Vannak-e adatvédelmi szempontok az e-mailek olvasási visszaigazolásának használatakor?
   Igen, vannak adatvédelmi aggályok az e-mailek követésével kapcsolatban. Egyes címzettek invazívnak tekinthetik, ezért elengedhetetlen, hogy ezt a funkciót felelősségteljesen használjuk, és tiszteletben tartsuk az adatvédelmi beállításokat.