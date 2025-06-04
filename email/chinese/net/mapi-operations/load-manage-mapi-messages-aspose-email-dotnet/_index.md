---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 加载和管理 MAPI 邮件。本指南内容全面，涵盖加载 MAPI 邮件、创建笔记以及管理 PST 文件。"
"title": "使用 Aspose.Email for .NET 加载和管理 MAPI 消息——综合指南"
"url": "/zh/net/mapi-operations/load-manage-mapi-messages-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for .NET 加载和管理 MAPI 消息：综合指南

## 介绍

使用 Aspose.Email for .NET，您可以无缝地将电子邮件功能集成到您的 .NET 应用程序中。这个强大的库以编程方式简化了 Microsoft Outlook 邮件的管理。无论您是开发需要处理电子邮件的应用程序，还是在企业环境中自动执行任务，本指南都能为您提供高效入门的见解。

**您将学到什么：**
- 如何从文件加载 MAPI 消息
- 以编程方式创建和自定义笔记
- 有效管理个人存储文件 (PST)

在开始编码之前，让我们确保您的环境已准备好必要的依赖项。

## 先决条件

要遵循本教程，请确保您具有以下设置：

### 所需的库、版本和依赖项
- **Aspose.Email for .NET**：确保与项目的目标框架兼容。

### 环境设置要求
- 在您的机器上安装兼容版本的 .NET SDK。
- 使用文本编辑器或支持 C# 开发的 IDE（如 Visual Studio）。

### 知识前提
- 对 C# 编程有基本的了解。
- 熟悉电子邮件概念和 MAPI 消息是有益的，但不是必需的。

## 设置 Aspose.Email for .NET

首先，将 Aspose.Email 库添加到您的项目中。操作如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用包管理器：**
```powershell
Install-Package Aspose.Email
```

**通过 NuGet 包管理器 UI：**
搜索“Aspose.Email”并安装最新版本。

### 许可证获取步骤
您可以先免费试用，或获取临时许可证来探索更多功能：
- **免费试用**： [下载](https://releases.aspose.com/email/net/)
- **临时执照**：可在 Aspose 网站上获取，以进行扩展访问。
- **购买**：完整许可选项可在 [Aspose 购买](https://purchase。aspose.com/buy).

**基本初始化和设置**
确保您的项目引用了必要的命名空间：
```csharp
using System;
using Aspose.Email.Mapi;
```

## 实施指南

我们将把实现分为两个主要功能：加载 MAPI 消息和管理 PST 文件。

### 功能1：加载MAPI消息

#### 概述
此功能演示了如何从文件加载 MAPI 消息，这对于处理应用程序中已保存的电子邮件消息或注释至关重要。

#### 实施步骤

**步骤 1：加载 MAPI 消息**
指定你的 `Note.msg` 文件的位置并使用 Aspose.Email 加载它：
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
MapiMessage mess = MapiMessage.FromFile(dataDir + "Note.msg");
```

**第 2 步：创建和自定义注释**
将加载的消息转换为具有不同属性的多个注释：
```csharp
// 创建黄色注释
MapiNote note1 = (MapiNote)mess.ToMapiMessageItem();
note1.Subject = "Yellow color note";
note1.Body = "This is a yellow color note";

// 创建粉色笔记
MapiNote note2 = (MapiNote)mess.ToMapiMessageItem();
note2.Subject = "Pink color note";
note2.Body = "This is a pink color note";
note2.Color = NoteColor.Pink;

// 用维度创建蓝色音符
MapiNote note3 = (MapiNote)mess.ToMapiMessageItem();
note3.Subject = "Blue color note";
note3.Body = "This is a blue color note";
note3.Color = NoteColor.Blue;
note3.Height = 500;
note3.Width = 500;
```

### 功能2：创建和管理个人存储文件（PST）

#### 概述
了解如何创建 PST 文件、添加文件夹以及插入 MAPI 消息。这对于需要在本地存储电子邮件的应用程序至关重要。

#### 实施步骤

**步骤 1：设置输出路径**
定义输出 PST 文件的保存位置：
```csharp
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\AddMapiNoteToPST_out.pst";

// 如果存在文件则删除，以确保不存在文件冲突。
if (File.Exists(outputPath))
{
    File.Delete(outputPath);
}
```

**步骤 2：创建并组织 PST**
初始化新的 PST 并创建文件夹：
```csharp
using (PersonalStorage personalStorage = PersonalStorage.Create(outputPath, FileFormatVersion.Unicode))
{
    // 创建一个“Notes”文件夹来存储您的笔记。
    FolderInfo notesFolder = personalStorage.CreatePredefinedFolder("Notes\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}