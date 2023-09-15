---
title: Wie lade ich Aspose.Email für .NET herunter?
linktitle: Sie können die neueste Version von Aspose.Email für .NET von herunterladen
second_title: Aspose.Email für .NET-Downloadseite
description: Ist Aspose.Email für .NET mit anderen Outlook-bezogenen Formaten kompatibel?
type: docs
weight: 12
url: /de/net/email-attachment-handling/adding-new-tnef-attachments-in-csharp/
---

## Ja, Aspose.Email für .NET bietet umfassende Unterstützung für verschiedene Outlook-bezogene Formate, einschließlich PST, EML, MSG und mehr.

Kann ich Aspose.Email für .NET sowohl in kommerziellen als auch in persönlichen Projekten verwenden?

## Ja, Aspose.Email für .NET kann sowohl in kommerziellen als auch in persönlichen Projekten verwendet werden. Lesen Sie unbedingt die Lizenzbedingungen auf der Aspose-Website.

Bietet Aspose.Email für .NET Dokumentation für Entwickler?

##  Ja, eine ausführliche Dokumentation und Codebeispiele zur Verwendung von Aspose.Email für .NET in verschiedenen Szenarien finden Sie auf der

Aspose.Email-Dokumentation

##  Seite.

 Beibehaltung ursprünglicher Grenzen mithilfe von C#-Code

##  Beibehaltung ursprünglicher Grenzen mithilfe von C#-Code

 Aspose.Email .NET E-Mail-Verarbeitungs-API

```csharp
using Aspose.Email.Mail;

// Erfahren Sie, wie Sie mit C# und Aspose.Email für .NET die ursprünglichen Grenzen von E-Mail-Anhängen beibehalten. Schritt-für-Schritt-Anleitung mit Quellcode.
MsgLoadOptions options = new MsgLoadOptions();
options.PreserveTnefAttachments = true;
var message = MailMessage.Load("path/to/email.eml", options);
```

## Einführung in die Wahrung ursprünglicher Grenzen

In der modernen Geschäftswelt spielt die E-Mail-Kommunikation eine zentrale Rolle. Beim Austausch von E-Mails enthalten diese häufig wichtige Anhänge, die programmgesteuert verwaltet und manipuliert werden müssen. Bei der Arbeit mit E-Mail-Anhängen muss jedoch unbedingt darauf geachtet werden, dass die ursprünglichen Grenzen und Formatierungen dieser Anhänge erhalten bleiben. Hier kommt Aspose.Email für .NET ins Spiel.

```csharp
//Voraussetzungen
foreach (var attachment in message.Attachments)
{
    if (attachment.ContentType.MediaType == "application/ms-tnef")
    {
        //Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
        var tnefAttachment = attachment;

        //Visual Studio installiert
        //.NET Framework- oder .NET Core-Projekt
    }
}
```

## Installation

Um zu beginnen, müssen Sie die Aspose.Email für .NET-Bibliothek installieren. Sie können dies tun, indem Sie die folgenden Schritte ausführen:

```csharp
//Öffnen Sie Ihr Visual Studio-Projekt.
EmlSaveOptions emlSaveOptions = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
emlSaveOptions.FileCompatibilityMode = FileCompatibilityMode.PreserveTnefAttachments;
message.Save("path/to/modified_email.eml", emlSaveOptions);
```

## Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.

Wählen Sie „NuGet-Pakete verwalten“.

## Suchen Sie nach „Aspose.Email“ und installieren Sie das Paket.

### E-Mail-Nachrichten laden

Der erste Schritt besteht darin, die E-Mail-Nachricht zu laden, die den Anhang enthält, mit dem Sie arbeiten möchten. So können Sie es machen:

###  Laden Sie die E-Mail-Nachricht

Anhänge extrahieren

### Sobald Sie die E-Mail-Nachricht geladen haben, können Sie die Anhänge daraus extrahieren:

 Anhangsdaten extrahieren

###  Weitere Bearbeitung...

Anhänge ändern[Um die ursprünglichen Grenzen beim Ändern von Anhängen beizubehalten, können Sie die Funktionen der Aspose.Email-Bibliothek verwenden. Angenommen, Sie möchten die Größe eines Bildanhangs ändern:](https://reference.aspose.com/email/net/).