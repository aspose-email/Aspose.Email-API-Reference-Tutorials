---
title: 使用 C# 代碼透過 DKIM 簽署電子郵件
linktitle: 使用 C# 代碼透過 DKIM 簽署電子郵件
second_title: Aspose.Email .NET 電子郵件處理 API
description: 了解使用 C# 和 Aspose.Email for .NET 透過 DKIM 保護電子郵件。帶有原始程式碼的分步指南。增強電子郵件的信任度和真實性。
weight: 11
url: /zh-hant/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 代碼透過 DKIM 簽署電子郵件


在當今的數位世界中，確保電子郵件通訊的真實性和完整性至關重要。實現此目的的一種方法是使用網域金鑰識別郵件 (DKIM) 簽署。在本逐步指南中，我們將探索如何使用 C# 和強大的 Aspose.Email for .NET 程式庫透過 DKIM 簽署電子郵件。

## DKIM簡介

### 什麼是 DKIM？
DKIM 代表網域金鑰識別郵件。它是一種電子郵件身份驗證方法，允許寄件者對電子郵件進行數位簽名，提供驗證電子郵件真實性的加密簽名。

### 為什麼 DKIM 很重要？
DKIM 透過確保傳入電子郵件來自合法來源且在傳輸過程中未被篡改，幫助防止電子郵件欺騙和網路釣魚攻擊。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  Aspose.Email for .NET：請確定您的專案中安裝了 Aspose.Email for .NET 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/email/net/).

2. DKIM 私鑰：您將需要 DKIM 私鑰來簽署您的電子郵件。確保您已準備好。 

## 第 1 步：初始化 DKIM 參數

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

在此步驟中，我們初始化 DKIM 參數。我們從檔案載入私鑰，指定選擇器和網域，並列出應包含在 DKIM 簽章中的標頭。

## 步驟 2：建立並準備電子郵件

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

在這裡，我們建立一個實例`MailMessage`類別並設定電子郵件的寄件者、收件者、主題和正文。

## 第 3 步：簽署電子郵件

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

現在，我們使用先前初始化的 DKIM 參數和私鑰對電子郵件進行簽署。

## 步驟 4：發送簽署電子郵件

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    //清理程式碼（如果有）
}
```
在此步驟中，我們使用 SMTP 用戶端傳送已簽署的電子郵件。確保更換`"your.email@gmail.com"`和`"your.password"`使用您的 Gmail 憑證。

## 完整原始碼
```csharp

string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP()+ "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");

MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);

try
{
	SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
	client.Send(signedMsg);                
}
finally
{}
```

## 結論

使用 DKIM 簽署電子郵件是確保電子郵件通訊安全性和真實性的關鍵一步。透過 Aspose.Email for .NET 和 C#，您可以在電子郵件傳送過程中輕鬆實現 DKIM 簽章。

---

## 經常問的問題

### 問題 1：什麼是 DKIM？為什麼它對電子郵件安全很重要？

DKIM 代表網域金鑰識別郵件，它對於電子郵件安全非常重要，因為它可以驗證電子郵件的真實性，防止欺騙和網路釣魚。

### Q2：如何取得DKIM私鑰？

您可以透過電子郵件服務提供者取得 DKIM 私鑰，也可以使用加密工具產生私鑰。

### Q3：我可以將 Aspose.Email for .NET 與 Gmail 以外的其他電子郵件提供者一起使用嗎？

是的，Aspose.Email for .NET 可以與各種電子郵件提供者一起使用，不僅限於 Gmail。

### 問題 4：DKIM 簽章應包含哪些標頭？

DKIM 簽名中包含的常見標頭包括「寄件者」、「主題」以及任何其他對於電子郵件身份驗證很重要的標頭。

### Q5：DKIM 是電子郵件驗證的唯一方法嗎？

不，還有其他方法（如 SPF 和 DMARC）與 DKIM 結合使用以增強電子郵件安全性。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
