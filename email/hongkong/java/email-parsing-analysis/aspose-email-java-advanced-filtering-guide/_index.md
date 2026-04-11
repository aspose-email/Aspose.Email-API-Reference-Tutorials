---
date: '2026-04-11'
description: 學習如何使用 Aspose.Email for Java 按主旨、日期、寄件者和網域篩選電子郵件。透過進階篩選，簡化收件箱管理。
keywords:
- filter emails by subject
- filter emails by date
- filter emails by sender
- filter emails by domain
title: 使用 Aspose.Email for Java 依主旨篩選電子郵件
url: /zh-hant/java/email-parsing-analysis/aspose-email-java-advanced-filtering-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 以 Aspose.Email for Java 按主旨篩選電子郵件

## 介紹

在當今的數位世界中，管理雜亂的收件匣是一項挑戰。無論您每天要篩選數百封電子郵件，或是希望優化電子郵件管理流程，高級篩選解決方案都是關鍵。**在本教學中，您將學習如何按主旨篩選電子郵件**，以及使用 Aspose.Email for Java 的日期、寄件者與網域等其他強大條件。透過 Aspose.Email for Java，開發人員能輕鬆且高效地篩選與管理電子郵件。本指南將逐步說明如何使用 Aspose.Email for Java 實作各種電子郵件篩選功能。

**您將學習：**
- 設定 Aspose.Email for Java
- 按主旨、日期、寄件者、網域與收件者篩選訊息
- 使用邏輯 AND/OR 運算結合查詢
- 了解電子郵件篩選中的大小寫敏感性

完成本指南後，您將能依據特定需求客製化電子郵件處理邏輯。讓我們先從前置條件開始。

## 快速解答
- **查詢 Exchange 信箱的主要類別是什麼？** `MailQueryBuilder` 可讓您建立彈性的篩選表達式。  
- **我可以在單一查詢中同時依主旨與日期篩選電子郵件嗎？** 可以——在同一個 `MailQueryBuilder` 上鏈接條件。  
- **如何篩選今天收到的訊息？** 使用 `builder.getInternalDate().on(new Date())`。  
- **是否支援大小寫敏感的篩選？** 在 `contains` 的第二個參數傳入 `true`。  
- **生產環境需要授權嗎？** 有效的 Aspose.Email 授權可解除所有功能限制。

## 前置條件

在使用 Aspose.Email for Java 實作進階電子郵件篩選之前，請確保您已具備：

- **必要函式庫：** Aspose.Email for Java 版本 25.4  
- **環境設定：** 需要至少 JDK 16 版的 Java 開發套件 (JDK)。  
- **知識前提：** 基本的 Java 程式設計概念與電子郵件協議的熟悉度。

## 設定 Aspose.Email for Java

首先，將 Aspose.Email 函式庫加入您的專案。若使用 Maven，請加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權

若要完整使用 Aspose.Email，您需要授權。您可以先使用免費試用版，或申請臨時授權以進行評估。若投入生產環境，建議購買授權以解鎖全部功能。

### 基本初始化與設定

使用必要的認證資訊初始化您的 `ExchangeClient`：

```java
ExchangeClient client = new ExchangeClient("YOUR_DOCUMENT_DIRECTORY", "username", "password", "domain");
```

## 實作指南

本節將每項功能拆解為可管理的步驟，協助您實作複雜的電子郵件篩選功能。

### 按主旨與日期篩選訊息

**Overview:** 此功能可依特定主旨關鍵字與內部日期，篩選 Exchange 信箱中的電子郵件。

#### 步驟實作：
1. **Initialize the Query Builder:**  
   ```java
   SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
   ExchangeQueryBuilder builder = new ExchangeQueryBuilder();
   builder.getSubject().contains("Newsletter");
   ```
2. **Set Date Filter:**  
   ```java
   try {
       builder.getInternalDate().on(sdf.parse("10/05/2016 10:00:00"));
   } catch (ParseException e) {
       e.printStackTrace(); // Handle parsing errors gracefully
   }
   ```
3. **Execute the Query:**  
   ```java
   MailQuery query = builder.getQuery();
   ExchangeMessageInfoCollection messages = client.listMessages(client.getMailboxInfo().getInboxUri(), query, false);
   ```

### 按今日日期篩選訊息

**Overview:** 取得今天收到的電子郵件。

#### Implementation:
1. **Build the Query:**  
   ```java
   MailQueryBuilder builderToday = new MailQueryBuilder();
   builderToday.getInternalDate().on(new Date());
   ```
2. **List Messages:**  
   使用 `client.listMessages()` 執行查詢，方式與前述範例相同，只需將特定日期改為今天。

### 在特定日期範圍內篩選訊息

**Overview:** 篩選在今天之前且自一天前起收到的電子郵件。

#### Implementation:
1. **Configure Date Range:**  
   ```java
   MailQueryBuilder builderDateRange = new MailQueryBuilder();
   builderDateRange.getInternalDate().beforeOrEqual(new Date());
   builderDateRange.getInternalDate().since(new Date(System.currentTimeMillis() - TimeUnit.DAYS.toMillis(1)));
   ```

### 按特定寄件者篩選訊息

**Overview:** 取得來自特定寄件者的電子郵件。

#### Implementation:
1. **Set Up the Query:**  
   ```java
   MailQueryBuilder builderSender = new MailQueryBuilder();
   builderSender.getFrom().contains("saqib.razzaq@127.0.0.1");
   ```

### 按特定網域篩選訊息

**Overview:** 取得來自特定網域的電子郵件。

#### Implementation:
1. **Domain‑Based Filtering:**  
   ```java
   MailQueryBuilder builderDomain = new MailQueryBuilder();
   builderDomain.getFrom().contains("SpecificHost.com");
   ```

### 按特定收件者篩選訊息

**Overview:** 取得寄送給特定收件者的電子郵件。

#### Implementation:
1. **Recipient Query Setup:**  
   ```java
   MailQueryBuilder builderRecipient = new MailQueryBuilder();
   builderRecipient.getTo().contains("recipient@example.com");
   ```

### 使用 AND 邏輯結合查詢

**Overview:** 使用邏輯 AND 運算結合多個條件。

#### Implementation:
1. **Setup Combined Conditions:**  
   ```java
   MailQueryBuilder builderAnd = new MailQueryBuilder();
   builderAnd.getFrom().contains("SpecificHost.com");
   builderAnd.getInternalDate().before(new Date());
   builderAnd.getInternalDate().since(new Date(System.currentTimeMillis() + TimeUnit.DAYS.toMillis(-7)));
   ```

### 使用 OR 邏輯結合查詢

**Overview:** 使用邏輯 OR 條件取得電子郵件。

#### Implementation:
1. **OR Condition Setup:**  
   ```java
   MailQueryBuilder builderOr = new MailQueryBuilder();
   builderOr.or(builderOr.getSubject().contains("test"), builderOr.getFrom().contains("noreply@host.com"));
   ```

### 按大小寫敏感度篩選訊息

**Overview:** 為電子郵件地址使用大小寫敏感的篩選。

#### Implementation:
1. **Case‑Sensitive Filtering:**  
   ```java
   MailQueryBuilder builderCaseSensitive = new MailQueryBuilder();
   builderCaseSensitive.getFrom().contains("tesT", true);
   ```

## 實務應用

- **Automated Email Sorting:** 自動依主旨或寄件者將電子郵件分類。  
- **Security Filters:** 依寄件者網域辨識並篩選潛在的網釣攻擊。  
- **Marketing Analysis:** 追蹤電子報與促銷郵件，以獲取行銷洞見。  
- **Time‑Based Archiving:** 依特定日期範圍封存電子郵件，以符合法規要求。

## 效能考量

優化效能在處理大量電子郵件資料時至關重要：

- 使用高效的查詢以減少資源消耗。  
- 若資料集龐大，請實作分頁以避免記憶體過載。  
- 定期分析與監控應用程式效能。

## 常見問題與解決方案

| 問題 | 典型原因 | 推薦解決方案 |
|------|----------|--------------|
| **ParseException** 在解析日期時發生 | 日期格式不正確 | 使用與輸入字串相符的 `SimpleDateFormat`，並務必以 try‑catch 包住。 |
| 沒有返回結果 | 篩選條件過於嚴格 | 放寬條件或確認信箱中確實有符合的訊息。 |
| 大小寫敏感未生效 | `contains` 未傳入 `true` 參數 | 在第二個參數傳入 `true` 以強制大小寫敏感匹配。 |
| 大型信箱查詢緩慢 | 缺少分頁機制 | 使用 `client.listMessages(..., pageSize, pageNumber)` 以分批取得結果。 |

## 常見問答

**Q1: 處理日期篩選時的 ParseException 最佳方式是什麼？**  
- **A:** 永遠以 try‑catch 包住 `sdf.parse()` 呼叫，以優雅地處理解析例外。

**Q2: 除了 Exchange，我可以在 Java 中使用 Aspose.Email 搭配其他郵件協議嗎？**  
- **A:** 可以，Aspose.Email 支援多種協議，包括 IMAP 與 POP3。詳情請參考文件。

**Q3: 如何在大型信箱中優化查詢效能？**  
- **A:** 盡可能縮小篩選條件範圍，並考慮使用分頁機制。

**Q4: 試用免費版後是否必須立即購買授權？**  
- **A:** 雖然免費試用適合評估，但購買授權可解除所有功能限制。

**Q5: 如何將 Aspose.Email 整合至其他 Java 應用程式？**  
- **A:** 直接將 Aspose.Email 作為函式庫加入您的 Java 專案，即可輕鬆整合。

**Q6: 可以結合超過兩個條件使用 AND/OR 邏輯嗎？**  
- **A:** 可以——在同一個 `MailQueryBuilder` 上鏈接更多條件，或依需求巢狀使用 OR 呼叫。

**Q7: 大小寫敏感的篩選是否也適用於主旨欄位？**  
- **A:** 完全支援。對任何欄位使用 `contains` 時，只要傳入 `true` 即可啟用大小寫敏感匹配。

**最後更新：** 2026-04-11  
**測試環境：** Aspose.Email for Java 25.4 (JDK 16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}