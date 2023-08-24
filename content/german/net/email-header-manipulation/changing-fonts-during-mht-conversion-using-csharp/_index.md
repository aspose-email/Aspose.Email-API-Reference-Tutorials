---
title: Schriftarten während der MHT-Konvertierung mit C# ändern
linktitle: Schriftarten während der MHT-Konvertierung mit C# ändern
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie Schriftarten während der MHT-Konvertierung mit Aspose.Email für .NET ändern. Schritt-für-Schritt-Anleitung mit Quellcode. Perfekt für die E-Mail-Archivierung und Dokumentenverwaltung.
type: docs
weight: 11
url: /de/net/email-header-manipulation/changing-fonts-during-mht-conversion-using-csharp/
---

Haben Sie schon einmal die Notwendigkeit gehabt, eine E-Mail-Nachricht in das MHT-Format zu konvertieren und dabei den Schriftstil beizubehalten? Dieser Leitfaden führt Sie durch den Prozess des Änderns von Schriftarten während der MHT-Konvertierung mithilfe der leistungsstarken Aspose.Email für .NET-Bibliothek. Egal, ob Sie an der E-Mail-Archivierung, Dokumentenverwaltung oder einem anderen Projekt arbeiten, das die E-Mail-Konvertierung beinhaltet, diese Schritt-für-Schritt-Anleitung hilft Ihnen dabei, Ihr Ziel nahtlos zu erreichen.

## Einführung in die MHT-Konvertierung und Aspose.Email für .NET

### Was ist MHT?

MHT (MIME HTML) ist ein Dateiformat, das es Ihnen ermöglicht, eine Webseite einschließlich aller ihrer Ressourcen in einem einzigen Dokument zu speichern. Es wird häufig zum Archivieren von Webseiten und E-Mail-Nachrichten verwendet, da es die Struktur und das Erscheinungsbild des ursprünglichen Inhalts beibehält.

### Über Aspose.Email für .NET

Aspose.Email für .NET ist eine robuste Bibliothek, die Funktionen für die Arbeit mit E-Mail-Formaten bietet, einschließlich Laden, Parsen und Konvertieren von E-Mails. Es ist eine ideale Wahl für Entwickler, die verschiedene E-Mail-bezogene Aufgaben effizient erledigen müssen.

## Einrichten Ihres Projekts

### Aspose.Email für .NET installieren

 Um zu beginnen, müssen Sie die Aspose.Email für .NET-Bibliothek installieren. Sie können es hier herunterladen[Aspose.Releases](https://releases.aspose.com/email/net) oder verwenden Sie NuGet Package Manager in Visual Studio.

### Erstellen eines neuen .NET-Projekts

1. Öffnen Sie Visual Studio und erstellen Sie ein neues .NET-Projekt.
2. Installieren Sie die Aspose.Email für .NET-Bibliothek mit NuGet Package Manager.
3. Jetzt können Sie mit dem Codieren beginnen!

## Laden und Analysieren einer E-Mail-Nachricht

### Laden einer E-Mail-Nachricht

Bevor wir die Schriftarten in der E-Mail ändern können, müssen wir eine E-Mail-Nachricht laden. Sie können eine E-Mail aus verschiedenen Quellen laden, beispielsweise einer Datei, einem Stream oder sogar einem Mailserver.

```csharp
// Laden Sie die E-Mail-Nachricht
var message = MailMessage.Load("sample.eml");
```

### Analysieren des Nachrichtentexts

Sobald die E-Mail geladen ist, können Sie auf ihre verschiedenen Teile zugreifen, einschließlich des HTML-Textes. Durch das Parsen des HTML-Körpers können wir Schriftartänderungen vornehmen.

```csharp
// Analysieren Sie den HTML-Text
var htmlBody = message.HtmlBody;
```

## Schriftarten in der E-Mail ändern

### Schriftstile verstehen

Schriftarten in HTML-E-Mails werden mithilfe von CSS-Stilen definiert. Um Schriftarten zu ändern, müssen Sie die CSS-Stile ändern, die mit dem HTML-Inhalt der E-Mail verknüpft sind.

### Schriftarten programmgesteuert ändern

Angenommen, Sie möchten die Schriftart eines Absatzes im HTML-Text der E-Mail ändern. So können Sie es machen:

```csharp
// Schriftart eines Absatzes ändern
htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");
```

## Konvertieren in das MHT-Format

### MHT-Nachricht erstellen

Um die E-Mail in das MHT-Format zu konvertieren, müssen Sie mit Aspose.Email eine MHT-formatierte E-Mail-Nachricht erstellen.

```csharp
// Erstellen Sie eine MHT-formatierte E-Mail-Nachricht
var mhtMessage = MhtMessage.FromMailMessage(message);
```

### Speichern der Nachricht im MHT-Format

Speichern Sie abschließend die MHT-formatierte Nachricht in einer Datei.

```csharp
// Speichern Sie die Nachricht im MHT-Format
mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
```

## Vollständiger Quellcode

Hier ist der vollständige Quellcode, der alles zusammenfügt:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Mhtml;

class Program
{
    static void Main()
    {
        var message = MailMessage.Load("sample.eml");
        var htmlBody = message.HtmlBody;
        htmlBody = htmlBody.Replace("<p>", "<p style=\"font-family: Arial;\">");

        var mhtMessage = MhtMessage.FromMailMessage(message);
        mhtMessage.Save("output.mht", SaveOptions.DefaultMhtml);
    }
}
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Schriftarten während der MHT-Konvertierung mit Aspose.Email für .NET ändern. Wenn Sie diese Schritte befolgen, können Sie E-Mail-Nachrichten nahtlos in das MHT-Format konvertieren und dabei Ihre gewünschten Schriftarten beibehalten.


## FAQs


### Kann ich mehrere E-Mails auf einmal in das MHT-Format konvertieren?

Ja, Sie können eine Sammlung von E-Mail-Nachrichten durchlaufen und auf jede Nachricht dieselben Schriftartänderungen anwenden, bevor Sie sie in das MHT-Format konvertieren.

### Unterstützt Aspose.Email auch andere E-Mail-Formate?

Ja, Aspose.Email unterstützt verschiedene E-Mail-Formate, darunter EML, MSG, PST und mehr.

### Ist es möglich, die Schriftartänderungen weiter anzupassen?

Absolut! Sie können weitere CSS-Stile erkunden, um Schriftarten anzupassen, z. B. Schriftgröße, Farbe und Ausrichtung.

### Kann ich Aspose.Email für kommerzielle Projekte verwenden?

Ja, Aspose.Email kann gemäß den Lizenzbedingungen sowohl für persönliche als auch für kommerzielle Projekte verwendet werden.

 Denken Sie daran, dass dieser Leitfaden einen allgemeinen Überblick bietet und Sie ihn weiter erkunden können, indem Sie auf ihn verweisen[Aspose.Email API-Referenz](https://reference.aspose.com/email/net/)und das Ausprobieren verschiedener Techniken zur Schriftartanpassung. Viel Spaß beim Codieren!