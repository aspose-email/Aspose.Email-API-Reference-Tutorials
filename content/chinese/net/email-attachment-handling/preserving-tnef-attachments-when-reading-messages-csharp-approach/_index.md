---
title: 安装 Aspose.Email for .NET
linktitle: 首先，您需要安装 Aspose.Email for .NET 库。您可以从
second_title: Aspose. 发布
description: 或使用 Visual Studio 中的 NuGet 包管理器。
type: docs
weight: 15
url: /zh/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## 创建新的 .NET 项目

打开 Visual Studio 并创建一个新的 .NET 项目。

## 使用 NuGet 包管理器安装 Aspose.Email for .NET 库。

您现在已经准备好开始编码了！

1. 加载和解析电子邮件消息[加载电子邮件消息](https://releases.aspose.com/email/net)在修改电子邮件中的字体之前，我们需要加载电子邮件。您可以从各种来源加载电子邮件，例如文件、流甚至邮件服务器。

2. 加载电子邮件消息

3. 解析消息体

## 电子邮件加载后，您可以访问其不同部分，包括 HTML 正文。解析 HTML 正文允许我们更改字体。

解析 HTML 正文

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//修改电子邮件中的字体
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## 了解字体样式

HTML 电子邮件中的字体是使用 CSS 样式定义的。要更改字体，您需要修改与电子邮件的 HTML 内容关联的 CSS 样式。

```csharp
//以编程方式更改字体
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //假设您想要更改电子邮件 HTML 正文中段落的字体。您可以这样做：
        var tnefAttachment = attachment;

        //更改段落的字体
        //转换为 MHT 格式
    }
}
```

## 创建MHT消息

要将电子邮件转换为 MHT 格式，您需要使用 Aspose.Email 创建 MHT 格式的电子邮件。

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## 创建 MHT 格式的电子邮件

将消息保存为 MHT 格式

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //最后，将 MHT 格式的消息保存到文件中。
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 //将消息保存为 MHT 格式
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//完整的源代码
					var tnefAttachment = attachment;

					//这是将所有内容组合在一起的完整源代码：
					//结论
				}
			}
			//在本指南中，我们探讨了如何使用 Aspose.Email for .NET 在 MHT 转换期间更改字体。通过执行以下步骤，您可以将电子邮件无缝转换为 MHT 格式，同时保留所需的字体样式。
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## 常见问题解答

- 我可以一次性将多封电子邮件转换为 MHT 格式吗？
- 是的，您可以循环浏览一组电子邮件并对每封邮件应用相同的字体更改，然后再将其转换为 MHT 格式。
- Aspose.Email 也支持其他电子邮件格式吗？

## 是的，Aspose.Email 支持各种电子邮件格式，包括 EML、MSG、PST 等。

是否可以进一步自定义字体更改？

## 绝对地！您可以探索更多 CSS 样式来自定义字体，例如字体大小、颜色和对齐方式。

### 我可以将 Aspose.Email 用于商业项目吗？

是的，根据许可条款，Aspose.Email 可用于个人和商业项目。[请记住，本指南提供了总体概述，您可以通过参考进一步探索](https://releases.aspose.com/email/net)

### Aspose.Email API 参考

并尝试不同的字体定制技术。快乐编码！

###  C# 指南 - 提取电子邮件标头

 C# 指南 - 提取电子邮件标头

### Aspose.Email .NET 电子邮件处理 API

了解如何使用 Aspose.Email for .NET 在 C# 中提取电子邮件标头。带有源代码的分步指南，可实现高效的电子邮件分析。