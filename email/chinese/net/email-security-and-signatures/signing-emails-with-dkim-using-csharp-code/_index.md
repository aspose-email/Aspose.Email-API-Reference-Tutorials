---
"description": "学习使用 C# 和 Aspose.Email for .NET 的 DKIM 保护电子邮件安全。包含源代码的分步指南。增强电子邮件的信任度和真实性。"
"linktitle": "使用 C# 代码通过 DKIM 签名电子邮件"
"second_title": "Aspose.Email .NET 电子邮件处理 API"
"title": "使用 C# 代码通过 DKIM 签名电子邮件"
"url": "/zh/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 代码通过 DKIM 签名电子邮件


在当今的数字世界中，确保电子邮件通信的真实性和完整性至关重要。实现此目标的方法之一是使用域名密钥识别邮件 (DKIM) 签名。在本分步指南中，我们将探索如何使用 C# 和强大的 Aspose.Email for .NET 库使用 DKIM 签名电子邮件。

## DKIM简介

### 什么是 DKIM？
DKIM 代表域名密钥识别邮件 (DomainKeys Identified Mail)。它是一种电子邮件身份验证方法，允许发件人对电子邮件进行数字签名，从而提供用于验证电子邮件真实性的加密签名。

### DKIM 为何重要？
DKIM 通过确保传入的电子邮件来自合法来源且在传输过程中未被篡改，帮助防止电子邮件欺骗和网络钓鱼攻击。

## 先决条件

在开始之前，请确保您已满足以下先决条件：

1. Aspose.Email for .NET：确保您的项目中已安装 Aspose.Email for .NET 库。您可以从以下链接下载： [这里](https://releases。aspose.com/email/net/).

2. DKIM 私钥：您需要一个 DKIM 私钥来签名您的电子邮件。请确保您已准备好。 

## 步骤1：初始化DKIM参数

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

在此步骤中，我们初始化 DKIM 参数。我们从文件加载私钥，指定选择器和域，并列出应包含在 DKIM 签名中的标头。

## 第 2 步：创建并准备电子邮件

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

在这里，我们创建一个 `MailMessage` 类并设置电子邮件的发件人、收件人、主题和正文。

## 步骤 3：签署电子邮件

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

现在，我们使用之前初始化的 DKIM 参数和私钥对电子邮件进行签名。

## 步骤 4：发送签名电子邮件

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // 清理代码（如果有）
}
```
在此步骤中，我们使用 SMTP 客户端发送签名的电子邮件。请确保替换 `"your.email@gmail.com"` 和 `"your.password"` 使用您的 Gmail 凭据。

## 完整的源代码
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

## 结论

使用 DKIM 签名电子邮件是确保电子邮件通信安全性和真实性的关键步骤。借助 Aspose.Email for .NET 和 C#，您可以轻松地在电子邮件发送过程中实现 DKIM 签名。

---

## 常见问题

### 问题 1：什么是 DKIM，为什么它对电子邮件安全很重要？

DKIM 代表域名密钥识别邮件，它对于电子邮件安全非常重要，因为它可以验证电子邮件的真实性，防止欺骗和网络钓鱼。

### 问题2：如何获取DKIM私钥？

您可以通过电子邮件服务提供商获取 DKIM 私钥，也可以使用加密工具生成 DKIM 私钥。

### 问题 3：除了 Gmail 之外，我还可以将 Aspose.Email for .NET 与其他电子邮件提供商一起使用吗？

是的，Aspose.Email for .NET 可以与各种电子邮件提供商一起使用，而不仅限于 Gmail。

### 问题 4：我应该在 DKIM 签名中包含哪些标头？

DKIM 签名中包含的常见标头有“发件人”、“主题”以及任何其他对电子邮件身份验证很重要的标头。

### 问题5：DKIM 是电子邮件身份验证的唯一方法吗？

不，还有其他方法，如 SPF 和 DMARC，可与 DKIM 结合使用以增强电子邮件安全性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}