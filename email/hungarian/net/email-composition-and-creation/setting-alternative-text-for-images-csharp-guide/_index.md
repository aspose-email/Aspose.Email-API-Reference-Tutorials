---
"description": "Tanuld meg, hogyan állíthatsz be alternatív szöveget az e-mailekben található képekhez az Aspose.Email for .NET használatával. Biztosítsd az akadálymentességet egyértelmű alternatív szöveggel. Dokumentáció és kód mellékelve."
"linktitle": "Képek alternatív szövegének beállítása - C# útmutató"
"second_title": "Aspose.Email .NET e-mail feldolgozó API"
"title": "Képek alternatív szövegének beállítása - C# útmutató"
"url": "/hu/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Képek alternatív szövegének beállítása - C# útmutató


Ez az útmutató végigvezeti Önt az e-mailekben található képek alternatív szövegének beállításán az Aspose.Email for .NET használatával. Az alternatív szöveg, más néven „alt szöveg”, egy kép szöveges leírását adja meg abban az esetben, ha a kép nem jeleníthető meg. Az Aspose.Email for .NET egy hatékony függvénykönyvtár, amely lehetővé teszi az e-mailek és mellékletek különböző formátumokban történő kezelését. Ebben az útmutatóban a képek alternatív szövegének beállítására fogunk összpontosítani e-mail üzenetekben a C# használatával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Visual Studio vagy bármilyen kompatibilis C# fejlesztői környezet telepítve.
2. Aspose.Email .NET könyvtárhoz. A NuGet csomagkezelőt a Visual Studio-ban használhatod.

## 1. lépés: Új projekt létrehozása

1. Indítsa el a Visual Studio alkalmazást, és hozzon létre egy új C# konzolalkalmazás-projektet.

## 2. lépés: Telepítse az Aspose.Emailt NuGet-en keresztül

1. Kattintson jobb gombbal a projektjére a Megoldáskezelőben, és válassza a „NuGet-csomagok kezelése” lehetőséget.
2. Keresd meg az „Aspose.Email” csomagot, és telepítsd a legújabb verzióját.

## 3. lépés: Utasítások hozzáadása

```csharp

using Aspose.Email.Mime;
```

## 4. lépés: Az e-mail üzenet betöltése és módosítása

1. Töltsd be az e-mailt a segítségével `MailMessage` osztály:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Töltse be az e-mail üzenet HTML tartalmát:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## 5. lépés: AlternativeView hozzáadása képek alternatív szövegéhez

Htmlview hozzáadása az üzenethez a kép alternatív szövegéhez alternatív nézetként. 
```csharp
message.AlternateViews.Add(htmlView);
```

## 6. lépés: Mentse el és küldje el az e-mailt

1. Mentse el a módosított üzenetet egy fájlba, vagy küldje el a kívánt módszerrel:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Következtetés

Ebben az útmutatóban megtanultad, hogyan állíthatsz be alternatív szöveget az e-mail üzenetekben található képekhez az Aspose.Email for .NET használatával. A fent vázolt lépéseket követve biztosíthatod, hogy az e-mail tartalmad akkor is hozzáférhető és informatív maradjon, ha a képek nem jeleníthetők meg.

## GYIK

## Hogyan tudom letölteni az Aspose.Email könyvtárat?

Az Aspose.Email könyvtárat letöltheted az Aspose kiadásaiból, vagy telepítheted a Visual Studio NuGet csomagkezelőjén keresztül.

### Hogyan adhatok hozzá képeket csatolt erőforrásként egy e-mailhez?

Ha képeket szeretne csatolt erőforrásként hozzáadni egy e-mailhez, használhatja a `LinkedResource` osztály. Rendeljen hozzá egy tartalomazonosítót a hivatkozott erőforráshoz, majd hivatkozzon erre a tartalomazonosítóra a HTML törzsben a `cid:` rendszer. Részletes információkért lásd a [LinkedResource dokumentáció](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Hol találok további dokumentációt az Aspose.Email for .NET-ről?

Részletesebb dokumentációt, oktatóanyagokat és példákat az Aspose.Email for .NET használatáról a következő helyen talál: [API-referencia](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}