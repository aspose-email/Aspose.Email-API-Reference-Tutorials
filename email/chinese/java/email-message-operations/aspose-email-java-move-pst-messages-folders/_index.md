---
date: '2026-08-11'
description: 了解如何使用 Aspose.Email for Java 移动 PST 文件夹和邮件——一步步指南，帮助您高效移动 PST。
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: 了解如何使用 Aspose.Email for Java 通过几行代码移动 PST 文件夹和邮件。本指南涵盖环境设置、子文件夹移动、单个项目迁移以及大容量
  PST 文件的最佳实践。
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: 如何使用 Aspose.Email Java 移动 PST 文件夹和邮件
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: 如何使用 Aspose.Email Java 移动 PST 文件夹和邮件
url: /zh/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email Java 移动 pst 文件夹和邮件

在需要重新组织大型 Outlook PST 文件时，高效的电子邮件管理至关重要。在本教程中，您将学习使用 Aspose.Email for Java 编程方式 **如何移动 pst** 文件夹和邮件，实现自动化清理、迁移和归档，而无需启动 Outlook。完整的 API 详情，请参阅 [Aspose Email Java 参考](https://reference.aspose.com/email/java/)。

## 快速答案
- **使用的库是什么？** Aspose.Email for Java  
- **我可以同时移动文件夹和单个邮件吗？** 是 — 使用 `moveItem` 移动邮件，使用 `moveSubfolders` 移动整个文件夹  
- **在生产环境中需要许可证吗？** 商业部署需要有效的 Aspose 许可证  
- **推荐使用哪个 Java 版本？** 为获得最佳性能，建议使用 Java 16 或更高版本  
- **是否需要示例 PST 文件？** 任何 Outlook 生成的 PST 都可使用；您可以使用 Outlook 创建，或使用测试文件  

## 在 Java 开发中移动 pst 是什么意思？
移动 pst 指的是在 Personal Storage Table（PST）文件内部以编程方式重新定位文件夹或邮件项。这使您能够自动化批量清理、归档旧邮件或在邮件存储之间迁移内容，而无需手动操作 Outlook，从而提升效率并减少人为错误。

## 为什么使用 Aspose.Email for Java 来移动 pst 数据？
使用 Aspose.Email 可以移动 pst 数据，因为它提供了 **纯 Java API**，可在任何操作系统上运行，支持 **超过 100 GB** 的 PST 文件，并且在标准服务器硬件上能够 **每分钟处理多达 500 000 条项目**。该库还提供详细的异常信息，帮助您快速定位问题。

## 前提条件
- Aspose.Email for Java（最新版本）  
- JDK 16+（或更高）  
- Maven 或 Gradle 构建系统  
- 用于测试的 PST 文件（任何 Outlook 生成的文件）

## 设置 Aspose.Email for Java
要使用 Aspose.Email，请在 `pom.xml` 文件中添加 Maven 依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 获取许可证的步骤
1. **免费试用** – 通过免费试用开始探索 Aspose.Email 功能。  
2. **临时许可证** – 从 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 获取延长使用的临时许可证。  
3. **购买** – 如果该库满足您的生产需求，可考虑购买完整许可证。有关定价详情，请参阅 [Aspose 的购买选项](https://purchase.aspose.com/buy)。  

### 基本初始化和设置
在开始处理 PST 文件之前，请确保已正确引用该库：

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## 如何移动 pst 文件夹和邮件
下面列出了在需要高效 **如何移动 pst** 项目时所需的核心操作。

### 初始化并访问 PST 文件
`PersonalStorage` 是 Aspose.Email 用于打开和操作 PST 文件的主要类。

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### 步骤 1：加载 PST 文件
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### 步骤 2：访问预定义文件夹
- **收件箱文件夹**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **已删除邮件文件夹**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### 将子文件夹移动到 PST 中的另一个文件夹
`FolderInfo` 表示 PST 文件中的一个文件夹，并提供移动子文件夹的方法。

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### 步骤 1：访问源文件夹和目标文件夹
```java
pst.moveItem(subfolder, deletedItems);
```

#### 步骤 2：从收件箱获取特定子文件夹
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### 步骤 3：移动整个子文件夹
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### 在 PST 中的文件夹之间移动单个邮件
`MessageInfoCollection` 保存 `MessageInfo` 对象的集合，每个对象代表一封电子邮件。

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### 步骤 1：从特定子文件夹检索邮件
```java
inbox.moveSubfolders(deletedItems);
```

#### 步骤 2：将第一封邮件移动到已删除邮件文件夹
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### 将所有子文件夹从一个文件夹移动到 PST 中的另一个文件夹
`moveSubfolders` 在一次调用中将所有子文件夹从源文件夹转移到目标文件夹。

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### 步骤 1：访问源文件夹和目标文件夹
```java
subfolder.moveContents(deletedItems);
```

#### 步骤 2：移动所有子文件夹
CODE_BLOCK_PLACEHOLDER_15_END

### 将子文件夹的所有内容移动到 PST 中的另一个文件夹
`moveAllContents`（使用 `moveItem` 的自定义循环）可以重新定位子文件夹内的所有邮件。

CODE_BLOCK_PLACEHOLDER_16_END

#### 步骤 1：访问源文件夹和目标文件夹
CODE_BLOCK_PLACEHOLDER_17_END

#### 步骤 2：从收件箱获取特定子文件夹
CODE_BLOCK_PLACEHOLDER_18_END

#### 步骤 3：移动子文件夹的所有内容
CODE_BLOCK_PLACEHOLDER_19_END

## 实际应用
移动 pst 文件夹和邮件的用途包括：

- **数据迁移** – 将邮箱从 Outlook 转移到其他邮件系统。  
- **邮件归档** – 自动将旧邮件组织到归档文件夹。  
- **清理操作** – 通过将过时的项目移动到归档或删除文件夹来整理收件箱。

## 性能考虑
在使用 Aspose.Email for Java 处理大型 PST 文件时，请遵循以下建议：

- **优化资源使用** – 使用 try‑with‑resources 或显式 `dispose` 及时关闭 `PersonalStorage` 对象。  
- **内存管理** – 将项目分批处理，而不是一次性加载整个文件夹到内存中；这可以减轻 JVM 的堆压力。

### 最佳实践
- 操作完成后始终释放 PST 资源。  
- 在尝试移动之前验证文件夹是否存在，以避免 `InvalidOperationException`。

## 常见问题

**问：什么是 PST 文件？**  
答：PST（Personal Storage Table）文件是 Outlook 的专有格式，用于在本地存储电子邮件、联系人、日历项以及其他邮箱数据。

**问：我可以在商业项目中使用 Aspose.Email for Java 吗？**  
答：可以，只要您通过 [Aspose 的购买选项](https://purchase.aspose.com/buy) 获得有效许可证，即可商业使用。

**问：在使用 Aspose.Email 处理 PST 文件时如何处理异常？**  
答：将代码放在 `try‑catch` 块中，以捕获 `IOException`、`InvalidOperationException` 或 Aspose 特定的异常，然后记录错误细节或根据需要重新抛出。

**问：运行此代码的系统要求是什么？**  
答：您需要 JDK 16 或更高版本，以及兼容的 IDE，如 IntelliJ IDEA 或 Eclipse。Aspose.Email 的 JAR 必须在项目的类路径中。

**问：在哪里可以找到更多关于 Aspose.Email for Java 的资源？**  
答：请访问官方文档 [Aspose Email Java 参考](https://reference.aspose.com/email/java/)。

**问：Aspose.Email 是否支持受密码保护的 PST 文件？**  
答：是的，您可以在调用 `PersonalStorage.fromFile` 时提供密码来打开加密的 PST。

**问：如何验证移动操作是否成功？**  
答：在调用 `moveItem` 或 `moveSubfolders` 后，使用 `getContents()` 或 `getSubFolders()` 查询目标文件夹，以确认已移动项目的存在。

## 资源
- **文档**: [Aspose Email Java 参考](https://reference.aspose.com/email/java/)  
- **API 详情**: [Aspose Email Java 参考](https://reference.aspose.com/email/java/)  
- **下载**: [Aspose Email Java 发布](https://releases.aspose.com/email/java/)  
- **购买**: [购买 Aspose 产品](https://purchase.aspose.com/buy)  
- **免费试用**: [Aspose 免费试用](https://releases.aspose.com/email/java/)  
- **临时许可证**: [获取临时许可证](https://purchase.aspose.com/temporary-license/)

---

**最后更新：** 2026-08-11  
**测试环境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Email for Java 批量更新 PST 邮件：完整指南](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [使用 Aspose.Email for Java 提取 Outlook PST 邮件：完整指南](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [使用 Aspose.Email for Java 在 PST 文件之间传输邮件：完整指南](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}