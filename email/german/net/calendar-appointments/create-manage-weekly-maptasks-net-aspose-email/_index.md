---
"date": "2025-05-30"
"description": "Erfahren Sie, wie Sie wöchentlich wiederkehrende Aufgaben mit Aspose.Email für .NET einrichten und verwalten. Diese Anleitung behandelt das Erstellen, Konfigurieren und Optimieren Ihrer Planungslösungen."
"title": "So erstellen Sie wöchentlich wiederkehrende MapiTasks in .NET mit Aspose.Email"
"url": "/de/net/calendar-appointments/create-manage-weekly-maptasks-net-aspose-email/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie wöchentlich wiederkehrende MapiTasks in .NET mit Aspose.Email

## Einführung

Die effiziente Verwaltung wiederkehrender Aufgaben ist für Entwickler von Anwendungen mit Terminplanungs- oder Kalenderfunktionen entscheidend. Ob Sie ein internes Tool für das Aufgabenmanagement entwickeln oder Kalenderfunktionen in eine Geschäftsanwendung integrieren – das Erstellen und Verwalten wöchentlich wiederkehrender Aufgaben kann die Produktivität deutlich steigern.

In diesem Tutorial erfahren Sie, wie Sie **Aspose.Email für .NET** Erstellen Sie wöchentlich wiederkehrende MapiTasks, die nach einem bestimmten Datum enden. Diese Funktion ist von unschätzbarem Wert für Entwickler, die die Planung ihrer Anwendungen mithilfe der robusten Funktionen von Aspose.Email automatisieren möchten.

### Was Sie lernen werden:
- Einrichten und Konfigurieren von Aspose.Email für .NET
- Erstellen einer wöchentlich wiederkehrenden MapiTask mit einem festgelegten Enddatum
- Implementierung mehrtägiger Wiederholungsmuster
- Berechnen der Anzahl der Vorkommnisse basierend auf benutzerdefinierten Wiederholungsregeln

Sind Sie bereit, leistungsstarke Planungslösungen zu entwickeln? Dann legen wir los!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Aspose.Email für .NET** Bibliothek: Sie können sie mit NuGet oder anderen Paketmanagern installieren.
- **.NET Framework 4.6.1 oder höher** oder **.NET Core/5+**: Stellen Sie sicher, dass Ihre Entwicklungsumgebung mit einer kompatiblen .NET-Version eingerichtet ist.
- Grundkenntnisse in C# und Vertrautheit mit Konzepten der objektorientierten Programmierung.

## Einrichten von Aspose.Email für .NET

Um Aspose.Email für .NET zu verwenden, müssen Sie es Ihrem Projekt hinzufügen. So geht's:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Email
```

**Verwenden der Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Email
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
- Suchen Sie nach „Aspose.Email“ und installieren Sie die neueste Version.

### Lizenzerwerb

Sie können eine Lizenz erwerben über:

- **Kostenlose Testversion**: Testen Sie Funktionen ohne Einschränkungen.
- **Temporäre Lizenz**: Verwenden Sie dies, um erweiterte Funktionen zu bewerten.
- **Kaufen**: Für den vollständigen Zugriff erwerben Sie eine kommerzielle Lizenz.

Sobald Sie Ihre Lizenzdatei haben, initialisieren Sie Aspose.Email, indem Sie die Lizenz in Ihrem Code anwenden:
```csharp
Aspose.Email.License license = new Aspose.Email.License();
license.SetLicense("path_to_license_file.lic");
```

## Implementierungshandbuch

Wir werden die Implementierung in zwei Hauptfunktionen unterteilen: Erstellen einer eintägigen wöchentlichen Wiederholung und Einrichten mehrtägiger Wiederholungen.

### Erstellen einer wöchentlich wiederkehrenden MapiTask, die nach einem bestimmten Datum endet

#### Überblick
Mit dieser Funktion können Sie Aufgaben erstellen, die wöchentlich an einem bestimmten Tag wiederholt werden, bis sie nach einem bestimmten Datum enden. Sie eignet sich ideal für die Planung wiederkehrender Besprechungen oder Termine.

#### Implementierungsschritte
**Schritt 1: Konfigurieren des Wiederholungsmusters**
Hier richten wir das Wiederholungsmuster ein mit `MapiCalendarWeeklyRecurrencePattern`.
```csharp
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1, // Wöchentliche Wiederholung
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday, // Wiederkehrend am Freitag
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR;INTERVAL=1")
};
```
**Schritt 2: Erstellen Sie die MapiTask**
Nachdem wir nun unser Wiederholungsmuster konfiguriert haben, erstellen wir eine Aufgabe und weisen ihr dieses Muster zu.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;

if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1; // Stellen Sie sicher, dass mindestens ein Vorkommen
}

task.Recurrence = rec;
```
**Schritt 3: Speichern Sie die Aufgabe**
Speichern Sie Ihre Aufgabe abschließend zur dauerhaften Speicherung in einer MSG-Datei.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateEveryDayRecurrence_out.msg", TaskSaveFormat.Msg);
```

### Erstellen einer wöchentlich wiederkehrenden MapiTask an mehreren Tagen, die nach einem bestimmten Datum endet

#### Überblick
Diese Funktion erweitert die vorherige Einrichtung, um Aufgaben zu ermöglichen, die an mehreren Tagen pro Woche wiederkehren, und bietet Flexibilität für komplexere Planungsanforderungen.

#### Implementierungsschritte
**Schritt 1: Konfigurieren des mehrtägigen Wiederholungsmusters**
Richten Sie ein Muster ein, das mehrere Wiederholungstage pro Woche umfasst.
```csharp
var record = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterDate,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 2, // Findet alle zwei Wochen statt
    WeekStartDay = DayOfWeek.Sunday,
    EndDate = new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    DayOfWeek = MapiCalendarDayOfWeek.Friday | MapiCalendarDayOfWeek.Monday, // Wiederkehrend freitags und montags
    OccurrenceCount = GetOccurrenceCount(
        new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        new DateTime(2015, 9, 1).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)), 
        "FREQ=WEEKLY;BYDAY=FR,MO;INTERVAL=2")
};
```
**Schritt 2: Erstellen und Zuweisen der MapiTask**
Erstellen Sie ähnlich wie zuvor eine Aufgabe und weisen Sie dieses mehrtägige Muster zu.
```csharp
MapiTask task = new MapiTask(
    "This is test task",
    "Sample Body",
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now)),
    new DateTime(2015, 7, 16).Add(TimeZone.CurrentTimeZone.GetUtcOffset(DateTime.Now))
);
task.State = MapiTaskState.NotAssigned;
task.Recurrence = record;
```
**Schritt 3: Speichern der mehrtägigen Aufgabe**
Speichern Sie Ihre Aufgabe auf ähnliche Weise, um sicherzustellen, dass sie korrekt gespeichert wird.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
task.Save(dataDir + "/SetWeeklyEndAfterDateMultipleDaysRecurrence_out.msg", TaskSaveFormat.Msg);
```

## Praktische Anwendungen

Hier sind einige praktische Anwendungen dieser Funktionen:

1. **Wöchentliche Meetings automatisieren**: Planen Sie wiederkehrende Teambesprechungen an bestimmten Tagen, beispielsweise freitags.
2. **Aufgabenfristen**: Legen Sie wöchentliche Fristen für Projektaufgaben fest, die jeden Montag und Freitag wiederkehren.
3. **Veranstaltungsplanung**Verwalten Sie Veranstaltungsplanungspläne, die an mehreren Tagen pro Woche Nachverfolgungen erfordern.

## Überlegungen zur Leistung

- **Optimieren Sie die Speichernutzung**: Stellen Sie sicher, dass Sie Objekte ordnungsgemäß entsorgen, um Speicherlecks zu vermeiden, insbesondere beim Umgang mit großen Datensätzen oder zahlreichen wiederkehrenden Aufgaben.
- **Effiziente Datumsberechnungen**: Verwenden Sie effiziente Algorithmen für Datumsberechnungen innerhalb Ihrer Wiederholungsregeln, um die Verarbeitungszeit zu minimieren.
- **Asynchrone Vorgänge**: Wenn Sie Aufgaben auf der Festplatte oder an Netzwerkspeicherorten speichern, sollten Sie zur Leistungssteigerung asynchrone Methoden in Betracht ziehen.

## Abschluss

In diesem Tutorial haben wir erläutert, wie Sie wöchentlich wiederkehrende MapiTasks mit Aspose.Email für .NET erstellen und verwalten. Mit den oben beschriebenen Schritten können Sie problemlos anspruchsvolle Planungsfunktionen in Ihre Anwendungen implementieren.

Um die Funktionen von Aspose.Email weiter zu erkunden oder komplexere Szenarien anzugehen, sollten Sie die offizielle Dokumentation und die Community-Foren lesen.

## FAQs

**F: Wie installiere ich Aspose.Email für .NET?**
A: Sie können es über den NuGet-Paketmanager mit dem Befehl installieren `Install-Package Aspose.Email`.

**F: Was ist eine MapiTask?**
A: Eine MapiTask stellt eine Outlook-Aufgabe mit Eigenschaften wie Betreff, Fälligkeitsdatum und Wiederholungsmuster dar.

**F: Kann ich die Wiederholungsmuster weiter anpassen?**
A: Ja, Sie können verschiedene Wiederholungstypen wie täglich oder monatlich verwenden, indem Sie die `PatternType` Eigentum von `MapiCalendarRecurrencePattern`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}