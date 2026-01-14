---
date: '2025-12-19'
description: Dowiedz się, jak ustawiać flagi śledzenia w Outlooku przy użyciu Aspose.Email
  dla Javy, w tym jak ustawiać flagę śledzenia w Outlooku i efektywnie usuwać flagę
  śledzenia w Outlooku.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Jak ustawić flagi śledzenia w Outlooku przy użyciu Aspose.Email dla Javy
url: /pl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić flagi w programie Outlook przy użyciu Aspose.Email dla Javy

## Wstęp
Jeśli dodatek stanowi problem z pojawieniem się e-maili, wiesz, jak ważne może być flagi stosowania w Outlooku. W tym przewodniku **jak ustawić flagi** programowo przy użyciu Aspose.Email dla Javy, a także omówimy, jak **umieścić flagę w Outlooku** dla odbiorców oraz jak **u rozwiązaniu flagę ograniczenia w Outlooku**, gdy zadanie zostanie zakończone. Po wykluczeniu możliwości zautomatyzowania wystąpienia zadań, przypomnienia i kontroli audytu bezpośrednio z kodu Java.

**Czego się uczysz**
- Tworzenie i zastosowanie flagi w wiadomościach Outlook.
- Usunięcie flagi dla rozstrzygnięcia.
- flagi przebiegu jako zakończone i jej następstwa.
- Odczytywanie opcji flagi w celu raportowania lub zgodności.

Przedostanie się do środowiska przed wyciekiem w kod.

## Szybkie odpowiedzi
- **Co oznacza „jak ustalić”?** Dodanie flagi z uruchomieniem, potwierdzeniem i terminem do elementu Outlook.
- **Jakiej biblioteki wymaga?** Aspose.Email dla Javy (v25.4 lub nowsza).
- **Czy jest to licencjat?** Tak, wymagana jest licencjat lub zakup, aby uzyskać pełne kwalifikacje.
- **Czy mogę ustawić flagi tylko dla odbiorców?** Oczywiście – `FollowUpManager.setFlagForRecipients`.
- **Czy można później usunąć flagę?** Tak, wywołaj `FollowUpManager.clearFlag`.

## Co to jest flaga uzupełniająca?
Oznaczenie funkcji Outlook, które oznacza e-mail jako zadanie, ewentualnie dodanie daty rozpoczęcia, przypomnienia i termin. Pomaga Tobie i Twojemu zespołowi bezpośrednio działać.

## Dlaczego warto używać Aspose.Email dla Java?
Aspose.Email czysto‑Java API, które działa bez zainstalowanego Outlooka, umożliwia manipulację plikami .msg, ustawianie flag i zadań zarządzania na zasilaniu elektrycznym — idealne dla usług backendowych, zautomatyzowanych przepływów pracy lub zintegrowanych z narzędziami do zarządzania projektami.

## Warunki wstępne
- **Aspose.Email dla Javy** wersja 25.4lub terazsza.
- **JDK16+** mechanicznie.
- IDE z Maven (IntelliJ IDEA, Eclipse itp.).
- Podstawowa przyjemność Javy oraz koncepcje e-mail.

## Konfigurowanie Aspose.Email dla Java
### Konfiguracja Mavena
Dodaj następującą zawartość do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Nabycie licencji
Aspose.Email wymaga licencji do użytku produkcyjnego:

- **Bezpłatna wersja próbna** – 30-dniowa ocena.
- **Licencja tymczasowa** – rozszerzone testowanie.
- **Pełna licencjat** – subskrypcja na zawsze.

Zainicjuj obciążenie przed operacją e-mail:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Przewodnik wdrażania

### Jak ustawić flagi uzupełniające (funkcja 1)
#### Przegląd
Ta sekcja Cię przez tworzenie wiadomości Outlook, definiowanie daty rozpoczęcia/przypomnienia/terminu oraz zastosowanie flagi zastosowania.

#### Krok 1: Utwórz i zainicjuj wiadomość
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Najpierw tworzymy `MailMessage`, ustawiamy nadawcę/odbiorcę, a następnie konwertujemy go na `MapiMessage` w celu manipulacji flagą.*

#### Krok 2: Określ daty dalszych działań
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Tutaj ustawiamy daty rozpoczęcia, przypomnienia i terminu przy użyciu klasy `Calendar`.*

#### Krok 3: Zastosuj opcje dalszych działań
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Obiekt `FollowUpOptions` zawiera wszystkie szczegóły flagi, które stosujemy za pomocą `FollowUpManager.setOptions`.*

#### Krok 4: Zapisz wiadomość
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Wiadomość jest zapisywana jako plik `.msg` z dołączoną flagą.*

### Jak ustawić flagę uzupełniającą programu Outlook dla odbiorców (funkcja 2)
#### Przegląd
Czasami trzeba o dodatkową wiadomość flagą tylko dla odbiorców. Ten przykład początkowo oznacza wiadomość jako szkic, a następnie dodaje flagę.

#### Krok 1: Oznacz jako wersję roboczą
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Oznaczenie wiadomości jako niewysłanej zapewnia, że ​​Outlook potraktuje ją jako szkic.*

#### Krok 2: Ustaw flagę odbiorcy
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaga jest teraz widoczna tylko dla odbiorców.*

### Jak oznaczyć flagę uzupełniającą programu Outlook jako ukończoną (funkcja 3)
#### Przegląd
Gdy zadanie jest zakończone, możesz programowo oznaczyć flagę jako zakończoną.

#### Krok 1: Załaduj wiadomość
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Krok 2: Oznacz jako ukończone i zapisz
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status flagi zmienia się na „Completed” i zaktualizowany plik jest zapisywany.*

### Jak usunąć flagę uzupełniającą programu Outlook (funkcja 4)
#### Przegląd
Jeśli flaga nie jest już dostępna, można ją całkowicie usunąć.

#### Krok 1: Załaduj i wyczyść flagę
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Wiadomość jest zapisywana bez żadnej flagi śledzenia.*

### Jak czytać opcje flagi uzupełniającej (funkcja 5)
#### Przegląd
Wykonaj audytu lub raportowania, jeśli potrzebujesz odczytać ustawienia flagi.

#### Krok 1: Pobierz opcje
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Obiekt `options` zawiera teraz daty rozpoczęcia, terminu i przypomnienia, a także temat flagi.*

## Praktyczne zastosowania
- **Integracja z zarządzaniem zadaniami:** Synchronizacja wyznaczonych e-maili z Jira, Trello lub Azure Boards.
- **Automatyczne przypomnienia:** Generowanie e-maili przypominających o zaległych przepisach.
- **Audyt zgodności:** Eksport danych flag do raportowania opisu.

## Względy wydajności
- **Obliczenia dat:** Obliczaj daty raz na partię, a nie wewnątrz całości.
- **Zarządzanie zasobami:** Zamykaj wszystkie strumienie lub uchwyty plików po zapisaniu wiadomości.
- **Użycie pamięci:** Przetwarzaj dużą skrzynkę pocztową w partach, aby zapewnić bezpieczeństwo sterty.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|--------|-----------|------------|
| Flaga nie pojawia się w programie Outlook | Wiadomość zapisana bez oznaczenia `MessageFlags` | zostanie zastosowane, że `setMessageFlags` jest ustalane na `MSGFLAG_UNSENT` przed zastosowaniem flagi dla odbiorców. |
| Zapis podstawowy `AccessDeniedException` | Nieprawidłowa ścieżka pliku lub brak uprawnień do zapisu | Sprawdź, czy katalog źródłowy jest aplikacją mającą uprawnienia do zapisu w tej lokalizacji. |
| Daty są przesunięte o jeden dzień | Niezgodność strefy czasowej | Używaj `TimeZone.getTimeZone("GMT")` lub swojej strefy użytkowej. |

## Często zadawane pytania
**P: Czym jest Aspose.Email dla Javy?**
Odp.: To całkowicie-Java API, które pozwala na tworzenie, udostępnianie i ustalanie plików e-mail (MSG, EML itp.) bez konieczności instalacji programu Outlook.

**Q: Jak uzyskać dostęp do wersji próbnej licencji?**
A: Odwiedź [stronę Aspose](https://releases.aspose.com/email/java/), aby otrzymać 30‑dniową próbę.

**Q: Czy można ustawić wiele flag ustaleń w jednej wiadomości?**
A: Outlook obsługuje tylko jedną flagę na wiadomość, ale może być dodatkowe dane zadań w niestandardowych wejściach MAPI.

**P: Moja wiadomość nie jest zapisywana po ustawieniu flagi. Co powinienem sprawdzić?**
A: zastosowanie się, że ścieżki `outputDir` są prawidłową aplikacją mającą uprawnienia do zapisu w tej lokalizacji.

**P: Jak mogę usunąć flagi z wielu wiadomości jednocześnie?**
A: Przejdź do kolekcji wiadomości i wywołanej `FollowUpManager.clearFlag` dla każdego `MapiMessage`.

## Zasoby
- [Dokumentacja](https://reference.aspose.com/email/java/)
- [Pobierz Aspose.Email dla Javy](https://releases.aspose.com/email/java/)
- [Bezpłatna wersja próbna Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Aktualizacja Ostatnia:** 2025-12-19
**Testowano z:** Aspose.Email dla Java 25.4 (jdk16)
**Autor:** Asponuj 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}