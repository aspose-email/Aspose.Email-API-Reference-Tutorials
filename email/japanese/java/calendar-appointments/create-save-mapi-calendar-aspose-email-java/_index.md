---
date: '2026-01-01'
description: Aspose.Email for Java を使用して MAPI カレンダー（Java）を作成し、カレンダーを PST に保存する方法を学びましょう。コード、繰り返し設定、受信者を含むステップバイステップのガイドです。
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Aspose.Email を使用した Java で MAPI カレンダーを作成する方法 – カレンダーを PST に保存
url: /ja/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email を使用して MAPI calendar java を作成する方法 – カレンダーを PST に保存

## はじめに

Java アプリケーションでカレンダー自動化を効率化したいですか？ **Aspose.Email for Java** を使用すると、**create MAPI calendar java** アイテムを作成し、繰り返しパターンを定義し、参加者を追加し、**save calendar to PST** ファイルを数行のコードで保存できます。このチュートリアルでは、ライブラリの設定から配布可能な完全なカレンダーエントリの生成まで、全工程を案内します。

### 学べること
- Aspose.Email を使用して **create MAPI calendar java** イベントを作成する方法。  
- 日次、週次、またはカスタムの繰り返しパターンを設定する。  
- カレンダー招待に受信者（主催者、参加者）を追加する。  
- Outlook 互換性のために **saving calendar to PST** でカレンダーアイテムを永続化する。  

さあ、開発環境を整えて始めましょう。

## クイック回答
- **どのライブラリですか？** Aspose.Email for Java  
- **主な目的は？** Create MAPI calendar java と **save calendar to PST**  
- **前提条件は？** Java 8+, Maven, Aspose.Email ライセンス  
- **典型的な実装時間は？** 基本的なイベントで 10‑15 分  
- **繰り返しを追加できますか？** はい – 日次、週次、月次など。  

## Java における MAPI カレンダーとは何ですか？

MAPI（Messaging Application Programming Interface）カレンダーオブジェクトは、Outlook 互換の会議または予定を表します。Aspose.Email を使用すると、これらのオブジェクトをプログラムで構築でき、Exchange、Outlook、または PST ファイルを使用する任意のクライアントとのシームレスな統合が可能です。

## カレンダー自動化に Aspose.Email を使用する理由
- **Full Outlook compatibility** – 生成されたアイテムは Outlook、OWA、モバイルクライアントで動作します。  
- **Rich recurrence support** – 日次、週次、月次、カスタムパターンを標準でサポート。  
- **No external dependencies** – 純粋な Java ライブラリで、COM 相互運用は不要です。  
- **High performance** – 大規模な PST ファイルやバルク操作を効率的に処理。  

## 前提条件

開始する前に、以下が揃っていることを確認してください。

### 必要なライブラリ
- **Aspose.Email for Java**: バージョン 25.4 以上。

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

Aspose.Email は無料トライアルを提供していますが、ライセンスを取得するとすべての機能が使用可能になります:

- **Free Trial**: 30 日間制限なくテスト可能。  
- **Temporary License**: 追加時間が必要な場合は [Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) からリクエストしてください。  
- **Purchase**: 永続ライセンスは [購入ページ](https://purchase.aspose.com/buy) から購入できます。

### 基本的な初期化

依存関係を追加したら、ライセンスファイルでライブラリを初期化します:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 実装ガイド

設定が完了したので、**create MAPI calendar java** と **save calendar to PST** を行いましょう。

### 繰り返し付き MAPI カレンダーの作成

#### 概要

カレンダーイベントを作成し、日次の繰り返しを適用し、参加者を追加し、最後に PST ファイルに保存します。

#### ステップバイステップ実装

1. **日付と繰り返しパターンの初期化**  

   First, define the start time and set a daily recurrence:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` は繰り返しの詳細を保持します。`MapiCalendarDailyRecurrencePattern` を使用して日次パターンを選択します。

2. **受信者の設定**  

   Add the people who should receive the meeting invitation:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` は各参加者を格納します。`MAPI_TO` は主要受信者としてマークします。

3. **MAPI カレンダーアイテムの作成**  

   Build the calendar object with all required details:

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

   *Explanation*: コンストラクタは主催者、件名、場所、開始/終了時間、説明、受信者リスト、繰り返しを受け取ります。

4. **PST ファイルへの保存**  

   Finally, persist the calendar by **saving calendar to PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` は新しい PST ファイルを生成し、`addMapiMessageItem` はカレンダーエントリを "Calendar" フォルダーに挿入します。

### トラブルシューティングのヒント
- ライセンスパスを確認してください。無効なライセンスは機能を制限します。  
- 受信者のメールアドレスが正しくフォーマットされていることを確認し、招待失敗を防ぎます。  
- 操作後に PST を (`pst.dispose()`) 閉じて、ファイルハンドルを解放してください。

## 実用的な適用例

**create MAPI calendar java** と **save calendar to PST** が有効に機能する一般的なシナリオは次のとおりです:

1. **Automated Meeting Scheduling** – 手動作業なしでプロジェクトチーム向けに繰り返し会議招待を生成。  
2. **Event Management Platforms** – カンファレンスセッションを Outlook 互換のカレンダーアイテムとしてエクスポート。  
3. **CRM Integration** – CRM システムから顧客の予定を PST ファイル経由で直接 Outlook に同期。

## パフォーマンス上の考慮点
- **Resource Management**: 使用後に `PersonalStorage` オブジェクトを破棄し、ファイルロックを防止。  
- **Batch Processing**: 大量の場合は非同期またはチャンク単位でカレンダーアイテムを処理し、メモリ使用量を抑えます。

## 結論

これで、Aspose.Email を使用して **create MAPI calendar java** オブジェクトを作成し、繰り返しを設定し、参加者を追加し、**save calendar to PST** する方法を学びました。この手法により、Java アプリケーションは Outlook 互換の高度なスケジューリングワークフローを自動化できます。

さらに詳しくは、公式の [Aspose.Email Documentation](https://reference.aspose.com/email/java/) をご覧ください。

## FAQ セクション

### Q: 週次の繰り返しパターンを作成できますか？
- **A**: はい！`MapiCalendarWeeklyRecurrencePattern` を使用して週次の繰り返しを定義できます。

### Q: イベントの繰り返しで例外を処理するには？
- **A**: 繰り返しオブジェクトの `setExceptions()` を呼び出し、パターンから外れる日付を指定します。

### Q: 既存のカレンダーアイテムを更新できますか？
- **A**: もちろんです。PST からアイテムをロードし、プロパティを変更して再度保存します。

### Q: PST ファイルを暗号化できますか？
- **A**: はい、PST を作成する際に `PersonalStorage` にパスワードを設定できます。

### Q: カレンダーイベントに添付ファイルを追加するには？
- **A**: 保存前に `calendar.getAttachments().addFileAttachment("path/to/file")` を使用します。

## リソース
- [Aspose.Email ドキュメント](https://reference.aspose.com/email/java/)  
- [Aspose.Email for Java のダウンロード](https://releases.aspose.com/email/java/)  
- [ライセンスの購入](https://purchase.aspose.com/buy)  
- [無料トライアル版](https://releases.aspose.com/email/java/)  
- [一時ライセンスのリクエスト](https://purchase.aspose.com/temporary-license/)  
- [Aspose サポートフォーラム](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-01  
**テスト環境:** Aspose.Email for Java 25.4 (JDK 16)  
**作者:** Aspose