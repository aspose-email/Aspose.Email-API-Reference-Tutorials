---
date: '2026-08-01'
description: 了解如何使用 Aspose.Email for Java 將行事曆匯出為 PST，包括如何新增與會者、設定開始與結束日期，以及有效管理約會。
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: 使用 Aspose.Email for Java 將行事曆匯出為 PST。一步一步學習如何建立約會、加入與會者，以及產生 Outlook
  PST 檔案。
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: 將行事曆匯出為 PST – Aspose.Email for Java 完整指南
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: 使用 Aspose.Email for Java 將行事曆匯出為 PST
url: /zh-hant/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 匯出行事曆至 PST

如果您正在開發需要與 Outlook 共享排程資料的 Java 應用程式，通常需要 **匯出行事曆至 PST**。在本教學中，我們將逐步說明所有必要步驟——從建立簡單的約會、加入參與者，到最終將事件寫入 PST 檔案，全部使用 Aspose.Email for Java。完成後，您將擁有可在 Windows、Linux 與 macOS 上執行的正式環境解決方案。

## 快速解答
- **主要目標是什麼？** 匯出行事曆事件至 PST 檔案。  
- **需要哪個函式庫？** Aspose.Email for Java (v25.4+)。  
- **需要授權嗎？** 需要，有效的 Aspose.Email 授權可移除評估限制。  
- **可以加入參與者嗎？** 當然可以——使用 `MapiRecipientCollection`。  
- **支援哪個 Java 版本？** JDK 16 或更高版本。

## 什麼是 **匯出行事曆至 PST**？
`MapiCalendar` 是 Aspose.Email 的類別，用於模擬 Outlook 行事曆項目，包含主旨、地點與時間細節。

將行事曆匯出至 PST 表示將記憶體中的 `MapiCalendar` 物件轉換為 Microsoft Outlook 個人儲存檔 (PST)。產生的 PST 檔案可直接在 Outlook 中開啟、與同事共享，或匯入任何支援 PST 格式的系統，並保留所有事件細節，如參與者、重複規則與提醒。

## 為何使用 Aspose.Email for Java 匯出行事曆至 PST？
您可以在未安裝 Outlook 的情況下產生完全相容的 PST 檔案。Aspose.Email 提供 **完整的 MAPI 支援**，可在 **所有主要作業系統** 上執行，且能在 Unicode PST 格式下處理 **高達 2 TB** 的資料——足以應付企業級的歸檔需求。此 API 亦允許您僅透過少量方法呼叫，即管理參與者、重複模式、提醒與自訂屬性，大幅降低開發工作量。

## 前置條件
- **函式庫與相依性**：Aspose.Email for Java 版本 25.4 或更新版本。  
- **環境**：JDK 16 或更高版本，使用 Maven 進行相依性管理。  
- **知識需求**：基本的 Java 程式設計與 Maven 使用經驗。

## 如何設定 Aspose.Email for Java
將 Aspose.Email 相依性加入 `pom.xml`，然後重新整理 Maven 專案。此一步即可在 classpath 中提供完整的 MAPI API。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
透過取得授權，即可解除 Aspose.Email 的評估限制，解鎖全部功能：

1. **免費試用**：前往 [Aspose 下載頁面](https://releases.aspose.com/email/java/) 取得臨時授權。  
2. **臨時授權**：透過 [購買頁面](https://purchase.aspose.com/temporary-license/) 申請。  
3. **購買授權**：可於 [Aspose 購買入口](https://purchase.aspose.com/buy) 購買永久授權以供長期使用。  

取得授權後，請在應用程式中初始化，以啟用所有功能。

## 如何 **建立約會**（Create Calendar Event Java）

載入 `MapiCalendar` 物件，設定其核心屬性，並回傳以供後續處理。此方法會建立包含主旨、地點、描述，以及您定義的 **java 行事曆開始日期** / **java 行事曆結束日期** 的行事曆項目。

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

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

*說明*：`MapiCalendar` 類別是 Aspose.Email 用於表示 Outlook 行事曆項目的類別。設定基本欄位後，您亦可在儲存前配置重複規則、提醒與類別。

## 如何 **加入參與者**（java add meeting attendees）

建立 `MapiRecipientCollection`，將每位參與者加入集合，並附加至會議。如此可確保在開啟 PST 時，每位參與者皆收到適當的邀請。

`MapiRecipientCollection` 為集合類別，用於保存代表會議參與者的 `MapiRecipient` 物件。`MapiRecipient` 代表單一參與者，具備電子郵件地址與收件者類型等屬性。

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

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

*說明*：`MapiRecipient` 定義單一會議參與者。將類型設為 `MAPI_TO` 表示主要參與者，`MAPI_CC` 或 `MAPI_BCC` 則可用於可選參與者。

## 如何 **匯出行事曆至 PST**（Create PST with calendar events）

建立 Unicode PST 檔案，新增「Calendar」資料夾，並插入先前建立的 `MapiCalendar` 物件。之後即可在 Outlook 中開啟或分發給最終使用者。

`PersonalStorage` 是 Aspose.Email 用於建立、開啟與操作 PST 檔案的類別。

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

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

*說明*：`PersonalStorage` 為 PST 操作的入口點。使用 Unicode 格式可避免舊版 PST 的 2 GB 限制，且在大型歸檔時可獲得更快的 I/O 效能。

## 實務應用
1. **企業排程** – 自動化內部會議的建立與分發。  
2. **活動管理** – 追蹤會議、工作坊與參與者名單。  
3. **CRM 整合** – 將約會與客戶關係管理工具同步。  
4. **專案規劃** – 將專案里程碑存為行事曆項目。  
5. **遠端團隊協作** – 產生 PST 檔案以供離線共享。

## 效能考量
- **釋放不再使用的物件**，以即時釋放記憶體。  
- **使用高效的集合**（例如 `ArrayList` 用於參與者清單），在處理數千名參與者時。  
- **快取常用事件**，若頻繁查詢 PST，可減少磁碟 I/O。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **未建立 PST 檔案** | 確認目標目錄的寫入權限，且確保資料夾路徑已存在。 |
| **參與者未收到邀請** | 確認每個 `MapiRecipient` 使用 `MapiRecipientType.MAPI_TO`，且會議組織者的電子郵件有效。 |
| **日期不匹配** | 對於開始/結束日期，請一致使用 `Calendar`；避免在未轉換的情況下混用 `java.util.Date` 與其他日期函式庫。 |

## 常見問答

**Q: 如何開始使用 Aspose.Email for Java？**  
A: 加入上述的 Maven 相依性，取得授權，並依照本指南的步驟建立與匯出行事曆事件。

**Q: 我可以自訂 PST 檔案的名稱與位置嗎？**  
A: 可以，請在 `createPSTWithCalendarEvents()` 中修改 `pstFilePath` 變數為系統上任何有效的路徑。

**Q: 能否為約會加入重複模式？**  
A: 當然可以——`MapiCalendar` 提供 `RecurrencePattern` 屬性，您可在儲存前進行設定。

**Q: Aspose.Email 是否支援除 PST 之外的其他行事曆格式？**  
A: 支援，您可使用相應的 API 方法匯出至 iCalendar（`.ics`）及其他格式。

**Q: 我能建立的 PST 檔案最大容量是多少？**  
A: 使用 Unicode 格式（`FileFormatVersion.Unicode`）時，PST 檔案可擴展至 2 TB，僅受可用磁碟空間限制。

---

**最後更新：** 2026-08-01  
**測試環境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [精通 Aspose.Email for Java：高效管理 Outlook PST 檔案](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [精通使用 Aspose.Email for Java 建立與儲存行事曆項目](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [如何使用 Aspose.Email for Java 從 ICS 檔案讀取多個行事曆事件](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}