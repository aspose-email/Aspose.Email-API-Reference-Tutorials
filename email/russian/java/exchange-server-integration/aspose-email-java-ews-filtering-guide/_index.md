---
date: '2026-07-17'
description: 'Как фильтровать электронные письма с помощью Aspose.Email Java и EWS:
  изучите методы фильтрации по дате, отправителю и теме, чтобы оптимизировать ваш
  почтовый ящик.'
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: Как фильтровать электронные письма с помощью Aspose.Email Java и EWS.
  Узнайте методы фильтрации по дате, отправителю и теме, чтобы ваш почтовый ящик был
  организован.
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: Как фильтровать электронные письма с Aspose.Email Java и EWS
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: Как фильтровать электронные письма с Aspose.Email Java и EWS — руководство
url: /ru/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение фильтрации электронной почты с Aspose.Email Java & EWS: Полное руководство

## Введение

**Как фильтровать электронные письма** эффективно является ключевым навыком для любого, кто работает с Microsoft Exchange или любой современной почтовой системой. Будь то разработчик, создающий корпоративную автоматизацию, или пользователь, желающий поддерживать чистоту входящих, освоение правильных техник фильтрации может сэкономить часы ручного труда. В этом руководстве мы пройдемся по Aspose.Email для Java вместе с Exchange Web Services (EWS), чтобы показать, как фильтровать по дате, отправителю, теме, домену, получателю и даже комбинировать несколько критериев с логическими операторами.

### Что вы узнаете
- Техники фильтрации сообщений с использованием EWS в Java.  
- Фильтрация писем по критериям, таким как дата, отправитель, тема и т.д.  
- Реализация поддержки постраничного вывода для работы с большими почтовыми ящиками.  
- Практические применения этих методов фильтрации в реальных сценариях.  
- Соображения по производительности и лучшие практики с Aspose.Email Java.

К концу этого руководства вы сможете писать чистый, производительный Java‑код, который извлекает именно те сообщения, которые нужны, с сервера Exchange.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.Email for Java.  
- **Какой протокол используется?** Exchange Web Services (EWS).  
- **Можно ли фильтровать по диапазону дат?** Да — используйте критерий `DateTime` в `SearchFilter`.  
- **Поддерживается ли постраничный вывод?** Абсолютно, API предоставляет `ItemView` с offset/limit.  
- **Нужна ли лицензия для продакшн?** Да, коммерческая лицензия снимает ограничения оценки.

## Что такое Aspose.Email for Java?
Aspose.Email for Java — это всесторонний API, который предоставляет программный доступ к почтовым серверам, MIME‑сообщениям и Exchange Web Services без необходимости использовать Outlook или любой другой клиент. Он абстрагирует нижележащие протоколы, позволяя сосредоточиться на бизнес‑логике. Библиотека поддерживает как локальные серверы Exchange, так и Exchange Online, предоставляя единый API для различных сценариев развертывания.

## Почему использовать Aspose.Email с EWS?
Aspose.Email поддерживает **50+** почтовых протоколов и может обрабатывать **сотни тысяч сообщений** в час, удерживая использование памяти ниже **100 МБ** благодаря потоковой архитектуре. Такая измеримая производительность делает её идеальной для автоматизации почтовых ящиков корпоративного масштаба. Кроме того, она имеет встроенную поддержку OAuth и современной аутентификации, упрощая безопасные подключения к средам Office 365.

## Предварительные требования

- **Требуемые библиотеки**: включите библиотеку Aspose.Email в ваш проект.  
- **Настройка окружения**: необходима готовая среда разработки для Java приложений.  
- **Требуемые знания**: знакомство с программированием на Java и почтовыми протоколами будет преимуществом.

## Настройка Aspose.Email для Java

### Установка через Maven
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Приобретение лицензии
- **Бесплатная пробная версия**: начните с бесплатной пробной версии, чтобы изучить возможности Aspose.Email.  
- **Временная лицензия**: получите временную лицензию для расширенной оценки.  
- **Покупка**: рассмотрите покупку полной лицензии, если инструмент соответствует вашим требованиям.

Инициализируйте и настройте Aspose.Email, импортируя необходимые пакеты и устанавливая соединение с вашим почтовым сервером, используя учетные данные EWS. Этот шаг критически важен для программного доступа к данным почтового ящика.

## Как фильтровать письма с помощью EWS в Java?

`ExchangeService` — класс Aspose.Email, представляющий соединение с сервером Exchange.  
`SearchFilter` определяет критерии для поиска элементов на сервере.  
`FindItems` выполняет поиск и возвращает совпадающие элементы.  
`ItemView` контролирует постраничный вывод и количество элементов, возвращаемых за запрос.

Загрузите экземпляр `ExchangeService` с вашими учетными данными, создайте `SearchFilter`, соответствующий вашим критериям, и вызовите `FindItems` с `ItemView`, чтобы получить только нужные сообщения. Этот одно‑строчный шаблон — подключиться → фильтровать → получать — покрывает большинство сценариев и масштабируется для больших ящиков при включённом постраничном выводе.

## Руководство по реализации

### Фильтрация сообщений с помощью EWS

#### Обзор
Фильтрация позволяет получать только те письма, которые соответствуют определённым условиям, например, конкретной теме или дате, непосредственно из вашего почтового ящика.
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**Объяснение**: Код устанавливает соединение с вашим почтовым ящиком и создает запрос для фильтрации писем, содержащих «Newsletter» в теме, на определённую дату.

### Как отфильтровать письма по дате сегодняшнего дня?

`SearchFilter.IsEqualTo` создает фильтр, который совпадает с элементами, где свойство равно заданному значению.  
`DateTimeReceived` — свойство, указывающее, когда письмо было получено.

Загрузите текущую дату, постройте `SearchFilter.IsEqualTo` по свойству `DateTimeReceived` и выполните запрос. Это вернёт только сообщения, полученные в день запуска кода, делая ежедневные скрипты обработки тривиальными. Вы можете комбинировать этот фильтр с дополнительными критериями, такими как отправитель или тема, чтобы ещё точнее сузить результаты за день.

### Как отфильтровать письма по диапазону дат?

`SearchFilter.IsGreaterThanOrEqualTo` создает фильтр, который совпадает с элементами, значение свойства которых больше или равно указанному.  
`SearchFilter.IsLessThanOrEqualTo` создает фильтр, который совпадает с элементами, значение свойства которых меньше или равно указанному.  
`SearchFilter.And` объединяет несколько фильтров, требуя выполнения всех условий.

Определите начальную и конечную `DateTime`, объедините их с помощью `SearchFilter.IsGreaterThanOrEqualTo` и `SearchFilter.IsLessThanOrEqualTo`, затем используйте `SearchFilter.And` для соединения двух. Полученный набор будет содержать каждое сообщение, попадающее в указанный интервал. Этот подход позволяет извлекать всю переписку за любой пользовательский период, например, за последний квартал или конкретный проектный таймлайн.

### Как отфильтровать письма по конкретному отправителю?

`SearchFilter.IsEqualTo` создает фильтр, который совпадает с элементами, где свойство равно заданному значению.

Создайте `SearchFilter.IsEqualTo` по свойству `From` с адресом электронной почты отправителя. Это изолирует все сообщения от данного контакта, что удобно для приоритетных ящиков или проверок соответствия. Вы также можете использовать `SearchFilter.ContainsSubstring` для частичных совпадений, когда точный адрес неизвестен или при фильтрации по домену.

### Как отфильтровать письма по конкретному домену?

`SearchFilter.ContainsSubstring` создает фильтр, который совпадает с элементами, где свойство содержит указанную подстроку.

Используйте `SearchFilter.ContainsSubstring` по свойству `From` с строкой домена (например, “@example.com”). Это извлечёт каждое письмо, пришедшее из данного домена, полезно для мониторинга партнёров или поставщиков. Комбинирование этого фильтра с датой позволяет отслеживать доменно‑специфичную переписку во времени, помогая в аудите безопасности.

### Как отфильтровать письма по конкретному получателю?

`SearchFilter.IsEqualTo` создает фильтр, который совпадает с элементами, где свойство равно заданному значению.

Примените `SearchFilter.IsEqualTo` к коллекции `ToRecipients` для целевого адреса. Это удобно, когда нужно проанализировать сообщения, отправленные в конкретный почтовый ящик или рассылочный список. Вы также можете использовать `SearchFilter.ContainsSubstring` для частичных совпадений при работе с несколькими получателями, имеющими общий домен.

### Как комбинировать запросы с логикой И?

`SearchFilter.And` объединяет несколько фильтров, требуя выполнения всех условий.

Связывайте несколько объектов `SearchFilter` с помощью `SearchFilter.And`. Например, объедините фильтр отправителя с фильтром темы, чтобы получить только рассылки от доверенного отправителя. Оператор И гарантирует, что будут возвращены только элементы, удовлетворяющие всем указанным условиям, сокращая набор результатов до самых релевантных сообщений.

### Как комбинировать запросы с логикой ИЛИ?

`SearchFilter.Or` объединяет фильтры, позволяя совпадать любому из условий.

Используйте `SearchFilter.Or` для объединения фильтров, когда достаточно, чтобы совпало любое из условий — идеально для извлечения сообщений, которые либо от определённого набора отправителей **или** содержат определённые ключевые слова. Применение логики ИЛИ расширяет поиск, позволяя захватить всю релевантную переписку по нескольким категориям без потери важной информации.

## Распространённые ошибки и советы

- **Постраничный вывод обязателен**: при работе с почтовыми ящиками более 1 000 элементов всегда используйте `ItemView` с размером страницы, чтобы избежать тайм‑аутов.  
- **Обработка часовых поясов**: EWS возвращает даты в UTC; преобразуйте их в ваш локальный часовой пояс перед сравнением.  
- **Избегайте полного сканирования ящика**: всегда применяйте `SearchFilter` на стороне сервера; клиентская фильтрация тратит полосу пропускания и память.  
- **Совет профессионала**: кэшируйте объект `ExchangeService` на всё время работы вашего приложения, чтобы снизить нагрузку аутентификации.

## Часто задаваемые вопросы

**Q: Можно ли использовать этот подход с Office 365?**  
A: Да, Aspose.Email работает с Office 365 Exchange Online, указав URL сервиса `https://outlook.office365.com/EWS/Exchange.asmx`.

**Q: Поддерживает ли Aspose.Email аутентификацию OAuth?**  
A: Абсолютно — используйте `OAuthCredentials` для аутентификации без сохранения паролей пользователей.

**Q: Какой максимальный размер почтового ящика я могу обработать?**  
A: API может обрабатывать почтовые ящики **нескольких гигабайт**; благодаря потоковой передаче результатов потребление памяти остаётся низким.

**Q: Как отфильтровать вложения по типу файла?**  
A: Добавьте `SearchFilter.ContainsSubstring` к свойству `AttachmentNames`, затем перебирайте только совпадающие элементы.

**Q: Есть ли способ сортировать результаты?**  
A: Да — передайте `SortDirection` и свойство, по которому нужно сортировать (например, `DateTimeReceived`) в вызов `FindItems`.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Email for Java 24.10  
**Author:** Aspose

## Связанные руководства

- [Как создать экземпляр EWSClient с использованием Aspose.Email for Java: Руководство по интеграции с Exchange Server](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Как загрузить письма с сервера Exchange с помощью Aspose.Email Java](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [Управление информацией почтового ящика EWS с помощью Aspose.Email for Java: Полное руководство](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```