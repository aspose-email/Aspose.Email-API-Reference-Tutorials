---
title: Подписание электронных писем с помощью DKIM с использованием кода C#
linktitle: Подписание электронных писем с помощью DKIM с использованием кода C#
second_title: Aspose.Email .NET API обработки электронной почты
description: Научитесь защищать электронную почту с помощью DKIM, используя C# и Aspose.Email для .NET. Пошаговое руководство с исходным кодом. Повысьте доверие и подлинность электронной почты.
weight: 11
url: /ru/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Подписание электронных писем с помощью DKIM с использованием кода C#


В современном цифровом мире обеспечение подлинности и целостности сообщений электронной почты имеет первостепенное значение. Один из способов добиться этого — использовать подписи DomainKeys Identified Mail (DKIM). В этом пошаговом руководстве мы рассмотрим, как подписывать электронные письма с помощью DKIM с использованием C# и мощной библиотеки Aspose.Email для .NET.

## Введение в DKIM

### Что такое ДКИМ?
DKIM означает «Почта, идентифицированная DomainKeys». Это метод аутентификации электронной почты, который позволяет отправителю подписывать электронное письмо цифровой подписью, предоставляя криптографическую подпись, подтверждающую подлинность электронного письма.

### Почему DKIM важен?
DKIM помогает предотвратить подделку электронной почты и фишинговые атаки, гарантируя, что входящие электронные письма получены из законных источников и не были подделаны во время передачи.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1.  Aspose.Email for .NET: убедитесь, что в вашем проекте установлена библиотека Aspose.Email for .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/email/net/).

2. Закрытый ключ DKIM. Для подписи электронных писем вам понадобится закрытый ключ DKIM. Убедитесь, что оно у вас готово. 

## Шаг 1. Инициализируйте параметры DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

На этом этапе мы инициализируем параметры DKIM. Мы загружаем закрытый ключ из файла, указываем селектор и домен и перечисляем заголовки, которые должны быть включены в подпись DKIM.

## Шаг 2. Создайте и подготовьте электронное письмо

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Здесь мы создаем экземпляр`MailMessage` class и установите отправителя, получателя, тему и текст электронного письма.

## Шаг 3. Подпишите электронное письмо

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Теперь мы подписываем электронное письмо, используя параметры DKIM и закрытый ключ, который мы инициализировали ранее.

## Шаг 4. Отправьте подписанное электронное письмо.

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Код очистки, если есть
}
```
 На этом этапе мы отправляем подписанное электронное письмо с помощью SMTP-клиента. Обязательно замените`"your.email@gmail.com"` и`"your.password"` с вашими учетными данными Gmail.

## Полный исходный код
```csharp

string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP()+ "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");

MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);

try
{
	SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
	client.Send(signedMsg);                
}
finally
{}
```

## Заключение

Подписание электронных писем с помощью DKIM — важный шаг в обеспечении безопасности и подлинности ваших сообщений электронной почты. С помощью Aspose.Email для .NET и C# вы можете легко внедрить подписи DKIM в процесс отправки электронной почты.

---

## Часто задаваемые вопросы

### Вопрос 1. Что такое DKIM и почему он важен для безопасности электронной почты?

DKIM означает «Почта, идентифицированная доменными ключами», и он важен для безопасности электронной почты, поскольку проверяет подлинность сообщений электронной почты, предотвращая подделку и фишинг.

### Вопрос 2. Как получить закрытый ключ DKIM?

Вы можете получить закрытый ключ DKIM через своего поставщика услуг электронной почты или создав его с помощью криптографических инструментов.

### Вопрос 3. Могу ли я использовать Aspose.Email для .NET с другими поставщиками электронной почты, кроме Gmail?

Да, Aspose.Email for .NET можно использовать с различными поставщиками электронной почты, не ограничиваясь Gmail.

### Вопрос 4. Какие заголовки следует включать в подпись DKIM?

Обычно в подпись DKIM включаются следующие заголовки: «От», «Тема» и любые другие заголовки, важные для аутентификации электронной почты.

### Вопрос 5. Является ли DKIM единственным методом аутентификации электронной почты?

Нет, существуют другие методы, такие как SPF и DMARC, которые используются в сочетании с DKIM для повышения безопасности электронной почты.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
