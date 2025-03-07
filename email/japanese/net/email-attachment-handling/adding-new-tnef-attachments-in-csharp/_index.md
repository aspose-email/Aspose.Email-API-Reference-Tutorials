---
title: C# での新しい TNEF 添付ファイルの追加
linktitle: C# での新しい TNEF 添付ファイルの追加
second_title: Aspose.Email .NET 電子メール処理 API
description: Aspose.Email for .NET を使用して C# で新しい TNEF 添付ファイルを追加する方法を学びます。シームレスな統合のためのコード例を含むステップバイステップのガイド。
weight: 12
url: /ja/net/email-attachment-handling/adding-new-tnef-attachments-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# での新しい TNEF 添付ファイルの追加


## .NET 用の TNEF 添付ファイルと Aspose.Email の概要

TNEF (Transport Neutral Encapsulation Format) 添付ファイルは、Microsoft Outlook が電子メール内のリッチ テキストと添付ファイルをパッケージ化するために使用する独自の形式です。 Aspose.Email for .NET は、C# を使用して、TNEF 添付ファイルを含むさまざまな形式の電子メールを操作できる強力なライブラリです。

## 開発環境のセットアップ

コーディングに入る前に、開発環境がセットアップされていることを確認してください。 Visual Studio をインストールし、新しい C# プロジェクトを作成します。

## 新しいプロジェクトの作成

まず、Visual Studio で新しい C# プロジェクトを作成します。適切なプロジェクト名と場所を選択します。

## Aspose.Email for .NET ライブラリの追加

電子メールと TNEF 添付ファイルを操作するには、Aspose.Email for .NET ライブラリをプロジェクトに追加する必要があります。これを行うには、Visual Studio の NuGet パッケージ マネージャーを使用します。 「Aspose.Email」を検索し、適切なパッケージをインストールします。

## TNEF 添付ファイルを含む既存の電子メールのロード

まず、TNEF 添付ファイルを含む既存の電子メールをロードしましょう。電子メール ファイルへのパスを指定する必要があります。

```csharp


// TNEF が添付された電子メールをロードします
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## TNEF 添付ファイルの抽出と変更

電子メールをロードしたら、TNEF 添付ファイルを抽出し、必要に応じて変更できます。

```csharp
//添付ファイルを反復処理する
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        // TNEF 添付ファイルを抽出する
        var tnefAttachment = attachment;

        //TNEF プロパティにアクセスし、必要に応じて変更します
        //tnefAttachment.Properties...
    }
}
```

## 変更された添付ファイルを含む電子メールの保存

TNEF 添付ファイルを変更した後、電子メールをファイルに保存し直すことができます。

```csharp
//変更したメールを保存する
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## 結論

この記事では、Aspose.Email for .NET を使用して C# で TNEF 添付ファイルを操作する方法を説明しました。 TNEF 添付ファイルを含む電子メールをロードし、それらの添付ファイルを抽出して変更し、変更した電子メールを保存する方法を学習しました。

## よくある質問

### Aspose.Email for .NET をインストールするにはどうすればよいですか?

NuGet パッケージ マネージャーを使用して、Aspose.Email for .NET をインストールできます。 「Aspose.Email」を検索して、適切なパッケージをインストールするだけです。

### Aspose.Email for .NET を使用して他の電子メール形式を操作できますか?

はい、Aspose.Email for .NET は、EML、MSG、PST などのさまざまな電子メール形式をサポートしています。

### Aspose.Email を商用プロジェクトに使用できますか?

はい、適切なライセンスを持っていれば、個人プロジェクトと商用プロジェクトの両方で Aspose.Email for .NET を使用できます。

### さらに詳しいドキュメントや例はどこで入手できますか?

より詳細なドキュメントとコード例については、次のサイトを参照してください。[Aspose.Email for .NET ドキュメント](https://reference.aspose.com/email/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
