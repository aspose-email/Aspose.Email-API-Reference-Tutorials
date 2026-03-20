---
date: '2026-03-20'
description: Aspose.Email for Java を使用して、日次の繰り返しと例外を持つ Outlook カレンダーを Java で作成し、カレンダーを
  PST に保存する方法を学びましょう。
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Outlook カレンダーを Java で作成し、日次の繰り返しと例外を設定する
url: /ja/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook カレンダー Java を日次の繰り返しと例外付きで作成する方法

繰り返しイベントを効率的に管理することは困難な場合があります。特に、日次の繰り返しパターンと時折の例外をサポートする **outlook calendar java** が必要なときはなおさらです。このチュートリアルでは、Outlook カレンダー Java オブジェクトの作成方法、日次繰り返しの設定、例外インスタンスの追加、そして最終的に Aspose.Email for Java を使用して **save calendar to PST** する方法を学びます。最後には、任意の Java ベースのスケジューリングサービスに組み込める再利用可能なコードスニペットが手に入ります。

## クイック回答
- **どのライブラリですか？** Aspose.Email for Java  
- **主なタスクは？** Create an Outlook calendar Java with daily recurrence and exceptions  
- **前提条件の JDK は？** Java 16 or higher  
- **例外にファイルを添付できますか？** Yes, using `MapiCalendarExceptionInfo`  
- **カレンダーはどこに保存されますか？** In a PST file via `PersonalStorage`

## Outlook カレンダー Java とは？

Outlook カレンダー Java オブジェクト（MAPI カレンダーとして実装）は、Microsoft Outlook の予定と同じ標準に従います。リッチな繰り返しルール、例外処理、出席者、添付ファイルを保存でき、エンタープライズ向けスケジューリングに最適です。

## なぜ Aspose.Email for Java を使用するのか？

Aspose.Email は、Outlook をインストールせずに MAPI オブジェクトを操作できる純粋な Java API を提供します。この **aspose email tutorial java** アプローチにより、サーバー側で PST ファイルを生成したり、会議シリーズを自動化したり、繰り返しロジックを完全に制御したりできます。

## 前提条件

Before we begin, ensure you have the following setup:
- **Aspose.Email Library**: バージョン 25.4（またはそれ以降） – Maven または直接ダウンロードで利用可能。  
- **Java Development Kit (JDK)**: JDK 16 以上。  
- **IDE**: IntelliJ IDEA、Eclipse、NetBeans、または任意の Java 対応エディタ。

### 必要なライブラリと依存関係

Maven を使用して Aspose.Email をプロジェクトに統合するには、`pom.xml` に以下の依存関係を追加します：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得

To use Aspose.Email, you'll need a license:
- **Free Trial** – 無料で全機能を試用できます。  
- **Temporary License** – 長期評価のためにリクエストできます。  
- **Full License** – 本番環境での導入のために購入します。

## Aspose.Email for Java の設定

First, set up your environment:

1. JDK 16 がインストールされ、`JAVA_HOME` が設定されていることを確認します。  
2. Maven の依存関係（または JAR をダウンロード）をプロジェクトに追加します。  

以下は、ライセンスファイルをロードする方法を示す小さなコードスニペットです：

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

### Outlook カレンダー Java を日次の繰り返しと例外付きで作成する

#### 概要
この機能により、繰り返し予定を自動化しつつ、特定のインスタンスをスキップまたは変更することができます。

#### 手順実装

**1. イベント開始日を設定する**  
シリーズの開始時期を決定します：

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI カレンダーオブジェクトを作成する**  
場所、件名、説明を指定します：

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 日次繰り返しパターンを定義する**  
イベントが毎日繰り返すように設定します：

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 繰り返しに例外を追加する**  
除外（または変更）すべき日付を指定します：

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

### カレンダー例外にファイルを添付する

#### 概要
任意の例外インスタンスに、サポート文書（例：議題）を添付できます。

**1. ファイルを作成して添付する**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Outlook カレンダー Java を PST に保存する (save calendar to pst)

#### 概要
Outlook やその他のクライアントが読み取れるように、カレンダーを PST ファイルに永続化します。

**1. カレンダーを作成し、PST に保存する**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 実用的な応用例
- **Corporate Scheduling** – 会議シリーズを自動化し、祝日を自動的にスキップします。  
- **Project Management** – 定期的なマイルストーンを追跡し、時折の日付変更に対応します。  
- **Event Planning** – 複数日にわたるカンファレンスで、キャンセルや再スケジュールされたセッションを管理します。

### 統合の可能性
Aspose.Email を CRM プラットフォーム、タスク管理 API、またはカスタムワークフローエンジンと組み合わせて、エンドツーエンドの自動化を実現します。

## パフォーマンス上の考慮点
- **Dispose Resources** – `PersonalStorage` の `dispose()` を必ず呼び出してファイルハンドルを解放します。  
- **Stream Usage** – メモリに PST 全体をロードしないよう、`ByteArrayOutputStream` またはファイルストリームを使用します。  
- **Async Operations** – 大量のカレンダー生成の場合、作成ロジックをバックグラウンドスレッドで実行し、UI の応答性を保ちます。

## 結論
このガイドに従うことで、日次繰り返しを持つ **create outlook calendar java** オブジェクトの作成方法、例外の追加、ファイルの添付、そして **save calendar to PST** の方法が分かります。これらの機能により、Outlook に直接触れることなく堅牢なスケジューリング機能を構築できます。

### 次のステップ
- 週次または月次の繰り返しパターンを試す。  
- 出席者、リマインダー、カテゴリなどの追加 MAPI プロパティを調査する。  
- より高度なシナリオのために、Aspose.Email の包括的な API ドキュメントを確認する。

## よくある質問

**Q: ライブラリはタイムゾーン対応の予定をサポートしていますか？**  
A: はい、`MapiCalendar` の `StartTimeZone` と `EndTimeZone` プロパティを設定できます。

**Q: 繰り返しシリーズから単一のインスタンスをプログラムで削除できますか？**  
A: 繰り返しパターンの `DeletedInstanceDates` コレクションを使用して、特定の日付を削除済みとしてマークします。

**Q: Aspose.Email で作成した PST ファイルのサイズに制限はありますか？**  
A: PST ファイルは Unicode 形式の制限に従い（デフォルトで最大 2 GB）、`PersonalStorage` の設定でより大きなサイズに構成可能です。

**Q: 会議リクエストに出席者を追加するには？**  
A: `MapiRecipient` オブジェクトを作成し、`RecipientType` を `MapiRecipientType.MAPI_TO` に設定して、`MapiMessage` の `Recipients` コレクションに追加します。

**Q: 繰り返しタスク（予定だけでなく）をサポートしていますか？**  
A: はい、Aspose.Email は同様の繰り返し機能を持つ `MapiTask` も提供しています。

**Q: このガイドを aspose email tutorial java シリーズの一部として使用できますか？**  
A: もちろんです。この手順は、カレンダー作成を扱うすべての Aspose.Email Java チュートリアルの核心部分です。

## リソース
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**最終更新日:** 2026-03-20  
**テスト環境:** Aspose.Email for Java 25.4 (JDK 16)  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}