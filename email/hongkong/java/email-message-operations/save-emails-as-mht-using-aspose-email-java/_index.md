---
date: '2026-09-22'
description: 了解如何在 Java 中使用 Maven 搭配 Aspose.Email 授權將電郵儲存為 MHT 檔案。內容包括設定、客製化範本以及行事曆事件處理。
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: 了解如何在 Java 中使用 Maven 搭配 Aspose.Email 授權將電郵儲存為 MHT 檔案。內容包括設定、客製化範本以及行事曆支援。
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: 如何使用 Aspose.Email 授權將電郵儲存為 MHT
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: 如何使用 Aspose.Email 授權將電郵儲存為 MHT
url: /zh-hant/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Email 授權將電子郵件儲存為 MHT

## 介紹

有效管理電子郵件資料可能充滿挑戰，尤其在分享與歸檔時更是如此。在本指南中，我們將示範 **如何使用 Maven Aspose.Email for Java 搭配 Aspose.Email 授權來儲存 MHT 檔案**，讓您能以自訂範本將電子郵件轉換為 MHT，並保留行事曆事件。完成後，您將得到一個可直接執行的解決方案，適用於任何 Java 16+ 環境，且符合生產環境的授權需求。

## 快速解答
- **需要哪個函式庫？** Maven Aspose.Email for Java (v25.4+)。  
- **產生的格式是什麼？** MHT（MHTML）檔案，將 HTML、圖片與行事曆資料打包在一起。  
- **可以自訂標頭嗎？** 可以 – 使用 `MhtFormatOptions` 與範本字串。  
- **需要授權嗎？** 生產環境必須使用 Aspose.Email 授權；免費試用可用於評估。  
- **需要哪個 Java 版本？** JDK 16 或更新版本。  

## 什麼是 Maven Aspose.Email for Java？

Maven Aspose.Email for Java 是一套函式庫，提供完整的 API 讓您能直接在 Java 程式碼中建立、讀取、轉換與操作電子郵件訊息。它支援超過 30 種電子郵件格式，包括 MSG、EML 與 MHT，讓您幾乎能處理所有遇到的電子郵件檔案。

## 為什麼要將電子郵件轉換為 MHT？

MHT 檔案會將所有資源（HTML、圖片、行事曆資料）嵌入單一檔案，使其能在任何現代瀏覽器中即時檢視，且不需外部資源。此格式保留原始外觀，支援重複行事曆事件，並降低分享時遺失附件的風險。

## 前置條件
- **Aspose.Email for Java**（Maven 套件 `com.aspose:aspose-email:25.4`，使用 `jdk16` classifier）。  
- **Maven** 已安裝並在您的機器上配置。  
- **JDK 16+**（此函式庫以 Java 16 為目標）。  
- 有效的 **Aspose.Email 授權** 檔案，用於生產環境。  
- 基本的 Java 知識（檔案處理、Maven 依賴）。  

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

Aspose 提供免費試用以探索其功能，並提供購買授權或取得臨時授權的選項。

1. **免費試用** – 從 [Releases](https://releases.aspose.com/email/java/) 下載，無限制體驗功能。  
2. **臨時授權** – 透過 [Temporary License Page](https://purchase.aspose.com/temporary-license/) 申請完整功能的授權。  
3. **購買** – 取得永久授權以支援長期專案。  

### 基本初始化

安裝完成後，在您的 Java 應用程式中初始化函式庫：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

完成上述步驟後，您即可使用 Aspose.Email 的功能來有效處理電子郵件。

## 實作指南

### 功能 1：載入 MailMessage

#### 概觀

`MailMessage` 是 Aspose.Email 的核心物件，代表一封電子郵件，包含其標頭、內容、附件與行事曆事件。

#### 步驟說明

**匯入必要的類別**

```java
import com.aspose.email.MailMessage;
```

**從檔案載入電子郵件**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

此程式碼片段會從您指定的目錄載入電子郵件訊息。

### 功能 2：設定 MhtSaveOptions

#### 概觀

`MhtSaveOptions` 用於設定 Aspose.Email 如何將 `MailMessage` 儲存為 MHT 檔案，控制格式旗標、範本與資源嵌入。正確的設定可讓您嵌入標頭、渲染行事曆事件，並嵌入所有圖片。

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

此設定會在 MHT 輸出中設定標頭與行事曆事件的渲染。

### 功能 3：將 MailMessage 儲存為 MHT

#### 概觀

將已設定好的 `MailMessage` 儲存為 MHT 檔案會產生單一的自包含文件，可在瀏覽器或電子郵件客戶端開啟。`save` 方法會遵循先前定義的選項。

#### 步驟說明

**匯入必要的類別**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**儲存電子郵件訊息**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

此指令會將電子郵件寫入 MHT 檔案，供分享或歸檔使用。

## 實務應用
- **電子郵件歸檔** – 將重要的電子郵件轉換並儲存為網頁友善格式，以供長期保存。  
- **法律文件** – 在需要保留電子郵件真實性的法律證據中使用 MHT 檔案。  
- **跨平台分享** – 透過 MHT 將所有內容打包成單一檔案，跨平台分享時不會遇到相容性問題。  

將其與其他系統（如 CRM 或專案管理工具）整合，可透過直接嵌入關鍵電子郵件資料於工作流程中，提升協作效率。

## 效能考量

Aspose.Email for Java 能在不將整個文件載入記憶體的情況下處理高達 500 MB 的檔案，且在一般伺服器上通常能在 2 秒內將含有嵌入圖片的 100 頁電子郵件轉換完成。為了保持應用程式的回應性，請謹慎管理記憶體使用，並盡可能批次執行 I/O 操作。

## 常見問題與解決方案

`MhtFormatOptions` 為列舉型別，用於控制在將訊息儲存為 MHT 時包含哪些元素（標頭、資源、行事曆事件）。

| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| **NullPointerException on `msg.save`** | 輸出路徑不正確 | 確認 `YOUR_OUTPUT_DIRECTORY` 存在且可寫入。 |
| **Missing images in MHT** | `MhtFormatOptions` 未設定為嵌入資源 | 將 `MhtFormatOptions.EmbedResources` 加入選項旗標。 |
| **Calendar events not rendered** | 未加入 `RenderCalendarEvent` 旗標 | 確保使用 `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` |

## 常見問答

**Q: 儲存電子郵件為 MHT 時，如何處理附件？**  
A: 設定 `MhtSaveOptions` 以嵌入附件；函式庫會自動將其包含於 MHT 套件中。

**Q: 可以自訂輸出 MHT 檔案中的電子郵件標頭嗎？**  
A: 可以，使用 `MhtFormatOptions.WriteHeader` 並為每個標頭欄位提供自訂範本字串。

**Q: 使用 Aspose.Email Java 的系統需求是什麼？**  
A: 需要 JDK 16 或更高版本。此函式庫可在任何支援 Maven 專案的 IDE 中使用。

**Q: 能否只儲存電子郵件訊息的特定部分？**  
A: 雖然 MHT 通常包含完整訊息，但您可以在儲存前操作 `MailMessage` 屬性，以排除不需要的部分。

**Q: 如何排除電子郵件載入或儲存時的問題？**  
A: 核對檔案路徑、確保授權正確套用，並參考 Aspose.Email [support forum](https://forum.aspose.com/c/email/10) 取得詳細協助。

**Q: 此函式庫是否支援將其他格式（EML、MSG）轉換為 MHT？**  
A: 完全支援。`MailMessage.load` 能讀取 EML、MSG 以及其他支援的格式，之後即可使用相同的選項將其儲存為 MHT。

## 資源
- **文件**：欲深入了解所有功能，請造訪 [Aspose Email Java Documentation](https://reference.aspose.com/email/java/)。  
- **下載**：從 [Releases](https://releases.aspose.com/email/java/) 下載，開始免費試用。  
- **購買**：於 [Official Purchase Page](https://purchase.aspose.com/buy) 探索長期使用的購買方案。  
- **免費試用與臨時授權**：透過以下連結取得完整功能的免費試用或臨時授權：  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

立即探索、實作，並以 Aspose.Email for Java 轉變您的電子郵件處理方式！

---

**最後更新：** 2026-09-22  
**測試環境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

---

## 相關教學

- [精通 Aspose.Email for Java：授權與電子郵件處理指南](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [如何使用 Aspose.Email for Java 將 MSG 轉換為 MHT – 步驟指南](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [如何使用 Aspose.Email for Java 儲存 MSG 電子郵件](/email/java/email-message-operations/aspose-email-java-create-save-emails/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}