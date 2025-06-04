---
"description": "学习如何使用 Aspose.Email for .NET 在 C# 中指定收件人地址。高效地创建、配置和发送电子邮件。"
"linktitle": "在 C# 中指定收件人地址"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "在 C# 中指定收件人地址"
"url": "/zh/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中指定收件人地址



本指南将指导您使用 Aspose.Email for .NET 库在 C# 中指定收件人地址。Aspose.Email 是一个功能强大的 .NET API，可用于处理电子邮件消息以及执行各种与电子邮件相关的任务。在本教程中，我们将介绍如何使用该库向电子邮件消息添加收件人地址。

## 先决条件

开始之前，请确保您已具备以下条件：

1. 安装了 Visual Studio 或任何 C# 开发环境。
2. Aspose.Email for .NET 库。您可以从 [Aspose.Email for .NET 发布](https://releases。aspose.com/email/net/).

## 步骤

按照以下步骤使用 Aspose.Email for .NET 在 C# 中指定收件人地址：

### 1.创建一个新的 C# 项目

首先在您的开发环境中创建一个新的 C# 项目。

### 2. 添加对 Aspose.Email 的引用

1. 如果尚未下载并安装 Aspose.Email for .NET 库，请下载并安装。
2. 打开您的 C# 项目。
3. 右键单击解决方案资源管理器中的“引用”，然后选择“添加引用”。
4. 浏览并选择您下载的 Aspose.Email DLL 文件。

### 3. 导入必要的命名空间

在您的 C# 代码文件中，导入使用 Aspose.Email 类所需的命名空间：

```csharp
using Aspose.Email;

```

### 4.创建并配置电子邮件消息

创建一个新的实例 `MailMessage` 类来表示你的电子邮件消息。配置电子邮件的发件人和主题：

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5.添加收件人地址

您可以使用 `To`， `Cc`， 和 `Bcc` 的属性 `MailMessage` 类。您可以按照以下步骤添加收件人地址：

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. 完成电子邮件信息

将电子邮件正文和任何其他必要内容添加到您的电子邮件消息中：

```csharp
message.Body = "This is the email body.";
```

### 7.发送电子邮件

要发送电子邮件，您可以使用 `SmtpClient` Aspose.Email 提供的类。配置 SMTP 服务器设置并发送电子邮件：

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## 常见问题解答

### 如何添加多个收件人 `To`， `Cc`， 或者 `Bcc` 领域？

您可以通过调用 `Add` 方法多次在各自的 `MailAddressCollection`：

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### 我可以指定收件人姓名及其电子邮件地址吗？

是的，您可以在添加收件人时同时指定收件人的姓名和电子邮件地址：

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### 发送电子邮件时如何处理异常？

您可以使用 try-catch 块来处理电子邮件发送过程中可能发生的异常：

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

有关 Aspose.Email for .NET 的更多信息和高级功能，请参阅 [Aspose API 参考](https://reference。aspose.com/email/net/).

本指南介绍了如何使用 Aspose.Email for .NET 在 C# 中指定收件人地址。您已经学习了如何创建电子邮件消息、添加收件人地址以及使用该库的功能发送电子邮件。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}