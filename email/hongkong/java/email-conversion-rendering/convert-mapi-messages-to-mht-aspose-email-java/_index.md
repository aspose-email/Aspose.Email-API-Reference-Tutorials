---
date: '2026-01-17'
description: 學習如何使用 Aspose.Email for Java 將 MSG 轉換為 MHT。此逐步教學涵蓋載入、儲存及自訂範本，以應對實務電子郵件轉換需求。
keywords:
- convert MAPI messages
- Aspose.Email for Java
- MHT format conversion
title: 如何使用 Aspose.Email for Java 將 MSG 轉換為 MHT：完整指南
url: /zh-hant/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 將 MSG 轉換為 MHT：完整指南

## 介紹

將 **MSG 轉換為 MHT** 是在需要將 Outlook 訊息存檔或以網頁友善格式顯示時的常見需求。在本教學中，您將看到 Aspose.Email for Java 如何簡化轉換流程，讓您載入 MAPI（MSG）檔案、使用自訂 HTML 範本調整輸出，並將其儲存為可供瀏覽器或存檔系統使用的 MHT 檔案。

**您將學習到：**
- 如何高效載入與解析 MSG 檔案。  
- 如何設定 `MhtSaveOptions` 以獲得最佳的 MHT 輸出。  
- 如何套用自訂範本以提升可讀性。  
- 真實情境中將 MSG 轉換為 MHT 所帶來的價值。

讓我們先準備環境，然後深入程式碼。

## 快速解答
- **「將 MSG 轉換為 MHT」是什麼意思？** 它將 Outlook `.msg` 檔案轉換為網頁相容的 `.mht`（MHTML）格式。  
- **使用哪個函式庫？** Aspose.Email for Java（aspose email tutorial）。  
- **需要授權嗎？** 免費 30 天試用可用於評估；正式環境需購買授權。  
- **支援的 Java 版本？** Java 16 或更新版本（classifier `jdk16`）。  
- **典型使用情境？** 為合規存檔或在未安裝 Outlook 的瀏覽器中顯示電子郵件。

## 什麼是「將 MSG 轉換為 MHT」？
轉換過程會讀取二進位的 Outlook 訊息（`.msg`），並將其內容、附件與中繼資料重新寫入單一的基於 HTML 的 MHTML 檔案（`.mht`）。此單檔格式保留原始版面配置，且可在任何現代瀏覽器中檢視。

## 為何使用 Aspose.Email for Java？
- **功能完整的 API：** 處理所有 MAPI 屬性、附件與嵌入物件。  
- **無需 Outlook 依賴：** 可在任何伺服器端 Java 環境執行。  
- **可自訂範本：** 調整 HTML 輸出以符合品牌或報告標準。  
- **高效能：** 為大量批次與非同步處理進行最佳化。

## 前置條件
- **Aspose.Email 函式庫：** 版本 25.4 或更新（classifier `jdk16`）。  
- **Java 開發環境：** 已安裝 Maven 以管理相依性。  
- **基本的 Java 知識：** 熟悉檔案 I/O 與 Maven 專案。

## 設定 Aspose.Email for Java

要將 Aspose.Email 加入 Maven 專案，請加入以下相依性：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權（aspose email tutorial）

Aspose.Email 為商業產品，但您可以先使用 **免費試用**：

- **免費試用：** 完整功能 30 天。  
- **臨時授權：** 如有需要可延長評估。  
- **購買：** 取得永久授權以供正式使用。

### 基本初始化

加入 Maven 相依性後，於 Java 程式碼中初始化函式庫：

```java
// Import necessary classes
import com.aspose.email.License;

public class Main {
    public static void main(String[] args) {
        // Apply license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not applied: " + e.getMessage());
        }
    }
}
```

## 使用 Aspose.Email for Java 將 MSG 轉換為 MHT 的方法

### 載入 MSG 檔案

**步驟 1 – 匯入所需類別**

```java
import com.aspose.email.MapiMessage;
```

**步驟 2 – 從磁碟載入訊息**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ensure this path is correct
MapiMessage msg = MapiMessage.fromFile(dataDir + "MapiTask.msg");
```

`MapiMessage.fromFile()` 方法會讀取 `.msg` 檔案，並建立可操作的 `MapiMessage` 物件。

### 設定 MHT 儲存選項

**步驟 1 – 匯入儲存選項類別**

```java
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.SaveOptions;
```

**步驟 2 – 設定選項**

```java
MhtSaveOptions opt = SaveOptions.getDefaultMhtml();
opt.setMhtFormatOptions(MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader);
```

`RenderTaskFields` 確保包含任務專屬欄位，而 `WriteHeader` 會將標準電子郵件標頭加入 MHT 輸出。

### 定義自訂 HTML 範本（可選）

**步驟 1 – 匯入範本列舉**

```java
import com.aspose.email.MhtTemplateName;
```

**步驟 2 – 自訂範本**

```java
opt.getFormatTemplates().clear();
opt.getFormatTemplates().add(MhtTemplateName.Task.SUBJECT, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.ACTUAL_WORK, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.TOTAL_WORK, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.STATUS, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.OWNER, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.getFormatTemplates().add(MhtTemplateName.Task.PRIORITY, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

這些範本讓您控制每個任務屬性在最終 MHT 檔案中的呈現方式，提升最終使用者的可讀性。

### 將訊息儲存為 MHT 檔案

**步驟 1 – 定義輸出目錄**

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY"; // Ensure this path is correct
```

**步驟 2 – 執行儲存操作**

```java
msg.save(outputDir + "MapiTask_out.mht", opt);
```

`save` 方法會將自訂的 MHT 檔案寫入磁碟。執行程式前請確認 `outputDir` 路徑是否正確。

## 實務應用（為何將 MSG 轉換為 MHT？）

- **存檔：** 以單一可攜式格式儲存電子郵件，瀏覽器即可呈現，無需 Outlook。  
- **遷移：** 將舊有 Outlook 檔案庫搬移至基於 Web 的電子郵件平台。  
- **報告與分析：** 使用 HTML 解析器解析 MHT 檔案，以進行資料抽取與商業智慧分析。  
- **法律合規：** 以防篡改的格式保留原始訊息內容與中繼資料。

## 效能考量

- **批次處理：** 處理數千個 MSG 檔案時，分批執行以避免記憶體激增。  
- **非同步執行：** 利用 Java 的 `CompletableFuture` 或執行服務平行轉換檔案。  
- **資源清理：** 若開啟自訂串流（超出 Aspose API），請明確關閉。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|---------|---------------|-----|
| **NullPointerException on `msg.save`** | 輸出目錄不存在 | 建立目錄或使用 `Files.createDirectories(Paths.get(outputDir));` |
| **Missing attachments in MHT** | 未將 `MhtSaveOptions` 設定為嵌入資源 | 使用 `opt.setMhtFormatOptions(opt.getMhtFormatOptions() \| MhtFormatOptions.WriteResources);` |
| **Incorrect date format** | 語系設定不同 | 調整 `opt.setDateFormat("yyyy-MM-dd HH:mm:ss");` |

## 常見問答

**Q: MSG 與 MHT 有何不同？**  
A: MSG 是 Outlook 的專有二進位格式，用於儲存電子郵件、附件與中繼資料。MHT（MHTML）是基於 HTML 的單一檔案格式，將郵件正文、圖片與 CSS 打包，使其可在任何瀏覽器中檢視。

**Q: 我可以轉換其他 MAPI 項目，例如約會或聯絡人嗎？**  
A: 可以。Aspose.Email 支援透過相應的 `Mapi*` 類別並調整範本名稱，將約會、聯絡人與任務等轉換為 MHT。

**Q: 轉換過程需要網際網路連線嗎？**  
A: 不需要。所有處理皆在本機 Java 執行環境完成，僅授權驗證可能會向 Aspose 伺服器發出一次請求。

**Q: 轉換是執行緒安全的嗎？**  
A: 此 API 在唯讀操作下是執行緒安全的。若同時轉換大量檔案，請為每個執行緒建立獨立的 `MapiMessage` 物件。

**Q: Aspose.Email 能處理多大的 MSG 檔案？**  
A: 函式庫可處理高達數百 MB 的檔案，但仍需留意 JVM 堆積大小，並考慮對大型附件使用串流方式。

## 結論

您現在已擁有完整、可投入生產的工作流程，使用 Aspose.Email for Java **將 MSG 轉換為 MHT**。透過自訂範本，您可以將 HTML 輸出調整為符合組織品牌或報告標準，而函式庫則負責解析 Outlook 二進位格式的繁重工作。

**下一步：**
- 嘗試不同的 `MhtTemplateName` 值，以樣式化其他 MAPI 項目類型。  
- 將轉換整合至批次工作或 REST 服務，以提供即時處理。  
- 探索 Aspose.Email 的其他功能，如 PST 處理、郵件發送與 MIME 解析。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-17  
**測試環境：** Aspose.Email for Java 25.4 (classifier `jdk16`)  
**作者：** Aspose