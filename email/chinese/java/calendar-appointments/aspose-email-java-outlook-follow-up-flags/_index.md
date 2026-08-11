---
date: '2026-07-27'
description: 了解如何使用 Aspose.Email for Java 设置 Outlook Flag Java，涵盖标志创建、收件人标志、完成、删除和读取选项。
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: 使用 Aspose.Email for Java 设置 Outlook Flag Java。本指南展示了如何高效地创建、读取、完成和删除
  Outlook follow‑up flags。
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: 设置 Outlook Flag Java – 完整的 Aspose.Email 编程指南
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: 设置 Outlook Flag Java – 完整的 Aspose.Email 编程指南
url: /zh/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 设置 Outlook 标记（Java）

## 介绍
如果您需要以编程方式 **set outlook flag java**，这里就是正确的地方。Outlook 的跟进标记可以将普通邮件转换为可追踪的任务，而 Aspose.Email for Java 让您在没有安装 Outlook 的情况下管理这些标记。在本教程中，我们将演示如何创建、读取、完成以及最终移除标记，并说明如何为特定收件人应用标记。完成后，您将拥有一个可复用的 Java 代码片段，直接在后端服务中实现任务跟踪自动化。

## 快速答案
- **“set outlook flag java” 是什么意思？** 通过 Java 代码为 Outlook 项目添加包含开始、提醒和截止日期的标记。  
- **需要哪个库？** Aspose.Email for Java (v25.4 或更高)。  
- **需要许可证吗？** 需要——试用版可用于评估，但生产环境必须使用购买的许可证。  
- **可以只为收件人设置标记吗？** 完全可以——使用 `FollowUpManager.setFlagForRecipients`。  
- **以后可以移除标记吗？** 可以——调用 `FollowUpManager.clearFlag`。

## 什么是 Outlook 跟进标记？
Outlook 跟进标记是一种内置的任务标记，可为任意邮件项附加开始日期、提醒和截止日期。它将电子邮件转化为可追踪的行动项，帮助您和团队及时处理待办工作。

## 为什么使用 Aspose.Email for Java？
Aspose.Email for Java 支持 **70+ 种邮件格式**（包括 MSG、EML、MHTML 和 TNEF），并且在普通的 8 核服务器上能够 **每分钟处理超过 100,000 条消息**，且无需在主机上安装 Outlook。这使其非常适合后端自动化、合规报告以及与项目管理工具的集成。

## 前置条件
- **Aspose.Email for Java** 版本 25.4 或更高。  
- 已安装 **JDK 16+**。  
- 支持 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基础的 Java 知识以及对邮件概念的了解。

## 设置 Aspose.Email for Java
### Maven 配置
在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取
Aspose.Email 在生产环境下需要许可证：

- **免费试用** – 30 天评估。  
- **临时许可证** – 延长测试。  
- **正式许可证** – 永久订阅。

在进行任何邮件操作之前初始化许可证：

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## 设置 Outlook 标记 Java（功能 1）
### 直接答案
加载 `MailMessage`，将其转换为 `MapiMessage`，配置 `FollowUpOptions`，然后调用 `FollowUpManager.setOptions`。只需几行 Java 代码即可创建完整标记的 Outlook 项目。

### 步骤 1：创建并初始化消息
`MailMessage` 是 Aspose.Email 的高级类，用于表示电子邮件。构建完消息后，将其转换为 `MapiMessage` 以进行标记操作。

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我们首先构建 `MailMessage`，设置发件人/收件人，然后将其转换为 `MapiMessage` 以进行标记操作。*

### 步骤 2：定义跟进日期（Outlook 标记提醒）
`FollowUpOptions` 保存开始、提醒和截止日期。使用 Java 的 `Calendar` 设置精确的时间戳。

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*这里使用 `Calendar` 类设置开始时间、提醒（即 **outlook flag reminder**）和截止日期。*

### 步骤 3：应用跟进选项
`FollowUpManager.setOptions` 方法将标记附加到 `MapiMessage`。

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 对象包含所有标记细节，我们通过 `FollowUpManager.setOptions` 将其应用。*

### 步骤 4：保存消息
将标记后的消息保存为 `.msg` 文件，以便 Outlook 显示标记。

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*消息以 `.msg` 文件形式保存，标记已附加。*

## 如何为收件人设置标记（功能 2）？
在将消息标记为草稿后，使用 `FollowUpManager.setFlagForRecipients`。此方法仅在收件人的副本上添加跟进标记，发送者的视图保持不变。需要在应用标记前将 `MessageFlags.MSGFLAG_UNSENT` 设置为未发送状态。您还可以在调用方法前使用 `FollowUpOptions` 对象自定义开始、提醒和截止日期。

### 直接答案
使用 `MessageFlags.MSGFLAG_UNSENT` 将消息标记为草稿，然后调用 `FollowUpManager.setFlagForRecipients`。Outlook 只会在收件人侧显示标记，发送者侧不显示。

### 概述
有时您希望标记 **仅对收件人可见**。本示例先将消息标记为草稿，然后添加标记。

#### 步骤 1：标记为草稿
`MessageFlags` 是控制消息状态的 MAPI 枚举。设置 `MSGFLAG_UNSENT` 告诉 Outlook 该项目是草稿。

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*将消息标记为未发送可确保 Outlook 将其视为草稿。*

#### 步骤 2：设置收件人标记
`FollowUpManager.setFlagForRecipients` 将标记专门附加到收件人的副本。

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*标记现在仅对收件人可见——典型的 **flag for recipients** 场景。*

## 如何将 Outlook 跟进标记标记为已完成（功能 3）？
将 `.msg` 文件加载到 `MapiMessage`，然后调用 `FollowUpManager.completeFlag`。这会将标记状态更新为 Completed，并在 Outlook 中显示复选标记。完成后保存消息以持久化更改。如有审计需求，可通过设置 `FlagCompleteTime` 属性来指定完成时间。

### 直接答案
加载已有的 `.msg` 文件到 `MapiMessage`，调用 `FollowUpManager.completeFlag`，然后保存文件。标记状态变为 “Completed”，在 Outlook 中显示复选标记。

### 步骤 1：加载消息
`MapiMessage` 能读取已保存的 `.msg` 文件，提供对其 MAPI 属性的完整访问。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 步骤 2：标记为已完成并保存
`FollowUpManager.completeFlag` 更新标记状态，随后持久化更改。

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*标记状态变为 “Completed”，更新后的文件已保存。*

## 如何移除 Outlook 跟进标记（功能 4）？
使用 `MapiMessage` 打开 `.msg` 文件，调用 `FollowUpManager.clearFlag`，然后保存消息。此操作会删除所有与标记相关的 MAPI 属性，Outlook 将不再显示任何跟进指示。适用于任务被取消或不再相关的情况。请同时清除任何自定义提醒属性，以免残留通知。

### 直接答案
使用 `MapiMessage` 打开 `.msg` 文件，调用 `FollowUpManager.clearFlag`，并保存文件。消息将不再在 Outlook 中显示任何跟进指示。

### 步骤 1：加载并清除标记
`FollowUpManager.clearFlag` 移除消息中所有与标记相关的属性。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*消息已保存，且不再包含任何跟进标记。*

## 如何读取标记选项（功能 5）？
在加载的 `MapiMessage` 上调用 `FollowUpManager.getOptions`，即可获得包含开始、截止、提醒日期以及标记主题的 `FollowUpOptions` 对象。此对象可用于显示或记录标记详情，适合报告和合规审计。

### 直接答案
对已加载的 `MapiMessage` 使用 `FollowUpManager.getOptions`，获取包含开始、截止、提醒日期和标记主题的 `FollowUpOptions` 对象。此信息对报告或合规审计非常有用。

### 步骤 1：检索选项
返回的 `options` 对象提供了标记的完整配置信息。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 对象现在包含开始、截止和提醒日期，以及标记主题——在需要 **read flag options** 进行报告时非常实用。*

## 实际应用场景
- **任务管理集成：** 将标记邮件同步到 Jira、Trello 或 Azure Boards。  
- **自动提醒：** 为待处理的跟进生成每日提醒邮件。  
- **合规审计：** 导出标记数据用于监管报告，利用程序化读取标记选项的能力。

## 性能考虑
- **日期计算：** 在批处理时一次性计算日期，而不是在循环内部重复计算。  
- **资源管理：** 保存消息后关闭所有流或文件句柄。  
- **内存使用：** 将大型邮箱分块处理，以避免堆内存压力；Aspose.Email 能在不将整个文件加载到内存的情况下处理数百页的邮箱。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 标记未在 Outlook 中显示 | 消息保存时未正确设置 `MessageFlags` | 在应用收件人标记前确保 `setMessageFlags` 设置为 `MSGFLAG_UNSENT`。 |
| 保存时抛出 `AccessDeniedException` | 文件路径错误或缺少写入权限 | 确认输出目录存在且应用具有写入权限。 |
| 日期相差一天 | 时区不匹配 | 使用 `TimeZone.getTimeZone("GMT")` 或始终使用本地时区。 |

## 常见问答
**问：什么是 Aspose.Email for Java？**  
答：它是一个纯 Java API，能够在不安装 Outlook 的情况下创建、读取和操作邮件文件（MSG、EML 等）。

**问：如何获取免费试用许可证？**  
答：访问 [Aspose 网站](https://releases.aspose.com/email/java/) 下载 30 天试用版。

**问：可以在同一邮件上设置多个跟进标记吗？**  
答：Outlook 每封邮件仅支持一个标记，但您可以在自定义 MAPI 属性中存储额外的任务数据。

**问：设置标记后消息未保存，我该检查什么？**  
答：确认 `outputDir` 路径有效且应用拥有写入该位置的权限。

**问：如何一次性移除多封邮件的标记？**  
答：遍历消息集合，对每个 `MapiMessage` 调用 `FollowUpManager.clearFlag`。

## 资源
- [文档](https://reference.aspose.com/email/java/)
- [下载 Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email 免费试用](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**最后更新：** 2026-07-27  
**测试环境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Email for Java 管理 Outlook 类别 - 综合指南](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [使用 Aspose.Email 创建 Outlook 笔记 Java – 完整指南](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [使用 Aspose.Email for Java 在 Microsoft Exchange 中创建任务：完整指南](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}