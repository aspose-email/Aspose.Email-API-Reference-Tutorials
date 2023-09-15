---
title: Установка Aspose.Email для .NET
linktitle: Для начала вам необходимо установить библиотеку Aspose.Email for .NET. Вы можете скачать его с сайта
second_title: Aspose.Релизы
description: или используйте диспетчер пакетов NuGet в Visual Studio.
type: docs
weight: 15
url: /ru/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## Создание нового проекта .NET

Откройте Visual Studio и создайте новый проект .NET.

## Установите библиотеку Aspose.Email для .NET с помощью диспетчера пакетов NuGet.

Теперь вы готовы начать программировать!

1. Загрузка и анализ сообщения электронной почты[Загрузка сообщения электронной почты](https://releases.aspose.com/email/net)Прежде чем мы сможем изменить шрифты в электронном письме, нам нужно загрузить сообщение электронной почты. Вы можете загрузить электронное письмо из различных источников, таких как файл, поток или даже почтовый сервер.

2.  Загрузите сообщение электронной почты

3. Анализ тела сообщения

## После загрузки электронного письма вы можете получить доступ к его различным частям, включая тело HTML. Анализ тела HTML позволяет нам вносить изменения в шрифт.

 Разобрать тело HTML

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//Изменение шрифтов в электронном письме
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Понимание стилей шрифтов

Шрифты в электронных письмах HTML определяются с использованием стилей CSS. Чтобы изменить шрифты, вам необходимо изменить стили CSS, связанные с HTML-содержимым электронного письма.

```csharp
//Программное изменение шрифтов
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Допустим, вы хотите изменить шрифт абзаца в HTML-теле письма. Вот как вы можете это сделать:
        var tnefAttachment = attachment;

        // Изменить шрифт абзаца
        //Преобразование в формат MHT
    }
}
```

## Создание сообщения MHT

Чтобы преобразовать электронное письмо в формат MHT, вам необходимо создать сообщение электронной почты в формате MHT с помощью Aspose.Email.

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

##  Создать сообщение электронной почты в формате MHT.

Сохранение сообщения в формате MHT

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //Наконец, сохраните сообщение в формате MHT в файл.
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // Сохраните сообщение в формате MHT.
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//Полный исходный код
					var tnefAttachment = attachment;

					//Вот полный исходный код, который объединяет все:
					//Заключение
				}
			}
			//В этом руководстве мы рассмотрели, как изменить шрифты во время преобразования MHT с помощью Aspose.Email для .NET. Выполнив эти шаги, вы сможете легко конвертировать сообщения электронной почты в формат MHT, сохраняя при этом нужные стили шрифтов.
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## Часто задаваемые вопросы

- Могу ли я преобразовать несколько писем в формат MHT за один раз?
- Да, вы можете просмотреть коллекцию сообщений электронной почты и применить одни и те же изменения шрифта к каждому сообщению перед преобразованием их в формат MHT.
- Поддерживает ли Aspose.Email другие форматы электронной почты?

## Да, Aspose.Email поддерживает различные форматы электронной почты, включая EML, MSG, PST и другие.

Можно ли дополнительно настроить изменения шрифта?

## Абсолютно! Вы можете изучить дополнительные стили CSS для настройки шрифтов, таких как размер, цвет и выравнивание шрифта.

### Могу ли я использовать Aspose.Email для коммерческих проектов?

Да, Aspose.Email можно использовать как для личных, так и для коммерческих проектов в соответствии с условиями лицензии.[ Помните, что в этом руководстве представлен общий обзор, и вы можете изучить его дальше, обратившись к](https://releases.aspose.com/email/net)

### Справочник по API Aspose.Email

и опробовать различные методы настройки шрифтов. Приятного кодирования!

###  Руководство по C#. Извлечение заголовков электронной почты

 Руководство по C#. Извлечение заголовков электронной почты

###  Aspose.Email .NET API обработки электронной почты

 Узнайте, как извлечь заголовки электронной почты на C# с помощью Aspose.Email для .NET. Пошаговое руководство с исходным кодом для эффективного анализа электронной почты.