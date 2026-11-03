---
date: '2026-11-03'
description: Aspose.Email Javaを使用して、EMLに添付ファイルを追加する方法、JavaでMSGをEMLに変換する方法、MSGを一括でEMLに変換する方法、そしてTNEFを処理する方法を学びます。
images:
- /java/attachments-handling/aspose-email-java-tnef-attachments-guide/og-image.png
keywords:
- convert msg to eml
- add attachment to eml
- batch convert msg to eml
- maven aspose email dependency
- tnef handling
lastmod: '2026-11-03'
og_description: Aspose.Email JavaでMSGをEMLに変換し、EMLファイルに添付ファイルを追加します。Mavenの設定、TNEFの処理、一括変換、コード例が含まれています。
og_image_alt: Guide showing how to convert MSG to EML and add attachments using Aspose.Email
  Java
og_title: Aspose.Email JavaでMSGをEMLに変換し、添付ファイルを追加
schemas:
- author: Aspose
  dateModified: '2026-11-03'
  description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  headline: Add attachment to eml with Aspose.Email Java – convert msg to eml and
    handle TNEF
  type: TechArticle
- description: Learn how to add attachment to eml, convert msg to eml java, batch
    msg to eml, and handle TNEF using Aspose.Email Java.
  name: Add attachment to eml with Aspose.Email Java – convert msg to eml and handle
    TNEF
  steps:
  - name: Load the existing email message
    text: The `MailMessage` class represents an email message in memory, exposing
      headers, body, and attachments.
  - name: Add the new attachment
    text: The `Attachment` class encapsulates a file to be attached to a `MailMessage`.
  - name: Save the modified email message
    text: Calling `mail.save()` writes the updated message back to disk in EML format.
      *Pro tip:* Use try‑with‑resources to ensure streams are closed and avoid `FileNotFoundException`.
  - name: Load the MSG file
    text: The `MapiMessage` class reads Outlook MSG files and exposes their properties.
  - name: Set conversion options
    text: '`MailConversionOptions` lets you control how the conversion handles TNEF
      data.'
  - name: Convert and save
    text: Calling `msg.save()` with the appropriate options writes a TNEF‑preserving
      EML file.
  - name: Set load options
    text: '`MsgLoadOptions` instructs the loader to keep TNEF parts intact.'
  - name: Load EML file with options
    text: '`MailMessage.load()` reads the EML using the options defined above.'
  - name: Load the EML file
    text: The `MailMessage` class again serves as the entry point for reading an EML
      file.
  - name: Detect TNEF presence
    text: The boolean returned by `mail.getOriginalIsTnef()` tells you whether the
      original message contained TNEF data.
  type: HowTo
- questions:
  - answer: No. By default, TNEF data is preserved. You can control this behavior
      with `MailConversionOptions.setConvertAsTnef`.
    question: Does Aspose.Email automatically strip TNEF when converting to EML?
  - answer: Yes—use `mail.getAttachments()` which returns a collection you can iterate
      over.
    question: Can I programmatically list all attachments in a loaded message?
  - answer: Absolutely. Loop through the files, apply the conversion steps shown above,
      and save each result.
    question: Is there a way to batch convert msg files to eml in one run?
  type: FAQPage
tags:
- email conversion
- Aspose.Email
- java email processing
- attachment handling
title: Aspose.Email JavaでEMLに添付ファイルを追加 – MSGをEMLに変換しTNEFを処理する
url: /ja/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# eml に添付ファイルを追加し、Aspose.Email Java で msg を eml に変換するマスターガイド：TNEF とメール添付の処理  

## クイック回答
- **JavaでMSGをEMLに変換するには？** `MapiMessage`でMSGをロードし、`MailConversionOptions.convertAsTnef`を`true`に設定してからEMLとして保存します。  
- **TNEF 対応の EML に添付ファイルを追加できますか？** はい – EML をロードし、`mail.getAttachments().addItem(...)` を呼び出してから保存します。  
- **必要な Maven 依存関係は？** 下記の **Aspose.Email** Maven アーティファクトを含めます。  
- **本番環境でライセンスは必要ですか？** はい – 評価版は試用できますが、フルライセンスを取得すると制限が解除されます。  
- **既存メッセージで TNEF を検出する方法は？** EML をロードした後に `mail.getOriginalIsTnef()` を呼び出します。

## “convert msg to eml java” とは何ですか？
convert msg to eml java は、Microsoft Outlook MSG ファイルを Java を使用して RFC‑822 準拠の EML ファイルに変換するプロセスです。これにより、標準的なメールクライアントでメッセージを読み取れるようになり、変換中に TNEF エンコードデータを操作することが可能になります。

## eml に添付ファイルを追加する方法は？
対象の EML をロードし、新しいファイルを添付して保存するだけです – 3 つの簡潔な API 呼び出しで完了します。Aspose.Email を使用すれば手動で MIME を構築する必要がなく、ライブラリが既存の TNEF パーツを自動的に保持するため、最終的な EML は Outlook や他のクライアントと完全に互換性があります。

## このタスクに Aspose.Email Java を使用する理由は？
Aspose.Email は **30 以上のメール形式** をサポートし、**2 GB** までのファイルをメモリ全体にロードせずに処理できるため、大規模な移行に最適です。バッチ処理ユーティリティ、TNEF の保持、そして冗長なコードを削減するフルエント API も提供します。

## 前提条件
- **Aspose.Email for Java**（v25.4、JDK 16） – 下記の Maven 依存関係をご参照ください。  
- **Maven** または Aspose パッケージを解決できるその他のビルドツール。  
- Java I/O と例外処理の基本知識。

## Aspose.Email for Java の設定
Maven の `pom.xml` にライブラリを追加します:

以下の Maven 依存関係が Aspose.Email をプロジェクトに追加します。  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得
Aspose.Email は無料トライアルを提供していますが、無制限に使用するにはライセンス版が必要です。

- **無料トライアル:** Aspose.Email Java リリースページから一時ライセンスをダウンロードしてください: [Aspose.Email Java releases](https://releases.aspose.com/email/java/)。  
- **購入:** ライセンスを購入するには、[購入ページ](https://purchase.aspose.com/buy)をご利用ください。

`License` クラスは Aspose.Email のライセンスファイルを読み込み、完全な機能を有効化します。  
```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## 実装ガイド

### TNEF を含むメインメッセージに新しい添付ファイルを追加する
**eml に添付ファイルを追加する方法:** EML をロードし、ファイルを追加してから保存します。

#### 手順 1: 既存のメールメッセージをロードする
`MailMessage` クラスはメモリ上のメールメッセージを表し、ヘッダー、本文、添付ファイルにアクセスできます。  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### 手順 2: 新しい添付ファイルを追加する
`Attachment` クラスは `MailMessage` に添付するファイルをカプセル化します。  
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### 手順 3: 変更したメールメッセージを保存する
`mail.save()` は `MailMessage` を EML 形式でディスクに書き戻します。  
```java
eml.save(dataDir + "test_out.eml");
```
*プロのコツ:* try‑with‑resources を使用してストリームを確実に閉じ、`FileNotFoundException` を回避してください。

### MSG から TNEF 対応 EML を作成する
**msg を eml java に変換する方法:** `convertAsTnef` を `true` に設定します。

#### 手順 1: MSG ファイルをロードする
`MapiMessage` クラスは Outlook MSG ファイルを読み取り、そのプロパティにアクセスできます。  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### 手順 2: 変換オプションを設定する
`MailConversionOptions` では変換動作を制御でき、TNEF の取り扱いも設定できます。  
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### 手順 3: 変換して保存する
`msg.save()` は指定した変換オプションを使用して EML ファイルを作成します。  
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### MSG から TNEF 対応 EML を保持する
**TNEF を保持しながらメール添付を保存する方法:** `MsgLoadOptions` を使用します。

#### 手順 1: ロードオプションを設定する
`MsgLoadOptions` は EML ファイルのロード方法を構成し、必要に応じて TNEF パーツを保持します。  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### 手順 2: オプション付きで EML ファイルをロードする
`MailMessage.load()` は提供された `MsgLoadOptions` に従って EML ファイルを読み取ります。  
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### メッセージが TNEF かどうかを検出する
**TNEF の有無を確認する方法:** `getOriginalIsTnef()` を呼び出します。

#### 手順 1: EML ファイルをロードする
`MailMessage.load()` は検査または変更のために既存の EML ファイルをロードします。  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### 手順 2: TNEF の有無を検出する
`mail.getOriginalIsTnef()` は元のメッセージに TNEF データが含まれていた場合に true を返します。  
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## 一般的な使用例とバッチシナリオ
- **バッチ変換 msg:** `.msg` ファイルが格納されたフォルダーをループし、上記の変換手順を適用して各結果を `.eml` として保存します。大規模な移行に最適です。  
- **大量に eml に添付ファイルを追加:** 「添付ファイル追加」コードをファイルシステムイテレータと組み合わせ、複数のメッセージを一括で強化します。  
- **自動アーカイブ:** コンプライアンス監査のために、元の MSG と TNEF を保持した EML の両方を保存します。

## パフォーマンス上の考慮点
- **リソース管理:** ファイルストリームは try‑with‑resources でラップし、ハンドルを速やかに解放します。  
- **大容量添付ファイル:** 大きなファイルはチャンク単位で処理するか、直接ストリームで転送し、メモリ使用量を抑えます。  
- **モニタリング:** 多数の添付ファイルを扱う際は、Java のプロファイリングツールでヒープ消費を監視します。

## 結論
上記の手順に従うことで、**eml に添付ファイルを追加**し、**msg を eml java に変換**し、Aspose.Email for Java を使用して TNEF データを確実に扱うことができます。ライブラリは低レベルの MIME 処理を抽象化し、ビジネスロジックに集中できるようにします。詳しくは公式の [Aspose.Email Java documentation](https://reference.aspose.com/email/java/) を確認するか、他の変換オプションで実験してみてください。追加リソースとして、[Aspose Email Java Documentation](https://reference.aspose.com/email/java/)、[Aspose Email Java Releases](https://releases.aspose.com/email/java/)、および [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) ページがあります。

## FAQ セクション
**Q1: TNEF ファイルとは何ですか？**  
A1: TNEF は Transport Neutral Encapsulation Format の略で、Microsoft Outlook がリッチテキスト形式を添付メールとして送信する際に使用します。

**Q2: ライセンスを購入せずに Aspose.Email を使用できますか？**  
A2: はい、無料トライアルで開始できます。ただし、トライアル版にはフルスケールでの使用に影響する制限があります。

**Q3: Aspose.Email ですべてのメール形式間の変換は可能ですか？**  
A3: Aspose.Email は EML、MSG、MHTML などの主要フォーマット間の変換をサポートしていますが、特定の形式サポートは [ドキュメント](https://reference.aspose.com/email/java/) で確認してください。

**Q4: Aspose.Email でファイルが見つからないエラーをトラブルシュートするには？**  
A5: API に渡すファイルパスが正しいか、ファイルが存在するか、実行プロセスにそのディレクトリへの読み書き権限があるかを再確認してください。

**Q5: 大容量添付ファイルを Aspose.Email で扱う最適な方法は？**  
A5: 添付ファイルを小さなストリームまたはチャンクで処理し、常にストリームを速やかに閉じます。これによりメモリ圧迫が軽減され、`OutOfMemoryError` を防止できます。

## 追加のよくある質問

**Q: Aspose.Email は EML へ変換する際に自動的に TNEF を除去しますか？**  
A: いいえ。デフォルトでは TNEF データは保持されます。`MailConversionOptions.setConvertAsTnef` で動作を制御できます。

**Q: 読み込んだメッセージのすべての添付ファイルをプログラムで列挙できますか？**  
A: はい、`mail.getAttachments()` を使用すればコレクションが返り、イテレート可能です。

**Q: 1 回の実行で msg ファイルを eml にバッチ変換する方法はありますか？**  
A: もちろんです。ファイルをループし、上記の変換手順を適用して各結果を保存します。

**関連リソース:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Aspose.Email Java リリースページから一時ライセンスをダウンロード: [Aspose.Email Java releases](https://releases.aspose.com/email/java/).

---

**Last Updated:** 2026-11-03  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose  

## 関連チュートリアル

- [Maven Aspose Email: Preserve TNEF Attachments in EML (Java)](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [How to Add Aspose.Email Maven Dependency and Retrieve Email Attachment Content Descriptions (Java)](/email/java/attachments-handling/retrieve-email-attachment-content-descriptions-aspose-email-java/)
- [Extract Email Attachments Java with Aspose.Email – Complete Guide](/email/java/attachments-handling/)

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}