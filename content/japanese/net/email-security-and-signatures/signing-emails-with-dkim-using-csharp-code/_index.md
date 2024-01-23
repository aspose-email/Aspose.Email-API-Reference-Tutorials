---
title: C# コードを使用した DKIM での電子メールの署名
linktitle: C# コードを使用した DKIM での電子メールの署名
second_title: Aspose.Email .NET 電子メール処理 API
description: C# と Aspose.Email for .NET を使用して DKIM で電子メールを保護する方法を学びます。ソースコード付きのステップバイステップガイド。電子メールの信頼性と信頼性を強化します。
type: docs
weight: 11
url: /ja/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/
---

今日のデジタル世界では、電子メール通信の信頼性と整合性を確保することが最も重要です。これを実現する 1 つの方法は、DomainKeys Identified Mail (DKIM) 署名を使用することです。このステップバイステップ ガイドでは、C# と強力な Aspose.Email for .NET ライブラリを使用して DKIM で電子メールに署名する方法を説明します。

## DKIM の概要

### DKIMとは何ですか?
DKIM は DomainKeys Identified Mail の略です。これは、送信者が電子メールにデジタル署名し、電子メールの信頼性を検証する暗号署名を提供できる電子メール認証方法です。

### DKIM が重要なのはなぜですか?
DKIM は、受信電子メールが正当な送信元からのものであり、転送中に改ざんされていないことを保証することで、電子メールのなりすましやフィッシング攻撃の防止に役立ちます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Email for .NET: Aspose.Email for .NET ライブラリがプロジェクトにインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/email/net/).

2. DKIM 秘密キー: メールに署名するには DKIM 秘密キーが必要です。必ずご用意ください。 

## ステップ 1: DKIM パラメータを初期化する

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

このステップでは、DKIM パラメータを初期化します。ファイルから秘密キーをロードし、セレクターとドメインを指定して、DKIM 署名に含めるヘッダーをリストします。

## ステップ 2: 電子メールの作成と準備

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

ここでは、`MailMessage`クラスを選択し、電子メールの送信者、受信者、件名、本文を設定します。

## ステップ 3: 電子メールに署名する

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

次に、前に初期化した DKIM パラメータと秘密キーを使用して電子メールに署名します。

## ステップ 4: 署名済みメールを送信する

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    //クリーンアップ コード (存在する場合)
}
```
このステップでは、SMTP クライアントを使用して署名付き電子メールを送信します。必ず交換してください`"your.email@gmail.com"`そして`"your.password"`Gmail の認証情報を使用して。

## 完全なソースコード
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

DKIM を使用して電子メールに署名することは、電子メール通信のセキュリティと信頼性を確保するための重要な手順です。 Aspose.Email for .NET および C# を利用すると、電子メール送信プロセスに DKIM 署名を簡単に実装できます。

---

## よくある質問

### Q1: DKIM とは何ですか?また、電子メールのセキュリティにとって重要なのはなぜですか?

DKIM は DomainKeys Identified Mail の略で、電子メール メッセージの信頼性を検証し、なりすましやフィッシングを防ぐため、電子メール セキュリティにとって重要です。

### Q2: DKIM 秘密キーを取得するにはどうすればよいですか?

DKIM 秘密キーは、電子メール サービス プロバイダーを通じて取得するか、暗号化ツールを使用して生成することによって取得できます。

### Q3: Aspose.Email for .NET を Gmail 以外の電子メール プロバイダーで使用できますか?

はい、Aspose.Email for .NET は、Gmail に限定されず、さまざまな電子メール プロバイダーで使用できます。

### Q4: DKIM 署名にはどのヘッダーを含める必要がありますか?

DKIM 署名に含める一般的なヘッダーは、「From」、「Subject」、および電子メール認証に重要なその他のヘッダーです。

### Q5: 電子メール認証の方法は DKIM だけですか?

いいえ、電子メールのセキュリティを強化するために DKIM と組み合わせて使用される SPF や DMARC などの他の方法もあります。