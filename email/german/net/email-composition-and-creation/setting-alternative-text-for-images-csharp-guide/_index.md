---
"description": "Erfahren Sie, wie Sie mit Aspose.Email für .NET Alternativtexte für Bilder in E-Mails festlegen. Sorgen Sie für Barrierefreiheit mit klarem Alternativtext. Dokumentation und Code inklusive."
"linktitle": "Festlegen von Alternativtext für Bilder – C#-Handbuch"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "Festlegen von Alternativtext für Bilder – C#-Handbuch"
"url": "/de/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Festlegen von Alternativtext für Bilder – C#-Handbuch


Diese Anleitung führt Sie durch das Festlegen von Alternativtext für Bilder in E-Mails mit Aspose.Email für .NET. Alternativtext, auch „Alt-Text“ genannt, dient zur textuellen Beschreibung eines Bildes, falls dieses nicht angezeigt werden kann. Aspose.Email für .NET ist eine leistungsstarke Bibliothek, die Ihnen die Arbeit mit E-Mails und Anhängen in verschiedenen Formaten ermöglicht. In dieser Anleitung konzentrieren wir uns auf das Festlegen von Alternativtext für Bilder in E-Mail-Nachrichten mit C#.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio oder eine andere kompatible C#-Entwicklungsumgebung installiert.
2. Aspose.Email für die .NET-Bibliothek. Sie können den NuGet-Paket-Manager in Visual Studio verwenden.

## Schritt 1: Neues Projekt erstellen

1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Konsolenanwendungsprojekt.

## Schritt 2: Installieren Sie Aspose.Email über NuGet

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
2. Suchen Sie nach „Aspose.Email“ und installieren Sie die neueste Version des Pakets.

## Schritt 3: Using-Anweisungen hinzufügen

```csharp

using Aspose.Email.Mime;
```

## Schritt 4: Laden und Ändern der E-Mail-Nachricht

1. Laden Sie die E-Mail-Nachricht mit dem `MailMessage` Klasse:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

3. Laden Sie den HTML-Inhalt der E-Mail-Nachricht:

```csharp
var htmlView = AlternateView.CreateAlternateViewFromString("<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>", null, "text/html");
```

## Schritt 5: AlternativeView für alternativen Text zu Bildern hinzufügen

Fügen Sie der Nachricht eine HTML-Ansicht für Alternativtext zum Bild als AlternateView hinzu. 
```csharp
message.AlternateViews.Add(htmlView);
```

## Schritt 6: Speichern und senden Sie die E-Mail

1. Speichern Sie die geänderte Nachricht in einer Datei oder senden Sie sie mit der gewünschten Methode:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Abschluss

In dieser Anleitung haben Sie gelernt, wie Sie mit Aspose.Email für .NET Alternativtext für Bilder in E-Mail-Nachrichten festlegen. Mit den oben beschriebenen Schritten stellen Sie sicher, dass Ihre E-Mail-Inhalte auch dann zugänglich und informativ bleiben, wenn keine Bilder angezeigt werden können.

## Häufig gestellte Fragen

## Wie kann ich die Aspose.Email-Bibliothek herunterladen?

Sie können die Aspose.Email-Bibliothek aus den Aspose-Releases herunterladen oder über den NuGet-Paket-Manager in Visual Studio installieren.

### Wie füge ich Bilder als verknüpfte Ressourcen in einer E-Mail hinzu?

Um Bilder als verknüpfte Ressourcen in einer E-Mail hinzuzufügen, können Sie die `LinkedResource` Klasse. Weisen Sie der verknüpften Ressource eine Inhalts-ID zu und verweisen Sie dann im HTML-Textkörper mit dem `cid:` Schema. Detaillierte Informationen finden Sie im [LinkedResource-Dokumentation](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Wo finde ich weitere Dokumentation zu Aspose.Email für .NET?

Ausführlichere Dokumentationen, Tutorials und Beispiele zur Arbeit mit Aspose.Email für .NET finden Sie im [API-Referenz](https://reference.aspose.com/email/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}