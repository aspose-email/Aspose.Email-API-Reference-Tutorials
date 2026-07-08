---
date: '2026-07-08'
description: Узнайте, как создать EWS client Java с использованием Aspose.Email для
  эффективного управления электронной почтой, включая message deletion, appending
  и user impersonation на Exchange Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Узнайте, как создать EWS client Java с использованием Aspose.Email
  для эффективного управления электронной почтой, включая message deletion, appending
  и user impersonation на Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Создать EWS Client Java с Aspose.Email – Управление пользователями
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Создать EWS Client Java с Aspose.Email – Управление пользователями
url: /ru/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение управления электронной почтой: Aspose.Email Java для клиента EWS, пользователь и имперсонация

## Введение

В этом руководстве вы **создадите Java‑приложения клиента EWS** с помощью Aspose.Email, что позволит управлять несколькими почтовыми ящиками Exchange Server из единой Java‑базы кода. Мы пройдем процесс создания экземпляров `EWSClient`, удаления сообщений, добавления новых писем и имперсонации других пользователей — задачи, экономящие часы ручной работы в корпоративных средах.

### Что вы узнаете
- Как **создать объекты Java‑клиента EWS** с использованием разных учетных данных.  
- Эффективные методы удаления всех сообщений из выбранной папки.  
- Шаги для добавления готового письма в почтовый ящик пользователя.  
- Как имперсонировать другой почтовый ящик для сценариев совместных ящиков.

Теперь, когда вы знаете, что будем рассматривать, подготовим среду разработки.

## Быстрые ответы
- **Какой первый шаг?** Добавьте зависимость Aspose.Email Maven в ваш `pom.xml`.  
- **Какой класс представляет соединение с Exchange?** `EWSClient` (или его интерфейс `IEWSClient`).  
- **Можно ли удалить все сообщения одним вызовом?** Да — переберите с помощью `listMessages` и вызовите `deleteMessage` для каждого URI.  
- **Как отправить письмо без SMTP?** Используйте `appendMessage`, чтобы разместить `MailMessage` непосредственно в папке.  
- **Безопасна ли имперсонация?** Она работает под оригинальными учетными данными и учитывает политики делегирования Exchange.

## Что такое создание клиента EWS Java?
`create ews client java` относится к созданию объекта `EWSClient` в Java‑приложении, чтобы программно вызывать операции Exchange Web Services (EWS). Такой подход устраняет необходимость ручного взаимодействия с Outlook и позволяет автоматизировать обработку почтовых ящиков. Создавая отдельный клиент для каждого пользователя, вы можете изолировать учетные данные, применять политики для каждого ящика и масштабировать решение на десятки учетных записей без дублирования кода.

## Почему использовать Aspose.Email для интеграции с EWS?
Aspose.Email поддерживает **более 50** операций EWS, работает с **многосотенными** почтовыми ящиками без загрузки всего хранилища в память и обрабатывает **до 10 000** сообщений в минуту на типичном серверном оборудовании. Эти измеримые возможности делают её лучшим выбором для масштабной автоматизации электронной почты. Библиотека также абстрагирует низкоуровневые детали SOAP, предоставляя чистый, типобезопасный API, который сокращает время разработки и минимизирует количество ошибок.

## Требования
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** для управления зависимостями.  
- Библиотека **Aspose.Email for Java** (добавляется через Maven).  
- Базовые знания концепций Exchange Web Services (EWS).

## Настройка Aspose.Email для Java
Добавьте библиотеку в ваш Maven `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Получение лицензии
Aspose.Email предлагает бесплатную пробную версию с возможностью запросить временную лицензию для полного доступа. Для длительного использования рассмотрите покупку лицензии на [странице покупки Aspose](https://purchase.aspose.com/buy).

## Как создать клиент EWS Java?
Загрузите сервис Exchange с соответствующими учетными данными и получите экземпляр `IEWSClient` — этот двухшаговый шаблон является основой всех последующих операций. Вы можете переиспользовать один клиент для нескольких действий или создавать отдельные экземпляры для каждого пользователя для изоляции. **`IEWSClient` — это интерфейс, который предоставляет все операции EWS, тогда как `EWSClient` предоставляет статический фабричный метод для получения реализации.**

Создание клиента обычно включает указание URL сервиса, имени пользователя, пароля и, при необходимости, информации о домене. После создания клиент автоматически обрабатывает аутентификацию, подпись запросов и разбор ответов.

### Создание экземпляров EWSClient
**Определение:** `EWSClient` (доступный через интерфейс `IEWSClient`) — основной объект Aspose.Email для взаимодействия с сервером Exchange через EWS.

#### Импорт необходимых классов
Начните с импорта необходимых классов Aspose.Email:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### Инициализация экземпляров EWSClient
Создайте объекты `IEWSClient` для каждого почтового ящика, которым вы хотите управлять:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Объяснение:* Вспомогательная функция `getEWSClient` подключается к Exchange, используя предоставленные учетные данные, и возвращает готовый к использованию клиент, учитывающий текущие права пользователя.

## Как удалить сообщения из папки?
Получите все элементы в целевой папке и удалите каждый из них навсегда за один проход. Этот метод избавляет от необходимости открывать каждое сообщение отдельно. **`listMessages` возвращает коллекцию объектов `MessageInfo`, содержащих уникальный URI каждого сообщения, который затем передаётся в `deleteMessage` для удаления элемента с сервера.**

Обработка пакетами уменьшает количество сетевых запросов и предотвращает тайм‑ауты при работе с большими папками. Всегда проверяйте, что выбранная папка правильна, так как удаление необратимо без резервной копии.

### Список и удаление сообщений
Переберите каждый URI сообщения и вызовите операцию удаления:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Объяснение:* `listMessages` возвращает коллекцию объектов `MessageInfo`; их значения `getUniqueUri()` передаются в `deleteMessage`, который навсегда удаляет элементы с сервера.

## Как добавить сообщение в папку?
Создайте объект `MailMessage` локально и сохраните его непосредственно в папке почтового ящика — без необходимости в SMTP‑сервере. **`MailMessage` представляет электронное письмо с заголовками, телом и вложениями; его можно полностью сформировать в памяти перед сохранением в Exchange.**

Добавление обходит процесс отправки, что делает его идеальным для черновиков, шаблонов или программного создания сообщений, когда необходимо, чтобы письмо мгновенно появилось в почтовом ящике пользователя.

### Создание и отправка сообщений
Сформируйте письмо и добавьте его в папку Drafts:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Объяснение:* `appendMessage` принимает `MailMessage` и `FolderInfo` (например, Drafts) и записывает элемент в почтовый ящик, делая его мгновенно доступным пользователю.

## Как имперсонировать пользователя в EWS?
Переключите контекст безопасности клиента на другой почтовый ящик, выполните действия, затем вернитесь к исходной учётной записи. Это необходимо для администрирования совместных ящиков. **`impersonateUser` задаёт `ImpersonatedUserId` в базовом запросе EWS, позволяя серверу рассматривать вызов как исходящий из целевого почтового ящика.**

После завершения необходимых операций вызовите `resetImpersonation`, чтобы восстановить исходные учетные данные, гарантируя, что последующие вызовы будут выполнены в правильном контексте безопасности.

### Выполнение имперсонации пользователя
Временно измените контекст клиента, чтобы действовать от имени другого пользователя:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Объяснение:* `impersonateUser` задаёт `ImpersonatedUserId` в базовом запросе EWS, позволяя читать или писать как целевой пользователь. Вызов `resetImpersonation` восстанавливает исходные учетные данные.

## Практические применения
Using Aspose.Email Java enables robust email automation solutions:
1. **Автоматическая очистка почты:** Запланировать ночную задачу, которая очищает устаревшие папки Draft во множестве почтовых ящиков.  
2. **Пакетная рассылка писем:** Добавить шаблонное объявление во входящие каждого сотрудника одним циклом.  
3. **Управление совместными ящиками:** Имперсонировать почтовый ящик отдела для архивирования старых сообщений без предоставления каждому пользователю полного доступа.

## Соображения по производительности
To keep your application responsive when handling large mailboxes:
- **Пакетные вызовы API**, где это возможно (например, удалять по 500 сообщений за запрос).  
- **Потоковая обработка сообщений** вместо загрузки полных тел в память.  
- **Своевременно освобождать объекты клиента**, чтобы освободить сетевые сокеты и HTTP‑соединения.

## Распространённые проблемы и решения
- **Ошибки подключения:** Проверьте URL конечной точки EWS, убедитесь, что включён TLS 1.2, и подтвердите, что правила брандмауэра позволяют исходящие HTTPS‑соединения.  
- **Отказ в доступе при имперсонации:** У учетной записи службы должна быть назначена роль “ApplicationImpersonation” в Exchange.  
- **Тайм‑ауты больших папок:** Увеличьте тайм‑аут `HttpWebRequest` или обрабатывайте папку небольшими частями.

## Часто задаваемые вопросы

**Вопрос:** Как решить проблемы подключения к EWS?  
**Ответ:** Проверьте URL конечной точки, учетные данные и сетевые брандмауэры; включите подробное логирование в Aspose.Email для захвата данных HTTP‑запросов/ответов.

**Вопрос:** Может ли Aspose.Email эффективно обрабатывать большие объёмы писем?  
**Ответ:** Да — его пакетные API позволяют обрабатывать **10 000+** сообщений в минуту, удерживая использование памяти ниже 200 МБ.

**Вопрос:** Какие типичные сценарии использования имперсонации пользователя в EWS?  
**Ответ:** Управление совместными ящиками, массовое архивирование и запуск запланированных отчетов от имени нескольких пользователей без хранения их паролей.

**Вопрос:** Существуют ли ограничения на количество вызовов API, накладываемые Aspose.Email?  
**Ответ:** Сам Aspose.Email не накладывает ограничений на количество вызовов; однако Exchange может применять политики ограничения нагрузки, которые необходимо учитывать.

**Вопрос:** Как обеспечить безопасность учетных данных в Java‑коде?  
**Ответ:** Храните их в зашифрованных конфигурационных файлах или используйте Azure Key Vault / AWS Secrets Manager, и всегда используйте HTTPS для конечных точек EWS.

---

**Последнее обновление:** 2026-07-08  
**Тестировано с:** Aspose.Email for Java 23.10  
**Автор:** Aspose

## Связанные руководства

- [Как создать экземпляр EWSClient с помощью Aspose.Email для Java: руководство по интеграции с Exchange Server](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Как подключиться к Microsoft Exchange Server с помощью Aspose.Email для Java и EWS](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Автоматизация управления электронной почтой с Aspose.Email и Java EWS Client: полное руководство](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}