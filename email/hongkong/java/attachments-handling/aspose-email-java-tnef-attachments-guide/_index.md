---
date: '2025-12-13'
description: 了解如何使用 Aspose.Email for Java 轉換 msg 與 eml、加入新附件、儲存電子郵件附件以及處理 TNEF 資料。
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: 使用 Aspose.Email Java 轉換 msg、eml – TNEF 附件指南
url: /zh-hant/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 精通 Aspose.Email Java：處理 TNEF 與電郵附件  

在現代以電郵為核心的應用程式中，您常常需要 **convert msg eml** 檔案、向現有訊息新增附件，並保留 TNEF 等特殊格式。無論您是建置歸檔服務、遷移工具，或是客戶端電郵檢視器，Aspose.Email for Java 都提供乾淨、程式化的方式來完成這些工作。在本教學中，您將會看到如何 **convert msg to eml**、新增附件、儲存電郵附件，以及使用 Aspose.Email Java 函式庫處理 TNEF 資料。

## 快速答覆
- **如何將 MSG 轉換為 EML？** 使用 `MapiMessage` 搭配 `MailConversionOptions`，並將 `convertAsTnef` 設為 `true`。  
- **可以向已啟用 TNEF 的 EML 加入附件嗎？** 可以 – 載入 EML 後，呼叫 `getAttachments().addItem(...)`，再儲存。  
- **需要哪個版本的 Aspose.Email？** 範例使用 25.4 版（JDK 16）。  
- **正式環境需要授權嗎？** 需要 – 試用版可用於評估，但正式授權可移除限制。  
- **有沒有方法偵測現有訊息是否含 TNEF？** 載入 EML 後呼叫 `mail.getOriginalIsTnef()`。

## 什麼是 “convert msg eml”？
將 Microsoft Outlook MSG 檔案轉換為標準的 EML 格式，可讓任何符合 RFC‑822 標準的電郵客戶端讀取該訊息。此轉換同時讓您在過程中保留或操作 TNEF 編碼的資料。

## 為什麼使用 Aspose.Email Java 來完成此任務？
- **完整格式支援** – MSG、EML、MHTML 等。  
- **內建 TNEF 處理** – 無需第三方解析器。  
- **簡易 API** – 只需一行程式碼即可載入、轉換與儲存。  
- **彈性授權** – 試用版供測試，正式授權供生產使用。

## 前置條件
- **Aspose.Email for Java**（v25.4，JDK 16）– 請參考下方 Maven 相依性。  
- **Maven** 或其他能解析 Aspose 套件的建置工具。  
- 基本的 Java I/O 與例外處理知識。  

## 設定 Aspose.Email for Java
將函式庫加入 Maven `pom.xml`：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權
Aspose.Email 提供免費試用，但正式使用需購買授權。

- **免費試用：** 下載臨時授權 [此處](https://releases.aspose.com/email/java/)。  
- **購買授權：** 前往 [購買頁面](https://purchase.aspose.com/buy)。

在 Java 程式碼中初始化授權：

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## 實作指南

### 為含 TNEF 的主要訊息新增附件
**新增附件方式：** 載入 EML、加入檔案，最後儲存。

#### 步驟 1：載入現有電郵訊息
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### 步驟 2：加入新附件
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### 步驟 3：儲存已修改的電郵訊息
```java
eml.save(dataDir + "test_out.eml");
```
*小技巧：* 使用 try‑with‑resources 確保串流關閉，避免 `FileNotFoundException`。

### 從 MSG 建立啟用 TNEF 的 EML
**轉換方式：** 設定 `convertAsTnef` 為 `true`。

#### 步驟 1：載入 MSG 檔案
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### 步驟 2：設定轉換選項
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### 步驟 3：執行轉換並儲存
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### 載入 EML 時保留 TNEF 附件
**保存電郵附件同時保留 TNEF：** 使用 `MsgLoadOptions`。

#### 步驟 1：設定載入選項
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### 步驟 2：以選項載入 EML 檔案
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### 偵測訊息是否為 TNEF
**檢查 TNEF 存在方式：** 呼叫 `getOriginalIsTnef()`。

#### 步驟 1：載入 EML 檔案
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### 步驟 2：偵測 TNEF 存在性
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## 實務應用
1. **電郵歸檔：** 保留所有附件——包括 TNEF 編碼的附件，以符合合規稽核。  
2. **企業遷移：** 將舊有 MSG 檔案轉換為 EML，方便匯入現代郵件伺服器。  
3. **客戶支援：** 當使用者在 Outlook 與 Web‑mail 之間轉寄訊息時，自動偵測 TNEF 資料。

## 效能考量
- **資源管理：** 使用 try‑with‑resources 包裝檔案串流，及時釋放資源。  
- **大型附件：** 以分段或串流方式處理大檔案，避免記憶體占用過高。  
- **監控：** 使用 Java 效能分析工具觀察大量附件處理時的堆積使用情形。

## 結論
依循上述步驟，您即可 **convert msg eml**、新增附件、保存電郵附件，並可靠地使用 Aspose.Email for Java 處理 TNEF 資料。此函式庫抽象化了底層 MIME 處理，讓您專注於業務邏輯。欲深入了解，請參考官方 [Aspose 文件](https://reference.aspose.com/email/java/) 或嘗試其他轉換選項。

## FAQ 區段
**Q1：什麼是 TNEF 檔案？**  
A1：TNEF 代表 Transport Neutral Encapsulation Format，是 Microsoft Outlook 用來在以附件形式傳送電郵時保留 Rich‑Text 格式的機制。

**Q2：我可以在不購買授權的情況下使用 Aspose.Email 嗎？**  
A2：可以，您可以先使用免費試用版。但試用版會有一些限制，可能影響大規模使用。

**Q3：Aspose.Email 能否在所有電郵格式之間相互轉換？**  
A3：Aspose.Email 支援大多數常見格式的相互轉換——包括 EML、MSG、MHTML 等，請於[文件](https://reference.aspose.com/email/java/) 中確認特定格式支援情形。

**Q4：如何排除 Aspose.Email 的檔案找不到錯誤？**  
A4：請再次確認傳入 API 的檔案路徑正確、檔案確實存在，且執行程序對該目錄具有讀寫權限。

**Q5：處理大型附件的最佳方式是什麼？**  
A5：將附件以較小的串流或分段方式處理，並確保及時關閉串流。這可減少記憶體壓力，避免 `OutOfMemoryError`。

## 常見問題（補充）

**Q：Aspose.Email 在轉換為 EML 時會自動去除 TNEF 嗎？**  
A：不會。預設會保留 TNEF 資料。您可透過 `MailConversionOptions.setConvertAsTnef` 來控制此行為。

**Q：我可以程式化列出已載入訊息的所有附件嗎？**  
A：可以——使用 `mail.getAttachments()` 取得集合，然後遍歷即可。

**Q：是否能一次批次轉換多個 MSG 檔案為 EML？**  
A：絕對可以。遍歷檔案清單，套用上述轉換步驟，逐一儲存結果。

---

**最後更新：** 2025-12-13  
**測試環境：** Aspose.Email for Java 25.4（JDK 16）  
**作者：** Aspose  
**相關資源：** [Aspose Email Java 文件](https://reference.aspose.com/email/java/) | [Aspose Email Java 版本發布](https://releases.aspose.com/email/java/) | [購買 Aspose.Email for Java](https://purchase.aspose.com/buy) | 下載臨時授權 [此處](https://releases.aspose.com/email/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}