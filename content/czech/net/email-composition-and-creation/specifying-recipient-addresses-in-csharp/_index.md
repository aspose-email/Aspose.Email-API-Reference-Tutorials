---
title: Zadání adres příjemců v C#
linktitle: Zadání adres příjemců v C#
second_title: Aspose.Email .NET Email Processing API
description: Naučte se, jak zadat adresy příjemců v C# pomocí Aspose.Email for .NET. Vytvářejte, konfigurujte a posílejte e-maily efektivně.
type: docs
weight: 19
url: /cs/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Tato příručka vás provede procesem zadávání adres příjemců v jazyce C# pomocí knihovny Aspose.Email for .NET. Aspose.Email je výkonné rozhraní .NET API, které vám umožňuje pracovat s e-mailovými zprávami a různými úkoly souvisejícími s e-mailem. V tomto tutoriálu se budeme zabývat tím, jak přidat adresy příjemců do e-mailové zprávy pomocí knihovny.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Nainstalované Visual Studio nebo jakékoli vývojové prostředí C#.
2.  Aspose.Email pro knihovnu .NET. Můžete to získat z[Aspose.Email pro vydání .NET](https://releases.aspose.com/email/net/).

## Kroky

Chcete-li zadat adresy příjemců v C# pomocí Aspose.Email pro .NET, postupujte takto:

### 1. Vytvořte nový projekt C#

Začněte vytvořením nového projektu C# ve vašem vývojovém prostředí.

### 2. Přidejte odkaz na Aspose.Email

1. Stáhněte a nainstalujte si knihovnu Aspose.Email for .NET, pokud jste tak ještě neučinili.
2. Otevřete svůj projekt C#.
3. Klikněte pravým tlačítkem na "Reference" v Průzkumníku řešení a vyberte "Přidat odkaz".
4. Procházejte a vyberte soubory Aspose.Email DLL, které jste si stáhli.

### 3. Importujte potřebné jmenné prostory

Do souboru kódu C# importujte potřebné jmenné prostory pro použití tříd Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. Vytvořte a nakonfigurujte e-mailovou zprávu

 Vytvořte novou instanci souboru`MailMessage` třídy reprezentovat vaši e-mailovou zprávu. Nakonfigurujte odesílatele a předmět e-mailu:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Přidejte adresy příjemců

Adresy příjemců můžete přidat pomocí`To`, `Cc` , a`Bcc` vlastnosti`MailMessage` třída. Adresy příjemců můžete přidat takto:

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

 Chcete-li odeslat e-mail, můžete použít`SmtpClient` třídy poskytuje Aspose.Email. Nakonfigurujte nastavení serveru SMTP a odešlete e-mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Nejčastější dotazy

###  Jak mohu přidat více příjemců do`To`, `Cc`, or `Bcc` fields?

 Zavoláním na číslo můžete přidat více příjemců`Add` metodou vícekrát na příslušné`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Mohu zadat jména příjemců spolu s jejich e-mailovými adresami?

Ano, při přidávání příjemců můžete zadat jméno i e-mailovou adresu příjemce:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Jak vyřídím výjimky při odesílání e-mailu?

Bloky try-catch můžete použít ke zpracování výjimek, které mohou nastat během odesílání e-mailu:

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

 Další informace a pokročilé funkce Aspose.Email pro .NET naleznete na[Aspose API Reference](https://reference.aspose.com/email/net/).

Tím končí příručka o zadávání adres příjemců v C# pomocí Aspose.Email pro .NET. Naučili jste se vytvořit e-mailovou zprávu, přidat adresy příjemců a odeslat e-mail pomocí funkcí knihovny.