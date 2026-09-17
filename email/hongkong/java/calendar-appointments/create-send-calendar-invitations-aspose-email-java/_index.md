---
date: '2026-09-17'
description: 使用 Aspose.Email for Java 建立行事曆邀請可讓您以程式方式分享行事曆、設定委派權限，並傳送分享電子郵件。
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: 使用 Aspose.Email for Java 建立行事曆邀請可讓您以程式方式透過 Exchange Web Services 分享行事曆、設定委派權限，並傳送分享電子郵件，提升團隊協作。
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: 如何使用 Aspose.Email for Java 建立行事曆邀請
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: 如何使用 Aspose.Email for Java 建立行事曆邀請
url: /zh-hant/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 管理行事曆共享：Aspose.Email for Java 指南

## 管理行事曆共享的簡介
管理行事曆共享邀請可能是一項複雜的工作，特別是當需要在不同平台上處理多位使用者時。在本教學中，您將使用 Aspose.Email for Java **建立行事曆共享邀請**，涵蓋從建立委派存取權到發送行事曆共享電郵的全部內容。完成後，您將能設定委派權限、**配置行事曆權限**，並在組織內簡化協作。

**您將學習**
- 如何使用 Aspose.Email for Java 初始化 EWS 客戶端  
- 建立委派使用者並 **設定委派權限**  
- **建立委派存取** 並配置行事曆權限  
- 以程式方式發送 **行事曆共享電郵**（邀請）  
- 這些功能在實務情境中帶來的價值  

在深入之前，讓我們確保您已具備所有必要的條件。

## 快速答覆
- **本指南的主要目的為何？** 示範如何使用 Aspose.Email for Java **建立行事曆共享邀請**。  
- **需要哪個版本的函式庫？** Aspose.Email for Java 25.4（JDK 16 classifier）。  
- **是否需要授權？** 是 – 生產環境需使用試用版或正式授權。  
- **需要什麼環境？** JDK 16+、Maven 以及 Exchange Online 帳戶。  
- **可以在其他 Exchange 伺服器上使用嗎？** 可以，但可能需要調整服務 URL 與權限等級。

## 什麼是行事曆共享邀請？
行事曆共享邀請是一封電郵，允許其他使用者在不取得完整信箱權限的情況下檢視（或編輯）您的行事曆。它讓團隊成員能查看您的行程、提議會議或管理活動，同時保持信箱的安全。

## 為何要配置行事曆權限？
配置行事曆權限可讓您精確控制委派者的操作範圍——他們是只能閱讀事件、提議新會議，或是編輯現有項目。適當的權限設定可保護敏感資訊，同時促進有效協作。例如，授予唯讀存取可防止意外變更，而編輯權限則允許委派者代您排程或修改會議。

## 前置條件
- **Java Development Kit (JDK)：** 版本 16 或以上。  
- **Maven：** 用於相依性管理與專案建置。  
- **Aspose.Email for Java 函式庫：** 版本 25.4，支援 JDK 16。  

### 環境設定需求
1. 若尚未安裝 JDK，請安裝。您可從 [Oracle 官方網站](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
2. 確保您的機器已安裝並設定 Maven。  
3. 選擇如 IntelliJ IDEA 或 Eclipse 等 IDE，以便更輕鬆開發。

### 知識前置條件
- 基本的 Java 程式設計技能  
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
- **臨時授權：** 在 Aspose 網站上申請臨時金鑰。  
- **購買：** 取得永久授權以供正式部署使用。

### 基本初始化與設定
Maven 解析相依性後，初始化 EWS 客戶端：

`ExchangeService` 是用於與 Exchange Web Services 通訊的主要類別。  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## 如何建立行事曆共享邀請
要建立行事曆共享邀請，您首先使用 `ExchangeService` 客戶端連線至 Exchange，接著定義具有所需權限等級的委派，最後組合包含共享請求的 `MailMessage`。以下步驟示範此工作流程於 Java 中。

以下說明兩個核心功能：建立並發送行事曆共享邀請，以及 **設定委派權限** 以存取行事曆。

### 功能 1：建立並發送行事曆共享邀請
#### 概述
此功能將指引您完成初始化客戶端、**建立委派存取**，以及發送邀請電郵的步驟。

#### 步驟實作
##### 1️⃣ 初始化 EWS 客戶端
`ExchangeService` 代表與 Exchange 伺服器的連線，用於傳送與接收訊息。  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
此程式碼將您的 Java 應用程式連接至 Exchange Online。

##### 2️⃣ 建立委派使用者
`DelegateUser` 定義委派的電子郵件地址與授予的權限等級。  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
此處我們 **建立委派存取** 並指派 `Reviewer` 等級，讓委派者能檢視行事曆項目。

##### 3️⃣ 發送行事曆共享邀請
`MailMessage` 用於構建攜帶行事曆共享邀請的電郵。  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
此程式碼建立 **行事曆共享電郵**（邀請），並透過 EWS 客戶端發送。

### 功能 2：委派行事曆存取權限
#### 概述
本節說明如何 **配置行事曆權限**，並確保委派者擁有正確的權限。

#### 實作步驟
##### 1️⃣ 初始化 EWS 客戶端（重複使用）
`ExchangeService` 在初始設定後可重複用於多項操作。  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ 建立並設定委派權限
`ExchangeDelegateFolderPermissionLevel` 列舉委派對行事曆資料夾可擁有的存取等級。  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
此程式碼片段 **設定委派權限**，讓使用者在不取得完整信箱存取權的情況下檢視行事曆項目。

## 如何為委派者配置行事曆權限
當委派者需要超過唯讀的存取權時，您可以調整 `ExchangeDelegateFolderPermissionLevel` 以授予編輯、作者或擁有者權限。請選擇符合業務需求且最小化的等級，以維持安全同時提供必要功能。例如，指派 Editor 等級允許委派者建立、修改與刪除事件，而 Reviewer 等級僅允許檢視。

- `Reviewer` – 唯讀存取。  
- `Editor` – 讀寫存取。  
- `Author` – 可建立與讀取，但無法刪除。  
- `Owner` – 完全控制，包括變更權限。  

**小技巧：** 使用符合業務需求的最小權限等級，以確保行事曆資料的安全。

## 實務應用
行事曆共享管理在實務情境中的應用：

1. **企業會議** – 讓團隊成員檢視會議排程，卻不授予完整信箱權限。  
2. **專案管理** – 專案負責人可監控時間表，開發者則保留自行管理行事曆的權限。  
3. **活動策劃** – 供應商會收到 **行事曆共享電郵**，協調物流而不暴露內部細節。

## 效能考量
- **記憶體管理：** 在高流量應用程式中及時釋放大型 `MailMessage` 物件。  
- **例外處理：** 使用 try‑catch 包裹網路呼叫，以優雅處理連線問題。  
- **函式庫更新：** Aspose.Email for Java 支援超過 50 種協議，且可在不將整個檔案載入記憶體的情況下處理多達 10,000 筆行事曆項目，請保持函式庫為最新以獲得效能提升與錯誤修正。

## 常見問題與解決方案
| 問題 | 可能原因 | 解決方案 |
|------|----------|----------|
| 未收到邀請 | 垃圾郵件過濾或電子郵件地址錯誤 | 確認收件者地址，並將發件域名加入安全寄件者清單 |
| 權限未套用 | 使用了錯誤的 `ExchangeDelegateFolderPermissionLevel` | 再次確認權限等級符合所需存取 |
| `createCalendarSharingInvitationMessage` 執行時例外 | 缺少授權或函式庫過舊 | 確保已載入有效授權，且使用最新的 Aspose.Email 版本 |

## 常見問答
**Q: Aspose.Email for Java 的用途是什麼？**  
A: 它是一套完整的函式庫，用於在 Java 應用程式中處理電子郵件、行事曆與聯絡人，支援 Outlook、Exchange 及其他協議。

**Q: 如何設定使用 Aspose.Email 的環境？**  
A: 安裝 JDK 16+、Maven，將 Aspose.Email 相依性加入 `pom.xml`，並取得授權（試用或正式）。

**Q: 此程式碼能否用於其他版本的 Exchange Online？**  
A: 可以，但請確認服務 URL 與權限等級符合您伺服器的設定。

**Q: 若行事曆共享邀請發送失敗，該怎麼辦？**  
A: 檢查網路連線、認證資訊，以及委派使用者是否具備有效權限。查看例外細節以獲取線索。

**Q: 是否可以加入額外的權限，例如編輯或完整存取？**  
A: 當然可以 – 依需求將 `ExchangeDelegateFolderPermissionLevel.Reviewer` 替換為 `Editor`、`Author` 或 `Owner`。

## 結論
您現在擁有使用 Aspose.Email for Java **建立行事曆共享邀請** 的完整端對端解決方案。透過初始化 EWS 客戶端、**建立委派存取**、**設定委派權限**，以及發送 **行事曆共享電郵**，即可自動化組織內的協作。

**後續步驟**
- 嘗試其他權限等級（Editor、Owner）。  
- 將此邏輯整合至現有的排程或人力資源系統。  
- 探索其他 Aspose.Email 功能，如週期性事件或會議請求。

---

**最後更新：** 2026-09-17  
**測試環境：** Aspose.Email for Java 25.4（JDK 16 classifier）  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Email 建立行事曆項目（Java）](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java 依日期篩選 Exchange 約會](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [使用 Aspose.Email 建立 Exchange 行事曆（Java）– 完整指南](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}