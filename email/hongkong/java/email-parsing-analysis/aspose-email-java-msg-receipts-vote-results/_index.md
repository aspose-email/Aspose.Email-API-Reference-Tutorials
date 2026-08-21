---
date: '2026-06-13'
description: 了解如何使用 Aspose.Email for Java 讀取 MSG 檔案並解析 MSG 附件，並有效提取傳送/閱讀回執與投票結果。內容包括設定、程式碼與最佳實踐。
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: 如何使用 Aspose.Email for Java 讀取 MSG 檔案
url: /zh-hant/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java 讀取 MSG 檔案

## 介紹

以程式方式讀取 MSG 檔案可讓您從 Outlook 訊息中取得有價值的追蹤資料——傳送回執、已讀確認以及投票結果。本指南將示範 **如何讀取 msg** 檔案，說明必要的設定步驟，並展示如何有效擷取回執與投票資訊。

## 快速解答
- **什麼函式庫負責 MSG 解析？** Aspose.Email for Java.  
- **我可以擷取已讀回執嗎？** 可以，API 會回傳傳送與已讀的時間戳記。  
- **投票資料可取得嗎？** 當然可以；您可以取得每位收件人的投票回應。  
- **我需要授權嗎？** 試用版可用於測試；付費授權會移除評估限制。  
- **需要哪個 Java 版本？** 建議使用 Java 16 或更新版本。

## Aspose.Email for Java 是什麼？

Aspose.Email for Java 是一個獨立的 Java 函式庫，讓您在不需要 Microsoft Outlook 的情況下建立、操作與轉換電子郵件格式。它提供了豐富的物件模型，支援 MSG、EML、PST 以及其他多種格式，讓開發人員能直接在 Java 程式碼中處理電子郵件資料。（45 個字）

## 為何使用 Aspose.Email for Java 讀取 MSG 檔案？

Aspose.Email for Java 支援 **30+ 電子郵件格式**，且可在不將整個檔案載入記憶體的情況下處理高達 **500 MB** 的 MSG 檔案。其高效能的解析引擎降低 CPU 與記憶體使用量，適合大規模郵件封存處理與即時分析情境。（48 個字）

## 前置條件

- **函式庫與相依性：** Aspose.Email for Java 版本 25.4 或更新，以及 JDK 16+ 執行環境。  
- **IDE：** IntelliJ IDEA、Eclipse，或任何支援 Maven 的 Java 相容 IDE。  
- **基本技能：** 熟悉 Java 語法與物件導向概念。

## 取得授權

使用 Aspose.Email for Java 需要取得授權：

- **免費試用：** 從 [Aspose 的網站](https://releases.aspose.com/email/java/) 取得免費試用版。  
- **臨時授權：** 可於 [購買頁面](https://purchase.aspose.com/temporary-license/) 申請臨時授權。  
- **購買：** 若您對評估結果滿意，可透過 [Buy Aspose Products](https://purchase.aspose.com/buy) 頁面購買授權，以完整使用所有功能。

## 如何從 MSG 檔案中擷取已讀與傳送回執資訊？

載入 MSG 檔案，遍歷其收件者，並讀取 `DeliveryTime` 與 `ReadTime` 屬性。此方法會回傳每位收件者的郵件伺服器傳送訊息以及收件者開啟訊息的精確時間戳記，為分析提供精確的追蹤資料。（53 個字）

### 步驟 1：載入 MSG 檔案
MapiMessage 是 Aspose.Email 中代表 Outlook MSG 訊息的類別。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### 步驟 2：遍歷收件者
MapiRecipient 代表 MSG 檔案中單一的收件者（收件、抄送或密件副本）。  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 步驟 3：取得並列印傳送時間
DeliveryTime 是 MapiRecipient 的屬性，保存訊息傳送至收件者伺服器的時間戳記。  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 步驟 4：取得並列印已讀時間
ReadTime 是 MapiRecipient 的屬性，指示收件者開啟訊息的時間（若有此資訊）。  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## 如何從 MSG 檔案中讀取投票結果？

載入訊息後，API 會公開每位收件者的投票回應及回應時間，讓您能以程式方式彙總投票結果。此資料可用於產生摘要報告，或直接匯入商業智慧儀表板，以快速做出決策。（53 個字）

### 步驟 1：載入 MSG 檔案
再次使用 MapiMessage 以存取嵌入於 MSG 檔案中的投票資訊。  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### 步驟 2：遍歷收件者
MapiRecipient 提供對每位參與者投票選擇與回應時間的存取。  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### 步驟 3：取得並列印回應
`VotingResponse` 屬性包含實際的投票結果（例如「Accept」、「Decline」或自訂選項）。  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### 步驟 4：取得並列印回應時間
`VotingResponseTime` 記錄收件者提交投票的時間，便於對投票活動進行時間序列分析。  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## 實務應用

1. **電子郵件活動追蹤：** 透過分析回執時間戳記來衡量開啟率與傳送成功率。  
2. **調查分析：** 整合 Outlook 投票的結果，以快速做出決策。  
3. **客戶回饋管理：** 將回應資料匯入 CRM 或分析平台，以獲得更深入的洞見。

將這些擷取結果與資料庫或 BI 工具整合，可提升原始電子郵件資料的價值。

## 效能考量

- 以 **chunks**（分塊）方式處理大型 MSG 檔案，以降低記憶體使用量。  
- 處理數千封訊息時，使用 **streaming APIs**（串流 API）。  
- 將收件者資料存放於輕量級集合（如 `ArrayList` 或 `HashMap`），以加速查詢。

## 常見問題與解決方案

- **Null 時間戳記：** 缺少 `ReadTime` 通常表示收件者尚未開啟訊息。  
- **大型附件：** 若 MSG 含有巨大的附件，請啟用 `LoadOptions.setPreserveEmbeddedResources(false)` 以避免將其載入記憶體。  
- **編碼問題：** 讀取非 ASCII 內容時，請透過 `MailMessage.setCharset(Charset.forName("UTF-8"))` 設定正確的代碼頁。

## 常見問答

**Q: 如何處理大於 500 MB 的 MSG 檔案？**  
A: 將檔案切分為較小的片段，或使用串流 API 讀取部分內容，而不需完整載入記憶體。

**Q: 我可以直接將擷取的資料儲存到資料庫嗎？**  
A: 可以，將回執與投票欄位對映至資料庫結構，並使用 JDBC 或 ORM 進行持久化。

**Q: 這個函式庫能在 Linux 環境下運作嗎？**  
A: 完全可以；Aspose.Email for Java 與平台無關，只要有支援的 JDK，即可在任何作業系統上執行。

**Q: 有沒有辦法在讀取回執時同時擷取附件？**  
A: 載入 MSG 後使用 `MailMessage.getAttachments()`；此方法會回傳所有嵌入檔案的集合。

**Q: 若遇到錯誤，有哪些支援選項？**  
A: 可透過官方 Aspose Email 論壇尋求社群協助，或以有效授權開立支援票證。

## 資源
- **文件說明：** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **文件說明（重複）：** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **下載 SDK：** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **下載區段：** [Download Section](https://releases.aspose.com/email/java/)  
- **購買授權：** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **免費試用：** 從 [Free Trial Version](https://releases.aspose.com/email/java/) 開始  
- **臨時授權：** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援論壇：** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **支援論壇（重複）：** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-06-13  
**測試環境：** Aspose.Email for Java 25.4  
**作者：** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## 相關教學

- [如何使用 Aspose.Email for Java 載入與解析 Outlook MSG 檔案：完整指南](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [將 MSG 轉換為 EML 並使用 Aspose.Email for Java 管理附件](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [在 Java 中擷取內嵌附件 – MSG 檔案使用 Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}