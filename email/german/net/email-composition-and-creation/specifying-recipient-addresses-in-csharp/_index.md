---
"description": "Erfahren Sie, wie Sie Empfängeradressen in C# mit Aspose.Email für .NET angeben. Erstellen, konfigurieren und versenden Sie E-Mails effizient."
"linktitle": "Angeben von Empfängeradressen in C#"
"second_title": "Aspose.Email .NET E-Mail-Verarbeitungs-API"
"title": "Angeben von Empfängeradressen in C#"
"url": "/de/net/email-composition-and-creation/specifying-recipient-addresses-in-csharp/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Angeben von Empfängeradressen in C#



Diese Anleitung führt Sie durch die Angabe von Empfängeradressen in C# mithilfe der Aspose.Email für .NET-Bibliothek. Aspose.Email ist eine leistungsstarke .NET-API, die Ihnen die Arbeit mit E-Mail-Nachrichten und verschiedenen E-Mail-bezogenen Aufgaben ermöglicht. In diesem Tutorial erfahren Sie, wie Sie mithilfe der Bibliothek Empfängeradressen zu einer E-Mail-Nachricht hinzufügen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio oder eine beliebige C#-Entwicklungsumgebung installiert.
2. Aspose.Email für .NET-Bibliothek. Sie erhalten es von der [Aspose.Email für .NET-Releases](https://releases.aspose.com/email/net/).

## Schritte

Befolgen Sie diese Schritte, um Empfängeradressen in C# mit Aspose.Email für .NET anzugeben:

### 1. Erstellen Sie ein neues C#-Projekt

Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer Entwicklungsumgebung.

### 2. Verweis auf Aspose.Email hinzufügen

1. Laden Sie die Aspose.Email-Bibliothek für .NET herunter und installieren Sie sie, falls Sie dies noch nicht getan haben.
2. Öffnen Sie Ihr C#-Projekt.
3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf „Referenzen“ und wählen Sie „Referenz hinzufügen“.
4. Durchsuchen und wählen Sie die heruntergeladenen Aspose.Email-DLL-Dateien aus.

### 3. Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die erforderlichen Namespaces für die Verwendung von Aspose.Email-Klassen:

```csharp
using Aspose.Email;

```

### 4. Erstellen und konfigurieren Sie die E-Mail-Nachricht

Erstellen Sie eine neue Instanz des `MailMessage` Klasse zur Darstellung Ihrer E-Mail-Nachricht. Konfigurieren Sie den Absender und den Betreff der E-Mail:

```csharp
MailMessage message = new MailMessage();
message.From = new MailAddress("sender@example.com");
message.Subject = "Hello from Aspose.Email";
```

### 5. Empfängeradressen hinzufügen

Sie können Empfängeradressen hinzufügen, indem Sie `To`, `Cc`, Und `Bcc` Eigenschaften der `MailMessage` Klasse. So können Sie Empfängeradressen hinzufügen:

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

Zum Versenden der E-Mail können Sie die `SmtpClient` Klasse bereitgestellt von Aspose.Email. Konfigurieren Sie die SMTP-Servereinstellungen und senden Sie die E-Mail:

```csharp
SmtpClient client = new SmtpClient("smtp.example.com", 587, "your_username", "your_password");
client.SecurityOptions = SecurityOptions.Auto;

client.Send(message);
```

## FAQs

### Wie kann ich mehrere Empfänger zu der `To`, `Cc`, oder `Bcc` Felder?

Sie können mehrere Empfänger hinzufügen, indem Sie die `Add` Methode mehrmals auf den jeweiligen `MailAddressCollection`:

```csharp
message.To.Add(new MailAddress("recipient1@example.com"));
message.To.Add(new MailAddress("recipient2@example.com"));
```

### Kann ich Empfängernamen zusammen mit ihren E-Mail-Adressen angeben?

Ja, Sie können beim Hinzufügen von Empfängern sowohl den Namen als auch die E-Mail-Adresse des Empfängers angeben:

```csharp
message.To.Add(new MailAddress("recipient@example.com", "Recipient Name"));
```

### Wie gehe ich mit Ausnahmen beim Senden einer E-Mail um?

Sie können Try-Catch-Blöcke verwenden, um Ausnahmen zu behandeln, die beim Senden von E-Mails auftreten können:

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

Weitere Informationen und erweiterte Funktionen von Aspose.Email für .NET finden Sie im [Aspose API-Referenzen](https://reference.aspose.com/email/net/).

Damit ist die Anleitung zum Angeben von Empfängeradressen in C# mit Aspose.Email für .NET abgeschlossen. Sie haben gelernt, wie Sie eine E-Mail-Nachricht erstellen, Empfängeradressen hinzufügen und die E-Mail mithilfe der Funktionen der Bibliothek versenden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}