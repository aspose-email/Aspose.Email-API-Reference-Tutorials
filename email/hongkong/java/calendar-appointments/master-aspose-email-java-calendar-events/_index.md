---
date: '2026-02-24'
description: 了解如何使用 Aspose.Email for Java 將行事曆匯出為 PST，包括如何新增與會者、設定開始與結束日期，以及有效管理約會。
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: 使用 Aspose.Email for Java 將行事曆匯出為 PST
url: /zh-hant/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 匯出行事曆至 PST

如果您正在開發需要與 Outlook 共享排程資料的 Java 應用程式，通常需要 **匯出行事曆至 PST**。在本教學中，我們將逐步說明所有必要步驟——從建立簡單的約會、加入與會者，最後將事件寫入 PST 檔案，全部使用 Aspose.Email for Java。

## 快速解答
- **主要目標是什麼？** 匯出行事曆事件至 PST 檔案。  
- **需要哪個函式庫？** Aspose.Email for Java (v25.4+)。  
- **需要授權嗎？** 需要，有效的 Aspose.Email 授權會移除評估限制。  
- **可以加入與會者嗎？** 當然可以——使用 `MapiRecipientCollection`。  
- **支援哪個 Java 版本？** JDK 16 或更高。

## 什麼是 **匯出行事曆至 PST**？
將行事曆匯出至 PST 意味著將記憶體中的 `MapiCalendar` 物件轉換為 Microsoft Outlook 個人儲存檔 (PST)。產生的檔案可直接在 Outlook 中開啟、與同事共享，或匯入任何能辨識 PST 格式的系統。

## 為何使用 Aspose.Email for Java 匯出行事曆至 PST？
- **完整的 MAPI 支援** – 無需安裝 Outlook，即可建立、修改與儲存約會。  
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。  
- **豐富的 API** – 管理與會者、週期性、提醒等功能。  
- **效能最佳化** – 以低記憶體佔用處理大量事件。

## 前置條件
- **函式庫與相依性**：Aspose.Email for Java 版本 25.4 或更新。  
- **環境**：JDK 16 或更高，使用 Maven 管理相依性。  
- **知識需求**：基本的 Java 程式設計與 Maven 使用經驗。

## 如何設定 Aspose.Email for Java
在 `pom.xml` 中加入 Aspose.Email 相依性：

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
取得授權即可解除 Aspose.Email 的評估限制，解鎖完整功能：

1. **免費試用**：前往 [Aspose 下載頁面](https://releases.aspose.com/email/java/) 取得臨時授權。  
2. **臨時授權**：透過 [購買頁面](https://purchase.aspose.com/temporary-license/) 申請。  
3. **購買授權**：可於 [Aspose 購買入口](https://purchase.aspose.com/buy) 購買長期授權。

取得授權後，於應用程式中初始化，即可啟用全部功能。

## 如何 **建立約會**（Create Calendar Event Java）

### 步驟 1：定義開始與結束日期（java calendar start date / java calendar end date）
以下方法示範如何為約會設定開始與結束日期，並回傳 `MapiCalendar` 物件：

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

*說明*：此程式碼片段會建立一個具備特定地點、主旨、描述，以及您先前定義的 **java calendar start date** / **java calendar end date** 的 `MapiCalendar`。

## 如何 **加入與會者**（java add meeting attendees）

### 步驟 2：建立與會者清單
使用 `MapiRecipientCollection` 指定誰應收到會議邀請：

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

*說明*：此程式碼建立會議、設定組織者，並附加 **java add meeting attendees** 清單，使所有人皆收到正確的邀請。

## 如何 **匯出行事曆至 PST**（Create PST with calendar events）

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

*說明*：此程式碼透過建立 PST 容器、加入預先定義的「Calendar」資料夾，並插入先前建立的 `MapiCalendar` 物件，**匯出行事曆至 PST**。

## 實務應用
1. **企業排程** – 自動化內部會議的建立與分發。  
2. **活動管理** – 追蹤會議、工作坊及參與者名單。  
3. **CRM 整合** – 將約會與客戶關係管理工具同步。  
4. **專案規劃** – 將專案里程碑儲存為行事曆項目。  
5. **遠端團隊協作** – 產生 PST 檔案以供離線共享。

## 效能考量
- **釋放不再使用的物件** 以釋放記憶體。  
- **選擇高效能的集合** 以處理大量與會者清單。  
- **快取常用事件**，若頻繁查詢 PST。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **未建立 PST 檔案** | 確認目標目錄的寫入權限，且資料夾路徑已存在。 |
| **與會者未收到邀請** | 確認每個 `MapiRecipient` 使用 `MapiRecipientType.MAPI_TO`，且組織者的電子郵件有效。 |
| **日期不匹配** | 對開始/結束日期一致使用 `Calendar`，避免在未轉換的情況下混用 `java.util.Date` 與其他日期函式庫。 |

## 常見問與答

**Q: 如何開始使用 Aspose.Email for Java？**  
A: 加入上述的 Maven 相依性，取得授權，並依照本指南的步驟建立與匯出行事曆事件。

**Q: 我可以自訂 PST 檔案的名稱與位置嗎？**  
A: 可以，修改 `createPSTWithCalendarEvents()` 中的 `pstFilePath` 變數為系統上任何有效的路徑。

**Q: 能否為約會加入週期模式？**  
A: 當然可以——`MapiCalendar` 提供如 `RecurrencePattern` 等週期屬性，您可在儲存前進行設定。

**Q: Aspose.Email 是否支援除 PST 之外的其他行事曆格式？**  
A: 支援，您可以使用相應的 API 方法匯出至 iCalendar（`.ics`）等其他格式。

**Q: 我能建立的 PST 檔案最大容量是多少？**  
A: 使用 Unicode 格式（`FileFormatVersion.Unicode`）時，PST 檔案可擴展至 2 TB，僅受可用磁碟空間限制。

---

**最後更新：** 2026-02-24  
**測試環境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}