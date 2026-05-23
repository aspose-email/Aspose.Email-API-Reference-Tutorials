---
date: '2026-02-22'
description: 學習如何在 Outlook 中使用 Aspose.Email for Java 設定 Outlook 跟進旗標，包括為收件人設定、讀取及移除旗標。
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: 如何使用 Aspose.Email for Java 設定 Outlook 跟進旗標
url: /zh-hant/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

 not code blocks but placeholders. They should stay as is.

Also need to keep the shortcodes at top and bottom.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 設定 Outlook 待辦旗標

## 介紹
如果你曾經為了追蹤重要郵件而感到困擾，你一定知道 Outlook 的 **outlook follow up flag** 有多麼好用。本指南將示範如何使用 Aspose.Email for Java 以程式方式 **設定 outlook follow up flag**，同時說明 **為收件者設定 outlook follow up flag** 以及 **在任務完成後移除 outlook follow up flag**。完成後，你就能直接在 Java 程式碼中自動化任務追蹤、提醒與稽核流程。

**你將學會**
- 在 Outlook 訊息上建立並套用待辦旗標。  
- 為特定收件者設定待辦旗標。  
- 將旗標標記為已完成，並在之後移除。  
- 讀取旗標選項以供報表或合規使用。  

在進入程式碼前，先把開發環境準備好。

## 快速答覆
- **「how to set follow‑up」是什麼意思？** 為 Outlook 項目加入開始日期、提醒與截止日期的旗標。  
- **需要哪個函式庫？** Aspose.Email for Java（v25.4 或更新版本）。  
- **需要授權嗎？** 需要，完整功能必須使用試用或正式授權。  
- **可以只為收件者設定旗標嗎？** 當然可以 – 使用 `FollowUpManager.setFlagForRecipients`。  
- **之後可以移除旗標嗎？** 可以，呼叫 `FollowUpManager.clearFlag` 即可。

## 什麼是 Outlook 待辦旗標？
Outlook 待辦旗標是一種內建的任務標記，能為任何郵件項目附加開始日期、提醒與截止日期。它會把普通郵件轉變為可追蹤的工作項目，協助你和團隊掌握未完成的工作。

## 為什麼使用 Aspose.Email for Java？
Aspose.Email 提供純 Java API，無需安裝 Outlook，即可操作 .msg 檔案、設定旗標與管理任務，適合 **automate outlook tasks**、後端服務或與專案管理工具的整合。

## 前置條件
- **Aspose.Email for Java** 版本 25.4 以上（亦稱 **aspose email java**）。  
- 已安裝 **JDK 16+**。  
- 支援 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知識與郵件概念。

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
Aspose.Email 於正式環境必須使用授權：

- **免費試用** – 30 天評估。  
- **臨時授權** – 延長測試。  
- **正式授權** – 永久訂閱。

在執行任何郵件操作前先初始化授權：

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## 設定 Outlook 待辦旗標（功能 1）
### 步驟 1：建立並初始化訊息
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我們先建立 `MailMessage`，設定寄件者/收件者，然後轉換為 `MapiMessage` 以便操作旗標。*

### 步驟 2：定義待辦日期（Outlook 旗標提醒）
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*此處使用 `Calendar` 類別設定開始、提醒（**outlook flag reminder**）與截止日期。*

### 步驟 3：套用待辦選項
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 物件保存所有旗標細節，我們透過 `FollowUpManager.setOptions` 套用。*

### 步驟 4：儲存訊息
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*訊息以 `.msg` 檔案形式儲存，旗標已附加在內。*

## 為收件者設定旗標（功能 2）
### 概觀
有時需要旗標只在 **收件者** 那邊顯示。此範例先將訊息標記為草稿，然後再加入旗標。

#### 步驟 1：標記為草稿
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*將訊息標記為未發送，可讓 Outlook 視為草稿。*

#### 步驟 2：設定收件者旗標
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*旗標現在僅對收件者可見 – 典型的 **flag for recipients** 情境。*

## 將 Outlook 待辦旗標標記為已完成（功能 3）
### 步驟 1：載入訊息
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 步驟 2：標記為已完成並儲存
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*旗標狀態變更為「Completed」，並將更新後的檔案儲存。*

## 移除 Outlook 待辦旗標（功能 4）
### 步驟 1：載入並清除旗標
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*訊息已儲存，且不再帶有任何待辦旗標。*

## 讀取旗標選項（功能 5）
### 步驟 1：取得選項
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 物件現在包含開始、截止與提醒日期，以及旗標主旨 – 於報表或合規時 **read flag options** 非常有用。*

## 實務應用
- **任務管理整合：** 將已標記的郵件同步至 Jira、Trello 或 Azure Boards。  
- **自動提醒：** 為待處理的待辦產生每日提醒郵件。  
- **合規稽核：** 匯出旗標資料以符合監管報告需求。

## 效能考量
- **日期計算：** 批次處理時一次計算日期，避免在迴圈內重複計算。  
- **資源管理：** 儲存訊息後關閉所有串流或檔案句柄。  
- **記憶體使用：** 大型信箱分批處理，以免造成記憶體壓力。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 旗標在 Outlook 中未顯示 | 訊息儲存時缺少正確的 `MessageFlags` | 在套用收件者旗標前，確保 `setMessageFlags` 設為 `MSGFLAG_UNSENT`。 |
| 儲存時拋出 `AccessDeniedException` | 檔案路徑錯誤或缺少寫入權限 | 確認輸出目錄存在且應用程式具備寫入權限。 |
| 日期相差一天 | 時區不一致 | 使用 `TimeZone.getTimeZone("GMT")` 或統一使用本地時區。 |

## 常見問答
**Q: Aspose.Email for Java 是什麼？**  
A: 它是一套純 Java API，讓你在不安裝 Outlook 的情況下建立、讀取與操作郵件檔案（MSG、EML 等）。

**Q: 如何取得免費試用授權？**  
A: 前往 [Aspose 官方網站](https://releases.aspose.com/email/java/) 下載 30 天試用版。

**Q: 可以在同一封訊息上設定多個待辦旗標嗎？**  
A: Outlook 每封訊息僅支援一個旗標，但可將額外任務資料存於自訂 MAPI 屬性中。

**Q: 設定旗標後訊息未儲存，該檢查什麼？**  
A: 確認 `outputDir` 路徑正確且程式有寫入該目錄的權限。

**Q: 如何一次移除多封訊息的旗標？**  
A: 迭代訊息集合，對每個 `MapiMessage` 呼叫 `FollowUpManager.clearFlag`。

## 參考資源
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**最後更新：** 2026-02-22  
**測試環境：** Aspose.Email for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}