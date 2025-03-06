---
title: 使用 C# 代码通过 DKIM 签署电子邮件
linktitle: 使用 C# 代码通过 DKIM 签署电子邮件
second_title: Aspose.Email .NET 电子邮件处理 API
description: 了解使用 C# 和 Aspose.Email for .NET 通过 DKIM 保护电子邮件。带有源代码的分步指南。增强电子邮件的信任度和真实性。
weight: 11
url: /zh/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 代码通过 DKIM 签署电子邮件


在当今的数字世界中，确保电子邮件通信的真实性和完整性至关重要。实现此目的的一种方法是使用域名密钥识别邮件 (DKIM) 签名。在本分步指南中，我们将探索如何使用 C# 和强大的 Aspose.Email for .NET 库通过 DKIM 签署电子邮件。

## DKIM简介

### 什么是 DKIM？
DKIM 代表域名密钥识别邮件。它是一种电子邮件身份验证方法，允许发件人对电子邮件进行数字签名，提供验证电子邮件真实性的加密签名。

### 为什么 DKIM 很重要？
DKIM 通过确保传入电子邮件来自合法来源且在传输过程中未被篡改，帮助防止电子邮件欺骗和网络钓鱼攻击。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1.  Aspose.Email for .NET：确保您的项目中安装了 Aspose.Email for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/email/net/).

2. DKIM 私钥：您将需要 DKIM 私钥来签署您的电子邮件。确保您已准备好。 

## 第 1 步：初始化 DKIM 参数

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

在此步骤中，我们初始化 DKIM 参数。我们从文件中加载私钥，指定选择器和域，并列出应包含在 DKIM 签名中的标头。

## 第 2 步：创建并准备电子邮件

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

在这里，我们创建一个实例`MailMessage`类并设置电子邮件的发件人、收件人、主题和正文。

## 第 3 步：签署电子邮件

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

现在，我们使用之前初始化的 DKIM 参数和私钥对电子邮件进行签名。

## 第 4 步：发送签名电子邮件

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    //清理代码（如果有）
}
```
在此步骤中，我们使用 SMTP 客户端发送签名的电子邮件。确保更换`"your.email@gmail.com"`和`"your.password"`使用您的 Gmail 凭据。

## 完整源代码
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

使用 DKIM 签署电子邮件是确保电子邮件通信安全性和真实性的关键一步。借助 Aspose.Email for .NET 和 C#，您可以在电子邮件发送过程中轻松实现 DKIM 签名。

---

## 经常问的问题

### 问题 1：什么是 DKIM？为什么它对于电子邮件安全很重要？

DKIM 代表域名密钥识别邮件，它对于电子邮件安全非常重要，因为它可以验证电子邮件的真实性，防止欺骗和网络钓鱼。

### Q2：如何获取DKIM私钥？

您可以通过电子邮件服务提供商获取 DKIM 私钥，也可以使用加密工具生成私钥。

### Q3：我可以将 Aspose.Email for .NET 与 Gmail 之外的其他电子邮件提供商一起使用吗？

是的，Aspose.Email for .NET 可以与各种电子邮件提供商一起使用，不仅限于 Gmail。

### 问题 4：DKIM 签名中应包含哪些标头？

DKIM 签名中包含的常见标头包括“发件人”、“主题”以及对于电子邮件身份验证很重要的任何其他标头。

### Q5：DKIM 是电子邮件身份验证的唯一方法吗？

不，还有其他方法（如 SPF 和 DMARC）与 DKIM 结合使用以增强电子邮件安全性。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
