---
date: '2026-03-20'
description: 学习如何使用 Aspose.Email for Java 创建具有每日循环和例外的 Outlook 日历，并将日历保存为 PST。
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 使用 Java 创建 Outlook 日历，包含每日重复和例外
url: /zh/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何创建带有每日循环和例外的 Outlook calendar Java

管理循环事件可能非常具有挑战性，尤其是当您需要一个 **Outlook calendar Java** 能够支持每日循环模式并处理偶发的例外情况时。在本教程中，您将学习如何创建 Outlook calendar Java 对象、配置每日循环、添加例外实例，最后使用 Aspose.Email for Java **将日历保存到 PST**。完成后，您将拥有一段可复用的代码片段，可直接嵌入任何基于 Java 的调度服务中。

## 快速回答
- **使用哪个库？** Aspose.Email for Java  
- **主要任务？** 创建带有每日循环和例外的 Outlook calendar Java  
- **前置 JDK？** Java 16 或更高版本  
- **可以为例外附加文件吗？** 可以，使用 `MapiCalendarExceptionInfo`  
- **日历存放在哪里？** 通过 `PersonalStorage` 保存到 PST 文件中  

## 什么是 Outlook calendar java？
Outlook calendar Java 对象（实现为 MAPI 日历）遵循与 Microsoft Outlook 约会相同的标准。它能够存储丰富的循环规则、例外处理、与会者以及附件，是企业级调度的理想选择。

## 为什么使用 Aspose.Email for Java？
Aspose.Email 提供纯 Java API，让您无需安装 Outlook 即可操作 MAPI 对象。这种 **aspose email tutorial java** 方式支持服务器端生成 PST 文件、自动化会议系列以及对循环逻辑的完整控制。

## 前置条件

在开始之前，请确保已完成以下准备工作：
- **Aspose.Email 库**：版本 25.4（或更高）— 可通过 Maven 或直接下载获取。  
- **Java 开发工具包 (JDK)**：JDK 16 或更新版本。  
- **IDE**：IntelliJ IDEA、Eclipse、NetBeans 或任意支持 Java 的编辑器。

### 必要的库和依赖

若使用 Maven 将 Aspose.Email 集成到项目中，请在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取

使用 Aspose.Email 需要许可证：
- **免费试用** — 免费体验全部功能。  
- **临时许可证** — 申请后可进行延长评估。  
- **正式许可证** — 购买后用于生产环境部署。

## 设置 Aspose.Email for Java

首先，配置您的开发环境：

1. 确认已安装 JDK 16 并配置 `JAVA_HOME`。  
2. 将 Maven 依赖（或下载的 JAR 包）添加到项目中。  

下面是一个简短示例，展示如何加载许可证文件：

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

## 实现指南

### 创建带有每日循环和例外的 Outlook calendar java

#### 概述
此功能可让您自动化循环约会，同时仍能跳过或修改特定实例。

#### 步骤实现

**1. 设置事件开始日期**  
确定系列的起始时间：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. 创建 MAPI Calendar 对象**  
提供地点、主题和描述：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 定义每日循环模式**  
配置事件每天重复：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 为循环添加例外**  
指定需要排除（或修改）的日期：

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

### 为日历例外附加文件

#### 概述
您可以为任意例外实例附加支持文档（如议程）。

**1. 创建并附加文件**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### 将 Outlook calendar java 保存到 PST（save calendar to pst）

#### 概述
将日历持久化到 PST 文件，便于 Outlook 或其他客户端读取。

**1. 创建并保存日历到 PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 实际应用场景
- **企业调度** — 自动化会议系列，自动跳过节假日。  
- **项目管理** — 跟踪带有偶尔日期变动的循环里程碑。  
- **活动策划** — 管理多日会议，处理部分会议取消或重新安排。

### 集成可能性
将 Aspose.Email 与 CRM 平台、任务管理 API 或自定义工作流引擎结合，实现端到端自动化。

## 性能注意事项
- **释放资源** – 始终在 `PersonalStorage` 上调用 `dispose()` 以释放文件句柄。  
- **流的使用** – 推荐使用 `ByteArrayOutputStream` 或文件流，避免一次性加载整个 PST 到内存。  
- **异步操作** – 对于批量日历生成，可在后台线程中执行创建逻辑，以保持 UI 响应。

## 结论
通过本指南，您已经掌握了如何 **创建 outlook calendar java** 对象并实现每日循环、添加例外、附加文件以及 **将日历保存到 PST**。这些能力让您能够构建强大的调度功能，而无需直接操作 Outlook。

### 后续步骤
- 试验每周或每月循环模式。  
- 探索更多 MAPI 属性，如与会者、提醒和类别。  
- 查阅 Aspose.Email 的完整 API 文档，了解更高级的使用场景。

## 常见问题

**Q: 库是否支持时区感知的约会？**  
A: 支持，您可以在 `MapiCalendar` 上设置 `StartTimeZone` 和 `EndTimeZone` 属性。

**Q: 能否以编程方式删除循环系列中的单个实例？**  
A: 可以，使用循环模式的 `DeletedInstanceDates` 集合标记特定日期为已删除。

**Q: 使用 Aspose.Email 创建的 PST 文件大小是否有限制？**  
A: PST 文件遵循 Unicode 格式的默认上限（约 2 GB），但可通过 `PersonalStorage` 设置调整更大容量。

**Q: 如何向会议请求添加与会者？**  
A: 创建 `MapiRecipient` 对象，将其 `RecipientType` 设置为 `MapiRecipientType.MAPI_TO`，并加入 `MapiMessage` 的 `Recipients` 集合。

**Q: 是否支持循环任务（而不仅仅是约会）？**  
A: 支持，Aspose.Email 还提供具有相似循环功能的 `MapiTask`。

**Q: 我可以将本指南作为 aspose email tutorial java 系列的一部分吗？**  
A: 完全可以——本指南中的步骤是任何涉及日历创建的 Aspose.Email Java 教程的核心内容。

## 资源
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**最后更新：** 2026-03-20  
**测试环境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}