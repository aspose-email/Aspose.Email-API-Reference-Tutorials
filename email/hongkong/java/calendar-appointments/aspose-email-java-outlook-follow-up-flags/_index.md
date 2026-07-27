---
date: '2026-07-27'
description: 了解如何使用 Aspose.Email for Java 設定 Outlook 旗標（Java），涵蓋旗標建立、收件者旗標、完成、移除以及讀取選項。
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: 使用 Aspose.Email for Java 設定 Outlook 旗標（Java）。本指南示範如何有效地建立、讀取、完成及移除
  Outlook 待辦旗標。
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: 設定 Outlook 旗標（Java） – 完整 Aspose.Email 程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: 設定 Outlook 旗標（Java） – 完整 Aspose.Email 程式設計指南
url: /zh-hant/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 設定 Outlook 旗標 (Java)

## 介紹
如果您需要以程式方式 **設定 Outlook 旗標 Java**，您來對地方了。Outlook 的跟進旗標會將普通電子郵件轉換為可追蹤的工作項目，而 Aspose.Email for Java 讓您在未安裝 Outlook 的情況下管理這些旗標。在本教學中，我們將示範如何建立、讀取、完成，最後移除旗標，以及如何為特定收件者套用旗標。完成後，您將擁有可在後端服務直接自動化工作追蹤的 Java 程式碼片段。

## 快速答覆
- **「設定 outlook flag java」是什麼意思？** 透過 Java 程式碼為 Outlook 項目加入開始、提醒與到期日期的旗標。  
- **需要哪個函式庫？** Aspose.Email for Java (v25.4 或更新版本)。  
- **需要授權嗎？** 需要 – 試用版可供評估，但正式環境必須購買授權。  
- **可以只為收件者設定旗標嗎？** 當然可以 – 使用 `FollowUpManager.setFlagForRecipients`。  
- **之後可以移除旗標嗎？** 可以 – 呼叫 `FollowUpManager.clearFlag`。

## 什麼是 Outlook 跟進旗標？
Outlook 跟進旗標是一種內建的工作標記，可為任何郵件項目附加開始日期、提醒與到期日期。它會將電子郵件轉變為可追蹤的行動項目，協助您與團隊掌握待處理工作。

## 為什麼使用 Aspose.Email for Java？
Aspose.Email for Java 支援 **70+ 電子郵件格式**（包括 MSG、EML、MHTML、TNEF），且在一般 8 核心伺服器上每分鐘可處理 **超過 100,000 封訊息**，完全不需要在主機上安裝 Outlook。這使它非常適合後端自動化、合規報告以及與專案管理工具的整合。

## 前置條件
- **Aspose.Email for Java** 版本 25.4 或更新。  
- 已安裝 **JDK 16+**。  
- 支援 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知識與電子郵件概念。

## 設定 Aspose.Email for Java
### Maven 設定
在 `pom.xml` 中加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
Aspose.Email 需要授權才能於正式環境使用：

- **免費試用** – 30 天評估。  
- **臨時授權** – 延長測試。  
- **完整授權** – 永久訂閱。

在執行任何郵件操作前先初始化授權：

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## 設定 Outlook 旗標 Java（功能 1）
### 直接答案
載入 `MailMessage`，將其轉換為 `MapiMessage`，設定 `FollowUpOptions`，然後呼叫 `FollowUpManager.setOptions`。只需幾行 Java 程式碼，即可建立完整的旗標 Outlook 項目。

### 步驟 1：建立並初始化訊息
`MailMessage` 是 Aspose.Email 的高階類別，代表一封電子郵件。建立訊息後，將其轉換為 `MapiMessage` 以便操作旗標。

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我們先建立 `MailMessage`，設定寄件者/收件者，然後轉換為 `MapiMessage` 以進行旗標操作。*

### 步驟 2：定義跟進日期（Outlook 旗標提醒）
`FollowUpOptions` 包含開始、提醒與到期日期。使用 Java 的 `Calendar` 設定精確的時間戳記。

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*此處使用 `Calendar` 類別設定開始、提醒（即 **Outlook 旗標提醒**）與到期日期。*

### 步驟 3：套用跟進選項
`FollowUpManager.setOptions` 方法會將旗標附加至 `MapiMessage`。

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 物件包含所有旗標細節，我們透過 `FollowUpManager.setOptions` 套用它。*

### 步驟 4：儲存訊息
將已加旗標的訊息儲存為 `.msg` 檔，讓 Outlook 能顯示旗標。

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*訊息以 `.msg` 檔案形式儲存，旗標已隨檔案一起保存。*

## 如何為收件者設定旗標（功能 2）？
在將訊息標記為草稿後，使用 `FollowUpManager.setFlagForRecipients`。此方法僅在收件者的副本上加入跟進旗標，寄件者的檢視不受影響。需要先設定 `MessageFlags.MSGFLAG_UNSENT`，然後再套用旗標。您亦可在呼叫方法前，使用 `FollowUpOptions` 物件自訂開始、提醒與到期日期。

### 直接答案
先以 `MessageFlags.MSGFLAG_UNSENT` 將訊息標記為草稿，然後呼叫 `FollowUpManager.setFlagForRecipients`。Outlook 只會在收件者端顯示旗標，寄件者端不會看到。

### 概觀
有時您只想讓旗標 **僅對收件者** 可見。此範例先將訊息標記為草稿，然後加入旗標。

#### 步驟 1：標記為草稿
`MessageFlags` 為 MAPI 列舉，用於控制訊息狀態。設定 `MSGFLAG_UNSENT` 會告訴 Outlook 該項目為草稿。

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*將訊息標記為未傳送，可確保 Outlook 將其視為草稿。*

#### 步驟 2：設定收件者旗標
`FollowUpManager.setFlagForRecipients` 會將旗標僅附加於收件者的副本。

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*旗標現在只會在收件者端可見 – 典型的 **收件者旗標** 情境。*

## 如何將 Outlook 跟進旗標標記為已完成（功能 3）？
將 `.msg` 檔載入 `MapiMessage`，然後呼叫 `FollowUpManager.completeFlag`。此操作會將旗標狀態更新為 Completed，並在 Outlook 中顯示勾選標記。完成後儲存訊息以保留變更。如需審計，可調整 `FlagCompleteTime` 屬性設定完成時間。

### 直接答案
載入現有的 `.msg` 檔至 `MapiMessage`，呼叫 `FollowUpManager.completeFlag`，再儲存檔案。旗標狀態會變為「已完成」，在 Outlook 中顯示勾選。

### 步驟 1：載入訊息
`MapiMessage` 能讀取已儲存的 `.msg` 檔，讓您完整存取其 MAPI 屬性。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 步驟 2：標記為完成並儲存
`FollowUpManager.completeFlag` 會更新旗標狀態，之後將變更寫回檔案。

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*旗標狀態變為「已完成」，更新後的檔案已儲存。*

## 如何移除 Outlook 跟進旗標（功能 4）？
以 `MapiMessage` 開啟 `.msg` 檔，呼叫 `FollowUpManager.clearFlag`，然後儲存訊息。此操作會移除所有與旗標相關的 MAPI 屬性，Outlook 不再顯示任何跟進指示。當任務被取消或不再相關時使用此方法。亦請同時清除任何自訂的提醒屬性，以免留下殘餘通知。

### 直接答案
以 `MapiMessage` 開啟 `.msg` 檔，呼叫 `FollowUpManager.clearFlag`，再儲存檔案。訊息將不再顯示任何跟進指示。

### 步驟 1：載入並清除旗標
`FollowUpManager.clearFlag` 會移除訊息中所有與旗標相關的屬性。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*訊息已儲存，且不含任何跟進旗標。*

## 如何讀取旗標選項（功能 5）？
對已載入的 `MapiMessage` 呼叫 `FollowUpManager.getOptions`，即可取得 `FollowUpOptions` 物件。此物件提供開始、到期、提醒日期以及旗標主旨，方便您顯示或記錄旗標細節。對於報表與合規稽核相當有用。

### 直接答案
在已載入的 `MapiMessage` 上使用 `FollowUpManager.getOptions`，取得包含開始、到期、提醒日期與旗標主旨的 `FollowUpOptions` 物件。此資訊可用於報表或合規稽核。

### 步驟 1：取得選項
回傳的 `options` 物件讓您完整掌握旗標的設定。

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 物件現在包含開始、到期與提醒日期，以及旗標主旨 – 在需要 **讀取旗標選項** 以進行報表時非常實用。*

## 實務應用
- **工作管理整合：** 將已加旗標的郵件同步至 Jira、Trello 或 Azure Boards。  
- **自動提醒：** 為待處理的跟進項目產生每日提醒郵件。  
- **合規稽核：** 匯出旗標資料以符合監管報告需求，利用程式讀取旗標選項。

## 效能考量
- **日期計算：** 批次處理時僅計算一次日期，避免在迴圈內重複。  
- **資源管理：** 儲存訊息後務必關閉所有串流或檔案句柄。  
- **記憶體使用：** 將大型郵箱分塊處理，以免產生過大堆疊；Aspose.Email 能在不將整個檔案載入記憶體的情況下處理數百頁的郵箱。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 旗標未在 Outlook 中顯示 | 訊息儲存時未設定正確的 `MessageFlags` | 確認在套用收件者旗標前已將 `MessageFlags` 設為 `MSGFLAG_UNSENT`。 |
| 儲存時拋出 `AccessDeniedException` | 檔案路徑錯誤或缺乏寫入權限 | 檢查輸出目錄是否存在，且應用程式具有寫入權限。 |
| 日期錯差一天 | 時區不一致 | 使用 `TimeZone.getTimeZone("GMT")` 或統一使用本地時區。 |

## 常見問答
**Q: 什麼是 Aspose.Email for Java？**  
A: 它是一套純 Java API，讓您在不安裝 Outlook 的情況下建立、讀取與操作電子郵件檔案（MSG、EML 等）。

**Q: 如何取得免費試用授權？**  
A: 前往 [Aspose 網站](https://releases.aspose.com/email/java/) 下載 30 天試用版。

**Q: 我可以在同一封訊息上設定多個跟進旗標嗎？**  
A: Outlook 每封訊息僅支援一個旗標，但您可以將額外的工作資料存放於自訂 MAPI 屬性中。

**Q: 設定旗標後訊息未儲存，我該檢查什麼？**  
A: 確認 `outputDir` 路徑正確且程式具有寫入該位置的權限。

**Q: 如何一次移除多封訊息的旗標？**  
A: 迭代您的訊息集合，對每個 `MapiMessage` 呼叫 `FollowUpManager.clearFlag`。

## 資源
- [文件說明](https://reference.aspose.com/email/java/)  
- [下載 Aspose.Email for Java](https://releases.aspose.com/email/java/)  
- [Aspose.Email 免費試用](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**最後更新：** 2026-07-27  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Email for Java 管理 Outlook 類別 – 完整指南](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [使用 Aspose.Email 建立 Outlook 註解 Java – 完整指南](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [使用 Aspose.Email for Java 在 Microsoft Exchange 建立任務 – 完整指南](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}