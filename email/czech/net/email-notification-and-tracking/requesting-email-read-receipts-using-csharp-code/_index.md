---
title: Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#
linktitle: Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#
second_title: Aspose.Email .NET Email Processing API
description: Naučte se používat kód C# k vyžádání potvrzení o přečtení e-mailu pomocí Aspose.Email pro .NET, což zlepšuje sledování komunikace.
weight: 11
url: /cs/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vyžádání potvrzení o přečtení e-mailu pomocí kódu C#


V dnešní digitální době se komunikace prostřednictvím e-mailu stala nedílnou součástí našeho osobního i pracovního života. Při odesílání důležitých e-mailů se často chceme ujistit, že si příjemce naši zprávu přečetl a potvrdil. Zde vstupují do hry potvrzení o přečtení e-mailů. V tomto podrobném tutoriálu vás provedeme procesem vyžádání potvrzení o přečtení e-mailu pomocí jazyka C# s Aspose.Email pro .NET.

## Úvod do e-mailových potvrzení o přečtení

Potvrzení o přečtení e-mailu, známé také jako sledování e-mailů nebo potvrzení o vrácení, vám umožňují přijímat oznámení, když příjemce otevře a přečte váš e-mail. Je to cenná funkce, zejména v obchodní komunikaci, protože poskytuje potvrzení o doručení zprávy a zapojení.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Visual Studio nainstalované ve vašem systému.
- Knihovna Aspose.Email pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 1: Vytvoření instance MailMessage

 Prvním krokem při implementaci potvrzení o přečtení e-mailu je vytvoření instance souboru`MailMessage` třída. Tato třída představuje e-mailovou zprávu a umožňuje vám nastavit různé vlastnosti e-mailu.

```csharp
MailMessage message = new MailMessage();
```

## Krok 2: Zadání podrobností zprávy

Nyní uveďme podrobnosti e-mailové zprávy, včetně odesílatele, příjemce, těla HTML a možností oznámení o doručení.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Krok 3: Vytvoření instance SmtpClient

 Abychom mohli odeslat e-mail, musíme vytvořit instanci souboru`SmtpClient` třídy, která je zodpovědná za odeslání zprávy.

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

 Nakonec použijte`client.Send` způsob odeslání e-mailové zprávy. Pokud je zpráva úspěšně odeslána, zobrazí se upozornění „Zpráva odeslána“.

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

Pomocí těchto pěti jednoduchých kroků si můžete vyžádat potvrzení o přečtení e-mailů při odesílání e-mailů pomocí C# a Aspose.Email for .NET. Tato funkce přidává úroveň jistoty k vaší e-mailové komunikaci a zajišťuje, že budete vědět, kdy jsou vaše důležité zprávy přečteny.

## Kompletní zdrojový kód
```csharp
// Vytvořte třídu Instance of MailMessage
MailMessage message = new MailMessage();

// Zadejte pole From, To, HtmlBody, DeliveryNotificationOptions
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Vytvořte instanci třídy SmtpClient Class
SmtpClient client = new SmtpClient();

// Zadejte svůj poštovní server, uživatelské jméno, heslo a číslo portu
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send odešle tuto zprávu
	client.Send(message);
	// Zobrazit 'Message Sent' (Zpráva odeslána), pouze pokud byla zpráva úspěšně odeslána
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Závěr

tomto tutoriálu jsme prozkoumali, jak si vyžádat potvrzení o přečtení e-mailu pomocí C# s Aspose.Email pro .NET. Sledování e-mailů je výkonný nástroj, který zajišťuje, že vaše zprávy budou doručeny a přečteny zamýšlenými příjemci, zejména v profesionálním prostředí. Podle zde uvedených kroků můžete tuto funkci snadno implementovat do své e-mailové aplikace.

## Často kladené otázky (FAQ)

1. ### Jaký je účel potvrzení o přečtení e-mailu?
   Potvrzení o přečtení e-mailu poskytují potvrzení, že byl e-mail otevřen a přečten příjemcem. Často se používají pro sledování důležitých nebo časově citlivých zpráv.

2. ### Může příjemce zakázat potvrzení o přečtení e-mailu?
   Ano, e-mailové klienty často umožňují uživatelům zakázat odesílání potvrzení o přečtení. Není tedy zaručeno, že je vždy obdržíte.

3. ### Jsou potvrzení o přečtení e-mailů standardní funkcí všech e-mailových klientů?
   Ne, potvrzení o přečtení e-mailu není všeobecně podporováno. Zda fungují nebo ne, závisí na e-mailovém klientovi a nastavení příjemce.

4. ### Je možné sledovat otevření e-mailu na mobilním zařízení?
   Sledování e-mailů je obvykle založeno na e-mailovém klientovi a nastavení příjemce, takže může nebo nemusí fungovat na mobilních zařízeních v závislosti na různých faktorech.

5. ### Jsou při používání potvrzení o přečtení e-mailu zohledněny zásady ochrany osobních údajů?
   Ano, existují obavy o soukromí související se sledováním e-mailů. Někteří příjemci to mohou považovat za invazivní, takže je nezbytné používat tuto funkci zodpovědně a respektovat preference ochrany soukromí.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
