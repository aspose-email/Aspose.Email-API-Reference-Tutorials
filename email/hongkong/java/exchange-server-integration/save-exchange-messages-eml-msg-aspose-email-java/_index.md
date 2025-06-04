---
"date": "2025-05-29"
"description": "學習如何使用 Aspose.Email for Java 將 Exchange 郵件儲存為 EML 或 MSG 格式。本指南涵蓋設定、實施和實際應用。"
"title": "如何使用 Aspose.Email for Java 將 Exchange 郵件儲存為 EML/MSG 完整指南"
"url": "/zh-hant/java/exchange-server-integration/save-exchange-messages-eml-msg-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 將 Exchange 郵件儲存為 EML/MSG

## 介紹

在 Exchange Server 上處理大量資料時，高效的電子郵件管理至關重要。將郵件儲存為 EML 或 MSG 等格式對於歸檔或進一步處理至關重要。本教學提供了使用 Aspose.Email for Java 儲存 Exchange 郵件的全面指南。

Aspose.Email 簡化了將電子郵件功能整合到應用程式中的過程，實現了與各種郵件伺服器的無縫互動。在本文中，我們將探討如何使用 Aspose.Email for Java 將 Exchange 郵件儲存為 EML 和 MSG 格式。

### 您將學到什麼：
- 設定 Aspose.Email for Java
- 以 EML 格式儲存來自 Exchange Server 信箱的郵件
- 以 EML 格式儲存訊息到輸出流
- 以 MSG 格式儲存訊息

讓我們從先決條件開始吧！

## 先決條件

在深入實施之前，請確保您已：
1. **所需庫**：Aspose.Email for Java 函式庫版本 25.4 或更高版本。
2. **環境設定**：
   - 您的系統上安裝了 Java 開發工具包 (JDK) 16 或更高版本。
   - 配置有 JDK 的 IDE，例如 IntelliJ IDEA 或 Eclipse。
3. **知識前提**：
   - 對 Java 程式設計有基本的了解
   - 熟悉 Maven 的依賴管理

## 設定 Aspose.Email for Java

首先，將 Aspose.Email 庫新增到您的專案中。如果您使用 Maven，請將以下依賴項新增至您的 `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 許可證獲取

您可以免費試用 Aspose.Email for Java，或申請臨時授權以不受限制地探索其全部功能：

- **免費試用**：從下載庫 [Aspose 的發佈頁面](https://releases。aspose.com/email/java/).
- **臨時執照**申請臨時駕照 [Aspose的購買網站](https://purchase。aspose.com/temporary-license/).

取得許可證文件後，請在使用任何 Aspose.Email 功能之前在程式碼中對其進行初始化：

```java
License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## 實施指南

在本節中，我們將引導您將 Exchange 訊息儲存為 EML 和 MSG 格式。

### 使用 EWS 將郵件儲存為 EML

此功能可讓您以廣泛使用的 EML 格式儲存來自 Exchange Server 信箱的訊息。

#### 步驟 1：建立 IEWSClient 實例

首先，透過建立下列實例建立與 Exchange 伺服器的連接 `IEWSClient` 使用您的憑證：

```java
IEWSClient client = EWSClient.getEWSClient(
    "https://outlook.office365.com/exchangeews/exchange.asmx",
    "testUser",
    "pwd",
    "domain"
);
```

#### 步驟 2：列出收件匣中的郵件

接下來，檢索收件匣中的郵件清單：

```java
ExchangeMessageInfoCollection msgCollection = client.listMessages(
    client.getMailboxInfo().getInboxUri()
);
```

#### 步驟3：迭代並將每個訊息儲存為EML

最後，循環遍歷每個訊息並將其以 EML 格式儲存到磁碟：

```java
for (ExchangeMessageInfo msgInfo : msgCollection) {
    String strMessageURI = msgInfo.getUniqueUri();
    
    client.saveMessage(
        strMessageURI,
        "YOUR_OUTPUT_DIRECTORY" + msgInfo.getMessageId() + ".eml"
    );
}
```

### 使用 EWS 將訊息儲存到 OutputStream

此功能可讓您將訊息直接儲存到輸出流，這對於串流資料或進一步處理很有用。

#### 步驟 1：建立 IEWSClient 實例

和以前一樣，先創建 `IEWSClient` 實例：

```java
IEWSClient client = EWSClient.getEWSClient(
    "https://outlook.office365.com/exchangeews/exchange.asmx",
    "testUser",
    "pwd",
    "domain"
);
```

#### 步驟 2：列出收件匣中的郵件

檢索收件匣中的郵件：

```java
ExchangeMessageInfoCollection msgCollection = client.listMessages(
    client.getMailboxInfo().getInboxUri()
);
```

#### 步驟 3：迭代並將每個訊息儲存到 OutputStream

循環遍歷每個訊息，創建一個輸出流來保存它：

```java
for (ExchangeMessageInfo msgInfo : msgCollection) {
    String strMessageURI = msgInfo.getUniqueUri();
    
    try {
        OutputStream outputStream = new FileOutputStream(
            "YOUR_OUTPUT_DIRECTORY" + msgInfo.getMessageId() + "_Out.eml"
        );
        
        client.saveMessage(strMessageURI, outputStream);
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

### 使用 EWS 以 MSG 格式儲存訊息

以原生 MSG 格式儲存訊息有助於與 Microsoft Outlook 相容。

#### 步驟 1：建立 IEWSClient 實例

建立與 Exchange 伺服器的連線：

```java
IEWSClient client = EWSClient.getEWSClient(
    "https://outlook.office365.com/exchangeews/exchange.asmx",
    "testUser",
    "pwd",
    "domain"
);
```

#### 步驟 2：列出收件匣中的郵件

檢索收件匣中的郵件：

```java
ExchangeMessageInfoCollection msgCollection = client.listMessages(
    client.getMailboxInfo().getInboxUri()
);
```

#### 步驟 3：取得每個訊息並將其儲存為 MSG

取得每個訊息的詳細資訊並以 MSG 格式儲存：

```java
for (ExchangeMessageInfo msgInfo : msgCollection) {
    String strMessageURI = msgInfo.getUniqueUri();
    
    MailMessage msg = client.fetchMessage(strMessageURI);
    
    msg.save(
        "YOUR_OUTPUT_DIRECTORY" + msgInfo.getMessageId() + ".msg",
        SaveOptions.getDefaultMsg()
    );
}
```

## 實際應用

以下是保存 Exchange 訊息的一些實際用例：
1. **電子郵件歸檔**：透過以 EML 或 MSG 格式存檔電子郵件來儲存重要的通訊記錄。
2. **資料遷移**：透過將訊息匯出為相容格式，方便從一個電子郵件系統遷移到另一個電子郵件系統。
3. **法律合規**：透過維護所有通訊的安全檔案來確保遵守法律要求。
4. **備份解決方案**：建立關鍵電子郵件資料的備份，以用於災難復原。
5. **與第三方應用程式集成**：使用已儲存的電子郵件作為其他應用程式的輸入，例如 CRM 系統或文件管理平台。

## 性能考慮

在實現這些功能時，請考慮以下提示以優化效能：
- 盡可能批量處理訊息以減少伺服器負載。
- 監控記憶體使用情況並透過在使用後關閉流來有效地管理資源。
- 如果支持，則利用非同步處理來提高應用程式的回應能力。

## 結論

在本教學中，我們探索如何使用 Aspose.Email for Java 將 Exchange Server 郵件儲存為 EML 或 MSG 格式。您學習如何設定庫、如何連接到 Exchange 伺服器以及如何實現不同格式的郵件保存功能。

為了進一步提升您的技能，您可以考慮探索 Aspose.Email 的其他功能，例如行事曆管理和聯絡人同步。立即嘗試在您的專案中實施這些解決方案！

## 常見問題部分

**問題1：什麼是 Aspose.Email for Java？**
A1：Aspose.Email for Java 是一個強大的函式庫，它在 Java 應用程式中提供電子郵件處理功能，允許與各種郵件伺服器無縫整合。

**問題 2：如何使用 Aspose.Email 將 Exchange 訊息儲存為 EML？**
A2：使用 `saveMessage` 方法來自 `IEWSClient` 透過指定訊息 URI 和輸出路徑將訊息儲存為 EML 格式的類別。

**問題3：我可以將 Aspose.Email 用於非 Microsoft 電子郵件伺服器嗎？**
A3：是的，Aspose.Email 支援多種協議，包括 IMAP、POP3、SMTP 等，使其適用於各種電子郵件系統。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}