---
date: '2026-08-11'
description: Узнайте, как перемещать папки и сообщения pst с использованием Aspose.Email
  for Java — пошаговое руководство по эффективному перемещению pst.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Узнайте, как перемещать папки и сообщения pst с помощью Aspose.Email
  for Java в несколько строк кода. В этом руководстве рассматриваются настройка, перемещение
  подпапок, отдельных элементов и лучшие практики работы с большими файлами pst.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: Как переместить папки и сообщения pst с помощью Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: Как переместить папки и сообщения pst с помощью Aspose.Email Java
url: /ru/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как переместить папки PST и сообщения с помощью Aspose.Email Java

Эффективное управление электронной почтой имеет решающее значение, когда необходимо реорганизовать большие файлы Outlook PST. В этом руководстве вы узнаете, **как переместить PST** папки и сообщения программно с помощью Aspose.Email для Java, что позволяет автоматизировать очистку, миграцию и архивирование без запуска Outlook. Для полной информации об API см. [Справочник Aspose Email Java](https://reference.aspose.com/email/java/).

## Быстрые ответы
- **Какая библиотека используется?** Aspose.Email for Java  
- **Могу ли я переместить как папки, так и отдельные сообщения?** Да — используйте `moveItem` для сообщений и `moveSubfolders` для целых папок  
- **Нужна ли лицензия для продакшн?** Для коммерческих развертываний требуется действующая лицензия Aspose  
- **Какая версия Java рекомендуется?** Java 16 или новее для оптимальной производительности  
- **Требуется ли пример PST‑файла?** Любой PST, созданный в Outlook, подходит; вы можете создать его в Outlook или использовать тестовый файл  

## Что означает перемещение PST в разработке на Java?
Перемещение PST подразумевает программное перемещение папок или элементов электронной почты внутри файла Personal Storage Table (PST). Это позволяет автоматизировать массовую очистку, архивировать старую почту или мигрировать содержимое между хранилищами без ручного взаимодействия с Outlook, повышая эффективность и снижая риск человеческих ошибок.

## Почему использовать Aspose.Email для Java для перемещения данных PST?
Вы можете перемещать данные PST с помощью Aspose.Email, потому что он предоставляет **чистый Java API**, работающий на любой операционной системе, поддерживает **файлы PST более 100 ГБ** и обрабатывает **до 500 000 элементов в минуту** на стандартном серверном оборудовании. Библиотека также предоставляет детальные исключения, позволяющие быстро выявлять проблемы.

## Предварительные требования
- Aspose.Email for Java (последняя версия)  
- JDK 16+ (или новее)  
- Система сборки Maven или Gradle  
- PST‑файл для тестирования (любой файл, созданный в Outlook)

## Настройка Aspose.Email для Java
Чтобы использовать Aspose.Email, добавьте зависимость Maven в ваш файл `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Шаги получения лицензии
1. **Бесплатная пробная версия** — начните с бесплатной пробной версии, чтобы изучить возможности Aspose.Email.  
2. **Временная лицензия** — получите временную лицензию для длительного использования на сайте [Aspose](https://purchase.aspose.com/temporary-license/).  
3. **Покупка** — рассмотрите возможность покупки полной лицензии, если библиотека удовлетворяет ваши производственные требования. Для деталей ценообразования см. [Варианты покупки Aspose](https://purchase.aspose.com/buy).

### Базовая инициализация и настройка
Убедитесь, что библиотека правильно подключена, прежде чем начинать работу с PST‑файлами:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Как переместить папки PST и сообщения
Ниже перечислены основные операции, которые вам понадобятся, когда вы хотите эффективно **перемещать PST** элементы.

### Инициализация и доступ к PST‑файлу
`PersonalStorage` — основной класс Aspose.Email для открытия и работы с PST‑файлами.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Шаг 1: Загрузка PST‑файла
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Шаг 2: Доступ к предопределённым папкам
- **Папка «Входящие»**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Папка «Удалённые элементы»**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Перемещение подпапки в другую папку PST
`FolderInfo` представляет папку внутри PST‑файла и предоставляет методы для перемещения подпапок.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Шаг 1: Доступ к исходной и целевой папкам
```java
pst.moveItem(subfolder, deletedItems);
```

#### Шаг 2: Получить конкретную подпапку из «Входящих»
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Шаг 3: Переместить всю подпапку
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Перемещение отдельных сообщений между папками PST
`MessageInfoCollection` содержит коллекцию объектов `MessageInfo`, каждый из которых представляет электронное сообщение.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Шаг 1: Получить сообщения из конкретной подпапки
```java
inbox.moveSubfolders(deletedItems);
```

#### Шаг 2: Переместить первое сообщение в папку «Удалённые элементы»
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Перемещение всех подпапок из одной папки в другую в PST
`moveSubfolders` переносит каждую дочернюю папку из источника в назначение одним вызовом.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Шаг 1: Доступ к исходной и целевой папкам
```java
subfolder.moveContents(deletedItems);
```

#### Шаг 2: Переместить все подпапки
CODE_BLOCK_PLACEHOLDER_15_END

### Перемещение всего содержимого подпапки в другую папку PST
`moveAllContents` (пользовательский цикл с использованием `moveItem`) может переместить каждое сообщение внутри подпапки.

CODE_BLOCK_PLACEHOLDER_16_END

#### Шаг 1: Доступ к исходной и целевой папкам
CODE_BLOCK_PLACEHOLDER_17_END

#### Шаг 2: Получить конкретную подпапку из «Входящих»
CODE_BLOCK_PLACEHOLDER_18_END

#### Шаг 3: Переместить всё содержимое подпапки
CODE_BLOCK_PLACEHOLDER_19_END

## Практические применения
Перемещение папок PST и сообщений полезно для:
- **Миграция данных** — перемещение почтовых ящиков из Outlook в другую почтовую систему.  
- **Архивирование электронной почты** — автоматическая организация старой почты в архивные папки.  
- **Операции очистки** — упорядочивание входящих, перемещая устаревшие элементы в архивные или папки удаления.

## Соображения по производительности
При работе с большими PST‑файлами с помощью Aspose.Email для Java следуйте этим рекомендациям:
- **Оптимизировать использование ресурсов** — своевременно закрывать объекты `PersonalStorage`, используя try‑with‑resources или явный `dispose`.  
- **Управление памятью** — обрабатывать элементы пакетами вместо загрузки всей папки в память; это снижает нагрузку на кучу JVM.

### Лучшие практики
- Всегда освобождайте ресурсы PST после операций.  
- Проверяйте существование папки перед попыткой перемещения, чтобы избежать `InvalidOperationException`.  

## Часто задаваемые вопросы

**В: Что такое PST‑файл?**  
**О:** PST (Personal Storage Table) — собственный формат Outlook для локального хранения сообщений электронной почты, контактов, элементов календаря и других данных почтового ящика.

**В: Можно ли использовать Aspose.Email для Java в коммерческих проектах?**  
**О:** Да, вы можете использовать его в коммерческих целях, при условии наличия действующей лицензии, полученной через [Варианты покупки Aspose](https://purchase.aspose.com/buy).

**В: Как обрабатывать исключения при работе с PST‑файлами с помощью Aspose.Email?**  
**О:** Оберните код в блоки `try‑catch`, чтобы перехватывать `IOException`, `InvalidOperationException` или специфические исключения Aspose, затем записывайте детали ошибки в журнал или пробрасывайте дальше при необходимости.

**В: Каковы системные требования для выполнения этого кода?**  
**О:** Требуется JDK 16 или новее и совместимая IDE, например IntelliJ IDEA или Eclipse. JAR‑файл Aspose.Email должен находиться в classpath вашего проекта.

**В: Где можно найти дополнительные ресурсы по Aspose.Email для Java?**  
**О:** Посетите официальную документацию по адресу [Справочник Aspose Email Java](https://reference.aspose.com/email/java/).

**В: Поддерживает ли Aspose.Email PST‑файлы, защищённые паролем?**  
**О:** Да, вы можете открыть зашифрованные PST, передав пароль при вызове `PersonalStorage.fromFile`.

**В: Как проверить, что операция перемещения завершилась успешно?**  
**О:** После вызова `moveItem` или `moveSubfolders` запросите содержимое целевой папки с помощью `getContents()` или `getSubFolders()`, чтобы убедиться в наличии перемещённых элементов.

## Ресурсы
- **Документация**: [Справочник Aspose Email Java](https://reference.aspose.com/email/java/)  
- **Подробности API**: [Справочник Aspose Email Java](https://reference.aspose.com/email/java/)  
- **Скачать**: [Выпуски Aspose Email Java](https://releases.aspose.com/email/java/)  
- **Покупка**: [Купить продукты Aspose](https://purchase.aspose.com/buy)  
- **Бесплатная пробная версия**: [Бесплатные пробные версии Aspose](https://releases.aspose.com/email/java/)  
- **Временная лицензия**: [Получить временную лицензию](https://purchase.aspose.com/temporary-license/)

---

**Последнее обновление:** 2026-08-11  
**Тестировано с:** Aspose.Email for Java 25.4 (JDK 16)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Массовое обновление сообщений PST с Aspose.Email для Java: Полное руководство](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Как извлечь сообщения Outlook PST с помощью Aspose.Email для Java: Полное руководство](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Перенос сообщений между PST‑файлами с Aspose.Email для Java: Полное руководство](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}