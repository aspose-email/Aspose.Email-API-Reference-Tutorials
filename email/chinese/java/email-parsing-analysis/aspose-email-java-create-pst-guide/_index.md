---
date: '2026-06-08'
description: 了解如何使用 Aspose.Email for Java 创建 PST 文件，包括如何添加文件夹结构以及如何高效搜索 PST 内容。一步一步的指南。
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: 如何使用 Aspose.Email for Java 创建 PST 文件
url: /zh/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Aspose.Email for Java 的电子邮件管理

如果您需要以编程方式 **how to create pst** 文件，您来对地方了。在本教程中，我们将逐步演示生成 Unicode PST 文件、添加标准 Outlook 文件夹、导入邮件以及运行不区分大小写的搜索——全部使用 Aspose.Email for Java。完成后，您将拥有一个可复用的代码模式，能够从少量邮件扩展到多吉字节的归档。

## 快速答案
- **如何开始？** 添加 Aspose.Email Maven 依赖项，获取许可证，并实例化 `PersonalStorage`。
- **我可以添加收件箱文件夹吗？** 可以 – 调用 `pst.getRootFolder().addSubFolder("Inbox")`。
- **是否支持不区分大小写的搜索？** 使用 `PersonalStorageQueryBuilder` 并配合 `StringComparison.OrdinalIgnoreCase`。
- **可以处理多大的文件？** Aspose.Email 可处理最高 2 GB 的 PST 文件，而无需将整个文件加载到内存中。
- **生产环境是否需要付费许可证？** 永久许可证可移除试用限制并解锁全部性能特性。

## 什么是 how to create pst？
**how to create pst** 指的是使用代码而非 Outlook UI 生成 Outlook Personal Storage Table（PST）文件的编程过程。Aspose.Email for Java 提供了完整托管的 API，可创建 Unicode PST 文件、添加文件夹，并存储 `MapiMessage` 对象，无需安装 Outlook。

## 为什么使用 Aspose.Email 创建 PST？
Aspose.Email 支持 **50+** 种电子邮件相关格式（MSG、EML、MBOX、PST 等），并且能够在内存使用低于 **150 MB** 的情况下处理最高 **2 GB** 大小的 PST 文件，这得益于其惰性加载架构。这一量化能力使其非常适合企业归档、迁移和合规场景。

## 前提条件

- **Java Development Kit (JDK)** – 版本 16 或更高。
- **Maven** – 用于依赖管理。
- 基本的 Java 语法熟悉度；不需要事先了解 PST 文件。

## 如何创建 PST 文件？

`PersonalStorage` 类代表一个 PST 文件，并提供创建、打开和操作其内容的方法。要创建新的 Unicode PST，调用 `PersonalStorage.create()` 并传入所需的文件路径和格式版本。此操作会生成支持大文件夹、Unicode 字符和高效流式处理的现代 PST，适用于小规模和企业级归档任务。

### 步骤 1：添加 Maven 依赖

将 Aspose.Email Maven 依赖添加到您的 `pom.xml`。这会自动拉取所有必需的二进制文件。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 步骤 2：获取并应用许可证

提供免费试用，但永久许可证可移除评估限制并启用全速处理。

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## 如何向 PST 添加文件夹？

在 PST 根目录下创建所需的文件夹层次结构，然后在插入邮件时引用它。`FolderInfo` 对象代表每个文件夹，可任意嵌套，允许您构建如收件箱、已发送项或自定义项目文件夹等结构。添加文件夹是轻量级操作，不会加载邮件内容，即使是大型 PST 也能保持性能。

### 步骤 1：初始化 PersonalStorage

`PersonalStorage` 类是 Aspose.Email 的顶层对象，代表内存中的单个 PST 文件。实例化后，所有读写操作都通过该对象进行。

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### 步骤 2：定义目录路径

设置电子邮件文件的源路径和目标路径以及 PST 输出位置。

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### 步骤 3：创建 PST 文件

使用 `PersonalStorage.create()` 并传入 `FileFormatVersion.Unicode`，生成支持大文件夹和 Unicode 字符的现代 Unicode PST。

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 如何搜索 pst？

`PersonalStorageQueryBuilder` 是用于构建 PST 内容搜索查询的构建器类。通过配置所需的条件并指定 `StringComparison.OrdinalIgnoreCase`，您可以在主题、正文和自定义属性上执行快速的不区分大小写搜索，而无需将整个 PST 加载到内存中。

### 步骤 1：构建搜索查询

构造一个在主题或正文中查找关键字且忽略大小写的查询。

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### 步骤 2：执行查询并检索邮件

在目标文件夹上运行查询，并遍历返回的 `MapiMessage` 集合。

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 在 PST 中创建预定义文件夹

添加像 **Inbox** 这样的预定义文件夹有助于有效组织您的电子邮件数据。

### 步骤 1：初始化 PersonalStorage 对象
假设 `PersonalStorage` 对象（`pst`）已按前述方式创建。

### 步骤 2：创建 'Inbox' 文件夹

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 向 PST 文件夹添加邮件

通过从文件加载并转换来填充您的 PST 文件夹。

### 步骤 1：加载电子邮件消息

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### 步骤 2：添加到 PST 文件夹

将 `MailMessage` 转换为 `MapiMessage` 并添加：

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 实际应用

Aspose.Email for Java 不仅用于创建 PST 文件，它还是一个功能多样的工具，拥有众多应用场景：
- **电子邮件归档**：自动将企业邮件归档到 PST 文件，支持最长 10 年的保留策略。
- **迁移工具**：使用单个 API 调用即可将旧邮件存储（如 MBOX）无缝迁移到 Outlook PST。
- **数据分析**：提取发件人、收件人和时间戳等元数据，用于商业智能管道。
- **备份解决方案**：构建稳健的备份实用程序，增量存储邮件更改而无需重新处理整个邮箱。

## 性能考虑因素

使用 Aspose.Email 时确保最佳性能的要点：
- **资源管理**：始终调用 `pst.dispose()` 或使用 try‑with‑resources 及时释放本机句柄。
- **批量处理**：将邮件分批处理，每批 **500** 条，以保持内存使用可预测。
- **并发处理**：库对只读操作是线程安全的；写入时请同步对 `PersonalStorage` 实例的访问。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|----------|
| **OutOfMemoryError** when handling large PSTs | 将整个 PST 加载到内存中 | 启用 `PersonalStorage.setUseUnicode(true)` 并以流方式处理消息。 |
| **Folder not found** error | 文件夹路径大小写不正确 | 在查询中使用 `StringComparison.OrdinalIgnoreCase` 或规范化文件夹名称。 |
| **License not applied** | 在首次 API 调用前未加载许可证文件 | 在应用程序启动时加载许可证，确保在创建任何 `PersonalStorage` 对象之前完成。 |

## 常见问答

**Q: 最低需要的 Java 版本是什么？**  
A: 推荐使用 JDK 16 或更高，以获得对 Aspose.Email for Java 的完整兼容性。

**Q: 可以在没有许可证的情况下使用 Aspose.Email 吗？**  
A: 可以，提供试用模式，但 PST 大小限制为 **10 MB**，且某些优化功能被禁用。

**Q: 如何高效处理大型 PST 文件？**  
A: 将邮件分批处理，及时释放 `MapiMessage` 对象，并通过 `PersonalStorage.setUseUnicode(true)` 启用惰性加载。

**Q: 能否向 PST 文件中的邮件添加附件？**  
A: 完全可以。在将 `MailMessage` 转换为 `MapiMessage` 时，调用 `mapiMsg.getAttachments().add(attachment)` 即可嵌入文件。

**Q: 如遇问题，哪些支持渠道可用？**  
A: Aspose 提供专属支持论坛、详细文档以及面向付费客户的电子邮件支持。

## 资源
- [文档](https://reference.aspose.com/email/java/)
- [下载](https://releases.aspose.com/email/java/)
- [购买](https://purchase.aspose.com/buy)
- [免费试用](https://releases.aspose.com/email/java/)
- [临时许可证](https://purchase.aspose.com/temporary-license/)
- [支持论坛](https://forum.aspose.com/c/email/10)

---

**最后更新：** 2026-06-08  
**测试环境：** Aspose.Email for Java 24.10  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Email for Java 创建和管理 Outlook PST 文件](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [使用 Aspose.Email for Java 操作 PST 文件：全面指南](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Java 提取电子邮件附件 – 使用 Aspose.Email 处理 PST 文件的分步指南](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}