---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 高效管理 Outlook PST 聯絡人。本指南涵蓋如何載入、擷取和儲存 vCard 格式的聯絡人資料。"
"title": "如何使用 Aspose.Email for .NET 載入和儲存 Outlook PST 聯絡人－逐步指南"
"url": "/zh-hant/net/outlook-pst-ost-operations/load-save-outlook-pst-contacts-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for .NET 載入並儲存 Outlook PST 聯絡人

## 介紹

對於處理大量資料的企業來說，高效管理儲存在 Microsoft Outlook 個人儲存表 (PST) 檔案中的電子郵件聯絡人至關重要。無論您是遷移、審核還是整理聯絡人列表，如果沒有合適的工具，處理這些任務都會非常困難。本指南示範如何使用 Aspose.Email for .NET 輕鬆地從 PST 檔案中載入和儲存聯絡人。

**您將學到什麼：**
- 如何使用 Aspose.Email for .NET 載入 PST 文件
- 從 PST 文件中提取聯絡資訊
- 以 vCard（VCF）格式儲存提取的聯絡人

準備好簡化您的電子郵件管理了嗎？讓我們先設定您的環境並了解先決條件。

## 先決條件

在開始之前，請確保您已：

### 所需的庫和相依性：
- **Aspose.Email for .NET**：處理 PST 檔案的主要庫。
- **.NET SDK**：確保與適當版本的.NET 框架或.NET Core 相容。

### 環境設定要求：
- 像 Visual Studio 或 VS Code 這樣的支援 C# 的開發環境。

### 知識前提：
- 對 C# 和 .NET 專案結構有基本的了解。
- 熟悉在程式碼中處理文件目錄。

考慮到這些先決條件，讓我們設定 Aspose.Email for .NET。

## 設定 Aspose.Email for .NET

若要使用 Aspose.Email for .NET，請使用下列方法之一將程式庫新增至您的專案：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**在 Visual Studio 中使用套件管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**透過 NuGet 套件管理器 UI：**
搜尋“Aspose.Email”並安裝最新版本。

### 許可證取得步驟：
1. **免費試用**：從免費試用開始探索圖書館的功能。
2. **臨時執照**：如果您需要超出試用期的更多時間，請取得臨時許可證。
3. **購買**：考慮購買完整許可證以供長期使用。

安裝 Aspose.Email for .NET 後，透過包含其命名空間在專案中進行初始化：

```csharp
using Aspose.Email.Storage.Pst;
using Aspose.Email.Mapi;
```

## 實施指南

### 載入 Outlook PST 文件

此功能示範如何載入 PST 檔案並存取特定資料夾（如「聯絡人」）。

#### 概述
載入 PST 檔案是管理聯絡人的第一步，可讓您以程式設計方式存取和操作儲存的資料。

#### 步驟

**步驟 1**：設定目錄路徑
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 指定包含 PST 檔案的目錄。
```

**第 2 步**：載入 PST 文件
```csharp
PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir + "Outlook.pst");
FolderInfo folderInfo = personalStorage.RootFolder.GetSubFolder("Contacts");
// 現在可以存取聯絡人資料夾以進行進一步的操作。
```
*筆記*：確保您的 PST 檔案的路徑正確，並且「聯絡人」資料夾存在。

### 提取並顯示聯絡資訊

載入 PST 檔案後，接下來提取聯絡資訊。

#### 概述
此功能可讓您從 PST 檔案中儲存的每個聯絡人中提取詳細資訊並顯示它們。

#### 步驟

**步驟 1**：檢索聯絡人
```csharp
MessageInfoCollection messageInfoCollection = folderInfo.GetContents();
```

**第 2 步**：提取並顯示聯絡方式
```csharp
foreach (MessageInfo messageInfo in messageInfoCollection)
{
    MapiContact contact = (MapiContact)personalStorage.ExtractMessage(messageInfo).ToMapiMessageItem();
    Console.WriteLine("Name: " + contact.NameInfo.DisplayName + " - " + messageInfo.EntryIdString);
}
```

### 將聯絡資訊儲存為 VCF 格式

提取聯絡人後，將其儲存為更便攜的格式，如 vCard（VCF）。

#### 概述
將提取的聯絡人儲存到磁碟可以輕鬆共享和備份。

#### 步驟

**步驟 1**：設定輸出目錄
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY"; // 指定您的輸出目錄。
if (!Directory.Exists(outputDir))
    Directory.CreateDirectory(outputDir);
```

**第 2 步**：將聯絡人儲存為 VCF 文件
```csharp
foreach (MessageInfo messageInfo in messageInfoCollection)
{
    MapiContact contact = (MapiContact)personalStorage.ExtractMessage(messageInfo).ToMapiMessageItem();
    contact.Save(Path.Combine(outputDir, contact.NameInfo.DisplayName + ".vcf"), ContactSaveFormat.VCard);
}
```
*筆記*：確保輸出目錄存在或由您的程式碼建立。

## 實際應用

1. **資料遷移**：使用此解決方案將聯絡人從 PST 檔案遷移到其他系統。
2. **備份和還原**：自動備份 vCard 格式的聯絡人數據，以便在需要時輕鬆復原。
3. **與 CRM 系統集成**：提取聯絡人以實現與客戶關係管理 (CRM) 平台的無縫整合。

## 性能考慮

為了在使用 Aspose.Email for .NET 時最佳化效能：
- **記憶體管理**：適當處置物體以釋放資源。
- **批次處理**：如果需要，可以批次處理大型 PST 文件，從而減少記憶體佔用。
- **非同步操作**：盡可能使用非同步方法來增強反應能力。

## 結論

透過本指南，您學習如何使用 Aspose.Email for .NET 載入 Outlook PST 檔案並提取聯絡人資訊。現在，您可以將這些聯絡人儲存為 vCard 格式，以便輕鬆共用或備份。

**後續步驟：**
- 探索 Aspose.Email 庫的更多功能。
- 將此解決方案整合到更大的工作流程或應用程式中。

準備好將新學到的技能付諸實現了嗎？嘗試不同的 PST 文件，看看 Aspose.Email for .NET 如何簡化您的電子郵件管理任務！

## 常見問題部分

1. **我可以從雲端儲存載入 PST 檔案嗎？**
   - 是的，您需要執行額外的步驟將文件下載到本機，然後再載入它。

2. **如果我的 PST 檔案被加密了怎麼辦？**
   - 確保使用 Aspose.Email 存取 PST 檔案時設定了正確的密碼。

3. **如何處理大型 PST 檔案而不耗盡記憶體？**
   - 考慮以較小的批次處理聯絡人並及時處置物品。

4. **此方法可以用於舊版的 Outlook 嗎？**
   - 是的，只要這些版本支援 PST 格式。

5. **我可能會遇到哪些常見錯誤？**
   - 缺少資料夾或不正確的檔案路徑可能會導致異常；請確保您的目錄結構準確無誤。

## 資源

- [Aspose.Email for .NET 文檔](https://reference.aspose.com/email/net/)
- [下載 Aspose.Email for .NET](https://releases.aspose.com/email/net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/email/net/)
- [臨時執照申請](https://purchase.aspose.com/temporary-license/)
- [Aspose 支援論壇](https://forum.aspose.com/c/email/10)

本教學將協助您使用 Aspose.Email for .NET 高效管理電子郵件聯絡人。祝您程式愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}