---
title: C# で受信者アドレスを指定する
linktitle: C# で受信者アドレスを指定する
second_title: Aspose.Email .NET 電子メール処理 API
description: Aspose.Email for .NET を使用して C# で受信者アドレスを指定する方法を学習します。電子メールを効率的に作成、構成、送信します。
weight: 19
url: /ja/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で受信者アドレスを指定する



このガイドでは、Aspose.Email for .NET ライブラリを使用して C# で受信者アドレスを指定するプロセスについて説明します。 Aspose.Email は、電子メール メッセージや電子メール関連のさまざまなタスクを操作できる強力な .NET API です。このチュートリアルでは、ライブラリを使用して電子メール メッセージに受信者アドレスを追加する方法について説明します。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Visual Studio または任意の C# 開発環境がインストールされていること。
2.  .NET ライブラリ用の Aspose.Email。から入手できます。[Aspose.Email for .NET リリース](https://releases.aspose.com/email/net/).

## ステップ

Aspose.Email for .NET を使用して C# で受信者アドレスを指定するには、次の手順に従います。

### 1. 新しい C# プロジェクトを作成する

まず、開発環境で新しい C# プロジェクトを作成します。

### 2. Aspose.Email への参照を追加します。

1. まだダウンロードしていない場合は、Aspose.Email for .NET ライブラリをダウンロードしてインストールします。
2. C# プロジェクトを開きます。
3. ソリューション エクスプローラーで [参照] を右クリックし、[参照の追加] を選択します。
4. ダウンロードした Aspose.Email DLL ファイルを参照して選択します。

### 3. 必要な名前空間をインポートする

C# コード ファイルで、Aspose.Email クラスを使用するために必要な名前空間をインポートします。

```csharp
using Aspose.Email;

```

### 4. 電子メールメッセージを作成および構成する

の新しいインスタンスを作成します。`MailMessage`電子メール メッセージを表すクラス。電子メールの送信者と件名を設定します。

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. 受信者アドレスを追加する

受信者アドレスを追加するには、`To`, `Cc`、 そして`Bcc`のプロパティ`MailMessage`クラス。受信者アドレスを追加する方法は次のとおりです。

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. 電子メールメッセージに記入します

電子メールの本文とその他の必要なコンテンツを電子メール メッセージに追加します。

```csharp
message.Body = "This is the email body.";
```

### 7.メールを送信する

電子メールを送信するには、`SmtpClient` Aspose.Email によって提供されるクラス。 SMTP サーバー設定を構成し、電子メールを送信します。

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## よくある質問

### 複数の受信者を追加するにはどうすればよいですか?`To`, `Cc`, or `Bcc` fields?

を呼び出して複数の受信者を追加できます。`Add`メソッドをそれぞれに対して複数回実行します`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### 電子メール アドレスとともに受信者名を指定できますか?

はい、受信者を追加するときに受信者の名前と電子メール アドレスの両方を指定できます。

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### 電子メールの送信時に例外を処理するにはどうすればよいですか?

try-catch ブロックを使用して、電子メールの送信中に発生する可能性のある例外を処理できます。

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

 Aspose.Email for .NET の詳細および高度な機能については、「[Aspose API リファレンス](https://reference.aspose.com/email/net/).

これで、Aspose.Email for .NET を使用して C# で受信者アドレスを指定するガイドは終了です。ライブラリの機能を使用して電子メール メッセージを作成し、受信者アドレスを追加し、電子メールを送信する方法を学習しました。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
