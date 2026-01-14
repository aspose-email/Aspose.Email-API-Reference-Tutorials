---
date: '2025-12-19'
description: Узнайте, как установить флаги последующего действия в Outlook с помощью
  Aspose.Email для Java, включая эффективную установку и удаление флага последующего
  действия в Outlook.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Как установить флаги последующего действия в Outlook с помощью Aspose.Email
  для Java
url: /ru/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как установить флаги последующего действия в Outlook с помощью Aspose.Email для Java

## Введение
Если вы когда-нибудь вступите в борьбу с этой темой, чтобы не потерять важные письма, вы знаете, что общепризнанные ценные действия могут стать флагманскими действиями в Outlook. В этом руководстве мы покажем, **как программно установить флаги последовательного действия** с помощью Aspose.Email для Java, а также переключатель, как **установить флаг последовательного действия Outlook** для получателей и как **удалить флаг последовательного действия Outlook**, когда задача будет завершена. В конце вы сможете автоматизировать задачи отслеживания, напоминания и аудит-журналы прямо из вашего Java-кода.

**Что вы узнаете**
- Создание и применение флага в соответствии с действиями по сообщению Outlook.
- Установка флагов последующих действий для конкретных получателей.
- Пометка флага как завершенного и после его удаления.
- Чтение параметров флага для Великобритании или соответствие требованиям.

Подготовим окружение перед тем, как перейти к коду.

## Быстрые ответы
- **Что означает «как настроить отслеживание»?** Добавление флага с датами начала, напоминания и срока выполнения элемента Outlook.
- **Какая библиотека требуется?** Aspose.Email для Java (v25.4 или новее).
- **Нужна ли лицензия?** Да, для полной функциональности требуется пробная или приобретенная лицензия.
- **Можно ли устанавливать флаги только для получателей?** Конечно – викор `FollowUpManager.setFlagForRecipients`.
- **Можно ли позже убрать флаг?** Да, вызовите `FollowUpManager.clearFlag`.

## Что такое флаг отслеживания?
Флаг следующего действия — это функция Outlook, которая помечает письмо как задачу, при необходимости добавления дат, начала напоминания и срока выполнения. Он помогает вам и вашей группе следить за ожидаемыми действиями.

## Зачем использовать Aspose.Email для Java?
Aspose.Email предоставляет чистый Java‑API, который работает без установленного Outlook, позволяет манипулировать файлами .msg, сохранять флаги и управлять задачами на любой платформе — идеально для серверных сервисов, рабочих рабочих потоков или управления с инструментами управления проектами.

## Предварительные условия
- **Aspose.Email для Java** версия 25.4или новее.
- **JDK16+** установлен.
- IDE, совместимая с Maven (IntelliJ IDEA, Eclipse и др.).
- База знаний Java и знакомство с концепциями электронной почты.

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
Aspose.Email требует лицензию для использования в продакшене:

- **Бесплатная пробная** — 30‑дневная оплата.
- **Временная лицензия** — расширенное расширение.
- **Полная лицензия** — бессрочная подписка.

Инициализируйте лицензию перед любой операцией с письмами:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Руководство по внедрению

### Как установить флаги отслеживания (функция 1)
#### Обзор
В этом разделе мы пройдём по созданию сообщений Outlook, измерению даты начала/напоминания/срока и применению флага последующих действий.

#### Шаг 1: Создайте и инициализируйте сообщение
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Сначала мы создаём `MailMessage`, задаём отправителя/получателя, а затем преобразуем его в `MapiMessage` для работы с флагом.*

#### Шаг 2: Определите даты последующих действий
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Здесь мы задаём даты начала, напоминания и срока с помощью класса `Calendar`.*

#### Шаг 3: Примените параметры последующих действий
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Объект `FollowUpOptions` содержит все детали флага, которые мы применяем через `FollowUpManager.setOptions`.*

#### Шаг 4: Сохраните сообщение
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Сообщение сохраняется в файл `.msg` с прикреплённым флагом.*

### Как установить флаг «Отслеживание» в Outlook для получателей (Функция 2)
#### Обзор
Иногда требуется пометить сообщение только для получателей. В этом примере сообщение сначала помечается как черновик, после чего добавляется флаг.

#### Шаг 1: Пометить как черновик
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Пометка сообщения как несент‑драфта гарантирует, что Outlook воспримет его как черновик.*

#### Шаг 2: Установить флажок получателя
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Флаг теперь виден только получателям.*

### Как пометить отслеживание в Outlook как завершенное (Функция 3)
#### Обзор
Когда задача выполнена, её можно программно пометить как завершённую.

#### Шаг 1: Загрузите сообщение
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Шаг 2: Отметьте как выполненное и сохраните
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Статус флага меняется на «Completed», и обновлённый файл сохраняется.*

### Как удалить флажок отслеживания Outlook (функция 4)
#### Обзор
Если флаг больше не нужен, его можно полностью убрать.

#### Шаг 1. Загрузите и очистите флаг
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Сообщение сохраняется без какого‑либо флага последующего действия.*

### Как прочитать параметры флага отслеживания (функция 5)
#### Обзор
Для аудита или отчётности можно просмотреть текущие настройки флага.

#### Шаг 1: Получение параметров
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Объект `options` теперь содержит даты начала, срока и напоминания, а также тему флага.*

## Практическое применение
- **Интеграция управления задачами:** Синхронизация помеченных писем с Jira, Trello или Azure Boards.
- **Автоматические напоминания:** Генерация ежедневных писем‑напоминаний об ожидаемых действиях.
- **Аудит соответствия:** Экспорт данных флагов для регуляторных отчётов.

## Вопросы производительности
- **Вычисление даты:** Рассчитывайте даты один раз за пакет, а не внутри циклов.
- **Управление проблемами:** Закрывайте любые потоки или файловые дескрипторы после сохранения сообщений.
- **Потребление памяти:** Обрабатывайте большие почтовые ящики порциями, чтобы избежать нагрузки.

## Распространенные проблемы и решения
| Выпуск | Причина | Исправить |
|-------|-------|-----|
| Флаг не отображается в Outlook | Сообщение сохранено без неправильных `MessageFlags` | Убедитесь, что `setMessageFlags` установлен в `MSGFLAG_UNSENT` перед применением флага получателям. |
| При сохранении возникновения `AccessDeniedException` | Неправильный путь к файлу или отсутствие прав записи | Проверьте, что результаты каталога существуют и приложение имеет право на запись. |
| Даты смещения на один день | Несоответствие часовых поясов | Используйте TimeZone.getTimeZone("GMT") или последовательно применяйте ваш локальный часовой пояс. |

## Часто задаваемые вопросы
**В: Что такое Aspose.Email для Java?**
Ответ: Это чисто Java‑API, созданный специально для чтения и управления файлами электронной почты США (MSG, EML и т. д.) без необходимости установки Outlook.

**В: Как получить бесплатную пробную лицензию?**
О: Перейдите на [веб-сайт Aspose](https://releases.aspose.com/email/java/) и скачайте 30‑дневную пробную версию.

**Вопрос: Можно ли установить несколько флагов последующих действий в одном месте?**
Ответ: Outlook поддерживает только один флажок в сообщении, но вы можете хранить дополнительные данные в свойствах MAPI.

**В: Мое сообщение не сохраняется после установки флага. Что проверить?**
A: Убедитесь, что путь `outputDir` правильный, и приложение имеет права, записанные в этом каталоге.

**В: Как удалить флаги из большого количества сообщений одновременно?**
Ответ: Перейдите в цикл сбора сообщений и вызовите `FollowUpManager.clearFlag` для каждого `MapiMessage`.

## Ресурсы
- [Документация](https://reference.aspose.com/email/java/)
- [Скачать Aspose.Email для Java](https://releases.aspose.com/email/java/)
- [Бесплатная пробная версия Aspose.Email](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Последнее обновление:** 19.12.2025
**Протестировано с:** Aspose.Email для Java 25.4 (jdk16)
**Автор:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}