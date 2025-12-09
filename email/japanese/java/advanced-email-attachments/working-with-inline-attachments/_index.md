---
date: 2025-12-01
description: Aspose.Email for Java を使用して埋め込み画像付きのメールの送信方法を学びましょう。このガイドでは、画像をメールに埋め込む方法と、インライン添付ファイルを使用した
  HTML メールを Java で作成する方法を示します。
linktitle: Working with Inline Attachments in Aspose.Email
second_title: Aspose.Email Java Email Management API
title: Aspose.Email for Java を使用した埋め込み画像付きメールの送信方法
url: /ja/java/advanced-email-attachments/working-with-inline-attachments/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java を使用した埋め込み画像付きメールの送信方法

画像をメール本文に直接埋め込むことで、メッセージが洗練された印象になり、受信者は別ファイルをダウンロードすることなく画像を見ることができます。このチュートリアルでは、Aspose.Email for Java を使用して **埋め込み画像付きメールを送信する方法** を学びます。ライブラリの設定から HTML メールの作成、インラインリソースの追加、メッセージの送信までを網羅しています。

## Quick Answers
- **インライン画像の主要クラスはどれですか？** `LinkedResource`
- **HTML で画像を参照するメソッドは？** `<img>` タグで `cid:yourContentId` を使用
- **開発時にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です
- **任意の SMTP サーバーでメールを送信できますか？** はい、`SmtpClient` にサーバー情報を設定すれば可能です
- **この方法は主要なメールクライアントで動作しますか？** Outlook、Gmail、Thunderbird などのほとんどのモダンクライアントが CID 埋め込み画像に対応しています

## インライン添付（埋め込み画像）とは？

インライン添付（埋め込み画像、CID 画像とも呼ばれます）は、メールの MIME 本文内に格納されたファイルです。HTML 部分から **Content‑ID**（CID）で参照されます。この手法により、`<img>` タグを置いた場所に画像が表示され、別個のダウンロード可能な添付ファイルとしては現れません。

## Java メールで埋め込み画像を使用するメリット

- **プロフェッショナルな外観:** ロゴやバナー、商品画像が即座に表示されます
- **エンゲージメント向上:** 完成度の高いメールは受信者が読む可能性が高まります
- **余計なクリック不要:** 受信者は画像を見るために添付ファイルをダウンロードする必要がありません
- **ブランディングの一貫性:** ブランド資産がメッセージ本文と一体化します

## 前提条件

- Aspose.Email for Java ライブラリ（公式 [Aspose.Email for Java documentation](https://reference.aspose.com/email/java/) からダウンロード）
- Java 8 以上の開発環境
- メール送信用の SMTP サーバーへのアクセス権
- 埋め込みたい画像ファイル（例: `logo.png`）

## 手順ガイド

### Step 1: 基本的な HTML メールメッセージを作成

まず、HTML 本文を持つシンプルな `MailMessage` を作成します。ここが後で画像を埋め込むキャンバスになります。

```java
// Import necessary classes
import com.aspose.email.MailAddress;
import com.aspose.email.MailMessage;

// Create a new email message
MailMessage message = new MailMessage();
message.setSubject("Hello, World!");
message.setFrom(new MailAddress("sender@example.com"));
message.setTo(new MailAddress("recipient@example.com"));
message.setHtmlBody("<html><body>This is a sample email with inline attachments.</body></html>");
```

### Step 2: `LinkedResource` を使ってインライン画像を追加

次に画像を埋め込みます。`LinkedResource` クラスがインライン添付を表します。ユニークな **Content‑ID** を設定し、HTML 本文では `cid:` で参照します。

```java
import com.aspose.email.LinkedResource;

// Create a LinkedResource for the image
LinkedResource linkedResource = new LinkedResource("path/to/your/image.png");
linkedResource.setContentId("image001"); // Unique ID for the inline image

// Add the LinkedResource to the HTML body
message.getLinkedResources().add(linkedResource);

// Reference the inline image in the HTML body
message.setHtmlBody("<html><body>This is an inline image: <img src='cid:image001'></body></html>");
```

> **プロのコツ:** `ContentId` はメッセージ内で一意かつシンプルに保ち、競合を防ぎましょう。

### Step 3: `SmtpClient` でメールを送信

SMTP 設定を構成し、メッセージを送信します。埋め込み画像はメールと一緒に送られるため、受信者はすぐに画像を見ることができます。

```java
import com.aspose.email.SmtpClient;

// Create an instance of SmtpClient
SmtpClient client = new SmtpClient("smtp.example.com", 587, "username", "password");

// Send the email
client.send(message);
```

### Step 4: インライン画像を受信・抽出（任意）

受信したメールに埋め込み画像が含まれている場合、`.eml` ファイルを読み込み `LinkedResources` にアクセスして画像を取得できます。

```java
import com.aspose.email.MailMessage;
import com.aspose.email.LinkedResourceCollection;

// Load the received email message
MailMessage receivedMessage = MailMessage.load("path/to/received_email.eml");

// Access the inline attachments
LinkedResourceCollection inlineAttachments = receivedMessage.getLinkedResources();
```

## よくある問題と対処法

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Content‑ID が一致しない** | HTML の `cid:` 参照と `LinkedResource` の `ContentId` が異なる | 文字列が完全に一致しているか確認（例: `image001` と `cid:image001`） |
| **ファイルが見つからない** | 画像へのパスが間違っている、またはファイルが存在しない | 絶対パス／相対パスを確認し、サーバー上にファイルがあることを確認 |
| **SMTP 認証失敗** | 認証情報またはサーバー設定が誤っている | ホスト、ポート、ユーザー名、パスワードを再チェック。必要に応じて TLS/SSL を有効化 |
| **一部クライアントで画像が表示されない** | クライアントが外部リソースをブロックしている | 外部 URL ではなく CID 埋め込み画像（本手順）を使用 |

## FAQ

**Q: Aspose.Email for Java はどこからダウンロードできますか？**  
A: [documentation](https://reference.aspose.com/email/java/) からダウンロードできます。インストール手順に従ってプロジェクトに組み込みましょう。

**Q: Aspose.Email for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Email は他の Java ライブラリとスムーズに統合でき、メール処理と PDF 生成、OCR、データベースアクセスなどを組み合わせられます。

**Q: インライン添付でサポートされているファイル形式は？**  
A: PNG、JPEG、GIF などの一般的な画像形式に加え、SVG などのドキュメント形式もインラインリソースとして利用可能です。

**Q: HTML メールでインライン添付を扱うには？**  
A: `LinkedResource` クラスで `ContentId` を設定し、`message.getLinkedResources()` に追加します。HTML 本文では `<img src='cid:yourContentId'>` と記述します。

**Q: Aspose.Email for Java はさまざまなメールサーバーに対応していますか？**  
A: はい、任意の SMTP/IMAP/POP3 サーバーで動作します。正しいサーバーアドレス、ポート、認証情報を提供すれば問題なく利用できます。

---

**最終更新日:** 2025-12-01  
**テスト環境:** Aspose.Email for Java 24.12（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}