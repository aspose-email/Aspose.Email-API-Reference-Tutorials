---
title: 在 C# 中將電子郵件轉換為帶有時區的 MHT
linktitle: 在 C# 中將電子郵件轉換為帶有時區的 MHT
second_title: Aspose.Email .NET 電子郵件處理 API
description: 使用 Aspose.Email for .NET 將電子郵件轉換為具有準確時區的 MHT 格式。提供了逐步指南和程式碼範例。
weight: 12
url: /zh-hant/net/email-conversion-and-export/converting-email-to-mht-with-timezone-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中將電子郵件轉換為帶有時區的 MHT


## 電子郵件轉換簡介 電子郵件到有時區的 MHT

將電子郵件訊息轉換為各種格式是許多應用程式中的常見要求。在時間和時區資訊起著至關重要作用的情況下，確保在轉換過程中準確保留此資訊非常重要。在本指南中，我們將重點放在將電子郵件轉換為 MHT 格式，同時正確處理時區資料。

## 設定您的開發環境

在我們深入編碼過程之前，讓我們確保您的開發環境已準備好進行操作。確保安裝了相容版本的 Visual Studio，並建立新的 C# 專案以開始。

## 安裝 Aspose.Email for .NET

Aspose.Email for .NET 是一個功能豐富的函式庫，可以簡化與電子郵件相關的任務。要安裝它，請按照下列步驟操作：

1. 在 Visual Studio 中開啟您的專案。
2. 前往「工具」>「NuGet 套件管理器」>「管理解決方案的 NuGet 套件」。
3. 搜尋“Aspose.Email”並安裝該軟體包。

## 載入和解析電子郵件訊息

在此步驟中，我們將載入並解析要轉換的電子郵件。使用以下程式碼片段作為起點：

```csharp
//加入必要的 using 語句
using Aspose.Email;

//載入電子郵件訊息
var message = MailMessage.Load("path/to/your/email.eml");

//現在您可以存取訊息屬性
var subject = message.Subject;
var sender = message.From.Address;
//....其他屬性
```

## 處理時區資訊

正確處理時區資訊至關重要。以下程式碼片段示範如何從電子郵件中提取和管理時區資料：

```csharp
var timezone = message.TimezoneOffset;
var timezoneId = Timezone.GetIdFromOffset(timezone);
var timezoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timezoneId);
//現在您可以使用 timezoneInfo 來處理時區轉換
```

## 將電子郵件轉換為 MHT 格式

現在到了核心轉換步驟。我們將使用 Aspose.Email 執行到 MHT 格式的轉換：

```csharp
var mhtOptions = MhtSaveOptions.DefaultMhtml;
var mhtStream = new MemoryStream();
message.Save(mhtStream, mhtOptions);
```

## 儲存 MHT 文件

將電子郵件訊息轉換為 MHT 格式後，是時候將其另存為文件了：

```csharp
using var fileStream = new FileStream("output.mht", FileMode.Create);
mhtStream.Seek(0, SeekOrigin.Begin);
mhtStream.CopyTo(fileStream);
```

## 探索其他客製化

Aspose.Email for .NET 提供了各種自訂選項。您可以探索新增附件、修改訊息屬性等，以滿足您的應用程式的需求。

## 使用 Aspose.Email for .NET 的好處

Aspose.Email for .NET 簡化了複雜的電子郵件相關任務，使開發人員能夠專注於核心功能。它為各種電子郵件格式提供強大的支持，確保準確且有效率的轉換。

## 結論

在本指南中，我們學習如何使用 Aspose.Email for .NET 將電子郵件訊息轉換為 MHT 格式，同時處理時區資訊。透過執行這些步驟並探索進一步的自訂選項，您可以將電子郵件轉換功能無縫整合到您的應用程式中。

## 常見問題解答

### 電子郵件轉換期間如何處理附件？

要處理附件，您可以使用`Attachments`的財產`MailMessage`班級。在轉換過程中迭代附件並根據需要儲存它們。

### 我可以使用 Aspose.Email for .NET 將電子郵件轉換為其他格式嗎？

是的，Aspose.Email for .NET 支援各種格式，包括 MSG、EML、PST 等。您可以調整提供的程式碼範例以適合您所需的輸出格式。

### 時區資訊是否以 MHT 格式儲存？

是的，在轉換過程中會保留時區資訊。透過處理時區偏移並使用適當的`TimeZoneInfo`方法，您可以確保 MHT 檔案中準確的時區表示。

### 在哪裡可以找到有關 Aspose.Email for .NET 的更多文件和更新？

您可以參考文件以獲取全面的資訊和更新：[Aspose.Email for .NET API 參考](https://reference.aspose.com/email/net/)

### 如何下載最新版本的 Aspose.Email for .NET？

您可以從發布頁面下載最新版本：[下載 .NET 版 Aspose.Email](https://releases.aspose.com/email/net/)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
