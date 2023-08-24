---
title: Получение уведомлений о статусе доставки с помощью C#
linktitle: Получение уведомлений о статусе доставки с помощью C#
second_title: Aspose.Email .NET API обработки электронной почты
description: Узнайте, как получать уведомления о статусе доставки электронной почты с помощью C# и Aspose.Email для .NET.
type: docs
weight: 18
url: /ru/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Введение

При общении по электронной почте уведомления о статусе доставки (DSN) играют решающую роль в информировании отправителей о статусе доставки их электронных писем. Aspose.Email для .NET — это мощная библиотека, предоставляющая функциональные возможности для работы с электронной почтой, включая получение DSN. В этом руководстве мы рассмотрим процесс получения уведомлений о статусе доставки с использованием C# и библиотеки Aspose.Email для .NET.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio установлена.
2.  Aspose.Email для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/email/net).
3. Базовое понимание программирования на C#.

## Шаги

Выполните следующие шаги, чтобы получить уведомления о статусе доставки с помощью Aspose.Email для .NET:

### Шаг 1. Создайте новый проект

Откройте Visual Studio и создайте новый проект консольного приложения C#.

### Шаг 2. Добавьте ссылку на Aspose.Email

Скопируйте загруженную DLL Aspose.Email в каталог вашего проекта. Затем щелкните правой кнопкой мыши проект в обозревателе решений, выберите «Добавить» > «Ссылка» и найдите DLL Aspose.Email. Нажмите «ОК», чтобы добавить ссылку на ваш проект.

### Шаг 3. Напишите код для получения DSN

 Открой`Program.cs` файл в свой проект и импортируйте необходимые пространства имен:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 Внутри`Main` напишите код для подключения к почтовому серверу, получения DSN и их обработки:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Установите учетные данные и хост IMAP-сервера
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Выберите папку «Входящие»
            client.SelectFolder(ImapFolderInfo.InBox);

            // Поиск сообщений с помощью DSN
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Обработка полученных DSN
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // Обработать сведения о DSN
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Обработка других данных DSN

                // Отметьте сообщение как прочитанное или удалите его.
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Заменять`"your_imap_host"`, `"your_email"` , и`"your_password"` с фактическими данными вашего IMAP-сервера.

### Шаг 4. Запустите приложение

Создайте и запустите свое приложение. Он подключится к вашему почтовому серверу, получит DSN из папки «Входящие», обработает их данные и при необходимости удалит их или пометит как прочитанные.

## Часто задаваемые вопросы

### Как найти хост-сервер IMAP?

 Хост IMAP-сервера можно найти в документации или настройках вашего поставщика услуг электронной почты. Обычно это в формате`imap.yourdomain.com`.

### Как я могу обработать данные DSN, кроме темы и отправителя?

 Вы можете получить доступ к различным свойствам`MailMessage` объект для получения данных DSN, таких как адреса получателей, статус доставки, временная метка и т. д. Обратитесь к[Документация Aspose.Email](https://reference.aspose.com/email/net/) Чтобы получить больше информации.

### Нужно ли удалять или отмечать DSN как прочитанные?

Нет, это не обязательно. Удалять или помечать DSN как прочитанные зависит от требований вашего приложения. Приведенный код демонстрирует оба варианта, но вы можете настроить его в соответствии со своими потребностями.

## Заключение

Получение уведомлений о статусе доставки с использованием C# и Aspose.Email для .NET — это простой процесс. Библиотека Aspose.Email упрощает связь с сервером IMAP и предоставляет простые в использовании API для обработки сообщений электронной почты. Благодаря этому руководству вы теперь можете включить функцию получения DSN в свои приложения C#.