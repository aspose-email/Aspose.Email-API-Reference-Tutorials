---
date: '2026-09-12'
description: 了解如何使用 Aspose.Email 在 Java 中建立 iCalendar 檔案、設定參與者狀態，並高效產生多個行事曆事件。
keywords:
- create icalendar file java
- java generate ics calendar
- aspose email java
- ics export java
lastmod: '2026-09-12'
og_description: 使用 Aspose.Email 在 Java 中建立 iCalendar 檔案。設定參與者狀態、寫入多個事件，並與 Outlook、Google
  Calendar 等整合。
og_image_alt: Guide to creating iCalendar files in Java with Aspose.Email
og_title: 在 Java 中建立 iCalendar 檔案 – 使用 Aspose.Email 匯出 ICS
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  headline: How to create iCalendar file Java – export ICS with Aspose.Email
  type: TechArticle
- description: Learn how to create iCalendar file Java using Aspose.Email, set attendee
    status, and generate multiple calendar events efficiently.
  name: How to create iCalendar file Java – export ICS with Aspose.Email
  steps:
  - name: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
    text: '**Free trial** – Download a temporary license to test Aspose.Email without
      restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      for details.'
  - name: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
    text: '**Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).'
  - name: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
    text: '**Automated meeting scheduling** – Generate calendar invites on‑the‑fly
      for internal tools or CRM systems.'
  - name: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
    text: '**Cross‑platform calendar integration** – Export appointments from legacy
      databases to Outlook, Google Calendar, or Apple Calendar using the standard
      iCalendar format.'
  - name: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
    text: '**Event management platforms** – Bulk‑create schedules for conferences,
      workshops, or webinars with a single API call, preserving all attendee responses.'
  type: HowTo
- questions:
  - answer: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide
      the UID of the appointment you wish to update.
    question: Can I update an existing ICS file instead of creating a new one?
  - answer: Absolutely. Configure recurrence patterns on the `Appointment` object
      before writing to the ICS file.
    question: Does Aspose.Email support recurring events?
  - answer: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")`
      to embed non‑standard fields.
    question: Is it possible to add custom properties to an ICS event?
  - answer: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are
      supported.
    question: What time‑zone formats are accepted?
  - answer: A temporary license removes evaluation restrictions; a full license is
      required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- create icalendar file java
- aspose.email
- java calendar integration
title: 如何使用 Java 建立 iCalendar 檔案 – 使用 Aspose.Email 匯出 ICS
url: /zh-hant/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中建立 iCalendar 檔案 – 使用 Aspose.Email 匯出 ICS

跨時區管理會議行程可能相當頭痛，尤其當需要向數十位參與者發送邀請時。本教學將教您使用 Aspose.Email for Java **在 Java 中建立 iCalendar 檔案**、設定與會者狀態，並將多個行事曆事件寫入單一 `.ics` 檔案。逐步的程式碼片段可直接複製到您的專案中，說明則說明每個部分的意義。

## 快速解答
- **我可以使用 Aspose.Email for Java 設定與會者狀態嗎？** 是的 – 您可以為每位參與者指派 Accepted、Declined 或 Tentative 的值。  
- **我可以寫入單一 ICS 檔案多少個事件？** 此函式庫沒有硬性限制；範例示範了十個事件，且您可以擴展至數千個。  
- **開發時需要授權嗎？** 免費的臨時授權可移除評估限制；正式使用則需購買授權。  
- **建議使用哪個 Java 版本？** JDK 16（或更新）符合提供的分類器，並確保完整的 API 相容性。  
- **時區處理會自動嗎？** 您可以在建立日期時指定時區，Aspose.Email 會嵌入正確的 TZID。

## iCalendar 是什麼以及為何重要？
iCalendar（ICS）格式是 Outlook、Google Calendar、Apple Calendar 以及其他眾多客戶端之間交換行事曆資料的通用標準。匯出為 iCalendar 可讓您分發會議邀請、批量建立事件，或整合舊有系統而不會遺失與會者狀態或自訂屬性。

## 為何使用 Aspose.Email for Java 匯出 iCalendar 檔案？
Aspose.Email 讓您對每個 iCalendar 元素都有細緻的控制，同時保持實作簡單。它支援 **50 多種輸入與輸出格式**，可在不將整個檔案載入記憶體的情況下處理數百頁的行事曆，且可在任何執行 Java 16 或更新版本的平台上運作。這意味著您能產生穩健的 `.ics` 檔案，於所有主流行事曆客戶端皆能正確顯示。

## 前置條件

開始之前，請確保您具備以下項目：

### 必要的函式庫與版本
- **Aspose.Email for Java** 版本 25.4 或更新（此函式庫包含超過 30 個用於 iCalendar 處理的類別）。  
- Maven 用於相依性管理（或直接從 [Aspose](https://releases.aspose.com/email/java/) 下載 JAR）。

### 環境設定
- 已在機器上安裝 JDK 16（或更新）。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。

### 知識前提
- 基本的 Java 程式設計技能。  
- 熟悉用於日期時間處理的 `java.util.Calendar` 與 `java.util.Date`。

## 設定 Aspose.Email for Java

將 Aspose.Email 函式庫加入您的 Maven 專案：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 取得授權步驟
1. **免費試用** – 下載臨時授權以在無限制的情況下測試 Aspose.Email。詳情請參閱 [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)。  
2. **購買** – 若需長期使用，請於 [Aspose Purchase](https://purchase.aspose.com/buy) 購買訂閱。

在程式碼中初始化授權：

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

現在您已準備好深入本指南的兩個核心功能。

## 如何匯出 iCalendar 檔案（Java）：設定約會與會者的參與者狀態

### 什麼是行事曆約會中的參與者狀態？
參與者狀態記錄與會者對會議邀請的回覆情形——Accepted、Declined 或 Tentative。以程式方式設定此狀態對於自動排程系統與精確的會議追蹤至關重要。

您可以在寫入行事曆檔案前，直接於每個 `Attendee` 物件上設定參與者狀態。

### 步驟實作

#### 1️⃣ 建立並設定約會日期
`java.util.Calendar` 是用於處理日期與時間值的 Java 類別。使用 `java.util.Calendar` 定義開始與結束時間。函式庫會遵守提供的時區識別碼。

```java
String location = "Room 5";
Calendar calendar = Calendar.getInstance();

// Set start date and time
calendar.set(2011, Calendar.NOVEMBER, 10, 10, 12, 11);
Date startDate = calendar.getTime();

// Set end date and time
calendar.set(2012, Calendar.OCTOBER, 13, 13, 11, 12);
Date endDate = calendar.getTime();
```

#### 2️⃣ 定義組織者與與會者清單
`AttendeeCollection` 是保存代表會議參與者的 `Attendee` 物件的集合類別。建立 `AttendeeCollection` 並加入每位參與者的電子郵件地址。

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ 為每位與會者指派參與狀態
`ResponseType` 表示與會者的回覆狀態，如 Accepted、Declined 或 Tentative。於每個 `Attendee` 設定 `ResponseType` 屬性以指示 Accepted、Declined 或 Tentative。

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ 建立 `Appointment` 物件
`Appointment` 代表包含主旨、地點與時間等細節的行事曆事件。`Appointment` 類別代表單一行事曆事件。設定完日期、組織者與與會者後，即可將其序列化為 iCalendar。

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**專業提示：** 在將電子郵件地址加入集合前，請使用簡易的正則表達式驗證；格式錯誤的地址會導致 `ParseException`。

## 如何匯出 iCalendar 檔案（Java）：將多個事件寫入 ICS 檔案

### 為何使用 Java 匯出行事曆為 iCalendar？
iCalendar 格式是通用的，可讓您在 Outlook、Google Calendar、Apple Calendar 以及其他眾多客戶端之間分享會議資訊。透過 **java generate ics calendar** 搭配 Aspose.Email，您可保留與會者狀態、自訂屬性與重複規則，無需額外的轉換步驟。

### 步驟實作

#### 1️⃣ 設定儲存選項並建立 writer
`IcsSaveOptions` 設定 iCalendar 檔案的寫入方式，包括編碼與格式化選項。重複使用同一個實例可在處理大量事件時提升效能。

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ 為每個事件定義時間範圍
`java.util.Date` 代表特定的時間點，通常用於開始與結束時間戳記。遍歷您的資料來源，為每個約會建立開始/結束的 `Date` 物件。

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ 準備與會者集合
一次建立 `AttendeeCollection`，然後將其附加至每個產生的 `Appointment`。

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ 產生並寫入多個約會
迭代處理，為每筆資料建立 `Appointment`，並呼叫 `writer.write(appointment)`。最後，釋放 writer 以關閉檔案句柄。

```java
try {
    for (int i = 0; i < 10; i++) {
        Appointment app = new Appointment("Room 112", startDate, endDate,
                new MailAddress("organizer@domain.com"), attendees);
        app.setDescription("Test body " + i);
        app.setSummary("Test summary:" + i);
        
        writer.write(app); // Write the appointment to ICS file
    }
} finally {
    writer.dispose(); // Clean up resources
}
```

**常見陷阱：** 忘記呼叫 `writer.dispose()` 會使檔案保持開啟，導致後續執行時出現「檔案被使用」錯誤。

## 實務應用

Aspose.Email for Java 在許多實務情境中表現優異：

1. **自動會議排程** – 為內部工具或 CRM 系統即時產生行事曆邀請。  
2. **跨平台行事曆整合** – 使用標準 iCalendar 格式，將舊有資料庫的約會匯出至 Outlook、Google Calendar 或 Apple Calendar。  
3. **活動管理平台** – 透過單一 API 呼叫批量建立會議、工作坊或線上研討會的行程，保留所有與會者回覆。

## 效能考量

使用 **Aspose.Email for Java** 時，請留意以下建議：

- 完成後立即釋放 `CalendarWriter`、`Appointment` 以及任何 `MailMessage` 物件，以釋放原生資源。  
- 處理大量資料時批次處理約會；可將垃圾回收開銷降低至 30 %。  
- 重複使用單一 `IcsSaveOptions` 實例，而非每次寫入時都建立新實例。

## 常見問答

**Q: 我可以更新既有的 ICS 檔案而不是建立新檔案嗎？**  
A: 可以。設定 `saveOptions.setAction(AppointmentAction.Modify)` 並提供欲更新約會的 UID。

**Q: Aspose.Email 支援重複事件嗎？**  
A: 當然支援。在寫入 ICS 檔案前，於 `Appointment` 物件上設定重複模式。

**Q: 能否為 ICS 事件加入自訂屬性？**  
A: 可以。使用 `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` 來嵌入非標準欄位。

**Q: 支援哪些時區格式？**  
A: 同時支援 IANA 時區 ID（例如 “America/New_York”）與 GMT 偏移。

**Q: 開發建置需要授權嗎？**  
A: 臨時授權可移除評估限制；正式部署則需完整授權。

## 結論

您現在已了解 **在 Java 中建立 iCalendar 檔案**、設定參與者狀態，以及使用 Aspose.Email for Java 寫入多個事件的方式。這些功能讓您能構建穩健的排程功能、與任何行事曆客戶端整合，並在組織內部簡化事件分發。

---

**最後更新：** 2026-09-12  
**測試環境：** Aspose.Email for Java 25.4 (jdk16 classifier)  
**作者：** Aspose

## 相關教學

- [產生 .ics 檔案 Java – 使用 Aspose.Email for Java 建立行事曆邀請 – 完整教學](/email/java/)
- [解析 ics 檔案 Java – 使用 Aspose.Email 讀取行事曆事件](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [使用 Aspose.Email for Java 建立行事曆共享邀請](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}