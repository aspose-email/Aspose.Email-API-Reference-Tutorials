---
title: 將 HTML 正文新增至電子郵件 - C# 範例
linktitle: 將 HTML 正文新增至電子郵件 - C# 範例
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解如何在 Aspose.Email for .NET 中使用 HTML 增強電子郵件內容。包含 C# 範例的逐步指南。提升您的電子郵件溝通！
weight: 18
url: /zh-hant/net/email-composition-and-creation/adding-html-body-to-emails-csharp-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 HTML 正文新增至電子郵件 - C# 範例


電子郵件通訊已成為現代商業和個人互動不可或缺的一部分。雖然純文字電子郵件可以達到其目的，但將 HTML 內容合併到電子郵件中可以大大增強其視覺吸引力和功能。在本文中，我們將為您提供全面的逐步指南，並附有 C# 原始程式碼範例，介紹如何使用 Aspose.Email for .NET 將 HTML 正文新增至電子郵件中。

## Aspose.Email for .NET 簡介

Aspose.Email for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中使用電子郵件和相關功能。無論您是建立電子郵件用戶端、自動化電子郵件相關任務，還是自訂電子郵件模板，Aspose.Email 都能簡化流程並提供豐富的功能。

## 設定您的開發環境

在我們深入編碼之前，請確保您已將 Aspose.Email for .NET 庫整合到您的專案中。您可以透過 NuGet 套件管理器執行此操作。

## 建立新電子郵件

首先，建立一個新實例`MailMessage`班級。此類別可讓您定義電子郵件的各種屬性，例如寄件者、收件者、主題和附件。

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
message.Subject = "Hello from Aspose.Email!";
```

## 將 HTML 正文新增至電子郵件

現在是令人興奮的部分 - 將 HTML 正文新增到您的電子郵件中。您可以利用`HtmlBody`的財產`MailMessage`類別來設定電子郵件的 HTML 內容。

```csharp
string htmlContent = "<html><body><h1>Welcome to our Newsletter!</h1><p>This is a sample HTML email body.</p></body></html>";
message.HtmlBody = htmlContent;
```

## 在 HTML 正文中嵌入圖像

為了讓您的電子郵件在視覺上更具吸引力，您可能需要在 HTML 正文中嵌入圖像。您可以透過使用具有 Base64 編碼圖像資料的 HTML 標籤引用圖像或提供圖像來源的 URL 來實現此目的。

```csharp
string htmlContentWithImage = "<html><body><h1>Check out our New Product!</h1><img src='data:image/jpeg;base64,/9j...'></body></html>";
message.HtmlBody = htmlContentWithImage;
```

## 傳送電子郵件

一旦您完美地製作了電子郵件，就可以發送了。使用您首選的電子郵件伺服器的設定或第三方服務來傳送電子郵件。

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");
client.Send(message);
```

## 處理例外

請記住，網路問題和伺服器問題可能會導致發送電子郵件時出現異常。確保實施適當的異常處理，以確保流暢的使用者體驗。

## 結論

使用 Aspose.Email for .NET 將 HTML 內容合併到您的電子郵件中，為製作具有視覺吸引力的互動式電子郵件開闢了一個可能性的世界。從時事通訊到促銷活動，您現在可以以前所未有的方式與收件人互動。

## 常見問題解答

### 我可以在 Windows 表單和 ASP.NET 應用程式中使用 Aspose.Email for .NET 嗎？
   是的，Aspose.Email for .NET 用途廣泛，可用於各種類型的 .NET 應用程式。

### Aspose.Email for .NET 支援電子郵件附件嗎？
   絕對地！您可以使用該程式庫輕鬆地將文件附加到電子郵件中。

### 是否可以使用 Aspose.Email for .NET 非同步傳送電子郵件？
   是的，該庫提供了發送電子郵件的非同步方法，這可以提高某些場景下的效能。

### 我可以自訂 HTML 電子郵件中嵌入圖像的外觀嗎？
   當然！您可以使用 HTML 和 CSS 控制嵌入圖片的大小、對齊方式和其他屬性。

### 在哪裡可以找到 Aspose.Email for .NET 的綜合文件？
   您可以存取 Aspose 文件：[https://reference.aspose.com/email/net/](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
