---
date: '2026-01-01'
description: 學習如何使用 Aspose.Email for Java 建立 MAPI 行事曆並將行事曆儲存至 PST。逐步指南，包含程式碼、重複設定與收件者。
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: 如何使用 Aspose.Email 在 Java 中建立 MAPI 行事曆 – 將行事曆儲存至 PST
url: /zh-hant/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何建立 MAPI calendar java 與 Aspose.Email – 將行事曆儲存至 PST

## 介紹

您是否想在 Java 應用程式中簡化行事曆自動化？使用 **Aspose.Email for Java**，您只需幾行程式碼即可 **建立 MAPI calendar java** 項目、定義重複模式、加入與會者，並 **將行事曆儲存至 PST** 檔案。本教學將帶您完成整個流程——從設定函式庫到產生可供分發的完整行事曆項目。

### 您將學會
- 使用 Aspose.Email **建立 MAPI calendar java** 事件。  
- 設定每日、每週或自訂的重複模式。  
- 為行事曆邀請加入收件者（組織者、與會者）。  
- 透過 **將行事曆儲存至 PST** 以符合 Outlook 相容性。

讓我們一起開始，並將開發環境準備好。

## 快速答覆
- **使用哪個函式庫？** Aspose.Email for Java  
- **主要目標？** 建立 MAPI calendar java 並 **將行事曆儲存至 PST**  
- **前置條件？** Java 8+、Maven、Aspose.Email 授權  
- **一般實作時間？** 基本事件約 10‑15 分鐘  
- **可以加入重複嗎？** 可以 – 每日、每週、每月等皆支援  

## 什麼是 Java 中的 MAPI Calendar？
MAPI（Messaging Application Programming Interface）行事曆物件代表一個與 Outlook 相容的會議或約會。使用 Aspose.Email，您可以以程式方式建構這些物件，實現與 Exchange、Outlook 或任何支援 PST 檔案的客戶端的無縫整合。

## 為什麼選擇 Aspose.Email 進行行事曆自動化？
- **完整 Outlook 相容性** – 產生的項目可在 Outlook、OWA 以及行動客戶端使用。  
- **豐富的重複支援** – 內建每日、每週、每月及自訂模式。  
- **無外部相依** – 純 Java 函式庫，無需 COM 互操作。  
- **高效能** – 能有效處理大型 PST 檔案與批次操作。

## 前置條件

在開始之前，請確保您已具備：

### 必要函式庫
- **Aspose.Email for Java**：版本 25.4 或更新。

### 環境設定需求
- IntelliJ IDEA 或 Eclipse 等 Java IDE。  
- 已安裝 Maven 以管理相依性。

### 知識前提
- 基本的 Java 程式設計能力。  
- 熟悉物件導向概念。

## 設定 Aspose.Email for Java

將 Aspose.Email 的 Maven 相依性加入 `pom.xml`：

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

- **免費試用**：30 天內無功能限制。  
- **臨時授權**：如需延長，可透過 [Aspose 官方網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買授權**：前往 [購買頁面](https://purchase.aspose.com/buy) 取得永久授權。

### 基本初始化

加入相依性後，使用授權檔案初始化函式庫：

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 實作指南

現在環境已就緒，讓我們 **建立 MAPI calendar java** 並 **將行事曆儲存至 PST**。

### 建立具備重複的 MAPI Calendar

#### 概觀

我們將建立行事曆事件、套用每日重複、加入與會者，最後將其存入 PST 檔案。

#### 步驟說明

1. **初始化日期與重複模式**  

   首先定義開始時間，並設定每日重複：

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *說明*：`MapiCalendarEventRecurrence` 保存重複細節；我們透過 `MapiCalendarDailyRecurrencePattern` 設定每日模式。

2. **設定收件者**  

   加入應收到會議邀請的對象：

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *說明*：`MapiRecipientCollection` 儲存每位與會者；`MAPI_TO` 表示主要收件者。

3. **建立 MAPI Calendar 項目**  

   使用所有必要資訊建構行事曆物件：

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

   *說明*：建構子需要組織者、主旨、地點、開始/結束時間、說明、收件者清單與重複設定。

4. **儲存至 PST 檔案**  

   最後透過 **將行事曆儲存至 PST** 完成持久化：

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *說明*：`PersonalStorage.create` 產生新 PST 檔案，`addMapiMessageItem` 將行事曆項目加入「Calendar」資料夾。

### 疑難排解小技巧
- 確認授權檔路徑；授權無效會限制功能。  
- 確保收件者的電子郵件地址格式正確，以免邀請失敗。  
- 操作完畢後記得關閉 PST (`pst.dispose()`) 以釋放檔案句柄。

## 實務應用

以下情境特別適合 **建立 MAPI calendar java** 並 **將行事曆儲存至 PST**：

1. **自動化會議排程** – 為專案團隊產生週期性會議邀請，免除手動操作。  
2. **活動管理平台** – 將會議議程匯出為 Outlook 相容的行事曆項目。  
3. **CRM 整合** – 直接將客戶預約從 CRM 系統同步至 Outlook（透過 PST）。

## 效能考量

- **資源管理**：使用完 `PersonalStorage` 後務必釋放，以避免檔案鎖定。  
- **批次處理**：大量項目時，建議以非同步或分批方式處理，以降低記憶體使用。

## 結論

您已學會如何使用 Aspose.Email **建立 MAPI calendar java** 物件、設定重複、加入與會者，並 **將行事曆儲存至 PST**。此方法讓您的 Java 應用程式能自動化複雜的排程工作，同時保持 Outlook 相容性。

欲深入了解，請參考官方 [文件](https://reference.aspose.com/email/java/)。

## 常見問答

### Q: 可以建立每週的重複模式嗎？
- **A**：可以！使用 `MapiCalendarWeeklyRecurrencePattern` 定義每週重複。

### Q: 如何處理事件重複中的例外日期？
- **A**：在重複物件上呼叫 `setExceptions()`，指定偏離原模式的日期。

### Q: 能否更新已存在的行事曆項目？
- **A**：當然可以。從 PST 讀取項目、修改屬性後再儲存回去。

### Q: 可以為 PST 檔案加密嗎？
- **A**：可以，建立 PST 時可於 `PersonalStorage` 設定密碼。

### Q: 若要在行事曆事件中加入附件，該怎麼做？
- **A**：在儲存前呼叫 `calendar.getAttachments().addFileAttachment("path/to/file")`。

## 資源

- [Aspose.Email 文件](https://reference.aspose.com/email/java/)  
- [下載 Aspose.Email for Java](https://releases.aspose.com/email/java/)  
- [購買授權](https://purchase.aspose.com/buy)  
- [免費試用版](https://releases.aspose.com/email/java/)  
- [申請臨時授權](https://purchase.aspose.com/temporary-license/)  
- [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-01-01  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
