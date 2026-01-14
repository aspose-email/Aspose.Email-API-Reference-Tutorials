---
date: '2026-01-01'
description: 学习如何使用 Aspose.Email for Java 创建 MAPI 日历并将其保存到 PST。一步步的代码指南，涵盖循环（重复）和收件人。
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: 如何使用 Aspose.Email 在 Java 中创建 MAPI 日历 – 将日历保存到 PST
url: /zh/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email 创建 MAPI calendar java 并将日历保存到 PST

## 介绍

您是否希望在 Java 应用程序中简化日历自动化？使用 **Aspose.Email for Java**，您可以 **create MAPI calendar java** 项目，定义重复模式，添加与会者，并通过几行代码 **save calendar to PST** 文件。本教程将带您完整了解整个过程——从库的设置到生成可分发的完整日历条目。

### 您将学习
- 如何使用 Aspose.Email **create MAPI calendar java** 事件。  
- 配置每日、每周或自定义的重复模式。  
- 向日历邀请中添加收件人（组织者、与会者）。  
- 通过 **saving calendar to PST** 将日历项持久化，以实现 Outlook 兼容性。

让我们深入了解并准备好您的开发环境。

## 快速答复
- **哪个库？** Aspose.Email for Java  
- **主要目标？** Create MAPI calendar java 并 **save calendar to PST**  
- **先决条件？** Java 8+、Maven、Aspose.Email 许可证  
- **典型实现时间？** 基本事件 10‑15 分钟  
- **我可以添加重复吗？** 是的 – 每日、每周、每月等。

## 什么是 Java 中的 MAPI Calendar？
MAPI（消息应用程序编程接口）日历对象表示一个兼容 Outlook 的会议或约会。使用 Aspose.Email，您可以以编程方式构建这些对象，实现与 Exchange、Outlook 或任何使用 PST 文件的客户端的无缝集成。

## 为什么使用 Aspose.Email 进行日历自动化？
- **完整的 Outlook 兼容性** – 生成的项目可在 Outlook、OWA 和移动客户端中使用。  
- **丰富的重复支持** – 开箱即用的每日、每周、每月和自定义模式。  
- **无外部依赖** – 纯 Java 库，无需 COM 互操作。  
- **高性能** – 高效处理大型 PST 文件和批量操作。

## 先决条件

在开始之前，请确保您已具备：

### 必需的库
- **Aspose.Email for Java**：版本 25.4 或更高。

### 环境设置要求
- Java IDE，例如 IntelliJ IDEA 或 Eclipse。  
- 已安装 Maven 以管理依赖项。

### 知识先决条件
- 基本的 Java 编程技能。  
- 熟悉面向对象的概念。

## 设置 Aspose.Email for Java

将 Aspose.Email Maven 依赖添加到您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取

Aspose.Email 提供免费试用，但许可证可解锁全部功能：

- **免费试用**：30 天无限制测试。  
- **临时许可证**：如果需要更多时间，可通过 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 请求。  
- **购买**：从 [购买页面](https://purchase.aspose.com/buy) 购买永久许可证。

### 基本初始化

添加依赖后，使用您的许可证文件初始化库：

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 实施指南

现在您已经准备就绪，让我们 **create MAPI calendar java** 并 **save calendar to PST**。

### 使用重复创建 MAPI Calendar

#### 概述

我们将构建一个日历事件，应用每日重复，添加与会者，最后将其存储在 PST 文件中。

#### 步骤实现

1. **Initialize Date and Recurrence Pattern**  

   首先，定义开始时间并设置每日重复：

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *说明*：`MapiCalendarEventRecurrence` 保存重复细节；我们通过 `MapiCalendarDailyRecurrencePattern` 选择每日模式。

2. **Set Up Recipients**  

   添加应收到会议邀请的人员：

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *说明*：`MapiCollection` 存储每个与会者；`MAPI_TO` 将其标记为主要收件人。

3. **Create the MAPI Calendar Item**  

   使用所有必需细节构建日历对象：

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *说明*：构造函数需要组织者、主题、地点、开始/结束时间、描述、收件人列表和重复信息。

4. **Save to PST File**  

   最后，通过 **saving calendar to PST** 持久化日历：

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *说明*：`PersonalStorage.create` 生成新的 PST 文件，`addMapiMessageItem` 将日历条目插入 “Calendar” 文件夹。

### 故障排除提示
- 验证许可证路径；无效的许可证会限制功能。  
- 确保收件人电子邮件地址格式正确，以避免邀请失败。  
- 操作完成后关闭 PST (`pst.dispose()`) 以释放文件句柄。

## 实际应用

以下是 **creating MAPI calendar java** 和 **saving calendar to PST** 的常见场景：

1. **自动会议调度** – 为项目团队生成循环会议邀请，无需手动操作。  
2. **事件管理平台** – 将会议会话导出为 Outlook 兼容的日历项。  
3. **CRM 集成** – 将 CRM 系统中的客户预约直接同步到 Outlook，通过 PST 文件。

## 性能考虑

- **资源管理**：使用后释放 `PersonalStorage` 对象，以防止文件锁定。  
- **批处理**：对于大批量，异步或分块处理日历项，以保持低内存使用。

## 结论

您现在已经学习了如何使用 Aspose.Email **create MAPI calendar java** 对象，配置重复，添加与会者，并 **save calendar to PST**。此方法使您的 Java 应用程序能够自动化复杂的排程工作流，并保持 Outlook 兼容性。

欲深入了解，请查阅官方 [documentation](https://reference.aspose.com/email/java/)。

## 常见问题

### 问：我可以创建每周重复模式吗？
- **答**：可以！使用 `MapiCalendarWeeklyRecurrencePattern` 定义每周重复。

### 问：如何处理事件重复中的例外情况？
- **答**：在重复对象上调用 `setExceptions()`，指定偏离模式的日期。

### 问：是否可以更新现有的日历项？
- **答**：完全可以。从 PST 中加载该项，修改属性后再保存回去。

### 问：我可以加密 PST 文件吗？
- **答**：可以，Aspose.Email 允许在创建 PST 时对 `PersonalStorage` 设置密码。

### 问：如果需要向日历事件添加附件怎么办？
- **答**：在保存之前使用 `calendar.getAttachments().addFileAttachment("path/to/file")`。

## 资源
- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**最后更新：** 2026-01-01  
**测试环境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
