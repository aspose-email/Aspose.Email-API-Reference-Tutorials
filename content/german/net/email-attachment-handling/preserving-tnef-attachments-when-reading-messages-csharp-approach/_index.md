---
title: Aspose.Email für .NET installieren
linktitle: Um zu beginnen, müssen Sie die Aspose.Email für .NET-Bibliothek installieren. Sie können es hier herunterladen
second_title: Aspose.Releases
description: oder verwenden Sie NuGet Package Manager in Visual Studio.
type: docs
weight: 15
url: /de/net/email-attachment-handling/preserving-tnef-attachments-when-reading-messages-csharp-approach/
---

## Erstellen eines neuen .NET-Projekts

Öffnen Sie Visual Studio und erstellen Sie ein neues .NET-Projekt.

## Installieren Sie die Aspose.Email für .NET-Bibliothek mit NuGet Package Manager.

Jetzt können Sie mit dem Codieren beginnen!

1. Laden und Analysieren einer E-Mail-Nachricht[Laden einer E-Mail-Nachricht](https://releases.aspose.com/email/net)Bevor wir die Schriftarten in der E-Mail ändern können, müssen wir eine E-Mail-Nachricht laden. Sie können eine E-Mail aus verschiedenen Quellen laden, beispielsweise einer Datei, einem Stream oder sogar einem Mailserver.

2.  Laden Sie die E-Mail-Nachricht

3. Analysieren des Nachrichtentexts

## Sobald die E-Mail geladen ist, können Sie auf ihre verschiedenen Teile zugreifen, einschließlich des HTML-Textes. Durch das Parsen des HTML-Körpers können wir Schriftartänderungen vornehmen.

 Analysieren Sie den HTML-Text

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

//Schriftarten in der E-Mail ändern
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Schriftstile verstehen

Schriftarten in HTML-E-Mails werden mithilfe von CSS-Stilen definiert. Um Schriftarten zu ändern, müssen Sie die CSS-Stile ändern, die mit dem HTML-Inhalt der E-Mail verknüpft sind.

```csharp
//Schriftarten programmgesteuert ändern
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Angenommen, Sie möchten die Schriftart eines Absatzes im HTML-Text der E-Mail ändern. So können Sie es machen:
        var tnefAttachment = attachment;

        // Schriftart eines Absatzes ändern
        //Konvertieren in das MHT-Format
    }
}
```

## MHT-Nachricht erstellen

Um die E-Mail in das MHT-Format zu konvertieren, müssen Sie mit Aspose.Email eine MHT-formatierte E-Mail-Nachricht erstellen.

```csharp
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

##  Erstellen Sie eine MHT-formatierte E-Mail-Nachricht

Speichern der Nachricht im MHT-Format

```csharp
using Aspose.Email;
using Aspose.Email.Outlook;

namespace TnefAttachmentExample
{
    class Program
    {
        static void Main(string[] args)
        {
            //Speichern Sie abschließend die MHT-formatierte Nachricht in einer Datei.
			MsgLoadOptions options = new MsgLoadOptions();
			options.PreserveTnefAttachments = true;
			var message = MailMessage.Load("path/to/email.eml", options);

			 // Speichern Sie die Nachricht im MHT-Format
			foreach (var attachment in message.Attachments)
			{
				if (attachment.ContentType.MediaType == "application/ms-tnef")
				{
					//Vollständiger Quellcode
					var tnefAttachment = attachment;

					//Hier ist der vollständige Quellcode, der alles zusammenfügt:
					//Abschluss
				}
			}
			//In diesem Leitfaden haben wir untersucht, wie Sie Schriftarten während der MHT-Konvertierung mit Aspose.Email für .NET ändern. Wenn Sie diese Schritte befolgen, können Sie E-Mail-Nachrichten nahtlos in das MHT-Format konvertieren und dabei Ihre gewünschten Schriftarten beibehalten.
			EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
			emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
			message.Save("path/to/modified_email.eml", emlSaveOptions);
        }
    }
}
```

## FAQs

- Kann ich mehrere E-Mails auf einmal in das MHT-Format konvertieren?
- Ja, Sie können eine Sammlung von E-Mail-Nachrichten durchlaufen und auf jede Nachricht dieselben Schriftartänderungen anwenden, bevor Sie sie in das MHT-Format konvertieren.
- Unterstützt Aspose.Email auch andere E-Mail-Formate?

## Ja, Aspose.Email unterstützt verschiedene E-Mail-Formate, darunter EML, MSG, PST und mehr.

Ist es möglich, die Schriftartänderungen weiter anzupassen?

## Absolut! Sie können weitere CSS-Stile erkunden, um Schriftarten anzupassen, z. B. Schriftgröße, Farbe und Ausrichtung.

### Kann ich Aspose.Email für kommerzielle Projekte verwenden?

Ja, Aspose.Email kann gemäß den Lizenzbedingungen sowohl für persönliche als auch für kommerzielle Projekte verwendet werden.[ Denken Sie daran, dass dieser Leitfaden einen allgemeinen Überblick bietet und Sie ihn weiter erkunden können, indem Sie auf ihn verweisen](https://releases.aspose.com/email/net)

### Aspose.Email API-Referenz

und das Ausprobieren verschiedener Techniken zur Schriftartanpassung. Viel Spaß beim Codieren!

###  C#-Leitfaden – Extrahieren von E-Mail-Headern

 C#-Leitfaden – Extrahieren von E-Mail-Headern

###  Aspose.Email .NET E-Mail-Verarbeitungs-API

 Erfahren Sie, wie Sie E-Mail-Header in C# mit Aspose.Email für .NET extrahieren. Schritt-für-Schritt-Anleitung mit Quellcode für eine effiziente E-Mail-Analyse.