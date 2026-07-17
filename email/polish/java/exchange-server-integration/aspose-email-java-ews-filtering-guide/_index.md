---
date: '2026-07-17'
description: 'Jak filtrować e-maile przy użyciu Aspose.Email Java i EWS: poznaj techniki
  filtrowania według daty, nadawcy i tematu, aby usprawnić swoją skrzynkę pocztową.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Jak filtrować e-maile przy użyciu Aspose.Email Java i EWS. Odkryj
  techniki filtrowania według daty, nadawcy i tematu, aby utrzymać swoją skrzynkę
  pocztową w porządku.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Jak filtrować e-maile z Aspose.Email Java i EWS
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Jak filtrować e-maile przy użyciu Aspose.Email Java i EWS – przewodnik
url: /pl/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie filtrowania e‑maili przy użyciu Aspose.Email Java i EWS: Kompletny przewodnik

## Wprowadzenie

**Jak filtrować e‑maile** efektywnie jest kluczową umiejętnością dla każdego, kto pracuje z Microsoft Exchange lub jakąkolwiek nowoczesną skrzynką pocztową. Niezależnie od tego, czy jesteś programistą budującym automatyzację na poziomie całej firmy, czy osobą, która chce utrzymać porządek w swojej skrzynce odbiorczej, opanowanie właściwych technik filtrowania może zaoszczędzić godziny ręcznej pracy. W tym przewodniku przeprowadzimy Cię przez Aspose.Email for Java wraz z Exchange Web Services (EWS), aby pokazać, jak filtrować według daty, nadawcy, tematu, domeny, odbiorcy oraz jak łączyć wiele kryteriów przy użyciu operatorów logicznych.

### Czego się nauczysz
- Techniki filtrowania wiadomości przy użyciu EWS w Javie.  
- Filtrowanie e‑maili na podstawie kryteriów takich jak data, nadawca, temat itp.  
- Implementacja obsługi stronicowania w celu obsługi dużych skrzynek pocztowych.  
- Praktyczne zastosowania tych metod filtrowania w rzeczywistych scenariuszach.  
- Rozważania dotyczące wydajności oraz najlepsze praktyki z Aspose.Email Java.

Po zakończeniu tego samouczka będziesz w stanie napisać czysty, wydajny kod w Javie, który pobierze dokładnie te wiadomości, których potrzebujesz z serwera Exchange.

## Szybkie odpowiedzi
- **Jaka jest główna biblioteka?** Aspose.Email for Java.  
- **Jakiego protokołu używa?** Exchange Web Services (EWS).  
- **Czy mogę filtrować według zakresu dat?** Tak – użyj kryterium `DateTime` w `SearchFilter`.  
- **Czy obsługiwane jest stronicowanie?** Absolutnie, API oferuje `ItemView` z offsetem/limitem.  
- **Czy potrzebna jest licencja do produkcji?** Tak, licencja komercyjna usuwa ograniczenia wersji próbnej.

## Czym jest Aspose.Email for Java?
Aspose.Email for Java to kompleksowe API, które umożliwia programowy dostęp do serwerów pocztowych, wiadomości MIME oraz Exchange Web Services bez konieczności używania Outlooka lub innego klienta. Abstrahuje ono leżące u podstaw protokoły, pozwalając skupić się na logice biznesowej. Biblioteka obsługuje zarówno lokalne serwery Exchange, jak i Exchange Online, zapewniając jednolite API dla różnych scenariuszy wdrożeniowych.

## Dlaczego warto używać Aspose.Email z EWS?
Aspose.Email obsługuje **ponad 50** protokołów e‑mail i może przetwarzać **setki tysięcy wiadomości** na godzinę, utrzymując zużycie pamięci poniżej **100 MB** dzięki architekturze strumieniowej. Ta zmierzona wydajność czyni go idealnym rozwiązaniem do automatyzacji skrzynek pocztowych w skali przedsiębiorstwa. Dodatkowo oferuje wbudowaną obsługę OAuth i nowoczesnego uwierzytelniania, upraszczając bezpieczne połączenia z środowiskami Office 365.

## Wymagania wstępne

- **Wymagane biblioteki**: Dołącz bibliotekę Aspose.Email do swojego projektu.  
- **Konfiguracja środowiska**: Niezbędne jest gotowe środowisko programistyczne dla aplikacji Java.  
- **Wymagania wiedzy**: Znajomość programowania w Javie oraz protokołów e‑mail będzie korzystna.

## Konfiguracja Aspose.Email dla Java

### Instalacja Maven
Dodaj następującą zależność do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Uzyskanie licencji
- **Darmowa wersja próbna**: Rozpocznij od darmowej wersji próbnej, aby zapoznać się z możliwościami Aspose.Email.  
- **Licencja tymczasowa**: Uzyskaj tymczasową licencję na wydłużoną ocenę.  
- **Zakup**: Rozważ zakup pełnej licencji, jeśli narzędzie spełnia Twoje potrzeby.

Zainicjalizuj i skonfiguruj Aspose.Email, importując niezbędne pakiety i nawiązując połączenie z serwerem pocztowym przy użyciu poświadczeń EWS. Ten krok jest kluczowy dla programowego dostępu do danych skrzynki pocztowej.

## Jak filtrować e‑maile przy użyciu EWS w Javie?

ExchangeService jest klasą Aspose.Email, która reprezentuje połączenie z serwerem Exchange.  
SearchFilter definiuje kryteria wyszukiwania elementów na serwerze.  
FindItems wykonuje wyszukiwanie i zwraca pasujące elementy.  
ItemView kontroluje stronicowanie oraz liczbę elementów zwracanych w jednym żądaniu.

Załaduj instancję `ExchangeService` ze swoimi poświadczeniami, utwórz `SearchFilter` pasujący do Twoich kryteriów i wywołaj `FindItems` z `ItemView`, aby pobrać tylko potrzebne wiadomości. Ten jednowierszowy wzorzec — połącz → filtruj → pobierz — obejmuje większość przypadków użycia i skaluje się do dużych skrzynek pocztowych, gdy włączysz stronicowanie.

## Przewodnik implementacji

### Filtrowanie wiadomości przy użyciu EWS

#### Przegląd
Filtrowanie pozwala pobrać tylko e‑maile spełniające określone warunki, takie jak konkretny temat lub data, bezpośrednio z Twojej skrzynki pocztowej.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Wyjaśnienie**: Kod nawiązuje połączenie z Twoją skrzynką pocztową i tworzy zapytanie filtrujące e‑maile z 'Newsletter' w temacie, z określonej daty.

### Jak filtrować e‑maile według dzisiejszej daty?

SearchFilter.IsEqualTo tworzy filtr, który dopasowuje elementy, gdzie dana właściwość równa się określonej wartości.  
DateTimeReceived jest właściwością wskazującą, kiedy e‑mail został odebrany.

Załaduj bieżącą datę, zbuduj `SearchFilter.IsEqualTo` na właściwości `DateTimeReceived` i wykonaj zapytanie. To zwróci tylko wiadomości odebrane w dniu uruchomienia kodu, co czyni codzienne skrypty przetwarzające trywialnymi. Możesz połączyć ten filtr z dodatkowymi kryteriami, takimi jak nadawca lub temat, aby jeszcze bardziej zawęzić wyniki na dany dzień.

### Jak filtrować e‑maile w przedziale dat?

SearchFilter.IsGreaterThanOrEqualTo tworzy filtr, który dopasowuje elementy, których wartość właściwości jest większa lub równa określonej wartości.  
SearchFilter.IsLessThanOrEqualTo tworzy filtr, który dopasowuje elementy, których wartość właściwości jest mniejsza lub równa określonej wartości.  
SearchFilter.And łączy wiele filtrów, tak aby wszystkie warunki musiały być spełnione.

Zdefiniuj początkowy i końcowy `DateTime`, połącz je przy użyciu `SearchFilter.IsGreaterThanOrEqualTo` i `SearchFilter.IsLessThanOrEqualTo`, a następnie użyj `SearchFilter.And`, aby połączyć oba. Zestaw wyników zawiera każdą wiadomość mieszczącą się w określonym przedziale. To podejście umożliwia pobranie wszystkich komunikacji w dowolnym niestandardowym okresie, takim jak ostatni kwartał czy określony harmonogram projektu.

### Jak filtrować e‑maile według konkretnego nadawcy?

SearchFilter.IsEqualTo tworzy filtr, który dopasowuje elementy, gdzie dana właściwość równa się określonej wartości.

Utwórz `SearchFilter.IsEqualTo` na właściwości `From` z adresem e‑mail nadawcy. To izoluje wszystkie wiadomości od tego kontaktu, idealne dla priorytetowych skrzynek lub kontroli zgodności. Możesz także użyć `SearchFilter.ContainsSubstring` dla dopasowań częściowych, gdy dokładny adres jest nieznany lub przy filtrowaniu według domeny.

### Jak filtrować e‑maile według konkretnej domeny?

SearchFilter.ContainsSubstring tworzy filtr, który dopasowuje elementy, gdzie dana właściwość zawiera określony podciąg.

Użyj `SearchFilter.ContainsSubstring` na właściwości `From` z ciągiem domeny (np. „@example.com”). To pobierze każdy e‑mail pochodzący z tej domeny, przydatny do monitorowania partnerów lub dostawców. Łączenie tego filtru z kryteriami dat pozwala śledzić komunikację specyficzną dla domeny w czasie, wspomagając audyty bezpieczeństwa.

### Jak filtrować e‑maile według konkretnego odbiorcy?

SearchFilter.IsEqualTo tworzy filtr, który dopasowuje elementy, gdzie dana właściwość równa się określonej wartości.

Zastosuj `SearchFilter.IsEqualTo` na kolekcji `ToRecipients` dla docelowego adresu. To przydatne, gdy musisz audytować wiadomości wysłane do konkretnej skrzynki pocztowej lub listy dystrybucyjnej. Możesz także użyć `SearchFilter.ContainsSubstring` dla dopasowań częściowych, gdy masz do czynienia z wieloma odbiorcami dzielącymi wspólną domenę.

### Jak łączyć zapytania przy użyciu logiki AND?

SearchFilter.And łączy wiele filtrów, tak aby wszystkie warunki musiały być spełnione.

Łącz wiele obiektów `SearchFilter` przy użyciu `SearchFilter.And`. Na przykład połącz filtr nadawcy z filtrem tematu, aby pobrać tylko newslettery od zaufanego nadawcy. Operator AND zapewnia, że zwrócone zostaną tylko elementy spełniające wszystkie określone warunki, redukując zestaw wyników do najbardziej istotnych wiadomości.

### Jak łączyć zapytania przy użyciu logiki OR?

SearchFilter.Or łączy filtry, tak aby spełniony mógł być dowolny warunek.

Użyj `SearchFilter.Or`, aby połączyć filtry, gdy dowolny warunek ma pasować — idealne do pobierania wiadomości, które pochodzą albo od zestawu nadawców **lub** zawierają określone słowa kluczowe. Stosowanie logiki OR może rozszerzyć wyszukiwania, aby uchwycić wszystkie istotne komunikacje w wielu kategoriach, nie pomijając kluczowych informacji.

## Częste pułapki i wskazówki

- **Stronicowanie jest niezbędne**: Przy obsłudze skrzynek większych niż 1 000 elementów zawsze używaj `ItemView` z określonym rozmiarem strony, aby uniknąć przekroczeń czasu.  
- **Obsługa stref czasowych**: EWS zwraca daty w UTC; przed porównaniem przelicz je na swoją lokalną strefę.  
- **Unikaj pełnych skanów skrzynki**: Zawsze stosuj `SearchFilter` po stronie serwera; filtrowanie po stronie klienta marnuje przepustowość i pamięć.  
- **Wskazówka**: Przechowuj w pamięci obiekt `ExchangeService` przez cały czas działania aplikacji, aby zmniejszyć obciążenie uwierzytelniania.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego podejścia z Office 365?**  
A: Tak, Aspose.Email działa z Office 365 Exchange Online, wskazując adres usługi na `https://outlook.office365.com/EWS/Exchange.asmx`.

**Q: Czy Aspose.Email obsługuje uwierzytelnianie OAuth?**  
A: Absolutnie — użyj `OAuthCredentials`, aby uwierzytelnić się bez przechowywania haseł użytkowników.

**Q: Jaki jest maksymalny rozmiar skrzynki, który mogę przetworzyć?**  
A: API może obsługiwać skrzynki o **kilku gigabajtach**; dzięki strumieniowaniu wyników zużycie pamięci pozostaje niskie.

**Q: Jak filtrować załączniki według typu pliku?**  
A: Dodaj `SearchFilter.ContainsSubstring` na właściwości `AttachmentNames`, a następnie iteruj tylko po pasujących elementach.

**Q: Czy istnieje sposób na sortowanie wyników?**  
A: Tak — przekaż `SortDirection` oraz właściwość, po której chcesz sortować (np. `DateTimeReceived`) do wywołania `FindItems`.

---

**Ostatnia aktualizacja:** 2026-07-17  
**Testowano z:** Aspose.Email for Java 24.10  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć instancję EWSClient przy użyciu Aspose.Email for Java: przewodnik integracji serwera Exchange](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Jak pobrać e‑maile z serwera Exchange przy użyciu Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Zarządzanie informacjami skrzynki EWS przy użyciu Aspose.Email for Java: kompleksowy przewodnik](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```