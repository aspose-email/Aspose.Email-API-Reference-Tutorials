---
date: '2025-12-19'
description: 了解如何使用 Aspose.Email for Java 在 Outlook 中设置跟进标记，包括如何高效地设置 Outlook 跟进标记和删除
  Outlook 跟进标记。
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: 如何使用 Aspose.Email for Java 在 Outlook 中设置跟进标记
url: /zh/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 在 Outlook 中设置跟进标记

## 介绍
如果你曾经为跟踪重要邮件而苦恼，你就会知道 Outlook 的跟进标记有多么有价值。在本指南中，我们将展示 **如何使用 Aspose.Email for Java 编程方式设置跟进标记**，并且还会讲解如何 **为收件人设置 Outlook 跟进标记**，以及在任务完成后 **如何移除 Outlook 跟进标记**。阅读完本指南后，你将能够直接在 Java 代码中实现任务跟踪、提醒和审计日志的自动化。

**你将学到的内容**
- 在 Outlook 邮件上创建并应用跟进标记。  
- 为特定收件人设置跟进标记。  
- 将标记标记为已完成并随后移除。  
- 读取标记选项以用于报告或合规。  

在深入代码之前，让我们先准备好开发环境。

## 快速回答
- **“how to set follow-up” 是什么意思？** 为 Outlook 项目添加带有开始、提醒和截止日期的标记。  
- **需要哪个库？** Aspose.Email for Java（v25.4 或更高）。  
- **需要许可证吗？** 是的，完整功能需要试用或正式许可证。  
- **可以仅为收件人设置标记吗？** 当然——使用 `FollowUpManager.setFlagForRecipients`。  
- **以后可以移除标记吗？** 可以，调用 `FollowUpManager.clearFlag`。

## 什么是跟进标记？
跟进标记是 Outlook 的一项功能，它将电子邮件标记为任务，并可选择附加开始、提醒和截止日期。它帮助你和团队保持对待办事项的关注。

## 为什么使用 Aspose.Email for Java？
Aspose.Email 提供纯 Java API，无需安装 Outlook，即可在任何平台上操作 .msg 文件、设置标记和管理任务——非常适合后端服务、自动化工作流或与项目管理工具的集成。

## 前置条件
- **Aspose.Email for Java** 版本 25.4 或更高。  
- 已安装 **JDK 16+**。  
- 支持 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基础的 Java 知识以及对电子邮件概念的了解。

## 设置 Aspose.Email for Java
### Maven 配置
在你的 `pom.xml` 中添加以下依赖：

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

## 实现指南

### 如何设置跟进标记（功能 1）
#### 概述
本节将指导你创建 Outlook 邮件、定义开始/提醒/截止日期，并应用跟进标记。

#### 步骤 1：创建并初始化邮件
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我们首先构建 `MailMessage`，设置发件人/收件人，然后将其转换为 `MapiMessage` 以便操作标记。*

#### 步骤 2：定义跟进日期
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*这里使用 `Calendar` 类设置开始、提醒和截止日期。*

#### 步骤 3：应用跟进选项
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 对象保存所有标记细节，我们通过 `FollowUpManager.setOptions` 将其应用。*

#### 步骤 4：保存邮件
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*邮件以 `.msg` 文件形式保存，标记已附加。*

### 为收件人设置 Outlook 跟进标记（功能 2）
#### 概述
有时你只需要为收件人设置标记。此示例先将邮件标记为草稿，然后添加标记。

#### 步骤 1：标记为草稿
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*将邮件标记为未发送可确保 Outlook 将其视为草稿。*

#### 步骤 2：设置收件人标记
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*标记现在仅对收件人可见。*

### 将 Outlook 跟进标记标记为已完成（功能 3）
#### 概述
任务完成后，你可以以编程方式将标记标记为已完成。

#### 步骤 1：加载邮件
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### 步骤 2：标记为已完成并保存
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*标记状态变为 “Completed”，并将更新后的文件保存。*

### 移除 Outlook 跟进标记（功能 4）
#### 概述
如果标记不再需要，你可以彻底清除它。

#### 步骤 1：加载并清除标记
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*邮件保存后不再包含任何跟进标记。*

### 读取跟进标记选项（功能 5）
#### 概述
为审计或报告目的，你可能需要读取现有的标记设置。

#### 步骤 1：检索选项
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 对象现在包含开始、截止、提醒日期以及标记主题。*

## 实际应用场景
- **任务管理集成：** 将标记的邮件同步至 Jira、Trello 或 Azure Boards。  
- **自动提醒：** 为待处理的跟进生成每日提醒邮件。  
- **合规审计：** 导出标记数据用于监管报告。

## 性能考虑
- **日期计算：** 在批处理时一次性计算日期，而不是在循环内部。  
- **资源管理：** 保存邮件后关闭所有流或文件句柄。  
- **内存使用：** 将大型邮箱分块处理，以避免堆内存压力。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 标记未在 Outlook 中显示 | 邮件保存时缺少正确的 `MessageFlags` | 在应用收件人标记前确保 `setMessageFlags` 设置为 `MSGFLAG_UNSENT`。 |
| 保存时抛出 `AccessDeniedException` | 文件路径错误或缺少写入权限 | 确认输出目录存在且应用具有写入权限。 |
| 日期偏差一天 | 时区不匹配 | 使用 `TimeZone.getTimeZone("GMT")` 或始终使用本地时区。 |

## 常见问答
**问：什么是 Aspose.Email for Java？**  
答：它是一个纯 Java API，允许你在无需安装 Outlook 的情况下创建、读取和操作邮件文件（MSG、EML 等）。

**问：如何获取免费试用许可证？**  
答：访问 [Aspose 网站](https://releases.aspose.com/email/java/) 下载 30 天试用版。

**问：可以在同一邮件上设置多个跟进标记吗？**  
答：Outlook 每封邮件仅支持一个标记，但你可以在自定义 MAPI 属性中存储额外的任务数据。

**问：设置标记后邮件未保存，应该检查什么？**  
答：确认 `outputDir` 路径有效且应用拥有写入该位置的权限。

**问：如何一次性移除多封邮件的标记？**  
答：遍历邮件集合，对每个 `MapiMessage` 调用 `FollowUpManager.clearFlag`。

## 资源
- [文档](https://reference.aspose.com/email/java/)
- [下载 Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email 免费试用](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**最后更新：** 2025-12-19  
**测试环境：** Aspose.Email for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}