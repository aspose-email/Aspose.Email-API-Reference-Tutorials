---
title: Lieferstatusbenachrichtigungen mit C# abrufen
linktitle: Lieferstatusbenachrichtigungen mit C# abrufen
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie E-Mail-Benachrichtigungen zum Zustellungsstatus mit C# und Aspose.Email für .NET abrufen.
type: docs
weight: 18
url: /de/net/email-processing-and-analysis/retrieving-delivery-status-notifications-with-csharp/
---

## Einführung

In der E-Mail-Kommunikation spielen Delivery Status Notifications (DSNs) eine entscheidende Rolle, um Absender über den Zustellstatus ihrer E-Mails zu informieren. Aspose.Email für .NET ist eine leistungsstarke Bibliothek, die Funktionen für die Arbeit mit E-Mails bereitstellt, einschließlich des Abrufens von DSNs. In diesem Leitfaden gehen wir durch den Prozess des Abrufens von Benachrichtigungen zum Lieferstatus mithilfe von C# und der Aspose.Email für .NET-Bibliothek.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio installiert.
2.  Aspose.Email für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/email/net).
3. Grundlegendes Verständnis der C#-Programmierung.

## Schritte

Befolgen Sie diese Schritte, um Benachrichtigungen zum Lieferstatus mit Aspose.Email für .NET abzurufen:

### Schritt 1: Erstellen Sie ein neues Projekt

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Konsolenanwendungsprojekt.

### Schritt 2: Aspose.Email-Referenz hinzufügen

Kopieren Sie die heruntergeladene Aspose.Email-DLL in das Verzeichnis Ihres Projekts. Klicken Sie dann im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, wählen Sie „Hinzufügen“ > „Referenz“ und suchen Sie nach der Aspose.Email-DLL. Klicken Sie auf „OK“, um die Referenz zu Ihrem Projekt hinzuzufügen.

### Schritt 3: Schreiben Sie Code zum Abrufen von DSNs

 Öffne das`Program.cs` Datei in Ihrem Projekt und importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Email;
using Aspose.Email.Imap;
using Aspose.Email.Mail;
```

 Im Inneren`Main` -Methode schreiben Sie den Code, um eine Verbindung zum E-Mail-Server herzustellen, DSNs abzurufen und sie zu verarbeiten:

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Legen Sie Ihre IMAP-Server-Anmeldeinformationen und Ihren Host fest
        string host = "your_imap_host";
        int port = 993;
        string username = "your_email";
        string password = "your_password";

        using (ImapClient client = new ImapClient(host, port, username, password))
        {
            // Wählen Sie den Posteingangsordner aus
            client.SelectFolder(ImapFolderInfo.InBox);

            // Suchen Sie nach Nachrichten mit DSNs
            MailQueryBuilder queryBuilder = new MailQueryBuilder();
            queryBuilder.HasFlags(Aspose.Email.Mail.MessageFlags.DeliveryNotification);
            MailQuery query = queryBuilder.GetQuery();
            ImapMessageInfoCollection messages = client.ListMessages(query);

            // Abgerufene DSNs verarbeiten
            foreach (ImapMessageInfo messageInfo in messages)
            {
                MailMessage message = client.FetchMessage(messageInfo.SequenceNumber);

                // DSN-Details verarbeiten
                Console.WriteLine("Subject: " + message.Subject);
                Console.WriteLine("From: " + message.From);
                // ... Verarbeiten Sie andere DSN-Details

                // Markieren Sie die Nachricht als gelesen oder löschen Sie sie
                client.DeleteMessage(messageInfo.SequenceNumber);
            }
        }
    }
}
```

 Ersetzen`"your_imap_host"`, `"your_email"` , Und`"your_password"` mit Ihren tatsächlichen IMAP-Serverdetails.

### Schritt 4: Führen Sie die Anwendung aus

Erstellen Sie Ihre Anwendung und führen Sie sie aus. Es stellt eine Verbindung zu Ihrem E-Mail-Server her, ruft DSNs aus dem Posteingangsordner ab, verarbeitet deren Details und löscht sie optional oder markiert sie als gelesen.

## FAQs

### Wie finde ich den IMAP-Server-Host?

 Den Host des IMAP-Servers finden Sie in der Dokumentation oder den Einstellungen Ihres E-Mail-Dienstanbieters. Es hat normalerweise das Format`imap.yourdomain.com`.

### Wie kann ich andere DSN-Details als Betreff und Absender verarbeiten?

 Sie können auf verschiedene Eigenschaften des zugreifen`MailMessage` Objekt zum Abrufen von DSN-Details wie Empfängeradressen, Lieferstatus, Zeitstempel und mehr. Siehe die[Aspose.Email-Dokumentation](https://reference.aspose.com/email/net/) für mehr Informationen.

### Ist es notwendig, DSNs zu löschen oder als gelesen zu markieren?

Nein, es ist nicht notwendig. Ob DSNs gelöscht oder als gelesen markiert werden, hängt von den Anforderungen Ihrer Anwendung ab. Der bereitgestellte Code demonstriert beide Optionen, Sie können ihn jedoch an Ihre Bedürfnisse anpassen.

## Abschluss

Das Abrufen von Benachrichtigungen zum Lieferstatus mit C# und Aspose.Email für .NET ist ein unkomplizierter Prozess. Die Aspose.Email-Bibliothek vereinfacht die Kommunikation mit dem IMAP-Server und stellt benutzerfreundliche APIs zur Verarbeitung von E-Mail-Nachrichten bereit. Mit diesem Leitfaden können Sie jetzt DSN-Abruffunktionen in Ihre C#-Anwendungen integrieren.