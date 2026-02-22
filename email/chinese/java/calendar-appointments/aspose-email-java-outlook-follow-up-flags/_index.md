---
date: '2026-02-22'
description: 学习如何使用 Aspose.Email for Java 在 Outlook 中设置跟进标记，包括为收件人设置、读取和删除标记。
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: 如何使用 Aspose.Email for Java 设置 Outlook 跟进标记
url: /zh/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 设置 Outlook Follow Up Flag

## Introduction
如果你曾经为跟踪重要邮件而苦恼，你就会知道 Outlook 的 **outlook follow up flag** 有多么有价值。在本指南中，我们将演示如何使用 Aspose.Email for Java 以编程方式 **how to set an outlook follow up flag**，并且还会介绍如何 **set outlook follow up flag for recipients**，以及在任务完成后如何 **remove an outlook follow up flag**。完成后，你将能够直接从 Java 代码中自动化任务跟踪、提醒和审计日志。

**What you’ll learn**
- 在 Outlook 邮件上创建并应用跟进标记。  
- 为特定收件人设置跟进标记。  
- 将标记标记为已完成并随后移除。  
- 读取标记选项以用于报告或合规。  

让我们在深入代码之前先准备好环境。

## Quick Answers
- **What does “how to set follow‑up” mean?** 为 Outlook 项目添加带有开始、提醒和截止日期的标记。  
- **Which library is required?** Aspose.Email for Java (v25.4 或更新版本)。  
- **Do I need a license?** 是的，完整功能需要试用或购买许可证。  
- **Can I set flags for recipients only?** 当然可以 – 使用 `FollowUpManager.setFlagForRecipients`。  
- **Is it possible to remove a flag later?** 可以，调用 `FollowUpManager.clearFlag`。

## What is an Outlook Follow Up Flag?
Outlook follow up flag 是一种内置的任务标记，可为任何邮件项附加开始日期、提醒和截止日期。它将普通电子邮件转换为可跟踪的操作项，帮助你和团队掌握待处理工作。

## Why Use Aspose.Email for Java?
Aspose.Email 提供纯 Java API，无需安装 Outlook，即可操作 .msg 文件、设置标记并在任何平台上管理任务——非常适合 **automate outlook tasks**、后端服务或与项目管理工具的集成。

## Prerequisites
- **Aspose.Email for Java** 版本 25.4 或更高（亦称 **aspose email java**）。  
- 已安装 **JDK 16+**。  
- 支持 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基础的 Java 知识以及对电子邮件概念的了解。

## Setting Up Aspose.Email for Java
### Maven Configuration
在你的 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email 需要许可证才能用于生产环境：

- **Free trial** – 30 天评估。  
- **Temporary license** – 延长测试。  
- **Full license** – 永久订阅。

在进行任何邮件操作之前初始化许可证：

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Set Outlook Follow Up Flag (Feature 1)
### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我们首先构建一个 `MailMessage`，设置发件人/收件人，然后将其转换为 `MapiMessage` 以进行标记操作。*

### Step 2: Define Follow‑Up Dates (Outlook Flag Reminder)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*这里使用 `Calendar` 类设置开始日期、提醒（即 **outlook flag reminder**）和截止日期。*

### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 对象保存所有标记细节，我们通过 `FollowUpManager.setOptions` 应用它们。*

### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*该邮件以 `.msg` 文件形式保存，并附带标记。*

## How to Set Flag for Recipients (Feature 2)
### Overview
有时你需要标记仅对 **only for recipients** 可见。此示例先将邮件标记为草稿，然后再添加标记。

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*将邮件标记为未发送可确保 Outlook 将其视为草稿。*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*标记现在仅对收件人可见——这是典型的 **flag for recipients** 场景。*

## How to Mark an Outlook Follow Up Flag as Completed (Feature 3)
### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*标记状态更改为 “Completed”，并保存更新后的文件。*

## How to Remove an Outlook Follow Up Flag (Feature 4)
### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*邮件保存后不再包含任何 follow‑up 标记。*

## How to Read Flag Options (Feature 5)
### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 对象现在包含开始、截止和提醒日期，以及标记主题——在需要 **read flag options** 进行报告时非常有用。*

## Practical Applications
- **Task‑Management Integration:** 将标记邮件同步至 Jira、Trello 或 Azure Boards。  
- **Automated Reminders:** 为待处理的跟进生成每日提醒邮件。  
- **Compliance Audits:** 导出标记数据以满足监管报告要求。

## Performance Considerations
- **Date Calculations:** 对于批量处理，请一次性计算日期，而不是在循环内部重复计算。  
- **Resource Management:** 保存邮件后关闭所有流或文件句柄。  
- **Memory Usage:** 将大型邮箱分块处理，以避免堆内存压力。

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| 标记未在 Outlook 中显示 | 邮件保存时未正确设置 `MessageFlags` | 确保在应用收件人标记前将 `setMessageFlags` 设置为 `MSGFLAG_UNSENT`。 |
| 保存时抛出 `AccessDeniedException` | 文件路径错误或缺少写入权限 | 验证输出目录是否存在且应用拥有写入权限。 |
| 日期相差一天 | 时区不匹配 | 使用 `TimeZone.getTimeZone("GMT")` 或始终使用本地区时区。 |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: 它是一个纯 Java API，允许你在无需安装 Outlook 的情况下创建、读取和操作电子邮件文件（MSG、EML 等）。

**Q: How do I obtain a free trial license?**  
A: 访问 [Aspose website](https://releases.aspose.com/email/java/) 下载 30 天试用版。

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook 每条消息仅支持一个标记，但你可以在自定义 MAPI 属性中存储额外的任务数据。

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: 确认 `outputDir` 路径有效且应用拥有写入该位置的权限。

**Q: How can I remove flags from many messages at once?**  
A: 遍历消息集合，对每个 `MapiMessage` 调用 `FollowUpManager.clearFlag`。

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}