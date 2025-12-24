---
date: '2025-12-24'
description: 学习如何使用 Aspose.Email for Java 将日历导出为 PST，包括如何添加与会者、设置开始和结束日期以及高效管理约会。
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: 使用 Aspose.Email for Java 将日历导出为 PST
url: /zh/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 将日历导出为 PST

高效地 **导出日历到 PST** 是在构建需要与 Outlook 或其他 Microsoft 产品共享日程数据的 Java 应用时的常见需求。在本教程中，您将看到如何创建约会、添加与会者、定义开始和结束日期，最后将所有内容保存到 PST 文件——全部使用 Aspose.Email for Java 完成。

## 快速答案
- **主要目标是什么？** 将日历事件导出为 PST 文件。  
- **需要哪个库？** Aspose.Email for Java（v25.4+）。  
- **需要许可证吗？** 是的，合法的 Aspose.Email 许可证可去除评估限制。  
- **可以添加与会者吗？** 当然——使用 `MapiRecipientCollection`。  
- **支持的 Java 版本？** JDK 16 或更高。

## 什么是 **export calendar to pst**？
将日历导出为 PST 意味着将内存中的 `MapiCalendar` 对象转换为 Microsoft Outlook Personal Storage Table（PST）文件。该文件可在 Outlook 中打开、与同事共享，或导入到其他支持 PST 格式的系统中。

## 为什么使用 Aspose.Email for Java 导出日历到 PST？
- **完整的 MAPI 支持** – 在无需安装 Outlook 的情况下创建、修改并保存约会。  
- **跨平台** – 可在 Windows、Linux 和 macOS 上运行。  
- **丰富的 API** – 管理与会者、重复规则、提醒等。  
- **性能优化** – 以低内存占用处理大量事件。

## 前置条件
- **库与依赖**：Aspose.Email for Java 版本 25.4 或更高。  
- **环境**：JDK 16 或更高，使用 Maven 管理依赖。  
- **知识**：基本的 Java 编程以及对 Maven 的了解。

## 如何设置 Aspose.Email for Java
在 `pom.xml` 中添加 Aspose.Email 依赖：

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 许可证获取
通过获取许可证来解锁 Aspose.Email 的全部功能，消除评估限制：

1. **免费试用**：访问 [Aspose 下载页面](https://releases.aspose.com/email/java/) 获取临时许可证。  
2. **临时许可证**：通过 [购买页面](https://purchase.aspose.com/temporary-license/) 申请。  
3. **购买许可证**：考虑从 [Aspose 购买门户](https://purchase.aspose.com/buy) 购买长期使用的许可证。

获取许可证后，在应用程序中初始化它以启用所有功能。

## 如何 **create appointment** (Create Calendar Event Java)

### 步骤 1：定义开始和结束日期（java calendar start date / java calendar end date）
以下方法展示了如何为约会设置开始和结束日期，并返回一个 `MapiCalendar` 对象：

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*说明*：此代码片段创建了一个带有特定地点、主题、描述以及您定义的 **java calendar start date** / **java calendar end date** 的 `MapiCalendar`。

## 如何 **add attendees** (how to add attendees)

### 步骤 2：构建与会者列表
使用 `MapiRecipientCollection` 指定谁应收到会议邀请：

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*说明*：此代码创建了会议，设置组织者，并附加 **how to add attendees** 列表，使每位与会者都能收到正确的邀请。

## 如何 **export calendar to pst** (Create PST with calendar events)

### 步骤 3：创建 PST 文件并添加事件
下面的方法演示了如何创建 Unicode PST 文件并存储普通约会以及带与会者的会议：

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*说明*：此代码片段通过创建 PST 容器、添加预定义的 “Calendar” 文件夹，并插入先前构建的 `MapiCalendar` 对象，实现了 **exports calendar to PST**。

## 实际应用场景
1. **业务排程** – 自动化内部会议的创建与分发。  
2. **活动管理** – 跟踪会议、研讨会及参与者名单。  
3. **CRM 集成** – 将约会同步至客户关系管理工具。  
4. **项目规划** – 将项目里程碑存储为日历项。  
5. **远程团队协作** – 生成 PST 文件以供离线共享。

## 性能注意事项
- **释放对象**：对不再使用的对象进行 dispose，以释放内存。  
- **选择高效集合**：在处理大量与会者列表时使用合适的集合类型。  
- **缓存常用事件**：如果频繁查询 PST，可缓存经常访问的事件。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **未创建 PST 文件** | 检查目标目录的写入权限，并确保文件夹路径已存在。 |
| **与会者未收到邀请** | 确认每个 `MapiRecipient` 使用 `MapiRecipientType.MAPI_TO`，且组织者邮箱有效。 |
| **日期不匹配** | 对开始/结束日期统一使用 `Calendar`，避免在未转换的情况下混用 `java.util.Date` 与其他日期库。 |

## 常见问答

**问：如何快速上手 Aspose.Email for Java？**  
答：按照上文的 Maven 依赖添加方式，引入许可证，然后按照本指南的步骤创建并导出日历事件。

**问：可以自定义 PST 文件的名称和位置吗？**  
答：可以，在 `createPSTWithCalendarEvents()` 方法中修改 `pstFilePath` 变量为系统上任意有效路径。

**问：能为约会添加重复模式吗？**  
答：完全可以——`MapiCalendar` 提供了 `RecurrencePattern` 等属性，您可以在保存前进行配置。

**问：Aspose.Email 是否支持除 PST 之外的其他日历格式？**  
答：支持，您可以使用相应的 API 方法导出为 iCalendar（`.ics`）等其他格式。

**问：可以创建的 PST 文件最大多大？**  
答：使用 Unicode 格式（`FileFormatVersion.Unicode`）时，PST 文件最大可达 2 TB，仅受磁盘空间限制。

---

**最后更新：** 2025-12-24  
**测试环境：** Aspose.Email for Java 25.4（jdk16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}