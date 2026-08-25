---
date: '2026-07-17'
description: 如何使用 Aspose.Email Java 和 EWS 过滤电子邮件：学习日期、发件人和主题过滤技术，以简化您的邮箱。
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: 如何使用 Aspose.Email Java 和 EWS 过滤电子邮件。了解日期、发件人和主题过滤技术，以保持邮箱整洁。
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: 如何使用 Aspose.Email Java 与 EWS 过滤电子邮件
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: 如何使用 Aspose.Email Java 与 EWS 过滤电子邮件指南
url: /zh/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Aspose.Email Java 与 EWS 的邮件过滤：完整指南

## 介绍

**如何高效过滤电子邮件** 是任何使用 Microsoft Exchange 或任何现代邮箱的人的核心技能。无论您是构建企业级自动化的开发者，还是希望保持收件箱整洁的个人，掌握正确的过滤技术都能节省数小时的手动工作。在本指南中，我们将结合 Aspose.Email for Java 与 Exchange Web Services（EWS），向您展示如何按日期、发件人、主题、域、收件人进行过滤，甚至使用逻辑运算符组合多个条件。

### 您将学习的内容
- 使用 Java 中的 EWS 过滤消息的技术。  
- 根据日期、发件人、主题等条件过滤电子邮件。  
- 实现分页支持以处理大型邮箱。  
- 这些过滤方法在实际场景中的应用。  
- 使用 Aspose.Email Java 时的性能考虑和最佳实践。

通过本教程，您将能够编写简洁、高性能的 Java 代码，从 Exchange 服务器中精确获取所需的邮件。

## 快速答疑
- **主要库是什么？** Aspose.Email for Java。  
- **使用的协议是什么？** Exchange Web Services (EWS)。  
- **我可以按日期范围过滤吗？** 可以——在 `SearchFilter` 中使用 `DateTime` 条件。  
- **支持分页吗？** 完全支持，API 提供带偏移/限制的 `ItemView`。  
- **生产环境需要许可证吗？** 是的，商业许可证可移除评估限制。

## 什么是 Aspose.Email for Java？
Aspose.Email for Java 是一个全面的 API，能够在不需要 Outlook 或其他客户端的情况下，以编程方式访问电子邮件服务器、MIME 消息和 Exchange Web Services。它抽象了底层协议，让您专注于业务逻辑。该库同时支持本地部署的 Exchange 服务器和 Exchange Online，提供统一的 API 以适应各种部署场景。

## 为什么将 Aspose.Email 与 EWS 结合使用？
Aspose.Email 支持 **50+** 种电子邮件协议，凭借其流式架构能够每小时处理 **数十万封邮件**，且内存使用保持在 **100 MB** 以下。这种可量化的性能使其非常适合企业级邮箱自动化。此外，它内置对 OAuth 和现代身份验证的支持，简化了与 Office 365 环境的安全连接。

## 前置条件

- **必需的库**：在项目中包含 Aspose.Email 库。  
- **环境设置**：需要准备好的 Java 应用开发环境。  
- **知识前提**：熟悉 Java 编程和电子邮件协议将有帮助。

## 设置 Aspose.Email for Java

### Maven 安装
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取
- **免费试用**：使用免费试用版探索 Aspose.Email 的功能。  
- **临时许可证**：获取临时许可证以延长评估时间。  
- **购买**：如果工具满足需求，请考虑购买完整许可证。

通过导入必要的包并使用 EWS 凭据建立与邮件服务器的连接来初始化和设置 Aspose.Email。此步骤对于以编程方式访问邮箱数据至关重要。

## 如何在 Java 中使用 EWS 过滤电子邮件？

ExchangeService 是 Aspose.Email 中表示与 Exchange 服务器连接的类。  
SearchFilter 定义在服务器上定位项目的条件。  
FindItems 执行搜索并返回匹配的项目。  
ItemView 控制分页以及每次请求返回的项目数量。

使用您的凭据加载 `ExchangeService` 实例，创建匹配条件的 `SearchFilter`，并使用 `ItemView` 调用 `FindItems` 以仅检索所需的邮件。这一行代码模式——连接 → 过滤 → 获取——覆盖大多数用例，并在启用分页时可扩展至大型邮箱。

## 实施指南

### 使用 EWS 过滤消息

#### 概述
过滤使您能够直接从邮箱中检索仅符合特定条件（如特定主题或日期）的电子邮件。
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**说明**：此代码建立与邮箱的连接，并创建查询以过滤主题中包含 “Newsletter” 且在特定日期之后的电子邮件。

### 如何按今天的日期过滤电子邮件？

SearchFilter.IsEqualTo 用于创建一个过滤器，匹配属性等于给定值的项目。  
DateTimeReceived 是指示电子邮件接收时间的属性。

加载当前日期，在 `DateTimeReceived` 属性上构建 `SearchFilter.IsEqualTo`，并执行查询。这将仅返回在运行代码的当天收到的邮件，使每日处理脚本变得简单。您可以将此过滤器与发件人或主题等其他条件组合，以进一步缩小当天的结果范围。

### 如何按日期范围过滤电子邮件？

SearchFilter.IsGreaterThanOrEqualTo 用于创建一个过滤器，匹配属性值大于或等于指定值的项目。  
SearchFilter.IsLessThanOrEqualTo 用于创建一个过滤器，匹配属性值小于或等于指定值的项目。  
SearchFilter.And 将多个过滤器组合，使所有条件必须满足。

定义开始和结束的 `DateTime`，分别使用 `SearchFilter.IsGreaterThanOrEqualTo` 和 `SearchFilter.IsLessThanOrEqualTo`，然后使用 `SearchFilter.And` 将两者连接。结果集包含所有落在指定时间窗口内的邮件。此方法使您能够检索任意自定义期间的所有通信，例如上一季度或特定项目时间线。

### 如何按特定发件人过滤电子邮件？

SearchFilter.IsEqualTo 用于创建一个过滤器，匹配属性等于给定值的项目。

在 `From` 属性上使用发送者的电子邮件地址创建 `SearchFilter.IsEqualTo`。这会筛选出该联系人的所有邮件，适用于优先收件箱或合规检查。当确切地址未知或按域过滤时，也可以使用 `SearchFilter.ContainsSubstring` 进行部分匹配。

### 如何按特定域过滤电子邮件？

SearchFilter.ContainsSubstring 用于创建一个过滤器，匹配属性包含指定子字符串的项目。

在 `From` 属性上使用域字符串（例如 “@example.com”）的 `SearchFilter.ContainsSubstring`。这会提取所有来自该域的电子邮件，适用于合作伙伴或供应商监控。将此过滤器与日期条件结合，可随时间跟踪特定域的通信，有助于安全审计。

### 如何按特定收件人过滤电子邮件？

SearchFilter.IsEqualTo 用于创建一个过滤器，匹配属性等于给定值的项目。

在 `ToRecipients` 集合上对目标地址使用 `SearchFilter.IsEqualTo`。当需要审计发送到特定邮箱或分发列表的邮件时，这非常方便。处理多个共享相同域的收件人时，也可以使用 `SearchFilter.ContainsSubstring` 进行部分匹配。

### 如何使用 AND 逻辑组合查询？

SearchFilter.And 将多个过滤器组合，使所有条件必须满足。

使用 `SearchFilter.And` 链接多个 `SearchFilter` 对象。例如，将发件人过滤器与主题过滤器组合，以仅检索来自可信发件人的新闻通讯。AND 运算符确保仅返回满足所有指定条件的项目，从而将结果集缩小到最相关的邮件。

### 如何使用 OR 逻辑组合查询？

SearchFilter.Or 合并过滤器，使任意一个条件匹配即可。

在需要任意一个条件匹配时使用 `SearchFilter.Or` 合并过滤器——这非常适合提取来自一组发件人 **或** 包含特定关键字的邮件。使用 OR 逻辑可以扩大搜索范围，捕获多个类别中的所有相关通信，避免遗漏关键信息。

## 常见陷阱与技巧

- **分页至关重要**：处理超过 1,000 条项目的邮箱时，始终使用带页面大小的 `ItemView` 以避免超时。  
- **时区处理**：EWS 返回的日期为 UTC；在比较前转换为本地时区。  
- **避免完整邮箱扫描**：始终在服务器端应用 `SearchFilter`；客户端过滤会浪费带宽和内存。  
- **专业提示**：在应用程序生命周期内缓存 `ExchangeService` 对象，以减少身份验证开销。

## 常见问题

**问：我可以在 Office 365 中使用此方法吗？**  
答：可以，Aspose.Email 通过将服务 URL 指向 `https://outlook.office365.com/EWS/Exchange.asmx` 即可与 Office 365 Exchange Online 配合使用。

**问：Aspose.Email 支持 OAuth 身份验证吗？**  
答：当然——使用 `OAuthCredentials` 可在不存储用户密码的情况下进行身份验证。

**问：我可以处理的最大邮箱大小是多少？**  
答：该 API 能处理 **数 GB** 规模的邮箱；由于采用流式结果，内存消耗保持在低水平。

**问：如何按文件类型过滤附件？**  
答：在 `AttachmentNames` 属性上添加 `SearchFilter.ContainsSubstring`，然后仅遍历匹配的项目。

**问：有没有办法对结果进行排序？**  
答：有——在 `FindItems` 调用中传入 `SortDirection` 和要排序的属性（例如 `DateTimeReceived`）。

---

**最后更新：** 2026-07-17  
**测试版本：** Aspose.Email for Java 24.10  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Email for Java 创建 EWSClient 实例：Exchange Server 集成指南](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [如何使用 Aspose.Email Java 从 Exchange Server 下载邮件](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [使用 Aspose.Email for Java 管理 EWS 邮箱信息：完整指南](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```