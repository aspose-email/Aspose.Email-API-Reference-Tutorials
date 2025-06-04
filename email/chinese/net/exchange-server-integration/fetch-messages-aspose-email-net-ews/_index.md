---
"date": "2025-05-30"
"description": "Aspose.Email Net 代码教程"
"title": "使用 Aspose.Email .NET 和 EWS 获取消息"
"url": "/zh/net/exchange-server-integration/fetch-messages-aspose-email-net-ews/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email .NET 从 Exchange Web 服务获取消息

## 介绍

在当今快节奏的数字环境中，高效管理电子邮件通信对企业和个人都至关重要。无论是检索电子邮件还是处理附件，拥有一个强大的解决方案都能节省时间并简化操作。本指南将重点介绍如何使用 Aspose.Email .NET 通过 Exchange Web 服务 (EWS) 从 Exchange 服务器获取邮件。通过 Aspose.Email，您可以无缝访问收件箱，从而实现高效的电子邮件管理。

### 您将学到什么
- **连接到 Exchange 服务器：** 使用 Aspose.Email 建立连接。
- **列出收件箱消息：** 从您的收件箱中检索并显示消息。
- **获取消息详细信息：** 访问包括附件在内的完整消息内容。
- **设置目录路径：** 组织文档路径以便在应用程序之间保持一致使用。

让我们首先解决有效实施该解决方案所需的先决条件。

## 先决条件

在深入实施之前，请确保您已具备以下条件：

### 所需的库和依赖项
- **Aspose.Email for .NET**：这个库将是我们运营的核心。通过 NuGet 或其他包管理器安装它至关重要。
- **Exchange Web 服务 (EWS) 访问**：您需要访问 Exchange 服务器的凭据。

### 环境设置要求
- 与 Visual Studio 类似的兼容开发环境，支持 C# 和 .NET Framework。
- 如有必要，请拥有机器的管理权限，尤其是设置目录时。

### 知识前提
- 对 C# 编程有基本的了解。
- 熟悉 EWS 等电子邮件协议是有益的，但不是强制性的。

## 设置 Aspose.Email for .NET

设置 Aspose.Email 需要将其集成到您的开发环境中。请按照以下步骤开始：

### 安装信息

您可以使用以下方法之一安装 Aspose.Email：

**.NET CLI：**
```bash
dotnet add package Aspose.Email
```

**程序包管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**NuGet 包管理器 UI：**
- 搜索“Aspose.Email”并安装最新版本。

### 许可证获取步骤

要充分利用 Aspose.Email，您可能需要许可证。操作方法如下：
- **免费试用：** 从下载临时免费许可证 [Aspose的网站](https://purchase.aspose.com/temporary-license/) 探索功能。
- **购买：** 为了长期使用，请考虑购买完整许可证。

### 基本初始化和设置

要开始在您的项目中使用 Aspose.Email：

1. 添加必要的 `using` 指令：
   ```csharp
   using Aspose.Email.Clients.Exchange;
   using Aspose.Email.Clients.Exchange.WebService;
   ```

2. 使用适当的凭据初始化 Exchange 客户端：
   ```csharp
   IEWSClient client = EWSClient.GetEWSClient(
       "https://outlook.office365.com/ews/exchange.asmx",
       "testUser", 
       "pwd", 
       "domain"
   );
   ```

## 实施指南

本节将引导您使用 Aspose.Email 实现关键功能。

### 使用 EWS 从 Exchange Web 服务获取消息

**概述：**  
使用 Aspose.Email 可以简化连接到 Exchange 服务器和检索电子邮件的过程。此功能允许您列出收件箱中的邮件并获取包含附件在内的详细内容。

#### 步骤 1：创建 Exchange 客户端
```csharp
IEWSClient client = EWSClient.GetEWSClient(
    "https://outlook.office365.com/ews/exchange.asmx",
    "testUser", 
    "pwd", 
    "domain"
);
```
**解释：**  
此代码使用提供的凭据初始化与 Exchange 服务器的连接。请确保将占位符替换为实际数据。

#### 步骤 2：列出收件箱中的邮件
```csharp
ExchangeMessageInfoCollection msgCollection = client.ListMessages(client.MailboxInfo.InboxUri);
```
**解释：**  
使用以下方式检索收件箱中的所有邮件 `ListMessages`该方法返回一个消息信息对象的集合。

#### 步骤 3：获取消息详细信息
```csharp
foreach (ExchangeMessageInfo msgInfo in msgCollection)
{
    string strMessageURI = msgInfo.UniqueUri;
    MailMessage msg = client.FetchMessage(strMessageURI);
    
    foreach (Attachment att in msg.Attachments)
    {
        Console.WriteLine("Attachment Name: " + att.Name);
    }
}
```
**解释：**  
对于每条消息，使用 `FetchMessage` 获取完整内容。如有必要，请遍历附件。

### 设置文档和输出目录

**概述：**  
整理目录路径有助于维护整个应用程序的一致性。将这些目录定义为常量，以便于引用。

#### 步骤 1：定义路径常量
```csharp
public static class DirectoryPaths
{
    public const string DocumentDirectory = "@YOUR_DOCUMENT_DIRECTORY";
    public const string OutputDirectory = "@YOUR_OUTPUT_DIRECTORY";
}
```
**解释：**  
用实际目录路径替换占位符，以确保您的应用程序正确引用这些位置。

## 实际应用

以下是使用 Aspose.Email 获取消息的几个实际应用程序：

1. **自动电子邮件处理**：根据内容自动将电子邮件排序并分类到文件夹中。
2. **数据备份解决方案**：定期将重要的电子邮件和附件备份到安全的位置。
3. **与 CRM 系统集成**：直接在客户关系管理 (CRM) 工具中同步电子邮件通信，以增强跟踪。
4. **内容聚合**：收集特定类型的消息，例如发票或通知，以供集中审查。

## 性能考虑

为确保使用 Aspose.Email 时获得最佳性能：

- **批处理：** 批量检索和处理电子邮件以减少服务器负载。
- **内存管理：** 使用后妥善处理物品以释放资源。
- **网络优化：** 通过仅获取必要的数据（例如最初的标头）来最大限度地减少请求的数量。

## 结论

通过本教程，您学习了如何使用 Aspose.Email for .NET 高效地连接到 Exchange 服务器。现在，您可以轻松列出和提取收件箱中的邮件，从而增强您的电子邮件管理能力。如需进一步探索，您可以考虑将这些功能集成到更大型的应用程序中，或自动化特定的工作流程。

### 后续步骤
- 探索 Aspose.Email 的其他功能。
- 在完整的应用程序中实现获取消息的功能。
- 尝试不同类型的电子邮件服务器和配置。

## 常见问题解答部分

1. **如何处理身份验证错误？**  
   确保您的凭据正确并且您的帐户可以访问 EWS。

2. **我可以从子文件夹中获取消息吗？**  
   是的，请在 `ListMessages` 方法。

3. **如果我的连接超时怎么办？**  
   检查网络连接并考虑增加超时设置。

4. **如何按日期或发件人过滤电子邮件？**  
   在获取消息之前使用 EWS 过滤选项来缩小列表范围。

5. **Aspose.Email 是否与所有 .NET 版本兼容？**  
   是的，它支持从 2.0 开始的一系列 .NET 框架。

## 资源

- **文档：** [Aspose Email for .NET 文档](https://reference.aspose.com/email/net/)
- **下载：** [最新发布](https://releases.aspose.com/email/net/)
- **购买许可证：** [立即购买](https://purchase.aspose.com/buy)
- **免费试用：** [开始](https://releases.aspose.com/email/net/)
- **临时执照：** [在此申请](https://purchase.aspose.com/temporary-license/)
- **支持论坛：** [Aspose 电子邮件支持](https://forum.aspose.com/c/email/10)

按照本指南操作，您现在应该能够使用 .NET 中的 Aspose.Email 实现一个强大的解决方案，用于从 Exchange 服务器获取邮件。祝您编程愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}