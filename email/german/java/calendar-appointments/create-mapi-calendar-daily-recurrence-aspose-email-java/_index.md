---
date: '2026-03-20'
description: Erfahren Sie, wie Sie einen Outlook‑Kalender in Java mit täglicher Wiederholung
  und Ausnahmen erstellen und den Kalender mithilfe von Aspose.Email für Java in PST
  speichern.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: Outlook‑Kalender in Java mit täglicher Wiederholung und Ausnahmen erstellen
url: /de/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man einen Outlook‑Kalender‑Java mit täglicher Wiederholung und Ausnahmen erstellt

Das effiziente Verwalten wiederkehrender Ereignisse kann herausfordernd sein, besonders wenn Sie einen **outlook calendar java** benötigen, der tägliche Wiederholungsmuster und gelegentliche Ausnahmen unterstützt. In diesem Tutorial lernen Sie, wie Sie Outlook‑Kalender‑Java‑Objekte erstellen, tägliche Wiederholungen konfigurieren, Ausnahmeinstanzen hinzufügen und schließlich **calendar to PST speichern** mit Aspose.Email für Java. Am Ende haben Sie ein wiederverwendbares Code‑Snippet, das Sie in jeden Java‑basierten Planungsservice einbinden können.

## Schnellantworten
- **Welche Bibliothek?** Aspose.Email für Java  
- **Hauptaufgabe?** Einen Outlook‑Kalender‑Java mit täglicher Wiederholung und Ausnahmen erstellen  
- **Vorausgesetztes JDK?** Java 16 oder höher  
- **Kann ich Dateien an Ausnahmen anhängen?** Ja, mit `MapiCalendarExceptionInfo`  
- **Wo wird der Kalender gespeichert?** In einer PST‑Datei über `PersonalStorage`

## Was ist ein Outlook‑Kalender‑java?
Ein Outlook‑Kalender‑Java‑Objekt (implementiert als MAPI‑Kalender) folgt denselben Standards wie Microsoft‑Outlook‑Termine. Es speichert umfangreiche Wiederholungsregeln, Ausnahmebehandlung, Teilnehmer und Anhänge und ist damit ideal für Unternehmens‑Planungen.

## Warum Aspose.Email für Java verwenden?
Aspose.Email bietet eine reine Java‑API, mit der Sie MAPI‑Objekte bearbeiten können, ohne dass Outlook installiert sein muss. Dieser **aspose email tutorial java**‑Ansatz ermöglicht serverseitige Erstellung von PST‑Dateien, automatisierte Besprechungsreihen und volle Kontrolle über die Wiederholungslogik.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie folgendes eingerichtet haben:
- **Aspose.Email Bibliothek**: Version 25.4 (oder neuer) – verfügbar über Maven oder Direktdownload.  
- **Java Development Kit (JDK)**: JDK 16 oder neuer.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans oder ein beliebiger Java‑kompatibler Editor.

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
- **Kostenlose Testversion** – erkunden Sie alle Funktionen ohne Kosten.  
- **Temporäre Lizenz** – beantragen Sie für erweiterte Evaluation.  
- **Vollständige Lizenz** – erwerben Sie für den Produktionseinsatz.

## Aspose.Email für Java einrichten

Zuerst richten Sie Ihre Umgebung ein:

1. Vergewissern Sie sich, dass JDK 16 installiert ist und `JAVA_HOME` konfiguriert ist.  
2. Fügen Sie die Maven‑Abhängigkeit (oder das JAR) zu Ihrem Projekt hinzu.  

Hier ein kurzer Ausschnitt, der zeigt, wie eine Lizenzdatei geladen wird:

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

## Implementierungs‑Leitfaden

### Outlook‑Kalender‑java mit täglicher Wiederholung und Ausnahmen erstellen

#### Überblick
Diese Funktion ermöglicht das Automatisieren wiederkehrender Termine, wobei einzelne Instanzen übersprungen oder geändert werden können.

#### Schritt‑für‑Schritt‑Implementierung

**1. Startdatum des Ereignisses festlegen**  
Bestimmen Sie, wann die Serie beginnen soll:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI‑Kalender‑Objekt erstellen**  
Ort, Betreff und Beschreibung angeben:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Tägliches Wiederholungsmuster definieren**  
Konfigurieren Sie das Ereignis so, dass es jeden Tag wiederholt wird:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Eine Ausnahme zur Wiederholung hinzufügen**  
Ein Datum angeben, das ausgeschlossen (oder geändert) werden soll:

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

### Dateien an Kalender‑Ausnahmen anhängen

#### Überblick
Sie können unterstützende Dokumente (z. B. Agenden) an jede Ausnahmeinstanz anhängen.

**1. Datei erstellen und anhängen**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Outlook‑Kalender‑java in PST speichern (save calendar to pst)

#### Überblick
Persistieren Sie den Kalender in einer PST‑Datei, damit Outlook oder andere Clients ihn lesen können.

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

## Praktische Anwendungsfälle
- **Unternehmens‑Planung** – automatisierte Besprechungsreihen, die automatisch Feiertage überspringen.  
- **Projektmanagement** – wiederkehrende Meilensteine mit gelegentlichen Terminverschiebungen verfolgen.  
- **Event‑Planung** – mehrtägige Konferenzen verwalten, bei denen einzelne Sessions abgesagt oder neu terminiert werden.

### Integrationsmöglichkeiten
Kombinieren Sie Aspose.Email mit CRM‑Plattformen, Task‑Management‑APIs oder eigenen Workflow‑Engines, um End‑zu‑End‑Automatisierung zu ermöglichen.

## Leistungs‑Überlegungen
- **Ressourcen freigeben** – rufen Sie stets `dispose()` auf `PersonalStorage` auf, um Dateihandles zu schließen.  
- **Stream‑Verwendung** – bevorzugen Sie `ByteArrayOutputStream` oder Dateistreams, um das Laden ganzer PSTs in den Speicher zu vermeiden.  
- **Asynchrone Vorgänge** – für die massenhafte Kalendererstellung führen Sie die Logik in einem Hintergrund‑Thread aus, um die UI reaktionsfähig zu halten.

## Fazit
Nachdem Sie diesem Leitfaden gefolgt sind, wissen Sie jetzt, wie Sie **outlook calendar java**‑Objekte mit täglicher Wiederholung erstellen, Ausnahmen hinzufügen, Dateien anhängen und **calendar to PST** speichern. Diese Fähigkeiten ermöglichen den Aufbau robuster Planungsfunktionen, ohne jemals Outlook direkt zu verwenden.

### Nächste Schritte
- Experimentieren Sie mit wöchentlichen oder monatlichen Wiederholungsmustern.  
- Erkunden Sie weitere MAPI‑Eigenschaften wie Teilnehmer, Erinnerungen und Kategorien.  
- Lesen Sie die umfassende API‑Dokumentation von Aspose.Email für fortgeschrittene Szenarien.

## Häufig gestellte Fragen

**F: Unterstützt die Bibliothek zeitzonen‑bewusste Termine?**  
A: Ja, Sie können die Eigenschaften `StartTimeZone` und `EndTimeZone` auf `MapiCalendar` setzen.

**F: Kann ich programmgesteuert ein einzelnes Vorkommen aus einer wiederkehrenden Serie löschen?**  
A: Verwenden Sie die Sammlung `DeletedInstanceDates` im Wiederholungsmuster, um bestimmte Daten als entfernt zu markieren.

**F: Gibt es Beschränkungen für die Größe einer mit Aspose.Email erstellten PST‑Datei?**  
A: PST‑Dateien folgen den Unicode‑Format‑Grenzwerten (standardmäßig bis zu 2 GB), können jedoch über `PersonalStorage`‑Einstellungen größer konfiguriert werden.

**F: Wie füge ich Teilnehmer zu einer Besprechungsanfrage hinzu?**  
A: Erstellen Sie `MapiRecipient`‑Objekte, setzen Sie deren `RecipientType` auf `MapiRecipientType.MAPI_TO` und fügen Sie sie der `Recipients`‑Sammlung von `MapiMessage` hinzu.

**F: Gibt es Unterstützung für wiederkehrende Aufgaben (nicht nur Termine)?**  
A: Ja, Aspose.Email bietet ebenfalls `MapiTask` mit ähnlichen Wiederholungsfunktionen.

**F: Kann ich diesen Leitfaden als Teil einer aspose email tutorial java‑Reihe verwenden?**  
A: Absolut – die hier gezeigten Schritte sind ein Kernbestandteil jeder Aspose.Email‑Java‑Tutorial‑Reihe, die sich mit Kalendererstellung beschäftigt.

## Ressourcen
- [Aspose.Email für Java Dokumentation](https://reference.aspose.com/email/java/)
- [Aspose.Email herunterladen](https://releases.aspose.com/email/java/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/email/java/)
- [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)
- [Aspose Support‑Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-03-20  
**Getestet mit:** Aspose.Email für Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}