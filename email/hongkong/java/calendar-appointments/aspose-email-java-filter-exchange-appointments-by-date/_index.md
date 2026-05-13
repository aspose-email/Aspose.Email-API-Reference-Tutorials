---
date: '2026-02-17'
description: 學習如何加入 Aspose.Email Maven 相依性，並建立 Exchange 查詢 Java 程式，以依日期篩選 Exchange
  Server 約會。本 Aspose Email Java 教學涵蓋環境設定、取得 Exchange 行事曆事件以及最佳實踐。
keywords:
- filter Exchange server appointments
- Aspose.Email for Java setup
- Exchange Web Services (EWS) appointments
title: Aspose Email Maven 依賴 – 建構 Exchange 查詢 Java 用於篩選約會
url: /zh-hant/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/
weight: 1
---

". Translate.

Also keep URLs unchanged.

Also keep code block placeholders unchanged.

Now produce final output.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Email Maven 依賴 – 建構 Exchange Query Java 以篩選約會

有效的約會管理在當今商業環境中至關重要，效率高的排程能提升組織生產力。透過 **加入 Aspose.Email Maven 依賴** 並 **建構 exchange query Java**，根據特定日期範圍從 Exchange 伺服器篩選約會，即可簡化作業並改善時間管理。本教學將帶您完整走過從環境設定到執行查詢的每一步，並示範如何 **可靠地取得 exchange 行事曆事件**。

**您將學會**
- 使用所需的 Maven 依賴設定環境  
- 初始化與設定 Aspose.Email for Java  
- 建構 exchange query Java 以在特定日期範圍內篩選約會  
- 優化效能與記憶體使用的最佳實踐  

了解此解決方案所針對的問題後，讓我們先看看在實作前需要的前置條件。

## 快速回答
- **「build exchange query java」是什麼意思？** 指在 Java 中建立 `ExchangeQueryBuilder` 物件以查詢 Exchange 項目。  
- **需要哪個函式庫？** Aspose.Email for Java（v25.4 以上）。  
- **需要 Exchange 伺服器嗎？** 需要，且必須啟用 EWS 並提供正確的憑證。  
- **可以在執行時變更日期範圍嗎？** 當然可以，只要修改 `SimpleDateFormat` 的字串即可。  
- **正式環境需要授權嗎？** 必須，商業使用需具備有效的 Aspose.Email 授權。

## 前置條件

要跟隨本教學，請確保您具備以下工具與知識：

### 必要的函式庫與相依性
- **Aspose.Email for Java**：版本 25.4 或更新。  
- **Java Development Kit (JDK)**：使用 JDK 16 或更新版本。

### 環境設定需求
- 已設定好的 IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。  
- 可存取已啟用 EWS 的 Exchange 伺服器。

### 知識前提
- 基本的 Java 程式設計概念。  
- 熟悉 Maven 以管理相依性。

## 新增 Aspose.Email Maven 依賴

首先，將 Aspose.Email 函式庫加入專案相依性。若使用 Maven，請在 `pom.xml` 中加入以下 XML 片段：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 授權取得

Aspose.Email for Java 提供免費試用以評估功能。持續使用時，建議取得臨時授權或購買正式版：
- **免費試用**：可於 [Aspose Email Download](https://releases.aspose.com/email/java/) 頁面取得。  
- **臨時授權**：請前往 [Temporary License Page](https://purchase.aspose.com/temporary-license/) 申請。  
- **購買**：長期使用請至 [Purchase Aspose](https://purchase.aspose.com/buy) 購買授權。

### 基本初始化與設定

設定 Exchange 伺服器憑證以初始化 Aspose.Email for Java。如下建立 `IEWSClient`：

```java
String mailboxUri = "YOUR_EXCHANGE_SERVER_URI"; // Your Exchange Server URI
String username = "YOUR_USERNAME";               // Username for authentication
String password = "YOUR_PASSWORD";               // Password
String domain = "YOUR_DOMAIN";                   // Domain if required

IEWSClient client = EWSClient.getEWSClient(mailboxUri, username, password, domain);
```

此程式碼使用 Aspose.Email 函式庫與您的 Exchange 伺服器建立連線。

## 什麼是「build exchange query java」？

**build exchange query java** 這個詞彙描述的是建立 `ExchangeQueryBuilder` 實例、設定其條件（如日期範圍、主旨或組織者），再對 Exchange 信箱執行查詢的過程。此建構器將複雜的 SOAP 請求封裝於流暢的 Java API 中，讓您能輕鬆 **取得 exchange 行事曆事件**，無需自行撰寫 XML。

## 為何使用 Aspose.Email for Java？

- **完整的 EWS 支援** – 可處理約會、聯絡人、工作項目等。  
- **不需 Outlook** – 直接與 Exchange 伺服器互動。  
- **高效能** – 網路使用與記憶體管理皆優化。  
- **豐富文件** – 大量範例協助快速上手，是優秀的 **aspose email java tutorial**。

## 依日期篩選約會（Exchange Query 日期範圍）

本教學的核心功能是依特定日期範圍篩選約會。以下說明如何實作：

### 步驟 1：設定日期格式

先建立 `SimpleDateFormat` 物件，以將日期字串解析為 Java `Date` 物件。

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;

SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
```

此格式將用於解讀約會的開始與結束日期。

### 步驟 2：使用 ExchangeQueryBuilder 建構查詢

建立 `ExchangeQueryBuilder` 實例，並設定日期範圍條件：

```java
import com.aspose.email.ExchangeQueryBuilder;

ExchangeQueryBuilder builder = new ExchangeQueryBuilder();

// Specify the start date for filtering appointments
builder.getAppointment().getStart().since(sdf.parse("10/05/2016 10:00:00"));

// Define the end date to include all appointments before or equal to this time
builder.getAppointment().getEnd().beforeOrEqual(sdf.parse("10/15/2016 10:00:00"));
```

### 步驟 3：執行查詢

使用先前的 `IEWSClient` 物件執行查詢並取得約會：

```java
import com.aspose.email.MailQuery;

com.aspose.email.MailQuery query = builder.getQuery();
Appointment[] appointments = client.listAppointments(query);
```

此程式碼會抓取所有落在指定日期範圍內的約會。

### 疑難排解小技巧
- **日期解析錯誤**：請確認日期字串符合 `SimpleDateFormat` 定義的模式。  
- **驗證問題**：再次檢查 Exchange 伺服器憑證與網路連線。  
- **結果為空**：確認伺服器在給定範圍內確實有約會資料。

## 實務應用

此功能可應用於多種真實情境：
1. **企業行事曆管理** – 自動篩選特定月份的會議。  
2. **資源排程** – 透過排除過往預訂，找出空閒時段。  
3. **報表與分析** – 依期間產生約會資料報表。

## 效能考量

使用 Aspose.Email 時，請留意以下建議以維持效能：
- 限制查詢範圍以減少資料傳輸。  
- 重複使用單一 `SimpleDateFormat` 實例，避免頻繁建立。  
- 釋放不再使用的物件，以減少 Java 堆積記憶體佔用。

## 常見問題與解決方案
| 問題 | 可能原因 | 解決方式 |
|------|----------|----------|
| **DateParseException** | 字串與格式不符 | 調整 `SimpleDateFormat` 的模式或修正輸入字串。 |
| **401 Unauthorized** | 憑證錯誤或缺少 EWS 權限 | 確認使用者名稱/密碼，並確保帳號具備 EWS 存取權限。 |
| **未返回約會** | 查詢日期超出現有範圍 | 檢查伺服器行事曆是否有約會，或擴大日期窗口。 |

## 結論

使用 Aspose.Email for Java 依日期篩選 Exchange 伺服器的約會，可簡化行事曆管理、提升生產力，並提供排程模式的寶貴洞見。透過本 **aspose email java tutorial**，您已學會如何設定環境、配置函式庫，並 **build exchange query java** 以依特定條件篩選約會。

**後續步驟**
- 探索其他查詢選項，如主旨或組織者過濾。  
- 將取得的約會整合至自訂報表儀表板。  
- 了解 Aspose.Email 其他功能，例如發送會議請求或處理重複事件。

## 常見問答

**Q:** 可以在不購買的情況下使用 Aspose.Email 嗎？  
**A:** 可以，您可先使用免費試用版評估功能，再決定是否購買。

**Q:** 連線 Exchange 伺服器時發生驗證錯誤，該怎麼處理？  
**A:** 請再次確認憑證與網路設定，確保該帳號已啟用 EWS 存取。

**Q:** 本教學支援哪些日期格式？  
**A:** `SimpleDateFormat` 支援您自行定義的任何模式；範例使用 `"dd/MM/yyyy HH:mm:ss"`。

**Q:** 如何在執行時動態變更日期範圍？  
**A:** 只要在建構查詢前修改傳入 `since()` 與 `beforeOrEqual()` 方法的字串即可。

**Q:** 哪裡可以找到更多 Aspose.Email 功能文件？  
**A:** 完整文件可於 [Aspose Email Documentation](https://reference.aspose.com/email/java/) 取得。

## 資源
- **文件**： [Aspose Email Java Docs](https://reference.aspose.com/email/java/)  
- **下載**： [Aspose Email Releases](https://releases.aspose.com/email/java/)  
- **購買**： [Buy Aspose](https://purchase.aspose.com/buy)  
- **免費試用**： [Get a Free Trial](https://releases.aspose.com/email/java/)  
- **臨時授權**： [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **支援**： [Aspose Forum Support](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-02-17  
**測試環境：** Aspose.Email for Java 25.4 (jdk16)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}