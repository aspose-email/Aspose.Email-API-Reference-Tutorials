---
date: 2025-11-30
description: 學習如何使用 Aspose.Email for Java 附加圖片至電郵、發送嵌入圖片的 HTML 電郵，以及優化電郵的圖片大小。
language: zh-hant
linktitle: How to Attach Image to Email with Aspsoe.Email
second_title: Aspose.Email Java Email Management API
title: 如何使用 Aspose.Email for Java 在電郵中附加圖片
url: /java/advanced-email-attachments/embedding-images-as-attachments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Email for Java 附加圖片到電子郵件

在現代的電子郵件溝通中，**如何附加圖片到電子郵件**變得比以往更重要——視覺效果能提升互動率，並即時傳達您的訊息。本教學將完整說明如何將圖片作為附件、嵌入至 HTML 內文，並確保訊息在各郵件客戶端中呈現良好。我們也會分享發送帶嵌入圖片的 HTML 電子郵件以及優化圖片大小的最佳實踐技巧。

## 快速解答
- **建立電子郵件的主要類別是什麼？** `MailMessage`
- **哪個類別可在 HTML 內文中嵌入圖片？** `LinkedResource`
- **在正式環境發送郵件需要授權嗎？** 需要，必須購買商業版 Aspose.Email 授權。
- **如何減少附件大小？** 在加入之前先優化圖片（例如調整尺寸或壓縮）。
- **可以一次傳送多張圖片嗎？** 當然可以——只要為每張圖片設定唯一的 Content‑ID 即可。

## 什麼是將圖片附加到電子郵件？
將圖片附加到電子郵件即是把檔案加入郵件的 MIME 結構，使收件人能夠檢視。若使用 Content‑ID（CID）方式嵌入圖片，圖片會直接顯示在 HTML 內文中，而不是作為獨立附件，呈現出內嵌圖片的效果。

## 為什麼要發送帶嵌入圖片的 HTML 電子郵件？
在 HTML 中嵌入圖片可讓您設計更豐富的電子報、產品公告或支援票證。收件人能立即看到視覺內容，無需下載附件，從而提升開信率與整體互動。

## 前置作業
在開始之前，請確保您已具備：

- **Aspose.Email for Java** – 從官方網站下載：[Aspose.Email Java download](https://releases.aspose.com/email/java/)。
- 有效的 **SMTP 伺服器**（例如 Gmail、Outlook，或您自建的郵件中繼）。
- 您想要嵌入的圖片檔案（JPEG、PNG、GIF 等）。

> **專業提示：** *優化電子郵件圖片大小*，將寬度調整至 ≤600 px，並壓縮至 ≤100 KB。這可縮短載入時間，且不會觸發信箱大小限制。

## 建立電子郵件訊息
首先，匯入必要的命名空間，並實例化 `MailMessage`。此物件將保存主旨、收件人與郵件內文。

```java
// Import necessary libraries
import com.aspose.email.*;

// Create a new email message
MailMessage message = new MailMessage();
```

## 將圖片作為附件加入
接著，指向磁碟上的圖片檔案，並將其加入訊息的附件集合。稍後會以 Content‑ID 方式引用此附件。

```java
// Specify the path to the image file
String imagePath = "path/to/your/image.jpg";

// Attach the image to the email
Attachment attachment = new Attachment(imagePath);
message.getAttachments().add(attachment);
```

## 在 HTML 中嵌入已附加的圖片
為了在郵件內文中顯示圖片，建立一個 `LinkedResource` 包裹附件的資料流。指定唯一的 Content‑ID（例如 `image1`），並在 HTML 中使用 `cid:` 方案引用它。

```java
// Create a LinkedResource for the attached image
LinkedResource linkedImage = new LinkedResource(attachment.getContentStream(), "image/jpeg");
linkedImage.setContentId("image1");

// Create an HTML body with the embedded image
String htmlBody = "<html><body><h1>Check out this image:</h1><img src='cid:image1'></body></html>";
message.setHtmlBody(htmlBody);
message.getLinkedResources().addItem(linkedImage);
```

> **為什麼使用 `LinkedResource`？** 它告訴郵件客戶端此圖片是訊息內容的一部分，而非獨立下載，這對 **發送帶嵌入圖片的 HTML 電子郵件** 場景至關重要。

## 發送電子郵件
最後，使用 `SmtpClient` 設定您的伺服器資訊，並將訊息發送出去。請確保 SMTP 憑證具備以寄件者地址發信的權限。

```java
// Initialize the SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");

// Send the email
client.send(message);
```

當收件人開啟郵件時，HTML 內文會直接呈現圖片，提供流暢的視覺體驗。

## 常見問題與故障排除
| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 圖片未顯示 | Content‑ID 錯誤或缺少 `LinkedResource` | 確認 `linkedImage.setContentId("image1")` 與 HTML 中的 `src='cid:image1'` 相符。 |
| 電子郵件尺寸過大 | 圖片未優化（高解析度） | 在加入前先調整尺寸或壓縮圖片，目標 ≤100 KB。 |
| 電子郵件被標記為垃圾郵件 | 缺少正確的 MIME 標頭 | 確保 `SmtpClient` 使用 TLS/STARTTLS，並設定清晰的 `From` 位址。 |
| 內嵌圖片變成附件 | 客戶端不支援 CID | 在 `<img>` 標籤提供備援 URL（`src='cid:image1' alt='Image'`）。 |

## 常見問答

**Q: 如何在同一封郵件中嵌入多張圖片？**  
A: 為每張圖片重複附件與 `LinkedResource` 的步驟，為其指定唯一的 Content‑ID（如 `image2`、`image3`），並在 HTML 中相應引用。

**Q: 可以在純文字郵件中嵌入圖片嗎？**  
A: 純文字格式不支援嵌入圖片。您只能放入可點擊的 URL，讓收件人於瀏覽器中查看圖片。

**Q: 哪些圖片格式適合用於電子郵件嵌入？**  
A: JPEG、PNG 與 GIF 均被廣泛支援。照片建議使用 JPEG，需透明背景的圖形則使用 PNG。

**Q: 如何在郵件中控制圖片尺寸？**  
A: 可在 `<img>` 標籤加入 width/height 屬性，例如 `<img src='cid:image1' width='400' height='300'>`。

**Q: 嵌入圖片有尺寸限制嗎？**  
A: 雖然 SMTP 本身沒有嚴格限制，多數郵件服務商建議總郵件大小保持在 5 MB 以下。優化圖片大小有助於遠低於此上限。

## 結論
現在您已掌握 **如何使用 Aspose.Email for Java 附加圖片到電子郵件**，並能將其嵌入 HTML 內文，同時遵循 **優化圖片大小以供電子郵件使用** 的最佳實踐。此技巧讓您能打造視覺吸引且在各郵件客戶端中表現專業的訊息。

---

**最後更新：** 2025-11-30  
**測試環境：** Aspose.Email for Java 24.11（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}