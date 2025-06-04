---
"description": "Naučte se, jak zadat adresy příjemců v C# pomocí Aspose.Email pro .NET. Efektivně vytvářejte, konfigurujte a odesílejte e-maily."
"linktitle": "Zadávání adres příjemců v C#"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Zadávání adres příjemců v C#"
"url": "/cs/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zadávání adres příjemců v C#



Tato příručka vás provede procesem zadávání adres příjemců v jazyce C# pomocí knihovny Aspose.Email pro .NET. Aspose.Email je výkonné .NET API, které vám umožňuje pracovat s e-mailovými zprávami a různými úkoly souvisejícími s e-mailem. V tomto tutoriálu se budeme zabývat tím, jak pomocí knihovny přidat adresy příjemců do e-mailové zprávy.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Nainstalované Visual Studio nebo jakékoli vývojové prostředí C#.
2. Knihovna Aspose.Email pro .NET. Můžete ji získat z [Aspose.Email pro vydání .NET](https://releases.aspose.com/email/net/).

## Kroky

Chcete-li v jazyce C# pomocí Aspose.Email pro .NET zadat adresy příjemců, postupujte takto:

### 1. Vytvořte nový projekt v C#

Začněte vytvořením nového projektu C# ve vašem vývojovém prostředí.

### 2. Přidejte odkaz na Aspose.Email

1. Stáhněte a nainstalujte si knihovnu Aspose.Email pro .NET, pokud jste tak ještě neučinili.
2. Otevřete svůj projekt v C#.
3. Průzkumníku řešení klikněte pravým tlačítkem myši na „Odkazy“ a vyberte „Přidat odkaz“.
4. Procházejte a vyberte stažené soubory DLL Aspose.Email.

### 3. Importujte potřebné jmenné prostory

Do souboru kódu C# importujte potřebné jmenné prostory pro použití tříd Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. Vytvořte a nakonfigurujte e-mailovou zprávu

Vytvořte novou instanci `MailMessage` třída pro reprezentaci vaší e-mailové zprávy. Nakonfigurujte odesílatele a předmět e-mailu:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Přidejte adresy příjemců

Adresy příjemců můžete přidat pomocí `To`, `Cc`a `Bcc` vlastnosti `MailMessage` třída. Adresy příjemců můžete přidat takto:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Dokončete e-mailovou zprávu

Přidejte do e-mailové zprávy tělo e-mailu a veškerý další potřebný obsah:

```csharp
message.Body = "This is the email body.";
```

### 7. Odešlete e-mail

Pro odeslání e-mailu můžete použít `SmtpClient` třída poskytovaná službou Aspose.Email. Nakonfigurujte nastavení SMTP serveru a odešlete e-mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Často kladené otázky

### Jak mohu přidat více příjemců do `To`, `Cc`, nebo `Bcc` pole?

Více příjemců můžete přidat zavoláním na `Add` metodu několikrát na příslušné `MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Mohu zadat jména příjemců spolu s jejich e-mailovými adresami?

Ano, při přidávání příjemců můžete zadat jméno i e-mailovou adresu příjemce:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Jak mám řešit výjimky při odesílání e-mailu?

Bloky try-catch můžete použít k ošetření výjimek, ke kterým může dojít během odesílání e-mailů:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

Další informace a pokročilé funkce Aspose.Email pro .NET naleznete v [Reference API Aspose](https://reference.aspose.com/email/net/).

Tímto končí průvodce zadáváním adres příjemců v C# pomocí knihovny Aspose.Email pro .NET. Naučili jste se, jak vytvořit e-mailovou zprávu, přidat adresy příjemců a odeslat e-mail pomocí funkcí knihovny.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}