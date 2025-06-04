---
"date": "2025-05-29"
"description": "学习如何使用 Aspose.Email for Java 从 MSG 文件高效提取已送达、已读回执以及投票结果。本指南涵盖设置、代码实现和最佳实践。"
"title": "如何使用 Aspose.Email for Java 提取 MSG 收据和投票结果——综合指南"
"url": "/zh/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 提取 MSG 收据和投票结果：综合指南

## 介绍

有效地管理电子邮件跟踪对于了解邮件阅读情况或评估办公室投票结果至关重要。本指南演示如何使用 Aspose.Email for Java 从 Microsoft Outlook MSG 文件中检索已读和送达回执以及投票结果信息。利用这些功能，您可以深入了解电子邮件互动情况。

**您将学到什么：**
- 设置 Aspose.Email for Java
- 提取收件人跟踪详细信息，例如递送和阅读时间
- 从电子邮件收件人处读取投票结果数据
- 使用 Java 处理电子邮件数据的最佳实践

## 先决条件

要遵循本教程，请确保您具备以下条件：
- **库和依赖项：** Aspose.Email for Java 版本 25.4 和兼容的 JDK（Java 开发工具包），例如 JRE 16 或更高版本。
- **环境设置：** 合适的集成开发环境 (IDE)，例如配置了 Maven 支持的 IntelliJ IDEA 或 Eclipse。
- **知识前提：** 对 Java 编程、面向对象原理有基本的了解，并熟悉处理电子邮件数据。

## 设置 Aspose.Email for Java

要开始在您的项目中使用 Aspose.Email，请通过 Maven 集成它：

**Maven依赖：**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取

要使用 Aspose.Email for Java，您需要获得许可证：
- **免费试用：** 从免费试用版开始 [Aspose的网站](https://releases。aspose.com/email/java/).
- **临时执照：** 如需延长测试时间，请向 [购买页面](https://purchase。aspose.com/temporary-license/).
- **购买：** 如果您对评估感到满意，请购买许可证以获得所有功能的完全访问权限。

## 实施指南

### 提取已读和送达回执信息

此功能允许您从 MSG 文件中提取电子邮件发送和收件人阅读的时间。

#### 逐步实施

**步骤1：** 加载 MSG 文件
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```
**第 2 步：** 迭代收件人
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```
**步骤3：** 检索并打印交货时间
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```
**步骤4：** 检索并打印阅读时间
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```

### 阅读投票结果信息

此功能有助于提取收件人的投票方式和回复时间，这对于决策过程至关重要。

#### 逐步实施

**步骤1：** 加载 MSG 文件
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```
**第 2 步：** 迭代收件人
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```
**步骤3：** 检索并打印响应
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```
**步骤4：** 检索和打印响应时间
```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## 实际应用

1. **电子邮件活动跟踪：** 使用收据数据来衡量打开率和交付成功率。
2. **调查分析：** 快速分析基于电子邮件的调查的投票结果。
3. **客户反馈管理：** 有效地检索和处理响应以改进服务。

与 CRM 系统或分析工具集成可以更深入地了解沟通效果。

## 性能考虑

- 如果有必要，可以通过分块处理大型 MSG 文件来优化性能。
- 监控内存使用情况，尤其是在处理大量电子邮件时，以防止泄漏。
- 利用高效的数据结构来存储和访问收件人属性。

## 结论

在本教程中，您学习了如何利用 Aspose.Email for Java 从 MSG 文件中提取关键信息。这些功能可以通过跟踪电子邮件的发送和阅读时间或分析投票结果来显著增强您的沟通工作流程。继续探索 Aspose.Email 的功能，进一步优化您的电子邮件管理流程。

进一步探索：
- 深入了解 [Aspose 电子邮件文档](https://reference。aspose.com/email/java/).
- 尝试更多示例 [下载部分](https://releases。aspose.com/email/java/).

## 常问问题

1. **如何处理大型 MSG 文件？**
   - 以较小的批次处理它们以避免内存问题。
2. **如果收件人的响应时间为空怎么办？**
   - 这可能表明他们尚未回复或尚未设置属性。
3. **Aspose.Email 可以与数据库一起使用吗？**
   - 是的，将其与 SQL 或 NoSQL 数据库集成以存储和查询电子邮件数据。
4. **是否支持其他文件格式？**
   - 除了 MSG 文件之外，Aspose.Email 还支持 EML、PST 等多种格式。
5. **如果我遇到问题，我可以在哪里获得帮助？**
   - 访问 [Aspose 电子邮件论坛](https://forum.aspose.com/c/email/10) 寻求社区支持。

## 资源
- **文档：** [Aspose 电子邮件文档](https://reference.aspose.com/email/java/)
- **下载SDK：** [Aspose Email 下载](https://releases.aspose.com/email/java/)
- **购买许可证：** [购买 Aspose 产品](https://purchase.aspose.com/buy)
- **免费试用：** 从 [免费试用版](https://releases.aspose.com/email/java/)
- **临时执照：** [申请临时许可证](https://purchase.aspose.com/temporary-license/)
- **支持论坛：** 参与讨论 [Aspose 电子邮件论坛](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}