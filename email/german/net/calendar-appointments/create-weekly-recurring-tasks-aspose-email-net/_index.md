---
"date": "2025-05-30"
"description": "Erfahren Sie, wie Sie wöchentlich wiederkehrende Aufgaben mit Aspose.Email für .NET automatisieren. Folgen Sie unserer umfassenden Anleitung zum Einrichten, Konfigurieren und Implementieren von MapiTasks mit Wiederholungsmustern."
"title": "Erstellen Sie wöchentlich wiederkehrende Aufgaben mit Aspose.Email .NET für Kalender und Termine"
"url": "/de/net/calendar-appointments/create-weekly-recurring-tasks-aspose-email-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie wöchentlich wiederkehrende Aufgaben mit Aspose.Email .NET für Kalender und Termine

## Einführung

Die Verwaltung wiederkehrender Aufgaben kann eine Herausforderung sein, insbesondere wenn sie wöchentlich wiederholt und nahtlos in Ihren Arbeitsablauf integriert werden müssen. Dieses Tutorial führt Sie durch die Erstellung wöchentlich wiederkehrender Aufgaben mit der leistungsstarken Aspose.Email für .NET-Bibliothek, ideal für die Automatisierung von Erinnerungen oder die Planung regelmäßiger Updates.

**Was Sie lernen werden:**
- So erstellen Sie eine MapiTask mit wöchentlicher Wiederholung.
- Einrichten und Konfigurieren von Aspose.Email für .NET.
- Berechnen des Auftretens von Aufgaben zwischen Daten mithilfe von Wiederholungsregeln.
- Praktische Anwendungen zur Integration wiederkehrender Aufgaben in Geschäftsprozesse.

Lassen Sie uns Ihren Aufgabenverwaltungsprozess optimieren!

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Aspose.Email für .NET** installiert. Installationsanweisungen finden Sie weiter unten.
- Eine kompatible IDE (z. B. Visual Studio) für die C#-Entwicklung.
- Grundlegende Kenntnisse der C#-Programmierung und Vertrautheit mit Datumsmanipulationen.

### Einrichten von Aspose.Email für .NET

Installieren Sie zunächst die Aspose.Email-Bibliothek in Ihrem Projekt:

**.NET-CLI**
```bash
dotnet add package Aspose.Email
```

**Paketmanager**
```powershell
Install-Package Aspose.Email
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Email“ und wählen Sie die neueste Version zur Installation aus.

#### Lizenzerwerb
- **Kostenlose Testversion:** Laden Sie eine kostenlose Testversion herunter von [Aspose Downloads](https://releases.aspose.com/email/net/).
- **Temporäre Lizenz:** Fordern Sie eine temporäre Lizenz an unter [Aspose Temporäre Lizenz](https://purchase.aspose.com/temporary-license/) für erweiterte Tests.
- **Kaufen:** Für eine langfristige Nutzung sollten Sie den Kauf einer Lizenz über [Aspose Kauf](https://purchase.aspose.com/buy).

Sobald Sie das Paket installiert und Ihre Lizenz eingerichtet haben, initialisieren Sie Aspose.Email wie folgt:
```csharp
// Grundlegendes Initialisierungsbeispiel (nicht in allen Kontexten obligatorisch)
var license = new Aspose.Email.License();
license.SetLicense("path_to_your_license_file.lic");
```

## Implementierungshandbuch

Dieser Abschnitt behandelt zwei Hauptfunktionen: das Erstellen einer wöchentlich wiederkehrenden Aufgabe und das Berechnen von Vorkommen.

### Funktion 1: Wöchentliche Aufgabenerstellung mit Wiederholung

**Überblick:**
Erfahren Sie, wie Sie eine wöchentlich wiederholte MapiTask mit Aspose.Email erstellen. `MapiCalendarWeeklyRecurrencePattern`, wodurch die Aufgabenerstellung ohne manuelles Eingreifen bei jedem Vorkommen automatisiert wird.

#### Schritt 1: Datumsangaben festlegen und an die Zeitzone anpassen
```csharp
// Definieren Sie das Start-, Fälligkeits- und Enddatum für die Aufgabe
DateTime StartDate = new DateTime(2015, 7, 16);
DateTime DueDate = new DateTime(2015, 7, 16);
DateTime EndByDate = new DateTime(2015, 9, 1);

// Passen Sie Daten basierend auf der lokalen Zeitzonenverschiebung an
timeZone localZone = TimeZone.CurrentTimeZone;
TimeSpan ts = localZone.GetUtcOffset(DateTime.Now);
StartDate = StartDate.Add(ts);
DueDate = DueDate.Add(ts);
EndByDate = EndByDate.Add(ts);
```
**Erläuterung:**
Die Start-, Fälligkeits- und Enddaten der Aufgabe werden an die aktuelle Zeitzonenabweichung angepasst, um die Genauigkeit in verschiedenen Regionen sicherzustellen.

#### Schritt 2: MapiTask erstellen und konfigurieren
```csharp
// Erstellen Sie eine neue MapiTask mit den angegebenen Details
MapiTask task = new MapiTask("This is a test task", "Sample Body", StartDate, DueDate);
task.State = MapiTaskState.NotAssigned;
```
**Erläuterung:**
Initialisieren Sie den `MapiTask` Objekt mit Titel, Text, Startdatum und Fälligkeitsdatum. Setzen Sie den Aufgabenstatus auf `NotAssigned`und markiert es als ausstehend.

#### Schritt 3: Wöchentliches Wiederholungsmuster festlegen
```csharp
// Konfigurieren Sie das wöchentliche Wiederholungsmuster für die Aufgabe
var rec = new MapiCalendarWeeklyRecurrencePattern
{
    EndType = MapiCalendarRecurrenceEndType.EndAfterNOccurrences,
    PatternType = MapiCalendarRecurrencePatternType.Week,
    Period = 1,
    WeekStartDay = DayOfWeek.Sunday,
    DayOfWeek = MapiCalendarDayOfWeek.Friday,
    OccurrenceCount = GetOccurrenceCount(StartDate, EndByDate, "FREQ=WEEKLY;BYDAY=FR"),
};

// Stellen Sie sicher, dass mindestens ein Vorkommen vorliegt
if (rec.OccurrenceCount == 0)
{
    rec.OccurrenceCount = 1;
}
task.Recurrence = rec;
```
**Erläuterung:**
Mit diesem Snippet wird die Aufgabe so konfiguriert, dass sie wöchentlich am Freitag wiederholt wird. Die `GetOccurrenceCount` Die Funktion berechnet, wie viele Vorkommen zwischen dem Start- und dem Enddatum liegen.

#### Schritt 4: Aufgabe speichern
```csharp
// Speichern Sie die Aufgabe in einer Datei im angegebenen Ausgabeverzeichnis
string outputPath = "@YOUR_OUTPUT_DIRECTORY/Weekly_out.msg";
task.Save(outputPath, TaskSaveFormat.Msg);
```
**Erläuterung:**
Die abgeschlossene Aufgabe wird als MSG-Datei gespeichert. Stellen Sie sicher, dass Sie `@YOUR_OUTPUT_DIRECTORY` mit Ihrem tatsächlichen Pfad.

### Funktion 2: Berechnen von Vorkommen zwischen zwei Daten mit der Wiederholungsregel

**Überblick:**
Bestimmen Sie die Anzahl der wiederkehrenden Ereignisse zwischen zwei Daten mit Aspose.Email's `CalendarRecurrence` Klasse.

#### Schritt 1: Termine und Wiederholungsregel definieren
```csharp
// Legen Sie Start- und Enddaten fest, um Vorkommen zu berechnen
DateTime Start = new DateTime(2015, 7, 16);
DateTime EndBy = new DateTime(2015, 9, 1);
string RRule = "FREQ=WEEKLY;BYDAY=FR";
```
**Erläuterung:**
Diese Variablen legen den Datumsbereich fest und definieren eine Regel für wöchentliche Vorkommnisse an Freitagen.

#### Schritt 2: Vorkommen berechnen
```csharp
// Ermitteln Sie die Anzahl der Vorkommen zwischen den beiden Daten basierend auf der Wiederholungsregel
uint occurrenceCount = GetOccurrenceCount(Start, EndBy, RRule);
```
**Erläuterung:**
Die Funktion berechnet, wie oft die Aufgabe innerhalb des angegebenen Zeitraums wiederholt wird.

#### Schritt 3: Implementieren `GetOccurrenceCount` Verfahren
```csharp
private static uint GetOccurrenceCount(DateTime start, DateTime endBy, string rrule)
{
    // Erstellen Sie ein CalendarRecurrence-Objekt mit den Formaten DTSTART und RRULE
    CalendarRecurrence pattern = new CalendarRecurrence(string.Format("DTSTART:{0}\r\nRRULE:{1}", start.ToString("yyyyMMdd"), rrule));

    // Vorkommen innerhalb des angegebenen Datumsbereichs generieren
    DateCollection dates = pattern.GenerateOccurrences(start, endBy);

    // Gibt die Anzahl der generierten Vorkommen zurück
    return (uint)dates.Count;
}
```
**Erläuterung:**
Der `CalendarRecurrence` Das Objekt wird mit einem Startdatum und einer Wiederholungsregel initialisiert und generiert Vorkommen, die innerhalb des angegebenen Bereichs liegen.

## Praktische Anwendungen

Erkunden Sie reale Szenarien, in denen wöchentlich wiederkehrende Aufgaben integriert werden können:
1. **Projektmanagement:** Automatisieren Sie regelmäßige Erinnerungen an Statusaktualisierungen für Teammitglieder nach einem festgelegten Zeitplan.
2. **Finanzen:** Planen Sie die wöchentliche Erstellung und Verteilung von Finanzberichten an die Stakeholder.
3. **Kundendienst:** Richten Sie wöchentliche Folgeanrufe oder E-Mails an wichtige Kunden ein, um Service-Feedback zu erhalten.
4. **Personalverwaltung:** Implementieren Sie regelmäßige Leistungsbeurteilungspläne für Mitarbeiter.
5. **Gesundheitspflege:** Automatisieren Sie die Planung routinemäßiger Patientenuntersuchungen oder Medikamentenerinnerungen.

## Überlegungen zur Leistung

Beachten Sie beim Arbeiten mit Aspose.Email in .NET die folgenden Tipps:
- Überwachen Sie die Speichernutzung, um eine effiziente Ressourcenverwaltung sicherzustellen.
- Optimieren Sie Datumsmanipulationen und Aufgabenkonfigurationen für höhere Geschwindigkeit.
- Überprüfen Sie regelmäßig die Leistungskennzahlen und passen Sie die Einstellungen nach Bedarf an.

**Bewährte Methoden:**
- Entsorgen Sie Gegenstände ordnungsgemäß mit `using` Abrechnungen oder manuelle Entsorgung, um zeitnah Ressourcen freizugeben.
- Testen Sie die Lösung in einer Staging-Umgebung, bevor Sie sie in der Produktion bereitstellen.

## Abschluss

In dieser Anleitung erfahren Sie, wie Sie wöchentlich wiederkehrende Aufgaben mit Aspose.Email für .NET effizient automatisieren. Dieses Tool verbessert Ihre Fähigkeit, wiederkehrende Aufgaben zu verwalten und stellt sicher, dass nichts übersehen wird.

### Nächste Schritte:
- Experimentieren Sie mit verschiedenen Wiederholungsmustern.
- Entdecken Sie weitere Funktionen von Aspose.Email.
- Geben Sie diese Lösung innerhalb Ihres Teams oder Ihrer Organisation weiter, um ihre Wirkung zu verstärken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}