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
# Jak ustawić flagi śledzenia w Outlook przy użyciu Aspose.Email dla Javy

## Introduction
Jeśli kiedykolwiek miałeś problem z śledzeniem ważnych e‑maili, wiesz, jak cenne mogą być flagi śledzenia w Outlooku. W tym przewodniku pokażemy **jak ustawiać flagi śledzenia** programowo przy użyciu Aspose.Email dla Javy, a także omówimy, jak **ustawić flagę śledzenia w Outlooku** dla odbiorców oraz jak **usunąć flagę śledzenia w Outlooku**, gdy zadanie zostanie zakończone. Po zakończeniu będziesz mógł automatyzować śledzenie zadań, przypomnienia i ścieżki audytu bezpośrednio z kodu Java.

**Czego się nauczysz**
- Tworzenie i zastosowanie flagi śledzenia w wiadomości Outlook.  
- Ustawianie flag śledzenia dla konkretnych odbiorców.  
- Oznaczanie flagi jako zakończonej i późniejsze jej usunięcie.  
- Odczytywanie opcji flagi w celu raportowania lub zgodności.  

Przygotujmy środowisko przed zanurzeniem się w kod.

## Quick Answers
- **Co oznacza „jak ustawić śledzenie”?** Dodanie flagi z datą rozpoczęcia, przypomnieniem i terminem do elementu Outlook.  
- **Jakiej biblioteki wymaga?** Aspose.Email dla Javy (v25.4 lub nowsza).  
- **Czy potrzebna jest licencja?** Tak, wymagana jest licencja próbna lub zakupiona, aby uzyskać pełną funkcjonalność.  
- **Czy mogę ustawić flagi tylko dla odbiorców?** Oczywiście – użyj `FollowUpManager.setFlagForRecipients`.  
- **Czy można później usunąć flagę?** Tak, wywołaj `FollowUpManager.clearFlag`.  

## What is a Follow‑Up Flag?
Flaga śledzenia to funkcja Outlook, która oznacza e‑mail jako zadanie, opcjonalnie dołączając daty rozpoczęcia, przypomnienia i terminu. Pomaga to Tobie i Twojemu zespołowi śledzić bieżące działania.

## Why use Aspose.Email for Java?
Aspose.Email udostępnia czysto‑Java API, które działa bez zainstalowanego Outlooka, umożliwiając manipulację plikami .msg, ustawianie flag i zarządzanie zadaniami na dowolnej platformie — idealne dla usług backendowych, zautomatyzowanych przepływów pracy lub integracji z narzędziami do zarządzania projektami.

## Prerequisites
- **Aspose.Email dla Javy** wersja 25.4 lub nowsza.  
- **JDK 16+** zainstalowane.  
- IDE kompatybilne z Maven (IntelliJ IDEA, Eclipse itp.).  
- Podstawowa znajomość Javy oraz koncepcji e‑mail.

## Setting Up Aspose.Email for Java
### Maven Configuration
Dodaj następującą zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email wymaga licencji do użytku produkcyjnego:

- **Bezpłatna wersja próbna** – 30‑dniowa ocena.  
- **Licencja tymczasowa** – rozszerzone testowanie.  
- **Pełna licencja** – subskrypcja na zawsze.

Zainicjuj licencję przed jakąkolwiek operacją e‑mail:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementation Guide

### How to Set Follow‑Up Flags (Feature 1)
#### Overview
Ta sekcja przeprowadza Cię przez tworzenie wiadomości Outlook, definiowanie dat rozpoczęcia/przypomnienia/terminu oraz zastosowanie flagi śledzenia.

#### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Najpierw tworzymy `MailMessage`, ustawiamy nadawcę/odbiorcę, a następnie konwertujemy go na `MapiMessage` w celu manipulacji flagą.*

#### Step 2: Define Follow‑Up Dates
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

#### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Obiekt `FollowUpOptions` zawiera wszystkie szczegóły flagi, które stosujemy za pomocą `FollowUpManager.setOptions`.*

#### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Wiadomość jest zapisywana jako plik `.msg` z dołączoną flagą.*

### How to Set Outlook Follow‑Up Flag for Recipients (Feature 2)
#### Overview
Czasami trzeba oznaczyć wiadomość flagą tylko dla odbiorców. Ten przykład najpierw oznacza wiadomość jako szkic, a następnie dodaje flagę.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Oznaczenie wiadomości jako niewysłanej zapewnia, że Outlook potraktuje ją jako szkic.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaga jest teraz widoczna tylko dla odbiorców.*

### How to Mark an Outlook Follow‑Up Flag as Completed (Feature 3)
#### Overview
Gdy zadanie jest zakończone, możesz programowo oznaczyć flagę jako zakończoną.

#### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status flagi zmienia się na „Completed” i zaktualizowany plik jest zapisywany.*

### How to Remove Outlook Follow‑Up Flag (Feature 4)
#### Overview
Jeśli flaga nie jest już potrzebna, możesz ją całkowicie usunąć.

#### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Wiadomość jest zapisywana bez żadnej flagi śledzenia.*

### How to Read Follow‑Up Flag Options (Feature 5)
#### Overview
Do audytu lub raportowania możesz potrzebować odczytać istniejące ustawienia flagi.

#### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Obiekt `options` zawiera teraz daty rozpoczęcia, terminu i przypomnienia, a także temat flagi.*

## Practical Applications
- **Integracja z zarządzaniem zadaniami:** Synchronizacja oznaczonych e‑maili z Jira, Trello lub Azure Boards.  
- **Automatyczne przypomnienia:** Generowanie codziennych e‑maili przypominających o zaległych śledzeniach.  
- **Audyt zgodności:** Eksport danych flag do raportowania regulacyjnego.

## Performance Considerations
- **Obliczenia dat:** Obliczaj daty raz na partię, a nie wewnątrz pętli.  
- **Zarządzanie zasobami:** Zamykaj wszystkie strumienie lub uchwyty plików po zapisaniu wiadomości.  
- **Użycie pamięci:** Przetwarzaj duże skrzynki pocztowe w partiach, aby uniknąć obciążenia sterty.

## Common Issues and Solutions
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Flaga nie pojawia się w Outlook | Wiadomość zapisana bez właściwych `MessageFlags` | Upewnij się, że `setMessageFlags` jest ustawione na `MSGFLAG_UNSENT` przed zastosowaniem flag dla odbiorców. |
| Zapis zgłasza `AccessDeniedException` | Nieprawidłowa ścieżka pliku lub brak uprawnień do zapisu | Sprawdź, czy katalog wyjściowy istnieje i aplikacja ma uprawnienia do zapisu w tej lokalizacji. |
| Daty są przesunięte o jeden dzień | Niezgodność strefy czasowej | Używaj `TimeZone.getTimeZone("GMT")` lub swojej lokalnej strefy konsekwentnie. |

## Frequently Asked Questions
**Q: Czym jest Aspose.Email dla Javy?**  
A: To czysto‑Java API, które pozwala tworzyć, odczytywać i manipulować plikami e‑mail (MSG, EML itp.) bez konieczności instalacji Outlook.

**Q: Jak uzyskać bezpłatną wersję próbną licencji?**  
A: Odwiedź [stronę Aspose](https://releases.aspose.com/email/java/), aby pobrać 30‑dniową wersję próbną.

**Q: Czy mogę ustawić wiele flag śledzenia w jednej wiadomości?**  
A: Outlook obsługuje tylko jedną flagę na wiadomość, ale możesz przechowywać dodatkowe dane zadania w niestandardowych właściwościach MAPI.

**Q: Moja wiadomość nie jest zapisywana po ustawieniu flagi. Co powinienem sprawdzić?**  
A: Upewnij się, że ścieżka `outputDir` jest prawidłowa i że aplikacja ma uprawnienia do zapisu w tej lokalizacji.

**Q: Jak mogę usunąć flagi z wielu wiadomości jednocześnie?**  
A: Przejdź pętlą po kolekcji wiadomości i wywołaj `FollowUpManager.clearFlag` dla każdego `MapiMessage`.

## Resources
- [Dokumentacja](https://reference.aspose.com/email/java/)
- [Pobierz Aspose.Email dla Javy](https://releases.aspose.com/email/java/)
- [Bezpłatna wersja próbna Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

**Ostatnia aktualizacja:** 2025-12-19  
**Testowano z:** Aspose.Email dla Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}