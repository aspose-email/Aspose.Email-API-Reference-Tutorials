---
date: '2026-08-01'
description: Erfahren Sie, wie Sie den Kalender mit Aspose.Email für Java in PST exportieren,
  einschließlich des Hinzufügens von Teilnehmern, Festlegens von Start‑ und Enddaten
  und der effizienten Verwaltung von Terminen.
keywords:
- export calendar to pst
- export recurring appointments
- Aspose.Email Java Calendar Events
lastmod: '2026-08-01'
og_description: Kalender mit Aspose.Email für Java in PST exportieren. Erfahren Sie
  Schritt für Schritt, wie Sie Termine erstellen, Teilnehmer hinzufügen und Outlook‑PST‑Dateien
  generieren.
og_image_alt: 'Developer guide: Export calendar to PST using Aspose.Email for Java'
og_title: Kalender in PST exportieren – Komplett‑Leitfaden mit Aspose.Email für Java
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  headline: Export calendar to PST with Aspose.Email for Java
  type: TechArticle
- description: Learn how to export calendar to PST with Aspose.Email for Java, including
    how to add attendees, set start and end dates, and manage appointments efficiently.
  name: Export calendar to PST with Aspose.Email for Java
  steps:
  - name: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
    text: '**Free Trial**: Visit the [Aspose download page](https://releases.aspose.com/email/java/)
      for a temporary license.'
  - name: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
    text: '**Temporary License**: Apply via the [purchase page](https://purchase.aspose.com/temporary-license/).'
  - name: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
    text: '**Purchase License**: Consider purchasing from [Aspose''s purchase portal](https://purchase.aspose.com/buy)
      for long‑term use.'
  - name: '**Business Scheduling** – Automate internal meeting creation and distribution.'
    text: '**Business Scheduling** – Automate internal meeting creation and distribution.'
  - name: '**Event Management** – Track conferences, workshops, and participant lists.'
    text: '**Event Management** – Track conferences, workshops, and participant lists.'
  - name: '**CRM Integration** – Sync appointments with customer relationship tools.'
    text: '**CRM Integration** – Sync appointments with customer relationship tools.'
  - name: '**Project Planning** – Store project milestones as calendar items.'
    text: '**Project Planning** – Store project milestones as calendar items.'
  - name: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
    text: '**Remote Team Collaboration** – Generate PST files for offline sharing.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown above, obtain a license, and follow the
      steps in this guide to create and export calendar events.
    question: How do I get started with Aspose.Email for Java?
  - answer: Yes, change the `pstFilePath` variable in `createPSTWithCalendarEvents()`
      to any valid path on your system.
    question: Can I customize the PST file name and location?
  - answer: Absolutely – `MapiCalendar` exposes a `RecurrencePattern` property that
      you can configure before saving.
    question: Is it possible to add recurrence patterns to appointments?
  - answer: Yes, you can export to iCalendar (`.ics`) and other formats using the
      appropriate API methods.
    question: Does Aspose.Email support other calendar formats besides PST?
  - answer: With the Unicode format (`FileFormatVersion.Unicode`), PST files can grow
      up to 2 TB, limited only by available disk space.
    question: What is the maximum size of a PST file I can create?
  type: FAQPage
tags:
- export calendar to pst
- Aspose.Email
- Java calendar appointments
title: Kalender in PST exportieren mit Aspose.Email für Java
url: /de/java/calendar-appointments/master-aspose-email-java-calendar-events/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kalender in PST exportieren mit Aspose.Email für Java

Wenn Sie eine Java‑Anwendung erstellen, die Planungsdaten mit Outlook teilen muss, benötigen Sie häufig das **Exportieren von Kalenderdaten in PST**. In diesem Tutorial führen wir Sie durch alles, was Sie benötigen – von der Erstellung eines einfachen Termins über das Hinzufügen von Teilnehmern bis hin zum Schreiben der Ereignisse in eine PST‑Datei, alles mit Aspose.Email für Java. Am Ende haben Sie eine produktionsreife Lösung, die unter Windows, Linux und macOS funktioniert.

## Schnelle Antworten
- **Was ist das Hauptziel?** Kalenderereignisse in eine PST‑Datei exportieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Email für Java (v25.4+).  
- **Benötige ich eine Lizenz?** Ja, eine gültige Aspose.Email‑Lizenz entfernt Evaluationsbeschränkungen.  
- **Kann ich Teilnehmer hinzufügen?** Absolut – verwenden Sie `MapiRecipientCollection`.  
- **Welche Java‑Version wird unterstützt?** JDK 16 oder höher.

## Was ist **Kalender in PST exportieren**?
`MapiCalendar` ist die Klasse von Aspose.Email, die ein Outlook‑Kalender‑Element modelliert, einschließlich Betreff, Ort und Zeitangaben.

Das Exportieren eines Kalenders in PST bedeutet, dass im Speicher befindliche `MapiCalendar`‑Objekte in eine Microsoft Outlook Personal Storage Table (PST) konvertiert werden. Die erzeugte PST‑Datei kann direkt in Outlook geöffnet, mit Kollegen geteilt oder in jedes System importiert werden, das das PST‑Format versteht, wobei alle Ereignisdetails wie Teilnehmer, Wiederholungen und Erinnerungen erhalten bleiben.

## Warum Aspose.Email für Java zum Exportieren von Kalendern in PST verwenden?
Sie können eine vollständig kompatible PST‑Datei erzeugen, ohne Outlook zu installieren. Aspose.Email bietet **vollständige MAPI‑Unterstützung**, funktioniert auf **allen gängigen Betriebssystemen** und kann **bis zu 2 TB** Daten im Unicode‑PST‑Format verarbeiten – ausreichend für Unternehmensarchive. Die API ermöglicht zudem das Verwalten von Teilnehmern, Wiederholungsmustern, Erinnerungen und benutzerdefinierten Eigenschaften mit nur wenigen Methodenaufrufen, wodurch der Entwicklungsaufwand erheblich reduziert wird.

## Voraussetzungen
- **Bibliotheken & Abhängigkeiten**: Aspose.Email für Java Version 25.4 oder neuer.  
- **Umgebung**: JDK 16 oder höher, Maven für die Abhängigkeitsverwaltung.  
- **Kenntnisse**: Grundlegende Java‑Programmierung und Vertrautheit mit Maven.

## So richten Sie Aspose.Email für Java ein
Fügen Sie die Aspose.Email‑Abhängigkeit zu Ihrer `pom.xml` hinzu und aktualisieren Sie Ihr Maven‑Projekt. Dieser einzelne Schritt stellt die gesamte MAPI‑API in Ihrem Klassenpfad bereit.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
Entsperren Sie die volle Funktionalität von Aspose.Email ohne Evaluationsbeschränkungen, indem Sie eine Lizenz erwerben:

1. **Kostenlose Testversion**: Besuchen Sie die [Aspose-Download‑Seite](https://releases.aspose.com/email/java/) für eine temporäre Lizenz.  
2. **Temporäre Lizenz**: Beantragen Sie sie über die [Kaufseite](https://purchase.aspose.com/temporary-license/).  
3. **Lizenz kaufen**: Erwägen Sie den Kauf über das [Aspose‑Kaufportal](https://purchase.aspose.com/buy) für die langfristige Nutzung.

Sobald Sie Ihre Lizenz haben, initialisieren Sie sie in Ihrer Anwendung, um alle Funktionen zu aktivieren.

## Wie man **einen Termin erstellt** (Kalenderereignis in Java erstellen)
Laden Sie ein `MapiCalendar`‑Objekt, setzen Sie dessen Kerneigenschaften und geben Sie es für die weitere Verarbeitung zurück. Diese Methode erstellt einen Kalendereintrag mit Betreff, Ort, Beschreibung sowie dem **java calendar start date** / **java calendar end date**, das Sie definiert haben.

```java
public static MapiCalendar createAppointment(String subject, String location,
                                             String description, Calendar start, Calendar end) {
    MapiCalendar appointment = new MapiCalendar();
    appointment.setSubject(subject);
    appointment.setLocation(location);
    appointment.setBody(description);
    appointment.setStartDate(start);
    appointment.setEndDate(end);
    return appointment;
}
```

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

*Erklärung*: Die Klasse `MapiCalendar` ist Aspose.Email‑Darstellung eines Outlook‑Kalender‑Elements. Nach dem Setzen der Grundfelder können Sie auch Wiederholungen, Erinnerungen und Kategorien konfigurieren, bevor Sie speichern.

## Wie man **Teilnehmer hinzufügt** (Java‑Teilnehmer zu einem Meeting hinzufügen)
Erstellen Sie eine `MapiRecipientCollection`, füllen Sie sie mit jedem Teilnehmer und hängen Sie sie an das Meeting an. Dadurch erhält jeder Teilnehmer eine ordnungsgemäße Einladung, wenn die PST‑Datei geöffnet wird.

`MapiRecipientCollection` ist eine Sammlungsklasse, die `MapiRecipient`‑Objekte enthält, die Meeting‑Teilnehmer repräsentieren. `MapiRecipient` stellt einen einzelnen Teilnehmer mit Eigenschaften wie E‑Mail‑Adresse und Empfängertyp dar.

```java
public static MapiRecipientCollection buildAttendees(List<String> emails) {
    MapiRecipientCollection attendees = new MapiRecipientCollection();
    for (String email : emails) {
        MapiRecipient recipient = new MapiRecipient(email, email, MapiRecipientType.MAPI_TO);
        attendees.add(recipient);
    }
    return attendees;
}
```

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

*Erklärung*: `MapiRecipient` definiert einen einzelnen Meeting‑Teilnehmer. Die Einstellung des Typs auf `MAPI_TO` markiert die Adresse als Hauptteilnehmer, während `MAPI_CC` oder `MAPI_BCC` für optionale Teilnehmer verwendet werden können.

## Wie man **Kalender in PST exportiert** (PST mit Kalenderereignissen erstellen)
Erstellen Sie eine Unicode‑PST‑Datei, fügen Sie einen „Calendar“-Ordner hinzu und fügen Sie die zuvor erstellten `MapiCalendar`‑Objekte ein. Die PST kann dann in Outlook geöffnet oder an Endbenutzer verteilt werden.

`PersonalStorage` ist die Aspose.Email‑Klasse, die zum Erstellen, Öffnen und Manipulieren von PST‑Dateien verwendet wird.

```java
public static void createPSTWithCalendarEvents(String pstFilePath,
                                                List<MapiCalendar> events) throws Exception {
    // Create a new Unicode PST (supports up to 2 TB)
    PersonalStorage pst = PersonalStorage.create(pstFilePath, FileFormatVersion.Unicode);
    // Add the default Calendar folder
    FolderInfo calendarFolder = pst.getRootFolder().addSubFolder("Calendar", 
                                   StandardIpmFolder.Calendar);
    // Insert each event
    for (MapiCalendar event : events) {
        calendarFolder.addMapiMessageItem(event);
    }
}
```

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

*Erklärung*: `PersonalStorage` ist der Einstiegspunkt für die PST‑Manipulation. Durch die Verwendung des Unicode‑Formats umgehen Sie das 2 GB‑Limit älterer PST‑Versionen und profitieren von schnellerem I/O bei großen Archiven.

## Praktische Anwendungen
1. **Geschäftsplanung** – Automatisieren Sie die interne Erstellung und Verteilung von Meetings.  
2. **Event‑Management** – Verfolgen Sie Konferenzen, Workshops und Teilnehmerlisten.  
3. **CRM‑Integration** – Synchronisieren Sie Termine mit CRM‑Tools.  
4. **Projektplanung** – Speichern Sie Projektmeilensteine als Kalendereinträge.  
5. **Zusammenarbeit im Remote‑Team** – Generieren Sie PST‑Dateien für die Offline‑Freigabe.

## Leistungsüberlegungen
- **Objekte freigeben** Sie nicht mehr benötigte Objekte, um den Speicher sofort freizugeben.  
- **Effiziente Sammlungen verwenden** (z. B. `ArrayList` für Teilnehmerlisten), wenn Sie Tausende von Teilnehmern verarbeiten.  
- **Häufig genutzte Ereignisse zwischenspeichern**, wenn Sie das PST wiederholt abfragen, um die Festplatten‑I/O zu reduzieren.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **PST file not created** | Überprüfen Sie die Schreibberechtigungen im Zielverzeichnis und stellen Sie sicher, dass der Ordnerpfad existiert. |
| **Attendees not receiving invitations** | Stellen Sie sicher, dass jeder `MapiRecipient` `MapiRecipientType.MAPI_TO` verwendet und die Organisator‑E‑Mail gültig ist. |
| **Date mismatch** | Verwenden Sie `Calendar` konsequent für Start‑/Enddaten; vermeiden Sie das Mischen von `java.util.Date` mit anderen Datumsbibliotheken ohne Konvertierung. |

## Häufig gestellte Fragen

**Q: Wie beginne ich mit Aspose.Email für Java?**  
A: Fügen Sie die oben gezeigte Maven‑Abhängigkeit hinzu, erhalten Sie eine Lizenz und folgen Sie den Schritten in diesem Leitfaden, um Kalenderereignisse zu erstellen und zu exportieren.

**Q: Kann ich den PST‑Dateinamen und -Speicherort anpassen?**  
A: Ja, ändern Sie die Variable `pstFilePath` in `createPSTWithCalendarEvents()` auf einen beliebigen gültigen Pfad auf Ihrem System.

**Q: Ist es möglich, Wiederholungsmuster zu Terminen hinzuzufügen?**  
A: Absolut – `MapiCalendar` stellt eine `RecurrencePattern`‑Eigenschaft bereit, die Sie vor dem Speichern konfigurieren können.

**Q: Unterstützt Aspose.Email andere Kalenderformate neben PST?**  
A: Ja, Sie können in iCalendar (`.ics`) und andere Formate exportieren, indem Sie die entsprechenden API‑Methoden verwenden.

**Q: Wie groß kann eine PST‑Datei maximal sein?**  
A: Im Unicode‑Format (`FileFormatVersion.Unicode`) können PST‑Dateien bis zu 2 TB wachsen, begrenzt nur durch den verfügbaren Festplattenspeicher.

---

**Zuletzt aktualisiert:** 2026-08-01  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Meistern Sie Aspose.Email für Java: Outlook‑PST‑Dateien effizient verwalten](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-outlook-pst-files/)
- [Meistern Sie das Erstellen und Speichern von Kalenderelementen mit Aspose.Email für Java](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Wie man mehrere Kalenderereignisse aus einer ICS‑Datei mit Aspose.Email in Java liest](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}