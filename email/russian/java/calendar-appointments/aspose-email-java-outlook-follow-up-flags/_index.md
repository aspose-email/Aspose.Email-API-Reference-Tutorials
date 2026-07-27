---
date: '2026-07-27'
description: Узнайте, как установить флаг Outlook в Java с помощью Aspose.Email for
  Java, охватывая создание флага, флаги получателей, завершение, удаление и варианты
  чтения.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Установите флаг Outlook в Java с Aspose.Email for Java. Это руководство
  показывает, как создавать, читать, завершать и удалять флаги отслеживания Outlook
  эффективно.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Установка флага Outlook в Java – Полное руководство по программированию
  Aspose.Email
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
title: Установка флага Outlook в Java – Полное руководство по программированию Aspose.Email
url: /ru/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Установить флаг Outlook Java с помощью Aspose.Email для Java

## Введение
Если вам нужно **set outlook flag java** программно, вы попали в нужное место. Флаг отслеживания Outlook превращает обычное письмо в задачу, а Aspose.Email for Java позволяет управлять этими флагами без установки Outlook. В этом руководстве мы пройдем процесс создания, чтения, завершения и, наконец, удаления флагов, а также применения флагов для конкретных получателей. К концу у вас будет переиспользуемый фрагмент Java, автоматизирующий отслеживание задач непосредственно из ваших серверных сервисов.

## Быстрые ответы
- **Что означает “set outlook flag java”?** Добавление флага с датой начала, напоминанием и датой завершения к элементу Outlook через код Java.  
- **Какая библиотека требуется?** Aspose.Email for Java (v25.4 or newer).  
- **Нужна ли лицензия?** Да — пробная версия подходит для оценки, но для продакшн требуется приобретённая лицензия.  
- **Можно ли установить флаги только для получателей?** Абсолютно — используйте `FollowUpManager.setFlagForRecipients`.  
- **Можно ли позже удалить флаг?** Да — вызовите `FollowUpManager.clearFlag`.

## Что такое флаг отслеживания Outlook?
Флаг отслеживания Outlook — это встроенный маркер задачи, который может прикреплять дату начала, напоминание и дату завершения к любому письму. Он превращает электронное письмо в отслеживаемый элемент действия, помогая вам и вашей команде оставаться в курсе ожидающих задач.

## Зачем использовать Aspose.Email для Java?
Aspose.Email for Java поддерживает **70+ форматов электронной почты** (включая MSG, EML, MHTML и TNEF) и может обрабатывать **более 100 000 сообщений в минуту** на типичном 8‑ядерном сервере, без необходимости установки Outlook на хост‑машине. Это делает его идеальным для автоматизации бекенда, отчётности по соответствию и интеграции с инструментами управления проектами.

## Требования
- **Aspose.Email for Java** version 25.4 or later.  
- **JDK 16+** installed.  
- IDE, совместимая с Maven (IntelliJ IDEA, Eclipse и т.д.).  
- Базовые знания Java и знакомство с концепциями электронной почты.

## Настройка Aspose.Email для Java
### Конфигурация Maven
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Приобретение лицензии
Aspose.Email requires a license for production use:

- **Free trial** – 30‑дневная оценка.  
- **Temporary license** – расширенное тестирование.  
- **Full license** – бессрочная подписка.

Initialize the license before any email operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Установить флаг Outlook Java (Функция 1)
### Прямой ответ
Load a `MailMessage`, convert it to a `MapiMessage`, configure `FollowUpOptions`, and call `FollowUpManager.setOptions`. This sequence creates a fully flagged Outlook item in just a few lines of Java code.

### Шаг 1: Создать и инициализировать сообщение
`MailMessage` is Aspose.Email’s high‑level class that represents an email. After you build the message, you convert it to a `MapiMessage` for flag manipulation.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Сначала мы создаём `MailMessage`, задаём отправителя/получателя, затем преобразуем его в `MapiMessage` для управления флагом.*

### Шаг 2: Определить даты отслеживания (напоминание флага Outlook)
`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s `Calendar` to set precise timestamps.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Здесь мы задаём даты начала, напоминания (**outlook flag reminder**) и завершения с помощью класса `Calendar`.*

### Шаг 3: Применить параметры отслеживания
The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Объект `FollowUpOptions` содержит все детали флага, которые мы применяем с помощью `FollowUpManager.setOptions`.*

### Шаг 4: Сохранить сообщение
Save the flagged message as a `.msg` file so Outlook can display the flag.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Сообщение сохраняется как файл `.msg` с прикреплённым флагом.*

## Как установить флаг для получателей (Функция 2)?
Use `FollowUpManager.setFlagForRecipients` after marking the message as a draft. This method adds the follow‑up flag only to the recipient’s copy, leaving the sender’s view unchanged. It requires setting `MessageFlags.MSGFLAG_UNSENT` before applying the flag. You can also customize the start, reminder, and due dates using a `FollowUpOptions` object before calling the method.

### Прямой ответ
Mark the message as a draft using `MessageFlags.MSGFLAG_UNSENT`, then call `FollowUpManager.setFlagForRecipients`. Outlook will show the flag only to the recipients, not to the sender.

### Обзор
Sometimes you need the flag to appear **only for recipients**. This example marks the message as a draft first, then adds the flag.

#### Шаг 1: Пометить как черновик
`MessageFlags` is a MAPI enumeration that controls the state of the message. Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Пометка сообщения как несохранённого гарантирует, что Outlook рассматривает его как черновик.*

#### Шаг 2: Установить флаг получателя
`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to the recipient’s copy.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Флаг теперь виден только получателям — классический сценарий **flag for recipients**.*

## Как отметить флаг отслеживания Outlook как выполненный (Функция 3)?
Load the .msg file into a `MapiMessage`, then call `FollowUpManager.completeFlag`. This updates the flag status to Completed and adds a check‑mark in Outlook. After completing, save the message to persist the change. You may also set the completion time by adjusting the `FlagCompleteTime` property if required for audit purposes.

### Прямой ответ
Load the existing `.msg` file into a `MapiMessage`, call `FollowUpManager.completeFlag`, and save the file. The flag status changes to “Completed” and appears with a check‑mark in Outlook.

### Шаг 1: Загрузить сообщение
`MapiMessage` can read a saved `.msg` file, giving you full access to its MAPI properties.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Шаг 2: Отметить как выполненный и сохранить
`FollowUpManager.completeFlag` updates the flag status, after which you persist the changes.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Статус флага меняется на “Completed”, и обновлённый файл сохраняется.*

## Как удалить флаг отслеживания Outlook (Функция 4)?
Open the .msg file with `MapiMessage`, invoke `FollowUpManager.clearFlag`, and then save the message. This removes all flag‑related MAPI properties, so Outlook will no longer display any follow‑up indicator. Use this when a task is cancelled or no longer relevant. Ensure you also clear any custom reminder properties to avoid residual notifications.

### Прямой ответ
Open the `.msg` file with `MapiMessage`, invoke `FollowUpManager.clearFlag`, and save the file. The message will no longer display any follow‑up indicator in Outlook.

### Шаг 1: Загрузить и очистить флаг
`FollowUpManager.clearFlag` removes all flag‑related properties from the message.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Сообщение сохраняется без какого‑либо флага отслеживания.*

## Как прочитать параметры флага (Функция 5)?
Call `FollowUpManager.getOptions` on a loaded `MapiMessage` to obtain a `FollowUpOptions` object. This object provides the start, due, reminder dates, and the flag subject, allowing you to display or log the flag details. It is useful for reporting and compliance audits.

### Прямой ответ
Use `FollowUpManager.getOptions` on a loaded `MapiMessage` to retrieve a `FollowUpOptions` object containing start, due, reminder dates, and the flag subject. This is useful for reporting or compliance audits.

### Шаг 1: Получить параметры
The returned `options` object gives you full visibility into the flag’s configuration.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Объект `options` теперь содержит даты начала, завершения и напоминания, а также тему флага — полезно, когда нужно **read flag options** для отчётности.*

## Практические применения
- **Task‑Management Integration:** Синхронизация помеченных писем с Jira, Trello или Azure Boards.  
- **Automated Reminders:** Генерация ежедневных писем‑напоминаний о ожидающих отслеживаниях.  
- **Compliance Audits:** Экспорт данных флагов для регуляторных отчётов, используя возможность программного чтения параметров флага.

## Соображения по производительности
- **Date Calculations:** Вычисляйте даты один раз за пакет, а не внутри циклов.  
- **Resource Management:** Закрывайте любые потоки или файловые дескрипторы после сохранения сообщений.  
- **Memory Usage:** Обрабатывайте большие почтовые ящики порциями, чтобы избежать нагрузки на кучу; Aspose.Email может работать с несколькими сотнями страниц без загрузки всего файла в память.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|----------|
| Флаг не отображается в Outlook | Сообщение сохранено без правильных `MessageFlags` | Убедитесь, что `setMessageFlags` установлен в `MSGFLAG_UNSENT` перед применением флагов получателям. |
| Сохранение вызывает `AccessDeniedException` | Неправильный путь к файлу или отсутствие прав записи | Проверьте, что каталог вывода существует и приложение имеет права записи. |
| Даты смещены на один день | Несоответствие часовых поясов | Используйте `TimeZone.getTimeZone("GMT")` или вашу локальную зону последовательно. |

## Часто задаваемые вопросы
**Q: Что такое Aspose.Email for Java?**  
**A:** Это чистый Java API, позволяющий создавать, читать и изменять файлы электронной почты (MSG, EML и т.д.) без необходимости установки Outlook.

**Q: Как получить бесплатную пробную лицензию?**  
**A:** Посетите [Aspose website](https://releases.aspose.com/email/java/) для загрузки 30‑дневной пробной версии.

**Q: Можно ли установить несколько флагов отслеживания в одном сообщении?**  
**A:** Outlook поддерживает только один флаг на сообщение, но вы можете хранить дополнительные данные задачи в пользовательских свойствах MAPI.

**Q: Моё сообщение не сохраняется после установки флага. Что проверить?**  
**A:** Убедитесь, что путь `outputDir` действителен и приложение имеет права записи в указанную директорию.

**Q: Как удалить флаги из многих сообщений одновременно?**  
**A:** Пройдите цикл по коллекции сообщений и вызовите `FollowUpManager.clearFlag` для каждого `MapiMessage`.

## Ресурсы
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Последнее обновление:** 2026-07-27  
**Тестировано с:** Aspose.Email for Java 25.4 (JDK 16)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Управление категориями Outlook с помощью Aspose.Email for Java — Полное руководство](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Создание заметок Outlook Java с Aspose.Email – Полное руководство](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Создание задач в Microsoft Exchange с использованием Aspose.Email for Java: Полное руководство](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}