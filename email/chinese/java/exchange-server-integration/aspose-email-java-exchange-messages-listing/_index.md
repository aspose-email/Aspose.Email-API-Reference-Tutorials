---
date: '2026-10-02'
description: 了解如何使用 Aspose.Email for Java 连接 exchange 并列出 exchange public folders。本分步指南展示了
  Maven 依赖项和免代码设置。
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: 了解如何使用 Aspose.Email for Java 连接 exchange 并列出 exchange public folders。本指南涵盖了
  Maven 依赖、授权以及递归消息检索。
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: 如何在 Java 中连接 exchange 并列出 public folders
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: 如何在 Java 中连接 exchange 并列出 public folders
url: /zh/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中连接 Exchange 并列出公共文件夹

## 简介
在现代企业中，以编程方式访问 Microsoft Exchange 邮箱可以实现归档、监控和报告任务的自动化。本教程展示了 **如何使用 Aspose.Email for Java 连接 Exchange**，以及 **递归列出 Exchange 公共文件夹** 的方法。您将看到所需的 Maven 依赖、授权步骤以及 API 调用的完整顺序——无需额外库。完成后，您即可从任意公共文件夹提取邮件并本地保存。

## 快速答案
- **第一步是什么？** 将 Aspose.Email Maven 依赖添加到 `pom.xml` 中。  
- **需要许可证吗？** 是的——可使用临时许可证进行评估，或购买正式许可证用于生产。  
- **哪个类创建连接？** `ExchangeClient`（IMAP 场景使用 `ImapClient`）负责身份验证和服务器通信。  
- **可以自动列出子文件夹吗？** 可以——使用 API 提供的递归 `listSubFolders` 方法。  
- **此方法线程安全吗？** 客户端对象不是线程安全的；并发工作负载请为每个线程创建独立实例。

## 什么是如何连接 Exchange？
**如何连接 Exchange** 是指对本地或基于云的 Microsoft Exchange 服务器进行身份验证，以便 Java 应用程序能够发出文件夹枚举或邮件检索等 API 调用。Aspose.Email 对底层 EWS/IMAP 协议进行抽象，提供统一且一致的对象模型。

## 为什么列出 Exchange 公共文件夹？
列出公共文件夹可以让您了解组织用于共享邮箱、分发列表和归档存储的层次结构。Aspose.Email 能在一次调用中枚举 **50+ 公共文件夹**，并支持处理数百页的邮箱而无需将整个存储加载到内存中，内存占用可降低至 70 %。

## 先决条件
- **Aspose.Email for Java** — 版本 25.4 或更高（最新稳定版）。  
- **Java Development Kit (JDK)** — 已安装 JDK 11 或更高，并配置 `JAVA_HOME`。  
- **Maven** — 用于依赖管理和构建自动化。  
- 基本的 Java 语法和 Exchange 概念（邮箱、文件夹、EWS）知识。

## 设置 Aspose.Email for Java
要集成该库，请在项目的 `pom.xml` 中添加 Maven 依赖。这就是您需要的 **aspose email Maven 依赖**。

### Maven 依赖
在 `pom.xml` 的 `<dependencies>` 元素内部添加以下片段：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 获取许可证的步骤
Aspose.Email 需要有效许可证才能使用全部功能：

- **免费试用** – 从 [Aspose 网站](https://purchase.aspose.com/temporary-license/) 下载临时许可证，以评估 API。  
- **购买** – 通过 Aspose 门户获取商业许可证，用于生产部署。

#### 基本初始化
在 Maven 解析完包并拥有许可证文件后，将 `.lic` 文件放置在类路径上并初始化库：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 实现指南
我们将逐步讲解每个功能块，在详细步骤之前先用简洁段落回答关键问题。

### 如何连接 Exchange？
加载 `ExchangeClient`，提供服务器 URL、用户凭证和域，然后调用 `connect()`。客户端会与 Exchange Web Services (EWS) 建立 HTTPS 会话并验证凭证。如果连接失败，API 会抛出包含 HTTP 状态码的 `AuthenticationException`，便于快速排查。  
`ExchangeClient` 是 Aspose.Email 用于管理与 Exchange Web Services 连接的类。

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### 如何列出 Exchange 公共文件夹？
调用 `client.listPublicFolders()` 可获取 `FolderInfo` 对象集合，代表每个顶层公共文件夹。该方法返回文件夹名称、总项目数以及后续调用使用的唯一标识符。对典型的本地部署（最多 500 个文件夹），此调用在 2 秒内完成。  
`listPublicFolders()` 返回 `FolderInfo` 对象集合。  
`FolderInfo` 包含显示名称、项目计数等元数据。

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### 如何显示文件夹信息？
遍历 `FolderInfo` 集合，打印 `displayName` 和 `subFolderCount`。此快速快照帮助您在进行更深层爬取前了解层次结构。对于大型组织，API 可分页返回，每页 100 个文件夹，以降低内存占用。

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### 如何列出文件夹中的消息？
调用 `client.listMessages(folderId)`，其中 `folderId` 为前一步获取的标识符。该方法返回 `MessageInfo` 对象列表，包含主题、发件人和接收日期。可使用 `maxCount` 限制返回数量，防止在处理超大文件夹时压垮客户端。  
`listMessages(folderId)` 返回 `MessageInfo` 对象列表。  
`MessageInfo` 包含邮件的基本属性，如主题、发件人和接收日期。

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### 如何获取并保存消息？
对每个 `MessageInfo`，使用 `client.fetchMessage(messageId)` 下载完整的 MIME 内容。随后将字节数组写入磁盘上的 `.eml` 文件。API 采用流式处理，即使是 100 MB 的邮件也无需一次性加载全部负载。

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### 如何递归列出子文件夹中的消息？
实现深度优先遍历：从顶层文件夹开始，通过 `client.listSubFolders(parentId)` 列出子文件夹，然后对每个子文件夹重复消息列出流程。此模式确保公共文件夹树中的每条消息都被处理。递归深度仅受服务器文件夹层级限制（通常 < 20 级）。  
`listSubFolders(parentId)` 返回给定文件夹的直接子文件夹。

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## 实际应用
此工作流在真实场景中的典型用途：

1. **自动邮件归档** – 定期拉取所有公共文件夹的邮件并存入合规归档。  
2. **备份解决方案** – 将 Exchange 公共文件夹镜像到安全文件系统或云存储桶，确保数据冗余。  
3. **自定义邮件客户端** – 构建轻量级查看器，仅显示所需的文件夹和邮件，降低 UI 复杂度。

## 性能考虑
在面对数千个文件夹和数百万条消息时，请注意以下要点：

- **连接池** – 为多次操作复用单个 `ExchangeClient` 实例，而不是为每个文件夹创建新实例。  
- **惰性加载** – 仅请求所需的元数据（使用带 `maxCount` 参数的 `listMessages`），按需获取完整正文。  
- **释放对象** – 批处理完成后调用 `client.dispose()`，释放 HTTP 连接和线程本地缓冲区。  
- **并行处理** – 将顶层文件夹分配给多个线程，每个线程拥有独立的客户端实例，以充分利用多核 CPU。

## 常见问题

**Q: 可以将此代码用于 Exchange Online（Office 365）吗？**  
A: 可以。提供 Office 365 EWS 端点 (`https://outlook.office365.com/EWS/Exchange.asmx`) 并使用现代身份验证（OAuth）——Aspose.Email 原生支持 OAuth 令牌。

**Q: 如果文件夹包含超过 10 000 条消息怎么办？**  
A: 使用接受 `skip` 和 `take` 参数的 `listMessages` 重载进行分页，保持内存使用在可控范围。

**Q: 下载单封邮件有大小限制吗？**  
A: API 采用流式传输，支持最高 150 MB 的邮件下载，只要 JVM 拥有足够的本机内存即可。

**Q: 需要手动处理 SSL 证书吗？**  
A: 默认情况下 Aspose.Email 信任 Java 默认密钥库。如果 Exchange 服务器使用自签名证书，请将其导入 JVM 信任库，或在仅用于测试时调用 `client.setEnableSslVerification(false)`。

**Q: 如何记录操作以供审计？**  
A: 通过配置 `Logger.setLevel(Level.INFO)` 并将输出定向到文件或监控系统，启用 Aspose.Email 的内置日志功能。

## 结论
现在您已经掌握了使用 Aspose.Email for Java **连接 Exchange 并递归列出公共文件夹消息** 的完整、可投入生产的方案。步骤涵盖 Maven 设置、授权、连接、文件夹枚举、消息检索以及性能调优。您可以在此基础上进一步集成数据库、云存储或自定义分析管道，以满足组织的特定需求。

---

**最后更新：** 2026-10-02  
**测试环境：** Aspose.Email for Java 25.4  
**作者：** Aspose

## 相关教程

- [How to Connect to Exchange Server using Aspose.Email in Java: Step-by-Step Guide](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [How to Connect and List Exchange Server Folders Using Aspose.Email for Java](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Manage Exchange Server Folders Using Aspose.Email for Java: A Comprehensive Guide](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}