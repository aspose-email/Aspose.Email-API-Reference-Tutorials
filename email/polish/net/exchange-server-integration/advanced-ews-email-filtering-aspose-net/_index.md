---
"date": "2025-05-30"
"description": "Poznaj zaawansowane techniki filtrowania wiadomości e-mail za pomocą Aspose.Email dla .NET i EWS. Efektywnie zarządzaj wiadomościami e-mail według daty, nadawcy, odbiorcy, powiadomień, rozmiaru i innych."
"title": "Poznaj zaawansowane filtrowanie poczty e-mail EWS z Aspose.Email .NET dla integracji z serwerem Exchange"
"url": "/pl/net/exchange-server-integration/advanced-ews-email-filtering-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie zaawansowanego filtrowania poczty e-mail EWS z Aspose.Email .NET

## Wstęp
szybko zmieniającym się cyfrowym świecie efektywne zarządzanie pocztą e-mail jest kluczowe. Przy niezliczonej liczbie wiadomości przychodzących codziennie, sortowanie ich w celu szybkiego znalezienia odpowiednich informacji może znacznie zwiększyć produktywność. Ten samouczek przeprowadzi Cię przez zaawansowane techniki filtrowania przy użyciu Aspose.Email dla .NET i Exchange Web Services (EWS). Dowiesz się, jak połączyć się z EWS i filtrować wiadomości e-mail na podstawie kryteriów, takich jak data, nadawca, odbiorca, powiadomienia o dostarczeniu, rozmiar i inne.

**Czego się nauczysz:**
- Połącz się z EWS za pomocą Aspose.Email dla .NET.
- Filtruj wiadomości e-mail według daty, nadawcy, odbiorcy i innych atrybutów.
- Wprowadź obsługę stronicowania w celu efektywnego filtrowania wiadomości.
- Zoptymalizuj wydajność podczas obsługi dużych ilości danych e-mail.

Zanim przejdziemy do szczegółów implementacji, przyjrzyjmy się wymaganiom wstępnym.

## Wymagania wstępne
Aby skorzystać z tego samouczka, upewnij się, że posiadasz:
- **Aspose.Email dla .NET** biblioteka zainstalowana w Twoim projekcie. Ten samouczek dotyczy wersji 22.x i nowszych.
- Podstawowa znajomość programowania w języku C#.
- Dostęp do serwera Exchange z włączonym EWS (np. Microsoft Outlook).
- Visual Studio lub dowolne kompatybilne środowisko IDE.

Zanim przejdziesz do sekcji wdrażania, upewnij się, że te narzędzia są skonfigurowane.

## Konfigurowanie Aspose.Email dla .NET
Najpierw zainstaluj Aspose.Email w swoim projekcie, korzystając z jednej z następujących metod:

**Interfejs wiersza poleceń .NET:**
```bash
dotnet add package Aspose.Email
```

**Konsola Menedżera Pakietów:**
```powershell
Install-Package Aspose.Email
```

**Interfejs użytkownika Menedżera pakietów NuGet:**
Wyszukaj „Aspose.Email” i zainstaluj najnowszą wersję.

### Nabycie licencji
Licencję można nabyć na trzy sposoby:
- **Bezpłatna wersja próbna:** Pobierz tymczasową licencję, aby przetestować wszystkie funkcje.
- **Licencja tymczasowa:** Poproś Aspose o bezpłatną 30-dniową licencję tymczasową.
- **Zakup:** Kup subskrypcję, jeśli uważasz, że to narzędzie jest przydatne w przypadku długoterminowych projektów.

Po zainstalowaniu i uzyskaniu licencji należy zainicjować połączenie z EWS.

## Przewodnik wdrażania

### Funkcja: Połącz się z EWS
**Przegląd:** Nawiąż połączenie z usługami Exchange Web Services (EWS) przy użyciu Aspose.Email dla platformy .NET.

#### Krok 1: Zainicjuj połączenie
```csharp
using Aspose.Email.Clients.Exchange.WebService;
using System;

const string mailboxUri = "https://outlook.office365.com/ews/exchange.asmx";
const string username = "username";
const string password = "password";
const string domain = "domain";                        

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**Wyjaśnienie:** Ten kod łączy się z serwerem Exchange przy użyciu podanych danych uwierzytelniających. Zastąp symbole zastępcze rzeczywistym adresem URI skrzynki pocztowej i danymi uwierzytelniającymi.

### Funkcja: Filtruj wiadomości e-mail według daty
**Przegląd:** Dowiedz się, jak filtrować wiadomości e-mail otrzymane dziś i w ciągu ostatnich 7 dni.

#### Krok 1: Pobierz dzisiejsze wiadomości e-mail
```csharp
using Aspose.Email.Tools.Search;
using System;

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.On(DateTime.Now);
    
    MailQuery query = builder.GetQuery();
    var messagesToday = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### Krok 2: Pobierz wiadomości e-mail z ostatnich 7 dni
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.Before(DateTime.Now);
    builder.InternalDate.Since(DateTime.Now.AddDays(-7));
    
    MailQuery query = builder.GetQuery();
    var messagesLastWeek = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**Wyjaśnienie:** Użyj `MailQueryBuilder` do konstruowania zapytań na podstawie dat wiadomości e-mail. Umożliwia to filtrowanie wiadomości e-mail otrzymanych dzisiaj lub w określonym przedziale czasowym.

### Funkcja: Filtruj wiadomości e-mail według nadawcy lub domeny
**Przegląd:** Ta funkcja pokazuje, jak filtrować wiadomości e-mail od określonego nadawcy i domeny.

#### Krok 1: Pobierz wiadomości e-mail od określonego nadawcy
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderSender = new MailQueryBuilder();
    builderSender.From.Contains("saqib.razzaq@127.0.0.1");
    
    MailQuery querySender = builderSender.GetQuery();
    var senderMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySender);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### Krok 2: Pobierz wiadomości e-mail z określonej domeny
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderDomain = new MailQueryBuilder();
    builderDomain.From.Contains("SpecificHost.com");
    
    MailQuery queryDomain = builderDomain.GetQuery();
    var domainMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryDomain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**Wyjaśnienie:** Używać `MailQueryBuilder` filtrować wiadomości e-mail według adresu e-mail nadawcy lub domeny. Pomaga to identyfikować ważne komunikaty z określonych źródeł.

### Funkcja: Filtruj wiadomości e-mail według odbiorcy lub MessageId
**Przegląd:** Dowiedz się, jak filtrować wiadomości e-mail wysyłane do określonego odbiorcy i z określonym MessageId.

#### Krok 1: Pobierz wiadomości e-mail wysłane do określonego odbiorcy
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderRecipient = new MailQueryBuilder();
    builderRecipient.To.Contains("recipient@example.com");
    
    MailQuery queryRecipient = builderRecipient.GetQuery();
    var recipientMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryRecipient);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### Krok 2: Pobierz wiadomości e-mail według określonego MessageId
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMessageId = new ExchangeQueryBuilder();
    builderMessageId.MessageId.Equals("Specific-Message-ID");
    
    MailQuery queryMessageId = builderMessageId.GetQuery();
    var messageIdMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMessageId);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**Wyjaśnienie:** Filtrowanie według odbiorcy lub MessageId pomaga skupić się na interesujących Cię wiadomościach e-mail na podstawie zamierzonego odbiorcy lub unikalnego identyfikatora.

### Funkcja: Filtruj wiadomości e-mail według powiadomień o dostarczeniu i rozmiaru
**Przegląd:** Funkcja ta demonstruje filtrowanie wiadomości e-mail na podstawie powiadomień o dostarczeniu i rozmiaru wiadomości.

#### Krok 1: Pobierz powiadomienia o dostarczeniu poczty
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMDN = new ExchangeQueryBuilder();
    builderMDN.ContentClass.Equals(ContentClassType.MDN.ToString());
    
    MailQuery queryMDN = builderMDN.GetQuery();
    var mdnMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMDN);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### Krok 2: Filtruj wiadomości według rozmiaru
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderSize = new ExchangeQueryBuilder();
    builderSize.ItemSize.Greater(80000); // Przykładowy rozmiar w bajtach
    
    MailQuery querySize = builderSize.GetQuery();
    var sizeMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySize);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**Wyjaśnienie:** Użyj tych filtrów, aby skutecznie zarządzać wiadomościami e-mail na podstawie statusu dostarczenia i rozmiaru.

## Wniosek
W tym samouczku omówiono zaawansowane techniki filtrowania wiadomości e-mail przy użyciu Aspose.Email dla .NET z EWS. Opanowując te umiejętności, możesz wydajnie zarządzać skrzynką odbiorczą, zwiększając produktywność w obsłudze dużych ilości wiadomości e-mail.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}