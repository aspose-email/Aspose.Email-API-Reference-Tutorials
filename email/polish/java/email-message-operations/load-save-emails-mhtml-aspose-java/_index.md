---
date: '2026-08-27'
description: Dowiedz się, jak wczytywać pliki MSG i konwertować je na MHTML przy użyciu
  Aspose.Email for Java, w tym ustawienia niestandardowej strefy czasowej oraz wskazówki
  dotyczące przetwarzania e‑maili wsadowo.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Dowiedz się, jak wczytywać pliki MSG i eksportować je jako MHTML przy
  użyciu Aspose.Email for Java. Zawiera obsługę stref czasowych i wskazówki dotyczące
  przetwarzania wsadowego.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Jak wczytać plik MSG i zapisać jako MHTML z Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Jak wczytać plik MSG i zapisać jako MHTML przy użyciu Aspose.Email for Java
url: /pl/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak załadować plik msg i zapisać jako MHTML przy użyciu Aspose.Email dla Javy

## Wprowadzenie

Jeśli potrzebujesz **jak załadować plik msg**, dostosować ich znaczniki czasu, a następnie **przekonwertować msg na mhtml**, jesteś we właściwym miejscu. W tym samouczku przeprowadzimy Cię przez ładowanie wiadomości e‑mail w formacie `.msg`, zastosowanie własnego przesunięcia strefy czasowej oraz zapis wyniku jako archiwum MHTML — wszystko przy użyciu Aspose.Email dla Java. Niezależnie od tego, czy obsługujesz pojedynczą wiadomość, czy **przetwarzanie e‑maili wsadowe**, te kroki zapewnią solidne podstawy do niezawodnego archiwizowania i migracji.

**Czego się nauczysz**
- Jak załadować `MailMessage` z pliku `.msg`.
- Jak ustawić własną strefę czasową i bieżącą datę.
- Jak zapisać wiadomość jako MHTML z precyzyjnym formatowaniem.
- Wskazówki dotyczące skalowania podejścia w scenariuszach wsadowych.

Gotowy, aby usprawnić swój przepływ pracy z e‑mailami? Najpierw przygotujmy środowisko.

## Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.Email dla Java.
- **Czy mogę załadować MSG i wyeksportować do MHTML w jednym kroku?** Nie, najpierw ładujesz, potem dostosowujesz, a na końcu zapisujesz.
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest ważna licencja Aspose.Email.
- **Czy obsługa strefy czasowej jest wspierana?** Tak, poprzez `setTimeZoneOffset`.
- **Czy można tego używać w przetwarzaniu wsadowym?** Absolutnie – wystarczy opakować kroki w pętlę.

## Co to jest Aspose.Email dla Java?

Aspose.Email dla Java to kompleksowe API, które pozwala tworzyć, odczytywać, konwertować i manipulować wiadomościami e‑mail bez konieczności posiadania Microsoft Outlook. Obsługuje ponad 30 formatów e‑mail i może przetwarzać wiadomości liczące setki stron, jednocześnie utrzymując niskie zużycie pamięci.

## Dlaczego konwertować MSG na MHTML?

Konwersja plików MSG do MHTML daje przyjazną dla sieci, jednoplikową reprezentację, którą można otworzyć w dowolnej nowoczesnej przeglądarce. Ten format zachowuje oryginalne style, osadzone obrazy i załączniki, co czyni go idealnym do **archiwizacji prawnej**, **udostępniania między platformami** oraz **osadzania e‑maili w stronach internetowych lub dokumentacji**.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

### Wymagane biblioteki i zależności
- Biblioteka **Aspose.Email dla Java** w wersji 25.4 (klasyfikator jdk16) – biblioteka obsługuje **ponad 50** formatów wejściowych i wyjściowych e‑mail.
- Podstawowa znajomość Javy.
- IDE, takie jak IntelliJ IDEA lub Eclipse.

### Wymagania dotyczące konfiguracji środowiska
- Zainstalowany JDK 16 lub nowszy.
- Maven do zarządzania zależnościami.

## Konfiguracja Aspose.Email dla Java

Aby dodać bibliotekę do projektu Maven, włącz następującą zależność:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroki uzyskania licencji

Rozpocznij od **bezpłatnej wersji próbnej** lub uzyskaj **tymczasową licencję**, aby ocenić pełne możliwości biblioteki bez ograniczeń. Do długoterminowego użycia rozważ zakup licencji:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Podstawowa inicjalizacja

Klasa `License` rejestruje Twoją licencję Aspose.Email, odblokowując pełne funkcje.  
Po dodaniu zależności, zainicjalizuj licencję w kodzie Java:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Jak załadować msg i zapisać jako MHTML?

Załaduj plik MSG, dostosuj znacznik czasu i zapisz go jako MHTML w trzech prostych krokach. Najpierw utwórz `MailMessage` z pliku MSG przy użyciu `MsgLoadOptions`. Następnie ustaw żądane przesunięcie strefy czasowej za pomocą `setTimeZoneOffset`. Na końcu skonfiguruj `MhtSaveOptions` i wywołaj `save`, aby wygenerować archiwum MHTML.

### Funkcja 1: ładowanie MailMessage z pliku

Klasa `MailMessage` reprezentuje wiadomość e‑mail z nagłówkami, treścią i załącznikami.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` pozwala kontrolować sposób parsowania pliku MSG; domyślne ustawienia działają w większości scenariuszy.

### Funkcja 2: ustawianie bieżącej daty i własnego przesunięcia strefy czasowej

Obiekt `Date` przechowuje znacznik czasu, który zostanie zapisany w nagłówku **Date** wiadomości.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Przesunięcie wyrażane jest w milisekundach; dla UTC+5 podajesz `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Funkcja 3: zapisywanie MailMessage jako pliku MHTML

`MhtSaveOptions` definiuje, jak e‑mail jest pakowany do archiwum MHTML, zachowując obrazy w linii i załączniki.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Wynikowy plik `.mhtml` zachowuje oryginalne formatowanie, obrazy i załączniki, będąc wierną wizualną kopią pierwotnego MSG.

## Jak ustawić własne przesunięcie strefy czasowej?

Możesz zmodyfikować strefę czasową, wywołując `setTimeZoneOffset` na instancji `MailMessage`. Metoda oczekuje przesunięcia w milisekundach, umożliwiając zarówno wartości dodatnie (wschód od UTC), jak i ujemne (zachód od UTC). Przykładowo, UTC‑3 to `-3 * 60 * 60 * 1000`.

## Jak przetwarzać pliki MSG wsadowo?

Opakuj trzy‑etapowy przepływ w pętlę, która iteruje po katalogu z plikami `.msg`. Ponownie użyj jednej instancji `License`, aby uniknąć wielokrotnego I/O, i zwalniaj każdy `MailMessage` po zapisaniu, aby utrzymać niskie zużycie pamięci.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Wskazówki dotyczące przetwarzania wsadowego
1. **Ponowne użycie licencji** – wywołaj `new License().setLicense(...)` raz przy uruchamianiu aplikacji.
2. **Używaj try‑with‑resources** dla automatycznego czyszczenia strumieni.
3. **Loguj niepowodzenia** do osobnego pliku, aby móc później ponowić przetwarzanie problematycznych wiadomości.
4. **Rozważ równoległość** z `ForkJoinPool` przy dużych partiach, ale zapewnij, że każdy wątek używa własnej instancji `MailMessage`.

## Typowe problemy i rozwiązania

- **Skoki pamięci przy ogromnych plikach MSG** – włącz strumieniowanie, używając `MailMessage.load(InputStream, MsgLoadOptions)` i przetwarzaj strumień w fragmentach.
- **Nieprawidłowe znaczniki czasu** – upewnij się, że zegar systemowy jest ustawiony na UTC przed zastosowaniem przesunięć, lub jawnie przekaż instancję `java.util.Calendar`.
- **Brak załączników w MHTML** – upewnij się, że `MhtSaveOptions.setWriteHeader(true)` jest włączone; to osadza załączniki jako zasoby `cid:`.

## Najczęściej zadawane pytania

**P: Czy mogę ładować e‑maile z formatów innych niż .msg?**  
O: Tak, Aspose.Email obsługuje EML, MHT, EMLX i kilka innych formatów, łącznie z ponad 30 typami wejściowymi.

**P: Jak efektywnie obsługiwać bardzo duże pliki e‑mail?**  
O: Skorzystaj z API strumieniowych (`MailMessage.load(InputStream, ...)`) do odczytu i zapisu danych w fragmentach, co utrzymuje zużycie pamięci poniżej 50 MB nawet przy wiadomościach o 500 stronach.

**P: Czy można modyfikować załączniki w MailMessage?**  
O: Absolutnie. Możesz dodawać, usuwać lub zamieniać załączniki poprzez kolekcję `msg.getAttachments()`, a następnie wywołać `save`, aby zapisać zmiany.

**P: Co zrobić, gdy moje przesunięcie strefy czasowej jest ujemne (zachodnie względem UTC)?**  
O: Przekaż ujemną wartość w milisekundach do `setTimeZoneOffset`, np. `-3 * 60 * 60 * 1000` dla UTC‑3.

**P: Czy mogę używać Aspose.Email w projektach komercyjnych?**  
O: Tak, pod warunkiem posiadania ważnej licencji komercyjnej. Bezpłatna wersja próbna jest ograniczona do 20 MB na dokument.

**P: Jak przetwarzać tysiące plików MSG bez wyczerpania pamięci?**  
O: Przetwarzaj pliki w partiach, zwalniaj każdy `MailMessage` po zapisaniu i stosuj wzorzec `try‑with‑resources` Javy dla automatycznego czyszczenia.

## Zasoby
- [documentation](https://reference.aspose.com/email/java/)
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Ostatnia aktualizacja:** 2026-08-27  
**Testowano z:** Aspose.Email dla Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

## Powiązane samouczki

- [How to Load and Parse Outlook MSG Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email for Java: Save Emails as MHT Files](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [How to extract attachments from msg files using Aspose.Email for Java](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}