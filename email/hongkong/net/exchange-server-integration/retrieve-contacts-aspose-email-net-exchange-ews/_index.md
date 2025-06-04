---
"date": "2025-05-30"
"description": "了解如何使用 Aspose.Email for .NET 透過 EWS 將聯絡人管理與 Exchange 伺服器整合。本指南涵蓋了聯絡人的設定、連接和高效檢索。"
"title": "使用 Aspose.Email 和 EWS 在 .NET 中擷取聯絡人－綜合指南"
"url": "/zh-hant/net/exchange-server-integration/retrieve-contacts-aspose-email-net-exchange-ews/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 中使用 Aspose.Email 和 EWS 檢索聯絡人：綜合指南

## 介紹

從 Exchange 伺服器管理聯絡人可無縫整合到您的 .NET 應用程式中，簡化溝通工作流程、節省時間並提高工作效率。本教程將指導您使用強大的 **Aspose.Email for .NET** API 透過 Web 服務 (EWS) 連接到 Exchange 伺服器並檢索聯絡人清單。

### 您將學到什麼：
- 在您的專案中設定 Aspose.Email for .NET
- 使用 EWS 連接到 Exchange 伺服器
- 以程式設計方式檢索和顯示聯絡資訊

掌握這些技能後，您將能夠輕鬆管理電子郵件通訊。讓我們先來了解先決條件。

## 先決條件

在深入程式碼實作之前，請確保您的開發環境已準備好採取行動：

- **庫和版本**：確保您已安裝 Aspose.Email for .NET。
- **環境設定**：您需要一個.NET開發環境，例如Visual Studio 2019或更高版本。
- **知識前提**：對 C# 和使用 API 的基本了解將會有所幫助。

## 設定 Aspose.Email for .NET

首先，您需要將 Aspose.Email 庫新增到您的專案中。操作如下：

### 安裝

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Email
```

**使用套件管理器控制台：**
```powershell
Install-Package Aspose.Email
```

**透過 NuGet 套件管理器 UI：**
搜尋“Aspose.Email”並安裝最新版本。

### 許可證獲取

你可以從 **免費試用** 探索功能。對於較長的項目，請考慮購買許可證或申請臨時許可證：
- [免費試用](https://releases.aspose.com/email/net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [臨時執照](https://purchase.aspose.com/temporary-license/)

透過新增必要的 using 指令並建立實例來初始化您的項目 `IEWSClient` 用於連接設定。

## 實施指南

本節將引導您完成從 Exchange 伺服器擷取聯絡人所需的每個步驟。

### 步驟 1：建立 IEWSClient 實例

**概述**：使用 Aspose.Email 的 EWS 用戶端與您的 Exchange 伺服器建立安全連線。

```csharp
IEWSClient client = EWSClient.GetEWSClient(
    "https://outlook.office365.com/ews/exchange.asmx", 
    "testUser",    
    "pwd",         
    "domain"       
);
```

**解釋**： 代替 `"testUser"`， `"pwd"`， 和 `"domain"` 使用您的實際 Exchange 伺服器憑證。此步驟將驗證並初始化連線。

### 第 2 步：列出所有聯絡人

**概述**：使用 EWS 從您的郵箱中取得聯絡人。

```csharp
Contact[] contacts = client.GetContacts(client.MailboxInfo.ContactsUri);
```

**解釋**： `client.GetContacts` 檢索所有可用的聯絡人。此方法傳回一個聯絡人物件數組，可供後續處理。

### 步驟3：顯示聯絡資訊

**概述**：遍歷檢索到的聯絡人以顯示他們的姓名和電子郵件地址。

```csharp
foreach (MapiContact contact in contacts)
{
    Console.WriteLine(
        "Name: " + contact.NameInfo.DisplayName + ", Email Address: " +
        contact.ElectronicAddresses.Email1
    );
}
```

**解釋**：循環遍歷每個 `MapiContact` 存取和顯示姓名和電子郵件地址等重要資訊。

### 故障排除提示

- 確保伺服器 URL、使用者名稱、密碼和網域配置正確。
- 如果無法連線到 Exchange 伺服器，請檢查網路連線。
- 驗證您的 API 版本是否與您的 .NET 框架版本相容。

## 實際應用

以下是一些透過 Aspose.Email 檢索聯絡人可能有益的實際場景：
1. **自動電子郵件行銷活動**：自動收集和更新聯絡人清單以用於行銷目的。
2. **CRM集成**：在 Exchange 伺服器和 CRM 系統（如 Salesforce 或 Dynamics 365）之間同步聯絡人資訊。
3. **資料備份解決方案**：建立聯絡人資料備份，確保業務連續性。

## 性能考慮

在.NET應用程式中使用Aspose.Email時：
- **優化網路調用**：透過僅取得必需欄位來最大限度地減少 API 呼叫次數。
- **高效率的記憶體管理**：處理不再需要的物件以釋放記憶體資源。
- **批次處理**：如果處理大型資料集，請考慮分批處理聯絡人。

## 結論

現在您已經學習如何使用 Aspose.Email for .NET 連線到 Exchange 伺服器並擷取聯絡人。這款強大的工具可以顯著增強您應用程式的電子郵件管理功能。如需進一步探索，您可以考慮深入研究 API 的高級功能，例如發送電子郵件或管理日曆。

立即採取行動，在您的專案中嘗試此實現！

## 常見問題部分

1. **什麼是 Aspose.Email for .NET？**
   - 它是一個透過各種協定（包括 EWS）促進與 Exchange 等電子郵件伺服器互動的程式庫。
2. **連接到 Exchange 伺服器時如何處理身份驗證錯誤？**
   - 仔細檢查您的憑證並確保伺服器 URL 正確。
3. **Aspose.Email 可以離線工作嗎？**
   - 雖然它主要與線上服務交互，但您可以離線操作本機文件，例如 PST 或 MSG 格式。
4. **我一次可以檢索的聯絡人數量有限制嗎？**
   - 聯絡限制取決於您的 Exchange 伺服器設定；如有需要，請諮詢您的系統管理員。
5. **如何使用 Aspose.Email 更新聯絡人資訊？**
   - 利用 `UpdateContact` 修改屬性後的方法 `MapiContact`。

## 資源

- [Aspose.Email文檔](https://reference.aspose.com/email/net/)
- [下載 Aspose.Email](https://releases.aspose.com/email/net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/email/net/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}