---
title: C# コードを使用した電子メール ドキュメント変換の進行状況の追跡
linktitle: C# コードを使用した電子メール ドキュメント変換の進行状況の追跡
second_title: Aspose.Email .NET 電子メール処理 API
description: Aspose.Email for .NET を使用して電子メール通知と追跡を実装する方法を学びます。コード例を含むステップバイステップのガイド。今すぐメールコミュニケーションを強化しましょう!
type: docs
weight: 12
url: /ja/net/email-notification-and-tracking/tracking-email-document-conversion-progress-with-csharp-code/
---

今日のデジタル時代では、電子メールによるコミュニケーションは個人的な領域でも仕事上の領域でも重要な役割を果たしています。プログラマーであれば、電子メール メッセージをプログラムで処理し、操作する必要に遭遇したことがあるかもしれません。一般的なタスクの 1 つは、電子メール ドキュメントの変換の進行状況を追跡することです。この記事では、C# と Aspose.Email for .NET を使用したプロセスを段階的に説明します。

## Aspose.Email for .NET の概要

コードの説明に入る前に、Aspose.Email for .NET について簡単に説明しましょう。この強力なライブラリは、さまざまな形式の電子メールの読み取り、書き込み、変換など、電子メール メッセージを操作するための幅広い機能を提供します。私たちの場合は、電子メール文書の変換に焦点を当てます。

## 環境のセットアップ

始めるには、開発環境をセットアップする必要があります。次の前提条件が満たされていることを確認してください。

-  Aspose.Email for .NET ライブラリがインストールされています。からダウンロードできます[ここ](https://releases.aspose.com/email/net/).

それでは、コードに入りましょう。提供された C# ソース コードを使用して、電子メール ドキュメントの変換の進行状況を追跡するためのステップバイステップ ガイドを作成します。

## ステップ 1: 電子メール メッセージをロードする

まず、電子メール メッセージをファイルからロードします。必ず交換してください`"Your Document Directory"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "Your Document Directory";
var fileName = dataDir + "test.eml";
MailMessage msg = MailMessage.Load(fileName);
```

## ステップ 2: カスタム進行状況ハンドラーの定義

このステップでは、変換の進行状況を監視するカスタム進行状況ハンドラーを設定します。の`ShowEmlConversionProgress`メソッドは変換プロセス中に呼び出され、進行状況に関する情報が提供されます。

```csharp
private static void ShowEmlConversionProgress(ProgressEventHandlerInfo info)
{
    int total;
    int saved;
    switch (info.EventType)
    {
        case ProgressEventType.MimeStructureCreated:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("MimeStructureCreated - TotalMimePartCount: " + total);
            Console.WriteLine("MimeStructureCreated - SavedMimePartCount: " + saved);
            break;
        case ProgressEventType.MimePartSaved:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("MimePartSaved - TotalMimePartCount: " + total);
            Console.WriteLine("MimePartSaved - SavedMimePartCount: " + saved);
            break;
        case ProgressEventType.SavedToStream:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine("SavedToStream - TotalMimePartCount: " + total);
            Console.WriteLine("SavedToStream - SavedMimePartCount: " + saved);
            break;
    }
}
```

## ステップ 3: 進捗状況を追跡して電子メール メッセージを保存する

次に、進行状況を追跡しながら電子メール メッセージを保存しましょう。私たちが使用するのは、`EmlSaveOptions`カスタム進行状況ハンドラーを含むクラス。

```csharp
MemoryStream ms = new MemoryStream();
EmlSaveOptions opt = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
opt.CustomProgressHandler = new ConversionProgressEventHandler(ShowEmlConversionProgress);
msg.Save(ms, opt);
```

## 結論

おめでとう！ C# と Aspose.Email for .NET を使用して、電子メール ドキュメント変換の進行状況追跡を正常に実装しました。この機能は、アプリケーションで大量の電子メールやドキュメントの変換を処理する場合に役立ちます。

詳細と詳細なドキュメントについては、次のサイトを参照してください。[Aspose.Email for .NET API リファレンス](https://reference.aspose.com/email/net/).


## よくある質問

### Aspose.Email for .NET とは何ですか?
Aspose.Email for .NET は、.NET アプリケーションで電子メール メッセージを操作するための強力なライブラリです。電子メールの読み取り、書き込み、変換のための機能を提供します。

### Aspose.Email for .NET を使用して電子メール ドキュメントの変換の進行状況を追跡できますか?
はい、この記事で説明しているように、カスタム進行状況ハンドラーを使用して電子メール ドキュメント変換の進行状況を追跡できます。

### Aspose.Email for .NET は C# プロジェクトに簡単に統合できますか?
はい、Aspose.Email for .NET は C# プロジェクトに簡単に統合できます。 Web サイトからライブラリをダウンロードしてインストールできます。

### C# で電子メールを操作するための他のライブラリはありますか?
はい、他にもライブラリはありますが、Aspose.Email for .NET はその包括的な機能と使いやすさで知られています。

### Aspose.Email for .NET のその他のチュートリアルと例はどこで見つけられますか?
探索することができます[Aspose.Email for .NET API リファレンス](https://reference.aspose.com/email/net/)チュートリアル、例、詳細なドキュメントについては、こちらをご覧ください。

これで、C# アプリケーションで電子メール ドキュメントの変換の進行状況を自信を持って処理できるようになりました。コーディングを楽しんでください!