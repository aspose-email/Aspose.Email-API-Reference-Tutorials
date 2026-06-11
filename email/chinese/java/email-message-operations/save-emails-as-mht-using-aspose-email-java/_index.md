---
date: '2026-03-02'
description: 学习如何使用 Maven Aspose.Email for Java 将电子邮件保存为 MHT 文件。本分步指南涵盖设置、自定义模板以及电子邮件到
  MHT 的转换。
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: Maven Aspose.Email for Java：将电子邮件保存为 MHT 文件
url: /zh/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose.Email for Java: 如何将电子邮件保存为 MHT 文件

## 介绍

有效管理电子邮件数据可能具有挑战性，尤其是在共享和归档方面。在本指南中，我们将展示如何使用 **Maven Aspose.Email for Java** **保存 MHT** 文件，以便您能够使用自定义模板将电子邮件转换为 MHT 并保持日历事件完整。您将获得一个可直接运行的解决方案，适用于任何 Java 16+ 环境。

## 快速答疑
- **我需要哪个库？** Maven Aspose.Email for Java (v25.4+)。  
- **生成什么格式？** MHT（MHTML）文件，捆绑 HTML、图像和日历数据。  
- **我可以自定义标题吗？** 可以 – 使用 `MhtFormatOptions` 和模板字符串。  
- **我需要许可证吗？** 免费试用可用于评估；生产环境需要永久许可证。  
- **需要哪个 Java 版本？** JDK 16 或更高版本。

## 什么是 Maven Aspose.Email for Java？
Maven Aspose.Email for Java 是一个强大的 API，允许您直接在 Java 代码中创建、读取、转换和操作电子邮件消息。它支持多种格式，包括 MSG、EML 和 MHT，使其非常适合 **java email conversion** 任务。

## 为什么将电子邮件转换为 MHT？
- **网页友好**：MHT 文件可在浏览器中渲染，无需外部资源。  
- **归档稳定性**：所有资源均嵌入，保持原始外观。  
- **日历支持**：您可以使用自定义模板渲染循环事件。  

## 前提条件
- **Aspose.Email for Java**（Maven 构件 `com.aspose:aspose-email:25.4`，带 `jdk16` 分类器）。  
- **Maven** 已在您的机器上安装并配置。  
- **JDK 16+**（该库面向 Java 16）。  
- 基础 Java 知识（文件处理、Maven 依赖）。

## 设置 Aspose.Email for Java

### Maven 依赖

在您的 `pom.xml` 文件中添加以下依赖：

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取

Aspose 提供免费试用以探索其功能，同时提供购买许可证或获取临时许可证的选项。

1. **免费试用**：从 [Releases](https://releases.aspose.com/email/java/) 下载，无限制地探索功能。  
2. **临时许可证**：通过 [Temporary License Page](https://purchase.aspose.com/temporary-license/) 请求，获取完整功能版本。  
3. **购买**：如果 Aspose.Email 符合您的长期项目需求，请考虑购买。

### 基本初始化

安装完成后，在您的 Java 应用程序中初始化库：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

完成上述步骤后，您即可使用 Aspose.Email 的功能高效处理电子邮件。

## 实施指南

### 功能 1：加载 MailMessage

#### 概述
加载电子邮件消息是处理并将其保存为 MHT 文件的第一步。这里演示如何使用 `MailMessage` 加载 `.msg` 文件。

#### 步骤说明

**导入所需类**

```java
import com.aspose.email.MailMessage;
```

**从文件加载电子邮件**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

此代码段加载位于您指定目录中的电子邮件消息。

### 功能 2：配置 MhtSaveOptions

#### 概述
配置 `MhtSaveOptions` 对于定义电子邮件如何保存为 MHT 文件至关重要，包括日历事件的自定义格式化。

#### 步骤说明

**导入所需类**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**设置保存选项和模板**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

此配置在 MHT 输出中设置标题和日历事件的渲染。

### 功能 3：将 MailMessage 保存为 MHT

#### 概述
最后一步是使用指定的选项将配置好的 `MailMessage` 保存为 MHT 文件。

#### 步骤说明

**导入所需类**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**保存电子邮件消息**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

此命令将电子邮件写入 MHT 文件，准备好用于共享或归档。

## 实际应用
- **电子邮件归档**：将重要电子邮件转换并存储为网页友好格式。  
- **法律文档**：在需要保留电子邮件细节的法律证据中使用 MHT 文件。  
- **跨平台共享**：在不同平台之间共享电子邮件，无兼容性问题。  

将其与其他系统（如 CRM 或项目管理工具）集成，可通过将关键电子邮件数据直接嵌入工作流来提升协作。

## 性能考虑
为确保最佳性能：
- 在处理大量电子邮件时有效管理内存使用。  
- 优化文件 I/O 操作，防止保存过程中的瓶颈。  

遵循 Java 内存管理最佳实践将保持应用程序的响应性。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **NullPointerException on `msg.save`** | 输出路径不正确 | 确认 `YOUR_OUTPUT_DIRECTORY` 存在且可写。 |
| **Missing images in MHT** | `MhtFormatOptions` 未设置为嵌入资源 | 在选项标志中添加 `MhtFormatOptions.EmbedResources`。 |
| **Calendar events not rendered** | 未包含 `RenderCalendarEvent` 标志 | 确保 `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## 常见问题

**Q: 保存电子邮件为 MHT 时如何处理附件？**  
A: 确保已配置 `MhtSaveOptions` 以包含附件处理逻辑。该库支持将附件嵌入 MHT 文件。

**Q: 我可以自定义输出 MHT 文件中的电子邮件标题吗？**  
A: 可以，使用 `MhtFormatOptions.WriteHeader` 并按照教程中所示为各标题字段定义自定义模板。

**Q: 使用 Aspose.Email Java 的系统要求是什么？**  
A: 需要 JDK 16 或更高版本。该库可与大多数支持 Maven 项目的现代 IDE 无缝配合。

**Q: 能否仅保存电子邮件消息的特定部分？**  
A: 虽然 MHT 格式通常包含完整消息，但您可以使用 `MailMessage` 的属性有选择地处理和包含内容。

**Q: 如何排查电子邮件加载或保存时的问题？**  
A: 检查文件路径是否正确，确保项目中正确设置库，并参考 Aspose.Email 的 [support forum](https://forum.aspose.com/c/email/10) 获取帮助。

**Q: 该库是否支持将其他格式（EML、MSG）转换为 MHT？**  
A: 当然。`MailMessage.load` 可以读取 EML、MSG 以及其他格式，随后您可以使用相同的选项将其保存为 MHT。

## 资源
- **文档**：深入了解所有功能，请访问 [Aspose Email Java Documentation](https://reference.aspose.com/email/java/)。  
- **下载**：通过从 [Releases](https://releases.aspose.com/email/java/) 下载，开始免费试用。  
- **购买**：在 [Official Purchase Page](https://purchase.aspose.com/buy) 探索长期使用的购买选项。  
- **免费试用和临时许可证**：通过以下链接在免费试用期间访问完整功能或获取临时许可证：  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

立即探索、实现并转变您的电子邮件处理方式，使用 Aspose.Email for Java！

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
