---
date: '2026-09-22'
description: Maven を使用して Aspose.Email ライセンスでメールを Java の MHT ファイルとして保存する方法を学びます。セットアップ、カスタムテンプレート、カレンダーイベントの処理を含みます。
keywords:
- aspose email license
- how to save mht
- how to convert mht
- maven dependency aspose email
lastmod: '2026-09-22'
og_description: Maven を使用して Aspose.Email ライセンスでメールを Java の MHT ファイルとして保存する方法を学びます。セットアップ、カスタムテンプレート、カレンダーサポートを含みます。
og_image_alt: 'Tutorial: saving emails as MHT using Aspose.Email for Java with a license'
og_title: Aspose.Email ライセンスを使用してメールを MHT 形式で保存する方法
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  headline: How to use an Aspose.Email license to save emails as MHT
  type: TechArticle
- description: Learn how to use an Aspose.Email license with Maven to save emails
    as MHT files in Java. Includes setup, custom templates, and calendar event handling.
  name: How to use an Aspose.Email license to save emails as MHT
  steps:
  - name: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
    text: '**Free trial** – download from [Releases](https://releases.aspose.com/email/java/)
      and explore features without limitations.'
  - name: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary license** – request a fully functional version via the [Temporary
      License Page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase** – obtain a permanent license for long‑term projects.'
    text: '**Purchase** – obtain a permanent license for long‑term projects.'
  type: HowTo
- questions:
  - answer: Configure `MhtSaveOptions` to embed attachments; the library automatically
      includes them in the MHT package.
    question: How do I handle attachments when saving emails as MHT?
  - answer: Yes, use `MhtFormatOptions.WriteHeader` and provide custom template strings
      for each header field.
    question: Can I customize email headers in the output MHT file?
  - answer: A JDK 16 or higher is required. The library works with any IDE that supports
      Maven projects.
    question: What are the system requirements for using Aspose.Email Java?
  - answer: While MHT typically contains the full message, you can manipulate `MailMessage`
      properties to exclude unwanted sections before saving.
    question: Is it possible to save only specific parts of an email message?
  - answer: Verify file paths, ensure the license is correctly applied, and consult
      the Aspose.Email [support forum](https://forum.aspose.com/c/email/10) for detailed
      assistance.
    question: How can I troubleshoot issues with email loading or saving?
  type: FAQPage
tags:
- aspose email
- mht conversion
- java email processing
- maven
title: Aspose.Email ライセンスを使用してメールを MHT 形式で保存する方法
url: /ja/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email ライセンスを使用してメールを MHT として保存する方法

## はじめに

メールデータを効率的に管理することは、特に共有やアーカイブに関しては難しいことがあります。このガイドでは、**Maven Aspose.Email for Java と Aspose.Email ライセンスを使用して MHT ファイルを保存する方法**を示します。これにより、カスタムテンプレートを使用してメールを MHT に変換し、カレンダーイベントをそのまま保持できます。Java 16+ 環境で動作し、製品使用時のライセンス要件を満たす、すぐに実行できるソリューションが手に入ります。

## クイック回答
- **必要なライブラリは何ですか？** Maven Aspose.Email for Java (v25.4+)。  
- **生成されるフォーマットは何ですか？** HTML、画像、カレンダー データをまとめた MHT (MHTML) ファイルです。  
- **ヘッダーをカスタマイズできますか？** はい – `MhtFormatOptions` とテンプレート文字列を使用します。  
- **ライセンスは必要ですか？** 本番環境では Aspose.Email ライセンスが必要です。評価目的には無料トライアルが利用できます。  
- **必要な Java バージョンは何ですか？** JDK 16 以降です。  

## Maven Aspose.Email for Java とは？

Maven Aspose.Email for Java は、Java コードから直接メールメッセージを作成、読み取り、変換、操作するための包括的な API を提供するライブラリです。MSG、EML、MHT など 30 以上のメールフォーマットをサポートしており、実質的にあらゆるメールファイルを扱うことができます。

## なぜメールを MHT に変換するのか？

MHT ファイルは、HTML、画像、カレンダー データなどすべてのリソースを単一ファイルに埋め込むため、外部アセットなしで任意の最新ブラウザですぐに表示できます。この形式は元の外観を保持し、繰り返しカレンダー イベントをサポートし、共有時に添付ファイルが欠落するリスクを減らします。

## 前提条件
- **Aspose.Email for Java**（Maven アーティファクト `com.aspose:aspose-email:25.4`、`jdk16` classifier 付き）。  
- **Maven** がインストールされ、マシンで設定されていること。  
- **JDK 16+**（ライブラリは Java 16 を対象としています）。  
- 本番使用のための有効な **Aspose.Email ライセンス** ファイル。  
- 基本的な Java の知識（ファイル操作、Maven 依存関係）。  

## Aspose.Email for Java の設定

### Maven 依存関係

`pom.xml` ファイルに以下の依存関係を追加します。

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得

Aspose は機能を試すための無料トライアルを提供しており、ライセンスの購入や一時ライセンスの取得オプションもあります。

1. **無料トライアル** – [Releases](https://releases.aspose.com/email/java/) からダウンロードし、機能制限なしで試せます。  
2. **一時ライセンス** – [Temporary License Page](https://purchase.aspose.com/temporary-license/) からフル機能版をリクエストできます。  
3. **購入** – 長期プロジェクト向けの永続ライセンスを取得します。  

### 基本的な初期化

インストールが完了したら、Java アプリケーションでライブラリを初期化します。

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

これらの手順が完了すれば、効率的なメール処理のために Aspose.Email の機能を使用できるようになります。

## 実装ガイド

### 機能 1: MailMessage のロード

#### 概要

`MailMessage` は Aspose.Email のコアオブジェクトで、ヘッダー、本文、添付ファイル、カレンダー イベントを含むメールを表します。

#### 手順

**必要なクラスをインポート**

```java
import com.aspose.email.MailMessage;
```

**ファイルからメールをロード**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

このスニペットは、指定したディレクトリにあるメールメッセージをロードします。

### 機能 2: MhtSaveOptions の設定

#### 概要

`MhtSaveOptions` は、Aspose.Email が `MailMessage` を MHT ファイルとして保存する方法を設定し、フォーマットフラグ、テンプレート、リソース埋め込みを制御します。適切に設定すれば、ヘッダーの埋め込み、カレンダー イベントのレンダリング、すべての画像の埋め込みが可能です。

#### 手順

**必要なクラスをインポート**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**保存オプションとテンプレートを設定**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

この設定により、MHT 出力でヘッダーとカレンダー イベントのレンダリングが行われます。

### 機能 3: MailMessage を MHT として保存

#### 概要

設定した `MailMessage` を MHT ファイルとして保存すると、ブラウザやメールクライアントで開ける単一の自己完結型ドキュメントが作成されます。`save` メソッドは、以前に定義したオプションを尊重します。

#### 手順

**必要なクラスをインポート**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**メールメッセージを保存**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

このコマンドはメールを MHT ファイルに書き出し、共有やアーカイブの準備が整います。

## 実用的な活用例
- **メールアーカイブ** – 重要なメールをウェブフレンドリーな形式に変換・保存し、長期保存します。  
- **法的文書** – メールの忠実性が求められる法的証拠として MHT ファイルを使用します。  
- **クロスプラットフォーム共有** – MHT がすべてを1つのファイルにまとめるため、互換性問題なくプラットフォーム間でメールを共有できます。  

CRM やプロジェクト管理ツールなど他のシステムと統合することで、重要なメールデータをワークフローに直接埋め込み、コラボレーションを強化できます。

## パフォーマンス上の考慮点

Aspose.Email for Java は、ドキュメント全体をメモリに読み込むことなく最大 500 MB のファイルを処理でき、標準サーバー上で画像を埋め込んだ 100 ページのメールを 2 秒未満で変換することが一般的です。アプリケーションの応答性を保つため、メモリ使用量を注意深く管理し、可能な限り I/O 操作をバッチ処理してください。

## よくある問題と解決策

`MhtFormatOptions` は、メッセージを MHT として保存する際に含める要素（ヘッダー、リソース、カレンダー イベント）を制御する列挙型です。

| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **`msg.save` の NullPointerException** | 出力パスが正しくない | `YOUR_OUTPUT_DIRECTORY` が存在し、書き込み可能であることを確認してください。 |
| **MHT の画像が欠落** | `MhtFormatOptions` がリソース埋め込みに設定されていない | オプションフラグに `MhtFormatOptions.EmbedResources` を追加してください。 |
| **カレンダー イベントがレンダリングされない** | `RenderCalendarEvent` フラグが省略されている | `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` が設定されていることを確認してください。 |

## よくある質問

**Q: メールを MHT として保存する際に添付ファイルはどう扱いますか？**  
**A:** `MhtSaveOptions` を設定して添付ファイルを埋め込むと、ライブラリが自動的に MHT パッケージに含めます。

**Q: 出力 MHT ファイルのメールヘッダーをカスタマイズできますか？**  
**A:** はい、`MhtFormatOptions.WriteHeader` を使用し、各ヘッダー項目にカスタムテンプレート文字列を提供します。

**Q: Aspose.Email Java を使用するためのシステム要件は何ですか？**  
**A:** JDK 16 以上が必要です。Maven プロジェクトをサポートする任意の IDE で動作します。

**Q: メールメッセージの特定の部分だけを保存することは可能ですか？**  
**A:** MHT は通常全メッセージを含みますが、保存前に `MailMessage` のプロパティを操作して不要なセクションを除外できます。

**Q: メールのロードや保存に関する問題をトラブルシュートするには？**  
**A:** ファイルパスを確認し、ライセンスが正しく適用されていることを確認し、詳細な支援は Aspose.Email の [support forum](https://forum.aspose.com/c/email/10) を参照してください。

**Q: ライブラリは他のフォーマット（EML、MSG）を MHT に変換することをサポートしていますか？**  
**A:** もちろんです。`MailMessage.load` は EML、MSG などのサポートされたフォーマットを読み込め、その後同じオプションで MHT として保存できます。

## リソース
- **ドキュメント**: すべての機能を詳しく知るには、[Aspose Email Java Documentation](https://reference.aspose.com/email/java/) をご覧ください。  
- **ダウンロード**: 無料トライアルを開始するには、[Releases](https://releases.aspose.com/email/java/) からダウンロードしてください。  
- **購入**: 長期利用向けの購入オプションは、[Official Purchase Page](https://purchase.aspose.com/buy) をご確認ください。  
- **無料トライアルと一時ライセンス**: 無料トライアル中に包括的な機能にアクセスするか、以下のリンクから一時ライセンスを取得できます。  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

ぜひ Aspose.Email for Java を活用し、メール処理を探求・実装・変革してください！

---

**最終更新日:** 2026-09-22  
**テスト環境:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者:** Aspose  

## 関連チュートリアル

- [Aspose.Email for Java のマスタリング: ライセンスとメール処理ガイド](/email/java/getting-started/mastering-aspose-email-java-license-email-handling/)
- [Aspose.Email for Java を使用した MSG から MHT への変換 – ステップバイステップガイド](/email/java/email-conversion-rendering/convert-mapi-messages-to-mht-aspose-email-java/)
- [Aspose.Email for Java で MSG メールを保存する方法](/email/java/email-message-operations/aspose-email-java-create-save-emails/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}