---
date: '2025-12-19'
description: 學習如何使用 Aspose.Email for Java 在 Outlook 中設定跟進旗標，包括如何有效率地設定 Outlook 跟進旗標及移除
  Outlook 跟進旗標。
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: 如何使用 Aspose.Email for Java 在 Outlook 中設定跟進旗標
url: /zh-hant/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 在 Outlook 中設定跟進旗標

## 介紹
如果你曾經為了追蹤重要郵件而感到困擾，你就會知道 Outlook 的跟進旗標有多麼寶貴。在本指南中，我們將示範 **如何以程式方式設定跟進旗標**，同時說明如何 **為收件者設定 Outlook 跟進旗標**，以及在任務完成後 **如何移除 Outlook 跟進旗標**。完成閱讀後，你將能直接從 Java 程式碼自動化任務追蹤、提醒與稽核流程。

**你將學會**
- 在 Outlook 訊息上建立並套用跟進旗標。  
- 為特定收件者設定跟進旗標。  
- 將旗標標記為已完成，並在之後移除。  
- 讀取旗標選項以供報表或合規使用。  

在深入程式碼之前，先把開發環境準備好。

## 快速答覆
- **「如何設定跟進」是什麼意思？** 為 Outlook 項目新增包含開始、提醒與到期日期的旗標。  
- **需要哪個程式庫？** Aspose.Email for Java（v25.4 或更新版本）。  
- **需要授權嗎？** 需要，必須使用試用或正式授權才能取得完整功能。  
- **只能為收件者設定旗標嗎？** 當然可以 – 使用 `FollowUpManager.setFlagForRecipients`。  
- **之後可以移除旗標嗎？** 可以，呼叫 `FollowUpManager.clearFlag` 即可。

## 什麼是跟進旗標？
跟進旗標是 Outlook 的功能，可將電子郵件標記為任務，並可選擇性附加開始、提醒與到期日期。它能協助你與團隊掌握待處理的工作項目。

## 為什麼要使用 Aspose.Email for Java？
Aspose.Email 提供純 Java API，無需安裝 Outlook，即可操作 .msg 檔案、設定旗標與管理任務，適用於後端服務、自動化工作流程或與專案管理工具的整合。

## 前置條件
- **Aspose.Email for Java** 版本 25.4 以上。  
- 已安裝 **JDK 16+**。  
- 支援 Maven 的 IDE（IntelliJ IDEA、Eclipse 等）。  
- 具備基本的 Java 知識與郵件概念。

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

### 授權取得
Aspose.Email 於正式環境使用時需要授權：

- **免費試用** – 30 天評估。  
- **暫時授權** – 延長測試。  
- **正式授權** – 永續訂閱。

在執行任何郵件操作前先初始化授權：

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## 實作指南

### 如何設定跟進旗標（功能 1）
#### 概觀
本節說明如何建立 Outlook 訊息、定義開始/提醒/到期日期，並套用跟進旗標。

#### 步驟 1：建立並初始化訊息
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*我們先建立 `MailMessage`，設定寄件者與收件者，然後轉換為 `MapiMessage` 以便操作旗標。*

#### 步驟 2：定義跟進日期
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*此處使用 `Calendar` 類別設定開始、提醒與到期日期。*

#### 步驟 3：套用跟進選項
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 物件保存所有旗標細節，我們透過 `FollowUpManager.setOptions` 套用。*

#### 步驟 4：儲存訊息
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*訊息會以 `.msg` 檔案形式儲存，且已附加旗標。*

### 為收件者設定 Outlook 跟進旗標（功能 2）
#### 概觀
有時只需要為收件者設定旗標。此範例先將訊息標記為草稿，然後再加入旗標。

#### 步驟 1：標記為草稿
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*將訊息標記為未發送，可確保 Outlook 將其視為草稿。*

#### 步驟 2：設定收件者旗標
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*此時旗標僅會在收件者端顯示。*

### 將 Outlook 跟進旗標標記為已完成（功能 3）
#### 概觀
任務完成後，可程式化地將旗標標記為已完成。

#### 步驟 1：載入訊息
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### 步驟 2：標記為完成並儲存
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*旗標狀態會變為「Completed」，並將更新後的檔案儲存。*

### 移除 Outlook 跟進旗標（功能 4）
#### 概觀
若旗標不再需要，可將其完全清除。

#### 步驟 1：載入並清除旗標
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*訊息將在未帶任何跟進旗標的情況下儲存。*

### 讀取跟進旗標選項（功能 5）
#### 概觀
為了稽核或報表，可能需要讀取現有的旗標設定。

#### 步驟 1：取得選項
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 物件現在包含開始、到期與提醒日期，以及旗標主旨。*

## 實務應用
- **任務管理整合**：將已標記的郵件同步至 Jira、Trello 或 Azure Boards。  
- **自動提醒**：產生每日提醒郵件，提醒未完成的跟進項目。  
- **合規稽核**：匯出旗標資料以符合監管報告需求。

## 效能考量
- **日期計算**：批次處理時一次計算日期，避免在迴圈內重複計算。  
- **資源管理**：儲存訊息後務必關閉任何串流或檔案句柄。  
- **記憶體使用**：將大型信箱分批處理，以免造成記憶體壓力。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 旗標未在 Outlook 中顯示 | 訊息儲存時未正確設定 `MessageFlags` | 在套用收件者旗標前，確保 `setMessageFlags` 設為 `MSGFLAG_UNSENT`。 |
| 儲存時拋出 `AccessDeniedException` | 檔案路徑錯誤或缺少寫入權限 | 確認輸出目錄存在且應用程式具備寫入權限。 |
| 日期相差一天 | 時區不一致 | 使用 `TimeZone.getTimeZone("GMT")` 或統一使用本地時區。 |

## 常見問答
**Q: 什麼是 Aspose.Email for Java？**  
A: 它是一套純 Java API，讓你在不安裝 Outlook 的情況下建立、讀取與操作郵件檔案（MSG、EML 等）。

**Q: 如何取得免費試用授權？**  
A: 前往 [Aspose 官方網站](https://releases.aspose.com/email/java/) 下載 30 天試用版。

**Q: 可以在同一封訊息上設定多個跟進旗標嗎？**  
A: Outlook 每封訊息僅支援一個旗標，但你可以將額外的任務資料存於自訂 MAPI 屬性中。

**Q: 設定旗標後訊息未儲存，該檢查什麼？**  
A: 確認 `outputDir` 路徑正確，且應用程式有寫入該目錄的權限。

**Q: 如何一次移除多封訊息的旗標？**  
A: 迭代訊息集合，對每個 `MapiMessage` 呼叫 `FollowUpManager.clearFlag`。

## 相關資源
- [文件說明](https://reference.aspose.com/email/java/)
- [下載 Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email 免費試用](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**最後更新：** 2025-12-19  
**測試環境：** Aspose.Email for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}