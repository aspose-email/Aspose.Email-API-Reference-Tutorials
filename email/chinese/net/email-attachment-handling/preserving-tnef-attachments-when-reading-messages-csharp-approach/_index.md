---
"description": "通过本分步指南和源代码了解如何使用 Aspose.Email for .NET 保存 TNEF 附件。"
"linktitle": "读取邮件时保留 TNEF 附件 - C# 方法"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "读取邮件时保留 TNEF 附件 - C# 方法"
"url": "/zh/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 读取邮件时保留 TNEF 附件 - C# 方法


## TNEF 附件简介

TNEF，也称为“winmail.dat”，是 Microsoft Outlook 和 Exchange 使用的专有电子邮件附件格式。它封装了各种元素，例如格式化文本、嵌入图像，甚至日历信息。然而，当电子邮件在不同的电子邮件客户端或平台之间传输时，TNEF 附件有时会变得无法读取或访问。这时，Aspose.Email for .NET 就可以帮您解决。

## Aspose.Email for .NET 入门

Aspose.Email for .NET 是一个功能全面的库，提供处理电子邮件及其附件的各种功能。首先，您需要：

1. 下载并安装 Aspose.Email：访问 [这里](https://releases.aspose.com/email/net) 下载并安装最新版本的 Aspose.Email for .NET。

2. 创建新项目：打开 Visual Studio 环境并创建一个新的 C# 项目。

3. 添加引用：在您的项目中添加对下载的 Aspose.Email 程序集的引用。

## 加载和解析电子邮件消息

要处理电子邮件，首先需要加载并解析电子邮件。Aspose.Email 提供了一些类，允许您从各种来源加载电子邮件，包括文件、流，甚至电子邮件服务器。以下是如何从文件加载电子邮件的示例：

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

// 加载带有 TNEF 附件的电子邮件
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## 识别和提取 TNEF 附件

加载电子邮件后，下一步是识别并提取 TNEF 附件。TNEF 附件封装在一个特殊的“winmail.dat”文件中。Aspose.Email 简化了识别和提取这些附件的过程：

```csharp
// 检查邮件是否包含 TNEF 附件
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        // 提取 TNEF 附件
        var tnefAttachment = attachment;

        // 访问 TNEF 属性并根据需要进行修改
        // tnef附件.属性...
    }
}
```

## 保留 TNEF 附件

保存 TNEF 附件需要确保提取的附件保留其原始格式和内容。Aspose.Email 提供了访问 TNEF 附件中各种元素（例如文本、嵌入图像和日历数据）的方法和属性。

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## 完整的 C# 代码示例

以下是如何使用 Aspose.Email for .NET 读取和保存 TNEF 附件的完整示例：

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // 加载带有 TNEF 附件的电子邮件
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // 检查邮件是否包含 TNEF 附件
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					// 提取 TNEF 附件
					var tnefAttachment = attachment;

					// 访问 TNEF 属性并根据需要进行修改
					// tnef附件.属性...
				}
			}
			// 保留 TNEF 附件	
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## 处理 TNEF 附件的提示

- 在尝试提取之前，请务必检查电子邮件是否包含 TNEF 附件。
- 利用 Aspose.Email 的方法访问和保存 TNEF 附件内的各种元素。
- 确保您拥有最新版本的 Aspose.Email for .NET，以利用最新的功能。

## 结论

在本指南中，我们探讨了如何在使用 C# 编程语言和 Aspose.Email for .NET 读取邮件时保留 TNEF 附件。Aspose.Email 凭借其全面的工具集，简化了识别、提取和保存 TNEF 附件的流程，确保电子邮件中的关键信息保持完整且易于访问。

## 常见问题解答

### 如何下载 Aspose.Email for .NET？

您可以从发布页面下载 Aspose.Email for .NET： [这里](https://releases.aspose.com/email/net)

### 我可以使用 Aspose.Email 来处理其他电子邮件格式吗？

是的，Aspose.Email 支持各种电子邮件格式，包括 PST、EML、MSG 等。

### Aspose.Email 是否适合小型和大型应用程序？

当然！Aspose.Email 旨在满足从小型项目到企业级解决方案的各种应用需求。

### Aspose.Email 是否定期更新？

是的，Aspose 会定期更新以确保与最新技术和平台的兼容性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}