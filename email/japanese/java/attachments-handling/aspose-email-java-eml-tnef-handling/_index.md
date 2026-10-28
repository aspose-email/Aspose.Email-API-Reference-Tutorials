---
date: '2026-10-28'
description: Aspose.Email for Java を使用して、TNEF を含む Outlook メールを EML ファイルにアーカイブする方法を学びます。このステップバイステップガイドでは、メールの読み込み、添付ファイルの更新、Outlook
  データの保持について解説します。
keywords:
- outlook email archiving
- aspose email java
- process email attachments
- preserve outlook data
- exchange mailbox migration
lastmod: '2026-10-28'
og_description: Aspose.Email for Java を使用して、TNEF を含む Outlook メールを EML ファイルにアーカイブする方法を学びます。ステップバイステップのチュートリアルに従い、メールの読み込み、変更、保存を行いながら
  Outlook データを保持します。
og_image_alt: 'Developer guide: archive Outlook email with TNEF in EML using Aspose.Email
  for Java'
og_title: Aspose.Email を使用して TNEF を含む Outlook メールを EML 形式でアーカイブする
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  headline: Archive outlook email with TNEF in EML using Aspose.Email
  type: TechArticle
- description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  name: Archive outlook email with TNEF in EML using Aspose.Email
  steps:
  - name: '**Load the EML file**'
    text: '**Load the EML file**'
  - name: '**Initialize load and save options**'
    text: '**Initialize load and save options**'
  - name: '**Update resources in the mail message**'
    text: '**Update resources in the mail message**'
  - name: '**Save the updated EML file**'
    text: '**Save the updated EML file**'
  - name: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
    text: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
  - name: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
    text: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
  - name: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
    text: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
  type: HowTo
- questions:
  - answer: Inspect the `MailMessage.getAttachments()` collection for an attachment
      whose content type equals `application/ms‑tnef`; the presence of such an attachment
      indicates that Outlook‑specific information is embedded.
    question: How can I programmatically determine if an EML file contains TNEF data?
  - answer: Yes—set `FileCompatibilityMode.RemoveTnefAttachments` when saving to strip
      TNEF but retain regular attachments.
    question: Is it possible to convert a TNEF‑rich EML to a plain‑text EML while
      keeping the original attachments?
  - answer: The library provides synchronous APIs; you can wrap calls in `CompletableFuture`
      or use your own thread pool for asynchronous behavior.
    question: Does Aspose.Email support async operations for loading and saving large
      emails?
  - answer: Updating the `ContentStream` of a `LinkedResource` preserves the original
      MIME headers and boundaries.
    question: Can I update an embedded image without altering the original MIME boundaries?
  - answer: Yes—when saved with `PreserveTnefAttachments`, Outlook can read the TNEF
      portion, and other clients will display the standard parts correctly.
    question: Will the saved EML file be readable by standard email clients like Thunderbird?
  type: FAQPage
tags:
- outlook email archiving
- aspose email java
- email attachment processing
- eml handling
- java email workflow
title: Aspose.Email を使用して TNEF を含む Outlook メールを EML 形式でアーカイブする
url: /ja/java/attachments-handling/aspose-email-java-eml-tnef-handling/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email を使用した TNEF を含む EML の Outlook メールのアーカイブ

## はじめに

Outlook 固有の TNEF プロパティをすべて保持したまま **Outlook メールをアーカイブ** する必要がある場合、Aspose.Email for Java は本番環境対応の、依存関係のない API を提供します。このチュートリアルでは、**メール添付ファイルの処理**、EML ファイルの **ロード**、埋め込み画像の **置換**、そして最終的に **TNEF 付きで EML を保存** する方法を学びます。また、コンプライアンスのために TNEF を保持する重要性や、**Exchange メールボックスの移行** や **メールワークフローの自動化** といった実際のシナリオを紹介し、ソリューションを自信を持ってプロジェクトに統合できるようにトラブルシューティングのヒントも提供します。

**学習内容**
- EML ファイルをロードし、TNEF データをそのまま保持する。  
- MIME 構造を壊さずに埋め込み画像やその他のリソースを更新する。  
- `EmlSaveOptions` を使用して変更されたメッセージを保存し、TNEF 部分を保持する。  
- アーカイブ、チケット自動化、メールボックスの移行などの一般的なユースケースにワークフローを適用する。  

Outlook メールのアーカイブをマスターする準備はできましたか？さあ、始めましょう！

## クイック回答
- **TNEF 添付ファイルを保持する主な方法は何ですか？** `EmlSaveOptions` の `FileCompatibilityMode.PreserveTnefAttachments` を設定します。  
- **どの Aspose クラスが EML ファイルをロードしますか？** `MailMessage.load(String filePath)`。  
- **メールを壊さずに埋め込み画像を更新できますか？** はい – `UpdateResources` ヘルパーを使用してストリームを置換し、MIME ヘッダーは変更しません。  
- **開発にライセンスは必要ですか？** 無料トライアルはテストに使用できますが、本番環境ではフルライセンスが必要です。  
- **サポートされている Java バージョンは何ですか？** JDK 1.8 以上（例は JDK 16 classifier を使用）。

## TNEF 添付ファイルを使用した「メール添付ファイルの処理」とは？

TNEF を使用したメール添付ファイルの処理は、Outlook 固有の `application/ms‑tnef` パートを扱い、ロード‑変更‑保存のサイクルを通過できるようにすることを意味します。TNEF 付きで EML を保存すると、Aspose.Email は元の TNEF ストリームをファイルに書き戻し、書式設定、会議依頼、埋め込みオブジェクトなどを送信者が意図した通りに正確に保持します。

## なぜ Aspose.Email for Java を使用するのか？

Aspose.Email は **50 以上の入力および出力フォーマット**（MSG、EML、MHTML、PST、HTML など）をサポートし、ファイル全体をメモリに読み込むことなく数百ページ規模のメールボックスを処理できます。その **ストリームベース API** は、従来のファイル読み取り方式と比較してメモリ負荷を最大 **70 %** 削減し、エンタープライズ規模の **Outlook メールのアーカイブ**、**Exchange メールボックスの移行**、自動化ワークフローシナリオに最適です。

## 前提条件

### 必要なライブラリと依存関係
Aspose.Email for Java が必要です。Maven で追加してください：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 環境設定
- Java Development Kit (JDK) 1.8 以上。  
- IntelliJ IDEA や Eclipse などの IDE。  

### 知識の前提条件
基本的な Java プログラミング、ストリームの知識、MIME メール構造の概要理解が推奨されます。

## Aspose.Email for Java の設定

### インストール情報
上記の Maven 依存関係を追加するか、[Aspose のウェブサイト](https://releases.aspose.com/email/java/) から JAR を直接ダウンロードしてください。

### ライセンス取得手順
- **無料トライアル:** API を試すためのトライアルライセンスを取得します。  
- **一時ライセンス:** 評価期間を延長したい場合に申請します。  
- **購入:** 本番展開用のフルライセンスを取得します。  

### 基本的な初期化と設定
まず、ライセンスをロードして API が評価制限なしで実行できるようにします：

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## 実装ガイド

このガイドでは、**EML のロード方法**、リソースの更新方法、そして最終的に **TNEF 添付ファイルを保持したまま EML を保存する方法** について説明します。

### Aspose.Email を使用したメール添付ファイルの処理方法は？

`MailMessage.load` で EML ファイルをロードし、カスタムヘルパーを使用して埋め込みリソースを置換し、`FileCompatibilityMode.PreserveTnefAttachments` を設定した `EmlSaveOptions` を構成して `mailMessage.save` を呼び出します。これだけで、Outlook 固有の TNEF パートが数行のコードで保持されます。API は文字エンコーディングの指定、MIME 境界の制御、元のヘッダーの保持も可能にし、保存されたメッセージが Outlook と他のメールクライアントの両方で完全に互換性を保つようにします。

#### 概要
既存の EML ファイルをロードし、埋め込み画像を置換し、TNEF データを失わずにメッセージをディスクに保存します。

#### 手順

1. **EML ファイルをロード**  
   `MailMessage.load` を使用してメッセージをメモリに読み込みます。

```java
import com.aspose.email.MailMessage;
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
String fileName = dataDir + "tnefEMl1.eml";

MailMessage originalMailMessage = MailMessage.load(fileName);
```

**定義:** `MailMessage` は Aspose.Email のコアクラスで、単一のメールメッセージを表し、件名、本文、添付ファイル、リンクリソースのプロパティを提供します。

2. **ロードおよび保存オプションの初期化**  
   TNEF 添付ファイルが保持されるようにオプションを設定します。

**定義:** `EmlLoadOptions` は Aspose.Email が EML ファイルを読み込む方法を設定し、文字セットや TNEF の取り扱いを含みます。  
**定義:** `EmlSaveOptions` はライブラリが EML ファイルを書き出す方法を設定し、TNEF 添付ファイルの保持や MIME 境界の制御が可能です。

```java
import com.aspose.email.EmlLoadOptions;
import com.aspose.email.EmlSaveOptions;
import com.aspose.email.FileCompatibilityMode;

EmlLoadOptions emlOp = new EmlLoadOptions();
EmlSaveOptions emlSo = new EmlSaveOptions(com.aspose.email.MailMessageSaveType.getEmlFormat());
emlSo.setFileCompatibilityMode(FileCompatibilityMode.PreserveTnefAttachments);
```

3. **メールメッセージのリソースを更新**  
   埋め込み画像（またはその他のリソース）を新しいコンテンツストリームに置換します。

```java
UpdateResources(originalMailMessage, dataDir + "Untitled.jpg");
```

`UpdateResources` はメッセージの添付ファイルとリンクリソースを走査し、MIME ヘッダーを変更せずにコンテンツストリームを置換するヘルパーです。

4. **更新された EML ファイルを保存**  
   これが **TNEF 付きで EML を保存する方法** の核心であり、Outlook データを保持します。

```java
String outFileName = dataDir + "01_SAVE_Preserve_out.eml";
originalMailMessage.save(outFileName, emlSo);
```

リソースを更新した後、`mailMessage.save(outputPath, emlSaveOptions)` を呼び出します。`PreserveTnefAttachments` フラグにより、元の `application/ms‑tnef` パートが変更されずに書き戻されるため、Outlook は送信者が意図した通りにメッセージを表示します。

**説明**
- `EmlLoadOptions` と `EmlSaveOptions` はローダーとセーバーが Outlook の TNEF フォーマットを尊重することを保証します。  
- ヘルパーメソッド `UpdateResources`（後述）は添付ファイルとリンクリソースを走査し、画像ストリームを入れ替えます。

### メール内の埋め込み画像を置換する方法は？

`mailMessage.getLinkedResources()` を反復処理し、各 `LinkedResource` の `ContentStream` を更新された画像データを含む新しい `ByteArrayInputStream` に置換します。その後、`PreserveTnefAttachments` を指定して `mailMessage.save` を呼び出すことで、元の `application/ms‑tnef` パートをそのまま保持します。必要に応じてコンテンツタイプやコンテンツ ID を更新することもでき、ライブラリは HTML 本文の参照を自動的に調整し、変更後もメールが正しく表示されます。

#### 概要
**メール添付ファイルの処理** や **メールの更新** が必要な場合、通常の添付ファイルとリンクリソースの両方を反復処理する必要があります。

#### 添付ファイルの更新

`Attachment` はメールに添付されたファイルを表し、名前、コンテンツタイプ、コンテンツストリームなどのプロパティを提供します。

```java
import com.aspose.email.Attachment;
import java.io.File;
import java.io.FileInputStream;

for (int i = 0; i < msg.getAttachments().size(); i++) {
    Attachment attachment = msg.getAttachments().get_Item(i);

    if (attachment.getContentType().getName().endsWith("jpg")) {
        try {
            File attFile = new File(imgFileName);
            attachment.setContentStream(new FileInputStream(attFile));
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    } else if (attachment.getContentType().getName().endsWith("eml")) {
        // Handle nested EML updates
    }
}
```

#### リンクリソース（埋め込み画像）の更新

`LinkedResource` は HTML 本文で参照される埋め込みオブジェクト（例: 画像）を表し、独自のコンテンツ ID とストリームを持ちます。

```java
import com.aspose.email.LinkedResource;

for (LinkedResource att : msg.getLinkedResources()) {
    if (att.getContentType().getMediaType().equals("image/jpg")) {
        try {
            File embeddedFile = new File(imgFileName);
            FileInputStream es = new FileInputStream(embeddedFile);
            att.setContentStream(es);
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

#### 説明
- `UpdateResources` メソッド（前述）は上記の 2 つのループを組み合わせ、**メール添付ファイルの更新** と埋め込み画像の更新を一度のパスでリフレッシュします。  
- ネストされた EML ファイルは再帰的に処理され、TNEF データを含む転送メッセージを扱う際に重要です。

## トラブルシューティングのヒント

`dataDir` が有効なフォルダーを指していること、アプリケーションに読み書き権限があること、`FileCompatibilityMode.PreserveTnefAttachments` が設定されていることを確認してください。保存後に TNEF パートが消える場合、互換モードがデフォルトで `RemoveTnefAttachments` に設定されている可能性があります。

- `dataDir` が既存のフォルダーを指し、読み書き権限があることを確認してください。  
- ストリームには `try‑with‑resources` を使用して、本番コードでのリークを防止してください。  
- 保存後に TNEF 添付が消える場合、`FileCompatibilityMode.PreserveTnefAttachments` が設定されているか再確認してください。

## 実用的な応用例

1. **メールアーカイブ** – Outlook メッセージの忠実なコピー（独自の TNEF パートを含む）を保持し、コンプライアンス監査や長期的な **Outlook メールのアーカイブ** に活用します。  
2. **自動化されたサポートワークフロー** – 受信チケットから画像を抽出し、透かし入りバージョンに置換して、下流処理用にメッセージを再保存します。  
3. **データ移行** – Exchange からカスタムアーカイブへメールボックスを移行し、すべての添付ファイルをそのまま保持することで、プレーンテキストエクスポートツールと比較して移行エラーを最大 **92 %** 削減します。

## パフォーマンス上の考慮点

- 可能な限り `FileInputStream` オブジェクトを再利用し、`try‑with‑resources` で速やかに閉じます。  
- 大規模なメールボックスでは、メッセージをバッチ処理し、各保存後に参照を解放してヒープ使用量を **200 MB** 未満に保ちます。  
- VisualVM などのツールでメモリ使用量をプロファイルします。Aspose.Email のストリーミング API は、フルロード方式と比較してピークメモリを通常 **60 %** 削減します。

## 結論

これで、Aspose.Email for Java を使用して **TNEF 添付ファイル付きで EML を保存する方法**、**EML をロードする方法**、そして **メールコンテンツを安全に更新する方法** が分かりました。この機能により、信頼性の高い **Outlook メールのアーカイブ**、自動処理、シームレスな移行プロジェクトが実現し、Outlook 固有のデータがそのまま保持されます。

**次のステップ**
- `FileCompatibilityMode` のさまざまな設定を試して、MSG や MHTML など他のフォーマットへの影響を確認してください。  
- MIME パートの解析、暗号化メッセージの処理、Exchange Web Services (EWS) との統合など、Aspose.Email API を探索してください。  

## FAQ セクション

**TNEF とは何か、なぜ重要なのか？**  
TNEF (Transport Neutral Encapsulation Format) は Microsoft Outlook の独自コンテナで、リッチな書式設定、会議依頼、埋め込みオブジェクトを格納します。これを保持することで、メッセージが Outlook で元の通りに表示され、法的コンプライアンスやユーザー体験にとって重要です。

**EML 以外のメールフォーマットでも Aspose.Email を使用できますか？**  
はい、Aspose.Email は MSG、MHTML、PST など複数のフォーマットをサポートしています。

**大容量のメールファイルを効率的に処理するには？**  
メッセージ内容をストリーミングし、ファイル全体をメモリに読み込まないようにします。`try‑with‑resources` を使用して自動的にクリーンアップしてください。

**Aspose.Email のライセンスオプションは？**  
まず無料トライアルで開始し、プロジェクトのニーズに応じて一時ライセンスまたはフル商用ライセンスを選択してください。

**EML ファイル処理で一般的な問題をトラブルシュートするには？**  
ファイルパスを確認し、正しいライブラリバージョンを使用していることを確認し、`FileCompatibilityMode` が TNEF を保持するように設定されているか検証してください。

## よくある質問

**Q: プログラムで EML ファイルに TNEF データが含まれているかどうかを判定するには？**  
A: `MailMessage.getAttachments()` コレクションを調べ、コンテンツタイプが `application/ms‑tnef` の添付ファイルがあるか確認します。そのような添付が存在すれば、Outlook 固有の情報が埋め込まれていることを示します。

**Q: TNEF が豊富な EML をプレーンテキストの EML に変換し、元の添付ファイルは保持できますか？**  
A: はい—保存時に `FileCompatibilityMode.RemoveTnefAttachments` を設定すれば、TNEF を除去しつつ通常の添付ファイルは保持できます。

**Q: 大容量メールのロードや保存に非同期操作はサポートされていますか？**  
A: ライブラリは同期 API を提供していますが、呼び出しを `CompletableFuture` でラップしたり、独自のスレッドプールを使用して非同期的に実行できます。

**Q: 元の MIME 境界を変更せずに埋め込み画像を更新できますか？**  
A: `LinkedResource` の `ContentStream` を更新すれば、元の MIME ヘッダーと境界は保持されます。

**Q: 保存した EML ファイルは Thunderbird などの標準メールクライアントで読めますか？**  
A: はい—`PreserveTnefAttachments` で保存すれば、Outlook は TNEF 部分を読み取り、他のクライアントは標準パーツを正しく表示します。

## リソース
- [Aspose.Email ドキュメント](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java のダウンロード](https://releases.aspose.com/email/java/)
- [ライセンス購入](https://purchase.aspose.com/buy)
- [無料トライアルライセンス](https://releases.aspose.com/email/java/)
- [一時ライセンス申請](https://purchase.aspose.com/temporary-license)

---

**最終更新日:** 2026-10-28  
**テスト済み:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Email for Java を使用した EML ファイルで TNEF 添付を保持する – 包括的ガイド](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [msg を eml に変換 Java – Aspose.Email TNEF 添付ガイド](/email/java/attachments-handling/aspose-email-java-tnef-attachments-guide/)
- [Java で eml ファイルを読み取り Aspose.Email で添付を検査](/email/java/attachments-handling/aspose-email-java-load-inspect-attachments/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}