---
title: Üzenetvázlatok kezelése C#-ban – E-mail mentése piszkozatként
linktitle: Üzenetvázlatok kezelése C#-ban – E-mail mentése piszkozatként
second_title: Aspose.Email .NET Email Processing API
description: Ismerje meg, hogyan valósíthatja meg a piszkozatos e-mailek kezelését C# nyelven az Aspose.Email for .NET használatával. A piszkozatok zökkenőmentes létrehozása, szerkesztése és mentése.
type: docs
weight: 17
url: /hu/net/email-conversion-and-export/draft-message-handling-in-csharp-saving-email-as-draft/
---

## Bevezetés

piszkozatok kezelése kulcsfontosságú funkció az e-mail kliensek számára. A felhasználóknak gyakran el kell kezdeniük az e-mail írását, elmenthetik piszkozatként, majd később visszatérhetnek hozzá további szerkesztés vagy esetleges elküldés céljából. Ez a cikk bemutatja, hogyan valósítható meg ez a funkció az Aspose.Email for .NET könyvtár használatával.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Visual Studio (vagy bármilyen C# fejlesztői környezet)
- Aspose.Email a .NET könyvtárhoz

 Letöltheti az Aspose.Email könyvtárat innen[itt](https://releases.aspose.com/email/net).

## A projekt beállítása

1. Hozzon létre egy új C# projektet a fejlesztői környezetben.
2. Adjon hozzá hivatkozásokat az Aspose.Email DLL-ekhez a projektben.

## E-mail vázlat létrehozása

Üzenetpiszkozat létrehozásához kövesse az alábbi lépéseket:

## Címzettek és tárgy hozzáadása

```csharp
// Hozzon létre egy új MailMessage példányt
MailMessage draft = new MailMessage();

// Címzettek hozzáadása
draft.To.Add("recipient@example.com");
draft.Cc.Add("cc@example.com");
draft.Bcc.Add("bcc@example.com");

// Állítsa be az e-mail tárgyát
draft.Subject = "Draft Email Demo";
```

## E-mail törzs összeállítása

```csharp
// E-mail törzsének beállítása
draft.Body = new TextBody("Hello, this is a draft email.");
```

## Mentés piszkozatként

```csharp
// Mentse az e-mailt piszkozatként
draft.Save("draft.eml", SaveOptions.DefaultEml);
```

## Piszkozatok betöltése és szerkesztése

Üzenetek piszkozatainak betöltéséhez és szerkesztéséhez kövesse az alábbi lépéseket:

```csharp
// E-mail piszkozat betöltése
MailMessage loadedDraft = MailMessage.Load("draft.eml");

// Címzettek szerkesztése
loadedDraft.To.Clear();
loadedDraft.To.Add("newrecipient@example.com");

// Szerkessze az e-mail törzsét
loadedDraft.Body = new TextBody("Updated draft content.");

// Változtatások mentése
loadedDraft.Save("updated_draft.eml", SaveOptions.DefaultEml);
```

## Következtetés

Ebben a cikkben megvizsgáltuk, hogyan kezelhetjük a piszkozatüzeneteket C# nyelven az Aspose.Email for .NET könyvtár használatával. Megtanultuk, hogyan hozhatunk létre, szerkeszthetünk és menthetünk piszkozatú e-maileket, így a felhasználók zökkenőmentesen írhatnak üzeneteket. Az ebben az útmutatóban ismertetett lépések követésével e-mail kliens alkalmazását vázlatos üzenet funkcióval bővítheti.

## GYIK

### Hogyan tölthetem le az Aspose.Email for .NET könyvtárat?

 Letöltheti az Aspose.Email for .NET könyvtárat innen[itt](https://releases.aspose.com/email/net).

### Szerkeszthetem a mentett piszkozat címzettjeit és tárgyát?

Igen, betölthet egy mentett piszkozatot, szerkesztheti annak címzettjeit, tárgyát és tartalmát, majd mentheti a módosításokat frissített piszkozatként.

### Az e-mail piszkozata meghatározott formátumban van mentve?

Igen, a piszkozat e-mailt EML formátumban menti, amely egy széles körben használt formátum az e-mail üzenetekhez.

### Integrálhatom a piszkozatok kezelését a meglévő e-mail alkalmazásomba?

Az ebben az útmutatóban ismertetett lépések követésével zökkenőmentesen integrálhatja a piszkozatok kezelését meglévő e-mail kliens alkalmazásába.

### Támogat az Aspose.Email könyvtár egyéb e-mailekkel kapcsolatos funkciókat?

 Igen, az Aspose.Email könyvtár funkciók széles skáláját kínálja az e-mail üzenetek kezeléséhez, beleértve az e-mailek és mellékletek küldését, fogadását és kezelését. További részletekért tekintse meg a dokumentációt:[itt](https://reference.aspose.com)