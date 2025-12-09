---
date: 2025-12-01
description: 學習如何使用 Aspose.Email for Java 發送帶有嵌入圖像的電郵。本指南展示如何在電郵中嵌入圖像，以及如何使用 Java
  建立帶內嵌附件的 HTML 電郵。
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: 如何使用 Aspose.Email for Java 發送內嵌圖像的電郵
url: /zh-hant/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Email for Java 發送帶嵌入圖像的電郵

將圖像直接嵌入電郵可讓訊息看起來更精緻，且收件人無需下載額外檔案即可看到圖形。在本教學中，您將學習 **如何使用 Aspose.Email for Java 發送帶嵌入圖像的電郵**，內容涵蓋從設定函式庫、建立 HTML 電郵、加入內嵌資源，到最終發送訊息的完整流程。

## 快速解答
- **內嵌圖像的主要類別是什麼？** `LinkedResource`
- **哪個方法在 HTML 中引用圖像？** 在 `<img>` 標籤中使用 `cid:yourContentId`
- **開發階段需要授權嗎？** 免費試用可用於測試；正式上線需購買授權
- **可以使用任何 SMTP 伺服器發送電郵嗎？** 可以，只需以正確的伺服器資訊設定 `SmtpClient`
- **此方式與所有主流電郵客戶端相容嗎？** 大多數現代客戶端（Outlook、Gmail、Thunderbird）皆支援 CID 內嵌圖像

## 什麼是內嵌附件（嵌入圖像）？

內嵌附件——亦稱為嵌入圖像或 CID 圖像——是存放在電郵 MIME 主體內的檔案。它們透過 **Content‑ID**（CID）在訊息的 HTML 部分被引用。此技術讓您 **在電郵中嵌入圖像**，使圖像直接顯示於 `<img>` 標籤所在位置，而不會以可下載的附件形式出現。

## 為什麼在 Java 電郵中使用嵌入圖像？

- **專業外觀：** 標誌、橫幅與產品圖片可即時呈現  
- **提升互動率：** 完整的視覺內容更能吸引收件人閱讀  
- **免除額外點擊：** 使用者無需下載附件即可看到圖像  
- **品牌一致性：** 品牌資產與訊息內容保持同一行  

## 前置條件

- Aspose.Email for Java 函式庫（可從官方 [Aspose.Email for Java 文件](https://reference.aspose.com/email/java/) 下載）  
- Java 8+ 開發環境  
- 可用的 SMTP 伺服器以發送郵件  
- 想要嵌入的圖像檔案（例如 `logo.png`）  

## 步驟說明

### 步驟 1：建立基本的 HTML 電郵訊息

首先，建立一個帶有 HTML 內容的簡易 `MailMessage`，作為之後嵌入圖像的畫布。

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

現在將圖像嵌入電郵。`LinkedResource` 類別代表內嵌附件。為其指定唯一的 **Content‑ID**，並在 HTML 內以 `cid:` 方式引用。

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

> **小技巧：** 請確保 `ContentId` 簡潔且在同一封訊息中唯一，以免產生衝突。

### 步驟 3：透過 `SmtpClient` 發送電郵

設定 SMTP 參數並發送訊息。嵌入的圖像會隨電郵一起傳送，收件人即可即時看到。

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### 步驟 4：接收並擷取內嵌圖像（可選）

若需處理含有內嵌圖像的來信，可載入 `.eml` 檔案並存取其 `LinkedResources`。

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## 常見問題與解決方式

| 問題 | 為何會發生 | 解決方法 |
|------|------------|----------|
| **Content‑ID 不匹配** | HTML 中的 `cid:` 參考與 `LinkedResource` 設定的 `ContentId` 不相同。 | 確認兩者字串完全相同（例如 `image001` 與 `cid:image001`）。 |
| **找不到檔案** | 圖像路徑錯誤或檔案不存在。 | 檢查絕對或相對路徑，並確認檔案已放置於伺服器上。 |
| **SMTP 認證失敗** | 帳號密碼或伺服器設定錯誤。 | 再次核對主機、埠號、使用者名稱與密碼。必要時啟用 TLS/SSL。 |
| **部分客戶端不顯示圖像** | 某些客戶端會阻擋外部資源。 | 使用 CID 內嵌圖像（如本範例），而非外部 URL。 |

## 常見問答

**Q: 如何下載 Aspose.Email for Java？**  
A: 您可從 [文件](https://reference.aspose.com/email/java/) 下載 Aspose.Email for Java，並依照安裝說明將其加入專案。

**Q: Aspose.Email for Java 能與其他 Java 函式庫一起使用嗎？**  
A: 能，Aspose.Email 可順利與其他 Java 函式庫整合，讓您同時處理電郵、PDF 產生、OCR 或資料庫存取等工作。

**Q: 內嵌附件支援哪些檔案格式？**  
A: 支援常見的圖像格式，如 PNG、JPEG、GIF，亦支援其他文件類型（例如 SVG）作為內嵌資源。

**Q: 如何在 HTML 電郵中處理內嵌附件？**  
A: 使用 `LinkedResource` 類別設定 `ContentId`，將其加入 `message.getLinkedResources()`，並在 HTML 內以 `<img src='cid:yourContentId'>` 方式引用。

**Q: Aspose.Email for Java 是否相容不同的電郵伺服器？**  
A: 是的，支援任何 SMTP、IMAP、POP3 伺服器。只需提供正確的伺服器位址、埠號與驗證資訊即可。

**最後更新：** 2025-12-01  
**測試環境：** Aspose.Email for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}