---
date: '2026-03-18'
description: Aspose.Email for Java を使用して ics ファイルをエクスポートし、参加者のステータスを設定し、複数のカレンダーイベントを効率的に書き込む方法を学びましょう。
keywords:
- Aspose.Email Java
- set participant status in Java
- write ICS files with Java
title: ICSのエクスポート方法 – ステータス設定 – Aspose.Email Java
url: /ja/java/calendar-appointments/aspose-email-java-set-participant-status-write-ics/
weight: 1
---

 write final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Export ICS – Set Status – Aspose.Email Java

会議スケジュールを効率的に管理することは、多くのプロフェッショナルが直面する課題であり、特に異なるタイムゾーンにまたがる複数の参加者を扱う場合は難易度が上がります。このチュートリアルでは、Aspose.Email for Java を使用して **how to export ics** ファイルをエクスポートし、参加者（出席者）のステータスを設定し、複数のカレンダーイベントを単一ファイルに書き込む方法を紹介します。すべての手順はコード例として提供されているので、プロジェクトにそのままコピーして利用できます。

## Quick Answers
- **Can I set attendee status with Aspose.Email for Java?** Yes – you can assign Accepted, Declined, or Tentative values.  
- **How many events can I write to a single ICS file?** The library supports any number; the example creates ten events.  
- **Do I need a license for development?** A free temporary license works for evaluation; a purchased license is required for production.  
- **Which Java version is recommended?** JDK 16 (or later) matches the provided classifier.  
- **Is time‑zone handling automatic?** You can specify the time zone when creating dates; the library respects it.

## What is “how to export ics” and why does it matter?

ICS（iCalendar）形式は、Outlook、Google Calendar、Apple Calendar など多数のクライアント間でカレンダー情報を共有する事実上の標準です。ICS へエクスポートすることで、会議招待の配布、イベントの一括作成、レガシーシステムとの統合などを、参加者ステータスやカスタムプロパティを失うことなく実現できます。

## Why use Aspose.Email for Java to export ics?

- **Full control** over attendee responses (Accepted/Declined/Tentative).  
- **No external dependencies** – the library handles all iCalendar specifications internally.  
- **Bulk writing** – you can generate dozens or hundreds of events with a single writer, keeping file handles efficient.  
- **Cross‑platform compatibility** – generated ICS files work on any calendar client that follows the RFC 5545 standard.

## Prerequisites

Before you start, make sure you have the following:

### Required Libraries and Versions
- **Aspose.Email for Java** version 25.4 or later.  
- Maven for dependency management (or download directly from [Aspose](https://releases.aspose.com/email/java/)).

### Environment Setup Requirements
- A Java Development Kit (JDK) installed on your machine, preferably JDK 16 to match the Aspose.Email classifier used in this tutorial.  
- An Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse.

### Knowledge Prerequisites
- Basic Java programming skills.  
- Familiarity with `java.util.Calendar` and `java.util.Date` for date‑time handling.

## Setting Up Aspose.Email for Java

Add the Aspose.Email library to your Maven project:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition Steps

1. **Free Trial** – Download a temporary license to test Aspose.Email without restrictions. Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) for details.  
2. **Purchase** – For long‑term use, buy a subscription at [Aspose Purchase](https://purchase.aspose.com/buy).

Initialize the license in your code:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path/to/your/license.lic");
```

Now you’re ready to dive into the two core features of this guide.

## How to export ics: Set Participant Status of Appointment Attendees

### What is participant status in a calendar appointment?

Participant status indicates how an attendee has responded to a meeting invitation—Accepted, Declined, or Tentative. Using Aspose.Email for Java, you can set these values programmatically, which is essential for automated scheduling systems and **java calendar appointment** management.

### Step‑by‑step implementation

#### 1️⃣ Create and configure the appointment dates

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

#### 2️⃣ Define the organizer and the attendee list

```java
MailAddress organizer = new MailAddress("aaa@amail.com", "Organizer");

// Initialize attendee list
MailAddressCollection attendees = new MailAddressCollection();
```

#### 3️⃣ Assign participation status to each attendee

```java
MailAddress attendee1 = new MailAddress("bbb@bmail.com", "First attendee");
MailAddress attendee2 = new MailAddress("ccc@cmail.com", "Second attendee");

// Set statuses
attendee1.setParticipationStatus(ParticipationStatus.Accepted);
attendee2.setParticipationStatus(ParticipationStatus.Declined);

attendees.addMailAddress(attendee1);
attendees.addMailAddress(attendee2);
```

#### 4️⃣ Create the `Appointment` object

```java
Appointment target = new Appointment(location, startDate, endDate, organizer, attendees);
```

**Pro tip:** Always verify that email addresses are correctly formatted; otherwise, the library may throw parsing errors.

## How to export ics: Write Multiple Events to an ICS File

### Why export calendar to ics with Java?

The ICS format is universally understood, allowing you to share meeting information across Outlook, Google Calendar, Apple Calendar, and many other clients. By **write ics file java** with Aspose.Email, you preserve participant status, custom properties, and recurrence rules without extra conversion steps.

### Step‑by‑step implementation

#### 1️⃣ Configure save options and create a writer

```java
IcsSaveOptions saveOptions = new IcsSaveOptions();
saveOptions.setAction(AppointmentAction.Create);

CalendarWriter writer = new CalendarWriter("YOUR_OUTPUT_DIRECTORY/WriteMultipleEventsToICS_out.ics", saveOptions);
```

#### 2️⃣ Define the time frame for each event

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2018, Calendar.JUNE, 19, 19, 0, 0); // Start time
Date startDate = calendar.getTime();
calendar.set(2018, Calendar.JUNE, 19, 20, 0, 0); // End time
Date endDate = calendar.getTime();
```

#### 3️⃣ Prepare the attendees collection

```java
MailAddressCollection attendees = new MailAddressCollection();
attendees.addItem(new MailAddress("recepientEmail@gmail.com"));
```

#### 4️⃣ Generate and write multiple appointments

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

**Common pitfall:** Forgetting to call `writer.dispose()` can leave file handles open, causing access errors on subsequent runs.

## Practical Applications

Aspose.Email for Java shines in many real‑world scenarios:

1. **Automated Meeting Scheduling** – Generate calendar invites on‑the‑fly for internal tools or CRM systems.  
2. **Cross‑Platform Calendar Integration** – Export appointments from legacy systems to Outlook, Google Calendar, or Apple Calendar using the standard ICS format.  
3. **Event Management Platforms** – Bulk‑create schedules for conferences, workshops, or webinars with a single API call.

## Performance Considerations

When working with **aspose email java**, keep these tips in mind:

- Dispose of `CalendarWriter` (or any `MailMessage`/`Appointment`) objects as soon as you’re done.  
- Batch‑process appointments when handling large data sets to reduce garbage‑collection overhead.  
- Reuse a single `IcsSaveOptions` instance instead of creating a new one for each write operation.

## Frequently Asked Questions

**Q: Can I update an existing ICS file instead of creating a new one?**  
A: Yes. Set `saveOptions.setAction(AppointmentAction.Modify)` and provide the UID of the appointment you wish to update.

**Q: Does Aspose.Email support recurring events?**  
A: Absolutely. Configure recurrence patterns on the `Appointment` object before writing to the ICS file.

**Q: Is it possible to add custom properties to an ICS event?**  
A: Yes. Use `appointment.getCustomProperties().add("X‑MyProperty", "MyValue")` to embed non‑standard fields.

**Q: What time‑zone formats are accepted?**  
A: Both IANA time‑zone IDs (e.g., “America/New_York”) and GMT offsets are supported.

**Q: Do I need a license for development builds?**  
A: A temporary license removes evaluation restrictions; a full license is required for production deployments.

## Conclusion

You’ve now learned **how to export ics** files, set participant status, and write multiple events using Aspose.Email for Java. These capabilities let you build robust scheduling features, integrate with any calendar client, and streamline event distribution across your organization.

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}