---
date: '2026-06-18'
description: 了解如何使用 Aspose.Email for Java 從 Zimbra TGZ 檔案中提取電子郵件。內容包括 Maven 相依性、Aspose
  Email 設定以及實作範例。
keywords:
- how to use aspose.email
- maven dependency aspose email
- extract emails from zimbra tgz
schemas:
- author: Aspose
  dateModified: '2026-06-18'
  description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  headline: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  type: TechArticle
- description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  name: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  steps:
  - name: Define File Path
    text: Specify the absolute or relative path to the TGZ file you want to process.
  - name: Initialize TgzReader
    text: Create a `TgzReader` instance using the file path. *Direct answer:* Initializing
      `TgzReader` opens the archive and prepares it for sequential message extraction.
  - name: Extract Emails
    text: Iterate through each stored message, retrieve its folder location, and obtain
      a `MailMessage` object. - `readNextMessage()` returns `false` when no more messages
      remain. - `getCurrentDirectory()` shows the internal folder path inside the
      TGZ. - `getCurrentMessage()` gives you a fully parsed `MailMes
  type: HowTo
- questions:
  - answer: JDK 16+, Maven, and the `com.aspose:aspose-email` Maven artifact.
    question: What are the prerequisites for using Aspose.Email for Java?
  - answer: Purchase a license or request a temporary one via the [Aspose purchase
      page](https://purchase.aspose.com/buy).
    question: How can I obtain a license for production use?
  - answer: Verify the file exists, the path is correctly escaped for Java strings,
      and the process has read permissions.
    question: My TGZ path seems invalid—what should I check?
  - answer: Yes, the API is thread‑safe; you can instantiate separate `TgzReader`
      objects per thread.
    question: Does Aspose.Email support multi‑threaded extraction?
  - answer: Save each `MailMessage` as EML, JSON, or XML using `SaveOptions`, then
      feed the files into your downstream pipelines.
    question: How do I integrate extracted emails with other systems?
  type: FAQPage
title: 如何使用 Aspose.Email for Java：從 Zimbra TGZ 檔案中提取電子郵件
url: /zh-hant/java/email-parsing-analysis/extract-emails-zimbra-tgz-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-container >}}

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for Java：從 Zimbra TGZ 檔案中提取電子郵件

## 簡介

## 快速答案
- **什麼程式庫可提取 Zimbra TGZ 電子郵件？** Aspose.Email for Java.
- **需要哪個 Maven 套件？** `com.aspose:aspose-email`.
- **最低 Java 版本？** JDK 16 或更新版本。
- **能處理大型檔案嗎？** 可以，批次處理可保持低記憶體使用。
- **生產環境是否需要授權？** 需要，完整或臨時的 Aspose.Email 授權皆可。

## 先決條件

- **Java 開發工具包 (JDK)** 16 或以上。
- **Maven** 用於相依性管理。
- **Aspose.Email for Java** v25.4（或更新）— 我們接下來會加入 Maven 相依性。
- 取得您想要解析的 Zimbra TGZ 檔案。

## 如何加入 Aspose.Email 的 Maven 相依性？

若要在 Maven 專案中加入 Aspose.Email，請將相依性程式碼片段加入 `pom.xml` 的 `<dependencies>` 區段。Maven 會解析套件、下載所需的 JAR，並將程式庫加入您的 classpath，讓您能立即開始編寫程式碼，無需手動處理 JAR。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
</dependency>
```

*直接答案：* 加入上述相依性會自動下載程式庫，讓您無需手動處理 JAR 即可開始編寫程式碼。

## 取得授權

Aspose 提供三種授權方式：

- **免費試用** – 用於評估的臨時授權。
- **臨時授權** – 短期使用，無評估限制。
- **完整購買** – 無限制的生產環境使用。

前往 [Aspose 購買頁面](https://purchase.aspose.com/buy) 了解詳情。

## 基本初始化

要開始使用 Aspose.Email，請匯入所需類別並建立基本設定區塊。

```java
import com.aspose.email.*;
```

*直接答案：* 加入匯入後，您即可在 Java 程式碼中直接實例化 Aspose.Email 物件。

## 實作指南

### 什麼是 TgzReader 類別，它如何運作？

`TgzReader` 類別是 Aspose.Email 的串流 API，用於在不將整個檔案載入記憶體的情況下讀取 Zimbra TGZ 儲存檔案。

#### 步驟 1：定義檔案路徑

指定您要處理的 TGZ 檔案的絕對或相對路徑。

```java
String tgzPath = "C:/archives/zimbra_backup.tgz";
```

#### 步驟 2：初始化 TgzReader

使用檔案路徑建立 `TgzReader` 實例。

```java
TgzReader tgzReader = new TgzReader(tgzPath);
```

*直接答案：* 初始化 `TgzReader` 會開啟檔案並為順序提取訊息做好準備。

#### 步驟 3：提取電子郵件

遍歷每封儲存的訊息，取得其資料夾位置，並獲得 `MailMessage` 物件。

```java
while (tgzReader.readNextMessage()) {
    String directory = tgzReader.getCurrentDirectory();
    MailMessage message = tgzReader.getCurrentMessage();
    // Process the MailMessage (save, analyze, etc.)
}
tgzReader.dispose();
```

- `readNextMessage()` 在沒有更多訊息時返回 `false`。
- `getCurrentDirectory()` 顯示 TGZ 內部的資料夾路徑。
- `getCurrentMessage()` 提供完整解析的 `MailMessage`。

*直接答案：* 上述迴圈會提取檔案中的每封電子郵件，讓您能個別處理每則訊息。

### 如何使用 Aspose.Email 工具簡化目錄處理？

Aspose.Email 提供協助方法，可動態建立檔案系統路徑。以下是一個簡潔的工具方法，您可將其放入任何類別中使用。

```java
public static String buildOutputPath(String base, String folder, String fileName) {
    return Paths.get(base, folder, fileName).toString();
}
```

*直接答案：* 使用 `buildOutputPath` 產生一致的儲存電子郵件檔案的輸出位置。

#### 使用工具函式

將此工具與提取迴圈結合，將每封電子郵件儲存為 EML 檔案。

```java
String outputBase = "C:/extracted_emails";
while (tgzReader.readNextMessage()) {
    String dir = tgzReader.getCurrentDirectory();
    MailMessage msg = tgzReader.getCurrentMessage();
    String outPath = buildOutputPath(outputBase, dir, msg.getSubject() + ".eml");
    msg.save(outPath, SaveOptions.getDefaultEml());
}
```

*直接答案：* 此程式碼會將每則訊息儲存至與 TGZ 檔案內原始位置相同的資料夾中。

## 為何使用 Aspose.Email 進行 Zimbra TGZ 提取？

Aspose.Email 提供完整且高效能的解決方案，用於從 Zimbra TGZ 檔案中提取電子郵件。它支援串流以降低記憶體使用，能處理超過 1 GB 的大型檔案，且提供執行緒安全的 API，適合需要可靠性與速度的大規模備份、遷移或鑑識專案。

- **50+ 輸入格式** – Aspose.Email 可讀取 EML、MSG、MBOX、PST、以及 Zimbra TGZ 等多種格式。
- **支援 1 GB 以上的檔案** – 使用串流處理多 GB 的 TGZ 檔案，將記憶體使用維持在 200 MB 以下。
- **零外部相依性** – 無需 Zimbra 伺服器函式庫或原生工具。
- **執行緒安全 API** – 您可平行執行多個 `TgzReader` 實例以進行批次作業。

上述具體優勢使 Aspose.Email 成為大規模電子郵件封存專案的生產就緒選擇。

## 效能考量

處理極大型 TGZ 檔案時，請遵循以下最佳實踐：

- **及時釋放** – 完成後立即呼叫 `tgzReader.dispose()` 釋放原生資源。
- **批次處理** – 將訊息分組處理（例如每次 500 封），並在繼續前將結果寫入磁碟。
- **避免載入完整內容** – 使用串流 API（`readNextMessage`）而非將整個檔案載入記憶體。

遵循這些指導方針可保持 CPU 與記憶體佔用低，即使在一般伺服器上亦是如此。

## 實務應用

從 Zimbra TGZ 檔案中提取電子郵件可用於：

- **備份與復原** – 從已封存的 TGZ 檔案重建郵箱。
- **資料遷移** – 將舊版 Zimbra 資料遷移至 Exchange、Office 365 或自訂儲存。
- **鑑識分析** – 在不還原整個 Zimbra 實例的情況下檢視歷史通信。

## 常見問題

**問：使用 Aspose.Email for Java 的先決條件是什麼？**  
**答：** JDK 16+、Maven，以及 `com.aspose:aspose-email` Maven 套件。

**問：如何取得生產環境的授權？**  
**答：** 購買授權或透過 [Aspose 購買頁面](https://purchase.aspose.com/buy) 申請臨時授權。

**問：我的 TGZ 路徑似乎無效——應該檢查什麼？**  
**答：** 確認檔案存在、路徑在 Java 字串中正確轉義，且程式具有讀取權限。

**問：Aspose.Email 支援多執行緒提取嗎？**  
**答：** 支援，API 為執行緒安全；您可為每個執行緒實例化獨立的 `TgzReader` 物件。

**問：如何將提取的電子郵件整合至其他系統？**  
**答：** 使用 `SaveOptions` 將每個 `MailMessage` 儲存為 EML、JSON 或 XML，然後將檔案輸入至後續管線。

## 資源
- **文件說明**： [Aspose.Email for Java 文件說明](https://reference.aspose.com/email/java/)
- **下載**： [Aspose Email 版本發佈](https://releases.aspose.com/email/java/)
- **購買**： [購買 Aspose 產品](https://purchase.aspose.com/buy)
- **免費試用**： [Aspose Email 免費試用](https://releases.aspose.com/email/java/)
- **臨時授權**： [取得臨時授權](https://purchase.aspose.com/temporary-license/)
- **支援**： 如有問題或需要協助，請前往 [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

**最後更新：** 2026-06-18  
**測試環境：** Aspose.Email for Java 25.4  
**作者：** Aspose

## 相關教學

- [Aspose.Email Java 電子郵件解析與分析教學](/email/java/email-parsing-analysis/)
- [使用 Aspose.Email for Java 提取電子郵件附件](/email/java/advanced-email-attachments/)
- [使用 Aspose.Email for Java 高效載入與顯示 EML 電子郵件](/email/java/email-message-operations/load-display-eml-emails-aspose-java/)

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/pf/main-wrap-class >}}

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```java
import com.aspose.email.TgzReader;
import com.aspose.email.MailMessage;
```

```java
String storagePath = "YOUR_DOCUMENT_DIRECTORY/ZimbraSample.tgz";
```

```java
TgzReader reader = new TgzReader(storagePath);
```

```java
try {
    while (reader.readNextMessage()) { // Continue until all messages are read.
        String directoryName = reader.getCurrentDirectory(); // Get the current email's storage path.
        MailMessage eml = reader.getCurrentMessage(); // Retrieve the current email message.

        // At this point, 'directoryName' and 'eml' hold crucial details of each email.
    }
} finally {
    reader.dispose(); // Always dispose of resources to prevent memory leaks.
}
```

```java
import com.aspose.email.examples.Utils;

public class ExampleUtils {
    public static String getSharedDataDir(Class<?> cls) {
        return "YOUR_DOCUMENT_DIRECTORY/"; // Set your shared data directory path.
    }
}
```

```java
String dataDir = ExampleUtils.getSharedDataDir(ExampleUtils.class) + "email/";
// 'dataDir' now points to a specific subdirectory for email-related operations.
```