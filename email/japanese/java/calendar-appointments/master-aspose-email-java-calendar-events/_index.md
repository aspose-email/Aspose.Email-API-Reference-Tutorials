---
date: '2025-12-24'
description: Aspose.Email for Java を使用してカレンダーを PST にエクスポートする方法を学び、参加者の追加、開始日と終了日の設定、そして予定を効率的に管理する方法を含みます。
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Aspose.Email for Java を使用してカレンダーを PST にエクスポート
url: /ja/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java を使用したカレンダーの PST へのエクスポート

Efficiently **export calendar to PST** is a common requirement when building Java applications that need to share scheduling data with Outlook or other Microsoft products. In this tutorial you’ll see exactly how to create appointments, add attendees, define start and end dates, and finally save everything into a PST file—all using Aspose.Email for Java.

## Quick Answers
- **主な目的は何ですか？** Export calendar events to a PST file.  
- **必要なライブラリは何ですか？** Aspose.Email for Java (v25.4 以上)。  
- **ライセンスは必要ですか？** はい、有効な Aspose.Email ライセンスを使用すると評価制限が解除されます。  
- **参加者を追加できますか？** もちろんです – `MapiRecipientCollection` を使用します。  
- **サポートされている Java バージョンは？** JDK 16 以上。

## What is **export calendar to pst**?
Exporting a calendar to PST means converting in‑memory `MapiCalendar` objects into a Microsoft Outlook Personal Storage Table (PST). This file can be opened in Outlook, shared with colleagues, or imported into other systems that understand the PST format.

## Why use Aspose.Email for Java to export calendar to PST?
- **フル MAPI サポート** – Outlook をインストールせずに予定を作成、変更、保存できます。  
- **クロスプラットフォーム** – Windows、Linux、macOS で動作します。  
- **リッチな API** – 参加者、繰り返し、リマインダーなどを管理できます。  
- **パフォーマンス最適化** – 大量のイベントを低メモリフットプリントで処理できます。

## Prerequisites
- **ライブラリと依存関係**: Aspose.Email for Java バージョン 25.4 以上。  
- **環境**: JDK 16 以上、依存関係管理に Maven。  
- **知識**: 基本的な Java プログラミングと Maven の知識。

## How to set up Aspose.Email for Java
Add the Aspose.Email dependency to your `pom.xml`:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Unlock full functionality of Aspose.Email without evaluation limitations by acquiring a license:

1. **無料トライアル**: 一時ライセンスの取得のために [Aspose ダウンロードページ](https://releases.aspose.com/email/java/) を訪問してください。  
2. **一時ライセンス**: [購入ページ](https://purchase.aspose.com/temporary-license/) から申請してください。  
3. **ライセンス購入**: 長期利用のために [Aspose の購入ポータル](https://purchase.aspose.com/buy) から購入することを検討してください。

ライセンスを取得したら、アプリケーションで初期化してすべての機能を有効にします。

## How to **create appointment** (Create Calendar Event Java)

### Step 1: Define start and end dates (java calendar start date / java calendar end date)
The following method shows how to set the start and end dates for an appointment and return a `MapiCalendar` object:

```java
import com.aspose.email.MapiCalendar;
import java.util.Calendar;
import java.util.Date;

public MapiCalendar createAppointment() {
    Calendar cal = Calendar.getInstance();
    
    // Setting the start date
    cal.set(Calendar.YEAR, 2023);
    cal.set(Calendar.MONTH, Calendar.OCTOBER);
    cal.set(Calendar.DAY_OF_MONTH, 1);
    Date startDate = cal.getTime();
    
    // Setting the end date
    cal.set(Calendar.HOUR_OF_DAY, 10);
    Date endDate = cal.getTime();
    
    return new MapiCalendar("Conference Room", "Important Meeting",
        "Discuss project milestones and updates.", startDate, endDate);
}
```

*説明*: このスニペットは、特定の場所、件名、説明、および定義した **java calendar start date** / **java calendar end date** を持つ `MapiCalendar` を作成します。

## How to **add attendees** (how to add attendees)

### Step 2: Build the attendee list
Use `MapiRecipientCollection` to specify who should receive the meeting invitation:

```java
import com.aspose.email.MapiCalendar;
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;
import java.util.Date;

public MapiCalendar createMeetingWithAttendees(Date startDate, Date endDate) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    
    // Adding primary recipients
    attendees.add("attendee1@example.com", "John Doe", MapiRecipientType.MAPI_TO);
    attendees.add("attendee2@example.com", "Jane Smith", MapiRecipientType.MAPI_TO);
    
    return new MapiCalendar(
        "Main Office Boardroom",
        "Team Meeting",
        "Discuss quarterly goals.",
        startDate,
        endDate,
        "organizer@example.com",
        attendees
    );
}
```

*説明*: このコードは会議を作成し、主催者を設定し、**how to add attendees** リストを添付して全員が適切な招待状を受け取れるようにします。

## How to **export calendar to pst** (Create PST with calendar events)

### Step 3: Create a PST file and add the events
The method below demonstrates creating a Unicode PST file and storing both the simple appointment and the meeting with attendees:

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

public void createPSTWithCalendarEvents() {
    String pstFilePath = "/path/to/output/MapiCalendarToPST_out.pst";
    
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);

    MapiCalendar appointment = createAppointment();
    calendarFolder.addMapiMessageItem(appointment);
    
    Date startDate = new Date(); // Use actual dates from your event
    Date endDate = new Date();
    MapiCalendar meeting = createMeetingWithAttendees(startDate, endDate);
    calendarFolder.addMapiMessageItem(meeting);
}
```

*説明*: このスニペットは、PST コンテナを作成し、事前定義された「Calendar」フォルダーを追加し、以前に作成した `MapiCalendar` オブジェクトを挿入することで **exports calendar to PST** を実行します。

## Practical Applications
1. **ビジネススケジューリング** – 社内会議の作成と配布を自動化します。  
2. **イベント管理** – カンファレンス、ワークショップ、参加者リストを追跡します。  
3. **CRM 統合** – 予定を顧客関係ツールと同期します。  
4. **プロジェクト計画** – プロジェクトのマイルストーンをカレンダー項目として保存します。  
5. **リモートチームコラボレーション** – オフライン共有用に PST ファイルを生成します。

## Performance Considerations
- **不要なオブジェクトを破棄** してメモリを解放します。  
- **大規模な参加者リストには効率的なコレクションを選択** します。  
- **PST を頻繁にクエリする場合は、頻繁にアクセスするイベントをキャッシュ** します。

## Common Issues and Solutions
| 問題 | 解決策 |
|-------|----------|
| **PST ファイルが作成されない** | ターゲットディレクトリへの書き込み権限を確認し、フォルダー パスが存在することを確認してください。 |
| **参加者が招待を受け取らない** | `MapiRecipient` が `MapiRecipientType.MAPI_TO` を使用していること、主催者のメールが有効であることを確認してください。 |
| **日付の不一致** | `Calendar` を開始/終了日付に一貫して使用し、`java.util.Date` と他の日時ライブラリを変換せずに混在させないでください。 |

## Frequently Asked Questions

**Q: Aspose.Email for Java の使用を開始するにはどうすればよいですか？**  
A: 上記の Maven 依存関係を追加し、ライセンスを取得し、このガイドの手順に従ってカレンダーイベントを作成およびエクスポートします。

**Q: PST ファイル名と場所をカスタマイズできますか？**  
A: はい、`createPSTWithCalendarEvents()` の `pstFilePath` 変数をシステム上の任意の有効なパスに変更してください。

**Q: 予定に繰り返しパターンを追加できますか？**  
A: もちろんです – `MapiCalendar` は `RecurrencePattern` などの繰り返しプロパティを提供しており、保存前に設定できます。

**Q: Aspose.Email は PST 以外のカレンダー形式もサポートしていますか？**  
A: はい、適切な API メソッドを使用して iCalendar（`.ics`）やその他の形式にエクスポートできます。

**Q: 作成できる PST ファイルの最大サイズはどれくらいですか？**  
A: Unicode 形式（`FileFormatVersion.Unicode`）の場合、PST ファイルは最大 2 TB まで拡張可能で、ディスク容量が唯一の制限です。

---

**最終更新日:** 2025-12-24  
**テスト環境:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}