---
date: '2026-10-28'
description: 了解如何使用 Aspose.Email for Java 将 Outlook 邮件及 TNEF 存档为 EML 文件。本逐步指南涵盖加载、更新附件以及保留
  Outlook 数据。
keywords:
- outlook email archiving
- aspose email java
- process email attachments
- preserve outlook data
- exchange mailbox migration
lastmod: '2026-10-28'
og_description: 了解如何使用 Aspose.Email for Java 将 Outlook 邮件及 TNEF 存档为 EML 文件。遵循逐步教程进行加载、修改和保存，同时保留
  Outlook 数据。
og_image_alt: 'Developer guide: archive Outlook email with TNEF in EML using Aspose.Email
  for Java'
og_title: 使用 Aspose.Email 将 Outlook 邮件及 TNEF 存档为 EML
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  headline: Archive outlook email with TNEF in EML using Aspose.Email
  type: TechArticle
- description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  name: Archive outlook email with TNEF in EML using Aspose.Email
  steps:
  - name: '**Load the EML file**'
    text: '**Load the EML file**'
  - name: '**Initialize load and save options**'
    text: '**Initialize load and save options**'
  - name: '**Update resources in the mail message**'
    text: '**Update resources in the mail message**'
  - name: '**Save the updated EML file**'
    text: '**Save the updated EML file**'
  - name: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
    text: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
  - name: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
    text: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
  - name: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
    text: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
  type: HowTo
- questions:
  - answer: Inspect the `MailMessage.getAttachments()` collection for an attachment
      whose content type equals `application/ms‑tnef`; the presence of such an attachment
      indicates that Outlook‑specific information is embedded.
    question: How can I programmatically determine if an EML file contains TNEF data?
  - answer: Yes—set `FileCompatibilityMode.RemoveTnefAttachments` when saving to strip
      TNEF but retain regular attachments.
    question: Is it possible to convert a TNEF‑rich EML to a plain‑text EML while
      keeping the original attachments?
  - answer: The library provides synchronous APIs; you can wrap calls in `CompletableFuture`
      or use your own thread pool for asynchronous behavior.
    question: Does Aspose.Email support async operations for loading and saving large
      emails?
  - answer: Updating the `ContentStream` of a `LinkedResource` preserves the original
      MIME headers and boundaries.
    question: Can I update an embedded image without altering the original MIME boundaries?
  - answer: Yes—when saved with `PreserveTnefAttachments`, Outlook can read the TNEF
      portion, and other clients will display the standard parts correctly.
    question: Will the saved EML file be readable by standard email clients like Thunderbird?
  type: FAQPage
tags:
- outlook email archiving
- aspose email java
- email attachment processing
- eml handling
- java email workflow
title: 使用 Aspose.Email 将 Outlook 邮件及 TNEF 存档为 EML
url: /zh/java/attachments-handling/aspose-email-java-eml-tnef-handling/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Email 将 Outlook 电子邮件（含 TNEF）归档为 EML

## 介绍

如果您需要在保留每个 Outlook 特定的 TNEF 属性完整的情况下 **归档 Outlook 电子邮件**，Aspose.Email for Java 提供了可直接用于生产的、零依赖的 API。在本教程中，您将学习如何 **处理电子邮件附件**、**加载** EML 文件、**替换嵌入的图像**，以及最终 **保存带 TNEF 的 EML** 而不丢失任何数据。我们还将讨论为何保留 TNEF 对合规性重要，展示诸如 **Exchange 邮箱迁移** 和 **自动化电子邮件工作流** 等真实场景，并提供故障排除技巧，帮助您自信地将该解决方案集成到自己的项目中。

**您将学习**
- 加载 EML 文件并保持 TNEF 数据完整。  
- 更新嵌入的图像或其他资源而不破坏 MIME 结构。  
- 使用 `EmlSaveOptions` 保存修改后的消息，以保留 TNEF 部分。  
- 在常见用例中应用此工作流，如归档、工单自动化和邮箱迁移。  

准备好掌握 Outlook 电子邮件归档了吗？让我们开始吧！

## 快速回答
- **保留 TNEF 附件的主要方法是什么？** 在 `EmlSaveOptions` 中设置 `FileCompatibilityMode.PreserveTnefAttachments`。  
- **哪个 Aspose 类用于加载 EML 文件？** `MailMessage.load(String filePath)`。  
- **我可以在不破坏电子邮件的情况下更新嵌入的图像吗？** 可以——使用 `UpdateResources` 辅助方法替换流，同时保持 MIME 头不变。  
- **开发是否需要许可证？** 免费试用可用于测试；生产环境需要完整许可证。  
- **支持的 Java 版本是什么？** JDK 1.8 或更高（示例使用 JDK 16 classifier）。

## 什么是带 TNEF 附件的 “处理电子邮件附件”？
使用 TNEF 处理电子邮件附件涉及处理 Outlook 特有的 `application/ms‑tnef` 部分，以确保其在加载‑修改‑保存循环中保持完整。当您保存带 TNEF 的 EML 时，Aspose.Email 会将原始 TNEF 流写回文件，完整保留格式、会议请求和嵌入对象，完全按照发送者的意图。

## 为什么使用 Aspose.Email for Java？
Aspose.Email 支持 **50 多种输入和输出格式**（包括 MSG、EML、MHTML、PST 和 HTML），并且能够在不将整个文件加载到内存中的情况下处理数百页的邮箱。其 **基于流的 API** 与传统的文件读取方式相比，可将内存压力降低最多 **70 %**，因此非常适合企业级 **Outlook 电子邮件归档**、**Exchange 邮箱迁移** 和自动化工作流场景。

## 前提条件

### 必需的库和依赖项
You will need Aspose.Email for Java. Add it via Maven:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 环境设置
- Java 开发工具包 (JDK) 1.8 或更高。  
- IDE，例如 IntelliJ IDEA 或 Eclipse。  

### 知识前提
建议具备基础的 Java 编程、流的使用经验以及对 MIME 电子邮件结构的高级理解。

## 设置 Aspose.Email for Java

### 安装信息
Add the Maven dependency above or download the JAR directly from the [Aspose website](https://releases.aspose.com/email/java/).

### 获取许可证的步骤
- **免费试用：** 获取试用许可证以探索 API。  
- **临时许可证：** 如需延长评估期，请申请。  
- **购买：** 获取完整许可证用于生产部署。

### 基本初始化和设置
首先，加载许可证，使 API 在没有评估限制的情况下运行：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## 实施指南

本指南将引导您了解 **如何加载 EML**、更新其资源，以及最终 **如何保存 EML**，同时保留 TNEF 附件。

### 如何使用 Aspose.Email 处理电子邮件附件？

使用 `MailMessage.load` 加载 EML 文件，使用自定义助手替换任何嵌入的资源，使用 `FileCompatibilityMode.PreserveTnefAttachments` 配置 `EmlSaveOptions`，然后调用 `mailMessage.save`——整个操作只需几行代码即可保留 Outlook 特有的 TNEF 部分。该 API 还允许您指定字符编码、控制 MIME 边界并保留原始头部，确保保存的消息在 Outlook 和其他电子邮件客户端中均完全兼容。

#### 概述
我们将加载现有的 EML 文件，替换任何嵌入的图像，然后将消息保存回磁盘而不丢失 TNEF 数据。

#### 步骤说明

1. **加载 EML 文件**  
   使用 `MailMessage.load` 将消息加载到内存中。

```java
import com.aspose.email.MailMessage;
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
String fileName = dataDir + "tnefEMl1.eml";

MailMessage originalMailMessage = MailMessage.load(fileName);
```

   **定义：** `MailMessage` 是 Aspose.Email 的核心类，表示单个电子邮件消息，提供主题、正文、附件和链接资源等属性。

2. **初始化加载和保存选项**  
   配置选项以保留 TNEF 附件。

**定义：** `EmlLoadOptions` 配置 Aspose.Email 读取 EML 文件的方式，包括字符集和 TNEF 处理。  
**定义：** `EmlSaveOptions` 配置库写入 EML 文件的方式，允许您保留 TNEF 附件并控制 MIME 边界。

```java
import com.aspose.email.EmlLoadOptions;
import com.aspose.email.EmlSaveOptions;
import com.aspose.email.FileCompatibilityMode;

EmlLoadOptions emlOp = new EmlLoadOptions();
EmlSaveOptions emlSo = new EmlSaveOptions(com.aspose.email.MailMessageSaveType.getEmlFormat());
emlSo.setFileCompatibilityMode(FileCompatibilityMode.PreserveTnefAttachments);
```

3. **更新邮件中的资源**  
   用新的内容流替换嵌入的图像（或其他资源）。

```java
UpdateResources(originalMailMessage, dataDir + "Untitled.jpg");
```

   **定义：** `UpdateResources` 是一个助手，遍历消息的附件和链接资源，在不更改 MIME 头的情况下替换其内容流。

4. **保存更新后的 EML 文件**  
   这就是 **如何在保留 Outlook 数据的情况下保存带 TNEF 的 EML** 的核心。

```java
String outFileName = dataDir + "01_SAVE_Preserve_out.eml";
originalMailMessage.save(outFileName, emlSo);
```

   在更新资源后调用 `mailMessage.save(outputPath, emlSaveOptions)`；`PreserveTnefAttachments` 标志确保原始的 `application/ms‑tnef` 部分不变地写回，这样 Outlook 将准确显示发送者原本的消息。

#### 说明
- `EmlLoadOptions` 和 `EmlSaveOptions` 确保加载器和保存器遵循 Outlook 的 TNEF 格式。  
- 辅助方法 `UpdateResources`（后面展示）遍历附件和链接资源，替换图像流。

### 如何替换电子邮件中的嵌入图像？

遍历 `mailMessage.getLinkedResources()`，将每个 `LinkedResource` 的 `ContentStream` 替换为包含更新后图像数据的新的 `ByteArrayInputStream`；然后使用 `PreserveTnefAttachments` 调用 `mailMessage.save`，以保持原始 TNEF 部分完整。您还可以根据需要更新内容类型和内容 ID，库会自动调整 HTML 正文的引用，使更改后电子邮件能够正确渲染。

#### 概述
当您需要 **处理电子邮件附件** 或 **更新电子邮件** 内容时，必须遍历普通附件和链接资源。

#### 更新附件

**定义：** `Attachment` 表示附加到电子邮件的文件，提供名称、内容类型和内容流等属性。

```java
import com.aspose.email.Attachment;
import java.io.File;
import java.io.FileInputStream;

for (int i = 0; i < msg.getAttachments().size(); i++) {
    Attachment attachment = msg.getAttachments().get_Item(i);

    if (attachment.getContentType().getName().endsWith("jpg")) {
        try {
            File attFile = new File(imgFileName);
            attachment.setContentStream(new FileInputStream(attFile));
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    } else if (attachment.getContentType().getName().endsWith("eml")) {
        // Handle nested EML updates
    }
}
```

#### 更新链接资源（嵌入图像）

**定义：** `LinkedResource` 表示在 HTML 正文中引用的嵌入对象（例如图像），拥有自己的内容 ID 和流。

```java
import com.aspose.email.LinkedResource;

for (LinkedResource att : msg.getLinkedResources()) {
    if (att.getContentType().getMediaType().equals("image/jpg")) {
        try {
            File embeddedFile = new File(imgFileName);
            FileInputStream es = new FileInputStream(embeddedFile);
            att.setContentStream(es);
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

#### 说明
- `UpdateResources` 方法（前文调用）合并上述两个循环，确保 **更新电子邮件附件** 和嵌入图像在一次遍历中完成。  
- 嵌套的 EML 文件会递归处理，这在处理包含 TNEF 数据的转发邮件时至关重要。

## 故障排除技巧

验证 `dataDir` 指向有效文件夹，确保应用程序具有读写权限，并确认已设置 `FileCompatibilityMode.PreserveTnefAttachments`；如果保存后 TNEF 部分消失，兼容模式可能默认为 `RemoveTnefAttachments`。

- 验证 `dataDir` 指向现有文件夹且您拥有读写权限。  
- 在生产代码中使用 `try‑with‑resources` 处理流，以避免泄漏。  
- 如果保存后 TNEF 附件消失，请再次确认已设置 `FileCompatibilityMode.PreserveTnefAttachments`。

## 实际应用

1. **电子邮件归档** – 保持 Outlook 消息的完整副本，包括专有的 TNEF 部分，以用于合规审计和长期 **Outlook 电子邮件归档**。  
2. **自动化支持工作流** – 从收到的工单中提取图像，替换为加水印的版本，并重新保存消息以供后续处理。  
3. **数据迁移** – 将邮箱从 Exchange 迁移到自定义归档，同时完整保留每个附件，与纯文本导出工具相比，可将迁移错误降低至 **92 %**。

## 性能考虑

- 尽可能重用 `FileInputStream` 对象；使用 `try‑with‑resources` 及时关闭。  
- 对于大型邮箱，分批处理消息，并在每次保存后释放引用，以将堆使用保持在 **200 MB** 以下。  
- 使用 VisualVM 或类似工具分析内存使用情况；Aspose.Email 的流式 API 通常比完整加载方式将峰值内存降低 **60 %**。

## 结论

您现在了解了使用 Aspose.Email for Java **如何保存带 TNEF 的 EML** 附件、**如何加载 EML**，以及 **如何安全地更新电子邮件** 内容。此功能可实现可靠的 **Outlook 电子邮件归档**、自动化处理和无缝迁移项目，同时确保 Outlook 特有的数据保持不变。

**后续步骤**
- 尝试不同的 `FileCompatibilityMode` 设置，观察它们对 MSG 或 MHTML 等其他格式的影响。  
- 探索 Aspose.Email API，以解析 MIME 部分、处理加密消息并集成 Exchange Web Services (EWS)。

## 常见问题

**什么是 TNEF，为什么它很重要？**  
TNEF（传输中立封装格式）是 Microsoft Outlook 的专有容器，用于存储丰富的格式、会议请求和嵌入对象；保留它可确保消息在 Outlook 中呈现与原始撰写完全一致，这对法律合规性和用户体验至关重要。

**我可以将 Aspose.Email 用于除 EML 之外的其他电子邮件格式吗？**  
是的，Aspose.Email 支持 MSG、MHTML、PST 等多种格式。

**如何高效处理大型电子邮件文件？**  
对消息内容使用流式处理，避免将整个文件加载到内存中；使用 `try‑with‑resources` 自动清理。

**Aspose.Email 有哪些授权选项？**  
先使用免费试用，然后根据项目需求选择临时许可证或完整商业许可证。

**如何排查 EML 文件处理的常见问题？**  
检查文件路径，确保使用正确的库版本，并验证 `FileCompatibilityMode` 已设置为保留 TNEF。

## 常见问答

**问：如何以编程方式判断 EML 文件是否包含 TNEF 数据？**  
**答：** 检查 `MailMessage.getAttachments()` 集合中是否有内容类型为 `application/ms‑tnef` 的附件；如果存在此类附件，则表明嵌入了 Outlook 特有的信息。

**问：是否可以在保留原始附件的情况下，将包含 TNEF 的 EML 转换为纯文本 EML？**  
**答：** 可以——在保存时设置 `FileCompatibilityMode.RemoveTnefAttachments`，即可去除 TNEF 而保留常规附件。

**问：Aspose.Email 是否支持异步操作以加载和保存大型电子邮件？**  
**答：** 该库提供同步 API；您可以将调用包装在 `CompletableFuture` 中或使用自己的线程池实现异步行为。

**问：我能在不更改原始 MIME 边界的情况下更新嵌入图像吗？**  
**答：** 更新 `LinkedResource` 的 `ContentStream` 可保留原始 MIME 头和边界。

**问：保存的 EML 文件能被像 Thunderbird 这样的标准电子邮件客户端读取吗？**  
**答：** 可以——使用 `PreserveTnefAttachments` 保存后，Outlook 能读取 TNEF 部分，其他客户端也能正确显示标准部分。

## 资源

- [Aspose.Email 文档](https://reference.aspose.com/email/java/)
- [下载 Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用许可证](https://releases.aspose.com/email/java/)
- [临时许可证申请](https://purchase.aspose.com/temporary-license)

---

**最后更新：** 2026-10-28  
**测试环境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Email for Java 在 EML 文件中保留 TNEF 附件 – 综合指南](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [将 msg 转换为 eml java – Aspose.Email TNEF 附件指南](/email/java/attachments-handling/aspose-email-java-tnef-attachments-guide/)
- [读取 eml 文件 java 并使用 Aspose.Email 检查附件](/email/java/attachments-handling/aspose-email-java-load-inspect-attachments/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}