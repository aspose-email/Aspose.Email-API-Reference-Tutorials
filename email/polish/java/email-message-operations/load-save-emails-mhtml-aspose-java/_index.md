---
date: '2026-02-27'
description: Dowiedz się, jak wczytywać pliki MSG i konwertować je na MHTML przy użyciu
  Aspose.Email dla Javy, w tym ustawienia niestandardowej strefy czasowej oraz wskazówki
  dotyczące przetwarzania e‑maili wsadowo.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Jak wczytać plik MSG i zapisać jako MHTML przy użyciu Aspose.Email dla Javy
url: /pl/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak wczytać plik MSG i zapisać jako MHTML przy użyciu Aspose.Email dla Javy

## Wprowadzenie

Jeśli potrzebujesz **wczytać pliki msg**, dostosować ich znaczniki czasu, a następnie **przekonwertować msg na mhtml**, jesteś we właściwym miejscu. W tym samouczku przeprowadzimy Cię przez wczytywanie wiadomości e‑mail w formacie `.msg`, zastosowanie własnego przesunięcia strefy czasowej oraz zapis wyniku jako archiwum MHTML — wszystko przy użyciu Aspose.Email dla Javy. Niezależnie od tego, czy obsługujesz jedną wiadomość, czy **przetwarzanie wsadowe e‑maili**, te kroki zapewnią solidne podstawy.

**Czego się nauczysz**
- Jak wczytać `MailMessage` z pliku `.msg`.
- Jak ustawić własną strefę czasową i bieżącą datę.
- Jak zapisać wiadomość jako MHTML z precyzyjnym formatowaniem.
- Wskazówki dotyczące skalowania podejścia w scenariuszach wsadowych.

Gotowy, aby usprawnić swój przepływ pracy z e‑mailami? Najpierw przygotujmy środowisko.

## Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.Email dla Javy.
- **Czy mogę wczytać MSG i wyeksportować do MHTML w jednym kroku?** Nie, najpierw wczytujesz, potem dostosowujesz, a na końcu zapisujesz.
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest ważna licencja Aspose.Email.
- **Czy obsługa stref czasowych jest wspierana?** Tak, za pomocą `setTimeZoneOffset`.
- **Czy można tego używać w przetwarzaniu wsadowym?** Oczywiście – wystarczy umieścić kroki w pętli.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

### Wymagane biblioteki i zależności
- Biblioteka **Aspose.Email dla Javy** w wersji 25.4 (klasyfikator jdk16)
- Podstawowa znajomość Javy.
- IDE, takie jak IntelliJ IDEA lub Eclipse.

### Wymagania dotyczące konfiguracji środowiska
- Zainstalowany JDK 16 lub nowszy.
- Maven do zarządzania zależnościami.

## Konfiguracja Aspose.Email dla Javy

Aby dodać bibliotekę do projektu Maven, umieść następującą zależność:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroki uzyskania licencji

Rozpocznij od **bezpłatnej wersji próbnej** lub zdobądź **tymczasową licencję**, aby ocenić pełne możliwości biblioteki bez ograniczeń. Przy długoterminowym użytkowaniu rozważ zakup licencji:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Podstawowa inicjalizacja

Po dodaniu zależności, zainicjalizuj licencję w kodzie Javy:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Przewodnik implementacji

Podzielimy implementację na trzy wyraźne funkcje.

### Funkcja 1: Wczytywanie MailMessage z pliku

#### Przegląd
Wczytanie pliku `.msg` daje pełny programowy dostęp do treści e‑maila, załączników i metadanych.

#### Krok po kroku

**Import wymaganych klas**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Wczytaj wiadomość**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` pozwala kontrolować sposób interpretacji pliku MSG; domyślne ustawienia działają w większości scenariuszy.

### Funkcja 2: Ustawienie bieżącej daty i własnego przesunięcia strefy czasowej

#### Przegląd
Precyzyjne znaczniki czasu są niezbędne, gdy masz do czynienia z użytkownikami w różnych regionach.

**Ustaw bieżącą datę**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Zastosuj własne przesunięcie strefy czasowej (np. UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Przesunięcie wyrażane jest w milisekundach, więc możesz również podać wartości ujemne dla stref zachodzących od UTC.

### Funkcja 3: Zapis MailMessage jako pliku MHTML

#### Przegląd
MHTML łączy treść HTML i osadzone zasoby w jednym pliku, co jest idealne do archiwizacji lub udostępniania.

**Skonfiguruj opcje zapisu**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Zapisz wiadomość**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Powstały plik `.mhtml` zachowuje oryginalne formatowanie, obrazy i załączniki.

## Dlaczego konwertować MSG na MHTML?

Konwersja plików MSG do MHTML zapewnia przyjazną dla sieci, jednoplikową reprezentację, którą można otworzyć w dowolnej nowoczesnej przeglądarce. Jest to szczególnie przydatne w:

- **Archiwizacji prawnej**, gdzie wymagana jest wierna wizualna kopia.
- **Udostępnianiu międzyplatformowemu** bez konieczności posiadania Outlooka.
- **Wstawianiu e‑maili** do stron internetowych lub dokumentacji.

## Wskazówki dotyczące przetwarzania wsadowego e‑maili

Jeśli potrzebujesz **przetwarzania wsadowego e‑maili**, umieść kroki wczytywania, dostosowywania strefy czasowej i zapisu wewnątrz pętli iterującej po katalogu z plikami `.msg`. Pamiętaj o:

1. Ponownym użyciu jednej instancji `License`, aby uniknąć dodatkowego narzutu.
2. Zwolnieniu zasobów po każdej iteracji (`msg.dispose()` w razie potrzeby).
3. Logowaniu wszelkich niepowodzeń do osobnego pliku w celu późniejszej analizy.

## Praktyczne zastosowania

1. **Archiwizacja e‑maili:** Zachowaj komunikację w przenośnym formacie dla potrzeb zgodności.
2. **Globalne planowanie:** Dostosuj znaczniki czasu do jednej strefy przed wysyłką powiadomień.
3. **Integracja z CRM:** Automatycznie importuj zarchiwizowane e‑maile do systemu CRM jako załączniki MHTML.

## Uwagi dotyczące wydajności

- **Zarządzanie pamięcią:** Przetwarzaj duże partie w partiach, aby utrzymać niskie zużycie pamięci.
- **Optymalizacja I/O:** Używaj buforowanych strumieni przy odczycie/zapisie wielu plików.
- **Wykonanie równoległe:** Rozważ `ForkJoinPool` w Javie do przetwarzania równoległego, ale zapewnij bezpieczeństwo wątkowe obiektów Aspose.

## Zakończenie

Teraz wiesz **jak wczytać pliki msg**, zastosować własne przesunięcia strefy czasowej i **przekonwertować msg na mhtml** przy użyciu Aspose.Email dla Javy. Techniki te można skalować, aby obsłużyć **przetwarzanie wsadowe e‑maili**, oferując solidne rozwiązanie do archiwizacji, migracji i automatyzacji wiadomości.

**Kolejne kroki**  
Poznaj dodatkowe funkcje Aspose.Email, takie jak obsługa załączników, ekstrakcja elementów kalendarza czy wysyłanie SMTP, odwiedzając oficjalną [dokumentację](https://reference.aspose.com/email/java/).

## Najczęściej zadawane pytania

**P: Czy mogę wczytywać e‑maile z formatów innych niż .msg?**  
O: Tak, Aspose.Email obsługuje EML, MSG, MHT i kilka innych formatów.

**P: Jak efektywnie obsługiwać bardzo duże pliki e‑mail?**  
O: Skorzystaj z API strumieniowych udostępnianych przez Aspose.Email, aby czytać/zapisywać dane w fragmentach, zmniejszając obciążenie pamięci.

**P: Czy można modyfikować załączniki w MailMessage?**  
O: Oczywiście. Możesz dodawać, usuwać lub zamieniać załączniki poprzez kolekcję `MailMessage.getAttachments()`.

**P: Co zrobić, gdy moje przesunięcie strefy czasowej jest ujemne (za UTC)?**  
O: Przekaż ujemną wartość w milisekundach do `setTimeZoneOffset`, np. `-3 * 60 * 60 * 1000` dla UTC‑3.

**P: Czy mogę używać Aspose.Email w projektach komercyjnych?**  
O: Tak, pod warunkiem posiadania ważnej licencji komercyjnej.

**P: Jak przetwarzać tysiące plików MSG bez wyczerpania pamięci?**  
O: Przetwarzaj pliki w partiach, zwalniaj każdy `MailMessage` po zapisaniu i rozważ użycie wzorca `try‑with‑resources` w Javie dla automatycznego czyszczenia.

## Zasoby
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Ostatnia aktualizacja:** 2026-02-27  
**Testowano z:** Aspose.Email dla Javy 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}