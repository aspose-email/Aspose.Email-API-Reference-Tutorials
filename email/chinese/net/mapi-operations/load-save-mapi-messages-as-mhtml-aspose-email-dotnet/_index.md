---
"date": "2025-05-30"
"description": "学习如何使用 Aspose.Email for .NET 以编程方式从文件加载 MAPI 消息并将其转换为 MHT 格式。请遵循本分步指南。"
"title": "如何使用 Aspose.Email for .NET 将 MAPI 消息加载并保存为 MHTML"
"url": "/zh/net/mapi-operations/load-save-mapi-messages-as-mhtml-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for .NET 将 MAPI 消息加载并保存为 MHTML

## 介绍
以编程方式管理电子邮件消息可能颇具挑战性，尤其是像 MAPI 这样复杂的格式。然而，使用 Aspose.Email for .NET，您可以轻松地从文件加载这些消息，并将其保存为 Web 友好的 MHT（MIME HTML）格式。

本指南将指导您使用 Aspose.Email for .NET 将 MAPI 邮件转换为 MHTML 格式。您将学习如何配置保存选项并高效地执行文件操作。

**您将学到什么：**
- 在您的开发环境中设置 Aspose.Email for .NET。
- 使用加载 MAPI 消息 `MapiMessage` 班级。
- 配置自定义 HTML 模板以 MHT 格式保存。
- 使用定制选项将 MAPI 消息保存为 MHTML 文件。

## 先决条件

### 所需的库、版本和依赖项
要遵循本教程，您需要：
- **Aspose.Email for .NET**：确保您已安装 22.10 或更高版本。
- **.NET Framework 或 .NET Core/5+/6+**：取决于您的项目设置。

### 环境设置要求
确保您的开发环境支持 .NET 项目。您可以使用 Visual Studio、带有 C# 扩展的 VS Code，或任何支持 .NET 开发的 IDE。

### 知识前提
基本了解：
- C# 编程。
- 在 .NET 中处理文件和目录。
- 与第三方库合作。

## 设置 Aspose.Email for .NET
Aspose.Email 的使用非常简单。安装方法如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用包管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**使用 NuGet 包管理器 UI：**
1. 打开 NuGet 包管理器。
2. 搜索“Aspose.Email”并安装最新版本。

### 许可证获取
要开始使用 Aspose.Email，您可以：
- **免费试用**：下载试用许可证来测试所有功能。
- **临时执照**：获取临时许可证，以访问全功能，不受评估限制。
- **购买**：如果您准备将其集成到您的生产环境中，请购买订阅。

安装完成后，通过在项目中包含必要的命名空间来初始化库：
```csharp
using Aspose.Email;
using System;
```

## 实施指南

### 功能 1：从文件加载 MAPI 消息

#### 概述
此功能演示如何使用 Aspose.Email 从指定文件路径加载 MAPI 消息，这对于处理存储为 MAPI 消息的电子邮件至关重要。

#### 实施步骤
**步骤 1**：定义目录路径
代替 `"YOUR_DOCUMENT_DIRECTORY"` 与您的实际目录 `MapiTask.msg` 文件所在位置。
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 替换为您的文档目录路径
```
**第 2 步**：加载 MAPI 消息
使用 `MapiMessage.FromFile()` 方法来加载消息，创建一个 `MapiMessage` 来自它的对象。
```csharp
// 从指定文件加载 MapiMessage
dynamic msg = MapiMessage.FromFile(dataDir + "MapiTask.msg");
```

### 功能2：配置MHT保存选项

#### 概述
配置保存选项可让您自定义 MAPI 邮件以 MHTML 格式保存的方式。此步骤涉及设置模板和格式选项。

#### 实施步骤
**步骤 1**：初始化 `MhtSaveOptions`
设置默认的 MHTML 保存选项，该选项将针对自定义输出进行修改。
```csharp
dynamic opt = SaveOptions.DefaultMhtml;
```
**第 2 步**：设置格式选项
在保存的 MHTML 文件中启用任务字段和标题信息的渲染。
```csharp
opt.MhtFormatOptions = MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader;
```
**步骤3**：自定义模板
为各种任务属性定义 HTML 模板以控制它们在输出文件中的外观。
```csharp
// 清除现有模板
opt.FormatTemplates.Clear();

// 为特定任务属性添加自定义 HTML 模板
opt.FormatTemplates.Add(MhtTemplateName.Task.Subject, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.ActualWork, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.TotalWork, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Status, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Owner, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Priority, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

### 功能 3：将 MAPI 消息保存为 MHTML 文件

#### 概述
配置完成后，将加载的 MAPI 消息保存为 MHTML 文件。此步骤将使用之前设置的选项完成转换过程。

#### 实施步骤
**步骤 1**：定义输出文件路径
指定要保存转换后的 MHTML 文件的位置。
```csharp
string outputFile = dataDir + "MapiTask_out.mht";
```
**第 2 步**：保存消息
使用 `Save()` 方法并使用您配置的选项将消息转换并存储为 MHTML 格式。
```csharp
// 使用先前配置的选项将消息保存到 MHT 文件
dynamic msg.Save(outputFile, opt);
```

## 实际应用
1. **电子邮件归档**：将来自旧系统的电子邮件转换为适合网络的 MHTML 格式，以进行存档。
2. **与任务管理系统集成**：转换与任务相关的 MAPI 消息以用于支持 HTML 格式的现代项目管理应用程序。
3. **记录和共享**：以可访问的格式生成可共享的电子邮件任务报告，非常适合文档或协作。

## 性能考虑
### 优化性能
- 仅加载必要的文件以减少内存使用量。
- 尽可能使用异步方法来避免阻塞操作。

### 资源使用指南
- 处理大量消息时监控应用程序的内存占用。
- 使用后妥善处理物品以释放资源。

### 使用 Aspose.Email 进行 .NET 内存管理的最佳实践
- 利用 `using` 语句来自动处理对象。
- 定期更新 Aspose.Email 以利用新版本中的改进和优化。

## 结论
在本教程中，您学习了如何使用 Aspose.Email for .NET 从文件加载 MAPI 邮件并将其保存为 MHTML。现在，您已掌握了将这些功能应用到应用程序中的知识，从而增强电子邮件管理能力。

**后续步骤：**
- 尝试不同的 `MhtSaveOptions` 设置。
- 探索 Aspose.Email for .NET 提供的其他功能。

## 常见问题解答部分
1. **我可以免费使用 Aspose.Email 吗？**
   - 是的，您可以从 30 天的免费试用许可证开始，无限制地测试全部功能。
2. **除了 MAPI 和 MHTML 之外，Aspose.Email 还支持哪些格式？**
   - 它支持各种电子邮件格式，包括 EML、MSG、PST 等。
3. **如何在 Aspose.Email 中处理大文件？**
   - 使用流式传输等节省内存的技术来读取/写入大文件。
4. **我可以将此功能集成到 Web 应用程序中吗？**
   - 当然！此功能非常适合需要电子邮件管理功能的 Web 应用程序。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}