---
"description": "使用 Aspose.Email for .NET 将电子邮件转换为具有准确时区的 MHT 格式。提供分步指南和代码示例。"
"linktitle": "使用 C# 将电子邮件转换为带时区的 MHT"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "使用 C# 将电子邮件转换为带时区的 MHT"
"url": "/zh/net/email-conversion-and-export/converting-email-to-mht-with-timezone-in-csharp/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 将电子邮件转换为带时区的 MHT


## 电子邮件转换简介 使用时区将电子邮件转换为 MHT

将电子邮件转换为各种格式是许多应用程序的常见需求。在时间和时区信息至关重要的情况下，确保在转换过程中准确保留这些信息至关重要。在本指南中，我们将重点介绍如何将电子邮件转换为 MHT 格式，同时正确处理时区数据。

## 设置您的开发环境

在深入编码过程之前，请确保您的开发环境已准备就绪。确保您已安装兼容版本的 Visual Studio，并创建一个新的 C# 项目来开始。

## 安装 Aspose.Email for .NET

Aspose.Email for .NET 是一个功能丰富的库，可简化与电子邮件相关的任务。要安装它，请按照以下步骤操作：

1. 在 Visual Studio 中打开您的项目。
2. 转到“工具”>“NuGet 包管理器”>“管理解决方案的 NuGet 包”。
3. 搜索“Aspose.Email”并安装该包。

## 加载和解析电子邮件消息

在此步骤中，我们将加载并解析要转换的电子邮件。使用以下代码片段作为起点：

```csharp
// 添加必要的 using 语句
using Aspose.Email;

// 加载电子邮件消息
var message = MailMessage.Load("path/to/your/email.eml");

// 现在您可以访问消息属性
var subject = message.Subject;
var sender = message.From.Address;
// ...其他属性
```

## 处理时区信息

正确处理时区信息至关重要。以下代码片段演示了如何从电子邮件中提取和管理时区数据：

```csharp
var timezone = message.TimezoneOffset;
var timezoneId = Timezone.GetIdFromOffset(timezone);
var timezoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timezoneId);
// 您现在可以使用 timezoneInfo 来处理时区转换
```

## 将电子邮件转换为 MHT 格式

现在到了核心的转换步骤。我们将使用 Aspose.Email 执行到 MHT 格式的转换：

```csharp
var mhtOptions = MhtSaveOptions.DefaultMhtml;
var mhtStream = new MemoryStream();
message.Save(mhtStream, mhtOptions);
```

## 保存MHT文件

将电子邮件转换为 MHT 格式后，就可以将其保存为文件了：

```csharp
using var fileStream = new FileStream("output.mht", FileMode.Create);
mhtStream.Seek(0, SeekOrigin.Begin);
mhtStream.CopyTo(fileStream);
```

## 探索其他自定义

Aspose.Email for .NET 提供多种自定义选项。您可以探索添加附件、修改邮件属性等功能，以满足您的应用程序需求。

## 使用 Aspose.Email for .NET 的好处

Aspose.Email for .NET 简化了复杂的电子邮件相关任务，使开发人员能够专注于核心功能。它为各种电子邮件格式提供强大的支持，确保转换准确高效。

## 结论

在本指南中，我们学习了如何使用 Aspose.Email for .NET 将电子邮件转换为 MHT 格式，并处理时区信息。通过遵循这些步骤并探索更多自定义选项，您可以将电子邮件转换功能无缝集成到您的应用程序中。

## 常见问题解答

### 如何在电子邮件转换期间处理附件？

要处理附件，您可以使用 `Attachments` 的财产 `MailMessage` 类。在转换过程中，根据需要遍历附件并保存它们。

### 我可以使用 Aspose.Email for .NET 将电子邮件转换为其他格式吗？

是的，Aspose.Email for .NET 支持多种格式，包括 MSG、EML、PST 等。您可以根据所需的输出格式调整提供的代码示例。

### 时区信息是否以 MHT 格式保存？

是的，转换过程中会保留时区信息。通过处理时区偏移并使用适当的 `TimeZoneInfo` 方法，您可以确保 MHT 文件中的时区表示准确。

### 在哪里可以找到有关 Aspose.Email for .NET 的更多文档和更新？

您可以参考文档来获取全面的信息和更新： [Aspose.Email for .NET API 参考](https://reference.aspose.com/email/net/)

### 如何下载最新版本的 Aspose.Email for .NET？

您可以从发布页面下载最新版本： [下载 Aspose.Email for .NET](https://releases.aspose.com/email/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}