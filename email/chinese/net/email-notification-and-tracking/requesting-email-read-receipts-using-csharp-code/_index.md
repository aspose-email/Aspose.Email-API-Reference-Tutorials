---
title: 使用 C# 代码请求电子邮件已读回执
linktitle: 使用 C# 代码请求电子邮件已读回执
second_title: Aspose.Email .NET 电子邮件处理 API
description: 了解如何使用 C# 代码使用 Aspose.Email for .NET 请求电子邮件阅读回执，从而增强通信跟踪。
weight: 11
url: /zh/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 代码请求电子邮件已读回执


在当今的数字时代，通过电子邮件进行交流已成为我们个人和职业生活中不可或缺的一部分。通常，在发送重要电子邮件时，我们希望确保收件人已阅读并确认我们的消息。这就是电子邮件阅读回执发挥作用的地方。在本分步教程中，我们将指导您完成使用 C# 和 Aspose.Email for .NET 请求电子邮件已读回执的过程。

## 电子邮件已读回执简介

电子邮件阅读回执，也称为电子邮件跟踪或回执，允许您在收件人打开并阅读您的电子邮件时收到通知。这是一个很有价值的功能，特别是在商业通信中，因为它提供了消息传递和参与的确认。

## 先决条件

在我们深入研究代码之前，请确保您具备以下先决条件：

- Visual Studio 安装在您的系统上。
- 下载 Aspose.Email for .NET 库并在您的项目中引用。

## 第 1 步：创建 MailMessage 实例

实现电子邮件阅读回执的第一步是创建一个实例`MailMessage`班级。此类代表电子邮件消息并允许您设置电子邮件的各种属性。

```csharp
MailMessage message = new MailMessage();
```

## 第 2 步：指定消息详细信息

现在，让我们指定电子邮件的详细信息，包括发件人、收件人、HTML 正文和送达通知选项。

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## 步骤3：创建SmtpClient实例

要发送电子邮件，我们需要创建一个实例`SmtpClient`类，负责发送消息。

```csharp
SmtpClient client = new SmtpClient();
```

## 步骤 4：配置 SMTP 设置

通过指定主机服务器、用户名、密码和端口号来配置 SMTP 服务器设置。

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## 第 5 步：发送电子邮件

最后，使用`client.Send`发送电子邮件消息的方法。如果消息发送成功，将会显示“消息已发送”通知。

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

通过这五个简单的步骤，您可以在使用 C# 和 Aspose.Email for .NET 发送电子邮件时请求电子邮件已读回执。此功能为您的电子邮件通信增加了一层保证，确保您知道重要消息何时被阅读。

## 完整的源代码
```csharp
//创建 MailMessage 类的实例
MailMessage message = new MailMessage();

//指定 From、To、HtmlBody、DeliveryNotificationOptions 字段
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

//创建 SmtpClient 类的实例
SmtpClient client = new SmtpClient();

//指定您的邮件主机服务器、用户名、密码和端口号
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	//Client.Send 将发送此消息
	client.Send(message);
	//仅当消息发送成功时才显示“消息已发送”
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## 结论

在本教程中，我们探讨了如何使用 C# 和 Aspose.Email for .NET 请求电子邮件已读回执。电子邮件跟踪是一个强大的工具，可确保您的邮件被预期收件人传递和阅读，特别是在专业环境中。通过遵循此处概述的步骤，您可以在电子邮件应用程序中轻松实现此功能。

## 常见问题 (FAQ)

1. ### 电子邮件阅读回执的目的是什么？
   电子邮件阅读回执可确认收件人已打开并阅读电子邮件。它们通常用于跟踪重要或时间敏感的消息。

2. ### 收件人可以禁用电子邮件已读回执吗？
   是的，电子邮件客户端通常允许用户禁用发送已读回执。因此，不能保证您总是会收到它们。

3. ### 电子邮件已读回执是所有电子邮件客户端的标准功能吗？
   不，电子邮件阅读回执并未得到普遍支持。它们是否有效取决于电子邮件客户端和收件人的设置。

4. ### 是否可以跟踪电子邮件在移动设备上打开的时间？
   电子邮件跟踪通常基于收件人的电子邮件客户端和设置，因此它可能会或可能不会在移动设备上运行，具体取决于各种因素。

5. ### 使用电子邮件阅读回执时是否需要考虑隐私问题？
   是的，存在与电子邮件跟踪相关的隐私问题。一些接收者可能认为它具有侵入性，因此必须负责任地使用此功能并尊重隐私偏好。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
