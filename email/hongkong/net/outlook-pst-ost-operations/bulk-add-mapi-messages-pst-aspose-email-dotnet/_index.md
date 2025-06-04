---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 有效地將大量 MAPI 訊息新增至 Outlook PST 文件，從而提高速度和效能。"
"title": "如何使用 Aspose.Email for .NET 將 MAPI 訊息批次新增至 PST 文件"
"url": "/zh-hant/net/outlook-pst-ost-operations/bulk-add-mapi-messages-pst-aspose-email-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Email for .NET 將 MAPI 訊息批次新增至 PST 檔案：綜合指南

## 介紹

管理 Outlook PST 檔案中的大量電子郵件資訊可能頗具挑戰性。手動新增電子郵件既耗時又低效。本指南介紹了一種強大的解決方案，使用 **Aspose.Email for .NET** 簡化流程，大幅提高速度和效率。

在本教學結束時，您將了解如何利用 Aspose.Email 的功能：
- 以批次模式新增多個訊息
- 使用下列方法迭代 MAPI 訊息集合 `IEnumerable`

讓我們深入了解先決條件並開始吧！

### 先決條件

在繼續之前，請確保您已準備好以下內容：
- **所需庫**：安裝 Aspose.Email for .NET 版本 22.x 或更高版本。
- **環境設定**：安裝了 Visual Studio 的 .NET 開發環境。
- **知識前提**：熟悉 C# 和處理電子郵件資料。

## 設定 Aspose.Email for .NET

要使用 Aspose.Email for .NET，您需要將其安裝到您的專案中。操作步驟如下：

### 安裝方法

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用套件管理器控制台（NuGet）：**
```powershell
Install-Package Aspose.Email
```

或者，使用 **NuGet 套件管理器 UI** 在 Visual Studio 中：
- 搜尋“Aspose.Email”並安裝最新版本。

### 許可證獲取

先免費試用 Aspose.Email，評估其功能。如需延長使用期限或取得更多功能，請考慮購買臨時許可證。如需長期使用，請透過其購買授權。 [購買頁面](https://purchase。aspose.com/buy).

#### 基本初始化和設定

安裝後，在 C# 專案中初始化該程式庫，如下所示：
```csharp
using Aspose.Email.Storage.Pst;
```

## 實施指南

我們將把實作分為兩個主要功能：批次新增訊息和遍歷 MAPI 訊息集合。

### 功能 1：新增批次訊息並提升效能

#### 概述

此功能可讓您有效率地將多封電子郵件新增至 PST 檔案中，相較於單獨添加，可減少處理時間。它利用事件處理功能在每次添加時提供回饋。

##### 實施步驟

**步驟 1**：設定目錄和檔案路徑
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
string path = dataDir + "/PersonalStorageFile2.pst";
```

**第 2 步**：定義批次訊息新增方式
```csharp
private static void AddMessagesInBulkMode(string fileName, string msgFolderName)
{
    using (PersonalStorage personalStorage = PersonalStorage.FromFile(fileName))
    {
        FolderInfo folder = personalStorage.RootFolder.GetSubFolder("myInbox");
        folder.MessageAdded += OnMessageAdded;
        folder.AddMessages(new MapiMessageCollection(msgFolderName));
    }
}
```
- **參數**： `fileName` （PST 檔案路徑）， `msgFolderName` （訊息的來源資料夾）。
- **金鑰配置**：使用事件處理程序（`OnMessageAdded`) 提供訊息新增的即時更新。

**步驟3**：實作事件處理程序
```csharp
static void OnMessageAdded(object sender, MessageAddedEventArgs e)
{
    Console.WriteLine(e.EntryId);
    Console.WriteLine(e.Message.Subject);
}
```
- **目的**：記錄每個新增訊息的條目 ID 和主題，有助於偵錯或驗證。

### 功能 2：為 MapiMessages 實作 IEnumerable

#### 概述

透過實施 `IEnumerable`，您可以有效率地迭代儲存在檔案中的 MAPI 訊息集合。這在處理大型資料集時尤其有用。

##### 實施步驟

**步驟 1**：創建 `MapiMessageCollection` 班級
```csharp
class MapiMessageCollection : IEnumerable<MapiMessage>
{
    private string path;

    public MapiMessageCollection(string folderPath)
    {
        this.path = Path.Combine("YOUR_DOCUMENT_DIRECTORY", folderPath);
    }

    public IEnumerator<MapiMessage> GetEnumerator()
    {
        return new MapiMessageEnumerator(path);
    }

    IEnumerator IEnumerable.GetEnumerator() => GetEnumerator();
}
```
- **功能**：儲存並迭代訊息檔案。

**第 2 步**：實作枚舉器
```csharp
class MapiMessageEnumerator : IEnumerator<MapiMessage>
{
    private readonly string[] files;
    private int position = -1;

    public MapiMessageEnumerator(string directoryPath)
    {
        files = Directory.GetFiles(directoryPath);
    }

    public bool MoveNext()
    {
        position++;
        return (position < files.Length);
    }

    public void Reset() => position = -1;

    object IEnumerator.Current => Current;

    public MapiMessage Current
    {
        get
        {
            try { return MapiMessage.FromFile(files[position]); }
            catch (IndexOutOfRangeException) { throw new InvalidOperationException(); }
        }
    }

    public void Dispose() { }
}
```
- **功能**：管理訊息檔案的迭代，處理檔案邊界和異常。

## 實際應用

以下是這些功能的一些實際用例：
1. **自動電子郵件歸檔**：將來自不同來源的電子郵件批次新增到單一 PST 中進行存檔。
2. **電子郵件遷移**：使用批次在伺服器之間遷移大量電子郵件。
3. **數據分析**：迭代並分析文件中儲存的電子郵件內容，而無需將所有內容載入到記憶體中。

## 性能考慮

處理大型資料集時，優化效能至關重要：
- **批量處理**：透過批次處理訊息來減少單一操作的開銷。
- **記憶體管理**： 使用 `using` 語句以確保正確處置資源，最大限度地減少記憶體洩漏。
- **高效迭代**：實施 `IEnumerable` 允許延遲加載，減少初始加載時間。

## 結論

透過本指南，您學習如何使用 Aspose.Email for .NET 有效率地管理和處理 PST 檔案中的大量電子郵件。這些技巧不僅節省時間，還能提升應用程式的效能。繼續閱讀 Aspose.Email 的文檔，解鎖更多強大功能！

## 常見問題部分

**1. 如何取得 Aspose.Email 的臨時許可證？**
   - 訪問 [臨時許可證頁面](https://purchase.aspose.com/temporary-license/) 並按照說明進行操作。

**2. 我可以將郵件新增至「我的收件匣」以外的資料夾嗎？**
   - 是的，修改 `folder = personalStorage.RootFolder.GetSubFolder("myInbox")` 為您想要的資料夾名稱。

**3. 群發訊息有什麼限制？**
   - 批量操作可能會受到磁碟空間和 PST 檔案大小的限制。

**4. 在訊息迭代過程中出現異常如何處理？**
   - 圍繞潛在故障點（例如檔案存取或解析錯誤）實作 try-catch 區塊。

**5. Aspose.Email 適合大型企業解決方案嗎？**
   - 是的，它旨在在企業環境中有效地處理大量電子郵件管理任務。

## 資源
- **文件**： [Aspose.Email .NET 參考](https://reference.aspose.com/email/net/)
- **下載**： [Aspose.Email 發布](https://releases.aspose.com/email/net/)
- **購買**： [購買 Aspose.Email](https://purchase.aspose.com/buy)
- **免費試用**： [開始免費試用](https://releases.aspose.com/email/net/)
- **臨時執照**： [申請臨時許可證](https://purchase.aspose.com/temporary-license/)
- **支援**： [Aspose 電子郵件論壇](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}