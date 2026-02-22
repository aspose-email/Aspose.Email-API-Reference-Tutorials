---
date: '2026-02-22'
description: Dowiedz się, jak ustawić flagę śledzenia w Outlooku przy użyciu Aspose.Email
  dla Javy, w tym jak ustawiać, odczytywać i usuwać flagi dla odbiorców.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Jak ustawić flagę śledzenia w Outlooku przy użyciu Aspose.Email dla Javy
url: /pl/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić flagę śledzenia w Outlook przy użyciu Aspose.Email dla Javy

## Wprowadzenie
Jeśli kiedykolwiek miałeś problem z śledzeniem ważnych wiadomości e‑mail, wiesz, jak cenna może być **flaga śledzenia w Outlook**. W tym przewodniku pokażemy, **jak programowo ustawić flagę śledzenia w Outlook** przy użyciu Aspose.Email dla Javy, a także omówimy, jak **ustawić flagę śledzenia w Outlook dla odbiorców**, oraz jak **usunąć flagę śledzenia w Outlook**, gdy zadanie zostanie zakończone. Po zakończeniu będziesz mógł automatyzować śledzenie zadań, przypomnienia i ścieżki audytu bezpośrednio z kodu Java.

**Czego się nauczysz**
- Utwórz i zastosuj flagę śledzenia w wiadomości Outlook.  
- Ustaw flagi śledzenia dla konkretnych odbiorców.  
- Oznacz flagę jako zakończoną i później ją usuń.  
- Odczytaj opcje flagi w celu raportowania lub zgodności.  

Przygotujmy środowisko przed zagłębieniem się w kod.

## Szybkie odpowiedzi
- **Co oznacza „jak ustawić śledzenie”?** Dodanie flagi z datą rozpoczęcia, przypomnieniem i terminem do elementu Outlook.  
- **Jakiej biblioteki wymaga?** Aspose.Email for Java (v25.4 lub nowsza).  
- **Czy potrzebna jest licencja?** Tak, wymagana jest licencja próbna lub zakupiona, aby uzyskać pełną funkcjonalność.  
- **Czy mogę ustawić flagi tylko dla odbiorców?** Oczywiście – użyj `FollowUpManager.setFlagForRecipients`.  
- **Czy można później usunąć flagę?** Tak, wywołaj `FollowUpManager.clearFlag`.

## Co to jest flaga śledzenia w Outlook?
Flaga śledzenia w Outlook to wbudowany znacznik zadania, który może zawierać datę rozpoczęcia, przypomnienie i termin w dowolnym elemencie pocztowym. Przekształca zwykły e‑mail w śledzoną pozycję akcji, pomagając Tobie i Twojemu zespołowi nadążać za zaległymi zadaniami.

## Dlaczego warto używać Aspose.Email dla Javy?
Aspose.Email zapewnia czyste API w Javie, które działa bez konieczności instalacji Outlook, umożliwiając manipulację plikami .msg, ustawianie flag i zarządzanie zadaniami na dowolnej platformie — idealne do **automatyzacji zadań w Outlook**, usług backendowych lub integracji z narzędziami do zarządzania projektami.

## Prerequisites
- **Aspose.Email for Java** wersja 25.4 lub nowsza (znana także jako **aspose email java**).  
- **JDK 16+** zainstalowane.  
- IDE kompatybilne z Maven (IntelliJ IDEA, Eclipse itp.).  
- Podstawowa znajomość Javy oraz koncepcji e‑mail.

## Setting Up Aspose.Email for Java
### Maven Configuration
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email requires a license for production use:

- **Free trial** – 30‑day evaluation.  
- **Temporary license** – extended testing.  
- **Full license** – perpetual subscription.

Initialize the license before any email operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Najpierw budujemy `MailMessage`, ustawiamy nadawcę/odbiorcę, a następnie konwertujemy go na `MapiMessage` w celu manipulacji flagą.*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Tutaj ustawiamy daty rozpoczęcia, przypomnienia (**przypomnienie flagi w Outlook**) i terminu przy użyciu klasy `Calendar`.*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Obiekt `FollowUpOptions` przechowuje wszystkie szczegóły flagi, które stosujemy za pomocą `FollowUpManager.setOptions`.*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Wiadomość jest zapisywana jako plik `.msg` z dołączoną flagą.*

## How to Set Flag for Recipients (Feature 2)
### Overview
Czasami potrzebujesz, aby flaga pojawiła się **tylko dla odbiorców**. Ten przykład najpierw oznacza wiadomość jako szkic, a potem dodaje flagę.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Oznaczenie wiadomości jako niewysłanej zapewnia, że Outlook traktuje ją jako szkic.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Flaga jest teraz widoczna wyłącznie dla odbiorców – klasyczny scenariusz **flaga dla odbiorców**.*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Status flagi zmienia się na „Completed”, a zaktualizowany plik jest zapisywany.*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Wiadomość jest zapisywana bez żadnej flagi śledzenia.*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Obiekt `options` zawiera teraz daty rozpoczęcia, terminu i przypomnienia oraz temat flagi – przydatne, gdy musisz **odczytać opcje flagi** w raportach.*

## Practical Applications
- **Task‑Management Integration:** Synchronizuj flagowane e‑maile z Jira, Trello lub Azure Boards.  
- **Automated Reminders:** Generuj codzienne e‑maile przypominające o zaległych śledzeniach.  
- **Compliance Audits:** Eksportuj dane flag do raportów regulacyjnych.

## Performance Considerations
- **Date Calculations:** Obliczaj daty raz na partię, a nie wewnątrz pętli.  
- **Resource Management:** Zamykaj wszystkie strumienie lub uchwyty plików po zapisaniu wiadomości.  
- **Memory Usage:** Przetwarzaj duże skrzynki pocztowe w partiach, aby uniknąć nadmiernego zużycia pamięci.

## Common Issues and Solutions
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Ensure `setMessageFlags` is set to `MSGFLAG_UNSENT` before applying recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Verify the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Use `TimeZone.getTimeZone("GMT")` or your local zone consistently. |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: It’s a pure‑Java API that lets you create, read, and manipulate email files (MSG, EML, etc.) without needing Outlook installed.

**Q: How do I obtain a free trial license?**  
A: Visit the [Aspose website](https://releases.aspose.com/email/java/) to download a 30‑day trial.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook supports only one flag per message, but you can store additional task data in custom MAPI properties.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: Confirm the `outputDir` path is valid and that the application has permission to write to that location.

**Q: How can I remove flags from many messages at once?**  
A: Loop through your message collection and call `FollowUpManager.clearFlag` on each `MapiMessage`.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}