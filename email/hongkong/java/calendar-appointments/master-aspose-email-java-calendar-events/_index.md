---
date: '2025-12-24'
description: 了解如何使用 Aspose.Email for Java 將行事曆匯出為 PST，包含如何新增與會者、設定開始與結束日期，以及有效管理約會。
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: 使用 Aspose.Email for Java 匯出行事曆至 PST
url: /zh-hant/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 匯出日曆至 PST

在開發需要與 Outlook 或其他 Microsoft 產品共享排程資料的 Java 應用程式時，**匯出日曆至 PST** 是常見需求。本教學將示範如何建立約會、加入與會者、設定開始與結束日期，最後將所有內容儲存為 PST 檔案——全部使用 Aspose.Email for Java 完成。

## 快速回答
- **主要目標是什麼？** 將日曆事件匯出至 PST 檔案。  
- **需要哪個函式庫？** Aspose.Email for Java（v25.4 以上）。  
- **需要授權嗎？** 需要，合法的 Aspose.Email 授權可移除評估限制。  
- **可以加入與會者嗎？** 當然可以——使用 `MapiRecipientCollection`。  
- **支援哪個 Java 版本？** JDK 16 或更高。

## 什麼是 **export calendar to pst**？
將日曆匯出至 PST 意指將記憶體中的 `MapiCalendar` 物件轉換成 Microsoft Outlook 個人儲存檔（Personal Storage Table，PST）。此檔案可在 Outlook 中開啟、與同事共享，或匯入支援 PST 格式的其他系統。

## 為什麼使用 Aspose.Email for Java 來匯出日曆至 PST？
- **完整的 MAPI 支援** – 可在未安裝 Outlook 的環境下建立、修改並儲存約會。  
- **跨平台** – 支援 Windows、Linux 與 macOS。  
- **功能豐富的 API** – 管理與會者、重複規則、提醒等。  
- **效能最佳化** – 以低記憶體佔用處理大量事件。

## 前置條件
- **函式庫與相依性**：Aspose.Email for Java 版本 25.4 或更新。  
- **執行環境**：JDK 16 以上，使用 Maven 管理相依性。  
- **基礎知識**：基本的 Java 程式設計與 Maven 使用經驗。

## 如何設定 Aspose.Email for Java
將 Aspose.Email 相依性加入 `pom.xml`：

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
透過以下方式取得完整功能授權，解除評估限制：

1. **免費試用**：前往 [Aspose 下載頁面](https://releases.aspose.com/email/java/) 取得暫時授權。  
2. **臨時授權**：於 [購買頁面](https://purchase.aspose.com/temporary-license/) 申請。  
3. **正式授權**：考慮從 [Aspose 購買入口](https://purchase.aspose.com/buy) 購買長期授權。

取得授權後，於程式中初始化即可啟用全部功能。

## 如何 **create appointment**（建立日曆事件 Java）

### 步驟 1：定義開始與結束日期（java calendar start date / java calendar end date）
以下方法示範如何設定約會的開始與結束日期，並回傳 `MapiCalendar` 物件：

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

*說明*：此程式碼建立一個 `MapiCalendar`，設定特定地點、主旨、說明，以及您先前定義的 **java calendar start date** / **java calendar end date**。

## 如何 **add attendees**（加入與會者）

### 步驟 2：建立與會者清單
使用 `MapiRecipientCollection` 指定會議邀請的收件者：

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

*說明*：此程式碼建立會議、設定組織者，並附加 **how to add attendees** 清單，使每位與會者皆收到正確的邀請。

## 如何 **export calendar to pst**（建立含日曆事件的 PST）

### 步驟 3：建立 PST 檔案並加入事件
以下方法示範如何建立 Unicode PST 檔案，並儲存簡易約會與含與會者的會議：

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

*說明*：此程式碼 **exports calendar to PST**，透過建立 PST 容器、加入預設的「Calendar」資料夾，最後插入先前建立的 `MapiCalendar` 物件。

## 實務應用
1. **企業排程** – 自動化內部會議的建立與分發。  
2. **活動管理** – 追蹤會議、研討會與參與者名單。  
3. **CRM 整合** – 與客戶關係管理工具同步約會。  
4. **專案規劃** – 將專案里程碑存為日曆項目。  
5. **遠端團隊協作** – 產生 PST 檔案供離線共享。

## 效能考量
- **釋放不再使用的物件** 以減少記憶體佔用。  
- **選用高效集合** 處理大量與會者清單。  
- **快取常用事件**，若頻繁查詢 PST 可提升效能。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **未建立 PST 檔案** | 確認目標目錄具有寫入權限，且資料夾路徑已存在。 |
| **與會者未收到邀請** | 確認每個 `MapiRecipient` 使用 `MapiRecipientType.MAPI_TO`，且組織者的電子郵件有效。 |
| **日期不符** | 統一使用 `Calendar` 設定開始/結束日期，避免在未轉換的情況下混用 `java.util.Date` 與其他日期函式庫。 |

## 常見問答

**Q: 如何開始使用 Aspose.Email for Java？**  
A: 依照上方示範加入 Maven 相依性，取得授權，然後依本指南步驟建立並匯出日曆事件。

**Q: 可以自訂 PST 檔案名稱與儲存位置嗎？**  
A: 可以，將 `createPSTWithCalendarEvents()` 中的 `pstFilePath` 變數改為系統上任意有效路徑即可。

**Q: 能否為約會加入重複模式？**  
A: 當然可以 – `MapiCalendar` 提供 `RecurrencePattern` 等屬性，您可在儲存前自行設定。

**Q: Aspose.Email 是否支援除 PST 之外的其他日曆格式？**  
A: 支援，您可以使用相應的 API 方法匯出至 iCalendar（`.ics`）等格式。

**Q: PST 檔案的最大容量是多少？**  
A: 使用 Unicode 格式（`FileFormatVersion.Unicode`）時，PST 檔案可達 2 TB，僅受磁碟空間限制。

---

**最後更新：** 2025-12-24  
**測試環境：** Aspose.Email for Java 25.4（jdk16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}