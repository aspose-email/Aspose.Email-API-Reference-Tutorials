---
date: '2025-12-20'
description: Aspose.Email for Java を使用して、MAPI カレンダー（Java）の作成方法、日次の繰り返しパターンの管理、例外の処理方法を学びましょう。
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: MAPI カレンダー（Java）を作成：毎日の繰り返しと例外
url: /ja/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 日次繰り返しと例外を持つ MAPI カレンダー Java の作成方法

繰り返しイベントを効率的に管理することは、特に例外や変更が必要な場合に難しいことがあります。このチュートリアルでは **create mapi calendar java** オブジェクトを作成し、日次繰り返しパターンを設定し、Aspose.Email for Java を使用して例外を追加する方法を学びます。アプリケーション内でスケジューリングタスクをシームレスに自動化する方法を習得できます。

## クイックアンサー
- **ライブラリは？** Aspose.Email for Java
- **主なタスクは？** 毎日の繰り返しと例外機能を備えたMAPIカレンダーを作成する
- **JDKは必須ですか？** Java16以上
- **例外にファイルを添付できますか？** はい。`MapiCalendarExceptionInfo`を使用します。
- **カレンダーはどこに保存されますか？** `PersonalStorage`経由のPSTファイルに保存されます。

### MAPI カレンダーとは？
MAPI（Messaging Application Programming Interface）カレンダーは、Microsoft Outlook やその他のメールクライアントが予定データを保存するために使用する標準フォーマットです。豊富な繰り返し規則、例外、添付ファイルをサポートしており、エンタープライズ向けのスケジューリングに最適です。

### Aspose.Email for Java を使う理由
Aspose.Email は純粋な Java API を提供し、Outlook に依存せずに MAPI オブジェクトの作成、変更、保存が可能です。これにより、サーバーサイドのスケジューリング機能を構築したり、PST ファイルを生成したり、複雑な繰り返しシナリオをプログラムで処理したりできます。

## 前提条件

開始する前に、以下の環境が整っていることを確認してください。
- **Aspose.Email ライブラリ**: バージョン 25.4 (またはそれ以降) – Maven 経由で入手可能、または直接ダウンロード可能です。
- **Java Development Kit (JDK)**: JDK16 以降。
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, or any Java‑compatible editor.

### 必要なライブラリと依存関係

Maven を使用して Aspose.Email をプロジェクトに組み込むには、`pom.xml` に次の依存関係を追加します。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンスの取得

Aspose.Email を使用するにはライセンスが必要です。
- **無料トライアル** – すべての機能を無料で試用できます。  
- **一時ライセンス** – 延長評価用にリクエストできます。  
- **フルライセンス** – 本番環境での導入に購入してください。

## Aspose.Email for Java のセットアップ

まず環境を設定します。

1. JDK 16 がインストールされ、`JAVA_HOME` が設定されていることを確認します。  
2. Maven 依存関係（または JAR のダウンロード）をプロジェクトに追加します。  

以下はライセンスファイルを読み込むための簡単なコードスニペットです。

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## 実装ガイド

### 毎日の繰り返しと例外設定を含む MAPI カレンダーの作成

#### 概要
この機能により、繰り返し予定を自動化しつつ、特定のインスタンスをスキップまたは変更できるようになります。

#### 実装手順

**1. イベント開始日の設定** 
シリーズ開始日時を決定します。

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI カレンダーオブジェクトの作成**
場所、件名、説明を設定します。

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 毎日の繰り返しパターンの定義** 
イベントを毎日繰り返すように構成します。

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 繰り返しに例外を追加する**  
除外（または変更）したい日付を指定します。

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### カレンダー例外へのファイルの添付

#### 概要
例外インスタンスに対して、議事録などの補足文書を添付できます。

**1. ファイルを作成して添付する**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### MAPIカレンダーをPSTファイルに保存する

#### 概要

カレンダーを PST ファイルに永続化し、Outlook や他のクライアントで読み取れるようにします。

**1. カレンダーを作成してPSTファイルに保存する**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 実用的なアプリケーション
- **企業スケジューリング** – 会議シリーズを自動化し、祝日を自動的に除外します。  
- **プロジェクト管理** – 定期的なマイルストーンを追跡し、必要に応じて日付をシフトします。  
- **イベントプランニング** – 複数日にわたるカンファレンスで、セッションのキャンセルや再スケジュールを管理します。

### 統合の可能性
Aspose.Email を CRM プラットフォーム、タスク管理 API、またはカスタムワークフローエンジンと組み合わせて、エンドツーエンドの自動化を実現できます。

## パフォーマンスに関する考慮事項
- **リソースの破棄** – `PersonalStorage` の `dispose()` を必ず呼び出してファイルハンドルを解放します。  
- **ストリームの使用** –`ByteArrayOutputStream` やファイルストリームを使用し、PST 全体をメモリに読み込むのを回避します。  
- **非同期操作** – 大量のカレンダー生成はバックグラウンドスレッドで実行し、UI の応答性を保ちます。

## まとめ

本ガイドに従うことで、**create mapi calendar java** オブジェクトを日次繰り返しで作成し、例外を追加し、ファイルを添付し、すべてを PST ファイルに保存する方法が分かります。これらの機能により、Outlook に直接触れることなく堅牢なスケジューリング機能を構築できます。

### 次のステップ

- 週次または月次の繰り返しパターンを試してみてください。  
- 参加者、リマインダー、カテゴリなどの追加 MAPI プロパティを探索してください。  
- Aspose.Email の包括的な API ドキュメントを確認し、より高度なシナリオに挑戦してください。

## よくある質問

**Q: ライブラリはタイムゾーンを考慮した予定をサポートしていますか？**
 
A: はい、`MapiCalendar` の `StartTimeZone` と `EndTimeZone` プロパティを設定できます。

**Q: 定期的な予定から1つの予定をプログラムで削除できますか？**
 
A: 繰り返しパターンの `DeletedInstanceDates` コレクションを使用して、特定の日付を除外としてマークできます。

**Q: Aspose.Email で作成する PST ファイルのサイズに制限はありますか？**
  
A: PST ファイルは Unicode 形式の制限（デフォルトで最大 2 GB）に従いますが、`PersonalStorage` 設定でより大きなサイズに構成可能です。

**Q: 会議出席依頼に出席者を追加するにはどうすればよいですか？**
 
A: `MapiRecipient` オブジェクトを作成し、`RecipientType` を `MapiRecipientType.MAPI_TO` に設定して、`MapiMessage` の `Recipients` コレクションに追加します。

**Q: 予定だけでなく、定期的なタスクもサポートされていますか？**
 
A: はい、Aspose.Email は同様の繰り返し機能を持つ `MapiTask` も提供しています。

## リソース
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)（ドキュメント）  
- [Download Aspose.Email](https://releases.aspose.com/email/java/)（ダウンロード）  
- [Purchase a License](https://purchase.aspose.com/buy)（ライセンス購入）  
- [Free Trial Version](https://releases.aspose.com/email/java/)（無料トライアル）  
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)（一時ライセンス申請）  
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)（サポートフォーラム）



---

**最終更新日:** 2025年12月20日
**テスト環境:** Aspose.Email for Java 25.4 (JDK16)
**作成者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
