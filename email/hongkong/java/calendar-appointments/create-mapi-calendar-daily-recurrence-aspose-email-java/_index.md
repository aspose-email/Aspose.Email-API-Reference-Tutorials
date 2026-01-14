---
date: '2025-12-20'
description: 學習如何使用 Aspose.Email for Java 建立 MAPI 行事曆、管理每日重複模式，並處理例外情況。
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 使用 Java 建立 MAPI 行事曆（每日重複與例外）
url: /zh-hant/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用每日重複與例外建立 mapi calendar java

有效管理重複事件可能相當具挑戰性，尤其在需要例外或變更時更是如此。在本教學中，您將 **create mapi calendar java** 物件、設定每日重複規則，並使用 Aspose.Email for Java 新增例外。您將學會如何在應用程式中無縫自動化排程任務。

## Quick Answers
- **Which library?** Aspose.Email for Java  
- **Primary task?** Create a MAPI calendar with daily recurrence and exceptions  
- **Prerequisite JDK?** Java 16 or higher  
- **Can I attach files to exceptions?** Yes, using `MapiCalendarExceptionInfo`  
- **Where is the calendar stored?** In a PST file via `PersonalStorage`

### What is a MAPI calendar?
MAPI（Messaging Application Programming Interface）行事曆是 Microsoft Outlook 及其他郵件客戶端用來儲存約會資料的標準格式。它支援豐富的重複規則、例外與附件，非常適合企業排程需求。

### Why use Aspose.Email for Java?
Aspose.Email 提供純 Java API，讓您在不依賴 Outlook 的情況下建立、修改與儲存 MAPI 物件。這意味著您可以在伺服器端建置排程功能、產生 PST 檔，並以程式方式處理複雜的重複情境。

## Prerequisites

在開始之前，請確保已完成以下設定：
- **Aspose.Email Library**：版本 25.4（或更新）– 可透過 Maven 或直接下載取得。  
- **Java Development Kit (JDK)**：JDK 16 或更新版本。  
- **IDE**：IntelliJ IDEA、Eclipse、NetBeans，或任何支援 Java 的編輯器。

### Required Libraries and Dependencies

若使用 Maven 將 Aspose.Email 整合至專案，請在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

使用 Aspose.Email 前需取得授權：
- **Free Trial** – 免費試用全部功能。  
- **Temporary License** – 申請延長評估期。  
- **Full License** – 正式購買以供生產環境使用。

## Setting Up Aspose.Email for Java

首先，設定開發環境：

1. 確認已安裝 JDK 16，且 `JAVA_HOME` 已正確設定。  
2. 將 Maven 相依性（或下載 JAR）加入專案。  

以下是一段簡短程式碼，示範如何載入授權檔案：

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

## Implementation Guide

### Creating MAPI Calendar with Daily Recurrence and Exceptions

#### Overview
此功能可自動化重複約會，同時允許跳過或修改特定例項。

#### Step‑by‑Step Implementation

**1. Set Up Event Start Date**  
決定系列的開始日期：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Create the MAPI Calendar Object**  
設定地點、主旨與說明：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Define a Daily Recurrence Pattern**  
將事件設為每日重複：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Add an Exception to the Recurrence**  
指定需排除（或變更）的日期：

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

### Attaching Files to Calendar Exceptions

#### Overview
您可以為任何例外實例附加支援文件（例如議程）。

**1. Create and Attach a File**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Saving MAPI Calendar in PST Files

#### Overview
將行事曆持久化至 PST 檔，讓 Outlook 或其他客戶端可讀取。

**1. Create and Save Calendar to PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Practical Applications
- **Corporate Scheduling** – 自動化會議系列，並自動跳過假日。  
- **Project Management** – 追蹤具偶爾日期變動的重複里程碑。  
- **Event Planning** – 管理多日會議，處理部分議程取消或重新排程。

### Integration Possibilities
將 Aspose.Email 與 CRM 平台、任務管理 API 或自訂工作流程引擎結合，實現端對端自動化。

## Performance Considerations
- **Dispose Resources** – 使用完 `PersonalStorage` 後務必呼叫 `dispose()` 釋放檔案句柄。  
- **Stream Usage** – 建議使用 `ByteArrayOutputStream` 或檔案串流，避免一次載入整個 PST 至記憶體。  
- **Async Operations** – 若大量產生行事曆，請將建立邏輯放在背景執行緒，以保持 UI 響應。

## Conclusion
透過本指南，您已學會如何 **create mapi calendar java** 物件，設定每日重複、加入例外、附加檔案，並將所有內容儲存至 PST 檔。這些功能讓您能在不接觸 Outlook 的前提下，打造穩健的排程系統。

### Next Steps
- 嘗試每週或每月的重複模式。  
- 探索更多 MAPI 屬性，如參與者、提醒與類別。  
- 查閱 Aspose.Email 完整 API 文件，了解更進階的使用情境。

## Frequently Asked Questions

**Q: Does the library support time‑zone aware appointments?**  
A: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.

**Q: Can I programmatically delete a single occurrence from a recurring series?**  
A: Use the `DeletedInstanceDates` collection on the recurrence pattern to mark specific dates as removed.

**Q: Are there limits on the size of a PST file created with Aspose.Email?**  
A: PST files follow the Unicode format limits (up to 2 GB by default), but you can configure larger sizes via `PersonalStorage` settings.

**Q: How do I add attendees to a meeting request?**  
A: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`, and add them to the `Recipients` collection of the `MapiMessage`.

**Q: Is there support for recurring tasks (not just appointments)?**  
A: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.

## Resources
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
