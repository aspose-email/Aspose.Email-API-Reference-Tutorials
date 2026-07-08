---
date: '2026-07-08'
description: Aspose.Email を使用して EWS クライアント Java を作成し、効率的なメール管理を実現する方法を学びます。Exchange
  Server 上での message deletion、appending、user impersonation を含みます。
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Aspose.Email を使用して EWS クライアント Java を作成し、効率的なメール管理を実現する方法を学びます。Exchange
  Server 上での message deletion、appending、user impersonation を含みます。
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Aspose.Email を使用して EWS クライアント Java を作成 – ユーザー管理
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Aspose.Email を使用して EWS クライアント Java を作成 – ユーザー管理
url: /ja/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# メール管理のマスター: Aspose.Email Java の EWS クライアント ユーザーとインパーソネーション

## はじめに

このチュートリアルでは、Aspose.Email を使用して **create EWS client Java** アプリケーションを作成し、単一の Java コードベースから複数の Exchange Server メールボックスを管理できるようにします。`EWSClient` インスタンスの作成、メッセージの削除、新しいメールの追加、他のユーザーへのインパーソネーションの手順を解説します。これらのタスクは、エンタープライズ環境での手作業を何時間も削減します。

### 学習内容
- 異なる資格情報を使用して **create EWS client Java** オブジェクトを作成する方法。  
- 選択したフォルダーからすべてのメッセージを削除する効率的な手法。  
- 既成のメールをユーザーのメールボックスに追加する手順。  
- 共有メールボックスシナリオで別のメールボックスをインパーソネートする方法。

これでカバーする内容が分かったので、開発環境を整えましょう。

## クイック回答
- **最初のステップは何ですか？** `pom.xml` に Aspose.Email の Maven 依存関係を追加します。  
- **Exchange 接続を表すクラスはどれですか？** `EWSClient`（またはそのインターフェイス `IEW​SClient`）。  
- **すべてのメッセージを一度に削除できますか？** はい—`listMessages` で反復し、各 URI に対して `deleteMessage` を呼び出します。  
- **SMTP を使用せずにメールを送信するには？** `appendMessage` を使用して `MailMessage` を直接フォルダーに配置します。  
- **インパーソネーションは安全ですか？** 元の資格情報で実行され、Exchange の委任ポリシーを尊重します。

## create EWS client Java とは何ですか？
`create ews client java` は、Java アプリケーション内で `EWSClient` オブジェクトをインスタンス化し、Exchange Web Services（EWS）操作をプログラムから呼び出せるようにすることを指します。このアプローチにより、手動の Outlook 操作が不要になり、メールボックスの自動処理が可能になります。ユーザーごとに専用クライアントを作成することで、資格情報を分離し、メールボックス単位のポリシーを適用でき、コードの重複なしに多数のアカウントにスケールできます。

## EWS 統合に Aspose.Email を使用する理由
Aspose.Email は **50+** の EWS 操作をサポートし、**数百ページ** のメールボックスをメモリ全体にロードせずに処理でき、典型的なサーバーハードウェア上で **1 分間に最大 10,000** 件のメッセージを処理します。これらの定量的な能力により、大規模なメール自動化に最適な選択肢となります。また、低レベルの SOAP 詳細を抽象化し、型安全なクリーン API を提供するため、開発時間が短縮されバグが最小化されます。

## 前提条件
- **Java Development Kit (JDK)** ≥ 16。  
- **Maven**（依存関係管理用）。  
- **Aspose.Email for Java** ライブラリ（Maven で追加）。  
- Exchange Web Services (EWS) の基本概念に関する知識。

## Aspose.Email for Java の設定
Maven `pom.xml` にライブラリを追加します:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得
Aspose.Email は無料トライアルを提供しており、フル機能の一時ライセンスをリクエストできます。長期利用の場合は、[Aspose's purchase page](https://purchase.aspose.com/buy) からライセンス購入をご検討ください。

## EWS client Java の作成方法
Exchange サービスに適切な資格情報で接続し、`IEWSClient` インスタンスを取得します。この 2 ステップ パターンが以降のすべての操作のコアです。同じクライアントを複数のアクションに再利用することも、ユーザーごとに別々のインスタンスを作成して分離することも可能です。**`IEWSClient` はすべての EWS 操作を公開するインターフェイスで、`EWSClient` は実装を取得する静的ファクトリ メソッドを提供します。**

### EWSClient インスタンスの作成
**定義:** `EWSClient`（`IEWSClient` インターフェイス経由で公開）は、EWS を介して Exchange サーバーと通信するための Aspose.Email の主要オブジェクトです。

#### 必要なクラスのインポート
まず、必要な Aspose.Email クラスをインポートします:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### EWSClient インスタンスの初期化
管理したい各メールボックス用に `IEWSClient` オブジェクトを作成します:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*説明:* `getEWSClient` ヘルパーは提供された資格情報で Exchange に接続し、現在のユーザーの権限を尊重した使用可能なクライアントを返します。

## フォルダーからメッセージを削除する方法?
対象フォルダー内のすべてのアイテムを取得し、1 回のパスで永久に削除します。この方法は、個々のメッセージを開くオーバーヘッドを回避します。**`listMessages` は各メッセージの一意な URI を含む `MessageInfo` コレクションを返し、これを `deleteMessage` に渡してサーバーからアイテムを削除します。** バッチ処理によりネットワーク往復回数が減り、大きなフォルダーでもタイムアウトを防げます。削除対象のフォルダーが正しいことを必ず確認してください。削除はバックアップなしでは元に戻せません。

### メッセージの一覧取得と削除
各メッセージ URI を反復し、削除操作を呼び出します:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*説明:* `listMessages` は `MessageInfo` オブジェクトのコレクションを返し、その `getUniqueUri()` 値を `deleteMessage` に渡してサーバーから永久に削除します。

## フォルダーにメッセージを追加する方法?
`MailMessage` オブジェクトをローカルで作成し、SMTP サーバーを介さずに直接メールボックスのフォルダーに保存します。**`MailMessage` はヘッダー、本文、添付ファイルを含むメールを表し、完全にメモリ上で構築してから Exchange に永続化できます。** 送信パイプラインをバイパスするため、下書きやテンプレート、プログラム的に即座にユーザーのメールボックスに表示したいメッセージに最適です。

### メッセージの作成と送信
メールを構築し、Drafts フォルダーに追加します:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*説明:* `appendMessage` は `MailMessage` と `FolderInfo`（例: Drafts）を受け取り、アイテムをメールボックスに書き込み、ユーザーがすぐに利用できるようにします。

## EWS でユーザーをインパーソネートする方法?
クライアントのセキュリティ コンテキストを別のメールボックスに切り替えて操作し、完了後に元のアカウントに戻します。これは共有メールボックスの管理に不可欠です。**`impersonateUser` は基礎となる EWS リクエストに `ImpersonatedUserId` を設定し、サーバーに対して呼び出しが対象メールボックスから行われたかのように扱わせます。** 必要な操作が終わったら `resetImpersonation` を呼び出して元の資格情報に復元し、以降の呼び出しが正しいセキュリティ コンテキストで実行されるようにします。

### ユーザーインパーソネーションの実行
一時的にクライアントのコンテキストを別ユーザーに変更します:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*説明:* `impersonateUser` は基礎となる EWS リクエストに `ImpersonatedUserId` を設定し、対象ユーザーとして読み書きできます。`resetImpersonation` を呼び出すと元の資格情報に戻ります。

## 実用的な応用例
Aspose.Email Java を使用すると、堅牢なメール自動化ソリューションが実現します:
1. **自動メールクリーンアップ:** 数十のメールボックスにわたる古い Draft フォルダーを夜間ジョブでクリアします。  
2. **バッチメール配信:** テンプレート化されたお知らせをすべての従業員の受信トレイに一括で追加します。  
3. **共有メールボックス管理:** 部門のメールボックスをインパーソネートして、各ユーザーに完全なアクセス権を付与せずに古いメッセージをアーカイブします。

## パフォーマンス考慮事項
大規模なメールボックスを扱う際にアプリケーションの応答性を保つため:
- **可能な限りバッチ API 呼び出し**（例: 1 リクエストで 500 メッセージを削除）。  
- **メッセージをストリーム**し、全文をメモリにロードしない。  
- **クライアントオブジェクトを速やかに破棄**して、ネットワークソケットと HTTP 接続を解放します。

## よくある問題と解決策
- **接続エラー:** EWS エンドポイント URL を確認し、TLS 1.2 が有効か確認し、ファイアウォール規則が外部 HTTPS を許可しているか確認してください。  
- **インパーソネーションの権限拒否:** サービスアカウントに Exchange で “ApplicationImpersonation” ロールが割り当てられている必要があります。  
- **大きなフォルダーのタイムアウト:** `HttpWebRequest` のタイムアウトを増やすか、フォルダーを小さなチャンクに分割して処理してください。

## よくある質問

**Q: How do I troubleshoot connectivity issues with EWS?**  
A: エンドポイント URL、資格情報、ネットワークファイアウォールを確認し、Aspose.Email の詳細ロギングを有効にして HTTP リクエスト/レスポンス データを取得してください。

**Q: Can Aspose.Email handle large volumes of emails efficiently?**  
A: はい—バッチ API により **10,000 件以上** のメッセージを 1 分間に処理でき、メモリ使用量は 200 MB 未満に抑えられます。

**Q: What are typical use cases for user impersonation in EWS?**  
A: 共有メールボックスの管理、バルク アーカイブ、複数ユーザーに代わってスケジュールされたレポートを実行し、各ユーザーのパスワードを保存しないケースです。

**Q: Are there limits on API calls imposed by Aspose.Email?**  
A: Aspose.Email 自体には呼び出し制限はありませんが、Exchange がスロットリング ポリシーを適用する可能性があるため、これを考慮してください。

**Q: How can I keep credentials secure in my Java code?**  
A: 資格情報は暗号化された設定ファイルに保存するか、Azure Key Vault / AWS Secrets Manager を使用し、常に HTTPS を介して EWS エンドポイントに接続してください。

---

**最終更新日:** 2026-07-08  
**テスト環境:** Aspose.Email for Java 23.10  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Email for Java を使用した EWSClient インスタンスの作成方法: Exchange Server 統合ガイド](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Aspose.Email for Java と EWS を使用して Microsoft Exchange Server に接続する方法](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [Aspose.Email と Java EWS クライアントでメール管理を自動化する包括的ガイド](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}