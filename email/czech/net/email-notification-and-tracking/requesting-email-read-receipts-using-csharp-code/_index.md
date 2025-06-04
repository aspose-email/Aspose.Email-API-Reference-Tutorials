---
"description": "Naučte se, jak pomocí kódu C# vyžádat potvrzení o přečtení e-mailů pomocí Aspose.Email pro .NET a vylepšit tak sledování komunikace."
"linktitle": "Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#"
"second_title": "Rozhraní API pro zpracování e-mailů Aspose.Email v .NET"
"title": "Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#"
"url": "/cs/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#


dnešní digitální době se komunikace prostřednictvím e-mailu stala nedílnou součástí našeho osobního i profesního života. Při odesílání důležitých e-mailů se často chceme ujistit, že si příjemce naši zprávu přečetl a potvrdil její příjem. A právě zde přicházejí na řadu potvrzení o přečtení e-mailu. V tomto podrobném návodu vás provedeme procesem vyžádání potvrzení o přečtení e-mailu pomocí C# s Aspose.Email pro .NET.

## Úvod do potvrzení o přečtení e-mailů

Potvrzení o přečtení e-mailů, známá také jako sledování e-mailů nebo potvrzení o vrácení, vám umožňují dostávat oznámení, když příjemce váš e-mail otevře a přečte. Je to cenná funkce, zejména v obchodní komunikaci, protože poskytuje potvrzení o doručení zprávy a interakci.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Visual Studio nainstalované ve vašem systému.
- Knihovna Aspose.Email pro .NET byla stažena a odkazována ve vašem projektu.

## Krok 1: Vytvoření instance MailMessage

Prvním krokem při implementaci potvrzení o přečtení e-mailů je vytvoření instance `MailMessage` třída. Tato třída představuje e-mailovou zprávu a umožňuje nastavit různé vlastnosti e-mailu.

```csharp
MailMessage message = new MailMessage();
```

## Krok 2: Zadání podrobností zprávy

Nyní specifikujme podrobnosti e-mailové zprávy, včetně odesílatele, příjemce, obsahu HTML a možností oznámení o doručení.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Krok 3: Vytvoření instance SmtpClient

Pro odeslání e-mailu musíme vytvořit instanci `SmtpClient` třída, která je zodpovědná za odeslání zprávy.

```csharp
SmtpClient client = new SmtpClient();
```

## Krok 4: Konfigurace nastavení SMTP

Nakonfigurujte nastavení serveru SMTP zadáním hostitelského serveru, uživatelského jména, hesla a čísla portu.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Krok 5: Odeslání e-mailu

Nakonec použijte `client.Send` způsob odeslání e-mailové zprávy. Pokud je zpráva úspěšně odeslána, zobrazí se oznámení „Zpráva odeslána“.

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

Pomocí těchto pěti jednoduchých kroků si můžete vyžádat potvrzení o přečtení e-mailů při odesílání e-mailů pomocí C# a Aspose.Email pro .NET. Tato funkce přidává do vaší e-mailové komunikace vrstvu jistoty a zajišťuje, že budete vědět, kdy jsou vaše důležité zprávy přečteny.

## Kompletní zdrojový kód
```csharp
// Vytvoření instance třídy MailMessage
MailMessage message = new MailMessage();

// Zadejte pole Od, Komu, HtmlBody a DeliveryNotificationOptions.
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Vytvořte instanci třídy SmtpClient
SmtpClient client = new SmtpClient();

// Zadejte svůj poštovní hostitelský server, uživatelské jméno, heslo a číslo portu.
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send odešle tuto zprávu
	client.Send(message);
	// Zobrazit „Zpráva odeslána“, pouze pokud byla zpráva úspěšně odeslána
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Závěr

V tomto tutoriálu jsme prozkoumali, jak si pomocí C# s Aspose.Email pro .NET vyžádat potvrzení o přečtení e-mailů. Sledování e-mailů je výkonný nástroj pro zajištění doručení a přečtení zpráv zamýšlenými příjemci, zejména v profesionálním prostředí. Dodržením zde uvedených kroků můžete tuto funkci snadno implementovat do své e-mailové aplikace.

## Často kladené otázky (FAQ)

1. ### K čemu slouží potvrzení o přečtení e-mailů?
   Potvrzení o přečtení e-mailu poskytují potvrzení, že příjemce e-mail otevřel a přečetl. Často se používají ke sledování důležitých nebo časově citlivých zpráv.

2. ### Může příjemce zakázat potvrzení o přečtení e-mailů?
   Ano, e-mailoví klienti často uživatelům umožňují zakázat odesílání potvrzení o přečtení. Proto není zaručeno, že je vždy obdržíte.

3. ### Jsou potvrzení o přečtení e-mailů standardní funkcí ve všech e-mailových klientech?
   Ne, potvrzení o přečtení e-mailů nejsou univerzálně podporována. Jejich fungování závisí na e-mailovém klientovi a nastavení příjemce.

4. ### Je možné sledovat, kdy je e-mail otevřen na mobilním zařízení?
   Sledování e-mailů je obvykle založeno na e-mailovém klientovi a nastavení příjemce, takže na mobilních zařízeních může, ale nemusí fungovat v závislosti na různých faktorech.

5. ### Existují při používání potvrzení o přečtení e-mailů aspekty ochrany osobních údajů?
   Ano, sledování e-mailů s sebou nese obavy o soukromí. Někteří příjemci to mohou považovat za invazivní, proto je nezbytné tuto funkci používat zodpovědně a respektovat preference týkající se soukromí.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}