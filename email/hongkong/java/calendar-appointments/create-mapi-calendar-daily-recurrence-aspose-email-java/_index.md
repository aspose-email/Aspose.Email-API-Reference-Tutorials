---
date: '2026-09-17'
description: 了解如何使用 Java 建立 Outlook 行事曆（每日重複與例外），並使用 Aspose.Email for Java 將行事曆儲存為
  PST。
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: 使用 Aspose.Email 於 Java 建立 Outlook 行事曆。了解每日重複、例外處理以及一步一步的 PST 儲存教學。
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: 使用 Java 建立 Outlook 行事曆（每日重複與例外）
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
title: 使用 Java 建立 Outlook 行事曆（每日重複與例外）
url: /zh-hant/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 outlook calendar java（每日重複與例外）

有效管理重複事件可能具有挑戰性，特別是當您需要支援每日重複模式與偶爾例外的 **outlook calendar java** 時。在本教學中，您將學習如何建立 Outlook calendar Java 物件、設定每日重複、加入例外實例，最後使用 Aspose.Email for Java **save calendar to PST**。完成後，您將擁有可重複使用的程式碼片段，能直接嵌入任何基於 Java 的排程服務。

## 快速解答
- **使用哪個函式庫？** Aspose.Email for Java  
- **主要任務？** 建立 Outlook calendar Java，具備每日重複與例外  
- **前置條件 JDK？** Java 16 或更新版本  
- **我可以將檔案附加到例外嗎？** 可以，使用 `MapiCalendarExceptionInfo`  
- **行事曆儲存於何處？** 透過 `PersonalStorage` 儲存於 PST 檔案  

## 什麼是 Outlook calendar java？
Outlook calendar Java 物件是 Outlook 約會的程式化表示，基於 MAPI（訊息應用程式介面）規範構建，包含主旨、地點、開始/結束時間、重複規則、參與者與附件等屬性。此物件可被操作、序列化，並儲存於 PST 檔案中，無需 Outlook。

## 為何使用 Aspose.Email for Java？
Aspose.Email for Java 讓您在未安裝 Outlook 的情況下操作 MAPI 物件。此函式庫支援 **50+ MAPI 屬性**，能在 **2 秒** 內產生最高 **2 GB** 的 Unicode PST 檔案（針對一般約會資料），且可在任何支援 Java 16+ 的平台上執行。這種純 Java 的方式可實現伺服器端行事曆建立、自動化會議系列，以及對重複邏輯的完整控制。

## 前置條件

在開始之前，請確保您已完成以下設定：
- **Aspose.Email Library**：版本 25.4（或更新）– 可透過 Maven 或直接下載取得。  
- **Java Development Kit (JDK)**：JDK 16 或更新版本。  
- **IDE**：IntelliJ IDEA、Eclipse、NetBeans，或任何相容 Java 的編輯器。

### 必要的函式庫與相依性

要使用 Maven 將 Aspose.Email 整合至專案，請在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權

使用 Aspose.Email 前，您需要取得授權：
- **免費試用** – 無償探索所有功能。  
- **臨時授權** – 申請延長評估。  
- **正式授權** – 購買後用於正式環境。

## 設定 Aspose.Email for Java

首先，設定您的環境：

1. 確認已安裝 JDK 16 且已設定 `JAVA_HOME`。  
2. 將 Maven 相依性（或下載 JAR）加入您的專案。  

以下是一段簡短程式碼範例，示範如何載入授權檔案：

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

### 建立 outlook calendar java（每日重複與例外）

#### 概觀
此功能讓您自動化重複約會，同時仍能跳過或修改特定實例。

#### 步驟實作

**1. 設定事件開始日期**  
確定系列應何時開始：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. 建立 MAPI 行事曆物件**  
`MapiCalendar` 類別是記憶體中代表單一行事曆項目的最高層物件。提供地點、主旨與描述：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 定義每日重複模式**  
`MapiCalendarRecurrencePattern` 類別儲存每日重複約會的規則。將事件設定為每日重複：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 為重複加入例外**  
`MapiCalendarExceptionInfo` 描述一個偏離規則的單一發生——可以是排除或變更。指定應排除（或變更）的日期：

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
您可以將支援文件（例如議程）附加至任何例外實例。

**1. 建立並附加檔案**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## 將 outlook calendar java 儲存至 PST（save calendar to pst）

#### 概觀
將行事曆持久化至 PST 檔案，以便 Outlook 或其他客戶端讀取。

**1. 建立並儲存行事曆至 PST**  
`PersonalStorage` 類別提供建立新 PST 檔案並將 MAPI 項目加入其中的方法。

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
- **企業排程** – 自動化會議系列，並自動跳過假日。  
- **專案管理** – 追蹤具有偶爾日期變動的重複里程碑。  
- **活動規劃** – 管理多天會議，處理取消或重新排程的場次。

### 整合可能性
將 Aspose.Email 與 CRM 平台、任務管理 API 或自訂工作流程引擎結合，以驅動端對端自動化。

## 效能考量
- **釋放資源** – 必須在 `PersonalStorage` 上呼叫 `dispose()` 以釋放檔案句柄。  
- **串流使用** – 建議使用 `ByteArrayOutputStream` 或檔案串流，以避免將整個 PST 載入記憶體。  
- **非同步操作** – 若大量產生行事曆，請將建立邏輯放在背景執行緒，以保持 UI 響應。

## 結論
依照本指南，您現在已了解如何 **create outlook calendar java** 物件，設定每日重複、加入例外、附加檔案，並 **save calendar to PST**。這些功能讓您能在不直接操作 Outlook 的情況下，建構穩健的排程功能。

### 後續步驟
- 嘗試每週或每月的重複模式。  
- 探索其他 MAPI 屬性，如參與者、提醒與類別。  
- 檢視 Aspose.Email 完整的 API 文件，以了解更進階的情境。

## 常見問題

**Q: 此函式庫是否支援時區感知的約會？**  
A: 是的，您可以在 `MapiCalendar` 上設定 `StartTimeZone` 與 `EndTimeZone` 屬性。

**Q: 我能以程式方式刪除重複系列中的單一發生嗎？**  
A: 使用重複模式的 `DeletedInstanceDates` 集合，將特定日期標記為已移除。

**Q: 使用 Aspose.Email 建立的 PST 檔案大小是否有限制？**  
A: PST 檔案遵循 Unicode 格式限制（預設最高 2 GB），但可透過 `PersonalStorage` 設定調整為更大尺寸。

**Q: 如何將參與者加入會議請求？**  
A: 建立 `MapiRecipient` 物件，將其 `RecipientType` 設為 `MapiRecipientType.MAPI_TO`，再加入 `MapiMessage` 的 `Recipients` 集合。

**Q: 是否支援重複的工作項目（不僅限於約會）？**  
A: 是的，Aspose.Email 亦提供具相似重複功能的 `MapiTask`。

**Q: 我可以將此指南作為 Aspose.Email Java 教學系列的一部分嗎？**  
A: 當然可以——此處示範的步驟是任何涉及行事曆建立的 Aspose.Email Java 教學的核心部分。

## 資源
- [Aspose.Email for Java 文件說明](https://reference.aspose.com/email/java/)
- [下載 Aspose.Email](https://releases.aspose.com/email/java/)
- [購買授權](https://purchase.aspose.com/buy)
- [免費試用版](https://releases.aspose.com/email/java/)
- [申請臨時授權](https://purchase.aspose.com/temporary-license/)
- [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-09-17  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Email 匯出 Outlook 行事曆 PST – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [如何使用 Aspose.Email 建立 Calendar Item Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [使用 Aspose.Email for Java 建立行事曆共享邀請](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}