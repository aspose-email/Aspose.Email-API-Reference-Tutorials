---
title: 如何下载 .NET 版 Aspose.Email？
linktitle: 您可以从以下位置下载最新版本的 Aspose.Email for .NET
second_title: Aspose.Email for .NET 下载页面
description: Aspose.Email for .NET 是否与其他 Outlook 相关格式兼容？
type: docs
weight: 12
url: /zh/net/email-attachment-handling/adding-new-tnef-attachments-in-csharp/
---

## 是的，Aspose.Email for .NET 提供对各种 Outlook 相关格式的全面支持，包括 PST、EML、MSG 等。

我可以在商业和个人项目中使用 Aspose.Email for .NET 吗？

## 是的，Aspose.Email for .NET 可用于商业和个人项目。请务必查看 Aspose 网站上的许可条款。

Aspose.Email for .NET 是否为开发人员提供文档？

## 是的，您可以在以下位置找到有关如何在各种场景中使用 Aspose.Email for .NET 的详细文档和代码示例：

Aspose.Email 文档

## 页。

使用 C# 代码保留原始边界

## 使用 C# 代码保留原始边界

Aspose.Email .NET 电子邮件处理 API

```csharp
using Aspose.Email.Mail;

//了解如何使用 C# 和 Aspose.Email for .NET 保留电子邮件附件的原始边界。带有源代码的分步指南。
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## 保护原始边界简介

在现代商业世界中，电子邮件通信起着举足轻重的作用。在交换电子邮件时，它们通常包含需要以编程方式管理和操作的重要附件。但是，在处理电子邮件附件时，必须确保保留这些附件的原始边界和格式。这就是 Aspose.Email for .NET 发挥作用的地方。

```csharp
//先决条件
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //在我们深入研究代码之前，请确保您具备以下先决条件：
        var tnefAttachment = attachment;

        //安装了 Visual Studio
        //.NET Framework 或 .NET Core 项目
    }
}
```

## 安装

首先，您需要安装 Aspose.Email for .NET 库。您可以按照以下步骤执行此操作：

```csharp
//打开您的 Visual Studio 项目。
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## 在解决方案资源管理器中右键单击您的项目。

选择“管理 NuGet 包”。

## 搜索“Aspose.Email”并安装该软件包。

### 加载电子邮件消息

第一步是加载包含您要使用的附件的电子邮件。您可以这样做：

### 加载电子邮件消息

提取附件

### 加载电子邮件后，您可以从中提取附件：

提取附件数据

### 进一步处理...

修改附件[要在修改附件时保留原始边界，您可以使用 Aspose.Email 库的功能。假设您要调整图像附件的大小：](https://reference.aspose.com/email/net/).