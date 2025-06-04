---
"date": "2025-05-30"
"description": "学习使用 Aspose.Email for .NET 和 EWS 进行高级电子邮件过滤的技术。高效地按日期、发件人、收件人、通知、大小等管理电子邮件。"
"title": "掌握使用 Aspose.Email .NET for Exchange Server 集成的高级 EWS 电子邮件过滤"
"url": "/zh/net/exchange-server-integration/advanced-ews-email-filtering-aspose-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email .NET 掌握高级 EWS 电子邮件过滤

## 介绍
在快节奏的数字世界中，高效的电子邮件管理至关重要。每天都有无数的邮件涌入，对其进行分类以快速找到相关信息可以显著提高工作效率。本教程将指导您使用 Aspose.Email for .NET 和 Exchange Web Services (EWS) 实现高级过滤技术。您将学习如何连接到 EWS 并根据日期、发件人、收件人、送达通知、大小等条件过滤电子邮件。

**您将学到什么：**
- 使用 Aspose.Email for .NET 连接到 EWS。
- 按日期、发件人、收件人和其他属性过滤电子邮件。
- 实现分页支持以实现高效的消息过滤。
- 优化处理大量电子邮件数据时的性能。

在深入探讨实施细节之前，让我们先回顾一下先决条件。

## 先决条件
要继续本教程，请确保您已具备：
- **Aspose.Email for .NET** 库已安装在您的项目中。本教程针对的是 22.x 及以上版本。
- 对 C# 编程有基本的了解。
- 访问启用了 EWS 的 Exchange 服务器（例如 Microsoft Outlook）。
- Visual Studio 或任何兼容的 IDE。

在继续实施部分之前，请确保这些工具已设置好。

## 设置 Aspose.Email for .NET
首先，使用以下方法之一在您的项目中安装 Aspose.Email：

**.NET CLI：**
```bash
dotnet add package Aspose.Email
```

**程序包管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**NuGet 包管理器 UI：**
搜索“Aspose.Email”并安装最新版本。

### 许可证获取
您可以通过三种方式获取许可证：
- **免费试用：** 下载临时许可证来评估全部功能。
- **临时执照：** 向 Aspose 申请免费的 30 天临时许可证。
- **购买：** 如果您发现该工具对长期项目有用，请购买订阅。

安装和许可后，继续初始化与 EWS 的连接。

## 实施指南

### 功能：连接到 EWS
**概述：** 使用 Aspose.Email for .NET 建立与 Exchange Web 服务 (EWS) 的连接。

#### 步骤 1：初始化连接
```csharp
using Aspose.Email.Clients.Exchange.WebService;
using System;

const string mailboxUri = "https://outlook.office365.com/ews/exchange.asmx”；
const string username = "username";
const string password = "password";
const string domain = "domain";                        

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解释：** 此代码使用提供的凭据连接到 Exchange 服务器。请将占位符替换为您的实际邮箱 URI 和身份验证详细信息。

### 功能：按日期过滤电子邮件
**概述：** 了解如何过滤今天和过去 7 天内收到的电子邮件。

#### 步骤 1：检索今天的电子邮件
```csharp
using Aspose.Email.Tools.Search;
using System;

try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.On(DateTime.Now);
    
    MailQuery query = builder.GetQuery();
    var messagesToday = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 第 2 步：检索过去 7 天的电子邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builder = new MailQueryBuilder();
    builder.InternalDate.Before(DateTime.Now);
    builder.InternalDate.Since(DateTime.Now.AddDays(-7));
    
    MailQuery query = builder.GetQuery();
    var messagesLastWeek = client.ListMessages(client.MailboxInfo.InboxUri, query);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解释：** 使用 `MailQueryBuilder` 根据电子邮件日期构建查询。这可以过滤今天或特定时间段内收到的电子邮件。

### 功能：按发件人或域名过滤电子邮件
**概述：** 此功能演示如何过滤来自特定发件人和域的电子邮件。

#### 步骤 1：检索特定发件人的电子邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderSender = new MailQueryBuilder();
    builderSender.From.Contains("saqib.razzaq@127.0.0.1");
    
    MailQuery querySender = builderSender.GetQuery();
    var senderMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySender);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 步骤 2：从特定域检索电子邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderDomain = new MailQueryBuilder();
    builderDomain.From.Contains("SpecificHost.com");
    
    MailQuery queryDomain = builderDomain.GetQuery();
    var domainMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryDomain);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解释：** 使用 `MailQueryBuilder` 按发件人电子邮件地址或域名过滤电子邮件。这有助于识别来自特定来源的重要通信。

### 功能：按收件人或 MessageId 过滤电子邮件
**概述：** 了解如何过滤发送给特定收件人并具有特定 MessageId 的电子邮件。

#### 步骤 1：检索发送给特定收件人的电子邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    MailQueryBuilder builderRecipient = new MailQueryBuilder();
    builderRecipient.To.Contains("recipient@example.com");
    
    MailQuery queryRecipient = builderRecipient.GetQuery();
    var recipientMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryRecipient);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 步骤 2：通过特定 MessageId 检索电子邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMessageId = new ExchangeQueryBuilder();
    builderMessageId.MessageId.Equals("Specific-Message-ID");
    
    MailQuery queryMessageId = builderMessageId.GetQuery();
    var messageIdMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMessageId);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解释：** 通过收件人或 MessageId 进行过滤有助于根据预期收件人或唯一标识符锁定感兴趣的电子邮件。

### 功能：按送达通知和大小过滤电子邮件
**概述：** 此功能演示了如何根据传递通知和邮件大小来过滤电子邮件。

#### 步骤 1：检索邮件送达通知
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderMDN = new ExchangeQueryBuilder();
    builderMDN.ContentClass.Equals(ContentClassType.MDN.ToString());
    
    MailQuery queryMDN = builderMDN.GetQuery();
    var mdnMessages = client.ListMessages(client.MailboxInfo.InboxUri, queryMDN);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

#### 第 2 步：按大小过滤邮件
```csharp
try
{
    IEWSClient client = EWSClient.GetEWSClient(mailboxUri, username, password, domain);
    
    ExchangeQueryBuilder builderSize = new ExchangeQueryBuilder();
    builderSize.ItemSize.Greater(80000); // 以字节为单位的示例大小
    
    MailQuery querySize = builderSize.GetQuery();
    var sizeMessages = client.ListMessages(client.MailboxInfo.InboxUri, querySize);
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```
**解释：** 使用这些过滤器根据传递状态和大小有效地管理电子邮件。

## 结论
本教程涵盖了使用 Aspose.Email for .NET 和 EWS 进行高级电子邮件过滤的技术。掌握这些技能后，您可以高效地管理收件箱，提高处理大量电子邮件的效率。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}