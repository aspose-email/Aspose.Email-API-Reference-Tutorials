---
date: '2026-03-20'
description: 學習如何使用 Aspose.Email for Java 匯出 Outlook 行事曆 PST —— 建立 MAPI 行事曆項目、設定重複規則、加入與會者，並儲存至
  PST。
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: 使用 Aspose.Email – Java 匯出 Outlook 行事曆 PST
url: /zh-hant/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email – Java 匯出 Outlook 行事曆 PST

## 簡介

您是否希望在 Java 應用程式中簡化行事曆自動化，並需要 **匯出 Outlook 行事曆 PST** 檔案？使用 **Aspose.Email for Java**，您可以 **建立 MAPI 行事曆 Java** 項目、定義重複模式、加入與會者，並僅用幾行程式碼 **將行事曆儲存至 PST**。本教學將帶您完成整個流程——從設定函式庫到產生可直接分發的完整行事曆項目。

### 您將學到的內容
- 如何使用 Aspose.Email **建立 MAPI 行事曆 Java** 事件。  
- 設定每日、每週或自訂的重複模式。  
- 將收件者（組織者、與會者）加入行事曆邀請。  
- 透過 **將行事曆儲存至 PST** 以保留行事曆項目，確保 Outlook 相容性。  
- 如何使用可重用程式碼 **自動化會議排程**。

## 快速答覆
- **使用的函式庫？** Aspose.Email for Java  
- **主要目標？** 匯出 Outlook 行事曆 PST 並 **將行事曆儲存至 PST**  
- **前置條件？** Java 8 以上、Maven、Aspose.Email 授權  
- **一般實作時間？** 基本事件約 10‑15 分鐘  
- **可以加入重複嗎？** 可以——每日、每週、每月等。

## 匯出 Outlook 行事曆 PST

本節將說明完整流程，讓您 **匯出 Outlook 行事曆 PST** 檔案。建立 MAPI 行事曆物件後，最後一步是將其儲存至 Outlook 可直接讀取的 PST 檔案中。

## 為何使用 Aspose.Email 進行行事曆自動化？

- **完整的 Outlook 相容性**——產生的項目可在 Outlook、OWA 及行動裝置客戶端使用。  
- **豐富的重複支援**——內建每日、每週、每月及自訂模式。  
- **無外部相依性**——純 Java 函式庫，無需 COM 互操作。  
- **高效能**——有效處理大型 PST 檔案與批次操作。  
- **自動化會議排程**——將此邏輯嵌入批次工作或 Web 服務，可自動建立數百個邀請。

## 前置條件

在開始之前，請確保您已具備以下條件：

### 必要函式庫
- **Aspose.Email for Java**：版本 25.4 或更新。

### 環境設定需求
- Java IDE，例如 IntelliJ IDEA 或 Eclipse。  
- 已安裝 Maven 以管理相依性。

### 知識前置條件
- 基本的 Java 程式設計技能。  
- 熟悉物件導向概念。

## 設定 Aspose.Email for Java

將 Aspose.Email Maven 相依性加入您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權

Aspose.Email 提供免費試用版，但授權可解鎖全部功能：

- **免費試用**：30 天無限制測試。  
- **臨時授權**：如需延長時間，請透過 [Aspose 官方網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買**：在 [購買頁面](https://purchase.aspose.com/buy) 購買永久授權。

### 基本初始化

加入相依性後，使用授權檔案初始化函式庫：

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 實作指南

現在環境已就緒，讓我們 **建立 MAPI 行事曆 Java** 並 **將行事曆儲存至 PST**。

### 建立具重複功能的 MAPI 行事曆

#### 概觀

我們將建立行事曆事件、套用每日重複、加入與會者，最後將其儲存至 PST 檔案。

#### 步驟實作

1. **初始化日期與重複模式**  

   首先，定義開始時間並設定每日重複：

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *說明*：`MapiCalendarEventRecurrence` 保存重複細節；我們透過 `MapiCalendarDailyRecurrencePattern` 選擇每日模式。

2. **設定收件者**  

   新增應收到會議邀請的人員：

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *說明*：`MapiRecipientCollection` 儲存每位與會者；`MAPI_TO` 標記為主要收件者。

3. **建立 MAPI 行事曆項目**  

   使用所有必要資訊建立行事曆物件：

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

   *說明*：建構子需要組織者、主旨、地點、開始/結束時間、描述、收件者清單與重複設定。

4. **儲存至 PST 檔案**  

   最後，透過 **將行事曆儲存至 PST** 來永久保存行事曆：

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *說明*：`PersonalStorage.create` 產生新 PST 檔案，`addMapiMessageItem` 將行事曆項目插入「Calendar」資料夾。

### 故障排除提示
- 確認授權檔案路徑；無效的授權會限制功能。  
- 確保收件者的電子郵件地址格式正確，以免邀請失敗。  
- 操作完成後關閉 PST（`pst.dispose()`），釋放檔案句柄。

## 實務應用

以下是 **建立 MAPI 行事曆 Java** 並 **將行事曆儲存至 PST** 的常見應用情境：

1. **自動化會議排程**——為專案團隊產生重複會議邀請，免除人工操作。  
2. **活動管理平台**——將會議議程匯出為 Outlook 相容的行事曆項目。  
3. **CRM 整合**——直接將 CRM 系統的客戶預約同步至 Outlook，透過 PST 檔案。

## 效能考量

- **資源管理**：使用完畢後釋放 `PersonalStorage` 物件，以防止檔案鎖定。  
- **批次處理**：大量資料時，將行事曆項目非同步或分批處理，以降低記憶體使用。

## 結論

您現在已學會如何透過建立 MAPI 行事曆 Java 物件、設定重複、加入與會者，並使用 Aspose.Email **匯出 Outlook 行事曆 PST** 以及 **將行事曆儲存至 PST**。此方法讓您的 Java 應用程式能自動化複雜的排程工作流程，並具備 Outlook 相容性。

欲深入了解，請參閱官方 [文件](https://reference.aspose.com/email/java/)。

## 常見問答

### Q: 我可以建立每週重複模式嗎？
- **A**：可以！使用 `MapiCalendarWeeklyRecurrencePattern` 定義每週重複。

### Q: 如何處理事件重複中的例外情況？
- **A**：在重複物件上呼叫 `setExceptions()`，指定偏離模式的日期。

### Q: 是否可以更新現有的行事曆項目？
- **A**：當然可以。從 PST 載入項目，修改其屬性，然後重新儲存。

### Q: 我可以加密 PST 檔案嗎？
- **A**：可以，Aspose.Email 允許在建立 PST 時於 `PersonalStorage` 設定密碼。

### Q: 如果需要在行事曆事件中加入附件該怎麼辦？
- **A**：在儲存前使用 `calendar.getAttachments().addFileAttachment("path/to/file")` 加入檔案附件。

## 資源

- [Aspose.Email 文件說明](https://reference.aspose.com/email/java/)
- [下載 Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [購買授權](https://purchase.aspose.com/buy)
- [免費試用版](https://releases.aspose.com/email/java/)
- [申請臨時授權](https://purchase.aspose.com/temporary-license/)
- [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-03-20  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}