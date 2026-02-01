---
date: 2026-02-01
description: 學習如何使用 Aspose.Email for Java 建立 HTML 電郵圖片，包括如何發送內嵌圖片的電郵、在 Java 中嵌入圖片的電郵，以及提取電郵中的內嵌圖片。
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: 如何使用 Aspose.Email for Java 建立帶嵌入式內嵌附件的 HTML 電郵圖片
url: /zh-hant/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Email for Java 建立嵌入式內嵌附件的 HTML 電子郵件圖像

將圖像直接嵌入電子郵件可讓您的訊息看起來更精緻，並確保收件人無需下載額外檔案即可看到圖形。在本教學中，您將學習如何 **建立圖像的郵件，內容涵蓋從設定函式庫、建立 HTML 電子郵件、加入內嵌資源，到最終傳送訊息的全部步驟。

## 快速解答
- **內嵌圖像的主要類別是什麼？** `LinkedResource`
- **哪個方法在 HTML 中引用圖像？** 在 `<img>` 標籤中使用 `cid:yourContentId授權嗎？** 免費試用版可用於測試；正式環境需購買授權
- **可以使用任何 SMTP 伺服器傳送郵件嗎？** 可以，只需使用您的所有主流郵件客戶端相容嗎？** 大多數現代客戶端（Outlook、Gmail、Thunderbird）皆支援 CID 內嵌圖像

## 什麼是內嵌附件（嵌入式圖像）？

內嵌附件——有時稱為嵌入式或 CID 圖像——是存放於電子郵件 MIME 主體內的檔案。它們透過 **Content‑ID**（CID）在訊息的 HTML 部分被引用。此技術讓您 **在電子郵件中嵌會以可下載的獨立附件形式出現。

## 為什麼在 Java 中使用嵌入式圖像建立 HTML 電子郵件圖像？

- **專業外觀：** 標誌、橫幅與產品圖片會即時顯示。  
- **提升互動率：** 收件人較願意閱讀外觀完整的電子郵件。  
- **免除額外點擊：** 使用者無需下載附件即可看到圖像。  
- **品牌形象一致性：** 您的品牌資產會與訊息內容保持件

- Aspose.Email for Java 函式庫（從官方 [Aspose.Email for Java 文件](https://reference.aspose.com/email/java/) 下載）  
- Java 8 以上開發環境  
- 可用於寄送郵件的 SMTP 伺服器存取權限  
- 欲嵌入的圖像檔案（例如 `logo.png`）

## 逐步指南

### HTML 內容的簡易 `MailMessage`。這將作為之後嵌入圖像的畫布。

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### 步驟 2：使用 `LinkedResource` 加入內嵌圖像

現在我們要嵌入圖像。`LinkedResource` 類別代表內嵌附件。為其指派唯一的 **Content‑ID**，並在 HTML 內容中以 `cid:` 方式引用。

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **專業提示：** 請保持 `ContentId` 簡潔且在訊息內唯一，以避免衝突。

### 步驟 3：透過 `SmtpClient` 傳送電子郵件

設定您的送，收件人即可即時看到。

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### 步擷取內嵌圖像（可選）

如果需要處理含有嵌入案並存取其 `LinkedResources`。

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## 常見問題與解決方法

| 問題 | 為何發生 | 解決方式 |
|------|----------|----------|
| **Content‑ID 不匹配** | HTML 中的 `cid:` 參考與 `LinkedResource`相同（例如 `像路徑不正確或檔案不存在。 | 確認絕對或相對路徑正確，且檔案確實存在於伺服器上。 |
| **SMTP 認證失敗** | | 再次檢查主機、埠號、使用者名稱與密碼 TLS/SSL。 |
| **某些客戶端未顯示圖像** | 部分客戶端會阻擋外部資源。 | 使用 CID 內嵌圖像（如範例所示），而非外部 URL。 |

##您可從 [文件](https://reference.aspose.com/email/java/) 下載 Aspose.Email for Java。請依照安裝說明將其設定於您的專案中。

**Q：可以將 Aspose.Email for其他 Java 函式庫順暢整合，讓您可將郵件處理與 PDF 產生、OCR 或資料庫存取等功能結合。

**Q：內嵌附件，如 PNG、型（例如 SVG）作為內嵌資源。

**Q：如何在 HTML 電子郵件中處理內嵌附件？**  
A：使用 `LinkedResource` 類別指定 `ContentId`，將其加入 `message.getLinkedResources()`，並在 HTML 內容中以 `<img src='cid:yourContentId'>` 方式引用。

**Q：Aspose.Email for Java 是否相容於不同的郵件伺服器？**  
A：可以，它支援任何 SMTP、IMAP、POP3 伺服器。只需提供正確的伺服器位址、埠號與認證資訊。

---

**Last Updated:** 2026-02-01  
**Tested With:** Aspose.Email for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}