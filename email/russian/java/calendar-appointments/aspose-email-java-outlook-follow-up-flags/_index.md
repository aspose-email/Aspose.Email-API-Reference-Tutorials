---
date: '2026-02-22'
description: Узнайте, как установить флаг напоминания в Outlook с помощью Aspose.Email
  для Java, включая установку, чтение и удаление флагов для получателей.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Как установить флаг «Follow Up» в Outlook с помощью Aspose.Email для Java
url: /ru/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 keep code block placeholders unchanged.

Also preserve markdown tables.

Now produce final content with shortcodes at top and bottom.

Let's construct.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как установить флаг отслеживания Outlook с помощью Aspose.Email для Java

## Введение
Если вы когда‑либо сталкивались с проблемой отслеживания важных писем, вы знаете, насколько ценным может быть **outlook follow up flag** в Outlook. В этом руководстве мы покажем, **как программно установить флаг отслеживания Outlook** с помощью Aspose.Email для Java, а также расскажем, как **установить флаг отслеживания Outlook для получателей**, и как **удалить флаг отслеживания Outlook**, когда задача завершена. К концу вы сможете автоматизировать отслеживание задач, напоминания и журналы аудита непосредственно из вашего Java‑кода.

**Что вы узнаете**
- Создание и применение флага отслеживания к сообщению Outlook.  
- Установка флагов отслеживания для конкретных получателей.  
- Пометка флага как выполненного и последующее его удаление.  
- Чтение параметров флага для отчётности или соответствия требованиям.  

Подготовим окружение перед тем, как перейти к коду.

## Быстрые ответы
- **Что означает «how to set follow‑up»?** Добавление флага с датой начала, напоминанием и сроком выполнения к элементу Outlook.  
- **Какая библиотека требуется?** Aspose.Email для Java (v25.4 или новее).  
- **Нужна ли лицензия?** Да, для полной функциональности требуется trial‑лицензия или приобретённая лицензия.  
- **Можно ли установить флаги только для получателей?** Абсолютно — используйте `FollowUpManager.setFlagForRecipients`.  
- **Можно ли позже удалить флаг?** Да, вызовите `FollowUpManager.clearFlag`.

## Что такое флаг отслеживания Outlook?
Флаг отслеживания Outlook — это встроенный маркер задачи, который может содержать дату начала, напоминание и срок выполнения для любого почтового элемента. Он превращает обычное письмо в отслеживаемый пункт действия, помогая вам и вашей команде контролировать текущие задачи.

## Почему использовать Aspose.Email для Java?
Aspose.Email предоставляет чистый Java‑API, который работает без установленного Outlook, позволяя манипулировать .msg‑файлами, устанавливать флаги и управлять задачами на любой платформе — идеально для **automate outlook tasks**, серверных сервисов или интеграции с инструментами управления проектами.

## Требования
- **Aspose.Email для Java** версии 25.4 или новее (также известен как **aspose email java**).  
- **JDK 16+** установлен.  
- IDE, совместимая с Maven (IntelliJ IDEA, Eclipse и т.д.).  
- Базовые знания Java и знакомство с концепциями электронной почты.

## Настройка Aspose.Email для Java
### Конфигурация Maven
Добавьте следующую зависимость в ваш `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Получение лицензии
Aspose.Email требует лицензии для использования в продакшене:

- **Бесплатная пробная версия** — 30‑дневная оценка.  
- **Временная лицензия** — расширенное тестирование.  
- **Полная лицензия** — бессрочная подписка.

Инициализируйте лицензию перед любой операцией с электронной почтой:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Установить флаг отслеживания Outlook (Функция 1)
### Шаг 1: Создать и инициализировать сообщение
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Сначала создаём `MailMessage`, задаём отправителя/получателя, затем преобразуем его в `MapiMessage` для работы с флагом.*

### Шаг 2: Определить даты отслеживания (напоминание флага Outlook)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Здесь задаём дату начала, напоминание (**outlook flag reminder**) и срок выполнения с помощью класса `Calendar`.*

### Шаг 3: Применить параметры отслеживания
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Объект `FollowUpOptions` содержит все детали флага, которые мы применяем через `FollowUpManager.setOptions`.*

### Шаг 4: Сохранить сообщение
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Сообщение сохраняется как файл `.msg` с прикреплённым флагом.*

## Как установить флаг для получателей (Функция 2)
### Обзор
Иногда требуется, чтобы флаг отображался **только у получателей**. В этом примере сообщение сначала помечается как черновик, затем добавляется флаг.

#### Шаг 1: Пометить как черновик
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Пометка сообщения как несохранённого гарантирует, что Outlook рассматривает его как черновик.*

#### Шаг 2: Установить флаг получателя
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Флаг теперь виден только получателям — классический сценарий **flag for recipients**.*

## Как пометить флаг отслеживания Outlook как выполненный (Функция 3)
### Шаг 1: Загрузить сообщение
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Шаг 2: Пометить как выполненный и сохранить
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Статус флага меняется на «Completed», и обновлённый файл сохраняется.*

## Как удалить флаг отслеживания Outlook (Функция 4)
### Шаг 1: Загрузить и очистить флаг
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Сообщение сохраняется без какого‑либо флага отслеживания.*

## Как прочитать параметры флага (Функция 5)
### Шаг 1: Получить параметры
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Объект `options` теперь содержит даты начала, срока и напоминания, а также тему флага — полезно, когда нужно **read flag options** для отчётности.*

## Практические применения
- **Интеграция управления задачами:** Синхронизация помеченных писем с Jira, Trello или Azure Boards.  
- **Автоматические напоминания:** Генерация ежедневных писем‑напоминаний о предстоящих отслеживаниях.  
- **Аудит соответствия:** Экспорт данных флагов для регуляторных отчётов.

## Соображения по производительности
- **Вычисление дат:** Рассчитывайте даты один раз за пакет, а не внутри циклов.  
- **Управление ресурсами:** Закрывайте любые потоки или файловые дескрипторы после сохранения сообщений.  
- **Использование памяти:** Обрабатывайте большие почтовые ящики порциями, чтобы избежать нагрузки на кучу.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| Флаг не отображается в Outlook | Сообщение сохранено без правильных `MessageFlags` | Убедитесь, что `setMessageFlags` установлен в `MSGFLAG_UNSENT` перед применением флагов получателей. |
| При сохранении возникает `AccessDeniedException` | Неправильный путь к файлу или отсутствие прав записи | Проверьте, что выходной каталог существует и приложение имеет права на запись. |
| Даты смещены на один день | Несоответствие часовых поясов | Используйте `TimeZone.getTimeZone("GMT")` или consistently ваш локальный часовой пояс. |

## Часто задаваемые вопросы
**В: Что такое Aspose.Email для Java?**  
О: Это чистый Java‑API, позволяющий создавать, читать и изменять файлы электронной почты (MSG, EML и др.) без необходимости установки Outlook.

**В: Как получить бесплатную пробную лицензию?**  
О: Перейдите на [сайт Aspose](https://releases.aspose.com/email/java/) и скачайте 30‑дневную пробную версию.

**В: Можно ли установить несколько флагов отслеживания на одно сообщение?**  
О: Outlook поддерживает только один флаг на сообщение, но вы можете хранить дополнительные данные задачи в пользовательских свойствах MAPI.

**В: Моё сообщение не сохраняется после установки флага. Что проверить?**  
О: Убедитесь, что путь `outputDir` корректен и приложение имеет права записи в эту директорию.

**В: Как удалить флаги из множества сообщений одновременно?**  
О: Пройдитесь по коллекции сообщений в цикле и вызовите `FollowUpManager.clearFlag` для каждого `MapiMessage`.

## Ресурсы
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Последнее обновление:** 2026-02-22  
**Тестировано с:** Aspose.Email for Java 25.4 (jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}