---
"date": "2025-05-30"
"description": "学习如何使用 Aspose.Email for .NET 以编程方式发送电子邮件。本指南涵盖创建电子邮件消息、配置 SMTP 客户端以及有效处理异常。"
"title": "使用 Aspose.Email 在 .NET 中以编程方式发送电子邮件——综合指南"
"url": "/zh/net/smtp-client-operations/send-email-aspose-net-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在.NET中使用Aspose.Email以编程方式发送电子邮件：完整指南

## 介绍

以编程方式发送电子邮件对于许多软件应用程序至关重要，无论是用于通知、更新还是市场营销。在 .NET 生态系统中，可以使用 Aspose.Email 库高效地完成此任务。本指南将指导您如何使用 Aspose.Email .NET API 创建和配置电子邮件消息、设置 SMTP 客户端以及无缝发送电子邮件。

**您将学到什么：**
- 如何创建和配置 `MailMessage` .NET 中的实例。
- 如何使用 Aspose.Email 设置 SMTP 客户端以实现安全的电子邮件传递。
- 使用 Aspose.Email 以编程方式发送电子邮件并有效处理异常的技术。

在深入实施之前，让我们先回顾一些先决条件，以确保您已做好准备。

### 先决条件

要遵循本教程，您需要：
- **.NET 框架/核心**：确保您的计算机上已安装 .NET。本指南适用于 .NET Core 和 .NET Framework。
- **Aspose.Email库**：使用 Aspose.Email 库创建和发送电子邮件。
- **开发环境**：一个合适的 IDE，如 Visual Studio 或 VS Code，并在 C# 中设置一个控制台应用程序项目。
- **基础知识**：需要了解 C#、面向对象编程概念并熟悉 SMTP 协议。

## 设置 Aspose.Email for .NET

首先，将 Aspose.Email 库添加到您的 .NET 项目中。您可以通过以下几种方法完成此操作：

**使用 .NET CLI：**
```shell
dotnet add package Aspose.Email
```

**在 Visual Studio 中使用包管理器控制台：**
```shell
Install-Package Aspose.Email
```

**使用 NuGet 包管理器 UI：**
- 打开 NuGet 包管理器。
- 搜索“Aspose.Email”。
- 安装最新版本。

### 许可证获取
要使用 Aspose.Email，请先从其官方网站下载免费试用版。如需长期使用，请考虑购买许可证或获取临时许可证以解锁所有功能（不受限制）。

## 实施指南

为了清楚起见，本指南分为几个部分：创建和配置电子邮件消息、设置 SMTP 客户端以及发送电子邮件。

### 创建和配置电子邮件消息
创建一个 `MailMessage` 实例涉及指定日期、优先级、敏感度、发件人、收件人、主题和正文等属性。此功能允许您在发送电子邮件之前设置其元数据。

#### 步骤 1：实例化 MailMessage 类
```csharp
using Aspose.Email.Mime;
using System;

// 创建 MailMessage 的新实例
MailMessage msg = new MailMessage();
```

#### 步骤 2：设置电子邮件属性
配置基本电子邮件属性：
- **日期**： 使用 `DateTime.Now` 当前时间。
- **优先事项**：根据紧急程度分配高优先级或普通优先级。
- **敏感度**：通常设置为正常，但可以根据需要进行调整。
- **发件人和收件人**：为两个字段指定电子邮件地址。

```csharp
msg.Date = DateTime.Now;
msg.Priority = MailPriority.High;
msg.Sensitivity = MailSensitivity.Normal;
msg.To = "asposetest123@gmail.com";
msg.From = "aspose.example@gmail.com"; // 使用有效的发件人电子邮件地址\msg.Subject = "测试电子邮件";
msg.Body = "Hello World!";
```

### 配置 SMTP 客户端
设置 `SmtpClient` 需要指定服务器详细信息、凭据和安全选项。此配置步骤可确保您的电子邮件通过指定的 SMTP 服务器安全投递。

#### 步骤1：创建SmtpClient实例
```csharp
using Aspose.Email.Clients.Smtp;
using Aspose.Email.Clients;

private static SmtpClient GetSmtpClient()
{
    // 使用 Gmail 的 SMTP 服务器详细信息进行初始化
    SmtpClient client = new SmtpClient("smtp.gmail.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}