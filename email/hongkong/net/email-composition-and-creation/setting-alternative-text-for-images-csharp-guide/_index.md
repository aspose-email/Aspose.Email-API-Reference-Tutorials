---
title: 設定圖像的替代文字 - C# 指南
linktitle: 設定圖像的替代文字 - C# 指南
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解使用 Aspose.Email for .NET 設定電子郵件中圖像的替代文字。使用清晰的替代文字確保可訪問性。包含文檔和程式碼。
type: docs
weight: 15
url: /zh-hant/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

本指南將引導您完成使用 Aspose.Email for .NET 設定電子郵件中圖像的替代文字的過程。替代文字（也稱為“替代文字”）用於在圖像無法顯示的情況下提供圖像的文字描述。 Aspose.Email for .NET 是一個功能強大的程式庫，可讓您處理各種格式的電子郵件和附件。在本指南中，我們將重點介紹使用 C# 設定電子郵件中的圖像的替代文字。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. 安裝了 Visual Studio 或任何相容的 C# 開發環境。
2. Aspose.Email for .NET 函式庫。您可以在 Visual Studio 中使用 NuGet 套件管理器。

## 第 1 步：建立一個新項目

1. 啟動 Visual Studio 並建立一個新的 C# 控制台應用程式專案。

## 步驟2：透過NuGet安裝Aspose.Email

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的項目，然後選擇「管理 NuGet 套件」。
2. 搜尋“Aspose.Email”並安裝最新版本的軟體包。

## 第 3 步：新增 using 語句

```csharp

using Aspose.Email.Mime;
```

## 第 4 步：載入並修改電子郵件訊息

1. 使用以下命令載入電子郵件訊息`MailMessage`班級：

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. 載入電子郵件的 HTML 內容：

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## 第 5 步：新增 AlternativeView 以將替代文字新增至圖像中

將替代文字到圖像的 htmlview 作為 AlternateView 新增到訊息中。 
```csharp
message.AlternateViews.Add(htmlView);
```

## 第 6 步：儲存並發送電子郵件

1. 將修改後的訊息儲存到文件或使用您想要的方法發送：

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## 結論

在本指南中，您學習如何使用 Aspose.Email for .NET 設定電子郵件中圖像的替代文字。透過執行上述步驟，即使無法顯示圖像，您也可以確保您的電子郵件內容仍然可存取且資訊豐富。

## 常問問題

## 如何下載 Aspose.Email 函式庫？

您可以從 Aspose Releases 下載 Aspose.Email 程式庫，或透過 Visual Studio 中的 NuGet 套件管理器安裝它。

### 如何在電子郵件中新增圖像作為連結資源？

若要將圖片新增為電子郵件中的連結資源，您可以使用`LinkedResource`班級。將內容 ID 指派給連結的資源，然後使用 HTML 正文中引用此內容 ID`cid:`方案。有關詳細信息，請參閱[連結資源文檔](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### 在哪裡可以找到有關 Aspose.Email for .NET 的更多文件？

您可以在以下位置找到有關使用 Aspose.Email for .NET 的更多詳細文件、教學和範例：[API參考](https://reference.aspose.com/email/net/).