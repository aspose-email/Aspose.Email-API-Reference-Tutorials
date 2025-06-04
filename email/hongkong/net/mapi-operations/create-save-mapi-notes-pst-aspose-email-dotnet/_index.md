---
"date": "2025-05-30"
"description": "學習如何使用 C# 和 Aspose.Email 建立數位筆記並將其保存到 PST 檔案中，從而有效地管理數位筆記。請按照本逐步教程進行操作。"
"title": "使用 Aspose.Email for .NET 建立並儲存 MAPI 註解到 PST 檔案－綜合指南"
"url": "/zh-hant/net/mapi-operations/create-save-mapi-notes-pst-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Email for .NET 建立並儲存 MAPI 註解到 PST 檔案：綜合指南

## 介紹

您是否希望透過使用 C# 建立並保存數位筆記到 PST 檔案來有效地管理它們？本指南將向您展示如何使用 Aspose.Email for .NET 建立 MAPI 筆記、設定其屬性並將其儲存到新的 PST 檔案中。無論您是經驗豐富的開發人員，還是電子郵件程式設計新手，本教學都將引導您完成每個步驟。

### 您將學到什麼：
- 如何安裝和設定 Aspose.Email for .NET。
- 建立 MAPI 註釋並設定其屬性，如顏色、主題、正文和尺寸。
- 使用預定義資料夾將多個註解儲存到 PST 檔案中。
- 實際應用和效能優化技巧。

讓我們先確保您已設定好一切！

## 先決條件
在深入實施之前，請確保你的開發環境已準備就緒。你需要：

- **Aspose.Email for .NET 函式庫**：本教學使用 Aspose.Email 版本 22.xx 或更高版本。
- **開發環境**：安裝了 Visual Studio（2017 或更新版本）並配置為使用 C# 的機器。
- **對 C# 和 .NET 架構有基本的了解**：熟悉 C# 中的基本程式設計概念將會很有幫助。

## 設定 Aspose.Email for .NET
首先，透過以下方式安裝 Aspose.Email 庫：

**.NET CLI**
```bash
dotnet add package Aspose.Email
```

**套件管理器控制台**
```powershell
Install-Package Aspose.Email
```

**NuGet 套件管理器 UI**
- 開啟 Visual Studio，進入“管理 NuGet 套件”，搜尋“Aspose.Email”。安裝最新版本。

### 許可證獲取
若要無限制地使用 Aspose.Email，請考慮取得許可證：
- **免費試用**：從免費試用開始 [Aspose 下載](https://releases。aspose.com/email/net/).
- **臨時執照**：透過以下方式申請臨時許可證 [Aspose臨時許可證](https://purchase。aspose.com/temporary-license/).
- **購買**：如需長期使用，請購買許可證 [Aspose 購買](https://purchase。aspose.com/buy).

### 基本初始化
安裝後，請確保您的專案引用 Aspose.Email，包括：
```csharp
using Aspose.Email;
using Aspose.Email.Mapi;
```

## 實施指南
本節介紹如何逐步建立 MAPI 註解並將其儲存到 PST 檔案中。

### 建立和刪除現有的 PST 文件
首先設定文件目錄並處理現有文件：
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 將其設定為您的實際路徑
if (File.Exists(dataDir + "/SampleNote_out.pst"))
{
    File.Delete(dataDir + "/SampleNote_out.pst"); // 如果存在則刪除，重新開始
}
```

### 建立新的 PST 檔案和預定義資料夾
使用預先定義的「Notes」資料夾以 Unicode 格式建立新的 PST 檔案：
```csharp
using (PersonalStorage pst = PersonalStorage.Create(dataDir + "/SampleNote_out.pst", FileFormatVersion.Unicode))
{
    FolderInfo notesFolder = pst.CreatePredefinedFolder("Notes", StandardIpmFolder.Notes);
```

### 載入並將 MSG 轉換為 MAPI 註釋
載入現有的 MSG 檔案並將其轉換為 `MapiMessage`：
```csharp
MapiMessage message = MapiMessage.FromFile(dataDir + "/Note.msg"); // 確保您有此 MSG 文件
```

### 建立和自訂註釋
#### 註#1：黃色註釋
設定第一條筆記的主題、正文和顏色等屬性。
```csharp
// 使用黃色建立註解 #1
MapiNote note1 = (MapiNote)message.ToMapiMessageItem();
note1.Subject = "Yellow color note";
note1.Body = "This is a yellow color note";
```

#### 註#2：粉紅色註釋
使用不同的屬性自訂第二個註釋。
```csharp
// 使用粉紅色創建註釋＃2
MapiNote note2 = (MapiNote)message.ToMapiMessageItem();
note2.Subject = "Pink color note";
note2.Body = "This is a pink color note";
note2.Color = NoteColor.Pink;
```

#### 註釋 #3：帶有尺寸的藍色註釋
為第三個註釋添加尺寸以實現更多自訂。
```csharp
// 使用藍色和特定尺寸創建註釋＃3
MapiNote note3 = (MapiNote)message.ToMapiMessageItem();
note3.Subject = "Blue color note";
note3.Body = "This is a blue color note";
note3.Color = NoteColor.Blue;
note3.Height = 500; // 自訂高度
note3.Width = 500; // 自訂寬度
```

### 將註釋儲存到 PST 文件
將所有建立的註釋新增到新 PST 檔案中的「註釋」資料夾中：
```csharp
// 在資料夾中新增註釋
notesFolder.AddMapiMessageItem(note1);
notesFolder.AddMapiMessageItem(note2);
notesFolder.AddMapiMessageItem(note3);
}
```

## 實際應用
此功能可用於各種場景：
- **筆記管理系統**：在企業環境中自動建立和組織筆記。
- **電子郵件歸檔解決方案**：與需要將電子郵件內容存檔為筆記的系統整合。
- **客製化 CRM 工具**：透過將客戶互動儲存為筆記來增強客戶關係管理工具。

## 性能考慮
為了在 .NET 中使用 Aspose.Email 時獲得最佳效能：
- 透過適當處置物件來有效管理資源。
- 限制對大型 PST 檔案的並發操作數，以防止記憶體溢位。
- 盡可能使用非同步方法進行檔案 I/O 操作。

## 結論
現在，您已經掌握如何使用 Aspose.Email for .NET 建立 MAPI 註解並將其儲存到 PST 檔案中。這款強大的工具為以程式方式管理電子郵件資料開闢了無限可能。您可以造訪 Aspose.Email 的 [文件](https://reference.aspose.com/email/net/) 或嘗試其他功能。

準備好進一步提升你的技能了嗎？在小型專案中實施此解決方案，並即時見證其優勢！

## 常見問題部分
**問題1：我可以在Linux上使用Aspose.Email for .NET嗎？**
- 是的，Aspose.Email 與 .NET Core 等跨平台環境相容。

**Q2：是否可以根據內容動態變更筆記顏色？**
- 當然！您可以實現邏輯，根據筆記內容或其他條件設定其顏色屬性。

**Q3：如何有效處理大型 PST 檔案？**
- 考慮分塊操作並使用流技術來有效管理記憶體使用。

**Q4：Aspose.Email 可以同時建立多個 PST 檔案嗎？**
- 是的，但建議為每個檔案使用單獨的執行緒或進程，以防止資源爭用。

**問題5：在哪裡可以找到更多有關 Aspose.Email 的資源？**
- 探索 [Aspose 文檔](https://reference.aspose.com/email/net/) 和 [社群論壇](https://forum.aspose.com/c/email/10) 提供廣泛的指導和支持。

## 資源
- **文件**： [訪問這裡](https://reference.aspose.com/email/net/)
- **下載 Aspose.Email**： [取得最新版本](https://releases.aspose.com/email/net/)
- **購買許可證**： [立即購買](https://purchase.aspose.com/buy)
- **免費試用**： [開始免費試用](https://releases.aspose.com/email/net/)
- **臨時執照**： [在此請求](https://purchase.aspose.com/temporary-license/)
- **支援論壇**： [參與討論](https://forum.aspose.com/c/email/10)

現在，您已經掌握了利用 Aspose.Email for .NET 管理 PST 檔案中的 MAPI 註解的知識。祝您編碼愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}