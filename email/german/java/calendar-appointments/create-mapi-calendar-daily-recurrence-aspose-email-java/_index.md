---
date: '2026-09-17'
description: Erfahren Sie, wie Sie einen Outlook‑Kalender in Java mit täglicher Wiederholung
  und Ausnahmen erstellen und den Kalender mithilfe von Aspose.Email for Java als
  PST speichern.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Erstellen Sie einen Outlook‑Kalender in Java mit Aspose.Email. Erfahren
  Sie alles über tägliche Wiederholung, Ausnahmebehandlung und das Speichern als PST
  in einer Schritt‑für‑Schritt‑Anleitung.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Outlook‑Kalender in Java mit täglicher Wiederholung und Ausnahmen erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Outlook‑Kalender in Java mit täglicher Wiederholung und Ausnahmen erstellen
url: /de/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook‑Kalender Java mit täglicher Wiederholung und Ausnahmen erstellen

Die effiziente Verwaltung wiederkehrender Ereignisse kann herausfordernd sein, besonders wenn Sie einen **outlook calendar java** benötigen, der tägliche Wiederholungsmuster und gelegentliche Ausnahmen unterstützt. In diesem Tutorial lernen Sie, wie Sie Outlook‑Kalender‑Java‑Objekte erstellen, die tägliche Wiederholung konfigurieren, Ausnahmeinstanzen hinzufügen und schließlich **save calendar to PST** mit Aspose.Email für Java speichern. Am Ende haben Sie ein wiederverwendbares Code‑Snippet, das Sie in jeden Java‑basierten Planungsservice einbinden können.

## Schnelle Antworten
- **Welche Bibliothek?** Aspose.Email for Java  
- **Primäre Aufgabe?** Create an Outlook calendar Java with daily recurrence and exceptions  
- **Vorausgesetztes JDK?** Java 16 or higher  
- **Kann ich Dateien an Ausnahmen anhängen?** Yes, using `MapiCalendarExceptionInfo`  
- **Wo wird der Kalender gespeichert?** In a PST file via `PersonalStorage`  

## Was ist ein Outlook calendar java?
Ein Outlook‑Kalender‑Java‑Objekt ist eine programmatische Darstellung eines Outlook‑Termins, basierend auf der MAPI (Messaging Application Programming Interface)-Spezifikation, die Eigenschaften wie Betreff, Ort, Start‑/Endzeit, Wiederholungsregeln, Teilnehmer und Anhänge enthält. Dieses Objekt kann manipuliert, serialisiert und in PST‑Dateien gespeichert werden, ohne dass Outlook erforderlich ist.

## Warum Aspose.Email für Java verwenden?
Aspose.Email für Java ermöglicht die Arbeit mit MAPI‑Objekten, ohne Outlook zu installieren. Die Bibliothek unterstützt **50+ MAPI‑Eigenschaften**, kann Unicode‑PST‑Dateien bis zu **2 GB** in weniger als **2 Sekunden** für typische Termindaten erzeugen und läuft auf jeder Plattform, die Java 16+ unterstützt. Dieser reine Java‑Ansatz ermöglicht serverseitige Kalendererstellung, automatisierte Besprechungsreihen und vollständige Kontrolle über die Wiederholungslogik.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgende Umgebung eingerichtet haben:
- **Aspose.Email Library**: Version 25.4 (oder neuer) – verfügbar über Maven oder direkten Download.  
- **Java Development Kit (JDK)**: JDK 16 oder neuer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans oder ein beliebiger Java‑kompatibler Editor.

### Erforderliche Bibliotheken und Abhängigkeiten

Um Aspose.Email in Ihr Projekt mit Maven zu integrieren, fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung

Um Aspose.Email zu verwenden, benötigen Sie eine Lizenz:
- **Free trial** – alle Funktionen kostenlos testen.  
- **Temporary license** – für erweiterte Evaluierung anfordern.  
- **Full license** – für den Produktionseinsatz erwerben.

## Einrichtung von Aspose.Email für Java

Zuerst richten Sie Ihre Umgebung ein:

1. Überprüfen Sie, dass JDK 16 installiert ist und `JAVA_HOME` konfiguriert ist.  
2. Fügen Sie die Maven‑Abhängigkeit (oder laden Sie das JAR herunter) zu Ihrem Projekt hinzu.  

Hier ein kleiner Ausschnitt, der zeigt, wie eine Lizenzdatei geladen wird:

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

## Implementierungsleitfaden

### Outlook calendar java mit täglicher Wiederholung und Ausnahmen erstellen

#### Übersicht
Diese Funktion ermöglicht es Ihnen, wiederkehrende Termine zu automatisieren und gleichzeitig bestimmte Instanzen zu überspringen oder zu ändern.

#### Schritt‑für‑Schritt‑Implementierung

**1. Startdatum des Ereignisses festlegen**  
Bestimmen Sie, wann die Serie beginnen soll:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI‑Kalenderobjekt erstellen**  
Die Klasse `MapiCalendar` ist das oberste Objekt, das ein einzelnes Kalenderelement im Speicher darstellt. Geben Sie Ort, Betreff und Beschreibung an:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Tägliches Wiederholungsmuster definieren**  
Die Klasse `MapiCalendarRecurrencePattern` speichert die Regel, die den Termin täglich wiederholt. Konfigurieren Sie das Ereignis so, dass es jeden Tag wiederholt wird:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Eine Ausnahme zur Wiederholung hinzufügen**  
`MapiCalendarExceptionInfo` beschreibt ein einzelnes Vorkommen, das vom Muster abweicht – entweder ausgeschlossen oder geändert. Geben Sie ein Datum an, das ausgeschlossen (oder geändert) werden soll:

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

### Dateien an Kalenderexzeptionen anhängen

#### Übersicht
Sie können unterstützende Dokumente (z. B. Agenden) an jede Ausnahmeinstanz anhängen.

**1. Datei erstellen und anhängen**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Outlook calendar java in PST speichern (save calendar to pst)

#### Übersicht
Speichern Sie den Kalender in einer PST‑Datei, damit Outlook oder andere Clients ihn lesen können.

**1. Kalender erstellen und in PST speichern**  
Die Klasse `PersonalStorage` bietet Methoden zum Erstellen einer neuen PST‑Datei und zum Hinzufügen von MAPI‑Elementen.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Praktische Anwendungen
- **Corporate scheduling** – Besprechungsreihen automatisieren, Feiertage automatisch überspringen.  
- **Project management** – wiederkehrende Meilensteine mit gelegentlichen Datumsverschiebungen verfolgen.  
- **Event planning** – mehrtägige Konferenzen verwalten, bei denen einige Sitzungen abgesagt oder neu terminiert werden.

### Integrationsmöglichkeiten
Kombinieren Sie Aspose.Email mit CRM‑Plattformen, Task‑Management‑APIs oder benutzerdefinierten Workflow‑Engines, um End‑zu‑End‑Automatisierung zu ermöglichen.

## Leistungsüberlegungen
- **Dispose resources** – rufen Sie stets `dispose()` auf `PersonalStorage` auf, um Dateihandles freizugeben.  
- **Stream usage** – bevorzugen Sie `ByteArrayOutputStream` oder Dateistreams, um das Laden ganzer PSTs in den Speicher zu vermeiden.  
- **Async operations** – für die massenhafte Kalendererstellung führen Sie die Erstellungslogik in einem Hintergrundthread aus, um die UI reaktionsfähig zu halten.

## Fazit
Durch Befolgen dieser Anleitung wissen Sie jetzt, wie Sie **outlook calendar java**‑Objekte mit täglicher Wiederholung erstellen, Ausnahmen hinzufügen, Dateien anhängen und **save calendar to PST**. Diese Möglichkeiten ermöglichen es Ihnen, robuste Planungsfunktionen zu entwickeln, ohne Outlook direkt zu verwenden.

### Nächste Schritte
- Experimentieren Sie mit wöchentlichen oder monatlichen Wiederholungsmustern.  
- Erkunden Sie zusätzliche MAPI‑Eigenschaften wie Teilnehmer, Erinnerungen und Kategorien.  
- Überprüfen Sie die umfassende API‑Dokumentation von Aspose.Email für fortgeschrittene Szenarien.

## Häufig gestellte Fragen

**Q: Unterstützt die Bibliothek zeitzonenbewusste Termine?**  
A: Ja, Sie können die Eigenschaften `StartTimeZone` und `EndTimeZone` auf `MapiCalendar` setzen.

**Q: Kann ich programmgesteuert ein einzelnes Vorkommen aus einer wiederkehrenden Serie löschen?**  
A: Verwenden Sie die Sammlung `DeletedInstanceDates` im Wiederholungsmuster, um bestimmte Daten als entfernt zu markieren.

**Q: Gibt es Beschränkungen für die Größe einer mit Aspose.Email erstellten PST‑Datei?**  
A: PST‑Dateien folgen den Unicode‑Formatgrenzen (standardmäßig bis zu 2 GB), aber Sie können über die Einstellungen von `PersonalStorage` größere Größen konfigurieren.

**Q: Wie füge ich Teilnehmer zu einer Besprechungsanfrage hinzu?**  
A: Erstellen Sie `MapiRecipient`‑Objekte, setzen Sie deren `RecipientType` auf `MapiRecipientType.MAPI_TO` und fügen Sie sie der `Recipients`‑Sammlung von `MapiMessage` hinzu.

**Q: Gibt es Unterstützung für wiederkehrende Aufgaben (nicht nur Termine)?**  
A: Ja, Aspose.Email bietet auch `MapiTask` mit ähnlichen Wiederholungsfunktionen.

**Q: Kann ich dieses Handbuch als Teil einer Aspose.Email Java‑Tutorial‑Reihe verwenden?**  
A: Absolut – die hier gezeigten Schritte sind ein Kernbestandteil jedes Aspose.Email Java‑Tutorials, das die Kalendererstellung behandelt.

## Ressourcen
- [Aspose.Email für Java Dokumentation](https://reference.aspose.com/email/java/)
- [Aspose.Email herunterladen](https://releases.aspose.com/email/java/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/email/java/)
- [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)
- [Aspose Support-Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-09-17  
**Getestet mit:** Aspose.Email für Java 25.4 (JDK 16)  
**Autor:** Aspose

## Verwandte Tutorials

- [Outlook-Kalender PST mit Aspose.Email exportieren – Java](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Wie man ein Kalender-Element in Java mit Aspose.Email erstellt](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Kalenderfreigabe-Einladung mit Aspose.Email für Java erstellen](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}