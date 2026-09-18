---
date: '2026-09-17'
description: 了解如何使用 Java 创建 outlook 日历，设置 daily recurrence 和 exceptions，并使用 Aspose.Email
  for Java 将日历保存为 PST。
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: 使用 Aspose.Email 在 Java 中创建 outlook 日历。通过分步指南学习 daily recurrence、exception
  handling 以及保存为 PST 的方法。
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: 在 Java 中创建 outlook 日历，支持 daily recurrence 和 exceptions
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: 使用 Java 创建 outlook 日历，支持 daily recurrence 和 exceptions
url: /zh/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 outlook calendar java（每日重复和例外）

有效管理重复事件可能具有挑战性，尤其是当您需要一个支持每日重复模式和偶尔例外的 **outlook calendar java** 时。在本教程中，您将学习如何使用 Aspose.Email for Java 创建 Outlook calendar Java 对象、配置每日重复、添加例外实例，最后 **save calendar to PST**。完成后，您将拥有一个可重复使用的代码片段，可直接嵌入任何基于 Java 的调度服务中。

## 快速答案
- **使用的库？** Aspose.Email for Java  
- **主要任务？** Create an Outlook calendar Java with daily recurrence and exceptions  
- **前置 JDK？** Java 16 or higher  
- **可以在例外中附加文件吗？** Yes, using `MapiCalendarExceptionInfo`  
- **日历存储在哪里？** In a PST file via `PersonalStorage`  

## 什么是 Outlook calendar java？
Outlook calendar Java 对象是对 Outlook 约会的编程表示，基于 MAPI（Messaging Application Programming Interface）规范构建，包含主题、地点、开始/结束时间、重复规则、与会者和附件等属性。该对象可以被操作、序列化，并存储在 PST 文件中，无需 Outlook。

## 为什么使用 Aspose.Email for Java？
Aspose.Email for Java 让您无需安装 Outlook 即可操作 MAPI 对象。该库支持 **50+ MAPI 属性**，能够在 **2 秒** 内生成最大 **2 GB** 的 Unicode PST 文件（针对典型约会数据），并可在任何支持 Java 16+ 的平台上运行。这种纯 Java 方法实现了服务器端日历创建、自动化会议系列以及对重复逻辑的完整控制。

## 前置条件

在开始之前，请确保您已完成以下设置：
- **Aspose.Email 库**：Version 25.4（或更高）– 可通过 Maven 或直接下载获取。  
- **Java 开发工具包 (JDK)**：JDK 16 或更高。  
- **IDE**：IntelliJ IDEA、Eclipse、NetBeans，或任何兼容 Java 的编辑器。

### 必需的库和依赖

要使用 Maven 将 Aspose.Email 集成到项目中，请在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取

使用 Aspose.Email，您需要获得许可证：
- **免费试用** – 免费探索所有功能。  
- **临时许可证** – 申请以进行延长评估。  
- **正式许可证** – 购买用于生产部署。

## 设置 Aspose.Email for Java

首先，设置您的环境：

1. 验证已安装 JDK 16 并配置 `JAVA_HOME`。  
2. 将 Maven 依赖（或下载的 JAR）添加到项目中。  

下面是一个小示例，展示如何加载许可证文件：

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## 实施指南

### 创建 outlook calendar java（每日重复和例外）

#### 概述
此功能让您能够自动化重复约会，同时仍可跳过或修改特定实例。

#### 步骤实现

**1. 设置事件开始日期**  
确定系列应何时开始：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. 创建 MAPI 日历对象**  
`MapiCalendar` 类是内存中表示单个日历项的顶层对象。提供地点、主题和描述：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 定义每日重复模式**  
`MapiCalendarRecurrencePattern` 类存储每天重复约会的规则。将事件配置为每日重复：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 为重复添加例外**  
`MapiCalendarExceptionInfo` 描述与模式偏离的单个出现——可以是排除或更改。指定应排除（或更改）的日期：

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### 将文件附加到日历例外

#### 概述
您可以将支持文档（例如议程）附加到任何例外实例。

**1. 创建并附加文件**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## 将 outlook calendar java 保存至 PST（save calendar to pst）

#### 概述
将日历持久化到 PST 文件，以便 Outlook 或其他客户端读取。

**1. 创建并保存日历至 PST**  
`PersonalStorage` 类提供创建新 PST 文件并向其添加 MAPI 项目的方法。

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 实际应用
- **企业排程** – 自动化会议系列，自动跳过假期。  
- **项目管理** – 跟踪带有偶尔日期变动的重复里程碑。  
- **活动策划** – 管理多天会议，部分议程被取消或重新安排。

### 集成可能性
将 Aspose.Email 与 CRM 平台、任务管理 API 或自定义工作流引擎结合，实现端到端自动化。

## 性能考虑
- **释放资源** – 始终在 `PersonalStorage` 上调用 `dispose()` 以释放文件句柄。  
- **流的使用** – 优先使用 `ByteArrayOutputStream` 或文件流，以避免将整个 PST 加载到内存。  
- **异步操作** – 对于批量日历生成，将创建逻辑放在后台线程运行，以保持 UI 响应。

## 结论
通过本指南，您现在了解如何 **create outlook calendar java** 对象的每日重复、添加例外、附加文件，并 **save calendar to PST**。这些功能让您无需直接接触 Outlook 即可构建强大的调度特性。

### 下一步
- 尝试每周或每月的重复模式。  
- 探索更多 MAPI 属性，如与会者、提醒和类别。  
- 查阅 Aspose.Email 的完整 API 文档，了解更高级的场景。

## 常见问题

**Q: 库是否支持时区感知的约会？**  
A: 是的，您可以在 `MapiCalendar` 上设置 `StartTimeZone` 和 `EndTimeZone` 属性。

**Q: 我可以以编程方式删除重复系列中的单个出现吗？**  
A: 使用重复模式上的 `DeletedInstanceDates` 集合标记特定日期为已删除。

**Q: 使用 Aspose.Email 创建的 PST 文件大小是否有限制？**  
A: PST 文件遵循 Unicode 格式限制（默认最多 2 GB），但可通过 `PersonalStorage` 设置配置更大尺寸。

**Q: 如何向会议请求添加与会者？**  
A: 创建 `MapiRecipient` 对象，将其 `RecipientType` 设置为 `MapiRecipientType.MAPI_TO`，并将其添加到 `MapiMessage` 的 `Recipients` 集合中。

**Q: 是否支持重复任务（不仅限于约会）？**  
A: 是的，Aspose.Email 还提供具有类似重复功能的 `MapiTask`。

**Q: 我可以将本指南作为 Aspose.Email Java 教程系列的一部分吗？**  
A: 当然可以——这里展示的步骤是任何涉及日历创建的 Aspose.Email Java 教程的核心部分。

## 资源
- [Aspose.Email for Java 文档](https://reference.aspose.com/email/java/)
- [下载 Aspose.Email](https://releases.aspose.com/email/java/)
- [购买许可证](https://purchase.aspose.com/buy)
- [免费试用版](https://releases.aspose.com/email/java/)
- [申请临时许可证](https://purchase.aspose.com/temporary-license/)
- [Aspose 支持论坛](https://forum.aspose.com/c/email/10)

---

**最后更新：** 2026-09-17  
**测试环境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Email 导出 Outlook 日历 PST – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [如何使用 Aspose.Email 创建 Java 日历项](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [使用 Aspose.Email for Java 创建日历共享邀请](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}