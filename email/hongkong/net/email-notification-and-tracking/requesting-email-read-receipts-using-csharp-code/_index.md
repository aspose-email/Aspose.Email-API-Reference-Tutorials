---
"description": "了解如何使用 C# 程式碼透過 Aspose.Email for .NET 要求電子郵件閱讀回執，從而增強通訊追蹤。"
"linktitle": "使用 C# 程式碼請求電子郵件閱讀回執"
"second_title": "Aspose.Email .NET 電子郵件處理 API"
"title": "使用 C# 程式碼請求電子郵件閱讀回執"
"url": "/zh-hant/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 程式碼請求電子郵件閱讀回執


在當今的數位時代，透過電子郵件進行交流已成為我們個人和職業生活中不可或缺的一部分。通常，在發送重要電子郵件時，我們希望確保收件人已閱讀並確認收到我們的訊息。這時，電子郵件已讀回執就派上用場了。在本逐步教學中，我們將引導您使用 C# 和 Aspose.Email for .NET 要求電子郵件已讀回執的過程。

## 電子郵件已讀回執簡介

電子郵件已讀回執，也稱為電子郵件追蹤或回執，允許您在收件者開啟並閱讀您的電子郵件時收到通知。這項功能非常有用，尤其是在商務溝通中，因為它可以確認郵件的送達和參與度。

## 先決條件

在深入研究程式碼之前，請確保您已滿足以下先決條件：

- 您的系統上安裝了 Visual Studio。
- 已下載 Aspose.Email for .NET 程式庫並在您的專案中引用。

## 步驟 1：建立 MailMessage 實例

實現電子郵件閱讀回執的第一步是創建一個 `MailMessage` 類。此類別代表一封電子郵件訊息，並允許您設定電子郵件的各種屬性。

```csharp
MailMessage message = new MailMessage();
```

## 步驟 2：指定訊息詳細信息

現在，讓我們指定電子郵件訊息的詳細信息，包括寄件者、收件人、HTML 正文和傳遞通知選項。

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## 步驟3：建立SmtpClient實例

要發送電子郵件，我們需要建立一個 `SmtpClient` 類，負責發送訊息。

```csharp
SmtpClient client = new SmtpClient();
```

## 步驟4：設定SMTP設定

透過指定主機伺服器、使用者名稱、密碼和連接埠號碼來設定您的 SMTP 伺服器設定。

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## 步驟5：發送電子郵件

最後，使用 `client.Send` 方法發送電子郵件訊息。如果訊息發送成功，則會顯示「訊息已發送」通知。

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

透過這五個簡單的步驟，您可以在使用 C# 和 Aspose.Email for .NET 發送電子郵件時請求電子郵件已讀回執。此功能為您的電子郵件通訊增添了一層保障，確保您知道何時重要郵件被閱讀。

## 完整的原始碼
```csharp
// 建立 MailMessage 類別的實例
MailMessage message = new MailMessage();

// 指定寄件者、收件人、HtmlBody、DeliveryNotificationOptions 字段
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// 建立 SmtpClient 類別的實例
SmtpClient client = new SmtpClient();

// 指定您的郵件主機伺服器、使用者名稱、密碼和連接埠號
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send 將發送此訊息
	client.Send(message);
	// 僅當訊息發送成功時才顯示“訊息已發送”
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## 結論

在本教學中，我們探討如何使用 C# 和 Aspose.Email for .NET 要求電子郵件已讀回執。電子郵件追蹤是一個強大的工具，可以確保您的郵件送達並被目標收件者閱讀，尤其是在專業環境中。按照此處概述的步驟，您可以輕鬆地在您的電子郵件應用程式中實現此功能。

## 常見問題 (FAQ)

1. ### 電子郵件已讀回執的用途是什麼？
   電子郵件已讀回執用於確認收件者已開啟並閱讀電子郵件。它們通常用於追蹤重要或時效性較強的訊息。

2. ### 收件者可以停用電子郵件已讀回執嗎？
   是的，電子郵件用戶端通常允許使用者停用發送已讀回執的功能。因此，無法保證您始終都能收到已讀回執。

3. ### 電子郵件已讀回執是所有電子郵件用戶端的標準功能嗎？
   不，電子郵件已讀回執並非普遍支持。其是否有效取決於電子郵件用戶端和收件者的設定。

4. ### 是否可以追蹤電子郵件在行動裝置上開啟的時間？
   電子郵件追蹤通常基於收件者的電子郵件用戶端和設置，因此它可能在行動裝置上運行，也可能不運行，這取決於各種因素。

5. ### 使用電子郵件閱讀回執時是否需要考慮隱私問題？
   是的，電子郵件追蹤存在隱私問題。有些收件者可能會認為這屬於侵犯隱私的行為，因此請務必負責任地使用此功能並尊重他們的隱私偏好。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}