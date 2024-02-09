---
title: 使用 C# 程式碼追蹤電子郵件文件轉換進度
linktitle: 使用 C# 程式碼追蹤電子郵件文件轉換進度
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解如何使用 Aspose.Email for .NET 實作電子郵件通知和追蹤。帶有程式碼範例的分步指南。立即增強您的電子郵件溝通！
type: docs
weight: 12
url: /zh-hant/net/email-notification-and-tracking/tracking-email-document-conversion-progress-with-csharp-code/
---

在當今的數位時代，電子郵件通訊在個人和專業領域都發揮著至關重要的作用。作為一名程式設計師，您可能遇到過以程式設計方式處理和操作電子郵件的需要。一項常見任務是追蹤電子郵件文件轉換的進度，在本文中，我們將使用 C# 和 Aspose.Email for .NET 逐步指導您完成該過程。

## Aspose.Email for .NET 簡介

在深入研究程式碼之前，我們先簡單介紹一下 Aspose.Email for .NET。這個強大的程式庫提供了處理電子郵件的廣泛功能，包括閱讀、編寫和轉換各種格式的電子郵件。在我們的例子中，我們將專注於電子郵件文件轉換。

## 設定您的環境

首先，您需要設定開發環境。確保您具備以下先決條件：

- 已安裝 Aspose.Email for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/email/net/).

現在，讓我們進入程式碼。我們將建立一個使用提供的 C# 原始碼追蹤電子郵件文件轉換進度的逐步指南。

## 第 1 步：載入電子郵件訊息

我們首先從文件中載入電子郵件。確保更換`"Your Document Directory"`與文檔目錄的實際路徑。

```csharp
string dataDir = "Your Document Directory";
var fileName = dataDir + "test.eml";
MailMessage msg = MailMessage.Load(fileName);
```

## 第 2 步：定義自訂進度處理程序

在此步驟中，我們設定一個自訂進度處理程序來監視轉換進度。這`ShowEmlConversionProgress`方法將在轉換過程中被呼叫以提供有關進度的資訊。

```csharp
private static void ShowEmlConversionProgress(ProgressEventHandlerInfo info)
{
    int total;
    int saved;
    switch (info.EventType)
    {
        case ProgressEventType.MimeStructureCreated:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("MimeStructureCreated - TotalMimePartCount: " + total);
            Console.WriteLine("MimeStructureCreated - SavedMimePartCount: " + saved);
            break;
        case ProgressEventType.MimePartSaved:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("MimePartSaved - TotalMimePartCount: " + total);
            Console.WriteLine("MimePartSaved - SavedMimePartCount: " + saved);
            break;
        case ProgressEventType.SavedToStream:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("SavedToStream - TotalMimePartCount: " + total);
            Console.WriteLine("SavedToStream - SavedMimePartCount: " + saved);
            break;
    }
}
```

## 第 3 步：儲存電子郵件並追蹤進度

現在，讓我們在追蹤進度的同時儲存電子郵件。我們使用`EmlSaveOptions`具有自訂進度處理程序的類別。

```csharp
MemoryStream ms = new MemoryStream();
EmlSaveOptions opt = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
opt.CustomProgressHandler = new ConversionProgressEventHandler(ShowEmlConversionProgress);
msg.Save(ms, opt);
```

## 結論

恭喜！您已使用 C# 和 Aspose.Email for .NET 成功實現了電子郵件文件轉換進度追蹤。在應用程式中處理大量電子郵件和文件轉換時，此功能非常有價值。

有關更多資訊和詳細文檔，請訪問[Aspose.Email for .NET API 參考](https://reference.aspose.com/email/net/).


## 常見問題解答

### 什麼是 .NET 的 Aspose.Email？
Aspose.Email for .NET 是一個功能強大的程式庫，用於在 .NET 應用程式中處理電子郵件訊息。它提供閱讀、撰寫和轉換電子郵件的功能。

### 我可以使用 Aspose.Email for .NET 追蹤電子郵件文件轉換進度嗎？
是的，您可以使用自訂進度處理程序來追蹤電子郵件文件轉換進度，如本文所示。

### Aspose.Email for .NET 是否可以輕鬆整合到我的 C# 專案中？
是的，Aspose.Email for .NET 很容易整合到 C# 專案中。您可以從網站下載並安裝該庫。

### 還有其他函式庫可以在 C# 中處理電子郵件嗎？
是的，還有其他函式庫，但 Aspose.Email for .NET 以其全面的功能和易用性而聞名。

### 在哪裡可以找到有關 Aspose.Email for .NET 的更多教學和範例？
您可以探索[Aspose.Email for .NET API 參考](https://reference.aspose.com/email/net/)有關教程、範例和詳細文件。

現在，您已做好充分準備，可以自信地在 C# 應用程式中處理電子郵件文件轉換進度。快樂編碼！