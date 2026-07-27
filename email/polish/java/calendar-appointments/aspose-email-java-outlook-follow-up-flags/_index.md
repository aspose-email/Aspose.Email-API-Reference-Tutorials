---
date: '2026-07-27'
description: Dowiedz się, jak ustawić flagę Outlook w Javie przy użyciu Aspose.Email
  dla Javy, obejmując tworzenie flag, flagi odbiorców, zakończenie, usuwanie oraz
  opcje odczytu.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Ustaw flagę Outlook w Javie przy użyciu Aspose.Email dla Javy. Ten
  przewodnik pokazuje, jak tworzyć, odczytywać, finalizować i usuwać flagi śledzenia
  Outlook efektywnie.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Ustaw flagę Outlook w Javie – Kompletny przewodnik programistyczny Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Ustaw flagę Outlook w Javie – Kompletny przewodnik programistyczny Aspose.Email
url: /pl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ustaw flagę Outlook w Javie przy użyciu Aspose.Email dla Javy

## Wprowadzenie
Jeśli potrzebujesz **set outlook flag java** programowo, trafiłeś we właściwe miejsce. Flaga śledzenia w Outlooku zamienia zwykły e‑mail w zadanie do monitorowania, a Aspose.Email dla Javy pozwala zarządzać tymi flagami bez konieczności instalacji Outlooka. W tym samouczku przejdziemy przez tworzenie, odczytywanie, oznaczanie jako zakończone oraz usuwanie flag, a także jak zastosować flagi dla konkretnych odbiorców. Na końcu będziesz mieć gotowy fragment kodu Javy, który automatyzuje śledzenie zadań bezpośrednio z usług backendowych.

## Szybkie odpowiedzi
- **Co oznacza „set outlook flag java”?** Dodanie flagi z datą rozpoczęcia, przypomnieniem i terminem do elementu Outlooka przy użyciu kodu Java.  
- **Jakiej biblioteki potrzebuję?** Aspose.Email dla Javy (wersja 25.4 lub nowsza).  
- **Czy potrzebna jest licencja?** Tak – wersja próbna działa w ocenie, ale do produkcji wymagana jest zakupiona licencja.  
- **Czy mogę ustawiać flagi tylko dla odbiorców?** Oczywiście – użyj `FollowUpManager.setFlagForRecipients`.  
- **Czy można później usunąć flagę?** Tak – wywołaj `FollowUpManager.clearFlag`.

## Co to jest flaga śledzenia w Outlooku?
Flaga śledzenia w Outlooku to wbudowany znacznik zadania, który może zawierać datę rozpoczęcia, przypomnienie oraz termin wykonania dla dowolnego elementu pocztowego. Przekształca e‑mail w śledzoną pozycję akcji, pomagając Tobie i Twojemu zespołowi nadążać za zaległymi zadaniami.

## Dlaczego warto używać Aspose.Email dla Javy?
Aspose.Email dla Javy obsługuje **ponad 70 formatów e‑mail** (w tym MSG, EML, MHTML i TNEF) i może przetworzyć **ponad 100 000 wiadomości na minutę** na typowym serwerze 8‑rdzeniowym, bez potrzeby instalacji Outlooka na maszynie hosta. Dzięki temu jest idealny do automatyzacji backendowej, raportowania zgodności oraz integracji z narzędziami do zarządzania projektami.

## Wymagania wstępne
- **Aspose.Email dla Javy** w wersji 25.4 lub nowszej.  
- **JDK 16+** zainstalowane.  
- IDE zgodne z Maven (IntelliJ IDEA, Eclipse itp.).  
- Podstawowa znajomość Javy oraz koncepcji e‑mail.

## Konfiguracja Aspose.Email dla Javy
### Konfiguracja Maven
Dodaj następującą zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Uzyskanie licencji
Aspose.Email wymaga licencji do użytku produkcyjnego:

- **Bezpłatna wersja próbna** – 30‑dniowa ocena.  
- **Licencja tymczasowa** – wydłużone testy.  
- **Pełna licencja** – subskrypcja na stałe.

Zainicjuj licencję przed jakąkolwiek operacją na e‑mailach:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Ustaw flagę Outlook w Javie (Funkcja 1)
### Bezpośrednia odpowiedź
Wczytaj `MailMessage`, przekonwertuj go na `MapiMessage`, skonfiguruj `FollowUpOptions` i wywołaj `FollowUpManager.setOptions`. Ta sekwencja tworzy w pełni oznaczoną flagą pozycję Outlooka w kilku linijkach kodu Java.

### Krok 1: Utwórz i zainicjuj wiadomość
`MailMessage` to wysokopoziomowa klasa Aspose.Email reprezentująca e‑mail. Po zbudowaniu wiadomości konwertujesz ją na `MapiMessage` w celu manipulacji flagą.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Najpierw budujemy `MailMessage`, ustawiamy nadawcę/odbiorcę, a następnie konwertujemy na `MapiMessage` w celu manipulacji flagą.*

### Krok 2: Zdefiniuj daty śledzenia (Przypomnienie flagi Outlook)
`FollowUpOptions` przechowuje daty rozpoczęcia, przypomnienia i terminu. Użyj klasy Java `Calendar`, aby ustawić dokładne znaczniki czasu.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Tutaj ustawiamy datę rozpoczęcia, przypomnienie (czyli **outlook flag reminder**) oraz termin przy użyciu klasy `Calendar`.*

### Krok 3: Zastosuj opcje śledzenia
Metoda `FollowUpManager.setOptions` dołącza flagę do `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Obiekt `FollowUpOptions` zawiera wszystkie szczegóły flagi, które aplikujemy przy pomocy `FollowUpManager.setOptions`.*

### Krok 4: Zapisz wiadomość
Zapisz oznaczoną wiadomość jako plik `.msg`, aby Outlook mógł wyświetlić flagę.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Wiadomość jest zapisywana jako plik `.msg` z dołączoną flagą.*

## Jak ustawić flagę dla odbiorców (Funkcja 2)?
Użyj `FollowUpManager.setFlagForRecipients` po oznaczeniu wiadomości jako szkic. Metoda ta dodaje flagę śledzenia wyłącznie do kopii odbiorcy, pozostawiając widok nadawcy niezmieniony. Wymaga ustawienia `MessageFlags.MSGFLAG_UNSENT` przed zastosowaniem flagi. Możesz także dostosować daty rozpoczęcia, przypomnienia i terminu przy pomocy obiektu `FollowUpOptions` przed wywołaniem metody.

### Bezpośrednia odpowiedź
Oznacz wiadomość jako szkic przy użyciu `MessageFlags.MSGFLAG_UNSENT`, a następnie wywołaj `FollowUpManager.setFlagForRecipients`. Outlook pokaże flagę tylko odbiorcom, nie nadawcy.

### Przegląd
Czasami potrzebujesz, aby flaga była widoczna **tylko dla odbiorców**. Ten przykład najpierw oznacza wiadomość jako szkic, a potem dodaje flagę.

#### Krok 1: Oznacz jako szkic
`MessageFlags` to wyliczenie MAPI kontrolujące stan wiadomości. Ustawienie `MSGFLAG_UNSENT` informuje Outlook, że element jest szkicem.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Ustawienie wiadomości jako niewysłanej sprawia, że Outlook traktuje ją jako szkic.*

#### Krok 2: Ustaw flagę odbiorcy
`FollowUpManager.setFlagForRecipients` dołącza flagę wyłącznie do kopii odbiorcy.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaga jest teraz widoczna tylko dla odbiorców – klasyczny scenariusz **flag for recipients**.*

## Jak oznaczyć flagę śledzenia Outlook jako zakończoną (Funkcja 3)?
Wczytaj plik .msg do `MapiMessage`, a następnie wywołaj `FollowUpManager.completeFlag`. Aktualizuje to status flagi na „Completed” i dodaje znak wyboru w Outlooku. Po zakończeniu zapisz wiadomość, aby zachować zmianę. W razie potrzeby możesz ustawić czas zakończenia, modyfikując właściwość `FlagCompleteTime` w celach audytowych.

### Bezpośrednia odpowiedź
Wczytaj istniejący plik `.msg` do `MapiMessage`, wywołaj `FollowUpManager.completeFlag` i zapisz plik. Status flagi zmieni się na „Completed” i pojawi się znak wyboru w Outlooku.

### Krok 1: Wczytaj wiadomość
`MapiMessage` potrafi odczytać zapisany plik `.msg`, dając pełny dostęp do jego właściwości MAPI.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Krok 2: Oznacz jako zakończone i zapisz
`FollowUpManager.completeFlag` aktualizuje status flagi, po czym zapisujesz zmiany.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status flagi zmienia się na „Completed”, a zaktualizowany plik jest zapisywany.*

## Jak usunąć flagę śledzenia Outlook (Funkcja 4)?
Otwórz plik .msg przy pomocy `MapiMessage`, wywołaj `FollowUpManager.clearFlag`, a następnie zapisz wiadomość. To usuwa wszystkie właściwości MAPI związane z flagą, więc Outlook nie wyświetli już żadnego wskaźnika śledzenia. Użyj tego, gdy zadanie zostaje anulowane lub nie jest już istotne. Upewnij się także, że usuniesz wszelkie niestandardowe właściwości przypomnienia, aby uniknąć pozostałych powiadomień.

### Bezpośrednia odpowiedź
Otwórz plik `.msg` przy pomocy `MapiMessage`, wywołaj `FollowUpManager.clearFlag` i zapisz plik. Wiadomość nie będzie już wyświetlać żadnego wskaźnika śledzenia w Outlooku.

### Krok 1: Wczytaj i usuń flagę
`FollowUpManager.clearFlag` usuwa wszystkie właściwości związane z flagą z wiadomości.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Wiadomość jest zapisywana bez żadnej flagi śledzenia.*

## Jak odczytać opcje flagi (Funkcja 5)?
Wywołaj `FollowUpManager.getOptions` na wczytanym `MapiMessage`, aby uzyskać obiekt `FollowUpOptions`. Obiekt ten dostarcza daty rozpoczęcia, terminu, przypomnienia oraz temat flagi, co pozwala wyświetlić lub zalogować szczegóły flagi. Jest przydatny do raportowania i audytów zgodności.

### Bezpośrednia odpowiedź
Użyj `FollowUpManager.getOptions` na wczytanym `MapiMessage`, aby pobrać obiekt `FollowUpOptions` zawierający daty rozpoczęcia, terminu, przypomnienia oraz temat flagi. Przydaje się to do raportowania lub audytów zgodności.

### Krok 1: Pobierz opcje
Zwrócony obiekt `options` daje pełną widoczność konfiguracji flagi.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Obiekt `options` zawiera teraz daty rozpoczęcia, terminu i przypomnienia oraz temat flagi – przydatny, gdy musisz **read flag options** w celu raportowania.*

## Praktyczne zastosowania
- **Integracja z zarządzaniem zadaniami:** Synchronizuj oznaczone e‑maile z Jira, Trello lub Azure Boards.  
- **Automatyczne przypomnienia:** Generuj codzienne e‑maile przypominające o zaległych śledzeniach.  
- **Audyt zgodności:** Eksportuj dane flag do raportów regulacyjnych, wykorzystując możliwość programowego odczytu opcji flagi.

## Wskazówki dotyczące wydajności
- **Obliczenia dat:** Obliczaj daty raz na partię, a nie wewnątrz pętli.  
- **Zarządzanie zasobami:** Zamykaj wszystkie strumienie i uchwyty plików po zapisaniu wiadomości.  
- **Użycie pamięci:** Przetwarzaj duże skrzynki pocztowe w partiach, aby uniknąć nadmiernego obciążenia sterty; Aspose.Email radzi sobie z setkami tysięcy wiadomości bez ładowania całego pliku do pamięci.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| Flaga nie wyświetla się w Outlooku | Wiadomość zapisana bez właściwych `MessageFlags` | Upewnij się, że `setMessageFlags` jest ustawione na `MSGFLAG_UNSENT` przed zastosowaniem flag dla odbiorców. |
| Zapis zgłasza `AccessDeniedException` | Nieprawidłowa ścieżka pliku lub brak uprawnień do zapisu | Sprawdź, czy katalog wyjściowy istnieje i czy aplikacja ma prawo zapisu. |
| Daty są przesunięte o jeden dzień | Niezgodność strefy czasowej | Używaj `TimeZone.getTimeZone("GMT")` lub konsekwentnie swojej lokalnej strefy. |

## Najczęściej zadawane pytania
**P: Czym jest Aspose.Email dla Javy?**  
O: To czysto‑Java API, które pozwala tworzyć, odczytywać i modyfikować pliki e‑mail (MSG, EML itp.) bez potrzeby instalacji Outlooka.

**P: Jak uzyskać bezpłatną licencję próbną?**  
O: Odwiedź [stronę Aspose](https://releases.aspose.com/email/java/) i pobierz 30‑dniową wersję próbną.

**P: Czy mogę ustawić wiele flag śledzenia w jednej wiadomości?**  
O: Outlook obsługuje tylko jedną flagę na wiadomość, ale możesz przechowywać dodatkowe dane zadania w niestandardowych właściwościach MAPI.

**P: Moja wiadomość nie jest zapisywana po ustawieniu flagi. Co sprawdzić?**  
O: Zweryfikuj, czy ścieżka `outputDir` jest prawidłowa i czy aplikacja ma uprawnienia do zapisu w tym miejscu.

**P: Jak usunąć flagi z wielu wiadomości jednocześnie?**  
O: Przejdź pętlą po kolekcji wiadomości i wywołaj `FollowUpManager.clearFlag` dla każdego `MapiMessage`.

## Zasoby
- [Dokumentacja](https://reference.aspose.com/email/java/)
- [Pobierz Aspose.Email dla Javy](https://releases.aspose.com/email/java/)
- [Bezpłatna wersja próbna Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Ostatnia aktualizacja:** 2026-07-27  
**Testowane z:** Aspose.Email dla Javy 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Zarządzanie kategoriami Outlook przy użyciu Aspose.Email dla Javy – Kompletny przewodnik](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Tworzenie notatek Outlook w Javie z Aspose.Email – Pełny przewodnik](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Tworzenie zadań w Microsoft Exchange przy użyciu Aspose.Email dla Javy: Kompletny przewodnik](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}