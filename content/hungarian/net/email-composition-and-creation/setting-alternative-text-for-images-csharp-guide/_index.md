---
title: Alternatív szöveg beállítása képekhez - C# útmutató
linktitle: Alternatív szöveg beállítása képekhez - C# útmutató
second_title: Aspose.Email .NET Email Processing API
description: Ismerje meg, hogyan állíthat be alternatív szöveget az e-mailekben lévő képekhez az Aspose.Email for .NET segítségével. Biztosítsa a hozzáférhetőséget tiszta alternatív szöveggel. Dokumentáció és kód mellékelve.
type: docs
weight: 15
url: /hu/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Ez az útmutató végigvezeti Önt az Aspose.Email for .NET segítségével az e-mailek képeinek alternatív szövegének beállításán. Az alternatív szöveg, más néven "alt szöveg" a kép szöveges leírására szolgál arra az esetre, ha a kép nem jeleníthető meg. Az Aspose.Email for .NET egy hatékony könyvtár, amely lehetővé teszi a különféle formátumú e-mailek és mellékletek kezelését. Ebben az útmutatóban az e-mail üzenetekben lévő képek alternatív szövegének beállítására összpontosítunk C# használatával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Visual Studio vagy bármilyen kompatibilis C# fejlesztői környezet telepítve.
2. Aspose.Email a .NET könyvtárhoz. Használhatja a NuGet Package Managert a Visual Studióban.

## 1. lépés: Hozzon létre egy új projektet

1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# konzolalkalmazásprojektet.

## 2. lépés: Telepítse az Aspose.Email-t a NuGet segítségével

1. Kattintson a jobb gombbal a projektre a Solution Explorerben, és válassza a „NuGet-csomagok kezelése” lehetőséget.
2. Keresse meg az „Aspose.Email” kifejezést, és telepítse a csomag legújabb verzióját.

## 3. lépés: Adjon hozzá utasításokat

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## 4. lépés: Töltse be és módosítsa az e-mail üzenetet

1.  Töltse be az e-mail üzenetet a`MailMessage` osztály:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Töltse be az e-mail üzenet HTML-tartalmát:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## 5. lépés: Adja hozzá az AlternativeView-t az alternatív szöveghez a képekhez

Adja hozzá a HTML-nézetet az Alternatív szöveg képhez AlternateView-ként az üzenethez. 
```csharp
message.AlternateViews.Add(htmlView);
```

## 6. lépés: Mentse el és küldje el az e-mailt

1. Mentse el a módosított üzenetet egy fájlba, vagy küldje el a kívánt módszerrel:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Következtetés

Ebből az útmutatóból megtanulta, hogyan állíthat be alternatív szöveget az e-mail üzenetekben lévő képekhez az Aspose.Email for .NET használatával. A fent vázolt lépések követésével biztosíthatja, hogy e-mail tartalma elérhető és tájékoztató jellegű maradjon akkor is, ha a képeket nem lehet megjeleníteni.

## GYIK

## Hogyan tölthetem le az Aspose.Email könyvtárat?

Az Aspose.Email könyvtárat letöltheti az Aspose Releases lapból, vagy telepítheti a NuGet Package Manager segítségével a Visual Studio alkalmazásban.

### Hogyan adhatok hozzá képeket linkelt forrásként egy e-mailben?

Ha képeket szeretne csatolt forrásként hozzáadni egy e-mailben, használja a`LinkedResource` osztály. Rendeljen tartalomazonosítót a hivatkozott erőforráshoz, majd hivatkozzon erre a tartalomazonosítóra a HTML törzsében a következővel:`cid:` rendszer. Részletes információkért lásd a[LinkedResource dokumentáció](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Hol találok további dokumentációt az Aspose.Email for .NET-hez?

 Részletesebb dokumentációt, oktatóanyagokat és példákat találhat az Aspose.Email for .NET használatáról a következő helyen:[API-referencia](https://reference.aspose.com/email/net/).