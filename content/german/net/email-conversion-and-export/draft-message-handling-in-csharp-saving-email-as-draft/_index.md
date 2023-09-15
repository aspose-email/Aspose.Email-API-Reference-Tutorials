---
title: Umgang mit Nachrichtenentwürfen in C# – E-Mail als Entwurf speichern
linktitle: Umgang mit Nachrichtenentwürfen in C# – E-Mail als Entwurf speichern
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie die Bearbeitung von E-Mail-Entwürfen in C# mit Aspose.Email für .NET implementieren. Erstellen, bearbeiten und speichern Sie Entwürfe nahtlos.
type: docs
weight: 17
url: /de/net/email-conversion-and-export/draft-message-handling-in-csharp-saving-email-as-draft/
---

## Einführung

Die Bearbeitung von Nachrichtenentwürfen ist eine entscheidende Funktionalität für E-Mail-Clients. Benutzer benötigen häufig die Möglichkeit, mit dem Verfassen einer E-Mail zu beginnen, sie als Entwurf zu speichern und später zur weiteren Bearbeitung oder zum eventuellen Versenden darauf zurückzukommen. In diesem Artikel wird gezeigt, wie Sie diese Funktion mithilfe der Aspose.Email für .NET-Bibliothek implementieren.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio (oder eine beliebige C#-Entwicklungsumgebung)
- Aspose.Email für .NET-Bibliothek

 Sie können die Aspose.Email-Bibliothek herunterladen von[Hier](https://releases.aspose.com/email/net).

## Einrichten des Projekts

1. Erstellen Sie ein neues C#-Projekt in Ihrer Entwicklungsumgebung.
2. Fügen Sie Verweise auf die Aspose.Email-DLLs in Ihrem Projekt hinzu.

## Erstellen des E-Mail-Entwurfs

Um einen Nachrichtenentwurf zu erstellen, gehen Sie folgendermaßen vor:

## Empfänger und Betreff hinzufügen

```csharp
// Erstellen Sie eine neue MailMessage-Instanz
MailMessage draft = new MailMessage();

// Empfänger hinzufügen
draft.To.Add("recipient@example.com");
draft.Cc.Add("cc@example.com");
draft.Bcc.Add("bcc@example.com");

// E-Mail-Betreff festlegen
draft.Subject = "Draft Email Demo";
```

## E-Mail-Text verfassen

```csharp
// E-Mail-Text festlegen
draft.Body = new TextBody("Hello, this is a draft email.");
```

## Als Entwurf speichern

```csharp
// Speichern Sie die E-Mail als Entwurf
draft.Save("draft.eml", SaveOptions.DefaultEml);
```

## Entwürfe laden und bearbeiten

Um Nachrichtenentwürfe zu laden und zu bearbeiten, gehen Sie folgendermaßen vor:

```csharp
// Laden Sie einen E-Mail-Entwurf
MailMessage loadedDraft = MailMessage.Load("draft.eml");

// Empfänger bearbeiten
loadedDraft.To.Clear();
loadedDraft.To.Add("newrecipient@example.com");

// E-Mail-Text bearbeiten
loadedDraft.Body = new TextBody("Updated draft content.");

// Änderungen speichern
loadedDraft.Save("updated_draft.eml", SaveOptions.DefaultEml);
```

## Abschluss

In diesem Artikel haben wir untersucht, wie Entwurfsnachrichten in C# mithilfe der Aspose.Email für .NET-Bibliothek verarbeitet werden. Wir haben gelernt, wie man E-Mail-Entwürfe erstellt, bearbeitet und speichert, um Benutzern ein nahtloses Erlebnis beim Verfassen von Nachrichten zu bieten. Indem Sie die in dieser Anleitung beschriebenen Schritte befolgen, können Sie Ihre E-Mail-Client-Anwendung mit der Funktionalität für Nachrichtenentwürfe erweitern.

## FAQs

### Wie lade ich die Aspose.Email für .NET-Bibliothek herunter?

 Sie können die Aspose.Email für .NET-Bibliothek unter herunterladen[Hier](https://releases.aspose.com/email/net).

### Kann ich die Empfänger und den Betreff eines gespeicherten Entwurfs bearbeiten?

Ja, Sie können einen gespeicherten Entwurf laden, dessen Empfänger, Betreff und Inhalt bearbeiten und die Änderungen dann als aktualisierten Entwurf speichern.

### Wird der E-Mail-Entwurf in einem bestimmten Format gespeichert?

Ja, der E-Mail-Entwurf wird im EML-Format gespeichert, einem weit verbreiteten Format für E-Mail-Nachrichten.

### Kann ich die Bearbeitung von Nachrichtenentwürfen in meine bestehende E-Mail-Anwendung integrieren?

Auf jeden Fall können Sie die Bearbeitung von Nachrichtenentwürfen nahtlos in Ihre bestehende E-Mail-Client-Anwendung integrieren, indem Sie die in diesem Leitfaden beschriebenen Schritte befolgen.

### Unterstützt die Aspose.Email-Bibliothek andere E-Mail-bezogene Funktionen?

 Ja, die Aspose.Email-Bibliothek bietet eine breite Palette von Funktionen für die Arbeit mit E-Mail-Nachrichten, einschließlich des Sendens, Empfangens und Bearbeitens von E-Mails und Anhängen. Weitere Einzelheiten finden Sie in der Dokumentation:[Hier](https://reference.aspose.com)