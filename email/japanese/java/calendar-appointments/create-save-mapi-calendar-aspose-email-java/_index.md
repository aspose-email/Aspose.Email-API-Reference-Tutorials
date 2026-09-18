---
date: '2026-09-17'
description: Aspose.Email for Java を使用して Outlook カレンダー PST をエクスポートする方法を学びます。MAPI カレンダー
  アイテムの作成、繰り返し設定、参加者の追加、PST への保存が可能です。
keywords:
- export outlook calendar pst
- how to export pst
- how to add recurrence
- how to add attendees
- save calendar to pst
lastmod: '2026-09-17'
og_description: Aspose.Email for Java を使用して Outlook カレンダー PST をエクスポートします。MAPI カレンダー
  アイテムの作成、繰り返し設定、参加者の追加、数分で PST に保存する方法を学びます。
og_image_alt: Guide to exporting Outlook calendar PST files with Aspose.Email for
  Java
og_title: Aspose.Email – Java を使用した Outlook カレンダー PST のエクスポート
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  headline: Export Outlook calendar PST with Aspose.Email – Java
  type: TechArticle
- description: Learn how to export Outlook calendar PST using Aspose.Email for Java
    – create MAPI calendar items, set recurrence, add attendees, and save to PST.
  name: Export Outlook calendar PST with Aspose.Email – Java
  steps:
  - name: '**Initialize date and recurrence pattern**'
    text: '**Initialize date and recurrence pattern**'
  - name: '**Set up recipients**'
    text: '**Set up recipients**'
  - name: '**Create the MAPI calendar item**'
    text: '**Create the MAPI calendar item**'
  - name: '**Save to PST file**'
    text: '**Save to PST file**'
  - name: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
    text: '**Automated meeting scheduling** – Generate recurring meeting invites for
      project teams without manual effort.'
  - name: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
    text: '**Event management platforms** – Export conference sessions as Outlook‑compatible
      calendar items.'
  - name: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
    text: '**CRM integration** – Sync customer appointments from a CRM system directly
      into Outlook via PST files.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java
    question: Which library?
  - answer: Export Outlook calendar PST and **save calendar to PST**
    question: Primary goal?
  - answer: Java 8+, Maven, Aspose.Email license
    question: Prerequisites?
  - answer: 10‑15 minutes for a basic event
    question: Typical implementation time?
  - answer: Yes – daily, weekly, monthly, etc.
    question: Can I add recurrence?
  type: FAQPage
tags:
- export outlook calendar pst
- Aspose.Email
- Java calendar automation
title: Aspose.Email – Java を使用した Outlook カレンダー PST のエクスポート
url: /ja/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email – Java を使用した Outlook カレンダー PST のエクスポート

## はじめに

Java アプリケーションでカレンダー自動化を効率化し、**export Outlook calendar PST** ファイルが必要ですか？ **Aspose.Email for Java** を使用すれば、**create MAPI calendar Java** アイテムを作成し、再発パターンを定義し、参加者を追加し、**save calendar to PST** を数行のコードで実行できます。このチュートリアルでは、ライブラリの設定から配布可能な完全なカレンダーエントリの生成まで、全工程を案内します。

### 学べること
- Aspose.Email を使用して **create MAPI calendar Java** イベントを作成する方法。  
- 日次、週次、またはカスタムの再発パターンを設定する。  
- カレンダー招待に受信者（主催者、参加者）を追加する。  
- **saving calendar to PST** によってカレンダーアイテムを永続化し、Outlook 互換性を確保する。  
- 再利用可能なコードで **automate meeting scheduling** を行う方法。

## クイック回答
- **どのライブラリですか？** Aspose.Email for Java  
- **主な目的は？** Export Outlook calendar PST and **save calendar to PST**  
- **前提条件は？** Java 8+, Maven, Aspose.Email license  
- **実装にかかる時間は？** 10‑15 minutes for a basic event  
- **再発を追加できますか？** Yes – daily, weekly, monthly, etc.

## Outlook カレンダー PST のエクスポート

このセクションでは、**export Outlook calendar PST** ファイルを作成できるエンドツーエンドのフローに焦点を当てます。MAPI カレンダーオブジェクトを作成した後、最終ステップは Outlook が直接読み取れる PST ファイルに保存することです。

## カレンダー自動化に Aspose.Email を使用する理由は？

Aspose.Email を使用して Outlook カレンダー PST をエクスポートすると、信頼性の高いサーバーサイドの方法で Outlook 互換のアイテムを生成できます。ライブラリは **50+ input and output formats** をサポートし、2 GB を超える PST ファイルを処理でき、典型的なサーバーハードウェアで 1 分間に数千件のカレンダーエントリを処理します。組み込みの再発エンジンは日次、週次、月次、カスタムパターンをカバーし、手動の日付計算の必要性を排除します。

## 前提条件

開始する前に、以下が揃っていることを確認してください：

### 必要なライブラリ
- **Aspose.Email for Java**: バージョン 25.4 以降 (Java 8‑21 をサポート)

### 環境設定要件
- IntelliJ IDEA や Eclipse などの Java IDE。  
- 依存関係管理のために Maven がインストールされていること。

### 知識の前提条件
- 基本的な Java プログラミングスキル。  
- オブジェクト指向の概念に慣れていること。

## Aspose.Email for Java の設定

`pom.xml` に Aspose.Email の Maven 依存関係を追加します:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得

Aspose.Email は無料トライアルを提供していますが、ライセンスを取得するとすべての機能が利用可能になります:
- **Free trial**: 30 日間制限なしでテストできます。  
- **Temporary license**: 追加時間が必要な場合は [Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) からリクエストしてください。  
- **Purchase**: [購入ページ](https://purchase.aspose.com/buy) から永続ライセンスを購入してください。

### 基本的な初期化

依存関係を追加したら、ライセンスファイルでライブラリを初期化します:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 実装ガイド

セットアップが完了したので、**create MAPI calendar Java** と **save calendar to PST** を行いましょう。

### 再発付き MAPI カレンダーの作成

#### 概要

カレンダーイベントを作成し、日次の再発を適用し、参加者を追加し、最終的に PST ファイルに保存します。

#### ステップバイステップ実装

1. **日付と再発パターンの初期化**  

   `MapiCalendarEventRecurrence` はカレンダーアイテムの再発詳細を保持するクラスです。  
   `MapiCalendarDailyRecurrencePattern` はシンプルな日次繰り返しスケジュールを定義します。  
   まず、開始時刻を定義し、日次再発を設定します：

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

2. **受信者の設定**  

   `MapiRecipientCollection` は会議に招待された人々のリストを表します。  
   `MAPI_TO` は受信者を主要な参加者としてマークするフラグです。  
   会議招待を受け取るべき人々を追加します：

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

3. **MAPI カレンダーアイテムの作成**  

   `MapiMessage` クラス（ここではカレンダーオブジェクトとして使用）は、主催者、件名、場所、開始/終了時刻、説明、受信者リスト、再発など、すべてのイベントプロパティをカプセル化します。  
   必要な詳細をすべて設定してカレンダーオブジェクトを構築します：

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

4. **PST ファイルへの保存**  

   `PersonalStorage` は PST ファイルの作成と操作のための Aspose.Email のトップレベル API です。  
   `addMapiMessageItem` は指定フォルダーに MAPI メッセージ（カレンダーアイテムを含む）を挿入します。  
   最後に、**save calendar to PST** によってカレンダーを永続化します：

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

### トラブルシューティングのヒント
- ライセンスパスを確認してください。無効なライセンスは機能を制限します。  
- 受信者のメールアドレスが正しくフォーマットされていることを確認し、招待失敗を防ぎます。  
- 操作後に PST (`pst.dispose()`) を閉じてファイルハンドルを解放してください。

## 実用的な応用例

以下は **create MAPI calendar Java** と **save calendar to PST** が活躍する一般的なシナリオです：
1. **Automated meeting scheduling** – プロジェクトチーム向けに手動作業なしで定期的な会議招待を生成します。  
2. **Event management platforms** – カンファレンスセッションを Outlook 互換のカレンダーアイテムとしてエクスポートします。  
3. **CRM integration** – CRM システムから顧客の予約を直接 PST ファイル経由で Outlook に同期します。

## パフォーマンス上の考慮点
- **Resource management**: 使用後に `PersonalStorage` オブジェクトを破棄してファイルロックを防止します。  
- **Batch processing**: 大量の場合はカレンダーアイテムを非同期またはチャンクで処理し、メモリ使用量を低く保ちます。  
- **Scalability**: Aspose.Email は 2 GB を超える PST ファイルにも書き込み可能で、メモリ消費は 200 MB 未満に抑えられます。

## 結論

これで、MAPI calendar Java オブジェクトを作成し、再発を設定し、参加者を追加し、Aspose.Email を使用して **export Outlook calendar PST** と **save calendar to PST** を行う方法を学びました。このアプローチにより、Java アプリケーションは Outlook 互換の高度なスケジューリングワークフローを自動化できます。  
さらに詳しくは、公式の [ドキュメント](https://reference.aspose.com/email/java/) をご覧ください。

## FAQ セクション

### Q: 週次の再発パターンを作成できますか？
- **A**: はい！ `MapiCalendarWeeklyRecurrencePattern` を使用して週次の繰り返しを定義します。

### Q: イベントの再発で例外を処理するには？
- **A**: 再発オブジェクトで `setExceptions()` を呼び出し、パターンから外れる日付を指定します。

### Q: 既存のカレンダーアイテムを更新できますか？
- **A**: もちろんです。PST からアイテムをロードし、プロパティを変更して再度保存します。

### Q: PST ファイルを暗号化できますか？
- **A**: はい、Aspose.Email では PST を作成する際に `PersonalStorage` にパスワードを設定できます。

### Q: カレンダーイベントに添付ファイルを追加するには？
- **A**: 保存する前に `calendar.getAttachments().addFileAttachment("path/to/file")` を使用して添付ファイルを追加します。

## リソース
- [Aspose.Email ドキュメント](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java のダウンロード](https://releases.aspose.com/email/java/)
- [ライセンスの購入](https://purchase.aspose.com/buy)
- [無料トライアル版](https://releases.aspose.com/email/java/)
- [一時ライセンスのリクエスト](https://purchase.aspose.com/temporary-license/)
- [Aspose サポートフォーラム](https://forum.aspose.com/c/email/10)

---

**最終更新日:** 2026-09-17  
**テスト環境:** Aspose.Email for Java 25.4 (JDK 16)  
**作者:** Aspose

## 関連チュートリアル
- [Aspose.Email for Java を使用した Outlook PST ファイルの作成と管理](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Aspose.Email for Java で PST ファイルを作成する方法](/email/java/email-parsing-analysis/aspose-email-java-create-pst-guide/)
- [Aspose.Email を使用した Java カレンダーアイテムの作成](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}