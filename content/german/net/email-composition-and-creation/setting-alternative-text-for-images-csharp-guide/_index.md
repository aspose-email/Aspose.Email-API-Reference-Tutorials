---
title: Alternativtext für Bilder festlegen – C#-Handbuch
linktitle: Alternativtext für Bilder festlegen – C#-Handbuch
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Email für .NET alternativen Text für Bilder in E-Mails festlegen. Stellen Sie die Barrierefreiheit mit klarem Alt-Text sicher. Dokumentation und Code enthalten.
type: docs
weight: 15
url: /de/net/email-composition-and-creation/setting-alternative-text-for-images-csharp-guide/
---

Dieser Leitfaden führt Sie durch den Prozess des Festlegens alternativer Texte für Bilder in E-Mails mit Aspose.Email für .NET. Alternativer Text, auch „Alt-Text“ genannt, wird verwendet, um eine Textbeschreibung eines Bildes bereitzustellen, falls das Bild nicht angezeigt werden kann. Aspose.Email für .NET ist eine leistungsstarke Bibliothek, die es Ihnen ermöglicht, mit E-Mails und Anhängen in verschiedenen Formaten zu arbeiten. In diesem Leitfaden konzentrieren wir uns auf das Festlegen alternativer Texte für Bilder in E-Mail-Nachrichten mit C#.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio oder eine beliebige kompatible C#-Entwicklungsumgebung installiert.
2. Aspose.Email für .NET-Bibliothek. Sie können den NuGet-Paket-Manager in Visual Studio verwenden.

## Schritt 1: Erstellen Sie ein neues Projekt

1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Konsolenanwendungsprojekt.

## Schritt 2: Installieren Sie Aspose.Email über NuGet

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“.
2. Suchen Sie nach „Aspose.Email“ und installieren Sie die neueste Version des Pakets.

## Schritt 3: Using-Anweisungen hinzufügen

```csharp
using Aspose.Email.Mail;
using Aspose.Email.Mime;
```

## Schritt 4: Laden und ändern Sie die E-Mail-Nachricht

1.  Laden Sie die E-Mail-Nachricht mit`MailMessage` Klasse:

```csharp
MailMessage message = new MailMessage();
message.Subject = "Sample Email with Alternative Text";
message.From = new MailAddress("sender@example.com");
message.To.Add("recipient@example.com");
```

2.  Erstellen Sie eine Instanz von`MhtmlMessageFormatter`Klasse zum Formatieren der Nachricht:

```csharp
MhtmlMessageFormatter formatter = new MhtmlMessageFormatter();
```

3. Laden Sie den HTML-Inhalt der E-Mail-Nachricht:

```csharp
string htmlContent = "<html><body><img src='cid:logo.jpg' alt='Company Logo'></body></html>";
formatter.SetBodyContent(htmlContent, "text/html");
```

## Schritt 5: Alternativtext zu Bildern hinzufügen

1.  Suchen Sie die`AlternateView` Enthält den HTML-Text und die Bilder:

```csharp
AlternateView htmlView = message.AlternateViews.GetHtmlView();
```

2.  Suchen Sie die`LinkedResource` Darstellung des Bildes:

```csharp
LinkedResource linkedResource = htmlView.LinkedResources.GetLinkedResourceByContentId("logo.jpg");
```

3. Legen Sie den alternativen Text für das Bild fest:

```csharp
linkedResource.AlternateText = "Company Logo";
```

## Schritt 6: Speichern und senden Sie die E-Mail

1. Speichern Sie die geänderte Nachricht in einer Datei oder senden Sie sie mit der gewünschten Methode:

```csharp
message.Save("output.eml", SaveOptions.DefaultEml);
```

## Abschluss

In dieser Anleitung haben Sie erfahren, wie Sie mit Aspose.Email für .NET alternativen Text für Bilder in E-Mail-Nachrichten festlegen. Indem Sie die oben beschriebenen Schritte befolgen, können Sie sicherstellen, dass Ihre E-Mail-Inhalte auch dann zugänglich und informativ bleiben, wenn Bilder nicht angezeigt werden können.

## FAQ

## Wie kann ich die Aspose.Email-Bibliothek herunterladen?

Sie können die Aspose.Email-Bibliothek aus den Aspose-Releases herunterladen oder über den NuGet Package Manager in Visual Studio installieren.

### Wie füge ich Bilder als verknüpfte Ressourcen in einer E-Mail hinzu?

 Um Bilder als verknüpfte Ressourcen in einer E-Mail hinzuzufügen, können Sie die verwenden`LinkedResource`Klasse. Weisen Sie der verknüpften Ressource eine Inhalts-ID zu und verweisen Sie dann im HTML-Text auf diese Inhalts-ID mithilfe von`cid:` planen. Ausführliche Informationen finden Sie im[LinkedResource-Dokumentation](https://reference.aspose.com/email/net/aspose.email/linkedresource/).
### Wo finde ich weitere Dokumentation zu Aspose.Email für .NET?

 Ausführlichere Dokumentation, Tutorials und Beispiele zum Arbeiten mit Aspose.Email für .NET finden Sie im[API-Referenz](https://reference.aspose.com/email/net/).