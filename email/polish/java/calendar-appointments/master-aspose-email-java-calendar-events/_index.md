---
date: '2026-08-01'
description: Dowiedz się, jak eksportować kalendarz do PST przy użyciu Aspose.Email
  for Java, w tym jak dodać uczestników, ustawić daty rozpoczęcia i zakończenia oraz
  efektywnie zarządzać spotkaniami.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Eksportuj kalendarz do PST przy użyciu Aspose.Email for Java. Dowiedz
  się krok po kroku, jak tworzyć spotkania, dodawać uczestników i generować pliki
  Outlook PST.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Eksport kalendarza do PST – Kompletny przewodnik z Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Eksportuj kalendarz do PST przy użyciu Aspose.Email for Java
url: /pl/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Eksportowanie kalendarza do PST przy użyciu Aspose.Email dla Javy

Jeśli tworzysz aplikację w Javie, która musi udostępniać dane o planowaniu w Outlooku, często będziesz musiał **eksportować kalendarz do PST**. W tym samouczku przeprowadzimy Cię przez wszystko, czego potrzebujesz — od stworzenia prostego spotkania, przez dodanie uczestników, aż po zapisanie zdarzeń do pliku PST, wszystko przy użyciu Aspose.Email dla Javy. Po zakończeniu będziesz mieć gotowe do produkcji rozwiązanie działające na systemach Windows, Linux i macOS.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Eksportowanie zdarzeń kalendarza do pliku PST.  
- **Która biblioteka jest wymagana?** Aspose.Email for Java (v25.4+).  
- **Czy potrzebna jest licencja?** Tak, ważna licencja Aspose.Email usuwa ograniczenia wersji ewaluacyjnej.  
- **Czy mogę dodać uczestników?** Oczywiście – użyj `MapiRecipientCollection`.  
- **Jaką wersję Javy obsługuje?** JDK 16 lub wyższą.

## Co to jest **eksportowanie kalendarza do pst**?
`MapiCalendar` to klasa Aspose.Email, która modeluje element kalendarza Outlook, w tym temat, lokalizację i szczegóły czasowe.

Eksportowanie kalendarza do PST oznacza konwersję obiektów `MapiCalendar` znajdujących się w pamięci do Microsoft Outlook Personal Storage Table (PST). Wygenerowany plik PST może być otwarty bezpośrednio w Outlooku, udostępniony współpracownikom lub zaimportowany do dowolnego systemu rozumiejącego format PST, zachowując wszystkie szczegóły zdarzeń, takie jak uczestnicy, powtarzalność i przypomnienia.

## Dlaczego warto używać Aspose.Email dla Javy do eksportowania kalendarza do PST?
Możesz wygenerować w pełni kompatybilny plik PST bez instalowania Outlooka. Aspose.Email zapewnia **pełne wsparcie MAPI**, działa na **wszystkich głównych systemach operacyjnych** i może obsłużyć **do 2 TB** danych w formacie Unicode PST — wystarczająco dla archiwów na skalę przedsiębiorstwa. API pozwala również zarządzać uczestnikami, wzorcami powtarzalności, przypomnieniami i własnościami niestandardowymi przy użyciu kilku wywołań metod, co znacząco redukuje nakład pracy programistycznej.

## Wymagania wstępne
- **Biblioteki i zależności**: Aspose.Email for Java wersja 25.4 lub nowsza.  
- **Środowisko**: JDK 16 lub wyższy, Maven do zarządzania zależnościami.  
- **Wiedza**: Podstawowa programowanie w Javie oraz znajomość Maven.

## Jak skonfigurować Aspose.Email dla Javy
Dodaj zależność Aspose.Email do swojego `pom.xml` i odśwież projekt Maven. Ten pojedynczy krok udostępnia całe API MAPI na Twojej ścieżce klas.

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

### Uzyskanie licencji
Odblokuj pełną funkcjonalność Aspose.Email bez ograniczeń wersji ewaluacyjnej, uzyskując licencję:

1. **Bezpłatna wersja próbna**: Odwiedź [stronę pobierania Aspose](https://releases.aspose.com/email/java/) po tymczasową licencję.  
2. **Licencja tymczasowa**: Złóż wniosek przez [stronę zakupu](https://purchase.aspose.com/temporary-license/).  
3. **Kup licencję**: Rozważ zakup przez [portal zakupowy Aspose](https://purchase.aspose.com/buy) do długoterminowego użytku.

Po uzyskaniu licencji, zainicjalizuj ją w aplikacji, aby włączyć wszystkie funkcje.

## Jak **utworzyć spotkanie** (Create Calendar Event Java)

Wczytaj obiekt `MapiCalendar`, ustaw jego podstawowe właściwości i zwróć gotowy do dalszego przetwarzania. Ta metoda tworzy wpis kalendarza z tematem, lokalizacją, opisem oraz **datą rozpoczęcia kalendarza java** / **datą zakończenia kalendarza java**, które zdefiniowałeś.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*Wyjaśnienie*: Klasa `MapiCalendar` jest reprezentacją Aspose.Email elementu kalendarza Outlook. Po ustawieniu podstawowych pól możesz również skonfigurować powtarzalność, przypomnienia i kategorie przed zapisaniem.

## Jak **dodać uczestników** (java add meeting attendees)

Utwórz `MapiRecipientCollection`, wypełnij go każdym uczestnikiem i dołącz do spotkania. To zapewnia, że każdy uczestnik otrzyma właściwe zaproszenie po otwarciu pliku PST.

`MapiRecipientCollection` to klasa kolekcji, która przechowuje obiekty `MapiRecipient` reprezentujące uczestników spotkania. `MapiRecipient` reprezentuje pojedynczego uczestnika z właściwościami takimi jak adres e‑mail i typ odbiorcy.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*Wyjaśnienie*: `MapiRecipient` definiuje pojedynczego uczestnika spotkania. Ustawienie typu na `MAPI_TO` oznacza adres jako głównego uczestnika, podczas gdy `MAPI_CC` lub `MAPI_BCC` mogą być użyte dla uczestników opcjonalnych.

## Jak **eksportować kalendarz do pst** (Create PST with calendar events)

Utwórz plik Unicode PST, dodaj folder "Calendar" i wstaw wcześniej utworzone obiekty `MapiCalendar`. PST może następnie zostać otwarty w Outlooku lub rozpowszechniony wśród użytkowników.

`PersonalStorage` to klasa Aspose.Email używana do tworzenia, otwierania i manipulacji plikami PST.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*Wyjaśnienie*: `PersonalStorage` jest punktem wejścia do manipulacji PST. Korzystając z formatu Unicode, unikasz limitu 2 GB starszych wersji PST i korzystasz z szybszego I/O przy dużych archiwach.

## Praktyczne zastosowania
1. **Planowanie biznesowe** – Automatyzuj tworzenie i dystrybucję wewnętrznych spotkań.  
2. **Zarządzanie wydarzeniami** – Śledź konferencje, warsztaty i listy uczestników.  
3. **Integracja z CRM** – Synchronizuj spotkania z narzędziami do zarządzania relacjami z klientami.  
4. **Planowanie projektów** – Przechowuj kamienie milowe projektu jako elementy kalendarza.  
5. **Współpraca zespołów zdalnych** – Generuj pliki PST do udostępniania offline.

## Rozważania dotyczące wydajności
- **Uwalniaj obiekty**, których już nie potrzebujesz, aby szybko zwolnić pamięć.  
- **Używaj wydajnych kolekcji** (np. `ArrayList` dla list uczestników) przy obsłudze tysięcy uczestników.  
- **Cache'uj często używane zdarzenia**, jeśli wielokrotnie odczytujesz PST, co zmniejsza operacje I/O na dysku.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Plik PST nie został utworzony** | Sprawdź uprawnienia zapisu w docelowym katalogu i upewnij się, że ścieżka folderu istnieje. |
| **Uczestnicy nie otrzymują zaproszeń** | Potwierdź, że każdy `MapiRecipient` używa `MapiRecipientType.MAPI_TO` oraz że e‑mail organizatora jest prawidłowy. |
| **Niezgodność dat** | Używaj konsekwentnie `Calendar` dla dat rozpoczęcia/zakonczenia; unikaj mieszania `java.util.Date` z innymi bibliotekami dat bez konwersji. |

## Najczęściej zadawane pytania

**P: Jak rozpocząć pracę z Aspose.Email dla Javy?**  
O: Dodaj zależność Maven przedstawioną powyżej, uzyskaj licencję i postępuj zgodnie z krokami w tym przewodniku, aby tworzyć i eksportować zdarzenia kalendarza.

**P: Czy mogę dostosować nazwę i lokalizację pliku PST?**  
O: Tak, zmień zmienną `pstFilePath` w metodzie `createPSTWithCalendarEvents()` na dowolną prawidłową ścieżkę w systemie.

**P: Czy można dodać wzorce powtarzalności do spotkań?**  
O: Oczywiście – `MapiCalendar` udostępnia właściwość `RecurrencePattern`, którą możesz skonfigurować przed zapisaniem.

**P: Czy Aspose.Email obsługuje inne formaty kalendarzy oprócz PST?**  
O: Tak, możesz eksportować do iCalendar (`.ics`) i innych formatów używając odpowiednich metod API.

**P: Jaki jest maksymalny rozmiar pliku PST, który mogę utworzyć?**  
O: W formacie Unicode (`FileFormatVersion.Unicode`) pliki PST mogą rosnąć do 2 TB, ograniczone jedynie dostępną przestrzenią dyskową.

---
**Ostatnia aktualizacja:** 2026-08-01  
**Testowano z:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Opanuj Aspose.Email dla Javy: Efektywne zarządzanie plikami Outlook PST](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Opanuj tworzenie i zapisywanie elementów kalendarza przy użyciu Aspose.Email dla Javy](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Jak odczytać wiele zdarzeń kalendarza z pliku ICS przy użyciu Aspose.Email w Javie](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}