---
"description": "Aspose.Email for .NET を使用して、C# で新しい TNEF 添付ファイルを追加する方法を学びましょう。シームレスな統合を実現するコード例を交えたステップバイステップのガイドです。"
"linktitle": "C# で新しい TNEF 添付ファイルを追加する"
"second_title": "Aspose.Email .NET メール処理 API"
"title": "C# で新しい TNEF 添付ファイルを追加する"
"url": "/ja/net/email-attachment-handling/adding-new-tnef-attachments-in-csharp/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# C# で新しい TNEF 添付ファイルを追加する


## TNEF 添付ファイルと Aspose.Email for .NET の概要

TNEF（Transport Neutral Encapsulation Format）添付ファイルは、Microsoft Outlook がメール内のリッチテキストや添付ファイルをパッケージ化するために使用する独自の形式です。Aspose.Email for .NET は、C# を使用して TNEF 添付ファイルを含む様々な形式のメールを操作できる強力なライブラリです。

## 開発環境の設定

コーディングを始める前に、開発環境がセットアップされていることを確認してください。Visual Studioをインストールし、新しいC#プロジェクトを作成してください。

## 新しいプロジェクトの作成

まず、Visual Studio で新しい C# プロジェクトを作成します。適切なプロジェクト名と場所を選択します。

## Aspose.Email for .NET ライブラリの追加

メールとTNEF添付ファイルを扱うには、Aspose.Email for .NETライブラリをプロジェクトに追加する必要があります。Visual StudioのNuGetパッケージマネージャーを使用して追加できます。「Aspose.Email」を検索し、適切なパッケージをインストールしてください。

## TNEF 添付ファイル付きの既存のメールを読み込む

まず、TNEF 添付ファイルを含む既存のメールを読み込みます。メールファイルへのパスを指定する必要があります。

```csharp


// TNEF添付ファイル付きのメールを読み込む
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## TNEF添付ファイルの抽出と変更

電子メールを読み込んだら、TNEF 添付ファイルを抽出し、必要に応じて変更できます。

```csharp
// 添付ファイルを反復処理する
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        // TNEF添付ファイルの抽出
        var tnefAttachment = attachment;

        // TNEFプロパティにアクセスし、必要に応じて変更する
        // tnefAttachment.Properties...
    }
}
```

## 変更した添付ファイルを含むメールを保存する

TNEF 添付ファイルを変更した後、電子メールをファイルに保存し直すことができます。

```csharp
// 変更したメールを保存する
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## 結論

この記事では、Aspose.Email for .NET を使用して C# で TNEF 添付ファイルを操作する方法について説明しました。TNEF 添付ファイル付きのメールを読み込み、添付ファイルを抽出して変更し、変更後のメールを保存する方法を学習しました。

## よくある質問

### Aspose.Email for .NET をインストールするにはどうすればよいですか?

Aspose.Email for .NETはNuGetパッケージマネージャーを使ってインストールできます。「Aspose.Email」を検索し、適切なパッケージをインストールしてください。

### Aspose.Email for .NET を使用して他の電子メール形式を扱うことはできますか?

はい、Aspose.Email for .NET は、EML、MSG、PST など、さまざまな電子メール形式をサポートしています。

### Aspose.Email を商用プロジェクトに使用できますか?

はい、適切なライセンスをお持ちであれば、個人プロジェクトと商用プロジェクトの両方で Aspose.Email for .NET を使用できます。

### さらに詳しいドキュメントや例はどこで見つかりますか?

より詳細なドキュメントとコード例については、 [Aspose.Email for .NET ドキュメント](https://reference。aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}