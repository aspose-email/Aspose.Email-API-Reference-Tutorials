---
"description": "Naučte se nastavit alternativní text pro obrázky v e-mailech pomocí Aspose.Email pro .NET. Zajistěte přístupnost pomocí jasného alternativního textu. Dokumentace a kód jsou součástí balení."
"linktitle": "Nastavení alternativního textu pro obrázky - Průvodce C#"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Nastavení alternativního textu pro obrázky - Průvodce C#"
"url": "/cs/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení alternativního textu pro obrázky - Průvodce C#


Tato příručka vás provede procesem nastavení alternativního textu pro obrázky v e-mailech pomocí knihovny Aspose.Email pro .NET. Alternativní text, známý také jako „alt text“, se používá k poskytnutí textového popisu obrázku v případě, že jej nelze zobrazit. Aspose.Email pro .NET je výkonná knihovna, která umožňuje pracovat s e-maily a přílohami v různých formátech. V této příručce se zaměříme na nastavení alternativního textu pro obrázky v e-mailových zprávách pomocí jazyka C#.

## Předpoklady

Než začnete, ujistěte se, že máte následující předpoklady:

1. Nainstalované Visual Studio nebo jakékoli kompatibilní vývojové prostředí C#.
2. Knihovna Aspose.Email pro .NET. Správce balíčků NuGet můžete použít ve Visual Studiu.

## Krok 1: Vytvořte nový projekt

1. Spusťte Visual Studio a vytvořte nový projekt konzolové aplikace v C#.

## Krok 2: Instalace Aspose.Email přes NuGet

1. V Průzkumníku řešení klikněte pravým tlačítkem myši na svůj projekt a vyberte možnost „Spravovat balíčky NuGet“.
2. Vyhledejte „Aspose.Email“ a nainstalujte nejnovější verzi balíčku.

## Krok 3: Přidání příkazů Using

```csharp

using Aspose.Email.Mime;
```

## Krok 4: Načtení a úprava e-mailové zprávy

1. Načtěte e-mailovou zprávu pomocí `MailMessage` třída:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Načtěte HTML obsah e-mailové zprávy:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Krok 5: Přidání alternativního zobrazení pro alternativní text k obrázkům

Přidejte do zprávy htmlview pro alternativní text k obrázku jako AlternateView. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Krok 6: Uložení a odeslání e-mailu

1. Uložte upravenou zprávu do souboru nebo ji odešlete požadovanou metodou:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Závěr

V této příručce jste se naučili, jak nastavit alternativní text pro obrázky v e-mailových zprávách pomocí Aspose.Email pro .NET. Dodržením výše uvedených kroků můžete zajistit, že obsah vašeho e-mailu zůstane přístupný a informativní, i když nelze zobrazit obrázky.

## Často kladené otázky

## Jak si mohu stáhnout knihovnu Aspose.Email?

Knihovnu Aspose.Email si můžete stáhnout z Aspose Releases nebo ji nainstalovat pomocí NuGet Package Manageru ve Visual Studiu.

### Jak přidám obrázky jako propojené zdroje do e-mailu?

Chcete-li do e-mailu přidat obrázky jako propojené zdroje, můžete použít `LinkedResource` třída. Přiřaďte odkazovanému zdroji ID obsahu a poté na toto ID obsahu odkazujte v těle HTML pomocí `cid:` schéma. Podrobné informace naleznete v [Dokumentace k LinkedResource](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Kde najdu další dokumentaci k Aspose.Email pro .NET?

Podrobnější dokumentaci, návody a příklady práce s Aspose.Email pro .NET naleznete v [Referenční informace k API](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}