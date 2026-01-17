---
date: '2026-01-17'
description: 学习如何使用 Aspose.Email for Java 将 MSG 转换为 MHT。本分步教程涵盖加载、保存以及自定义模板，以实现实际场景中的电子邮件转换。
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 使用 Aspose.Email for Java 将 MSG 转换为 MHT 的完整指南
url: /zh/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 将 MSG 转换为 MHT：全面指南

## 介绍

将 **MSG 转换为 MHT** 是在需要归档或以网页友好格式展示 Outlook 邮件时的常见需求。在本教程中，你将看到 Aspose.Email for Java 如何简化此转换过程，让你加载 MAPI（MSG）文件、使用自定义 HTML 模板调整输出，并将其保存为可在浏览器或归档系统中使用的 MHT 文件。

**你将学习的内容：**
- 如何高效加载和解析 MSG 文件。  
- 如何配置 `MhtSaveOptions` 以获得最佳的 MHT 输出。  
- 如何应用自定义模板提升可读性。  
- 在实际场景中，MSG 转换为 MHT 能带来的价值。

让我们准备好环境并深入代码。

## 快速答案
- **“将 MSG 转换为 MHT” 是什么意思？** 它将 Outlook `.msg` 文件转换为网页兼容的 `.mht`（MHTML）格式。  
- **使用的库是什么？** Aspose.Email for Java（aspose email tutorial）。  
- **需要许可证吗？** 免费的 30 天试用可用于评估；生产环境需要许可证。  
- **支持的 Java 版本？** Java 16 或更高（classifier `jdk16`）。  
- **典型使用场景？** 为合规性归档邮件或在不使用 Outlook 的情况下在浏览器中显示邮件。

## 什么是 “将 MSG 转换为 MHT”？
转换过程读取二进制 Outlook 消息（`.msg`），并将其内容、附件和元数据重新写入单个基于 HTML 的 MHTML 文件（`.mht`）。这种单文件格式在保留原始布局的同时，可在任何现代浏览器中查看。

## 为什么使用 Aspose.Email for Java？
- **功能完整的 API：** 处理所有 MAPI 属性、附件和嵌入对象。  
- **无需 Outlook 依赖：** 可在任何服务器端 Java 环境中运行。  
- **可自定义模板：** 根据品牌或报告标准定制 HTML 输出。  
- **高性能：** 针对大批量和异步处理进行优化。

## 前置条件

- **Aspose.Email 库：** 版本 25.4 或更高（classifier `jdk16`）。  
- **Java 开发环境：** 已安装 Maven 用于依赖管理。  
- **基础 Java 知识：** 熟悉文件 I/O 和 Maven 项目。

## 设置 Aspose.Email for Java

要将 Aspose.Email 添加到你的 Maven 项目中，请在 `pom.xml` 中加入以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 获取许可证（aspose email tutorial）

Aspose.Email 是商业产品，但你可以先使用 **免费试用**：

- **免费试用：** 完整功能，30 天。  
- **临时许可证：** 如有需要可延长评估期。  
- **购买：** 获取永久许可证用于生产环境。

### 基本初始化

在添加 Maven 依赖后，在 Java 代码中初始化库：

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## 使用 Aspose.Email for Java 将 MSG 转换为 MHT 的步骤

### 加载 MSG 文件

**步骤 1 – 导入所需类**

```java
import com.aspose.email.MapiMessage;
```

**步骤 2 – 从磁盘加载消息**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

`MapiMessage.fromFile()` 方法读取 `.msg` 文件并创建可操作的 `MapiMessage` 对象。

### 配置 MHT 保存选项

**步骤 1 – 导入保存选项类**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**步骤 2 – 设置选项**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` 确保任务特定字段被包含，`WriteHeader` 将标准邮件头写入 MHT 输出。

### 定义自定义 HTML 模板（可选）

**步骤 1 – 导入模板枚举**

```java
import com.aspose.email.MhtTemplateName;
```

**步骤 2 – 自定义模板**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

这些模板让你能够控制每个任务属性在最终 MHT 文件中的呈现方式，使输出对终端用户更清晰。

### 将消息保存为 MHT 文件

**步骤 1 – 定义输出目录**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**步骤 2 – 执行保存操作**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

`save` 方法将自定义的 MHT 文件写入磁盘。运行代码前请确认 `outputDir` 路径已存在。

## 实际应用（为何要将 MSG 转换为 MHT？）

- **归档：** 将邮件存储为单个可移植格式，浏览器无需 Outlook 即可渲染。  
- **迁移：** 将旧版 Outlook 档案迁移至基于 Web 的邮件平台。  
- **报告与分析：** 使用 HTML 解析器解析 MHT 文件以进行数据提取和商业智能。  
- **法律合规：** 以防篡改的格式保留原始邮件内容和元数据。

## 性能考虑

- **批量处理：** 处理成千上万的 MSG 文件时，分批进行以避免内存峰值。  
- **异步执行：** 利用 Java 的 `CompletableFuture` 或执行器服务并行转换文件。  
- **资源清理：** 若打开了 Aspose API 之外的自定义流，请显式关闭。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| **`msg.save` 抛出 NullPointerException** | 输出目录不存在 | 创建目录或使用 `Files.createDirectories(Paths.get(outputDir));` |
| **MHT 中缺少附件** | `MhtSaveOptions` 未设置嵌入资源 | 使用 `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **日期格式不正确** | 区域设置不同 | 调整 `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## 常见问答

**问：MSG 与 MHT 有何区别？**  
答：MSG 是 Outlook 的专有二进制格式，存储邮件、附件和元数据。MHT（MHTML）是基于 HTML 的单文件格式，将邮件正文、图片和 CSS 打包，使其可在任何浏览器中查看。

**问：我可以转换其他 MAPI 项目，如约会或联系人吗？**  
答：可以。Aspose.Email 支持将约会、联系人和任务等转换为 MHT，只需使用相应的 `Mapi*` 类并调整模板名称。

**问：转换过程需要联网吗？**  
答：不需要。所有处理均在本地 Java 运行时完成；仅在许可证激活时可能会短暂访问 Aspose 服务器。

**问：该转换是线程安全的吗？**  
答：API 对只读操作是线程安全的。并发转换大量文件时，请为每个线程实例化独立的 `MapiMessage` 对象。

**问：Aspose.Email 能处理多大的 MSG 文件？**  
答：库可处理数百兆字节的文件，但仍需监控 JVM 堆大小，并考虑对大附件进行流式处理。

## 结论

现在，你已经掌握了使用 Aspose.Email for Java **将 MSG 转换为 MHT** 的完整、可用于生产的工作流。通过自定义模板，你可以将 HTML 输出调整为符合组织品牌或报告标准，而库则负责解析 Outlook 二进制格式的繁重工作。

**后续步骤：**  
- 试验不同的 `MhtTemplateName` 值，以为其他 MAPI 项目类型设置样式。  
- 将转换集成到批处理作业或 REST 服务，实现按需处理。  
- 探索 Aspose.Email 的其他功能，如 PST 处理、邮件发送和 MIME 解析。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-17  
**测试环境：** Aspose.Email for Java 25.4（classifier `jdk16`）  
**作者：** Aspose