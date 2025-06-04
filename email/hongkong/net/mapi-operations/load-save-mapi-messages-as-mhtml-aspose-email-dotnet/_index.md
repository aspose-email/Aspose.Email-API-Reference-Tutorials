---
"date": "2025-05-30"
"description": "學習如何使用 Aspose.Email for .NET 以程式設計方式從檔案載入 MAPI 訊息並將其轉換為 MHT 格式。請遵循本逐步指南。"
"title": "如何使用 Aspose.Email for .NET 將 MAPI 訊息載入並儲存為 MHTML"
"url": "/zh-hant/net/mapi-operations/load-save-mapi-messages-as-mhtml-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for .NET 將 MAPI 訊息載入並儲存為 MHTML

## 介紹
以程式方式管理電子郵件訊息可能頗具挑戰性，尤其是像 MAPI 這樣複雜的格式。然而，使用 Aspose.Email for .NET，您可以輕鬆地從檔案載入這些訊息，並將其儲存為 Web 友善的 MHT（MIME HTML）格式。

本指南將指導您使用 Aspose.Email for .NET 將 MAPI 郵件轉換為 MHTML 格式。您將學習如何配置保存選項並有效率地執行檔案操作。

**您將學到什麼：**
- 在您的開發環境中設定 Aspose.Email for .NET。
- 使用載入 MAPI 訊息 `MapiMessage` 班級。
- 配置自訂 HTML 範本以 MHT 格式儲存。
- 使用自訂選項將 MAPI 訊息儲存為 MHTML 檔案。

## 先決條件

### 所需的函式庫、版本和相依性
要遵循本教程，您需要：
- **Aspose.Email for .NET**：請確保您已安裝 22.10 或更高版本。
- **.NET Framework 或 .NET Core/5+/6+**：取決於您的項目設定。

### 環境設定要求
確保您的開發環境支援 .NET 專案。您可以使用 Visual Studio、具有 C# 擴充功能的 VS Code，或任何支援 .NET 開發的 IDE。

### 知識前提
基本了解：
- C# 程式設計。
- 在 .NET 中處理文件和目錄。
- 與第三方函式庫合作。

## 設定 Aspose.Email for .NET
Aspose.Email 的使用非常簡單。安裝方法如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用套件管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**使用 NuGet 套件管理器 UI：**
1. 開啟 NuGet 套件管理器。
2. 搜尋“Aspose.Email”並安裝最新版本。

### 許可證獲取
要開始使用 Aspose.Email，您可以：
- **免費試用**：下載試用許可證來測試所有功能。
- **臨時執照**：取得臨時許可證，以存取全功能，不受評估限制。
- **購買**：如果您準備將其整合到您的生產環境中，請購買訂閱。

安裝完成後，透過在專案中包含必要的命名空間來初始化函式庫：
```csharp
using Aspose.Email;
using System;
```

## 實施指南

### 功能 1：從檔案載入 MAPI 訊息

#### 概述
此功能示範如何使用 Aspose.Email 從指定檔案路徑載入 MAPI 訊息，這對於處理儲存為 MAPI 訊息的電子郵件至關重要。

#### 實施步驟
**步驟 1**：定義目錄路徑
代替 `"YOUR_DOCUMENT_DIRECTORY"` 與您的實際目錄 `MapiTask.msg` 文件所在位置。
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 替換為您的文件目錄路徑
```
**第 2 步**：載入 MAPI 訊息
使用 `MapiMessage.FromFile()` 方法來載入訊息，建立一個 `MapiMessage` 來自它的物件。
```csharp
// 從指定檔案載入 MapiMessage
dynamic msg = MapiMessage.FromFile(dataDir + "MapiTask.msg");
```

### 功能2：配置MHT儲存選項

#### 概述
配置儲存選項可讓您自訂 MAPI 郵件以 MHTML 格式儲存的方式。此步驟涉及設定範本和格式選項。

#### 實施步驟
**步驟 1**：初始化 `MhtSaveOptions`
設定預設的 MHTML 儲存選項，該選項將針對自訂輸出進行修改。
```csharp
dynamic opt = SaveOptions.DefaultMhtml;
```
**第 2 步**：設定格式選項
在已儲存的 MHTML 檔案中啟用任務欄位和標題資訊的渲染。
```csharp
opt.MhtFormatOptions = MhtFormatOptions.RenderTaskFields | MhtFormatOptions.WriteHeader;
```
**步驟3**：自訂模板
為各種任務屬性定義 HTML 範本以控制它們在輸出檔案中的外觀。
```csharp
// 清除現有模板
opt.FormatTemplates.Clear();

// 為特定任務屬性新增自訂 HTML 模板
opt.FormatTemplates.Add(MhtTemplateName.Task.Subject, "<span class='headerLineTitle'>Subject:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.ActualWork, "<span class='headerLineTitle'>Actual Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.TotalWork, "<span class='headerLineTitle'>Total Work:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Status, "<span class='headerLineTitle'>Status:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Owner, "<span class='headerLineTitle'>Owner:</span><span class='headerLineText'>{0}</span><br/>");
opt.FormatTemplates.Add(MhtTemplateName.Task.Priority, "<span class='headerLineTitle'>Priority:</span><span class='headerLineText'>{0}</span><br/>");
```

### 功能 3：將 MAPI 訊息儲存為 MHTML 文件

#### 概述
配置完成後，將載入的 MAPI 訊息儲存為 MHTML 檔案。此步驟將使用先前設定的選項完成轉換過程。

#### 實施步驟
**步驟 1**：定義輸出檔路徑
指定要儲存轉換後的 MHTML 檔案的位置。
```csharp
string outputFile = dataDir + "MapiTask_out.mht";
```
**第 2 步**：保存訊息
使用 `Save()` 方法並使用您配置的選項將訊息轉換並儲存為 MHTML 格式。
```csharp
// 使用先前配置的選項將訊息儲存到 MHT 文件
dynamic msg.Save(outputFile, opt);
```

## 實際應用
1. **電子郵件歸檔**：將舊系統的電子郵件轉換為適合網路的 MHTML 格式，以進行存檔。
2. **與任務管理系統集成**：轉換與任務相關的 MAPI 訊息以用於支援 HTML 格式的現代專案管理應用程式。
3. **記錄和共享**：以可存取的格式產生可共用的電子郵件任務報告，非常適合文件或協作。

## 性能考慮
### 優化效能
- 僅載入必要的文件以減少記憶體使用量。
- 盡可能使用非同步方法來避免阻塞操作。

### 資源使用指南
- 處理大量訊息時監控應用程式的記憶體佔用。
- 使用後妥善處理物品以釋放資源。

### 使用 Aspose.Email 進行 .NET 記憶體管理的最佳實踐
- 利用 `using` 語句來自動處理物件。
- 定期更新 Aspose.Email 以利用新版本中的改進和最佳化。

## 結論
在本教學中，您學習如何使用 Aspose.Email for .NET 從檔案載入 MAPI 郵件並將其儲存為 MHTML。現在，您已掌握了將這些功能應用到應用程式中的知識，從而增強電子郵件管理能力。

**後續步驟：**
- 嘗試不同的 `MhtSaveOptions` 設定.
- 探索 Aspose.Email for .NET 提供的其他功能。

## 常見問題部分
1. **我可以免費使用 Aspose.Email 嗎？**
   - 是的，您可以從 30 天的免費試用許可證開始，無限制地測試全部功能。
2. **除了 MAPI 和 MHTML 之外，Aspose.Email 還支援哪些格式？**
   - 它支援各種電子郵件格式，包括 EML、MSG、PST 等。
3. **如何在 Aspose.Email 中處理大檔案？**
   - 使用串流等節省記憶體的技術來讀取/寫入大檔案。
4. **我可以將此功能整合到 Web 應用程式中嗎？**
   - 當然！此功能非常適合需要電子郵件管理功能的 Web 應用程式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}