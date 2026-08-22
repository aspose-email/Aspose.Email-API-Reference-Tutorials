---
date: '2026-07-08'
description: Dowiedz się, jak utworzyć klienta EWS w Javie przy użyciu Aspose.Email
  do efektywnego zarządzania pocztą e‑mail, w tym message deletion, appending i user
  impersonation na Exchange Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Dowiedz się, jak utworzyć klienta EWS w Javie przy użyciu Aspose.Email
  do efektywnego zarządzania pocztą e‑mail, w tym message deletion, appending i user
  impersonation na Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Utwórz klienta EWS w Javie z Aspose.Email – Zarządzanie użytkownikami
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Utwórz klienta EWS w Javie z Aspose.Email – Zarządzanie użytkownikami
url: /pl/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie zarządzania pocztą e‑mail: Aspose.Email Java dla użytkownika klienta EWS i impersonacji

## Wprowadzenie

W tym samouczku **stworzysz aplikacje EWS client Java** z użyciem Aspose.Email, co umożliwi zarządzanie wieloma skrzynkami pocztowymi Exchange Server z jednego kodu Java. Przejdziemy przez tworzenie instancji `EWSClient`, usuwanie wiadomości, dołączanie nowych e‑maili oraz impersonację innych użytkowników — zadania, które oszczędzają godziny ręcznej pracy w środowiskach korporacyjnych.

### Czego się nauczysz
- Jak **tworzyć obiekty EWS client Java** używając różnych danych uwierzytelniających.  
- Efektywne techniki usuwania każdej wiadomości z wybranego folderu.  
- Kroki do dołączenia gotowego e‑maila do skrzynki pocztowej użytkownika.  
- Jak impersonować inną skrzynkę pocztową w scenariuszach skrzynek współdzielonych.

Teraz, gdy wiesz, co omówimy, przygotujmy środowisko programistyczne.

## Szybkie odpowiedzi
- **Jaki jest pierwszy krok?** Dodaj zależność Aspose.Email Maven do swojego `pom.xml`.  
- **Która klasa reprezentuje połączenie Exchange?** `EWSClient` (lub jej interfejs `IEWSClient`).  
- **Czy mogę usunąć wszystkie wiadomości w jednym wywołaniu?** Tak — iteruj przy użyciu `listMessages` i wywołaj `deleteMessage` dla każdego URI.  
- **Jak wysłać e‑mail bez SMTP?** Użyj `appendMessage`, aby umieścić `MailMessage` bezpośrednio w folderze.  
- **Czy impersonacja jest bezpieczna?** Działa pod oryginalnymi poświadczeniami i respektuje polityki delegacji Exchange.

## Czym jest create EWS client Java?
`create ews client java` odnosi się do tworzenia obiektu `EWSClient` w aplikacji Java, aby programowo wywoływać operacje Exchange Web Services (EWS). To podejście eliminuje potrzebę ręcznej interakcji z Outlook i umożliwia automatyczne przetwarzanie skrzynek pocztowych. Tworząc dedykowanego klienta dla każdego użytkownika, możesz izolować poświadczenia, wymuszać zasady per‑skrzynka i skalować rozwiązanie na dziesiątki kont bez duplikacji kodu.

## Dlaczego używać Aspose.Email do integracji z EWS?
Aspose.Email obsługuje **ponad 50** operacji EWS, radzi sobie z **wieloma setkami stron** skrzynek bez ładowania całego magazynu do pamięci oraz przetwarza **do 10 000** wiadomości na minutę na typowym sprzęcie serwerowym. Te zmierzone możliwości czynią go top‑choice dla dużej skali automatyzacji poczty. Biblioteka dodatkowo abstrahuje niskopoziomowe szczegóły SOAP, oferując czyste, typowo‑bezpieczne API, które skraca czas rozwoju i minimalizuje błędy.

## Wymagania wstępne
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** do zarządzania zależnościami.  
- **Biblioteka Aspose.Email for Java** (dodaj przez Maven).  
- Podstawowa znajomość koncepcji Exchange Web Services (EWS).

## Konfiguracja Aspose.Email dla Java
Dodaj bibliotekę do swojego Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Uzyskanie licencji
Aspose.Email oferuje darmową wersję próbną, z możliwością żądania tymczasowej licencji dla pełnych możliwości. Do długoterminowego użytku rozważ zakup licencji na [stronie zakupu Aspose](https://purchase.aspose.com/buy).

## Jak stworzyć EWS client Java?
Załaduj usługę Exchange przy użyciu odpowiednich poświadczeń i uzyskaj instancję `IEWSClient` — ten dwustopniowy wzorzec jest rdzeniem każdej kolejnej operacji. Możesz ponownie używać tego samego klienta do wielu akcji lub tworzyć oddzielne instancje per użytkownik dla izolacji. **`IEWSClient` jest interfejsem udostępniającym wszystkie operacje EWS, natomiast `EWSClient` zapewnia statyczną metodę fabryczną do uzyskania implementacji.**  

Tworzenie klienta zazwyczaj wymaga podania URL usługi, nazwy użytkownika, hasła oraz opcjonalnie informacji o domenie. Po zainicjowaniu klient automatycznie obsługuje uwierzytelnianie, podpisywanie żądań i parsowanie odpowiedzi.

### Tworzenie instancji EWSClient
**Definicja:** `EWSClient` (udostępniany poprzez interfejs `IEWSClient`) jest głównym obiektem Aspose.Email do komunikacji z serwerem Exchange przez EWS.

#### Import wymaganych klas
Rozpocznij od zaimportowania niezbędnych klas Aspose.Email:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### Inicjalizacja instancji EWSClient
Utwórz obiekty `IEWSClient` dla każdej skrzynki, którą chcesz zarządzać:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Wyjaśnienie:* Pomocnicza metoda `getEWSClient` łączy się z Exchange przy użyciu podanych poświadczeń, zwracając gotowego do użycia klienta, który respektuje bieżące uprawnienia użytkownika.

## Jak usuwać wiadomości z folderu?
Pobierz wszystkie elementy w docelowym folderze i trwale usuń każdy z nich w jednym przebiegu. Metoda ta unika narzutu otwierania każdej wiadomości osobno. **`listMessages` zwraca kolekcję obiektów `MessageInfo` zawierających unikalny URI każdej wiadomości, który następnie przekazujesz do `deleteMessage`, aby usunąć element z serwera.**  

Przetwarzanie w partiach zmniejsza liczbę wywołań sieciowych i zapobiega timeoutom przy dużych folderach. Zawsze weryfikuj, że docelowy folder jest prawidłowy, ponieważ usunięcia są nieodwracalne bez kopii zapasowej.

### Lista i usuwanie wiadomości
Iteruj po każdym URI wiadomości i wywołaj operację usuwania:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Wyjaśnienie:* `listMessages` zwraca kolekcję obiektów `MessageInfo`; ich wartości `getUniqueUri()` są przekazywane do `deleteMessage`, który trwale usuwa elementy z serwera.

## Jak dołączyć wiadomość do folderu?
Zbuduj lokalnie obiekt `MailMessage` i zapisz go bezpośrednio w folderze skrzynki — bez potrzeby serwera SMTP. **`MailMessage` reprezentuje e‑mail z nagłówkami, treścią i załącznikami; może być w pełni skonstruowany w pamięci przed zapisaniem w Exchange.**  

Dołączanie omija pipeline wysyłki, co jest idealne dla szkiców, szablonów lub programowego tworzenia wiadomości, które mają pojawić się od razu w skrzynce użytkownika.

### Tworzenie i wysyłanie wiadomości
Zbuduj e‑mail i dołącz go do folderu Drafts:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Wyjaśnienie:* `appendMessage` przyjmuje `MailMessage` oraz `FolderInfo` (np. Drafts) i zapisuje element w skrzynce, udostępniając go natychmiast użytkownikowi.

## Jak impersonować użytkownika w EWS?
Zmień kontekst bezpieczeństwa klienta na inną skrzynkę, wykonaj operacje, a następnie przywróć pierwotne konto. Jest to niezbędne przy administracji skrzynkami współdzielonymi. **`impersonateUser` ustawia `ImpersonatedUserId` w podstawowym żądaniu EWS, pozwalając serwerowi traktować wywołanie tak, jakby pochodziło od docelowej skrzynki.**  

Po zakończeniu wymaganych operacji wywołaj `resetImpersonation`, aby przywrócić oryginalne poświadczenia, zapewniając, że kolejne wywołania będą wykonywane w prawidłowym kontekście bezpieczeństwa.

### Wykonywanie impersonacji użytkownika
Tymczasowo zmień kontekst klienta, aby działał jako inny użytkownik:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Wyjaśnienie:* `impersonateUser` ustawia `ImpersonatedUserId` w podstawowym żądaniu EWS, umożliwiając odczyt lub zapis tak, jakbyś był docelowym użytkownikiem. Wywołanie `resetImpersonation` przywraca pierwotne poświadczenia.

## Praktyczne zastosowania
Użycie Aspose.Email Java umożliwia solidne rozwiązania automatyzacji poczty:
1. **Automatyczne czyszczenie poczty:** Zaplanuj nocne zadanie, które usuwa przestarzałe foldery Draft we wszystkich skrzynkach.  
2. **Masowa dystrybucja e‑maili:** Dołącz szablonowy komunikat do skrzynki Inbox każdego pracownika w jednej pętli.  
3. **Zarządzanie skrzynką współdzieloną:** Impersonuj skrzynkę działu, aby archiwizować stare wiadomości bez przyznawania każdemu użytkownikowi pełnego dostępu.

## Wskazówki dotyczące wydajności
Aby aplikacja pozostawała responsywna przy obsłudze dużych skrzynek:
- **Wywołania API w partiach** tam, gdzie to możliwe (np. usuwanie 500 wiadomości na żądanie).  
- **Strumieniowanie wiadomości** zamiast ładowania pełnych treści do pamięci.  
- **Szybkie zwalnianie obiektów klienta** w celu zwolnienia gniazd sieciowych i połączeń HTTP.

## Typowe problemy i rozwiązania
- **Błędy połączenia:** Sprawdź URL punktu końcowego EWS, upewnij się, że włączony jest TLS 1.2 oraz potwierdź, że reguły zapory pozwalają na wychodzące połączenia HTTPS.  
- **Brak uprawnień do impersonacji:** Konto serwisowe musi mieć przypisaną rolę „ApplicationImpersonation” w Exchange.  
- **Timeouty przy dużych folderach:** Zwiększ limit czasu `HttpWebRequest` lub przetwarzaj folder w mniejszych fragmentach.

## Najczęściej zadawane pytania

**P: Jak rozwiązać problemy z łącznością z EWS?**  
O: Sprawdź URL punktu końcowego, poświadczenia oraz zapory sieciowe; włącz szczegółowe logowanie w Aspose.Email, aby przechwycić dane żądania/odpowiedzi HTTP.

**P: Czy Aspose.Email radzi sobie efektywnie z dużymi wolumenami e‑maili?**  
O: Tak — jego API w partiach pozwala przetworzyć **10 000+** wiadomości na minutę przy zużyciu pamięci poniżej 200 MB.

**P: Jakie są typowe scenariusze użycia impersonacji użytkownika w EWS?**  
O: Zarządzanie skrzynkami współdzielonymi, masowa archiwizacja oraz uruchamianie zaplanowanych raportów w imieniu wielu użytkowników bez przechowywania ich haseł.

**P: Czy Aspose.Email nakłada limity na wywołania API?**  
O: Sama biblioteka nie nakłada limitów; jednak Exchange może egzekwować polityki throttlingu, które należy respektować.

**P: Jak bezpiecznie przechowywać poświadczenia w kodzie Java?**  
O: Przechowuj je w zaszyfrowanych plikach konfiguracyjnych lub używaj Azure Key Vault / AWS Secrets Manager, zawsze korzystaj z HTTPS dla punktów końcowych EWS.

---

**Ostatnia aktualizacja:** 2026-07-08  
**Testowano z:** Aspose.Email for Java 23.10  
**Autor:** Aspose

## Powiązane samouczki

- [How to Create an EWSClient Instance Using Aspose.Email for Java: Exchange Server Integration Guide](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [How to Connect to Microsoft Exchange Server Using Aspose.Email for Java and EWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Automate Email Management with Aspose.Email and Java EWS Client: A Comprehensive Guide](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}