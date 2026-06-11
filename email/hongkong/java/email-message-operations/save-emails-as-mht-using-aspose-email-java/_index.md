---
date: '2026-03-02'
description: 學習如何使用 Maven Aspose.Email for Java 將電郵儲存為 MHT 檔案。本分步指南涵蓋設定、客製化範本以及電郵轉換為
  MHT。
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: Maven Aspose.Email for Java：將電郵儲存為 MHT 檔案
url: /zh-hant/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email for Java：如何將電郵儲存為 MHT 檔案

## 介紹

有效管理電郵資料可能相當具挑戰性，尤其在分享與歸檔時更是如此。在本指南中，我們將示範如何使用 **Maven Aspose.Email for Java** **儲存 MHT** 檔案，讓您能以自訂範本將電郵轉換為 MHT，並保留行事曆事件。完成後，您將擁有一個可直接執行的解決方案，適用於任何 Java 16 以上的環境。

## 快速解答
- **需要哪個函式庫？** Maven Aspose.Email for Java (v25.4+)。  
- **產生的格式為何？** MHT（MHTML）檔案，將 HTML、圖片與行事曆資料封裝在一起。  
- **可以自訂標頭嗎？** 可以 — 使用 `MhtFormatOptions` 及範本字串。  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買永久授權。  
- **需要哪個 Java 版本？** JDK 16 或更新版本。

## 什麼是 Maven Aspose.Email for Java？

Maven Aspose.Email for Java 是一套功能強大的 API，讓您能直接在 Java 程式碼中建立、讀取、轉換與操作電郵訊息。它支援多種格式，包括 MSG、EML 與 MHT，使其成為 **java email conversion** 任務的理想選擇。

## 為什麼要將電郵轉換為 MHT？

- **網頁友好**：MHT 檔案可在瀏覽器中直接呈現，無需外部資源。  
- **歸檔穩定性**：所有資源皆內嵌，保留原始外觀。  
- **行事曆支援**：可使用自訂範本呈現重複事件。  

## 前置條件

- **Aspose.Email for Java**（Maven 套件 `com.aspose:aspose-email:25.4`，帶有 `jdk16` classifier）。  
- **Maven** 已安裝並在您的機器上配置。  
- **JDK 16+**（此函式庫以 Java 16 為目標）。  
- 具備基本的 Java 知識（檔案處理、Maven 依賴）。

## 設定 Aspose.Email for Java

### Maven 依賴

在您的 `pom.xml` 檔案中加入以下依賴：

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 取得授權

Aspose 提供免費試用以探索其功能，亦提供購買授權或取得臨時授權的選項。

1. **免費試用**：從 [Releases](https://releases.aspose.com/email/java/) 下載，無限制探索功能。  
2. **臨時授權**：透過 [Temporary License Page](https://purchase.aspose.com/temporary-license/) 申請，即可取得完整功能版本。  
3. **購買**：若 Aspose.Email 符合您的長期專案需求，請考慮購買授權。

### 基本初始化

安裝完成後，在 Java 應用程式中初始化函式庫：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

完成上述步驟後，您即可使用 Aspose.Email 的功能來高效處理電郵。

## 實作指南

### 功能 1：載入 MailMessage

#### 概述

載入電郵訊息是處理並儲存為 MHT 檔案的第一步。本節示範如何使用 `MailMessage` 載入 `.msg` 檔案。

#### 步驟說明

**匯入必要的類別**

```java
import com.aspose.email.MailMessage;
```

**從檔案載入電郵**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

此程式碼片段會載入位於您指定目錄的電郵訊息。

### 功能 2：設定 MhtSaveOptions

#### 概述

設定 `MhtSaveOptions` 對於定義電郵如何儲存為 MHT 檔案至關重要，亦可自訂行事曆事件的格式。

#### 步驟說明

**匯入必要的類別**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**設定儲存選項與範本**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

此設定會在 MHT 輸出中設定標頭與行事曆事件的呈現。

### 功能 3：將 MailMessage 儲存為 MHT

#### 概述

最後一步是使用指定的選項，將已設定好的 `MailMessage` 儲存為 MHT 檔案。

#### 步驟說明

**匯入必要的類別**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**儲存電郵訊息**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

此指令會將電郵寫入 MHT 檔案，供分享或歸檔使用。

## 實務應用

- **電郵歸檔**：將重要電郵轉換並儲存為網頁友好格式。  
- **法律文件**：在需保留電郵細節的法律證據中使用 MHT 檔案。  
- **跨平台分享**：在不同平台間分享電郵，無相容性問題。

將其與其他系統（如 CRM 或專案管理工具）整合，可透過將關鍵電郵資料直接嵌入工作流程，提升協作效率。

## 效能考量

為確保最佳效能：

- 在處理大量電郵時，有效管理記憶體使用量。  
- 優化檔案 I/O 操作，以防止儲存過程中的瓶頸。

遵循 Java 記憶體管理的最佳實踐，可保持應用程式的回應性。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **`msg.save` 發生 NullPointerException** | 輸出路徑不正確 | 確認 `YOUR_OUTPUT_DIRECTORY` 存在且可寫入。 |
| **MHT 中缺少圖片** | `MhtFormatOptions` 未設定為嵌入資源 | 在選項旗標中加入 `MhtFormatOptions.EmbedResources`。 |
| **行事曆事件未呈現** | 未加入 `RenderCalendarEvent` 旗標 | 確保使用 `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## 常見問答

**Q：在將電郵儲存為 MHT 時，如何處理附件？**  
A：確保 `MhtSaveOptions` 已設定包含附件處理邏輯。此函式庫支援將附件嵌入 MHT 檔案。

**Q：可以自訂輸出 MHT 檔案中的電郵標頭嗎？**  
A：可以，使用 `MhtFormatOptions.WriteHeader`，並依照本教學示範為各標頭欄位定義自訂範本。

**Q：使用 Aspose.Email Java 的系統需求是什麼？**  
A：需要 JDK 16 或更高版本。此函式庫可與支援 Maven 專案的主流 IDE 無縫配合。

**Q：能否只儲存電郵訊息的特定部分？**  
A：雖然 MHT 格式通常會包含完整訊息，但您可利用 `MailMessage` 的屬性，選擇性處理與包含內容。

**Q：如何排除電郵載入或儲存時的問題？**  
A：檢查檔案路徑是否正確，確保專案中正確設定函式庫，並參考 Aspose.Email 的 [support forum](https://forum.aspose.com/c/email/10) 取得協助。

**Q：此函式庫是否支援將其他格式（EML、MSG）轉換為 MHT？**  
A：當然支援。`MailMessage.load` 可讀取 EML、MSG 及其他格式，之後可使用相同的選項將其儲存為 MHT。

## 資源

- **文件說明**：欲深入了解所有功能，請造訪 [Aspose Email Java Documentation](https://reference.aspose.com/email/java/)。  
- **下載**：從 [Releases](https://releases.aspose.com/email/java/) 下載，開始免費試用。  
- **購買**：於 [Official Purchase Page](https://purchase.aspose.com/buy) 探索長期使用的購買方案。  
- **免費試用與臨時授權**：透過以下連結取得完整功能的免費試用或臨時授權：  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

立即探索、實作，並以 Aspose.Email for Java 轉變您的電郵處理方式！

---

**最後更新：** 2026-03-02  
**測試環境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
