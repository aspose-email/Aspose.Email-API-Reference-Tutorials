---
date: '2026-09-17'
description: Dowiedz się, jak utworzyć kalendarz Outlook w Javie z codziennym powtarzaniem
  i wyjątkami oraz zapisać go w formacie PST przy użyciu Aspose.Email dla Javy.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Utwórz kalendarz Outlook w Javie przy użyciu Aspose.Email. Dowiedz
  się, jak obsługiwać codzienne powtarzanie, wyjątki oraz zapisywać do PST w przewodniku
  krok po kroku.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Utwórz kalendarz Outlook w Javie z codziennym powtarzaniem i wyjątkami
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Utwórz kalendarz Outlook w Javie z codziennym powtarzaniem i wyjątkami
url: /pl/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kalendarz Outlook w Javie z codzienną powtarzalnością i wyjątkami

Zarządzanie powtarzającymi się zdarzeniami efektywnie może być wyzwaniem, szczególnie gdy potrzebujesz **outlook calendar java**, które obsługuje codzienne wzorce powtarzalności i okazjonalne wyjątki. W tym samouczku nauczysz się, jak tworzyć obiekty Outlook calendar Java, konfigurować codzienną powtarzalność, dodawać wyjątki oraz ostatecznie **save calendar to PST** przy użyciu Aspose.Email for Java. Po zakończeniu będziesz mieć wielokrotnego użytku fragment kodu, który możesz wstawić do dowolnej usługi planowania opartej na Javie.

## Szybkie odpowiedzi
- **Która biblioteka?** Aspose.Email for Java  
- **Główne zadanie?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Wymagany JDK?** Java 16 or higher  
- **Czy mogę dołączyć pliki do wyjątków?** Yes, using `MapiCalendarExceptionInfo`  
- **Gdzie przechowywany jest kalendarz?** In a PST file via `PersonalStorage`  

## Czym jest Outlook calendar java?
Obiekt Outlook calendar Java jest programistyczną reprezentacją spotkania Outlook, zbudowaną na specyfikacji MAPI (Messaging Application Programming Interface), która obejmuje właściwości takie jak temat, lokalizacja, godziny rozpoczęcia/zakonczenia, reguły powtarzalności, uczestnicy i załączniki. Ten obiekt może być modyfikowany, serializowany i przechowywany w plikach PST bez konieczności używania Outlooka.

## Dlaczego używać Aspose.Email for Java?
Aspose.Email for Java pozwala pracować z obiektami MAPI bez instalowania Outlooka. Biblioteka obsługuje **ponad 50 właściwości MAPI**, może generować pliki Unicode PST o rozmiarze do **2 GB** w mniej niż **2 sekundy** dla typowych danych spotkań i działa na każdej platformie obsługującej Java 16+. To czysto‑Java podejście umożliwia tworzenie kalendarzy po stronie serwera, automatyzację serii spotkań oraz pełną kontrolę nad logiką powtarzalności.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następującą konfigurację:
- **Aspose.Email Library**: wersja 25.4 (lub późniejsza) – dostępna przez Maven lub bezpośrednie pobranie.  
- **Java Development Kit (JDK)**: JDK 16 lub nowszy.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans lub dowolny edytor kompatybilny z Javą.

### Wymagane biblioteki i zależności

Aby zintegrować Aspose.Email w swoim projekcie przy użyciu Maven, dodaj następującą zależność do pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Uzyskanie licencji

Aby używać Aspose.Email, potrzebna jest licencja:
- **Free trial** – przetestuj wszystkie funkcje bez kosztów.  
- **Temporary license** – poproś o przedłużoną wersję próbną.  
- **Full license** – zakup do wdrożeń produkcyjnych.

## Konfiguracja Aspose.Email dla Java

Najpierw skonfiguruj swoje środowisko:

1. Verify JDK 16 is installed and `JAVA_HOME` is configured.  
2. Add the Maven dependency (or download the JAR) to your project.  

Here’s a tiny snippet that shows how to load a license file:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## Przewodnik implementacji

### Tworzenie outlook calendar java z codzienną powtarzalnością i wyjątkami

#### Przegląd
Ta funkcja pozwala automatyzować powtarzające się spotkania, jednocześnie umożliwiając pomijanie lub modyfikowanie konkretnych wystąpień.

#### Implementacja krok po kroku

**1. Ustaw datę rozpoczęcia wydarzenia**  
Określ, kiedy seria ma się rozpocząć:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Utwórz obiekt kalendarza MAPI**  
`Klasa MapiCalendar` jest obiektem najwyższego poziomu, który reprezentuje pojedynczy element kalendarza w pamięci. Podaj lokalizację, temat i opis:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Zdefiniuj dzienny wzorzec powtarzalności**  
`Klasa MapiCalendarRecurrencePattern` przechowuje regułę, która powtarza spotkanie codziennie. Skonfiguruj wydarzenie, aby powtarzało się każdego dnia:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Dodaj wyjątek do powtarzalności**  
`MapiCalendarExceptionInfo` opisuje pojedyncze wystąpienie, które odbiega od wzorca — może być wykluczone lub zmienione. Określ datę, która ma być wykluczona (lub zmieniona):

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### Dołączanie plików do wyjątków kalendarza

#### Przegląd
Możesz dołączyć dokumenty pomocnicze (np. agendy) do dowolnego wystąpienia wyjątku.

**1. Utwórz i dołącz plik**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Zapisywanie outlook calendar java do PST (zapisz kalendarz do pst)

#### Przegląd
Zachowaj kalendarz w pliku PST, aby Outlook lub inne klienty mogły go odczytać.

**1. Utwórz i zapisz kalendarz do PST**  
`Klasa PersonalStorage` udostępnia metody do tworzenia nowego pliku PST i dodawania do niego elementów MAPI.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Praktyczne zastosowania
- **Corporate scheduling** – automatyzuj serie spotkań, automatycznie pomijając święta.  
- **Project management** – śledź powtarzające się kamienie milowe z okazjonalnymi zmianami dat.  
- **Event planning** – zarządzaj wielodniowymi konferencjami, w których niektóre sesje są odwoływane lub przestawiane.

### Możliwości integracji
Połącz Aspose.Email z platformami CRM, API zarządzania zadaniami lub własnymi silnikami przepływu pracy, aby uzyskać automatyzację end‑to‑end.

## Rozważania dotyczące wydajności
- **Dispose resources** – zawsze wywołuj `dispose()` na `PersonalStorage`, aby zwolnić uchwyty plików.  
- **Stream usage** – preferuj `ByteArrayOutputStream` lub strumienie plików, aby uniknąć ładowania całych PST do pamięci.  
- **Async operations** – przy masowej generacji kalendarzy uruchamiaj logikę tworzenia w wątku w tle, aby interfejs był responsywny.

## Zakończenie
Postępując zgodnie z tym przewodnikiem, teraz wiesz, jak **create outlook calendar java** obiekty z codzienną powtarzalnością, dodawać wyjątki, dołączać pliki oraz **save calendar to PST**. Te możliwości pozwalają budować solidne funkcje planowania bez konieczności bezpośredniego używania Outlooka.

### Kolejne kroki
- Eksperymentuj z tygodniowymi lub miesięcznymi wzorcami powtarzalności.  
- Zbadaj dodatkowe właściwości MAPI, takie jak uczestnicy, przypomnienia i kategorie.  
- Przejrzyj kompleksową dokumentację API Aspose.Email, aby poznać bardziej zaawansowane scenariusze.

## Najczęściej zadawane pytania

**Q: Czy biblioteka obsługuje spotkania z uwzględnieniem strefy czasowej?**  
A: Tak, możesz ustawić właściwości `StartTimeZone` i `EndTimeZone` w `MapiCalendar`.

**Q: Czy mogę programowo usunąć pojedyncze wystąpienie z serii powtarzalnej?**  
A: Użyj kolekcji `DeletedInstanceDates` w wzorcu powtarzalności, aby oznaczyć konkretne daty jako usunięte.

**Q: Czy istnieją limity rozmiaru pliku PST tworzonego przy użyciu Aspose.Email?**  
A: Pliki PST podlegają limitom formatu Unicode (domyślnie do 2 GB), ale możesz skonfigurować większe rozmiary za pomocą ustawień `PersonalStorage`.

**Q: Jak dodać uczestników do zaproszenia na spotkanie?**  
A: Utwórz obiekty `MapiRecipient`, ustaw ich `RecipientType` na `MapiRecipientType.MAPI_TO` i dodaj je do kolekcji `Recipients` w `MapiMessage`.

**Q: Czy istnieje obsługa powtarzających się zadań (nie tylko spotkań)?**  
A: Tak, Aspose.Email udostępnia również `MapiTask` z podobnymi możliwościami powtarzalności.

**Q: Czy mogę użyć tego przewodnika jako części serii samouczków Aspose.Email Java?**  
A: Oczywiście – przedstawione tutaj kroki są podstawową częścią każdego samouczka Aspose.Email Java dotyczącego tworzenia kalendarza.

## Zasoby
- [Dokumentacja Aspose.Email for Java](https://reference.aspose.com/email/java/)
- [Pobierz Aspose.Email](https://releases.aspose.com/email/java/)
- [Kup licencję](https://purchase.aspose.com/buy)
- [Wersja próbna](https://releases.aspose.com/email/java/)
- [Poproś o tymczasową licencję](https://purchase.aspose.com/temporary-license/)
- [Forum wsparcia Aspose](https://forum.aspose.com/c/email/10)

---

**Ostatnia aktualizacja:** 2026-09-17  
**Testowano z:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Powiązane samouczki

- [Eksportuj kalendarz Outlook PST przy użyciu Aspose.Email – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Jak utworzyć element kalendarza w Javie przy użyciu Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Utwórz zaproszenie do udostępniania kalendarza przy użyciu Aspose.Email for Java](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}