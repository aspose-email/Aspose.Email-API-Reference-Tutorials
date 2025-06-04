---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 通过 EWS 将联系人管理与 Exchange 服务器集成。本指南涵盖了联系人的设置、连接和高效检索。"
"title": "使用 Aspose.Email 和 EWS 在 .NET 中检索联系人——综合指南"
"url": "/zh/net/exchange-server-integration/retrieve-contacts-aspose-email-net-exchange-ews/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 中使用 Aspose.Email 和 EWS 检索联系人：综合指南

## 介绍

从 Exchange 服务器管理联系人可无缝集成到您的 .NET 应用程序中，从而简化沟通工作流程、节省时间并提高工作效率。本教程将指导您使用强大的 **Aspose.Email for .NET** API 通过 Web 服务 (EWS) 连接到 Exchange 服务器并检索联系人列表。

### 您将学到什么：
- 在您的项目中设置 Aspose.Email for .NET
- 使用 EWS 连接到 Exchange 服务器
- 以编程方式检索和显示联系信息

掌握这些技能后，您将能够轻松管理电子邮件通信。让我们先了解一下先决条件。

## 先决条件

在深入代码实现之前，请确保您的开发环境已准备好采取行动：

- **库和版本**：确保您已安装 Aspose.Email for .NET。
- **环境设置**：您需要一个.NET开发环境，例如Visual Studio 2019或更高版本。
- **知识前提**：对 C# 和使用 API 的基本了解将会有所帮助。

## 设置 Aspose.Email for .NET

首先，您需要将 Aspose.Email 库添加到您的项目中。操作如下：

### 安装

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用包管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**通过 NuGet 包管理器 UI：**
搜索“Aspose.Email”并安装最新版本。

### 许可证获取

你可以从 **免费试用** 探索功能。对于较长的项目，请考虑购买许可证或申请临时许可证：
- [免费试用](https://releases.aspose.com/email/net/)
- [购买许可证](https://purchase.aspose.com/buy)
- [临时执照](https://purchase.aspose.com/temporary-license/)

通过添加必要的 using 指令并创建实例来初始化您的项目 `IEWSClient` 用于连接设置。

## 实施指南

本节将引导您完成从 Exchange 服务器检索联系人所需的每个步骤。

### 步骤 1：创建 IEWSClient 实例

**概述**：使用 Aspose.Email 的 EWS 客户端与您的 Exchange 服务器建立安全连接。

```csharp
IEWSClient client = EWSClient.GetEWSClient(
    "https://outlook.office365.com/ews/exchange.asmx", 
    "testUser",    
    "pwd",         
    "domain"       
);
```

**解释**： 代替 `"testUser"`， `"pwd"`， 和 `"domain"` 使用您的实际 Exchange 服务器凭据。此步骤将验证并初始化连接。

### 第 2 步：列出所有联系人

**概述**：使用 EWS 从您的邮箱中获取联系人。

```csharp
Contact[] contacts = client.GetContacts(client.MailboxInfo.ContactsUri);
```

**解释**： `client.GetContacts` 检索所有可用的联系人。该方法返回一个联系人对象数组，可供后续处理。

### 步骤3：显示联系信息

**概述**：遍历检索到的联系人以显示他们的姓名和电子邮件地址。

```csharp
foreach (MapiContact contact in contacts)
{
    Console.WriteLine(
        "Name: " + contact.NameInfo.DisplayName + ", Email Address: " +
        contact.ElectronicAddresses.Email1
    );
}
```

**解释**：循环遍历每个 `MapiContact` 访问和显示姓名和电子邮件地址等重要信息。

### 故障排除提示

- 确保服务器 URL、用户名、密码和域配置正确。
- 如果无法连接到 Exchange 服务器，请检查网络连接。
- 验证您的 API 版本是否与您的 .NET 框架版本兼容。

## 实际应用

以下是一些通过 Aspose.Email 检索联系人可能有益的实际场景：
1. **自动电子邮件营销活动**：自动收集和更新联系人列表以用于营销目的。
2. **CRM集成**：在 Exchange 服务器和 CRM 系统（如 Salesforce 或 Dynamics 365）之间同步联系人信息。
3. **数据备份解决方案**：创建联系人数据备份，确保业务连续性。

## 性能考虑

在.NET应用程序中使用Aspose.Email时：
- **优化网络调用**：通过仅获取必需字段来最大限度地减少 API 调用次数。
- **高效的内存管理**：处理不再需要的对象以释放内存资源。
- **批处理**：如果处理大型数据集，请考虑分批处理联系人。

## 结论

您现在已经学习了如何使用 Aspose.Email for .NET 连接到 Exchange 服务器并检索联系人。这款强大的工具可以显著增强您应用程序的电子邮件管理功能。如需进一步探索，您可以考虑深入研究 API 的高级功能，例如发送电子邮件或管理日历。

立即采取行动，在您的项目中尝试此实现！

## 常见问题解答部分

1. **什么是 Aspose.Email for .NET？**
   - 它是一个通过各种协议（包括 EWS）促进与 Exchange 等电子邮件服务器交互的库。
2. **连接到 Exchange 服务器时如何处理身份验证错误？**
   - 仔细检查您的凭据并确保服务器 URL 正确。
3. **Aspose.Email 可以离线工作吗？**
   - 虽然它主要与在线服务交互，但您可以离线操作本地文件，例如 PST 或 MSG 格式。
4. **我一次可以检索的联系人数量有限制吗？**
   - 联系限制取决于您的 Exchange 服务器配置；如有需要，请咨询您的系统管理员。
5. **如何使用 Aspose.Email 更新联系人信息？**
   - 利用 `UpdateContact` 修改属性后的方法 `MapiContact`。

## 资源

- [Aspose.Email文档](https://reference.aspose.com/email/net/)
- [下载 Aspose.Email](https://releases.aspose.com/email/net/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用](https://releases.aspose.com/email/net/)
- [临时执照](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}