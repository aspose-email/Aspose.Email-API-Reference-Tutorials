---
"description": "C#とAspose.Email for .NETを使用して、DKIMでメールを保護する方法を学びましょう。ソースコード付きのステップバイステップガイドで、メールの信頼性と真正性を高めます。"
"linktitle": "C# コードを使用して DKIM でメールに署名する"
"second_title": "Aspose.Email .NET メール処理 API"
"title": "C# コードを使用して DKIM でメールに署名する"
"url": "/ja/net/email-security-and-signatures/signing-emails-with-dkim-using-csharp-code/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# C# コードを使用して DKIM でメールに署名する


今日のデジタル世界において、電子メール通信の真正性と整合性を確保することは極めて重要です。これを実現する方法の一つとして、DomainKeys Identified Mail（DKIM）署名の利用が挙げられます。このステップバイステップガイドでは、C#と強力なAspose.Email for .NETライブラリを用いて、DKIMで電子メールに署名する方法を解説します。

## DKIMの概要

### DKIMとは何ですか？
DKIMはDomainKeys Identified Mail（ドメインキー識別メール）の略です。送信者がメールにデジタル署名し、メールの真正性を検証する暗号署名を提供するメール認証方式です。

### DKIM が重要な理由は何ですか?
DKIM は、受信メールが正当なソースからのものであり、送信中に改ざんされていないことを確認することで、メールのなりすましやフィッシング攻撃を防ぐのに役立ちます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Email for .NET: プロジェクトにAspose.Email for .NETライブラリがインストールされていることを確認してください。ダウンロードはこちらから可能です。 [ここ](https://releases。aspose.com/email/net/).

2. DKIM秘密鍵：メールに署名するにはDKIM秘密鍵が必要です。必ずご用意ください。 

## ステップ1: DKIMパラメータを初期化する

```csharp
string privateKeyFile = Path.Combine(RunExamples.GetDataDir_SMTP().Replace("_Send", string.Empty), RunExamples.GetDataDir_SMTP() + "key2.pem");

RSACryptoServiceProvider rsa = PemReader.GetPrivateKey(privateKeyFile);
DKIMSignatureInfo signInfo = new DKIMSignatureInfo("test", "yandex.ru");
signInfo.Headers.Add("From");
signInfo.Headers.Add("Subject");
```

このステップでは、DKIMパラメータを初期化します。ファイルから秘密鍵を読み込み、セレクタとドメインを指定し、DKIM署名に含めるヘッダーをリストします。

## ステップ2: メールを作成して準備する

```csharp
MailMessage mailMessage = new MailMessage("useremail@gmail.com", "test@gmail.com");
mailMessage.Subject = "Signed DKIM message text body";
mailMessage.Body = "This is a text body signed DKIM message";
```

ここでは、 `MailMessage` クラスを作成し、メールの送信者、受信者、件名、本文を設定します。

## ステップ3: メールに署名する

```csharp
MailMessage signedMsg = mailMessage.DKIMSign(rsa, signInfo);
```

ここで、先ほど初期化した DKIM パラメータと秘密キーを使用して電子メールに署名します。

## ステップ4: 署名されたメールを送信する

```csharp
try
{
    SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "your.email@gmail.com", "your.password");
    client.Send(signedMsg);                
}
finally
{
    // クリーンアップコード（ある場合）
}
```
このステップでは、SMTPクライアントを使用して署名されたメールを送信します。 `"your.email@gmail.com"` そして `"your.password"` Gmail の認証情報を入力します。

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

DKIMによるメール署名は、メール通信のセキュリティと信頼性を確保するための重要なステップです。Aspose.Email for .NET and C#を使えば、メール送信プロセスにDKIM署名を簡単に実装できます。

---

## よくある質問

### Q1: DKIM とは何ですか? また、電子メールのセキュリティにとってなぜ重要ですか?

DKIM は DomainKeys Identified Mail の略で、電子メール メッセージの信頼性を検証し、なりすましやフィッシングを防止するため、電子メールのセキュリティにとって重要です。

### Q2: DKIM 秘密鍵を取得するにはどうすればよいですか?

DKIM 秘密キーは、電子メール サービス プロバイダーを通じて取得するか、暗号化ツールを使用して生成することができます。

### Q3: Aspose.Email for .NET を Gmail 以外のメール プロバイダーでも使用できますか?

はい、Aspose.Email for .NET は Gmail に限らず、さまざまな電子メール プロバイダーで使用できます。

### Q4: DKIM 署名にはどのようなヘッダーを含める必要がありますか?

DKIM 署名に含める一般的なヘッダーは、「From」、「Subject」、および電子メール認証に重要なその他のヘッダーです。

### Q5: 電子メール認証の方法は DKIM のみですか?

いいえ、電子メールのセキュリティを強化するために DKIM と組み合わせて使用される SPF や DMARC などの他の方法もあります。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}