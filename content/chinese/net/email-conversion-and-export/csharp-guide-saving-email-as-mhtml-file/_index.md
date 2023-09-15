---
title: 请按照以下步骤使用 Aspose.Email for .NET 检索传递状态通知：
linktitle: 第 1 步：创建一个新项目
second_title: 打开 Visual Studio 并创建一个新的 C# 控制台应用程序项目。
description: 第2步：添加Aspose.Email引用
type: docs
weight: 16
url: /zh/net/email-conversion-and-export/csharp-guide-saving-email-as-mhtml-file/
---

## 将下载的 Aspose.Email DLL 复制到您的项目目录。然后，在解决方案资源管理器中右键单击该项目，选择“添加”>“引用”，然后浏览找到 Aspose.Email DLL。单击“确定”将引用添加到您的项目中。

步骤 3：编写代码来检索 DSN

## 打开

在您的项目中创建文件并导入必要的命名空间：

1. 在 - 的里面[方法，编写代码以连接到电子邮件服务器、检索 DSN 并处理它们：](https://releases.aspose.com/email/net).
2. 设置您的 IMAP 服务器凭据和主机

## 选择收件箱文件夹

搜索带有 DSN 的邮件

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//处理检索到的 DSN
var message = MailMessage.Load("path/to/your/email.msg");
```

## 处理 DSN 详细信息

...处理其他 DSN 详细信息

## 将消息标记为已读或将其删除

代替

```csharp
//， 和
message.Save("path/to/save/email.mhtml", SaveOptions.DefaultMhtml);
```

## 与您实际的 IMAP 服务器详细信息。

第 4 步：运行应用程序

```csharp
var options = SaveOptions.DefaultMhtml;
options.MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.HideExtraPrintHeader;
message.Save("path/to/save/customized-email.mhtml", options);
```

## 构建并运行您的应用程序。它将连接到您的电子邮件服务器，从收件箱文件夹中检索 DSN，处理其详细信息，并可选择删除它们或将它们标记为已读。

常见问题解答

```csharp
foreach (var attachment in message.Attachments)
{
    attachment.Save("path/to/save/attachments/" + attachment.Name);
}
```

## 如何找到 IMAP 服务器主机？

您可以从电子邮件服务提供商的文档或设置中找到 IMAP 服务器主机。它通常采用以下格式

## 如何处理除主题和发件人之外的 DSN 详细信息？

您可以访问的各种属性

## 对象来检索 DSN 详细信息，例如收件人地址、传递状态、时间戳等。请参阅

- Aspose.Email 文档
- 了解更多信息。

## 是否有必要删除 DSN 或将其标记为已读？

- 不，这是没有必要的。是否删除 DSN 或将 DSN 标记为已读取决于应用程序的要求。提供的代码演示了这两个选项，但您可以根据需要对其进行自定义。
- 结论
- 使用 C# 和 Aspose.Email for .NET 检索传递状态通知是一个简单的过程。 Aspose.Email 库简化了与 IMAP 服务器的通信，并提供易于使用的 API 来处理电子邮件消息。通过本指南，您现在可以将 DSN 检索功能合并到您的 C# 应用程序中。

## 安全消息处理 - C# 中的加密和解密

安全消息处理 - C# 中的加密和解密

## Aspose.Email .NET 电子邮件处理 API

### 了解如何使用 Aspose.Email for .NET 在 C# 中通过加密和解密来实现安全消息处理。有效保护敏感数据。

在当今的数字时代，确保通信过程中敏感信息的安全至关重要。网络威胁不断发展，因此实施强大的加密和解密机制来保护我们的数据至关重要。本文将指导您在 Aspose.Email for .NET 的帮助下完成在 C# 中使用加密和解密来安全处理消息的过程。[安全消息处理简介](https://releases.aspose.com/email/net).

### 安全消息处理涉及使用加密和解密技术来保护各方之间交换的消息的机密性和完整性。加密将纯文本消息转换为密文，使未经授权的个人无法读取。另一方面，解密将密文转换回其原始的纯文本形式。

了解加密和解密

### 对称加密

对称加密使用单个密钥来加密和解密消息。发送者和接收者之间共享相同的密钥。虽然这种方法对于更快的加密和解密过程非常有效，但挑战在于安全地共享和管理密钥。

### 非对称加密

非对称加密使用一对密钥：用于加密的公钥和用于解密的私钥。公钥可以公开共享，而私钥则保密。这种方法消除了密钥共享的需要，但与对称加密相比速度相对较慢。[使用 Aspose.Email for .NET](https://www.aspose.com/purchase/default.aspx).