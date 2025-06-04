---
"description": "使用 Aspose.Email for .NET 將電子郵件轉換為具有準確時區的 MHT 格式。提供逐步指南和程式碼範例。"
"linktitle": "使用 C# 將電子郵件轉換為帶有時區的 MHT"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 C# 將電子郵件轉換為帶有時區的 MHT"
"url": "/zh-hant/net/email-conversion-and-export/converting-email-to-mht-with-timezone-in-csharp/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 將電子郵件轉換為帶有時區的 MHT


## 電子郵件轉換簡介 使用時區將電子郵件轉換為 MHT

將電子郵件轉換為各種格式是許多應用程式的常見需求。在時間和時區資訊至關重要的情況下，確保在轉換過程中準確保留這些資訊至關重要。在本指南中，我們將重點放在如何將電子郵件轉換為 MHT 格式，同時正確處理時區資料。

## 設定您的開發環境

在深入編碼過程之前，請確保您的開發環境已準備就緒。確保您已安裝相容版本的 Visual Studio，並建立一個新的 C# 專案來開始。

## 安裝 Aspose.Email for .NET

Aspose.Email for .NET 是一個功能豐富的程式庫，可簡化與電子郵件相關的任務。要安裝它，請按照以下步驟操作：

1. 在 Visual Studio 中開啟您的專案。
2. 前往「工具」>「NuGet 套件管理器」>「管理解決方案的 NuGet 套件」。
3. 搜尋“Aspose.Email”並安裝該套件。

## 載入和解析電子郵件訊息

在此步驟中，我們將載入並解析要轉換的電子郵件。使用以下程式碼片段作為起點：

```csharp
// 加入必要的 using 語句
using Aspose.Email;

// 載入電子郵件訊息
var message = MailMessage.Load("path/to/your/email.eml");

// 現在您可以存取訊息屬性
var subject = message.Subject;
var sender = message.From.Address;
// ....其他屬性
```

## 處理時區資訊

正確處理時區資訊至關重要。以下程式碼片段示範如何從電子郵件中提取和管理時區資料：

```csharp
var timezone = message.TimezoneOffset;
var timezoneId = Timezone.GetIdFromOffset(timezone);
var timezoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timezoneId);
// 現在您可以使用 timezoneInfo 來處理時區轉換
```

## 將電子郵件轉換為 MHT 格式

現在到了核心的轉換步驟。我們將使用 Aspose.Email 執行到 MHT 格式的轉換：

```csharp
var mhtOptions = MhtSaveOptions.DefaultMhtml;
var mhtStream = new MemoryStream();
message.Save(mhtStream, mhtOptions);
```

## 儲存MHT文件

將電子郵件轉換為 MHT 格式後，就可以將其儲存為文件了：

```csharp
using var fileStream = new FileStream("output.mht", FileMode.Create);
mhtStream.Seek(0, SeekOrigin.Begin);
mhtStream.CopyTo(fileStream);
```

## 探索其他自訂

Aspose.Email for .NET 提供多種自訂選項。您可以探索新增附件、修改郵件屬性等功能，以滿足您的應用程式需求。

## 使用 Aspose.Email for .NET 的好處

Aspose.Email for .NET 簡化了複雜的電子郵件相關任務，使開發人員能夠專注於核心功能。它為各種電子郵件格式提供強大的支持，確保轉換準確且有效率。

## 結論

在本指南中，我們學習如何使用 Aspose.Email for .NET 將電子郵件轉換為 MHT 格式，並處理時區資訊。透過遵循這些步驟並探索更多自訂選項，您可以將電子郵件轉換功能無縫整合到您的應用程式中。

## 常見問題解答

### 如何在電子郵件轉換期間處理附件？

要處理附件，您可以使用 `Attachments` 的財產 `MailMessage` 類。在轉換過程中，根據需要遍歷附件並儲存它們。

### 我可以使用 Aspose.Email for .NET 將電子郵件轉換為其他格式嗎？

是的，Aspose.Email for .NET 支援多種格式，包括 MSG、EML、PST 等。您可以根據所需的輸出格式調整提供的程式碼範例。

### 時區資訊是否以 MHT 格式儲存？

是的，轉換過程中會保留時區資訊。透過處理時區偏移並使用適當的 `TimeZoneInfo` 方法，您可以確保 MHT 檔案中的時區表示準確。

### 在哪裡可以找到有關 Aspose.Email for .NET 的更多文件和更新？

您可以參考文件來獲取全面的資訊和更新： [Aspose.Email for .NET API 參考](https://reference.aspose.com/email/net/)

### 如何下載最新版本的 Aspose.Email for .NET？

您可以從發布頁面下載最新版本： [下載 Aspose.Email for .NET](https://releases.aspose.com/email/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}