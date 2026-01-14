---
date: '2025-12-20'
description: Erfahren Sie, wie Sie einen MAPI‑Kalender in Java erstellen, tägliche
  Wiederholungsmuster verwalten und Ausnahmen mit Aspose.Email für Java behandeln.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Erstelle MAPI‑Kalender in Java mit täglicher Wiederholung und Ausnahmen
url: /de/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man mapi calendar java mit täglicher Wiederholung und Ausnahmen erstellt

Die effiziente Verwaltung wiederkehrender Ereignisse kann herausfordernd sein, insbesondere wenn Ausnahmen oder Änderungen erforderlich sind. In diesem Tutorial werden Sie **mapi calendar java**‑Objekte erstellen, tägliche Wiederholungsmuster einrichten und Ausnahmen mit Aspose.Email für Java hinzufügen. Sie lernen, wie Sie Planungsaufgaben nahtlos in Ihren Anwendungen automatisieren können.

## Schnelle Antworten
- **Welche Bibliothek?** Aspose.Email for Java  
- **Primäre Aufgabe?** Erstellen eines MAPI‑Kalenders mit täglicher Wiederholung und Ausnahmen  
- **Vorausgesetztes JDK?** Java 16 oder höher  
- **Kann ich Dateien an Ausnahmen anhängen?** Ja, mit `MapiCalendarExceptionInfo`  
- **Wo wird der Kalender gespeichert?** In einer PST‑Datei über `PersonalStorage`

### Was ist ein MAPI‑Kalender?
Ein MAPI (Messaging Application Programming Interface)-Kalender ist ein Standardformat, das von Microsoft Outlook und anderen E‑Mail‑Clients zum Speichern von Termindaten verwendet wird. Er unterstützt umfangreiche Wiederholungsregeln, Ausnahmen und Anhänge, was ihn ideal für Unternehmensplanung macht.

### Warum Aspose.Email für Java verwenden?
Aspose.Email bietet eine reine Java‑API, mit der Sie MAPI‑Objekte erstellen, ändern und speichern können, ohne Outlook zu benötigen. Das bedeutet, dass Sie serverseitige Planungsfunktionen implementieren, PST‑Dateien erzeugen und komplexe Wiederholungsszenarien programmgesteuert handhaben können.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgende Umgebung haben:
- **Aspose.Email Bibliothek**: Version 25.4 (oder neuer) – verfügbar über Maven oder Direktdownload.  
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

Um Aspose.Email zu nutzen, benötigen Sie eine Lizenz:
- **Kostenlose Testversion** – alle Funktionen ohne Kosten testen.  
- **Temporäre Lizenz** – für erweiterte Evaluierung anfordern.  
- **Vollständige Lizenz** – für den Produktionseinsatz erwerben.

## Einrichtung von Aspose.Email für Java

Zuerst richten Sie Ihre Umgebung ein:

1. Stellen Sie sicher, dass JDK 16 installiert ist und `JAVA_HOME` konfiguriert ist.  
2. Fügen Sie die Maven‑Abhängigkeit (oder laden Sie das JAR) zu Ihrem Projekt hinzu.  

Hier ist ein kleiner Ausschnitt, der zeigt, wie eine Lizenzdatei geladen wird:

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

### Erstellen eines MAPI‑Kalenders mit täglicher Wiederholung und Ausnahmen

#### Überblick
Diese Funktion ermöglicht es Ihnen, wiederkehrende Termine zu automatisieren und gleichzeitig bestimmte Instanzen zu überspringen oder zu ändern.

#### Schritt‑für‑Schritt‑Implementierung

**1. Startdatum des Ereignisses festlegen**  
Bestimmen Sie, wann die Serie beginnen soll:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI‑Kalenderobjekt erstellen**  
Geben Sie Ort, Betreff und Beschreibung an:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Tägliches Wiederholungsmuster definieren**  
Konfigurieren Sie das Ereignis so, dass es täglich wiederholt wird:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Eine Ausnahme zur Wiederholung hinzufügen**  
Geben Sie ein Datum an, das ausgeschlossen (oder geändert) werden soll:

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

### Dateien an Kalenderausnahmen anhängen

#### Überblick
Sie können unterstützende Dokumente (z. B. Agenden) an jede Ausnahmeinstanz anhängen.

**1. Datei erstellen und anhängen**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### MAPI‑Kalender in PST‑Dateien speichern

#### Überblick
Speichern Sie den Kalender in einer PST‑Datei, damit Outlook oder andere Clients ihn lesen können.

**1. Kalender erstellen und in PST speichern**

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
- **Unternehmensplanung** – Meeting‑Serien automatisieren, Feiertage automatisch überspringen.  
- **Projektmanagement** – wiederkehrende Meilensteine mit gelegentlichen Datumsverschiebungen verfolgen.  
- **Eventplanung** – mehrtägige Konferenzen verwalten, bei denen einige Sitzungen abgesagt oder neu terminiert werden.

### Integrationsmöglichkeiten
Kombinieren Sie Aspose.Email mit CRM‑Plattformen, Task‑Management‑APIs oder benutzerdefinierten Workflow‑Engines, um End‑zu‑End‑Automatisierung zu ermöglichen.

## Leistungsüberlegungen
- **Ressourcen freigeben** – rufen Sie stets `dispose()` auf `PersonalStorage` auf, um Dateihandles freizugeben.  
- **Stream‑Verwendung** – bevorzugen Sie `ByteArrayOutputStream` oder Dateistreams, um das Laden ganzer PSTs in den Speicher zu vermeiden.  
- **Asynchrone Vorgänge** – bei massiver Kalenderestellung die Erstellungslogik in einem Hintergrundthread ausführen, um die UI reaktionsfähig zu halten.

## Fazit
Durch Befolgen dieser Anleitung wissen Sie jetzt, wie Sie **mapi calendar java**‑Objekte mit täglicher Wiederholung erstellen, Ausnahmen hinzufügen, Dateien anhängen und alles in einer PST‑Datei speichern. Diese Möglichkeiten ermöglichen es Ihnen, robuste Planungsfunktionen zu erstellen, ohne Outlook direkt zu verwenden.

### Nächste Schritte
- Experimentieren Sie mit wöchentlichen oder monatlichen Wiederholungsmustern.  
- Erkunden Sie weitere MAPI‑Eigenschaften wie Teilnehmer, Erinnerungen und Kategorien.  
- Überprüfen Sie die umfassende API‑Dokumentation von Aspose.Email für fortgeschrittene Szenarien.

## Häufig gestellte Fragen

**Q: Unterstützt die Bibliothek zeitzonenbewusste Termine?**  
A: Ja, Sie können die Eigenschaften `StartTimeZone` und `EndTimeZone` auf `MapiCalendar` setzen.

**Q: Kann ich programmgesteuert ein einzelnes Vorkommen aus einer wiederkehrenden Serie löschen?**  
A: Verwenden Sie die Sammlung `DeletedInstanceDates` im Wiederholungsmuster, um bestimmte Daten als entfernt zu markieren.

**Q: Gibt es Beschränkungen für die Größe einer mit Aspose.Email erstellten PST‑Datei?**  
A: PST‑Dateien folgen den Unicode‑Formatgrenzen (standardmäßig bis zu 2 GB), aber Sie können größere Größen über die `PersonalStorage`‑Einstellungen konfigurieren.

**Q: Wie füge ich Teilnehmer zu einer Besprechungsanfrage hinzu?**  
A: Erstellen Sie `MapiRecipient`‑Objekte, setzen Sie deren `RecipientType` auf `MapiRecipientType.MAPI_TO` und fügen Sie sie der `Recipients`‑Sammlung von `MapiMessage` hinzu.

**Q: Gibt es Unterstützung für wiederkehrende Aufgaben (nicht nur Termine)?**  
A: Ja, Aspose.Email bietet auch `MapiTask` mit ähnlichen Wiederholungsfunktionen.

## Ressourcen
- [Aspose.Email für Java Dokumentation](https://reference.aspose.com/email/java/)
- [Aspose.Email herunterladen](https://releases.aspose.com/email/java/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/email/java/)
- [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)
- [Aspose Support-Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.Email für Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
