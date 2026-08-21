---
date: '2026-06-23'
description: Dowiedz się, jak filtrować e-maile według daty, nadawcy i tematu przy
  użyciu Aspose.Email dla Javy. Ten szczegółowy samouczek pokazuje, jak efektywnie
  automatyzować filtrowanie e-maili w protokole IMAP.
keywords:
- how to filter emails
- filter emails by date
- filter emails by sender
- filter emails by subject
- aspose email java tutorial
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  headline: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  type: TechArticle
- description: Learn how to filter emails by date, sender, and subject using Aspose.Email
    for Java. This step‑by‑step tutorial shows you how to automate IMAP email filtering
    efficiently.
  name: How to Filter Emails in Java with Aspose.Email – A Developer’s Guide
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later.'
    text: '**Java Development Kit (JDK)** – version 8 or later.'
  - name: '**Maven** – for dependency management.'
    text: '**Maven** – for dependency management.'
  - name: '**Aspose.Email for Java** – the core library we’ll use.'
    text: '**Aspose.Email for Java** – the core library we’ll use.'
  - name: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
    text: '**Download and Install** – Maven will pull the library automatically from
      the placeholder above.'
  - name: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
    text: '**Initialize Library** – Load your license file (if you have one) before
      making any API calls:'
  type: HowTo
- questions:
  - answer: Instantiate `ImapClient` with host, port, username, and password, then
      call `client.selectFolder("Inbox")`.
    question: How do I connect to an IMAP server using Aspose.Email?
  - answer: Yes – use `ImapQueryBuilder` to combine `date` and `fromAddress` criteria;
      the library sends a single SEARCH command.
    question: Can I filter emails by both date and sender in one request?
  - answer: Absolutely – set `client.setSecurityOptions(SecurityOptions.SSL_TLS)`
      before connecting.
    question: Does Aspose.Email support SSL/TLS for secure connections?
  - answer: The library can process mailboxes with **over 100,000 messages** as long
      as you use paging; memory usage stays below 50 MB.
    question: What is the maximum mailbox size Aspose.Email can handle?
  - answer: A temporary license removes the evaluation watermark and limits; a full
      license is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
title: Jak filtrować e-maile w Javie przy użyciu Aspose.Email – Przewodnik dla programistów
url: /pl/java/email-parsing-analysis/master-email-filtering-java-aspose-email-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak filtrować e-maile w Javie przy użyciu Aspere.Email – Przewodnik dla programistów

## Wprowadzenie

Jeśli szukasz **jak filtrować e-maile** programowo, trafiłeś we właściwe miejsce. Niezależnie od tego, czy zarządzasz firmową skrzynką pocztową, tworzysz system zgłoszeń wsparcia klienta, czy po prostu chcesz utrzymać swoją prywatną skrzynkę w porządku, automatyzacja filtrowania e-maili oszczędza godziny ręcznej pracy. W tym samouczku użyjemy **Aspose.Email for Java**, biblioteki obsługującej ponad 30 protokołów e-mailowych i radzącej sobie ze skrzynkami zawierającymi ponad 100 000 wiadomości bez ładowania całego folderu do pamięci. Nauczysz się łączyć się z serwerem IMAP, stosować filtry według daty, nadawcy, tematu i innych oraz optymalizować wydajność przy przetwarzaniu na dużą skalę.

## Szybkie odpowiedzi
- **Jaka biblioteka obsługuje filtrowanie IMAP w Javie?** Aspose.Email for Java.  
- **Czy mogę filtrować według daty i nadawcy w jednym wywołaniu?** Tak – połącz kryteria przy użyciu `ImapQueryBuilder`.  
- **Czy potrzebna jest licencja do produkcji?** Pełna licencja usuwa ograniczenia wersji próbnej; tymczasowa licencja działa w testach.  
- **Czy obsługiwane jest stronicowanie?** Absolutnie – pobieraj wiadomości strona po stronie, aby utrzymać niskie zużycie pamięci.  
- **Jakiej wersji Javy wymaga?** JDK 8 lub nowszy.

## Czym jest filtrowanie e-maili w Javie?

Filtrowanie e-maili w Javie oznacza programowe wybieranie wiadomości spełniających określone kryteria — takie jak data, nadawca lub temat — aby móc przetwarzać tylko odpowiedni podzbiór. Takie podejście zmniejsza ilość danych przesyłanych przez sieć i pozwala systemom downstream pracować na skoncentrowanym zestawie e-maili, poprawiając zarówno szybkość, jak i zużycie zasobów.

## Dlaczego warto używać Aspose.Email for Java?

Aspose.Email for Java obsługuje **ponad 30 formatów wejściowych i wyjściowych**, w tym EML, MSG, MBOX i PST, i może przetwarzać **skrzynki z ponad 100 000 wiadomości**, utrzymując zużycie pamięci poniżej 50 MB dzięki filtrowaniu po stronie serwera i stronicowaniu. Biblioteka zapewnia również wbudowaną obsługę niestandardowych flag IMAP, kodowania UTF‑8 oraz zapytań rozróżniających wielkość liter, co czyni ją kompleksowym rozwiązaniem dla automatyzacji e-maili na poziomie przedsiębiorstwa.

## Wymagania wstępne

1. **Java Development Kit (JDK)** – wersja 8 lub nowsza.  
2. **Maven** – do zarządzania zależnościami.  
3. **Aspose.Email for Java** – podstawowa biblioteka, której użyjemy.

### Wymagane biblioteki i zależności

Dodaj zależność Aspose.Email do pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Uzyskanie licencji

- **Bezpłatna wersja próbna** – pobierz wersję próbną, aby wypróbować wszystkie funkcje.  
- **Licencja tymczasowa** – uzyskaj licencję czasową do rozszerzonych testów.  
- **Pełna licencja** – zakup do użytku produkcyjnego i usuń wszystkie ograniczenia wersji próbnej.  
- **Plik licencji** – zdobądź go ze [strony Aspose](https://purchase.aspose.com/temporary-license/).

## Konfiguracja Aspose.Email for Java

Aby rozpocząć korzystanie z Aspose.Email, wykonaj następujące kroki:

1. **Pobierz i zainstaluj** – Maven automatycznie pobierze bibliotekę z podanego powyżej placeholdera.  
2. **Zainicjalizuj bibliotekę** – Załaduj plik licencji (jeśli go masz) przed wykonywaniem jakichkolwiek wywołań API:

```java
License license = new License();
license.setLicense("path/to/your/license/file");
```

## Przewodnik implementacji

### Jak połączyć się z serwerem IMAP?

Aby rozpocząć, musisz nawiązać połączenie z serwerem IMAP przy użyciu klasy `ImapClient`, która reprezentuje sesję klienta zdolną do uwierzytelniania i wysyłania poleceń do serwera. To połączenie jest podstawą wszystkich kolejnych operacji na skrzynce pocztowej.

Typowa sekwencja połączenia obejmuje określenie hosta, portu, danych uwierzytelniających oraz opcji bezpieczeństwa, a następnie wybranie żądanego folderu skrzynki (np. **Inbox**) przed wykonaniem jakichkolwiek zapytań.

```java
String host = "YOUR_IMAP_SERVER"; // Replace with your actual server details.
int port = 143;
String username = "user@host.com";
String password = "password";

ImapClient client = new ImapClient(host, port, username, password);
client.selectFolder("Inbox");
```

### Jak filtrować e-maile według tematu i daty?

Klasa `ImapQueryBuilder` pomaga tworzyć złożone kryteria wyszukiwania, które są tłumaczone na wydajne polecenia IMAP SEARCH. Łącząc słowa kluczowe tematu z zakresem dat, możesz pobrać tylko wiadomości istotne dla Twojej logiki przetwarzania.

W tym przykładzie szukamy wiadomości, których temat zawiera „Newsletter” i które zostały odebrane w bieżącym dniu, minimalizując transfer danych i obciążenie przetwarzania.

```java
Calendar calendarToday = Calendar.getInstance();
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter");
builder.getInternalDate().on(calendarToday.getTime());
MailQuery query = builder.getQuery();

ImapMessageInfoCollection messages = client.listMessages(query);
```

### Jak filtrować e-maile według dzisiejszej daty?

Korzystając z `ImapQueryBuilder`, możesz utworzyć filtr dopasowujący dokładną datę kalendarzową znacznika czasu wysłania wiadomości. Jest to przydatne w codziennych zadaniach przetwarzania, które muszą działać tylko na najnowszych wiadomościach.

```java
Calendar c = Calendar.getInstance();
c.set(Calendar.YEAR, 2023);
c.set(Calendar.MONTH, Calendar.APRIL); // Note: Months are zero-based.
c.set(Calendar.DAY_OF_MONTH, 24);

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().on(c.getTime());
// Execute the query as needed here.
```

### Jak filtrować e-maile w przedziale dat?

Gdy potrzebujesz pracować w przedziale kilku dni, `ImapQueryBuilder` pozwala określić początkowy i końcowy `DateTime`. Biblioteka konwertuje te wartości na odpowiednią składnię IMAP SEARCH, zwracając wszystkie wiadomości mieszczące się w określonym przedziale.

```java
Calendar startDate = Calendar.getInstance();
startDate.set(2023, 4, 17); // Start date set to April 17th, 2023.

MailQueryBuilder builder = new MailQueryBuilder();
builder.getInternalDate().before(Calendar.getInstance());
builder.getInternalDate().since(startDate.getTime());

// Build and execute the query as needed here.
```

### Jak filtrować e-maile według konkretnego nadawcy?

`ImapQueryBuilder` może celować w pojedynczy adres e-mail lub całą domenę, dopasowując nagłówek `From`. Umożliwia to izolowanie komunikacji od zaufanych partnerów lub odfiltrowanie niechcianych nadawców.

Podanie dokładnego adresu (np. `user@example.com`) lub wzorca domeny (np. `@example.com`) daje precyzyjne wyniki bezpośrednio z serwera.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("elon.musk@127.0.0.1");
// Execute the query as required.
```

### Jak filtrować e-maile według konkretnej domeny?

Podobnie jak przy filtrowaniu nadawcy, możesz ograniczyć wyniki do określonej domeny przy użyciu metody `fromAddress` klasy `ImapQueryBuilder`. Jest to przydatne, gdy musisz przetworzyć wszystkie wiadomości pochodzące od partnera korporacyjnego lub konkretnego dostawcy usług e-mail.

Zapytanie jest wykonywane na serwerze, więc tylko pasujące wiadomości są przesyłane do Twojej aplikacji.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("@SpecificHost.com");
// Build and execute the query as needed here.
```

### Jak filtrować e-maile według konkretnego odbiorcy?

Aby skupić się na wiadomościach skierowanych do konkretnej skrzynki, użyj metody `toAddress` klasy `ImapQueryBuilder`. Jest to szczególnie przydatne w przypadku wspólnych skrzynek lub skrzynek opartych na rolach, gdzie wielu użytkowników musi przetwarzać ten sam zestaw e-maili.

Builder tworzy klauzulę IMAP SEARCH dopasowującą nagłówek `To`, zapewniając efektywne filtrowanie po stronie serwera.

```java
MailQueryBuilder builder = new MailQueryBuilder();
builder.getTo().contains("recipient@example.com");
// Execute your query here.
```

### Jak wykonać filtrowanie e-maili rozróżniające wielkość liter?

Domyślnie wyszukiwania IMAP nie rozróżniają wielkości liter, ale `ImapQueryBuilder` oferuje opcję wymuszenia rozróżniania wielkości liter dla dokładnych dopasowań. Jest to istotne przy rozróżnianiu identyfikatorów różniących się jedynie wielkością liter.

Włącz flagę `setCaseSensitive(true)` przed dodaniem innych kryteriów, aby uzyskać precyzyjne filtrowanie.

```java
ImapQueryBuilder builder = new ImapQueryBuilder();
builder.getSubject().contains("Newsletter", true);
calendar c2 = Calendar.getInstance();
builder.getInternalDate().on(c2.getTime());
MailQuery query = builder.getQuery();
// Execute and process your query as needed.
```

### Jak określić kodowanie dla Query Buildera?

Podczas pracy z międzynarodowymi tematami lub adresami należy ustawić kodowanie znaków w `ImapQueryBuilder`. Użycie UTF‑8 zapewnia prawidłową interpretację znaków nie‑ASCII przez serwer IMAP.

Wywołaj `setEncoding(Encoding.UTF_8)` przed budowaniem zapytania, aby uniknąć zniekształconych wyników.

```java
ImapQueryBuilder builder = new ImapQueryBuilder(Charset.forName("UTF-8"));
builder.getSubject().contains("ğüşıöç", true);
MailQuery query = builder.getQuery();
// Execute and process your query here.
```

### Jak filtrować wiadomości z obsługą stronicowania?

Stronicowanie jest niezbędne przy dużych skrzynkach. `ImapClient` udostępnia metody pobierania wiadomości w partiach, co pozwala przetwarzać np. 500 wiadomości jednocześnie. Dzięki temu zużycie pamięci pozostaje niskie, a przepustowość rośnie.

Połącz stronicowanie z `ImapQueryBuilder`, aby pobierać tylko odpowiedni podzbiór na każdej stronie.

```java
ImapClient client = new ImapClient(host, port, username, password);
client.setSecurityOptions(SecurityOptions.Auto);

int itemsPerPage = 5;
String searchBody = "example body text";

ImapQueryBuilder iqb = new ImapQueryBuilder();
iqb.getBody().contains(searchBody);
MailQuery query = iqb.getQuery();

PageSettings pageSettings = new PageSettings();
pageSettings.setFolderName("Inbox");

List<ImapPageInfo> pages = new ArrayList<>();
ImapPageInfo pageInfo = client.listMessagesByPage(query, new PageInfo(itemsPerPage, 0), pageSettings);

pages.add(pageInfo);
while (!pageInfo.getLastPage()) {
    pageInfo = client.listMessagesByPage(query, pageInfo.getNextPage(), pageSettings);
    pages.add(pageInfo);
}

int retrievedItems = 0;
for (ImapPageInfo folderCol : pages) {
    retrievedItems += folderCol.getItems().size();
}
client.dispose();
```

### Jak filtrować wiadomości według niestandardowej flagi?

IMAP obsługuje flagi definiowane przez użytkownika, takie jak `\Flagged` lub własne tagi. Za pomocą `ImapQueryBuilder` możesz określić te flagi, aby pobrać tylko wiadomości oznaczone w ten sposób.

Ta możliwość jest przydatna w przepływach pracy, które polegają na flagowaniu wiadomości do późniejszego przeglądu lub specjalnego przetwarzania.

```java
ImapQueryBuilder queryBuilder = new ImapQueryBuilder();
queryBuilder.hasFlags(ImapMessageFlags.keyword("custom1"));
queryBuilder.hasNoFlags(ImapMessageFlags.keyword("custom2"));
// Execute and process your query here.
```

## Praktyczne zastosowania

- **Zarządzanie firmową pocztą** – Automatyczne sortowanie przychodzącej poczty do folderów działowych na podstawie nadawcy lub tematu.  
- **Systemy wsparcia klienta** – Priorytetyzowanie zgłoszeń poprzez filtrowanie e-maili zawierających „Urgent” lub pochodzących od klientów VIP.  
- **Narzędzia do osobistej organizacji** – Stwórz lekkie narzędzie Java, które archiwizuje dzisiejsze newslettery i usuwa spam w jednym uruchomieniu.

## Rozważania dotyczące wydajności

- **Filtrowanie po stronie serwera** – Pozwól serwerowi IMAP wykonać ciężką pracę; tylko pasujące wiadomości przemieszczają się przez sieć.  
- **Stronicowanie** – Pobieraj wyniki w partiach (np. strony po 200 wiadomości), aby uniknąć ładowania całej skrzynki do pamięci RAM.  
- **Ponowne użycie połączenia** – Utrzymuj jedną instancję `ImapClient` aktywną przez cały czas trwania zadania wsadowego, aby zmniejszyć narzut związany z nawiązywaniem połączenia.  
- **Monitorowanie** – Rejestruj liczbę przetworzonych wiadomości i upływający czas; dostosuj rozmiar strony, jeśli zauważysz skoki pamięci.

## Podsumowanie

Masz teraz kompletny zestaw narzędzi do **filtrowania e-maili** przy użyciu Aspose.Email for Java. Od prostych zapytań opartych na dacie po złożone filtry wielokryterialne z niestandardowymi flagami, biblioteka zapewnia precyzyjną kontrolę przy zachowaniu optymalnej wydajności.

### Kolejne kroki

- Połącz te filtry w jedną wielokrotnego użytku metodę dla swojej aplikacji.  
- Zapoznaj się z API **Aspose.Email** w celu wysyłania, przekazywania i odpowiadania na wiadomości.  
- Zintegruj z bazą danych, aby przechowywać metadane przefiltrowanych wiadomości w celach analitycznych.

---

## Najczęściej zadawane pytania

**Q: Jak połączyć się z serwerem IMAP przy użyciu Aspose.Email?**  
A: Zainstaluj `ImapClient` z hostem, portem, nazwą użytkownika i hasłem, a następnie wywołaj `client.selectFolder("Inbox")`.

**Q: Czy mogę filtrować e-maile zarówno według daty, jak i nadawcy w jednym żądaniu?**  
A: Tak – użyj `ImapQueryBuilder` do połączenia kryteriów `date` i `fromAddress`; biblioteka wysyła pojedyncze polecenie SEARCH.

**Q: Czy Aspose.Email obsługuje SSL/TLS dla bezpiecznych połączeń?**  
A: Absolutnie – ustaw `client.setSecurityOptions(SecurityOptions.SSL_TLS)` przed połączeniem.

**Q: Jaki jest maksymalny rozmiar skrzynki, który Aspose.Email może obsłużyć?**  
A: Biblioteka może przetwarzać skrzynki z **ponad 100 000 wiadomości**, pod warunkiem użycia stronicowania; zużycie pamięci pozostaje poniżej 50 MB.

**Q: Czy potrzebna jest licencja do wersji deweloperskich?**  
A: Licencja tymczasowa usuwa znak wodny i ograniczenia wersji próbnej; pełna licencja jest wymagana przy wdrożeniach produkcyjnych.

---

**Ostatnia aktualizacja:** 2026-06-23  
**Testowano z:** Aspose.Email for Java 24.9  
**Autor:** Aspose

## Powiązane samouczki

- [Pobierz e-maile z serwera IMAP przy użyciu Aspose.Email for Java: Przewodnik krok po kroku](/email/java/imap-client-operations/fetch-emails-imap-aspose-java/)
- [Opanuj inicjalizację klienta IMAP w Javie z Aspose.Email: Kompletny przewodnik](/email/java/imap-client-operations/imap-client-initialization-java-aspose-email/)
- [Jak wykonać kopię zapasową e-maili IMAP przy użyciu Aspose.Email for Java: Przewodnik krok po kroku](/email/java/imap-client-operations/imap-backup-aspose-email-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}