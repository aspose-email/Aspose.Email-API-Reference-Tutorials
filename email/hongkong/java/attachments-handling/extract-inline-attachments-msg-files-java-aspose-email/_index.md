---
date: '2025-12-17'
description: 學習如何使用 Aspose.Email for Java 提取內嵌附件並讀取 Outlook MSG（Java），一步步指南，協助您高效處理
  Outlook MSG 檔案。
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: 使用 Aspose.Email 在 Java 中提取 MSG 檔案的內嵌附件
url: /zh-hant/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email 的 Java – MSG 檔案提取內嵌附件

## 簡介

如果您需要從 Microsoft OutlookMSG 檔案中提取 Java 內嵌附件，那麼您來對地方了。許多開發人員在讀取 Outlookmsgjava 檔案時遇到困難，因為該格式將嵌入的圖像和文件隱藏在郵件正文中。在本教程中，我們將介紹一個簡潔且可用於生產環境的解決方案，該方案使用 Aspose.Email for Java 程式庫來定位、識別和保存這些內嵌附件。

完成本指南後，您將能夠：

* 在 Maven 專案中設定 Aspose.Email for Java。

* 讀取 Outlookmsgjava 檔案並枚舉其附件。

* 決定哪些附件是嵌入的，並寫入磁盤。

* 為大量處理程序提供最佳的實用方法。

## 快速解答

- **「內嵌附件」是什麼意思？ ** 嵌入在電子郵件正文中的附件（例如，顯示在郵件中的圖像）。 - **哪個函式庫可以處理 MSG 檔案？ ** Aspose.Email for Java。

- **我需要許可證嗎？ ** 試用版可用於評估；永久許可證可解除使用限制。

- **我可以一次處理多個 MSG 檔案嗎？ ** 可以－將邏輯批次處理，並使用執行緒池來實現可擴展性。

- **需要哪個 Java 版本？ ** JDK 16 或更高版本。

## 什麼是「提取 Java 內嵌附件」？

在 Java 中提取內聯附件是指以程式設計方式開啟 MSG 文件，掃描其附件集合，並僅提取標記為*內聯*（而非常規文件附件）的項目。當您需要將電子郵件的視覺內容（例如嵌入式徽標或螢幕截圖）儲存為單獨的圖像檔案時，此功能至關重要。

## 為什麼要使用 Aspose.Email 來完成此任務？

Aspose.Email 抽象化了底層 MAPI 結構，並為您提供了一個簡單、強型別的 API。與自行解析二進位 MSG 格式相比，Aspose.Email 具有以下優點：

* 處理所有 MSG 格式（Unicode、RTF、HTML）。

* 提供可靠的附件元資料屬性存取。

* 提供內建許可檢查和豐富的文件。

## 前提條件

若要繼續學習，請確保您已具備以下條件：

1. **庫和依賴項**

* Aspose.Email for Java（最新版本）。

* Maven（或支援 Maven 的 IDE）。

2. **運行時環境**

* 已安裝 JDK 16 或更高版本。

3. **基礎知識**

* 熟悉 Java I/O 和異常處理。

## 設定 Aspose.Email for Java

將 Aspose.Email 依賴項新增至您的 `pom.xml` 檔案中。以下程式碼片段與原始教程相同。

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 許可證取得步驟

* **免費試用：** 從 Aspose 網站下載試用版 DLL/JAR 檔案。

* **臨時許可證：** 申請 30 天評估許可證，進行無限制測試。

* **完整購買：** 取得永久許可證，用於生產環境部署。

## 實作指南

以下我們將解決方案分解為三個重點功能。每個功能都包含簡短說明，以及原始程式碼區塊（完全保留）。

### 功能 1 – 載入 MSG 文件

首先，將 Outlook 郵件載入到 `MapiMessage` 物件中。

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### 功能 2 – 取得附件

接下來，從郵件中提取完整的附件集合。

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### 功能 3 – 辨識並儲存內嵌附件

遍歷每個附件，檢查它是否為內嵌附件，如果是，則將其寫入磁碟。

```java
for (Object untypedAttachment : attachments) {
    MapiAttachment attachment = (MapiAttachment) untypedAttachment;
    if (IsAttachmentInline(attachment)) {
        try {
            SaveAttachment(attachment, UUID.randomUUID().toString());
        } catch (IOException e) {
            // Handle exception
        }
    }
}
```

#### 實用工具：判斷附件是否為內嵌附件

此輔助方法會檢查 MAPI 屬性，以確定附件是否為內嵌附件。

```java
import com.aspose.email.MapiAttachment;
import com.aspose.email.MapiObjectProperty;
import com.aspose.email.MapiProperty;

static boolean IsAttachmentInline(MapiAttachment attachment) {
    MapiObjectProperty objectData = attachment.getObjectData();
    if (objectData == null) return false;

    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("\u0003ObjInfo".equals(property.getName())) {
            byte[] data = property.getData();
            int odtPersist1 = data[1] << 8 | data[0];
            return (odtPersist1 & 0x40) == 0;
        }
    }
    return false;
}
```

#### 公用工具：儲存內嵌附件

將內嵌附件的二進位內容寫入本機檔案系統上的檔案。

```java
import com.aspose.email.MapiAttachment;
import java.io.FileOutputStream;
import java.io.IOException;

static void SaveAttachment(MapiAttachment attachment, String fileName) throws IOException {
    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("Package".equals(property.getName())) {
            try (FileOutputStream fs = new FileOutputStream(fileName)) {
                fs.write(property.getData(), 0, property.getData().length);
            }
        }
    }
}
```

## 實際應用

提取內嵌附件在許多實際場景中都非常有用：

* **自動化郵件處理** – 從新聞郵件中提取圖片進行分析。

* **資料遷移** – 從 Exchange 遷移到其他平台時，移動嵌入內容。

* **歸檔解決方案** – 透過單獨儲存內嵌資源，維持歸檔郵件的視覺效果。

## 效能注意事項

處理數百上千個 MSG 檔案時，請記住以下幾點：

* **批次處理：** 將檔案分組到易於管理的批次中，以避免記憶體峰值。

* **及時釋放資源：** 關閉流（使用 `try-with-resources`），並讓垃圾回收器回收物件。

* **並行執行：** 使用固定大小的 `ExecutorService` 並發執行多個提取作業，但要監控 CPU 使用率。

## 常見問題及故障排除

| 症狀 | 可能原因 |修復 |

|---------|--------------|-----|

| `attachment.getObjectData()` 拋出 `NullPointerException` 異常 | 郵件缺少附件元資料（例如，MSG 文件已損壞） | 在處理之前驗證 MSG 文件，或捕獲異常並記錄文件名。 |

| 儲存的檔案為空或已損壞 | 屬性名稱不正確（`"Package"` 區分大小寫） | 驗證屬性名稱是否與 MSG 檔案的實際屬性相符；Aspose.Email 文件列出了確切的字串。 |

| 處理大檔案時效能下降 | 流未關閉，導致記憶體洩漏 | 使用 try-with-resources 語句（如範例所示），並考慮在必要時增加 JVM 堆大小。 |

## 常見問題解答

**問：所需的最低 Aspose.Email 版本是什麼？ ** 

答：本教學使用 25.4 版本，但任何支援 JDK 16 的 24.x 及更高版本均可使用。

**問：我可以從加密的 MSG 檔案中提取內嵌附件嗎？ ** 

答：可以，前提是您在載入 `MapiMessage` 時提供正確的解密密碼。

**問：如何區分內嵌圖片和一般文件附件？ ** 

答：使用 `IsAttachmentInline` 輔助函數；它會檢查 MAPI 的 `ObjInfo` 標誌，該標誌會將附件標記為內嵌附件。

**問：有沒有辦法保留內嵌附件的原始檔名？ ** 

答：範例會產生一個 UUID 以確保唯一性，但您可以讀取 `attachment.getLongFileName()` 屬性並在呼叫 `SaveAttachment` 時使用它。

**問：這種方法在 Linux/macOS 和 Windows 上都適用嗎？ ** 

答：當然－只要安裝了 JDK，Aspose.Email 就是平台無關的。

## 資源

- **文件：** [Aspose Email 文件](https://docs.aspose.com/email/java/)

---

**上次更新：** 2025-12-17
**測試版本：** Aspose.Email for Java 25.4 (JDK16)
**作者：** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}