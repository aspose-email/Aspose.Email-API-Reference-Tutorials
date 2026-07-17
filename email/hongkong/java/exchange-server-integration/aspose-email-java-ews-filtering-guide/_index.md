---
date: '2026-07-17'
description: 使用 Aspose.Email Java 與 EWS 篩選電郵的方法：學習日期、寄件者與主旨的篩選技巧，以簡化您的電郵箱。
keywords:
- Aspose.Email Java
- email filtering techniques
- Exchange Web Services (EWS)
lastmod: '2026-07-17'
og_description: 使用 Aspose.Email Java 與 EWS 篩選電郵。探索日期、寄件者與主旨的篩選技巧，讓您的電郵箱保持井然有序。
og_image_alt: Guide to filtering emails with Aspose.Email Java and Exchange Web Services
og_title: 使用 Aspose.Email Java 與 EWS 篩選電郵
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: 'How to filter emails using Aspose.Email Java and EWS: learn date,
    sender, and subject filtering techniques to streamline your mailbox.'
  headline: How to Filter Emails with Aspose.Email Java & EWS Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Email works with Office 365 Exchange Online by pointing the
      service URL to `https://outlook.office365.com/EWS/Exchange.asmx`.
    question: Can I use this approach with Office 365?
  - answer: Absolutely—use `OAuthCredentials` to authenticate without storing user
      passwords.
    question: Does Aspose.Email support OAuth authentication?
  - answer: The API can handle mailboxes of **several gigabytes**; because it streams
      results, memory consumption stays low.
    question: What is the maximum mailbox size I can process?
  - answer: Add a `SearchFilter.ContainsSubstring` on the `AttachmentNames` property,
      then iterate only matching items.
    question: How do I filter attachments by file type?
  - answer: Yes—pass a `SortDirection` and the property you want to sort on (e.g.,
      `DateTimeReceived`) to the `FindItems` call.
    question: Is there a way to sort results?
  type: FAQPage
tags:
- how to filter emails
- aspose email java
- filter emails by date
- filter emails by sender
- ews integration
title: 使用 Aspose.Email Java 與 EWS 的電郵篩選指南
url: /zh-hant/java/exchange-server-integration/aspose-email-java-ews-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Aspose.Email Java 與 EWS 的電郵篩選：完整指南

## 介紹

**如何有效篩選電郵** 是任何使用 Microsoft Exchange 或現代郵箱的人必備的核心技能。無論您是開發企業級自動化的程式設計師，或是想保持收件匣整潔的個人，用對篩選技巧都能節省大量手動處理時間。在本指南中，我們將結合 Aspose.Email for Java 與 Exchange Web Services (EWS)，示範如何依日期、發件人、主旨、網域、收件人，甚至使用邏輯運算子結合多重條件來篩選電郵。

### 您將學習的內容
- 使用 Java 中的 EWS 篩選訊息的技巧。  
- 根據日期、發件人、主旨等條件篩選電郵。  
- 實作分頁支援以處理大型信箱。  
- 在實務情境中應用這些篩選方法。  
- 使用 Aspose.Email Java 時的效能考量與最佳實踐。

完成本教學後，您將能撰寫乾淨且效能優異的 Java 程式碼，精準取得 Exchange 伺服器上所需的訊息。

## 快速回答
- **主要的函式庫是什麼？** Aspose.Email for Java。  
- **使用哪種協議？** Exchange Web Services (EWS)。  
- **可以依日期範圍篩選嗎？** 可以 – 在 `SearchFilter` 中使用 `DateTime` 條件。  
- **支援分頁嗎？** 當然，API 提供帶有 offset/limit 的 `ItemView`。  
- **生產環境需要授權嗎？** 需要，商業授權會移除評估限制。

## Aspose.Email for Java 是什麼？
Aspose.Email for Java 是一套完整的 API，讓您在不需要 Outlook 或其他客戶端的情況下，以程式方式存取電郵伺服器、MIME 訊息與 Exchange Web Services。它抽象化底層協議，讓您專注於業務邏輯。此函式庫同時支援本地部署的 Exchange 伺服器與 Exchange Online，提供統一的 API 以因應各種部署情境。

## 為什麼要將 Aspose.Email 與 EWS 結合使用？
Aspose.Email 支援 **50+** 電郵協議，且每小時可處理 **數十萬封訊息**，同時記憶體使用量低於 **100 MB**，得益於其串流架構。這樣的效能表現使其成為企業規模信箱自動化的理想選擇。此外，它內建 OAuth 與現代驗證支援，簡化與 Office 365 環境的安全連線。

## 前置條件

- **必需的函式庫**：在專案中加入 Aspose.Email 函式庫。  
- **環境設定**：需要一個可用的 Java 應用程式開發環境。  
- **知識前提**：熟悉 Java 程式設計與電郵協議將有助於學習。

## 設定 Aspose.Email for Java

### Maven 安裝
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
- **免費試用**：先使用免費試用版探索 Aspose.Email 的功能。  
- **臨時授權**：取得臨時授權以延長評估時間。  
- **購買**：若工具符合需求，考慮購買完整授權。

透過匯入必要的套件並使用 EWS 憑證建立與郵件伺服器的連線，初始化並設定 Aspose.Email。此步驟對以程式方式存取信箱資料至關重要。

## 如何在 Java 中使用 EWS 篩選電郵？

`ExchangeService` 是 Aspose.Email 中代表與 Exchange 伺服器連線的類別。  
`SearchFilter` 定義在伺服器上定位項目的條件。  
`FindItems` 執行搜尋並回傳符合的項目。  
`ItemView` 控制分頁與每次請求回傳的項目數量。

載入具備憑證的 `ExchangeService` 實例，建立符合條件的 `SearchFilter`，再以 `ItemView` 呼叫 `FindItems` 取得所需訊息。這一行程式碼模式——連線 → 篩選 → 取得——涵蓋大多數使用情境，並在啟用分頁時可擴展至大型信箱。

## 實作指南

### 使用 EWS 篩選訊息

#### 概述
篩選允許您直接從信箱中僅取得符合特定條件（如特定主旨或日期）的電郵。
```java
import com.aspose.email.EWSClient;
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.MailQuery;
import com.aspose.email.ExchangeQueryBuilder;
import java.text.ParseException;
import java.text.SimpleDateFormat;

public class FilterMessagesUsingEWS {
    public static void main(String[] args) throws ParseException {
        // Establish a connection to the EWS server
        IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");

        SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
        
        // Build a query for emails containing 'Newsletter' in the subject
        ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
        builder.getSubject().contains("Newsletter");
        builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
        MailQuery query = builder.getQuery();

        // Retrieve messages matching the criteria
        ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
    }
}
```
**說明**：此程式碼建立與信箱的連線，並建立查詢以篩選主旨含有「Newsletter」且在特定日期之後的電郵。

### 如何依今天的日期篩選電郵？

`SearchFilter.IsEqualTo` 建立一個篩選條件，匹配屬性等於給定值。  
`DateTimeReceived` 為表示電郵接收時間的屬性。

載入當前日期，於 `DateTimeReceived` 屬性上建立 `SearchFilter.IsEqualTo`，並執行查詢。此篩選僅回傳在執行程式當天收到的訊息，使每日處理腳本變得簡單。您亦可將此篩選與發件人或主旨等其他條件結合，以進一步縮小當天的結果。

### 如何依日期範圍篩選電郵？

`SearchFilter.IsGreaterThanOrEqualTo` 建立一個篩選條件，匹配屬性值大於或等於指定值。  
`SearchFilter.IsLessThanOrEqualTo` 建立一個篩選條件，匹配屬性值小於或等於指定值。  
`SearchFilter.And` 結合多個篩選條件，使所有條件必須同時滿足。

定義開始與結束的 `DateTime`，分別使用 `SearchFilter.IsGreaterThanOrEqualTo` 與 `SearchFilter.IsLessThanOrEqualTo`，再以 `SearchFilter.And` 合併兩者。結果集合將包含所有落在指定時間窗口內的訊息。此方法讓您能取得任意自訂期間內的所有通訊，例如上一季或特定專案的時間範圍。

### 如何依特定發件人篩選電郵？

`SearchFilter.IsEqualTo` 建立一個篩選條件，匹配屬性等於給定值。

於 `From` 屬性建立 `SearchFilter.IsEqualTo`，指定發件人的電郵地址。此篩選可將所有來自該聯絡人的訊息隔離，適用於優先收件匣或合規性檢查。若地址不完整或需依網域篩選，可使用 `SearchFilter.ContainsSubstring` 進行部分匹配。

### 如何依特定網域篩選電郵？

`SearchFilter.ContainsSubstring` 建立一個篩選條件，匹配屬性包含指定子字串。

在 `From` 屬性上使用 `SearchFilter.ContainsSubstring`，傳入網域字串（例如 “@example.com”）。此篩選會抓取所有來自該網域的電郵，對於合作夥伴或供應商的監控非常有用。將此篩選與日期條件結合，可追蹤特定網域在不同時間段的通訊，協助安全稽核。

### 如何依特定收件人篩選電郵？

`SearchFilter.IsEqualTo` 建立一個篩選條件，匹配屬性等於給定值。

於 `ToRecipients` 集合上使用 `SearchFilter.IsEqualTo`，指定目標地址。此方式適合審核發送至特定信箱或通訊群組的訊息。若需針對多個收件人共享相同網域的情況，可使用 `SearchFilter.ContainsSubstring` 進行部分匹配。

### 如何使用 AND 邏輯結合查詢？

`SearchFilter.And` 結合多個篩選條件，使所有條件必須同時滿足。

使用 `SearchFilter.And` 連接多個 `SearchFilter` 物件。例如，將發件人篩選與主旨篩選結合，只取得來自可信發件人的新聞稿。AND 運算子確保僅回傳同時符合所有指定條件的項目，將結果集縮減至最相關的訊息。

### 如何使用 OR 邏輯結合查詢？

`SearchFilter.Or` 合併篩選條件，使任一條件符合即回傳。

使用 `SearchFilter.Or` 合併多個篩選條件，適用於需要抓取「來自某組發件人 **或** 包含特定關鍵字」的訊息。OR 邏輯可擴大搜尋範圍，確保不遺漏多類別中的關鍵通訊。

## 常見陷阱與技巧

- **分頁是必要的**：處理超過 1,000 項的信箱時，務必使用帶有頁面大小的 `ItemView` 以避免逾時。  
- **時區處理**：EWS 以 UTC 回傳日期；在比較前請轉換為本地時區。  
- **避免全信箱掃描**：務必在伺服器端套用 `SearchFilter`；客戶端過濾會浪費頻寬與記憶體。  
- **專業提示**：在應用程式生命週期內快取 `ExchangeService` 物件，以減少驗證開銷。

## 常見問答

**問：我可以在 Office 365 中使用此方法嗎？**  
答：可以，Aspose.Email 只要將服務 URL 指向 `https://outlook.office365.com/EWS/Exchange.asmx` 即可與 Office 365 Exchange Online 配合使用。

**問：Aspose.Email 支援 OAuth 驗證嗎？**  
答：當然支援——使用 `OAuthCredentials` 即可在不儲存使用者密碼的情況下完成驗證。

**問：我能處理的最大信箱大小是多少？**  
答：API 可處理 **數個 GB** 的信箱；由於採用串流方式，記憶體使用量保持在低水平。

**問：如何依檔案類型篩選附件？**  
答：在 `AttachmentNames` 屬性上加入 `SearchFilter.ContainsSubstring`，然後只遍歷符合條件的項目。

**問：有沒有方法對結果排序？**  
答：有——在呼叫 `FindItems` 時傳入 `SortDirection` 以及要排序的屬性（例如 `DateTimeReceived`），即可取得排序後的結果。

---

**最後更新：** 2026-07-17  
**測試環境：** Aspose.Email for Java 24.10  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Email for Java 建立 EWSClient 實例：Exchange Server 整合指南](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [如何使用 Aspose.Email Java 從 Exchange Server 下載電郵](/email/java/exchange-server-integration/aspose-email-java-exchange-server-download/)
- [使用 Aspose.Email for Java 管理 EWS 信箱資訊：完整指南](/email/java/exchange-server-integration/manage-ews-mailbox-info-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;

public class FilterMessagesBasedOnTodayDate {
    public static void main(String[] args) {
        // Build a query for today's emails
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getInternalDate().on(new Date());
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class FilterMessagesBasedOnDateRange {
    public static void main(String[] args) {
        // Build a query for emails received in the last 24 hours
        MailQueryBuilder builder = new MailQueryBuilder();
        Date today = new Date();
        builder.getInternalDate().beforeOrEqual(today);
        builder.getInternalDate().since(new Date(today.getTime() + TimeUnit.DAYS.toMillis(1)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificSender {
    public static void main(String[] args) {
        // Build a query for emails from 'saqib.razzaq@127.0.0.1'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("saqib.razzaq@127.0.0.1");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificDomain {
    public static void main(String[] args) {
        // Build a query for emails from 'SpecificHost.com'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class FilterMessagesBasedOnSpecificRecipient {
    public static void main(String[] args) {
        // Build a query for emails sent to 'recipient'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getTo().contains("recipient");
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;
import java.util.Date;
import java.util.concurrent.TimeUnit;

public class CombineQueriesWithAND {
    public static void main(String[] args) {
        // Build a combined query for specific domain, emails received before today,
        // and within the last 7 days
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com");
        builder.getInternalDate().before(new Date());
        builder.getInternalDate().since(new Date(new Date().getTime() + TimeUnit.DAYS.toMillis(-7)));
    }
}
```

```java
import com.aspose.email.MailQueryBuilder;

public class CombineQueriesWithOR {
    public static void main(String[] args) {
        // Build a query for emails either from 'SpecificHost.com' or containing 'Newsletter'
        MailQueryBuilder builder = new MailQueryBuilder();
        builder.getFrom().contains("SpecificHost.com")
                .or(builder.getSubject().contains("Newsletter"));
    }
}
```