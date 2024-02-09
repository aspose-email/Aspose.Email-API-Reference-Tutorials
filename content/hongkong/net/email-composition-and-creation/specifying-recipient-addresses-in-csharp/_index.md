---
title: 在 C# 中指定收件者地址
linktitle: 在 C# 中指定收件者地址
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解如何使用 Aspose.Email for .NET 在 C# 中指定收件者位址。有效率地建立、設定和發送電子郵件。
type: docs
weight: 19
url: /zh-hant/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


本指南將引導您完成使用 Aspose.Email for .NET 程式庫在 C# 中指定收件者位址的程序。 Aspose.Email 是一個功能強大的 .NET API，可讓您處理電子郵件和各種與電子郵件相關的任務。在本教程中，我們將介紹如何使用該程式庫將收件者地址新增至電子郵件。

## 先決條件

在開始之前，請確保您具備以下條件：

1. 安裝了 Visual Studio 或任何 C# 開發環境。
2.  Aspose.Email for .NET 函式庫。您可以從[Aspose.Email for .NET 版本](https://releases.aspose.com/email/net/).

## 腳步

請依照下列步驟使用 Aspose.Email for .NET 在 C# 中指定收件者位址：

### 1. 新建一個C#項目

首先在開發環境中建立一個新的 C# 專案。

### 2.加入Aspose.Email的引用

1. 如果尚未安裝，請下載並安裝 Aspose.Email for .NET 程式庫。
2. 開啟您的 C# 專案。
3. 右鍵單擊解決方案資源管理器中的“引用”，然後選擇“新增參考”。
4. 瀏覽並選擇您下載的 Aspose.Email DLL 檔案。

### 3.導入必要的命名空間

在您的 C# 程式碼檔案中，匯入使用 Aspose.Email 類別所需的命名空間：

```csharp
using Aspose.Email;
using Aspose.Email.Mail;
```

### 4. 建立並設定電子郵件

建立一個新實例`MailMessage`類別來表示您的電子郵件訊息。配置電子郵件的寄件者和主題：

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. 新增收件者地址

您可以使用以下命令新增收件者地址`To`, `Cc`， 和`Bcc`的屬性`MailMessage`班級。新增收件者地址的方法如下：

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. 填寫電子郵件訊息

將電子郵件正文和任何其他必要的內容新增到您的電子郵件中：

```csharp
message.Body = "This is the email body.";
```

### 7. 發送電子郵件

若要傳送電子郵件，您可以使用`SmtpClient`Aspose.Email 提供的類別。設定 SMTP 伺服器設定並傳送電子郵件：

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## 常見問題解答

### 如何將多個收件者新增至`To`, `Cc`, or `Bcc` fields?

您可以透過呼叫新增多個收件人`Add`對各自的方法多次`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### 我可以指定收件者姓名及其電子郵件地址嗎？

是的，您可以在新增收件者時指定收件者的姓名和電子郵件地址：

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### 發送郵件時出現異常如何處理？

您可以使用 try-catch 區塊來處理電子郵件傳送過程中可能發生的異常：

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

有關 Aspose.Email for .NET 的詳細資訊和進階功能，請參閱[Aspose API 參考](https://reference.aspose.com/email/net/).

關於使用 Aspose.Email for .NET 在 C# 中指定收件者地址的指南到此結束。您已了解如何建立電子郵件、新增收件者地址以及使用資料庫的功能傳送電子郵件。