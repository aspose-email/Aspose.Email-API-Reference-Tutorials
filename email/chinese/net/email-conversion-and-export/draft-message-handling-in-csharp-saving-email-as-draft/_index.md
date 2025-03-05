---
title: C# 中的草稿消息处理 - 将电子邮件保存为草稿
linktitle: C# 中的草稿消息处理 - 将电子邮件保存为草稿
second_title: Aspose.Email .NET 电子邮件处理 API
description: 了解如何使用 Aspose.Email for .NET 在 C# 中实现草稿电子邮件处理。无缝创建、编辑和保存草稿。
type: docs
weight: 17
url: /zh/net/email-conversion-and-export/draft-message-handling-in-csharp-saving-email-as-draft/
---

## 介绍

草稿消息处理是电子邮件客户端的一项重要功能。用户通常需要能够开始撰写电子邮件、将其保存为草稿，并稍后返回以进行进一步编辑或最终发送。本文演示了如何使用 Aspose.Email for .NET 库实现此功能。

## 先决条件

在我们深入实施之前，请确保您具备以下先决条件：

- Visual Studio（或任何 C# 开发环境）
- Aspose.Email for .NET 库

您可以从以下位置下载 Aspose.Email 库[这里](https://releases.aspose.com/email/net).

## 设置项目

1. 在您的开发环境中创建一个新的 C# 项目。
2. 添加对项目中 Aspose.Email DLL 的引用。

## 创建电子邮件草稿

要创建草稿消息，请执行以下步骤：

## 添加收件人和主题

```csharp
//创建一个新的 MailMessage 实例
MailMessage draft = new MailMessage();

//添加收件人
draft.To.Add("recipient@example.com");
draft.Cc.Add("cc@example.com");
draft.Bcc.Add("bcc@example.com");

//设置电子邮件主题
draft.Subject = "Draft Email Demo";
```

## 撰写电子邮件正文

```csharp
//设置电子邮件正文
draft.Body = new TextBody("Hello, this is a draft email.");
```

## 另存为草稿

```csharp
//将电子邮件另存为草稿
draft.Save("draft.eml", SaveOptions.DefaultEml);
```

## 加载和编辑草稿

要加载和编辑草稿消息，请按照下列步骤操作：

```csharp
//加载电子邮件草稿
MailMessage loadedDraft = MailMessage.Load("draft.eml");

//编辑收件人
loadedDraft.To.Clear();
loadedDraft.To.Add("newrecipient@example.com");

//编辑电子邮件正文
loadedDraft.Body = new TextBody("Updated draft content.");

//保存更改
loadedDraft.Save("updated_draft.eml", SaveOptions.DefaultEml);
```

## 结论

在本文中，我们探讨了如何使用 Aspose.Email for .NET 库在 C# 中处理草稿消息。我们学习了如何创建、编辑和保存草稿电子邮件，为用户在撰写邮件时提供无缝体验。通过遵循本指南中概述的步骤，您可以通过草稿消息功能增强电子邮件客户端应用程序。

## 常见问题解答

### 如何下载 Aspose.Email for .NET 库？

您可以从以下位置下载 Aspose.Email for .NET 库：[这里](https://releases.aspose.com/email/net).

### 我可以编辑已保存草稿的收件人和主题吗？

是的，您可以加载已保存的草稿，编辑其收件人、主题和内容，然后将更改另存为更新的草稿。

### 电子邮件草稿是否以特定格式保存？

是的，电子邮件草稿以 EML 格式保存，这是广泛使用的电子邮件格式。

### 我可以将草稿消息处理集成到我现有的电子邮件应用程序中吗？

当然，通过遵循本指南中提供的步骤，您可以将草稿消息处理无缝集成到现有的电子邮件客户端应用程序中。

### Aspose.Email 库是否支持其他电子邮件相关功能？

是的，Aspose.Email 库提供了广泛的用于处理电子邮件的功能，包括发送、接收和操作电子邮件和附件。您可以参考文档了解更多详细信息：[这里](https://reference.aspose.com)