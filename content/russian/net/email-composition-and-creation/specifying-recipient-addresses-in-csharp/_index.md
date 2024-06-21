---
title: Указание адресов получателей в C#
linktitle: Указание адресов получателей в C#
second_title: Aspose.Email .NET API обработки электронной почты
description: Узнайте, как указать адреса получателей на C# с помощью Aspose.Email для .NET. Эффективно создавайте, настраивайте и отправляйте электронные письма.
type: docs
weight: 19
url: /ru/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Это руководство проведет вас через процесс указания адресов получателей на C# с использованием библиотеки Aspose.Email для .NET. Aspose.Email — это мощный .NET API, который позволяет вам работать с сообщениями электронной почты и выполнять различные задачи, связанные с электронной почтой. В этом уроке мы расскажем, как добавить адреса получателей в сообщение электронной почты с помощью библиотеки.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Visual Studio или любая установленная среда разработки C#.
2.  Aspose.Email для библиотеки .NET. Вы можете получить его из[Aspose.Email для релизов .NET](https://releases.aspose.com/email/net/).

## Шаги

Выполните следующие шаги, чтобы указать адреса получателей на C# с помощью Aspose.Email для .NET:

### 1. Создайте новый проект C#.

Начните с создания нового проекта C# в своей среде разработки.

### 2. Добавьте ссылку на Aspose.Email.

1. Загрузите и установите библиотеку Aspose.Email для .NET, если вы еще этого не сделали.
2. Откройте свой проект C#.
3. Щелкните правой кнопкой мыши «Ссылки» в обозревателе решений и выберите «Добавить ссылку».
4. Просмотрите и выберите файлы Aspose.Email DLL, которые вы скачали.

### 3. Импортируйте необходимые пространства имен.

В файл кода C# импортируйте необходимые пространства имен для использования классов Aspose.Email:

```csharp
using Aspose.Email;

```

### 4. Создайте и настройте сообщение электронной почты.

 Создайте новый экземпляр`MailMessage` класс для представления вашего сообщения электронной почты. Настройте отправителя и тему письма:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Добавьте адреса получателей.

Вы можете добавить адреса получателей, используя`To`, `Cc` , и`Bcc` свойства`MailMessage` сорт. Вот как вы можете добавить адреса получателей:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Заполните электронное письмо.

Добавьте тело электронного письма и любой другой необходимый контент в свое сообщение электронной почты:

```csharp
message.Body = "This is the email body.";
```

### 7. Отправьте электронное письмо

 Чтобы отправить электронное письмо, вы можете использовать`SmtpClient` класс, предоставленный Aspose.Email. Настройте параметры SMTP-сервера и отправьте электронное письмо:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## Часто задаваемые вопросы

###  Как добавить несколько получателей в`To`, `Cc`, or `Bcc` fields?

 Вы можете добавить нескольких получателей, позвонив по телефону`Add` метод несколько раз для соответствующего`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Могу ли я указать имена получателей вместе с их адресами электронной почты?

Да, при добавлении получателей вы можете указать имя и адрес электронной почты получателя:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Как обрабатывать исключения при отправке электронного письма?

Вы можете использовать блоки try-catch для обработки исключений, которые могут возникнуть во время отправки электронной почты:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 Для получения дополнительной информации и расширенных функций Aspose.Email для .NET см.[Ссылки на API Aspose](https://reference.aspose.com/email/net/).

На этом завершается руководство по указанию адресов получателей на C# с использованием Aspose.Email для .NET. Вы узнали, как создать сообщение электронной почты, добавить адреса получателей и отправить электронное письмо, используя функции библиотеки.