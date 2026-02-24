---
date: '2026-02-24'
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
# Kalender in PST exportieren mit Aspose.Email für Java

Wenn Sie eine Java‑Anwendung erstellen, die Planungsdaten mit Outlook teilen muss, benötigen Sie häufig das **Exportieren von Kalenderdaten in PST**. In diesem Tutorial führen wir Sie durch alles, was Sie benötigen – vom Erstellen eines einfachen Termins über das Hinzufügen von Teilnehmern bis hin zum Schreiben der Ereignisse in eine PST‑Datei, alles mit Aspose.Email für Java.

## Schnelle Antworten
- **What is the primary goal?** Kalenderereignisse in eine PST‑Datei exportieren.  
- **Which library is required?** Aspose.Email für Java (v25.4+).  
- **Do I need a license?** Ja, eine gültige Aspose.Email‑Lizenz entfernt die Evaluationsbeschränkungen.  
- **Can I add attendees?** Absolut – verwenden Sie `MapiRecipientCollection`.  
- **What Java version is supported?** JDK 16 oder höher.

## Was ist **export calendar to pst**?
Das Exportieren eines Kalenders in PST bedeutet, dass im Speicher befindliche `MapiCalendar`‑Objekte in eine Microsoft Outlook Personal Storage Table (PST) konvertiert werden. Die resultierende Datei kann direkt in Outlook geöffnet, mit Kollegen geteilt oder in jedes System importiert werden, das das PST‑Format versteht.

## Warum Aspose.Email für Java zum Exportieren von Kalendern in PST verwenden?
- **Full MAPI support** – Termine erstellen, ändern und speichern, ohne dass Outlook installiert sein muss.  
- **Cross‑platform** – funktioniert unter Windows, Linux und macOS.  
- **Rich API** – verwalten Sie Teilnehmer, Wiederholungen, Erinnerungen und mehr.  
- **Performance‑optimized** – verarbeitet große Mengen von Ereignissen mit geringem Speicherverbrauch.

## Voraussetzungen
- **Libraries & Dependencies**: Aspose.Email für Java Version 25.4 oder neuer.  
- **Environment**: JDK 16 oder höher, Maven für das Abhängigkeitsmanagement.  
- **Knowledge**: Grundlegende Java‑Programmierung und Vertrautheit mit Maven.

## Wie man Aspose.Email für Java einrichtet
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
Schalten Sie die volle Funktionalität von Aspose.Email ohne Evaluationsbeschränkungen frei, indem Sie eine Lizenz erwerben:

1. **Free Trial**: Besuchen Sie die [Aspose-Download‑Seite](https://releases.aspose.com/email/java/) für eine temporäre Lizenz.  
2. **Temporary License**: Beantragen Sie sie über die [Kaufseite](https://purchase.aspose.com/temporary-license/).  
3. **Purchase License**: Erwägen Sie den Kauf über das [Aspose‑Kaufportal](https://purchase.aspose.com/buy) für die langfristige Nutzung.

Sobald Sie Ihre Lizenz haben, initialisieren Sie sie in Ihrer Anwendung, um alle Funktionen zu aktivieren.

## Wie man **einen Termin erstellt** (Kalenderereignis in Java erstellen)

### Schritt 1: Start‑ und Enddaten festlegen (java calendar start date / java calendar end date)
Die folgende Methode zeigt, wie Sie die Start‑ und Enddaten für einen Termin festlegen und ein `MapiCalendar`‑Objekt zurückgeben:

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

*Erklärung*: Dieses Snippet erstellt ein `MapiCalendar` mit einem bestimmten Ort, Betreff, Beschreibung und den von Ihnen definierten **java calendar start date** / **java calendar end date**.

## Wie man **Teilnehmer hinzufügt** (java add meeting attendees)

### Schritt 2: Teilnehmerliste erstellen
Verwenden Sie `MapiRecipientCollection`, um anzugeben, wer die Besprechungseinladung erhalten soll:

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

*Erklärung*: Dieser Code erstellt eine Besprechung, legt den Organisator fest und fügt die **java add meeting attendees**‑Liste hinzu, sodass alle eine ordnungsgemäße Einladung erhalten.

## Wie man **Kalender in PST exportiert** (PST mit Kalenderereignissen erstellen)

### Schritt 3: PST‑Datei erstellen und die Ereignisse hinzufügen
Die folgende Methode demonstriert das Erstellen einer Unicode‑PST‑Datei und das Speichern sowohl des einfachen Termins als auch der Besprechung mit Teilnehmern:

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

*Erklärung*: Dieses Snippet **exports calendar to PST** indem es einen PST‑Container erstellt, einen vordefinierten Ordner „Calendar“ hinzufügt und die zuvor erstellten `MapiCalendar`‑Objekte einfügt.

## Praktische Anwendungen
1. **Business Scheduling** – Interne Besprechungserstellung und -verteilung automatisieren.  
2. **Event Management** – Konferenzen, Workshops und Teilnehmerlisten verfolgen.  
3. **CRM Integration** – Termine mit CRM‑Tools synchronisieren.  
4. **Project Planning** – Projektmeilensteine als Kalendereinträge speichern.  
5. **Remote Team Collaboration** – PST‑Dateien für die Offline‑Freigabe erzeugen.

## Leistungsüberlegungen
- **Dispose objects** Sie nicht mehr benötigte Objekte freigeben, um Speicher zu sparen.  
- **Choose efficient collections** effiziente Sammlungen für große Teilnehmerlisten wählen.  
- **Cache frequently accessed events** häufig abgefragte Ereignisse zwischenspeichern, wenn Sie das PST wiederholt abfragen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **PST-Datei nicht erstellt** | Überprüfen Sie die Schreibberechtigungen im Zielverzeichnis und stellen Sie sicher, dass der Ordnerpfad existiert. |
| **Teilnehmer erhalten keine Einladungen** | Stellen Sie sicher, dass jeder `MapiRecipient` `MapiRecipientType.MAPI_TO` verwendet und die E‑Mail des Organisators gültig ist. |
| **Datumsabweichung** | Verwenden Sie `Calendar` konsequent für Start‑/Enddaten; vermeiden Sie das Mischen von `java.util.Date` mit anderen Datumsbibliotheken ohne Konvertierung. |

## Häufig gestellte Fragen

**Q: Wie beginne ich mit Aspose.Email für Java?**  
A: Fügen Sie die oben gezeigte Maven‑Abhängigkeit hinzu, erwerben Sie eine Lizenz und folgen Sie den Schritten in diesem Leitfaden, um Kalenderereignisse zu erstellen und zu exportieren.

**Q: Kann ich den PST‑Dateinamen und -Speicherort anpassen?**  
A: Ja, ändern Sie die Variable `pstFilePath` in `createPSTWithCalendarEvents()` zu einem beliebigen gültigen Pfad auf Ihrem System.

**Q: Ist es möglich, Wiederholungsmuster zu Terminen hinzuzufügen?**  
A: Absolut – `MapiCalendar` stellt Wiederholungseigenschaften wie `RecurrencePattern` bereit, die Sie vor dem Speichern konfigurieren können.

**Q: Unterstützt Aspose.Email andere Kalenderformate neben PST?**  
A: Ja, Sie können mit den entsprechenden API‑Methoden nach iCalendar (`.ics`) und andere Formate exportieren.

**Q: Wie groß kann eine PST‑Datei maximal sein, die ich erstellen kann?**  
A: Im Unicode‑Format (`FileFormatVersion.Unicode`) können PST‑Dateien bis zu 2 TB groß werden, begrenzt nur durch den verfügbaren Speicherplatz.

---

**Zuletzt aktualisiert:** 2026-02-24  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}