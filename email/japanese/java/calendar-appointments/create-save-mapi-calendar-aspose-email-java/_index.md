---
date: '2026-03-20'
description: Aspose.Email for Java を使用して Outlook カレンダー PST をエクスポートする方法を学びましょう – MAPI
  カレンダー アイテムを作成し、繰り返し設定を行い、出席者を追加し、PST に保存します。
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Aspose.Email を使用した Outlook カレンダー PST のエクスポート – Java
url: /ja/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email を使用した Outlook カレンダー PST のエクスポート – Java

## Introduction

Java アプリケーションでカレンダー自動化を効率化し、**Outlook カレンダー PST** ファイルをエクスポートしたいですか？ **Aspose.Email for Java** を使用すれば、**create MAPI calendar Java** アイテムを作成し、繰り返しパターンを定義し、出席者を追加し、数行のコードだけで **save calendar to PST** が可能です。このチュートリアルでは、ライブラリのセットアップから配布可能な完全なカレンダーエントリの生成まで、全工程を順を追って解説します。

### What You'll Learn
- Aspose.Email を使用して **create MAPI calendar Java** イベントを作成する方法。  
- 毎日、毎週、またはカスタムの繰り返しパターンを設定する方法。  
- カレンダー招待に受信者（主催者、出席者）を追加する方法。  
- Outlook 互換性のために **saving calendar to PST** でカレンダーアイテムを永続化する方法。  
- 再利用可能なコードで **automate meeting scheduling** を実現する方法。

## Quick Answers
- **Which library?** Aspose.Email for Java  
- **Primary goal?** Export Outlook calendar PST and **save calendar to PST**  
- **Prerequisites?** Java 8+, Maven, Aspose.Email license  
- **Typical implementation time?** 10‑15 分で基本的なイベントを作成  
- **Can I add recurrence?** はい – 毎日、毎週、毎月など

## Export Outlook calendar PST

このセクションでは、**export Outlook calendar PST** ファイルを実現するエンドツーエンドのフローに焦点を当てます。MAPI カレンダーオブジェクトを作成した後、最終ステップは Outlook が直接読み取れる PST ファイルに格納することです。

## Why use Aspose.Email for calendar automation?

- **Full Outlook compatibility** – 生成されたアイテムは Outlook、OWA、モバイルクライアントで動作します。  
- **Rich recurrence support** – 毎日、毎週、毎月、カスタムパターンを標準でサポート。  
- **No external dependencies** – 純粋な Java ライブラリで、COM 相互運用は不要です。  
- **High performance** – 大容量 PST ファイルやバルク操作を効率的に処理。  
- **Automate meeting scheduling** – バッチジョブや Web サービスに組み込んで、数百件の招待を自動作成。

## Prerequisites

開始する前に、以下を確認してください。

### Required Libraries
- **Aspose.Email for Java**: バージョン 25.4 以降。

### Environment Setup Requirements
- IntelliJ IDEA や Eclipse などの Java IDE。  
- 依存関係管理のために Maven がインストールされていること。

### Knowledge Prerequisites
- 基本的な Java プログラミングスキル。  
- オブジェクト指向の概念に慣れていること。

## Setting Up Aspose.Email for Java

`pom.xml` に Aspose.Email の Maven 依存関係を追加します。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

Aspose.Email は無料トライアルを提供していますが、ライセンスを取得するとすべての機能が解放されます。

- **Free Trial**: 30 日間制限なしでテスト可能。  
- **Temporary License**: 追加の期間が必要な場合は [Aspose のウェブサイト](https://purchase.aspose.com/temporary-license/) からリクエストしてください。  
- **Purchase**: 永続ライセンスは [購入ページ](https://purchase.aspose.com/buy) から入手できます。

### Basic Initialization

依存関係を追加したら、ライセンスファイルでライブラリを初期化します。

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Implementation Guide

環境が整ったので、**create MAPI calendar Java** と **save calendar to PST** を実装しましょう。

### Create a MAPI Calendar with Recurrence

#### Overview

カレンダーイベントを作成し、毎日の繰り返しを適用し、出席者を追加し、最終的に PST ファイルに保存します。

#### Step‑by‑Step Implementation

1. **Initialize Date and Recurrence Pattern**  

   まず開始時刻を定義し、毎日繰り返すパターンを設定します。

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Explanation*: `MapiCalendarEventRecurrence` が繰り返しの詳細を保持します。`MapiCalendarDailyRecurrencePattern` を使用して日次パターンを選択します。

2. **Set Up Recipients**  

   会議招待を受け取る人を追加します。

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Explanation*: `MapiRecipientCollection` が各出席者を格納し、`MAPI_TO` が主要受信者としてマークします。

3. **Create the MAPI Calendar Item**  

   必要なすべての情報でカレンダーオブジェクトを構築します。

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

   *Explanation*: コンストラクタは主催者、件名、場所、開始/終了時刻、説明、受信者リスト、繰り返し情報を受け取ります。

4. **Save to PST File**  

   最後に **saving calendar to PST** でカレンダーを永続化します。

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Explanation*: `PersonalStorage.create` が新しい PST ファイルを生成し、`addMapiMessageItem` が「Calendar」フォルダーにカレンダーエントリを挿入します。

### Troubleshooting Tips
- ライセンスパスを確認してください。無効なライセンスは機能を制限します。  
- 受信者のメールアドレスが正しい形式か確認し、招待失敗を防ぎます。  
- 操作後は PST を (`pst.dispose()`) 閉じてファイルハンドルを解放します。

## Practical Applications

**create MAPI calendar Java** と **save calendar to PST** が有効に機能する一般的なシナリオは次のとおりです。

1. **Automated Meeting Scheduling** – プロジェクトチーム向けに繰り返し会議招待を自動生成。  
2. **Event Management Platforms** – カンファレンスセッションを Outlook 互換のカレンダーアイテムとしてエクスポート。  
3. **CRM Integration** – CRM システムからの顧客予約を PST ファイル経由で直接 Outlook に同期。

## Performance Considerations

- **Resource Management**: 使用後は `PersonalStorage` オブジェクトを必ず破棄し、ファイルロックを防止します。  
- **Batch Processing**: 大量処理の場合は非同期またはチャンク単位でカレンダーアイテムを処理し、メモリ使用量を抑えます。

## Conclusion

MAPI カレンダー Java オブジェクトを作成し、繰り返し設定や出席者追加を行い、Aspose.Email を使って **export Outlook calendar PST** と **save calendar to PST** を実現する方法を学びました。この手法により、Java アプリケーションは Outlook 互換の高度なスケジューリングワークフローを自動化できます。

さらに詳しくは公式 [documentation](https://reference.aspose.com/email/java/) をご覧ください。

## FAQ Section

### Q: Can I create weekly recurrence patterns?
- **A**: はい！`MapiCalendarWeeklyRecurrencePattern` を使用して週単位の繰り返しを定義できます。

### Q: How do I handle exceptions in event recurrence?
- **A**: 繰り返しオブジェクトの `setExceptions()` を呼び出し、パターンから外れる日付を指定します。

### Q: Is it possible to update an existing calendar item?
- **A**: もちろん可能です。PST からアイテムを読み込み、プロパティを変更して再度保存します。

### Q: Can I encrypt the PST file?
- **A**: はい、`PersonalStorage` 作成時にパスワードを設定して PST を暗号化できます。

### Q: What if I need to add attachments to the calendar event?
- **A**: 保存前に `calendar.getAttachments().addFileAttachment("path/to/file")` を使用して添付ファイルを追加します。

## Resources

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}