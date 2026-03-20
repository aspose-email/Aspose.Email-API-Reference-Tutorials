---
date: '2026-03-20'
description: 學習如何使用 Aspose.Email for Java 建立具每日重複與例外的 Outlook 行事曆（Java），並將行事曆儲存為 PST
  檔案。
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 使用 Java 建立 Outlook 行事曆（每日重複與例外）
url: /zh-hant/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用每日重複與例外建立 Outlook 行事曆 Java

有效管理重複事件可能相當具挑戰性，尤其是當您需要支援每日重複模式與偶發例外的 **outlook calendar java** 時。本教學將教您如何建立 Outlook 行事曆 Java 物件、設定每日重複、加入例外實例，最後使用 Aspose.Email for Java **save calendar to PST**。完成後，您將擁有可重複使用的程式碼片段，能直接嵌入任何基於 Java 的排程服務。

## 快速解答
- **哪個函式庫？** Aspose.Email for Java  
- **主要任務？** Create an Outlook calendar Java with daily recurrence and exceptions  
- **前置條件 JDK？** Java 16 or higher  
- **我可以在例外上附加檔案嗎？** Yes, using `MapiCalendarExceptionInfo`  
- **行事曆儲存於何處？** In a PST file via `PersonalStorage`

## 什麼是 Outlook 行事曆 Java？

Outlook 行事曆 Java 物件（以 MAPI 行事曆實作）遵循與 Microsoft Outlook 約會相同的標準。它可儲存豐富的重複規則、例外處理、參與者與附件，十分適合企業級排程需求。

## 為何使用 Aspose.Email for Java？

Aspose.Email 提供純 Java API，讓您在未安裝 Outlook 的情況下操作 MAPI 物件。此 **aspose email tutorial java** 方法可在伺服器端產生 PST 檔案、自動化會議系列，並完整掌控重複邏輯。

## 前置條件

在開始之前，請確保已完成以下設定：

- **Aspose.Email 函式庫**：版本 25.4（或更新）— 可透過 Maven 或直接下載取得。  
- **Java Development Kit (JDK)**：JDK 16 或更新版本。  
- **IDE**：IntelliJ IDEA、Eclipse、NetBeans，或任何相容 Java 的編輯器。

### 必要的函式庫與相依性

若要使用 Maven 將 Aspose.Email 整合至專案，請在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權

使用 Aspose.Email 需要取得授權：

- **Free Trial** – 免費試用，探索全部功能。  
- **Temporary License** – 臨時授權，可申請延長評估期。  
- **Full License** – 正式授權，適用於生產環境部署。

## 設定 Aspose.Email for Java

首先，設定您的環境：

1. 確認已安裝 JDK 16 且已設定 `JAVA_HOME`。  
2. 將 Maven 相依性（或下載 JAR）加入專案。  

以下是一段小程式碼範例，示範如何載入授權檔案：

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

## 實作指南

### 建立具每日重複與例外的 Outlook 行事曆 Java

#### 概觀
此功能可自動化重複約會，同時允許跳過或修改特定實例。

#### 步驟說明

**1. 設定事件開始日期**  
決定系列的開始時間：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. 建立 MAPI 行事曆物件**  
提供地點、主旨與描述：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 定義每日重複模式**  
設定事件每日重複：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 為重複加入例外**  
指定要排除（或變更）的日期：

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

### 為行事曆例外附加檔案

#### 概觀
您可以為任何例外實例附加支援文件（例如議程）。

**1. 建立並附加檔案**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### 將 Outlook 行事曆 Java 儲存至 PST（save calendar to pst）

#### 概觀
將行事曆持久化至 PST 檔案，以便 Outlook 或其他客戶端讀取。

**1. 建立並儲存行事曆至 PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 實務應用
- **Corporate Scheduling** – 自動化會議系列，並自動跳過假日。  
- **Project Management** – 追蹤具有偶發日期變動的重複里程碑。  
- **Event Planning** – 管理多日會議，處理取消或重新安排的場次。

### 整合可能性
將 Aspose.Email 與 CRM 平台、任務管理 API 或自訂工作流程引擎結合，實現端對端自動化。

## 效能考量
- **Dispose Resources** – 必須在 `PersonalStorage` 上呼叫 `dispose()` 以釋放檔案句柄。  
- **Stream Usage** – 建議使用 `ByteArrayOutputStream` 或檔案串流，以避免將整個 PST 載入記憶體。  
- **Async Operations** – 若大量產生行事曆，請在背景執行緒上執行建立邏輯，以保持 UI 響應。

## 結論
依照本指南，您現在已掌握如何 **create outlook calendar java** 物件的每日重複、加入例外、附加檔案，並 **save calendar to PST**。這些功能讓您在不直接操作 Outlook 的情況下，構建強大的排程功能。

### 後續步驟
- 嘗試每週或每月的重複模式。  
- 探索其他 MAPI 屬性，如參與者、提醒與類別。  
- 檢視 Aspose.Email 完整的 API 文件，以了解更進階的情境。

## 常見問題

**Q: 此函式庫是否支援時區感知的約會？**  
A: 可以，您可以在 `MapiCalendar` 上設定 `StartTimeZone` 與 `EndTimeZone` 屬性。

**Q: 我能以程式方式刪除重複系列中的單一實例嗎？**  
A: 使用重複模式的 `DeletedInstanceDates` 集合，將特定日期標記為已移除。

**Q: 使用 Aspose.Email 建立的 PST 檔案大小是否有限制？**  
A: PST 檔案遵循 Unicode 格式的限制（預設最高 2 GB），但可透過 `PersonalStorage` 設定調整為更大容量。

**Q: 如何為會議請求加入參與者？**  
A: 建立 `MapiRecipient` 物件，將其 `RecipientType` 設為 `MapiRecipientType.MAPI_TO`，再加入 `MapiMessage` 的 `Recipients` 集合。

**Q: 是否支援重複的工作項目（非約會）？**  
A: 有，Aspose.Email 亦提供具相似重複功能的 `MapiTask`。

**Q: 我可以將本指南作為 aspose email tutorial java 系列的一部分嗎？**  
A: 當然可以——此處示範的步驟是任何涉及行事曆建立的 Aspose.Email Java 教學的核心內容。

## 資源
- [Aspose.Email for Java 文件](https://reference.aspose.com/email/java/)
- [下載 Aspose.Email](https://releases.aspose.com/email/java/)
- [購買授權](https://purchase.aspose.com/buy)
- [免費試用版](https://releases.aspose.com/email/java/)
- [申請臨時授權](https://purchase.aspose.com/temporary-license/)
- [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-03-20  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}