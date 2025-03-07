---
title: 在 C# 中指定收件人地址
linktitle: 在 C# 中指定收件人地址
second_title: Aspose.Email .NET 电子邮件处理 API
description: 了解如何使用 Aspose.Email for .NET 在 C# 中指定收件人地址。高效地创建、配置和发送电子邮件。
weight: 19
url: /zh/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中指定收件人地址



本指南将引导您完成使用 Aspose.Email for .NET 库在 C# 中指定收件人地址的过程。 Aspose.Email 是一个功能强大的 .NET API，允许您处理电子邮件和各种与电子邮件相关的任务。在本教程中，我们将介绍如何使用该库将收件人地址添加到电子邮件中。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了 Visual Studio 或任何 C# 开发环境。
2.  Aspose.Email for .NET 库。您可以从[Aspose.Email for .NET 版本](https://releases.aspose.com/email/net/).

## 脚步

按照以下步骤使用 Aspose.Email for .NET 在 C# 中指定收件人地址：

### 1. 新建一个C#项目

首先在开发环境中创建一个新的 C# 项目。

### 2.添加对Aspose.Email的引用

1. 如果尚未安装，请下载并安装 Aspose.Email for .NET 库。
2. 打开您的 C# 项目。
3. 右键单击解决方案资源管理器中的“引用”，然后选择“添加引用”。
4. 浏览并选择您下载的 Aspose.Email DLL 文件。

### 3.导入必要的命名空间

在您的 C# 代码文件中，导入使用 Aspose.Email 类所需的命名空间：

```csharp
using Aspose.Email;

```

### 4. 创建并配置电子邮件

创建一个新实例`MailMessage`类来表示您的电子邮件消息。配置电子邮件的发件人和主题：

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. 添加收件人地址

您可以使用以下命令添加收件人地址`To`, `Cc`， 和`Bcc`的属性`MailMessage`班级。添加收件人地址的方法如下：

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. 填写电子邮件消息

将电子邮件正文和任何其他必要的内容添加到您的电子邮件中：

```csharp
message.Body = "This is the email body.";
```

### 7. 发送电子邮件

要发送电子邮件，您可以使用`SmtpClient`Aspose.Email 提供的类。配置 SMTP 服务器设置并发送电子邮件：

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## 常见问题解答

### 如何将多个收件人添加到`To`, `Cc`, or `Bcc` fields?

您可以通过调用添加多个收件人`Add`对各自的方法多次`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### 我可以指定收件人姓名及其电子邮件地址吗？

是的，您可以在添加收件人时指定收件人的姓名和电子邮件地址：

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### 发送邮件时出现异常如何处理？

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

有关 Aspose.Email for .NET 的更多信息和高级功能，请参阅[Aspose API 参考](https://reference.aspose.com/email/net/).

关于使用 Aspose.Email for .NET 在 C# 中指定收件人地址的指南到此结束。您已了解如何创建电子邮件、添加收件人地址以及使用库的功能发送电子邮件。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
