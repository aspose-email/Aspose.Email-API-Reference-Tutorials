---
date: '2025-12-24'
description: Erfahren Sie, wie Sie Kalender mit Aspose.Email für Java in PST exportieren,
  einschließlich des Hinzufügens von Teilnehmern, des Festlegens von Anfangs‑ und
  Enddaten und der effizienten Verwaltung von Terminen.
keywords:
- Aspose.Email Java Calendar Events
- Create Calendar Events in Java
- Manage Calendar Appointments with Java
- export calendar to pst
title: Kalender nach PST exportieren mit Aspose.Email für Java
url: /de/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Calendar to PST with Aspose.Email for Java

Effizient **export calendar to PST** ist eine häufige Anforderung beim Erstellen von Java-Anwendungen, die Planungsdaten mit Outlook oder anderen Microsoft-Produkten teilen müssen. In diesem Tutorial sehen Sie genau, wie Sie Termine erstellen, Teilnehmer hinzufügen, Start‑ und Enddaten festlegen und schließlich alles in einer PST‑Datei speichern – alles mit Aspose.Email für Java.

## Schnelle Antworten
- **Was ist das Hauptziel?** Export calendar events to a PST file.  
- **Welche Bibliothek wird benötigt?** Aspose.Email for Java (v25.4+).  
- **Benötige ich eine Lizenz?** Yes, a valid Aspose.Email license removes evaluation limits.  
- **Kann ich Teilnehmer hinzufügen?** Absolutely – use `MapiRecipientCollection`.  
- **Welche Java‑Version wird unterstützt?** JDK 16 or higher.

## Was ist **export calendar to pst**?
Exporting a calendar to PST means converting in‑memory `MapiCalendar` objects into a Microsoft Outlook Personal Storage Table (PST). This file can be opened in Outlook, shared with colleagues, or imported into other systems that understand the PST format.

## Warum Aspose.Email für Java zum Exportieren von Kalendern nach PST verwenden?
- **Full MAPI support** – create, modify, and save appointments without needing Outlook installed.  
- **Cross‑platform** – works on Windows, Linux, and macOS.  
- **Rich API** – manage attendees, recurrence, reminders, and more.  
- **Performance‑optimized** – handle large volumes of events with low memory footprint.

## Voraussetzungen
- **Libraries & Dependencies**: Aspose.Email for Java version 25.4 or later.  
- **Environment**: JDK 16 or higher, Maven for dependency management.  
- **Knowledge**: Basic Java programming and familiarity with Maven.

## So richten Sie Aspose.Email für Java ein
Fügen Sie die Aspose.Email‑Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
Unlock full functionality of Aspose.Email without evaluation limitations by acquiring a license:

1. **Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/) for a temporary license.  
2. **Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Consider purchasing from [Aspose's purchase portal](https://purchase.aspose.com/buy) for long‑term use.

Sobald Sie Ihre Lizenz haben, initialisieren Sie sie in Ihrer Anwendung, um alle Funktionen zu aktivieren.

## Wie man **create appointment** (Create Calendar Event Java)

### Schritt 1: Define start and end dates (java calendar start date / java calendar end date)
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

*Erklärung*: Dieses Snippet erstellt ein `MapiCalendar` mit einem bestimmten Ort, Betreff, Beschreibung und dem **java calendar start date** / **java calendar end date**, den Sie definiert haben.

## Wie man **add attendees** (how to add attendees)

### Schritt 2: Build the attendee list
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

*Erklärung*: Dieser Code erstellt ein Meeting, legt den Organisator fest und fügt die **how to add attendees**‑Liste hinzu, sodass jeder eine ordnungsgemäße Einladung erhält.

## Wie man **export calendar to pst** (Create PST with calendar events)

### Schritt 3: Create a PST file and add the events
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

*Erklärung*: Dieses Snippet **exports calendar to PST**, indem es einen PST‑Container erstellt, einen vordefinierten „Calendar“-Ordner hinzufügt und die zuvor erstellten `MapiCalendar`‑Objekte einfügt.

## Praktische Anwendungen
1. **Business Scheduling** – Automate internal meeting creation and distribution.  
2. **Event Management** – Track conferences, workshops, and participant lists.  
3. **CRM Integration** – Sync appointments with customer relationship tools.  
4. **Project Planning** – Store project milestones as calendar items.  
5. **Remote Team Collaboration** – Generate PST files for offline sharing.

## Leistungsüberlegungen
- **Dispose objects** you no longer need to free memory.  
- **Choose efficient collections** for large attendee lists.  
- **Cache frequently accessed events** if you query the PST repeatedly.

## Häufige Probleme und Lösungen
| Issue | Solution |
|-------|----------|
| **PST file not created** | Verify write permissions on the target directory and ensure the folder path exists. |
| **Attendees not receiving invitations** | Confirm that each `MapiRecipient` uses `MapiRecipientType.MAPI_TO` and that the organizer email is valid. |
| **Date mismatch** | Use `Calendar` consistently for start/end dates; avoid mixing `java.util.Date` with other date libraries without conversion. |

## Häufig gestellte Fragen

**Q: How do I get started with Aspose.Email for Java?**  
A: Add the Maven dependency shown above, obtain a license, and follow the steps in this guide to create and export calendar events.

**Q: Can I customize the PST file name and location?**  
A: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()` to any valid path on your system.

**Q: Is it possible to add recurrence patterns to appointments?**  
A: Absolutely – `MapiCalendar` exposes recurrence properties such as `RecurrencePattern` that you can configure before saving.

**Q: Does Aspose.Email support other calendar formats besides PST?**  
A: Yes, you can export to iCalendar (`.ics`) and other formats using the appropriate API methods.

**Q: What is the maximum size of a PST file I can create?**  
A: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow up to 2 TB, limited only by disk space.

---

**Last Updated:** 2025-12-24  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}