---
"description": "Узнайте, как защитить электронные письма с помощью DKIM, используя C# и Aspose.Email для .NET. Пошаговое руководство с исходным кодом. Повысьте доверие и подлинность электронной почты."
"linktitle": "Подписание писем с помощью DKIM с использованием кода C#"
"second_title": "API обработки электронной почты Aspose.Email .NET"
"title": "Подписание писем с помощью DKIM с использованием кода C#"
"url": "/ru/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Подписание писем с помощью DKIM с использованием кода C#


В современном цифровом мире обеспечение подлинности и целостности сообщений электронной почты имеет первостепенное значение. Одним из способов достижения этого является использование подписей DomainKeys Identified Mail (DKIM). В этом пошаговом руководстве мы рассмотрим, как подписывать электронные письма с помощью DKIM, используя C# и мощную библиотеку Aspose.Email for .NET.

## Введение в DKIM

### Что такое DKIM?
DKIM означает DomainKeys Identified Mail. Это метод аутентификации электронной почты, который позволяет отправителю подписывать электронное письмо цифровой подписью, предоставляя криптографическую подпись, которая подтверждает подлинность электронного письма.

### Почему DKIM важен?
DKIM помогает предотвратить подделку электронных писем и фишинговые атаки, гарантируя, что входящие электронные письма поступают из законных источников и не были подделаны во время передачи.

## Предпосылки

Прежде чем начать, убедитесь, что у вас выполнены следующие предварительные условия:

1. Aspose.Email for .NET: Убедитесь, что в вашем проекте установлена библиотека Aspose.Email for .NET. Вы можете загрузить ее с [здесь](https://releases.aspose.com/email/net/).

2. DKIM Private Key: Вам понадобится DKIM private key для подписи ваших писем. Убедитесь, что он у вас готов. 

## Шаг 1: Инициализация параметров DKIM

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

На этом шаге мы инициализируем параметры DKIM. Загружаем закрытый ключ из файла, указываем селектор и домен, а также перечисляем заголовки, которые должны быть включены в подпись DKIM.

## Шаг 2: Создайте и подготовьте электронное письмо

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

Здесь мы создаем экземпляр `MailMessage` класс и задайте отправителя, получателя, тему и текст письма.

## Шаг 3: Подпишите электронное письмо

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

Теперь мы подписываем электронное письмо, используя параметры DKIM и закрытый ключ, которые мы инициализировали ранее.

## Шаг 4: Отправьте подписанное электронное письмо

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // Код очистки, если таковой имеется
}
```
На этом этапе мы отправляем подписанное письмо с помощью SMTP-клиента. Убедитесь, что вы заменили `"your.email@gmail.com"` и `"your.password"` с вашими учетными данными Gmail.

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

Подписание писем с помощью DKIM является важным шагом в обеспечении безопасности и подлинности ваших сообщений электронной почты. С помощью Aspose.Email для .NET и C# вы можете легко внедрить подписи DKIM в процесс отправки электронной почты.

---

## Часто задаваемые вопросы

### В1: Что такое DKIM и почему он важен для безопасности электронной почты?

DKIM означает DomainKeys Identified Mail (идентифицированная почта DomainKeys), и он важен для безопасности электронной почты, поскольку проверяет подлинность сообщений электронной почты, предотвращая подделку и фишинг.

### В2: Как получить закрытый ключ DKIM?

Вы можете получить закрытый ключ DKIM через своего поставщика услуг электронной почты или сгенерировать его с помощью криптографических инструментов.

### В3: Могу ли я использовать Aspose.Email для .NET с другими поставщиками электронной почты, помимо Gmail?

Да, Aspose.Email для .NET можно использовать с различными поставщиками электронной почты, не ограничиваясь Gmail.

### В4: Какие заголовки следует включить в подпись DKIM?

Обычно в подпись DKIM включаются заголовки «От», «Тема» и любые другие заголовки, которые важны для аутентификации электронной почты.

### В5: Является ли DKIM единственным методом аутентификации электронной почты?

Нет, существуют и другие методы, такие как SPF и DMARC, которые используются совместно с DKIM для повышения безопасности электронной почты.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}