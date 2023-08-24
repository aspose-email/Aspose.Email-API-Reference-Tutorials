---
title: Angeben von Empfängeradressen in C#
linktitle: Angeben von Empfängeradressen in C#
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie Empfängeradressen in C# mit Aspose.Email für .NET angeben. E-Mails effizient erstellen, konfigurieren und versenden.
type: docs
weight: 19
url: /de/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/
---


Dieser Leitfaden führt Sie durch den Prozess der Angabe von Empfängeradressen in C# mithilfe der Aspose.Email für .NET-Bibliothek. Aspose.Email ist eine leistungsstarke .NET-API, die Ihnen die Arbeit mit E-Mail-Nachrichten und verschiedenen E-Mail-bezogenen Aufgaben ermöglicht. In diesem Tutorial erfahren Sie, wie Sie mithilfe der Bibliothek Empfängeradressen zu einer E-Mail-Nachricht hinzufügen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio oder eine beliebige C#-Entwicklungsumgebung installiert.
2. Aspose.Email für .NET-Bibliothek. Sie erhalten es von der[Aspose.Email für .NET-Versionen](https://releases.aspose.com/email/net/).

## Schritte

Befolgen Sie diese Schritte, um Empfängeradressen in C# mit Aspose.Email für .NET anzugeben:

### 1. Erstellen Sie ein neues C#-Projekt

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer Entwicklungsumgebung.

### 2. Fügen Sie einen Verweis auf Aspose.Email hinzu

1. Laden Sie die Aspose.Email für .NET-Bibliothek herunter und installieren Sie sie, falls Sie dies noch nicht getan haben.
2. Öffnen Sie Ihr C#-Projekt.
3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf „Referenzen“ und wählen Sie „Referenz hinzufügen“.
4. Durchsuchen Sie die heruntergeladenen Aspose.Email-DLL-Dateien und wählen Sie sie aus.

### 3. Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die erforderlichen Namespaces für die Verwendung von Aspose.Email-Klassen:

```csharp
using Aspose.Email;
using Aspose.Email.Mail;
```

### 4. Erstellen und konfigurieren Sie die E-Mail-Nachricht

 Erstellen Sie eine neue Instanz von`MailMessage` Klasse, um Ihre E-Mail-Nachricht darzustellen. Konfigurieren Sie den Absender und Betreff der E-Mail:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Empfängeradressen hinzufügen

Mit dem können Sie Empfängeradressen hinzufügen`To`, `Cc` , Und`Bcc` Eigenschaften der`MailMessage` Klasse. So können Sie Empfängeradressen hinzufügen:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.Cc.Add(new MailAddress("recipient2@example.com"));
message.Bcc.Add(new MailAddress("recipient3@example.com"));
```

### 6. Vervollständigen Sie die E-Mail-Nachricht

Fügen Sie Ihrer E-Mail-Nachricht den E-Mail-Text und alle anderen erforderlichen Inhalte hinzu:

```csharp
message.Body = "This is the email body.";
```

### 7. Senden Sie die E-Mail

 Zum Versenden der E-Mail können Sie die verwenden`SmtpClient` Klasse, bereitgestellt von Aspose.Email. Konfigurieren Sie die SMTP-Servereinstellungen und senden Sie die E-Mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## FAQs

###  Wie kann ich mehrere Empfänger hinzufügen?`To`, `Cc`, or `Bcc` fields?

 Sie können mehrere Empfänger hinzufügen, indem Sie die aufrufen`Add` Methode mehrmals auf der jeweiligen`MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Kann ich Empfängernamen zusammen mit ihren E-Mail-Adressen angeben?

Ja, Sie können beim Hinzufügen von Empfängern sowohl den Namen als auch die E-Mail-Adresse des Empfängers angeben:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Wie gehe ich mit Ausnahmen beim Versenden einer E-Mail um?

Sie können Try-Catch-Blöcke verwenden, um Ausnahmen zu behandeln, die beim E-Mail-Versand auftreten können:

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Email sent successfully.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
```

 Weitere Informationen und erweiterte Funktionen von Aspose.Email für .NET finden Sie im[Aspose API-Referenzen](https://reference.aspose.com/email/net/).

Damit ist die Anleitung zum Angeben von Empfängeradressen in C# mit Aspose.Email für .NET abgeschlossen. Sie haben gelernt, wie Sie mithilfe der Bibliotheksfunktionen eine E-Mail-Nachricht erstellen, Empfängeradressen hinzufügen und die E-Mail versenden.