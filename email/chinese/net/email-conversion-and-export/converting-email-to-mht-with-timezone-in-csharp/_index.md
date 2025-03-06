---
title: 在 C# 中将电子邮件转换为带时区的 MHT
linktitle: 在 C# 中将电子邮件转换为带时区的 MHT
second_title: Aspose.Email .NET 电子邮件处理 API
description: 使用 Aspose.Email for .NET 将电子邮件转换为具有准确时区的 MHT 格式。提供了分步指南和代码示例。
weight: 12
url: /zh/net/email-conversion-and-export/converting-email-to-mht-with-timezone-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中将电子邮件转换为带时区的 MHT


## 电子邮件转换简介 电子邮件到带时区的 MHT

将电子邮件消息转换为各种格式是许多应用程序中的常见要求。在时间和时区信息起着至关重要作用的情况下，确保在转换过程中准确保留此信息非常重要。在本指南中，我们将重点关注将电子邮件转换为 MHT 格式，同时正确处理时区数据。

## 设置您的开发环境

在我们深入编码过程之前，让我们确保您的开发环境已准备好进行操作。确保安装了兼容版本的 Visual Studio，并创建一个新的 C# 项目以开始。

## 安装 Aspose.Email for .NET

Aspose.Email for .NET 是一个功能丰富的库，可以简化与电子邮件相关的任务。要安装它，请按照下列步骤操作：

1. 在 Visual Studio 中打开您的项目。
2. 转到“工具”>“NuGet 包管理器”>“管理解决方案的 NuGet 包”。
3. 搜索“Aspose.Email”并安装该软件包。

## 加载和解析电子邮件消息

在此步骤中，我们将加载并解析要转换的电子邮件。使用以下代码片段作为起点：

```csharp
//添加必要的 using 语句
using Aspose.Email;

//加载电子邮件消息
var message = MailMessage.Load("path/to/your/email.eml");

//现在您可以访问消息属性
var subject = message.Subject;
var sender = message.From.Address;
//...其他属性
```

## 处理时区信息

正确处理时区信息至关重要。以下代码片段演示了如何从电子邮件中提取和管理时区数据：

```csharp
var timezone = message.TimezoneOffset;
var timezoneId = Timezone.GetIdFromOffset(timezone);
var timezoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timezoneId);
//您现在可以使用 timezoneInfo 来处理时区转换
```

## 将电子邮件转换为 MHT 格式

现在到了核心转换步骤。我们将使用 Aspose.Email 执行到 MHT 格式的转换：

```csharp
var mhtOptions = MhtSaveOptions.DefaultMhtml;
var mhtStream = new MemoryStream();
message.Save(mhtStream, mhtOptions);
```

## 保存 MHT 文件

将电子邮件消息转换为 MHT 格式后，是时候将其另存为文件了：

```csharp
using var fileStream = new FileStream("output.mht", FileMode.Create);
mhtStream.Seek(0, SeekOrigin.Begin);
mhtStream.CopyTo(fileStream);
```

## 探索其他定制

Aspose.Email for .NET 提供了各种自定义选项。您可以探索添加附件、修改消息属性等，以满足您的应用程序的需求。

## 使用 Aspose.Email for .NET 的好处

Aspose.Email for .NET 简化了复杂的电子邮件相关任务，使开发人员能够专注于核心功能。它为各种电子邮件格式提供强大的支持，确保准确高效的转换。

## 结论

在本指南中，我们学习了如何使用 Aspose.Email for .NET 将电子邮件消息转换为 MHT 格式，同时处理时区信息。通过执行这些步骤并探索进一步的自定义选项，您可以将电子邮件转换功能无缝集成到您的应用程序中。

## 常见问题解答

### 电子邮件转换期间如何处理附件？

要处理附件，您可以使用`Attachments`的财产`MailMessage`班级。在转换过程中迭代附件并根据需要保存它们。

### 我可以使用 Aspose.Email for .NET 将电子邮件转换为其他格式吗？

是的，Aspose.Email for .NET 支持各种格式，包括 MSG、EML、PST 等。您可以调整提供的代码示例以适合您所需的输出格式。

### 时区信息是否以 MHT 格式保存？

是的，在转换过程中会保留时区信息。通过处理时区偏移并使用适当的`TimeZoneInfo`方法，您可以确保 MHT 文件中准确的时区表示。

### 在哪里可以找到有关 Aspose.Email for .NET 的更多文档和更新？

您可以参考文档以获取全面的信息和更新：[Aspose.Email for .NET API 参考](https://reference.aspose.com/email/net/)

### 如何下载最新版本的 Aspose.Email for .NET？

您可以从发布页面下载最新版本：[下载 .NET 版 Aspose.Email](https://releases.aspose.com/email/net/)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
