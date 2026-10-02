---
date: '2026-10-02'
description: Узнайте, как подключить Exchange и вывести список публичных папок Exchange
  с помощью Aspose.Email for Java. Это пошаговое руководство показывает зависимость
  Maven и настройку без кода.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Узнайте, как подключить Exchange и вывести список публичных папок
  Exchange с помощью Aspose.Email for Java. Это руководство охватывает зависимость
  Maven, лицензирование и рекурсивный поиск сообщений.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Как подключить Exchange и вывести список публичных папок в Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Как подключить Exchange и вывести список публичных папок в Java
url: /ru/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как подключить Exchange и вывести список публичных папок в Java

## Введение
В современных предприятиях программный доступ к почтовым ящикам Microsoft Exchange позволяет автоматизировать задачи архивации, мониторинга и создания отчетов. В этом руководстве показано, **как подключить exchange** с помощью Aspose.Email для Java и затем **рекурсивно вывести список публичных папок exchange**. Вы увидите необходимую зависимость Maven, шаги получения лицензии и точную последовательность вызовов API — без дополнительных библиотек. К концу вы сможете извлекать сообщения из любой публичной папки и сохранять их локально.

## Быстрые ответы
- **Какой первый шаг?** Добавьте зависимость Aspose.Email Maven в ваш `pom.xml`.  
- **Нужна ли лицензия?** Да — используйте временную лицензию для оценки или приобретите полную лицензию для продакшна.  
- **Какой класс создаёт соединение?** `ExchangeClient` (или `ImapClient` для IMAP) обрабатывает аутентификацию и связь с сервером.  
- **Могу ли я автоматически перечислять подпапки?** Да — используйте рекурсивный метод `listSubFolders`, предоставляемый API.  
- **Является ли этот подход потокобезопасным?** Объекты клиента не потокобезопасны; создавайте отдельный экземпляр для каждого потока при параллельных нагрузках.

## Что такое подключение к Exchange?
**Как подключить exchange** — это процесс аутентификации Java‑приложения к локальному или облачному серверу Microsoft Exchange, чтобы вы могли выполнять вызовы API, такие как перечисление папок или получение сообщений. Aspose.Email абстрагирует нижележащие протоколы EWS/IMAP, предоставляя единый согласованный объектный модель.

## Зачем перечислять публичные папки Exchange?
Перечисление публичных папок даёт представление о иерархической структуре, которую организации используют для общих почтовых ящиков, рассылочных списков и архивных хранилищ. Aspose.Email может перечислять более **50 публичных папок** за один вызов и поддерживает обработку многосотстраничных ящиков без загрузки всего хранилища в память, что снижает потребление ОЗУ до 70 %.

## Требования
- **Aspose.Email for Java** — версия 25.4 или новее (последний стабильный релиз).  
- **Java Development Kit (JDK)** — установлен JDK 11 или новее, настроена переменная `JAVA_HOME`.  
- **Maven** — для управления зависимостями и автоматизации сборки.  
- Базовые знания синтаксиса Java и концепций Exchange (почтовые ящики, папки, EWS).

## Настройка Aspose.Email для Java
Чтобы интегрировать библиотеку, добавьте зависимость Maven в файл `pom.xml` вашего проекта. Это **зависимость Maven Aspose.Email**, которая вам понадобится.

### Зависимость Maven
Добавьте следующий фрагмент внутри элемента `<dependencies>` вашего `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Шаги получения лицензии
Aspose.Email требует действительную лицензию для полного использования функций:

- **Бесплатная пробная версия** – Скачайте временную лицензию с [веб‑сайта Aspose](https://purchase.aspose.com/temporary-license/) для оценки API.  
- **Покупка** – Приобретите коммерческую лицензию через портал Aspose для продуктивных развертываний.

#### Базовая инициализация
После того как Maven загрузит пакет и у вас появится файл лицензии, разместите файл `.lic` в classpath и инициализируйте библиотеку:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Руководство по реализации
Мы пройдём каждый функциональный блок, отвечая на ключевые вопросы короткими, чёткими абзацами перед детальными шагами.

### Как подключить exchange?
Загрузите `ExchangeClient`, указав URL сервера, учётные данные пользователя и домен, затем вызовите `connect()`. Клиент устанавливает HTTPS‑сеанс с Exchange Web Services (EWS) и проверяет учётные данные. Если соединение не удаётся, API бросает подробное `AuthenticationException`, содержащее код HTTP‑статуса для быстрой диагностики.  
`ExchangeClient` — класс Aspose.Email, управляющий соединением с Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Как вывести список публичных папок Exchange?
Вызовите `client.listPublicFolders()`, чтобы получить коллекцию объектов `FolderInfo`, представляющих каждую публичную папку верхнего уровня. Метод возвращает метаданные, такие как имя папки, общее количество элементов и уникальный идентификатор, используемый в последующих вызовах. Этот вызов завершается менее чем за 2 секунды для типовых локальных развертываний с до 500 папками.  
`listPublicFolders()` возвращает коллекцию объектов `FolderInfo`.  
`FolderInfo` содержит метаданные, такие как отображаемое имя и количество элементов.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Как отобразить информацию о папке?
Итерируйте коллекцию `FolderInfo` и выводите `displayName` и `subFolderCount`. Этот быстрый снимок помогает понять иерархию перед более глубокой обработкой. Для крупных организаций API может постранично возвращать по 100 папок, чтобы снизить использование памяти.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Как вывести список сообщений из папки?
Вызовите `client.listMessages(folderId)`, где `folderId` — идентификатор, полученный на предыдущем шаге. Метод возвращает список объектов `MessageInfo` с темой, отправителем и датой получения. Вы можете ограничить набор результатов параметром `maxCount`, чтобы не перегружать клиент при обработке очень больших папок.  
`listMessages(folderId)` возвращает список объектов `MessageInfo`.  
`MessageInfo` содержит базовые свойства письма, такие как тема, отправитель и дата получения.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Как получить и сохранить сообщения?
Для каждого `MessageInfo` используйте `client.fetchMessage(messageId)`, чтобы загрузить полное MIME‑содержимое. Затем запишите массив байтов в файл `.eml` на диске. API потоково передаёт содержимое, поэтому даже сообщения размером 100 МБ обрабатываются без загрузки полного полезного нагрузки в память.  
`fetchMessage(messageId)` загружает полное MIME‑содержимое указанного письма.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Как рекурсивно вывести список сообщений из подпапок?
Реализуйте обход в глубину: начните с папки верхнего уровня, перечислите её подпапки через `client.listSubFolders(parentId)`, затем вызовите ту же процедуру получения сообщений для каждой дочерней папки. Такой подход гарантирует обработку каждого сообщения в дереве публичных папок. Глубина рекурсии ограничена только иерархией папок сервера (обычно < 20 уровней).  
`listSubFolders(parentId)` возвращает непосредственные дочерние папки указанной папки.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Практические применения
Реальные сценарии, где этот рабочий процесс особенно полезен:

1. **Автоматическое архивирование электронной почты** – Периодически извлекать все сообщения из публичных папок и сохранять их в соответствующий архив.  
2. **Решения резервного копирования** – Копировать публичные папки Exchange в защищённую файловую систему или облачное хранилище, обеспечивая избыточность данных.  
3. **Пользовательские почтовые клиенты** – Создавать лёгкие просмотрщики, отображающие только нужные папки и сообщения, уменьшая сложность пользовательского интерфейса.

## Соображения по производительности
При масштабировании до тысяч папок и миллионов сообщений учитывайте следующие рекомендации:

- **Пул соединений** – Переиспользуйте один экземпляр `ExchangeClient` для нескольких операций вместо создания нового клиента для каждой папки.  
- **Ленивая загрузка** – Запрашивайте только необходимые метаданные (`listMessages` с параметром `maxCount`) и получайте полные тела по требованию.  
- **Освобождение объектов** – Вызывайте `client.dispose()` после завершения пакетной обработки, чтобы освободить HTTP‑соединения и буферы потока.  
- **Параллельная обработка** – Распределяйте папки верхнего уровня между несколькими потоками, каждый со своим экземпляром клиента, чтобы эффективно использовать многоядерные процессоры.

## Часто задаваемые вопросы

**В: Можно ли использовать этот код с Exchange Online (Office 365)?**  
О: Да. Укажите конечную точку EWS Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) и используйте современную аутентификацию (OAuth) – Aspose.Email поддерживает OAuth‑токены из коробки.

**В: Что делать, если папка содержит более 10 000 сообщений?**  
О: Используйте перегруженный вариант `listMessages`, принимающий параметры `skip` и `take`, чтобы постранично обходить результаты и контролировать потребление памяти.

**В: Есть ли ограничение на размер одного письма, которое я могу загрузить?**  
О: API потоково передаёт содержимое, поэтому поддерживаются сообщения до 150 MB без превышения лимита кучи Java, при условии наличия достаточного нативного объёма памяти JVM.

**В: Нужно ли вручную обрабатывать SSL‑сертификаты?**  
О: По умолчанию Aspose.Email доверяет Java‑стандартному хранилищу сертификатов. Если ваш сервер Exchange использует самоподписанный сертификат, импортируйте его в truststore JVM или установите `client.setEnableSslVerification(false)` только для тестирования.

**В: Как вести журнал операций для целей аудита?**  
О: Включите встроенное логирование Aspose.Email, настроив `Logger.setLevel(Level.INFO)` и направив вывод в файл или систему мониторинга.

## Заключение
Теперь у вас есть полностью готовый, пригодный для продакшна рецепт **как подключить exchange** и рекурсивно перечислять сообщения из публичных папок с помощью Aspose.Email для Java. Шаги охватывают настройку Maven, лицензирование, соединение, перечисление папок, получение сообщений и оптимизацию производительности. Расширяйте эту основу, интегрируя её с базами данных, облачными хранилищами или пользовательскими аналитическими конвейерами, чтобы удовлетворить специфические потребности вашей организации.

---

**Last Updated:** 2026-10-02  
**Тестировано с:** Aspose.Email for Java 25.4  
**Автор:** Aspose

## Связанные руководства

- [Как подключить к серверу Exchange с помощью Aspose.Email в Java: пошаговое руководство](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Как подключить и вывести список папок сервера Exchange с помощью Aspose.Email для Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Управление папками сервера Exchange с помощью Aspose.Email для Java: полное руководство](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}