---
title: Nastavení alternativního textu pro obrázky - Průvodce C#
linktitle: Nastavení alternativního textu pro obrázky - Průvodce C#
second_title: Aspose.Email .NET Email Processing API
description: Naučte se nastavit alternativní text pro obrázky v e-mailech pomocí Aspose.Email for .NET. Zajistěte přístupnost pomocí jasného alternativního textu. Součástí je dokumentace a kód.
type: docs
weight: 15
url: /cs/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Tato příručka vás provede procesem nastavení alternativního textu pro obrázky v e-mailech pomocí Aspose.Email for .NET. Alternativní text, také známý jako „alt text“, se používá k poskytnutí textového popisu obrázku v případě, že obrázek nelze zobrazit. Aspose.Email for .NET je výkonná knihovna, která vám umožní pracovat s e-maily a přílohami v různých formátech. V této příručce se zaměříme na nastavení alternativního textu pro obrázky v e-mailových zprávách pomocí C#.

## Předpoklady

Než začnete, ujistěte se, že máte následující předpoklady:

1. Nainstalované Visual Studio nebo jakékoli kompatibilní vývojové prostředí C#.
2. Aspose.Email pro knihovnu .NET. Správce balíčků NuGet můžete použít v sadě Visual Studio.

## Krok 1: Vytvořte nový projekt

1. Spusťte Visual Studio a vytvořte nový projekt konzolové aplikace C#.

## Krok 2: Nainstalujte Aspose.Email přes NuGet

1. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
2. Vyhledejte „Aspose.Email“ a nainstalujte nejnovější verzi balíčku.

## Krok 3: Přidejte pomocí příkazů

```csharp

using Aspose.Email.Mime;
```

## Krok 4: Načtěte a upravte e-mailovou zprávu

1.  Načtěte e-mailovou zprávu pomocí`MailMessage` třída:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Načtěte obsah HTML e-mailové zprávy:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Krok 5: Přidejte k obrázkům AlternativeView pro alternativní text

Přidejte htmlview pro alternativní text k obrázku jako AlternateView do zprávy. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Krok 6: Uložte a odešlete e-mail

1. Uložte upravenou zprávu do souboru nebo ji odešlete požadovanou metodou:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Závěr

V této příručce jste se naučili, jak nastavit alternativní text pro obrázky v e-mailových zprávách pomocí Aspose.Email for .NET. Podle výše uvedených kroků můžete zajistit, že obsah vašeho e-mailu zůstane přístupný a informativní, i když nelze zobrazit obrázky.

## FAQ

## Jak si mohu stáhnout knihovnu Aspose.Email?

Knihovnu Aspose.Email si můžete stáhnout z Aspose Releases nebo ji nainstalovat pomocí NuGet Package Manager ve Visual Studiu.

### Jak přidám obrázky jako propojené zdroje do e-mailu?

Chcete-li přidat obrázky jako propojené zdroje v e-mailu, můžete použít`LinkedResource` třída. Přiřaďte ID obsahu propojenému zdroji a poté na toto ID obsahu odkazujte v těle HTML pomocí`cid:` systém. Podrobné informace naleznete na[Dokumentace LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Kde najdu další dokumentaci k Aspose.Email pro .NET?

 Podrobnější dokumentaci, návody a příklady práce s Aspose.Email pro .NET naleznete v[Reference API](https://reference.aspose.com/email/net/).