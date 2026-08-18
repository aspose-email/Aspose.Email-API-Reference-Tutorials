---
date: '2026-06-08'
description: 了解如何使用 Aspose.Email for Java 建立 PST 檔案，包括如何新增資料夾結構以及如何有效搜尋 PST 內容。一步一步的指南。
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: 使用 Aspose.Email for Java 建立 PST 檔案的方法
url: /zh-hant/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通使用 Aspose.Email for Java 進行電郵管理

如果您需要以程式方式 **how to create pst** 檔案，您來對地方了。在本教學中，我們將逐步說明如何產生 Unicode PST 檔案、加入標準 Outlook 資料夾、匯入訊息，並執行不區分大小寫的搜尋——全部使用 Aspose.Email for Java。完成後，您將擁有可重複使用的程式碼模式，能從少量電郵擴展至多吉位元組的封存。

## 快速解答
- **如何開始？** 添加 Aspose.Email Maven 相依性、取得授權，並實例化 `PersonalStorage`。
- **可以新增收件匣資料夾嗎？** 是 – 呼叫 `pst.getRootFolder().addSubFolder("Inbox")`。
- **支援不區分大小寫的搜尋嗎？** 使用 `PersonalStorageQueryBuilder` 並搭配 `StringComparison.OrdinalIgnoreCase`。
- **可處理的檔案大小為何？** Aspose.Email 可處理最高 2 GB 的 PST 檔案，且不會將整個檔案載入記憶體。
- **生產環境需要付費授權嗎？** 永久授權會移除試用限制，並解鎖全部效能功能。

## 什麼是 how to create pst？
**how to create pst** 指的是以程式方式產生 Outlook 個人儲存表格 (PST) 檔案，而非透過 Outlook 使用者介面。Aspose.Email for Java 提供完整管理的 API，能建立 Unicode PST 檔案、加入資料夾，並儲存 `MapiMessage` 物件，無需安裝 Outlook。

## 為何使用 Aspose.Email 來建立 PST？
Aspose.Email 支援 **50+** 種電郵相關格式（MSG、EML、MBOX、PST 等），且可處理 **最高 2 GB** 大小的 PST 檔案，同時因其延遲載入架構將記憶體使用量維持在 **150 MB** 以下。此可量化的能力使其非常適合企業級封存、遷移與合規情境。

## 前置條件

- **Java Development Kit (JDK)** – 版本 16 或更新。
- **Maven** – 用於相依性管理。
- 具備基本的 Java 語法知識；不需要先前的 PST 檔案經驗。

## 如何建立 PST 檔案？

`PersonalStorage` 類別代表 PST 檔案，提供建立、開啟與操作其內容的方法。若要建立新的 Unicode PST，請以目標檔案路徑與格式版本呼叫 `PersonalStorage.create()`。此操作會產生支援大型資料夾、Unicode 字元與高效串流的現代 PST，適用於小規模與企業級封存工作。

### 步驟 1：新增 Maven 相依性
將 Aspose.Email Maven 相依性加入您的 `pom.xml`。此舉會自動下載所有必要的二進位檔。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 步驟 2：取得並套用授權
提供免費試用版，但永久授權會移除評估限制，並啟用全速處理。

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## 如何向 PST 新增資料夾？

在 PST 根目錄下建立所需的資料夾層級，然後在插入訊息時參考它。`FolderInfo` 物件代表每個資料夾，且可任意巢狀，讓您能構建如收件匣、已傳送項目或自訂專案資料夾等結構。新增資料夾是一個輕量操作，不會載入訊息內容，即使在大型 PST 中亦能保持效能。

### 步驟 1：初始化 PersonalStorage
`PersonalStorage` 類別是 Aspose.Email 的頂層物件，代表記憶體中的單一 PST 檔案。實例化後，所有讀寫操作皆透過此物件執行。

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### 步驟 2：定義目錄路徑
設定電郵檔案的來源與目的路徑，以及 PST 輸出位置。

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### 步驟 3：建立 PST 檔案
使用 `PersonalStorage.create()` 並傳入 `FileFormatVersion.Unicode`，即可產生支援大型資料夾與 Unicode 字元的現代 Unicode PST。

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 如何搜尋 PST？

`PersonalStorageQueryBuilder` 是用於建構 PST 內容搜尋查詢的建構器類別。透過設定所需條件並指定 `StringComparison.OrdinalIgnoreCase`，您可以在不將整個 PST 載入記憶體的情況下，快速執行對主旨、內文與自訂屬性的不區分大小寫搜尋。

### 步驟 1：建構搜尋查詢
建立一個在主旨或內文中搜尋關鍵字且忽略大小寫的查詢。

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### 步驟 2：執行查詢並取得訊息
在目標資料夾上執行查詢，並遍歷返回的 `MapiMessage` 集合。

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 在 PST 中建立預定義資料夾

新增像 **Inbox** 這樣的預定義資料夾，可有效整理您的電郵資料。

### 步驟 1：初始化 PersonalStorage 物件
假設已如前所示建立 `PersonalStorage` 物件（`pst`）。

### 步驟 2：建立 'Inbox' 資料夾

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 向 PST 資料夾加入訊息

透過從檔案載入並轉換電郵訊息，將其填充至您的 PST 資料夾。

### 步驟 1：載入電郵訊息

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### 步驟 2：加入至 PST 資料夾
將 `MailMessage` 轉換為 `MapiMessage` 並加入：

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## 實務應用

Aspose.Email for Java 不僅僅是用來建立 PST 檔案，它是一個多功能工具，具備眾多應用場景：

- **Email Archiving**：自動將企業電郵封存至 PST 檔案，支援最長 10 年 的保留政策。
- **Migration Tools**：無縫從舊版郵件儲存（如 MBOX）遷移至 Outlook PST，只需對每封訊息呼叫一次 API。
- **Data Analysis**：提取寄件者、收件者與時間戳記等中繼資料，以供商業智慧管線使用。
- **Backup Solutions**：構建穩健的備份工具，儲存增量電郵變更，無需重新處理整個信箱。

## 效能考量

為確保使用 Aspose.Email 時的最佳效能，請注意以下事項：

- **Resource Management**：務必呼叫 `pst.dispose()` 或使用 try‑with‑resources 以即時釋放本機資源。
- **Batch Processing**：將電郵分批處理，每批 **500** 筆，以維持可預測的記憶體使用量。
- **Concurrency Handling**：此函式庫對唯讀操作為執行緒安全；寫入時需同步存取 `PersonalStorage` 實例。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|-------|-------|----------|
| **OutOfMemoryError** 處理大型 PST 時 | 將整個 PST 載入記憶體 | 啟用 `PersonalStorage.setUseUnicode(true)` 並以串流方式處理訊息。 |
| **Folder not found** 錯誤 | 資料夾路徑大小寫不正確 | 在查詢中使用 `StringComparison.OrdinalIgnoreCase` 或正規化資料夾名稱。 |
| **License not applied** | 在首次 API 呼叫前未載入授權檔案 | 在應用程式啟動時載入授權，於建立任何 `PersonalStorage` 物件之前。 |

## 常見問答

**Q: 需要的最低 Java 版本為何？**  
A: 建議使用 JDK 16 或更高版本，以確保與 Aspose.Email for Java 完全相容。

**Q: 可以在未取得授權的情況下使用 Aspose.Email 嗎？**  
A: 可以，提供試用模式，但會將 PST 大小限制為 **10 MB**，且會停用某些最佳化功能。

**Q: 如何有效處理大型 PST 檔案？**  
A: 將訊息分批處理，及時釋放 `MapiMessage` 物件，並透過 `PersonalStorage.setUseUnicode(true)` 啟用延遲載入。

**Q: 能否在 PST 檔案的電郵中加入附件？**  
A: 當然可以。將 `MailMessage` 轉換為 `MapiMessage` 時，呼叫 `mapiMsg.getAttachments().add(attachment)` 即可嵌入檔案。

**Q: 有哪些支援可協助排除問題？**  
A: Aspose 提供專屬支援論壇、詳細文件，以及對授權客戶的電子郵件支援。

## 資源
- [文件說明](https://reference.aspose.com/email/java/)
- [下載](https://releases.aspose.com/email/java/)
- [購買](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/email/java/)
- [臨時授權](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/email/10)

---

**最後更新：** 2026-06-08  
**測試環境：** Aspose.Email for Java 24.10  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Email for Java 建立與管理 Outlook PST 檔案](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [使用 Aspose.Email for Java 操作 PST 檔案：完整指南](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Java 提取電郵附件 - 使用 Aspose.Email 處理 PST 檔案 – 步驟指南](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}