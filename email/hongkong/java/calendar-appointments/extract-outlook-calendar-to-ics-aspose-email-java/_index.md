---
date: '2026-03-23'
description: 學習如何使用 Aspose.Email for Java 將 PST 轉換為 ICS、匯出 Outlook 行事曆的 ics 檔案，並高效地將行事曆儲存為
  ics。
keywords:
- Outlook Calendar to ICS
- Aspose.Email for Java
- PST to ICS conversion
title: 使用 Aspose.Email for Java 將 PST 轉換為 ICS
url: /zh-hant/java/calendar-appointments/extract-outlook-calendar-to-ics-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for Java 將 PST 轉換為 ICS

## 簡介：將 PST 轉換為 ICS

有效管理您的行事曆項目對避免錯過約會及節省時間至關重要。如果您使用 Microsoft Outlook PST 檔案，**將 PST 轉換為 ICS** 可讓您將 Outlook 行事曆項目提取為通用相容的格式。本教學將指導您使用 Aspose.Email for Java 載入 Outlook PST 檔案，並將其行事曆項目轉換為 **將行事曆儲存為 ics** 格式。

**您將學到**
- 如何使用 Aspose.Email for Java 存取與操作 PST 檔案。  
- 從 PST 檔案提取行事曆項目的步驟。  
- 技術說明如何 **匯出 Outlook 行事曆 ics** 以及 **備份 Outlook 行事曆 ics**，以便在不同平台間輕鬆分享。  
- 設定、效能與疑難排解的最佳實踐。  

讓我們深入設定環境並實作此功能！

## Quick Answers
- **「將 PST 轉換為 ICS」是什麼意思？** 它指的是從 Outlook PST 檔案讀取行事曆項目，並將其轉換為可攜帶的 iCalendar 格式。  
- **我應該使用哪個函式庫？** Aspose.Email for Java 提供簡易的 API 來處理 PST 與 iCalendar 匯出。  
- **我需要授權嗎？** 免費試用可用於評估；正式環境需購買商業授權。  
- **我可以批次處理大量項目嗎？** 可以——遍歷資料夾內容，將每個項目儲存為 *.ics* 檔案。  
- **需要哪個 Java 版本？** 建議使用 JDK 16 或更高版本，以配合最新的 Aspose.Email 版本。

## 什麼是「將 PST 轉換為 ICS」？

將 PST 轉換為 ICS 代表讀取 PST 檔案內的 `Calendar` 資料夾，將每個 `MapiCalendar` 物件轉換為 iCalendar（`.ics`）格式。此格式受到 Google Calendar、Apple Calendar 以及幾乎所有現代排程應用程式的支援。

## 為什麼要使用 Aspose.Email for Java？

Aspose.Email 將複雜的 MAPI 結構抽象化為簡潔的物件導向 API。它能處理 PST 解析、時區轉換與 iCalendar 序列化，無需撰寫底層程式碼。這使其在 **java convert pst ics** 這類對可靠性與速度有要求的情境中表現理想。

## Prerequisites
- **Java Development Kit (JDK)：** 版本 16 或以上。  
- **Aspose.Email 函式庫：** 版本 25.4 或更新（透過 Maven 安裝）。  
- **IDE：** IntelliJ IDEA、Eclipse，或任何相容 Java 的 IDE。  

### Knowledge Prerequisites
- 基本的 Java 程式設計。  
- 熟悉 Java 的檔案 I/O。  

## Setting Up Aspose.Email for Java

To get started, integrate the Aspose.Email library into your Maven project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
- **免費試用：** 無償探索 API。  
- **臨時授權：** 申請短期金鑰以延長測試時間。  
- **購買：** 取得正式授權以供生產環境使用。  

Once the library is added, initialize it in your Java code:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.Utils;

String dataDir = Utils.getSharedDataDir(SaveCalendarItemsFromOutlookPSTToDiskInICSFormat.class) + "outlook/";
```

## Implementation Guide

### Load Outlook PST File

#### Step 1: Import Required Classes

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.Utils;
```

#### Step 2: Load the PST File

```java
String dataDir = Utils.getSharedDataDir(SaveCalendarItemsFromOutlookPSTToDiskInICSFormat.class) + "outlook/";
PersonalStorage pst = PersonalStorage.fromFile(dataDir + "YOUR_DOCUMENT_DIRECTORY/Outlook.pst");
```

> **專業提示：** 將 `YOUR_DOCUMENT_DIRECTORY` 替換為實際存放 PST 檔案的資料夾路徑。

### Access Calendar Folder

#### Step 1: Import Required Classes

```java
import com.aspose.email.FolderInfo;
```

#### Step 2: Retrieve the Calendar Folder

```java
FolderInfo calendarFolder = pst.getRootFolder().getSubFolder("Calendar");
```

### Extract and Save Calendar Items to ICS Format

#### Step 1: Import Required Classes

```java
import com.aspose.email.MessageInfoCollection;
import com.aspose.email.MapiCalendar;
import com.aspose.email.AppointmentSaveFormat;
```

#### Step 2: Extract Calendar Items

```java
MessageInfoCollection messageInfoCollection = calendarFolder.getContents();

for (Object messageInfo : messageInfoCollection) {
    // Convert each item to MapiCalendar
    MapiCalendar calendar = (MapiCalendar) pst.extractMessage((com.aspose.email.MessageInfo) messageInfo).toMapiMessageItem();
    
    // Save the item in ICS format
    String outputDirectory = "YOUR_OUTPUT_DIRECTORY";
    calendar.save(outputDirectory + "/Calendar: " + calendar.getSubject() + ".ics", AppointmentSaveFormat.Ics);
}
```

> **注意：** `outputDirectory` 應指向您希望儲存 `.ics` 檔案的可寫入資料夾。

## Why Convert PST to ICS? (Common Use Cases)

1. **跨平台行事曆分享：** 將活動匯出為 `.ics`，再匯入 Google Calendar、Apple Calendar 或任何相容 iCalendar 的應用程式。  
2. **備份與存檔：** **備份 Outlook 行事曆 ics** 檔案以供長期保存或符合法規要求。  
3. **與業務系統整合：** 將匯出的 `.ics` 檔案導入 CRM、ERP 系統或自訂排程服務。  

## Performance Considerations

- **批次操作：** 盡可能將儲存動作分組，以減少磁碟 I/O。  
- **資源釋放：** 處理完畢後呼叫 `pst.dispose()` 以釋放原生資源。  

## Troubleshooting Tips
- **檔案存取問題：** 確認 PST 檔案來源與輸出目錄皆具讀寫權限。  
- **函式庫相容性：** 確認 Aspose.Email 版本與您的 JDK 相符（例如 JDK 16 使用 `jdk16` classifier）。  
- **大型 PST 檔案：** 將項目分成較小批次處理，或使用串流 API 以降低記憶體壓力。  

## Common Issues and Solutions
| 問題 | 解決方案 |
|-------|----------|
| **Permission denied** 儲存檔案時 | 以適當的作業系統權限執行 JVM，或選擇其他輸出路徑。 |
| **No calendar items returned** | 確認 PST 確實包含 `Calendar` 資料夾且該資料夾不為空。 |
| **Incorrect time zones** | 若需強制使用特定時區，請在儲存前使用 `calendar.setTimeZone()`。 |

## Frequently Asked Questions

**Q: 什麼是 ICS 檔案的主要用途？**  
A: ICS 檔案以標準化、跨平台的格式儲存行事曆事件資訊，幾乎所有行事曆應用程式皆可匯入。

**Q: 如何更新 Aspose.Email 函式庫版本？**  
A: 在 `pom.xml` 中將 `<version>` 標籤改為目標版本，然後執行 `mvn clean install` 以重新整理相依性。

**Q: 我可以用相同方式提取其他 PST 資料夾（例如 Inbox、Contacts）嗎？**  
A: 可以——只要在 `getSubFolder()` 呼叫中將 `"Calendar"` 替換為目標資料夾名稱即可。

**Q: 我的 PST 檔案受密碼保護，該怎麼辦？**  
A: 使用 `PersonalStorage.fromFile(path, password)` 開啟加密的 PST 檔案；詳情請參考 Aspose.Email 文件中的加密處理說明。

**Q: 如何有效處理非常大的 PST 檔案？**  
A: 將項目分批處理，考慮使用平行串流，並確保及時釋放 `PersonalStorage` 物件，以避免記憶體泄漏。

## Resources
- **文件說明：** [Aspose.Email Java Documentation](https://reference.aspose.com/email/java/)
- **下載函式庫：** [Aspose Email for Java Release Downloads](https://releases.aspose.com/email/java/)
- **購買授權：** [Buy Aspose.Email](https://purchase.aspose.com/buy)
- **免費試用：** [Try Aspose.Email for Free](https://releases.aspose.com/email/java/)
- **臨時授權：** [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- **支援論壇：** [Aspose Email Support](https://forum.aspose.com/c/email/10)

我們希望本教學能協助您善用 Aspose.Email for Java，有效管理 Outlook 行事曆資料。祝編程愉快！

**最後更新：** 2026-03-23  
**測試環境：** Aspose.Email for Java 25.4 (jdk16)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}