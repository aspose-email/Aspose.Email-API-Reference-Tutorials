---
title: 画像の代替テキストを設定する - C# ガイド
linktitle: 画像の代替テキストを設定する - C# ガイド
second_title: Aspose.Email .NET 電子メール処理 API
description: Aspose.Email for .NET を使用して電子メール内の画像の代替テキストを設定する方法を学びます。明確な代替テキストでアクセシビリティを確保します。ドキュメントとコードが含まれています。
type: docs
weight: 15
url: /ja/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

このガイドでは、Aspose.Email for .NET を使用して電子メール内の画像の代替テキストを設定するプロセスについて説明します。 「代替テキスト」とも呼ばれる代替テキストは、画像を表示できない場合に画像の説明をテキストで提供するために使用されます。 Aspose.Email for .NET は、さまざまな形式の電子メールや添付ファイルを処理できる強力なライブラリです。このガイドでは、C# を使用して電子メール メッセージ内の画像の代替テキストを設定することに焦点を当てます。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

1. Visual Studio または互換性のある C# 開発環境がインストールされていること。
2. .NET ライブラリ用の Aspose.Email。 Visual Studio で NuGet パッケージ マネージャーを使用できます。

## ステップ 1: 新しいプロジェクトを作成する

1. Visual Studio を起動し、新しい C# コンソール アプリケーション プロジェクトを作成します。

## ステップ 2: NuGet 経由で Aspose.Email をインストールする

1. ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択します。
2. 「Aspose.Email」を検索し、最新バージョンのパッケージをインストールします。

## ステップ 3: using ステートメントを追加する

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## ステップ 4: 電子メール メッセージをロードして変更する

1. を使用して電子メール メッセージをロードします。`MailMessage`クラス：

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. 電子メール メッセージの HTML コンテンツをロードします。

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## ステップ 5: 画像に代替テキスト用の AlternativeView を追加する

画像への代替テキストの htmlview を AlternateView としてメッセージに追加します。 
```csharp
message.AlternateViews.Add(htmlView);
```

## ステップ 6: 電子メールを保存して送信する

1. 変更したメッセージをファイルに保存するか、希望の方法を使用して送信します。

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## 結論

このガイドでは、Aspose.Email for .NET を使用して電子メール メッセージ内の画像の代替テキストを設定する方法を学習しました。上記の手順に従うことで、画像が表示できない場合でも、電子メールのコンテンツにアクセスでき、有益な情報を得ることができます。

## よくある質問

## Aspose.Email ライブラリをダウンロードするにはどうすればよいですか?

Aspose.Email ライブラリは、Aspose リリースからダウンロードするか、Visual Studio の NuGet パッケージ マネージャーを介してインストールできます。

### 画像をリンクされたリソースとして電子メールに追加するにはどうすればよいですか?

画像をリンクされたリソースとして電子メールに追加するには、`LinkedResource`クラス。リンクされたリソースにコンテンツ ID を割り当て、HTML 本文でこのコンテンツ ID を参照します。`cid:`スキーム。詳細については、「[LinkedResource ドキュメント](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Aspose.Email for .NET に関するその他のドキュメントはどこで見つけられますか?

 Aspose.Email for .NET の操作に関する詳細なドキュメント、チュートリアル、例は、次の場所にあります。[APIリファレンス](https://reference.aspose.com/email/net/).