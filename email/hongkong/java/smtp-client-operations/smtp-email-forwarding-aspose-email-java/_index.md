---
"date": "2025-05-29"
"description": "學習如何使用 Aspose.Email for Java 設定 SMTP 用戶端並有效率地轉送郵件。非常適合企業應用程式開發人員。"
"title": "使用 Aspose.Email for Java 進行 SMTP 電子郵件轉發－綜合指南"
"url": "/zh-hant/java/smtp-client-operations/smtp-email-forwarding-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 進行 SMTP 電子郵件轉發：綜合指南

在數位時代，以程式設計方式管理電子郵件對於開發企業或客戶通訊系統的開發人員至關重要。本指南詳細介紹如何使用 Aspose.Email for Java 設定 SMTP 用戶端，從而有效率地轉發電子郵件，而無需使用 `MailMessage`。讓我們來探索一下這個強大的工具如何滿足您的電子郵件自動化需求。

## 您將學到什麼：
- 使用 Aspose.Email for Java 設定 SMTP 用戶端
- 使用集合管理電子郵件收件人
- 直接從文件流轉發電子郵件

**先決條件：** 在深入研究之前，請確保您已準備好以下設定以有效遵循本教學。

### 先決條件
若要成功完成本指南，請確保您已：

- **庫和依賴項：**
  - Aspose.Email for Java 版本 25.4 或更高版本。
  
- **環境設定：**
  - 相容的 JDK（Java 開發工具包），最好是我們的 Maven 依賴項中的分類器指定的 JDK 16。
- **知識前提：**
  - 對 SMTP 協定有基本的了解
  - 熟悉 Java 程式設計

## 設定 Aspose.Email for Java

使用 Maven 整合 Aspose.Email 到你的專案中非常簡單。加入以下依賴到你的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得許可證
Aspose.Email 提供免費試用許可證，供您無限測試其全部功能。取得方式如下：

1. **免費試用：** 訪問 [Aspose 的免費試用頁面](https://releases.aspose.com/email/java/) 下載並開始使用評估版本。
2. **臨時執照：** 如需延長測試時間，請透過以下方式申請臨時許可證 [許可證請求頁面](https://purchase。aspose.com/temporary-license/).
3. **購買：** 如果您發現 Aspose.Email 對您的專案有益，請考慮購買完整許可證 [Aspose 的購買頁面](https://purchase。aspose.com/buy).

### 基本初始化和設定

一旦 Aspose.Email 包含在您的專案中，請初始化必要的元件：

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com"; // 您的 SMTP 伺服器位址
String username = "username";    // 身份驗證的使用者名稱
int smtpPort = 587;              // 埠號，TLS/STARTTLS 通常為 587
String password = "password";    // 身份驗證密碼

// 使用指定的憑證建立 SmtpClient 實例。
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

## 實施指南

### SMTP 用戶端配置
本節將指導您配置用於傳送電子郵件的 SMTP 用戶端。透過設定 `SmtpClient`，您可以使用指定的憑證和安全性選項與您的電子郵件伺服器建立連線。

#### 概述
配置涉及指定您的 SMTP 主機、連接埠、使用者名稱、密碼和安全性選項 - 通常為安全連接的 SSLExplicit。

```java
import com.aspose.email.SecurityOptions;
import com.aspose.email.SmtpClient;

String host = "mail.domain.com";
String username = "username";
int smtpPort = 587;
String password = "password";

// 使用指定的憑證初始化 SmtpClient。
SmtpClient client = new SmtpClient(host, smtpPort, username, password, SecurityOptions.SSLExplicit);
```

### 電子郵件收件者集合
使用以下方式簡化了收件者清單的管理 `MailAddressCollection`，它允許您輕鬆添加多個電子郵件地址。

#### 概述
此集合可用於儲存和管理收件者的電子郵件，以便進行轉發或傳送操作。

```java
import com.aspose.email.MailAddressCollection;

// 建立一個新的 MailAddressCollection 實例。
MailAddressCollection recipients = new MailAddressCollection();

// 將多個收件者新增至集合中。
recipients.add("to1@domain.com");
recipients.add("to2@domain.com");
```

### 不使用 MailMessage 進行郵件轉發
這個強大的功能允許您直接使用 `FileInputStream` 和 `SmtpClient`。

#### 概述
而不是創建新的 `MailMessage`，此方法使用現有的 EML 文件，從而可以有效地進行批量轉發。

```java
import java.io.FileInputStream;
import java.io.IOException;

String fileName = "YOUR_DOCUMENT_DIRECTORY/test.eml"; // EML 檔案的路徑

// 開啟電子郵件檔案的 FileInputStream。
FileInputStream fos = new FileInputStream(fileName);

try {
    // 使用 SmtpClient 實例和收件者集合轉送電子郵件。
    client.forward("Sender@domain.com\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}