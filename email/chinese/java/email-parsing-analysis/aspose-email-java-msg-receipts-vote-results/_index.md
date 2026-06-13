---
date: '2026-06-13'
description: 了解如何使用 Aspose.Email for Java 读取 MSG 文件并解析 MSG 附件，高效提取送达/阅读回执和投票结果。包括设置、代码示例和最佳实践。
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: 如何使用 Aspose.Email for Java 读取 MSG 文件
url: /zh/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 读取 MSG 文件

## 介绍

以编程方式读取 MSG 文件可以让您从 Outlook 邮件中提取有价值的跟踪数据——投递回执、阅读确认和投票结果。在本指南中，我们将展示 **如何读取 msg** 文件，逐步说明所需的设置，并演示如何高效提取回执和投票信息。

## 快速答案
- **处理 MSG 解析的库是什么？** Aspose.Email for Java。  
- **我可以提取阅读回执吗？** 是的，API 返回投递和阅读时间戳。  
- **投票数据可以获取吗？** 当然；您可以检索每个收件人的投票响应。  
- **我需要许可证吗？** 试用版可用于测试；付费许可证可移除评估限制。  
- **需要哪个 Java 版本？** 推荐使用 Java 16 或更高版本。

## Aspose.Email for Java 是什么？

Aspose.Email for Java 是一个独立的 Java 库，可在无需 Microsoft Outlook 的情况下实现电子邮件格式的创建、操作和转换。它提供了针对 MSG、EML、PST 以及许多其他格式的丰富对象模型，使开发人员能够直接在 Java 代码中处理电子邮件数据。（45 words）

## 为什么使用 Aspose.Email for Java 读取 MSG 文件？

Aspose.Email for Java 支持 **30+ 电子邮件格式**，并且能够在不将整个文件加载到内存中的情况下处理高达 **500 MB** 的 MSG 文件。其高性能解析引擎降低了 CPU 和内存消耗，使其非常适合大规模邮件归档处理和实时分析场景。（48 words）

## 前置条件

- **库和依赖项：** Aspose.Email for Java 版本 25.4 或更高，以及 JDK 16+ 运行时。  
- **IDE：** IntelliJ IDEA、Eclipse 或任何支持 Maven 的 Java 兼容 IDE。  
- **基本技能：** 熟悉 Java 语法和面向对象概念。

## 许可证获取

要使用 Aspose.Email for Java，您需要许可证：

- **免费试用：** 从 [Aspose's website](https://releases.aspose.com/email/java/) 上提供的免费试用版开始。  
- **临时许可证：** 从 [purchase page](https://purchase.aspose.com/temporary-license/) 请求临时许可证。  
- **购买：** 如果您对评估满意，可通过 [Buy Aspose Products](https://purchase.aspose.com/buy) 页面购买许可证，以完整访问所有功能。

## 如何从 MSG 文件中提取阅读和投递回执信息？

加载 MSG 文件，遍历其收件人，并读取 `DeliveryTime` 和 `ReadTime` 属性。此方法返回每个收件人邮件服务器投递消息以及收件人打开邮件的确切时间戳，为分析提供精确的跟踪数据。（53 words）

### 步骤 1：加载 MSG 文件
MapiMessage 是 Aspose.Email 中表示 Outlook MSG 消息的类。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### 步骤 2：遍历收件人
MapiRecipient 表示 MSG 文件中的单个收件人（收件人、抄送或密送）。  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 步骤 3：检索并打印投递时间
DeliveryTime 是 MapiRecipient 的属性，保存消息投递到收件人服务器的时间戳。  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 步骤 4：检索并打印阅读时间
ReadTime 是 MapiRecipient 的属性，指示收件人打开消息的时间（如果该信息可用）。  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## 如何读取 MSG 文件中的投票结果？

加载消息后，API 会公开每个收件人的投票响应及其响应时间，使您能够以编程方式汇总投票结果。这些数据可用于生成汇总报告或直接输入业务智能仪表板，以快速决策。（53 words）

### 步骤 1：加载 MSG 文件
再次使用 MapiMessage 访问 MSG 文件中嵌入的投票信息。  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### 步骤 2：遍历收件人
MapiRecipient 提供对每位参与者投票选择和响应时间的访问。  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 步骤 3：检索并打印响应
`VotingResponse` 属性包含实际投票（例如 “Accept”、 “Decline” 或自定义选项）。  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 步骤 4：检索并打印响应时间
`VotingResponseTime` 记录收件人提交投票的时间，便于对投票活动进行时间顺序分析。  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## 实际应用

1. **电子邮件活动跟踪：** 通过分析回执时间戳来衡量打开率和投递成功率。  
2. **调查分析：** 整合 Outlook 投票的结果，以快速决策。  
3. **客户反馈管理：** 将响应数据提取到 CRM 或分析平台，以获得更深入的洞察。

将这些提取结果与数据库或 BI 工具集成，可提升原始电子邮件数据的价值。

## 性能考虑

- 以 **块** 方式处理大型 MSG 文件，以保持内存使用低。  
- 处理成千上万的消息时使用 **流式 API**。  
- 将收件人数据存储在轻量级集合（如 `ArrayList` 或 `HashMap`）中，以实现快速查找。

## 常见问题及解决方案

- **空时间戳：** 缺少 `ReadTime` 通常表示收件人尚未打开邮件。  
- **大型附件：** 如果 MSG 包含巨大的附件，启用 `LoadOptions.setPreserveEmbeddedResources(false)` 以跳过加载它们到内存。  
- **编码问题：** 读取非 ASCII 内容时，通过 `MailMessage.setCharset(Charset.forName("UTF-8"))` 确保设置正确的代码页。

## 常见问答

**问：如何处理大于 500 MB 的 MSG 文件？**  
A: 将文件拆分为更小的段，或使用流式 API 读取部分内容，而无需完整加载到内存中。

**问：我可以直接将提取的数据存入数据库吗？**  
A: 可以，将回执和投票字段映射到您的数据库模式，并使用 JDBC 或 ORM 将其持久化。

**问：该库能在 Linux 环境下运行吗？**  
A: 当然可以；Aspose.Email for Java 与平台无关，可在任何支持的 JDK 所在的操作系统上运行。

**问：在读取回执时是否可以提取附件？**  
A: 在加载 MSG 后使用 `MailMessage.getAttachments()`；该方法返回所有嵌入文件的集合。

**问：如果遇到错误，有哪些支持选项？**  
A: 通过官方 Aspose Email 论坛寻求社区帮助，或使用有效许可证提交支持工单。

## 资源
- **文档：** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **文档（重复）：** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **下载 SDK：** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **下载区块：** [Download Section](https://releases.aspose.com/email/java/)  
- **购买许可证：** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **免费试用：** 从 [Free Trial Version](https://releases.aspose.com/email/java/) 开始  
- **临时许可证：** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支持论坛：** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **支持论坛（重复）：** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**最后更新：** 2026-06-13  
**测试环境：** Aspose.Email for Java 25.4  
**作者：** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## 相关教程

- [如何使用 Aspose.Email for Java 加载和解析 Outlook MSG 文件：综合指南](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [使用 Aspose.Email for Java 将 MSG 转换为 EML 并管理附件](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [提取内联附件 Java – MSG 文件使用 Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}