---
date: '2026-03-20'
description: 了解如何使用 Aspose.Email for Java 建立日曆共享邀請、設定日曆權限以及設定委派存取權。
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: 使用 Aspose.Email for Java 創建日曆共享邀請
url: /zh-hant/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 管理行事曆共享：Aspose.Email for Java 指南

## 管理行事曆共享的簡介
管理行事曆共享邀請可能是一項複雜的工作，尤其是在不同平台上處理多位使用者時。本教學將示範如何使用 Aspose.Email for Java **建立行事曆共享邀請**，涵蓋從建立委派存取權到發送行事曆共享電郵的全部步驟。完成後，您將能設定委派權限、**配置行事曆權限**，並在組織內簡化協作。

**您將學習的內容**
- 如何使用 Aspose.Email for Java 初始化 EWS 客戶端  
- 建立委派使用者並 **設定委派權限**  
- **建立委派存取權** 並配置行事曆權限  
- 以程式方式發送 **行事曆共享電郵**（邀請）  
- 這些功能在實務情境中的價值

在深入之前，讓我們確保您已具備所有必要條件。

## 快速解答
- **此指南的主要目的為何？** 示範如何使用 Aspose.Email for Java **建立行事曆共享邀請**。  
- **需要哪個版本的函式庫？** Aspose.Email for Java 25.4（JDK 16 classifier）。  
- **是否需要授權？** 是 – 生產環境必須使用試用或正式授權。  
- **需要什麼環境？** JDK 16 以上、Maven，以及 Exchange Online 帳戶。  
- **能否在其他 Exchange 伺服器上使用？** 可以，但可能需要調整服務 URL 與權限等級。

## 什麼是行事曆共享邀請？
行事曆共享邀請是一封電郵，允許其他使用者在不取得完整信箱權限的情況下，檢視（或編輯）您的行事曆。此功能常用於團隊協調、專案規劃與活動管理。

## 為何要配置行事曆權限？
配置行事曆權限可讓您精確控制委派者的操作範圍——無論是僅能閱讀事件、提出新事件，或是編輯現有項目。適當的權限設定能保護敏感資訊，同時促進有效協作。

## 先決條件
- **Java Development Kit (JDK)：** 版本 16 或更新。  
- **Maven：** 用於相依性管理與專案建置。  
- **Aspose.Email for Java 函式庫：** 版本 25.4，支援 JDK 16。

### 環境設定需求
1. 若尚未安裝 JDK，請先安裝。您可從 [Oracle 官方網站](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
2. 確認已在機器上安裝並設定 Maven。  
3. 選擇如 IntelliJ IDEA 或 Eclipse 等 IDE，以便更輕鬆開發。

### 知識先備條件
- 基本的 Java 程式設計能力  
- 熟悉 Maven 相依性  
- 可選：具備 Exchange Web Services (EWS) 經驗

## 設定 Aspose.Email for Java
### Maven 設定
將以下相依性加入您的 `pom.xml` 檔案：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
Aspose.Email for Java 需要授權才能完整使用功能。您可以：
- **免費試用：** 從 [Aspose 釋出頁面](https://releases.aspose.com/email/java/) 下載。  
- **臨時授權：** 在 Aspose 官網申請臨時金鑰。  
- **購買授權：** 取得永久授權以供正式環境使用。

### 基本初始化與設定
當 Maven 解析完相依性後，初始化 EWS 客戶端：

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## 如何建立行事曆共享邀請
以下說明兩個核心功能：建立並發送行事曆共享邀請，以及 **設定委派權限** 以存取行事曆。

### 功能 1：建立並發送行事曆共享邀請
#### 概觀
此功能將指導您完成初始化客戶端、**建立委派存取權**，以及發送邀請電郵的步驟。

#### 逐步實作
##### 1️⃣ 初始化 EWS 客戶端
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
此程式碼將您的 Java 應用程式連接至 Exchange Online。

##### 2️⃣ 建立委派使用者
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
此處我們 **建立委派存取權**，並指派 `Reviewer` 等級，讓委派者能檢視行事曆項目。

##### 3️⃣ 發送行事曆共享邀請
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
此程式碼建立 **行事曆共享電郵**（邀請），並透過 EWS 客戶端發送。

### 功能 2：委派行事曆存取權限
#### 概觀
本節說明如何 **配置行事曆權限**，並確保委派者擁有正確的權限。

#### 實作步驟
##### 1️⃣ 初始化 EWS 客戶端（重複使用）
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ 建立並設定委派權限
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
此程式碼片段 **設定委派權限**，讓使用者在不取得完整信箱存取權的情況下檢視行事曆項目。

## 如何為委派者配置行事曆權限
當您需要委派者執行除檢視事件之外的操作（如編輯或刪除）時，可變更 `ExchangeDelegateFolderPermissionLevel`：

- `Reviewer` – 只讀存取。  
- `Editor` – 讀寫存取。  
- `Author` – 可建立與閱讀，但無法刪除。  
- `Owner` – 完全控制，包括變更權限。

**小技巧：** 請使用符合業務需求的最低權限等級，以確保行事曆資料的安全。

## 實務應用
以下為 **管理行事曆共享** 的實務情境：
1. **公司會議** – 讓團隊成員檢視會議排程，卻不授予完整信箱權限。  
2. **專案管理** – 專案負責人可監控時間表，而開發人員仍保有自己的行事曆控制權。  
3. **活動規劃** – 供應商會收到 **行事曆共享電郵**，以協調物流，同時不洩漏內部細節。

## 效能考量
- **記憶體管理：** 在高流量應用程式中及時釋放大型 `MailMessage` 物件。  
- **例外處理：** 使用 try‑catch 包裹網路呼叫，以優雅地處理連線問題。  
- **函式庫更新：** 保持 Aspose.Email 為最新版本，以獲得效能提升與錯誤修正。

## 常見問題與解決方案
| 問題 | 可能原因 | 解決方案 |
|-------|--------------|----------|
| 未收到邀請 | 垃圾郵件過濾或電郵地址錯誤 | 確認收件者地址，並將發件域名加入安全寄件者清單 |
| 權限未套用 | 使用錯誤的 `ExchangeDelegateFolderPermissionLevel` | 再次確認權限等級符合所需存取 |
| `createCalendarSharingInvitationMessage` 執行時例外 | 缺少授權或函式庫過舊 | 確保已載入有效授權，且使用最新的 Aspose.Email 版本 |

## 常見問答
**Q: Aspose.Email for Java 有什麼用途？**  
A: 它是一套完整的函式庫，用於在 Java 應用程式中處理電郵、行事曆與聯絡人，支援 Outlook、Exchange 及其他通訊協定。

**Q: 如何設定使用 Aspose.Email 的環境？**  
A: 安裝 JDK 16 以上、Maven，將 Aspose.Email 相依性加入 `pom.xml`，並取得授權（試用或正式）。

**Q: 此程式碼能否在其他版本的 Exchange Online 上使用？**  
A: 可以，但請確認服務 URL 與權限等級符合您伺服器的設定。

**Q: 若行事曆共享邀請發送失敗該怎麼辦？**  
A: 檢查網路連線、認證資訊，以及委派使用者是否具備有效權限。查看例外細節以獲取線索。

**Q: 是否可以加入額外的權限，例如編輯或完整存取？**  
A: 當然可以 – 依需求將 `ExchangeDelegateFolderPermissionLevel.Reviewer` 替換為 `Editor`、`Author` 或 `Owner`。

## 結論
您現在已擁有使用 Aspose.Email for Java **建立行事曆共享邀請** 的完整端對端解決方案。透過初始化 EWS 客戶端、**建立委派存取權**、**設定委派權限**，以及發送 **行事曆共享電郵**，即可自動化組織內的協作。

**後續步驟**
- 嘗試其他權限等級（Editor、Owner）。  
- 將此邏輯整合至現有的排程或人力資源系統。  
- 探索 Aspose.Email 的其他功能，如週期性事件或會議請求。

---

**最後更新：** 2026-03-20  
**測試環境：** Aspose.Email for Java 25.4（JDK 16 classifier）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}