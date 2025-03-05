---
title: 使用 C# 程式碼要求電子郵件已讀回執
linktitle: 使用 C# 程式碼要求電子郵件已讀回執
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解如何使用 C# 程式碼使用 Aspose.Email for .NET 要求電子郵件閱讀回執，從而增強通訊追蹤。
type: docs
weight: 11
url: /zh-hant/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

在當今的數位時代，透過電子郵件進行交流已成為我們個人和職業生活中不可或缺的一部分。通常，在發送重要電子郵件時，我們希望確保收件人已閱讀並確認我們的訊息。這就是電子郵件閱讀回執發揮作用的地方。在本逐步教學中，我們將引導您完成使用 C# 和 Aspose.Email for .NET 要求電子郵件已讀回執的過程。

## 電子郵件已讀回執簡介

電子郵件閱讀回執，也稱為電子郵件追蹤或回執，允許您在收件者開啟並閱讀您的電子郵件時收到通知。這是一個很有價值的功能，特別是在商業通訊中，因為它提供了訊息傳遞和參與的確認。

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：

- Visual Studio 安裝在您的系統上。
- 下載 Aspose.Email for .NET 程式庫並在您的專案中引用。

## 第 1 步：建立 MailMessage 實例

實現電子郵件閱讀回執的第一步是建立一個實例`MailMessage`班級。此類別代表電子郵件訊息並允許您設定電子郵件的各種屬性。

```csharp
MailMessage message = new MailMessage();
```

## 第 2 步：指定訊息詳細信息

現在，讓我們指定電子郵件的詳細信息，包括寄件者、收件人、HTML 正文和送達通知選項。

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## 步驟3：建立SmtpClient實例

要傳送電子郵件，我們需要建立一個實例`SmtpClient`類，負責發送訊息。

```csharp
SmtpClient client = new SmtpClient();
```

## 步驟 4：設定 SMTP 設定

透過指定主機伺服器、使用者名稱、密碼和連接埠號碼來設定 SMTP 伺服器設定。

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## 第 5 步：發送電子郵件

最後，使用`client.Send`發送電子郵件訊息的方法。如果訊息發送成功，將會顯示「訊息已發送」通知。

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

透過這五個簡單的步驟，您可以在使用 C# 和 Aspose.Email for .NET 發送電子郵件時請求電子郵件已讀回執。此功能為您的電子郵件通訊增加了一層保證，確保您知道何時已閱讀重要訊息重要訊息。

## 完整的原始碼
```csharp
//建立 MailMessage 類別的實例
MailMessage message = new MailMessage();

//指定 From、To、HtmlBody、DeliveryNotificationOptions 字段
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

//建立 SmtpClient 類別的實例
SmtpClient client = new SmtpClient();

//指定您的郵件主機伺服器、使用者名稱、密碼和連接埠號
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	//Client.Send 將發送此訊息
	client.Send(message);
	//僅當訊息發送成功時才顯示“訊息已發送”
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## 結論

在本教學中，我們探討如何使用 C# 和 Aspose.Email for .NET 要求電子郵件已讀回執。電子郵件追蹤是一個強大的工具，可確保您的郵件被預期收件者傳遞和閱讀，特別是在專業環境中。透過遵循此處概述的步驟，您可以在電子郵件應用程式中輕鬆實現此功能。

## 常見問題 (FAQ)

1. ### 電子郵件閱讀回執的目的是什麼？
   電子郵件閱讀回執可確認收件者已開啟並閱讀電子郵件。它們通常用於追蹤重要或時間敏感的訊息。

2. ### 收件者可以停用電子郵件已讀回執嗎？
   是的，電子郵件用戶端通常允許使用者停用發送已讀回執。因此，不能保證您總是會收到它們。

3. ### 電子郵件已讀回執是所有電子郵件用戶端的標準功能嗎？
   不，電子郵件閱讀回執並未獲得普遍支持。它們是否有效取決於電子郵件用戶端和收件者的設定。

4. ### 是否可以追蹤電子郵件在行動裝置上開啟的時間？
   電子郵件追蹤通常基於收件者的電子郵件用戶端和設置，因此它可能會或可能不會在行動裝置上運行，具體取決於各種因素。

5. ### 使用電子郵件閱讀回執時是否需要考慮隱私問題？
   是的，存在與電子郵件追蹤相關的隱私問題。一些接收者可能認為它具有侵入性，因此必須負責任地使用此功能並尊重隱私偏好。