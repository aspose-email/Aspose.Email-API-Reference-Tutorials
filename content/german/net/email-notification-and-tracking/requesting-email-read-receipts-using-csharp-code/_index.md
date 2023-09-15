---
title: Anfordern von E-Mail-Lesebestätigungen mithilfe von C#-Code
linktitle: Anfordern von E-Mail-Lesebestätigungen mithilfe von C#-Code
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Erfahren Sie, wie Sie C#-Code verwenden, um E-Mail-Lesebestätigungen mit Aspose.Email für .NET anzufordern und so die Kommunikationsverfolgung zu verbessern.
type: docs
weight: 11
url: /de/net/email-notification-and-tracking/requesting-email-read-receipts-using-csharp-code/
---

Im heutigen digitalen Zeitalter ist die Kommunikation per E-Mail zu einem festen Bestandteil unseres persönlichen und beruflichen Lebens geworden. Beim Versenden wichtiger E-Mails möchten wir häufig sicherstellen, dass der Empfänger unsere Nachricht gelesen und bestätigt hat. Hier kommen E-Mail-Lesebestätigungen ins Spiel. In diesem Schritt-für-Schritt-Tutorial führen wir Sie durch den Prozess der Anforderung von E-Mail-Lesebestätigungen mithilfe von C# mit Aspose.Email für .NET.

## Einführung in E-Mail-Lesebestätigungen

Mit E-Mail-Lesebestätigungen, auch E-Mail-Tracking oder Rücksendebestätigungen genannt, können Sie Benachrichtigungen erhalten, wenn der Empfänger Ihre E-Mail öffnet und liest. Dies ist insbesondere in der Geschäftskommunikation eine wertvolle Funktion, da sie die Zustellung und Interaktion von Nachrichten bestätigt.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio ist auf Ihrem System installiert.
- Aspose.Email für .NET-Bibliothek heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 1: Erstellen einer MailMessage-Instanz

 Der erste Schritt bei der Implementierung von E-Mail-Lesebestätigungen besteht darin, eine Instanz davon zu erstellen`MailMessage` Klasse. Diese Klasse stellt eine E-Mail-Nachricht dar und ermöglicht Ihnen das Festlegen verschiedener Eigenschaften der E-Mail.

```csharp
MailMessage message = new MailMessage();
```

## Schritt 2: Nachrichtendetails angeben

Geben wir nun die Details der E-Mail-Nachricht an, einschließlich Absender, Empfänger, HTML-Text und Zustellungsbenachrichtigungsoptionen.

```csharp
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");
```

## Schritt 3: Erstellen einer SmtpClient-Instanz

 Um die E-Mail zu senden, müssen wir eine Instanz davon erstellen`SmtpClient` Klasse, die für das Senden der Nachricht verantwortlich ist.

```csharp
SmtpClient client = new SmtpClient();
```

## Schritt 4: Konfigurieren der SMTP-Einstellungen

Konfigurieren Sie Ihre SMTP-Servereinstellungen, indem Sie den Hostserver, den Benutzernamen, das Passwort und die Portnummer angeben.

```csharp
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;
```

## Schritt 5: Senden der E-Mail

 Zum Schluss verwenden Sie die`client.Send` Methode zum Senden der E-Mail-Nachricht. Wenn die Nachricht erfolgreich gesendet wurde, wird eine Benachrichtigung „Nachricht gesendet“ angezeigt.

```csharp
try
{
    client.Send(message);
    Console.WriteLine("Message sent");
}
catch (Exception ex)
{
    System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```

Mit diesen fünf einfachen Schritten können Sie E-Mail-Lesebestätigungen anfordern, wenn Sie E-Mails mit C# und Aspose.Email für .NET senden. Diese Funktion verleiht Ihrer E-Mail-Kommunikation eine zusätzliche Sicherheitsebene und stellt sicher, dass Sie wissen, wann Ihre wichtigen Nachrichten gelesen werden.

## Vollständiger Quellcode
```csharp
// Erstellen Sie eine Instanz der MailMessage-Klasse
MailMessage message = new MailMessage();

// Geben Sie die Felder „From“, „To“, „HtmlBody“ und „DeliveryNotificationOptions“ an
message.From = "sender@sender.com";
message.To.Add("receiver@receiver.com");
message.HtmlBody = "<html><body>This is the Html body</body></html>";
message.DeliveryNotificationOptions = DeliveryNotificationOptions.OnSuccess;
message.Headers.Add("Return-Receipt-To", "sender@sender.com");
message.Headers.Add("Disposition-Notification-To", "sender@sender.com");

// Erstellen Sie eine Instanz der SmtpClient-Klasse
SmtpClient client = new SmtpClient();

// Geben Sie Ihren Mailing-Hostserver, Benutzernamen, Passwort und Portnummer an
client.Host = "smtp.server.com";
client.Username = "Username";
client.Password = "Password";
client.Port = 25;

try
{
	// Client.Send sendet diese Nachricht
	client.Send(message);
	// Zeigt „Nachricht gesendet“ nur an, wenn die Nachricht erfolgreich gesendet wurde
	Console.WriteLine("Message sent");
}
catch (Exception ex)
{
	System.Diagnostics.Trace.WriteLine(ex.ToString());
}
```
## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie E-Mail-Lesebestätigungen mithilfe von C# mit Aspose.Email für .NET anfordern. E-Mail-Tracking ist ein leistungsstarkes Tool, um sicherzustellen, dass Ihre Nachrichten zugestellt und von den beabsichtigten Empfängern gelesen werden, insbesondere im beruflichen Umfeld. Wenn Sie die hier beschriebenen Schritte befolgen, können Sie diese Funktionalität problemlos in Ihre E-Mail-Anwendung implementieren.

## Häufig gestellte Fragen (FAQs)

1. ### Welchen Zweck haben E-Mail-Lesebestätigungen?
   E-Mail-Lesebestätigungen bestätigen, dass eine E-Mail vom Empfänger geöffnet und gelesen wurde. Sie werden häufig zum Verfolgen wichtiger oder zeitkritischer Nachrichten verwendet.

2. ### Können E-Mail-Lesebestätigungen vom Empfänger deaktiviert werden?
   Ja, E-Mail-Clients ermöglichen es Benutzern häufig, das Senden von Lesebestätigungen zu deaktivieren. Daher kann nicht garantiert werden, dass Sie sie immer erhalten.

3. ### Sind E-Mail-Lesebestätigungen eine Standardfunktion in allen E-Mail-Clients?
   Nein, E-Mail-Lesebestätigungen werden nicht allgemein unterstützt. Ob sie funktionieren oder nicht, hängt vom E-Mail-Client und den Einstellungen des Empfängers ab.

4. ### Ist es möglich zu verfolgen, wann eine E-Mail auf einem mobilen Gerät geöffnet wird?
   Die E-Mail-Verfolgung basiert in der Regel auf dem E-Mail-Client und den Einstellungen des Empfängers und kann daher je nach verschiedenen Faktoren auf Mobilgeräten funktionieren oder auch nicht.

5. ### Gibt es Datenschutzaspekte bei der Verwendung von E-Mail-Lesebestätigungen?
   Ja, es gibt Datenschutzbedenken im Zusammenhang mit der E-Mail-Verfolgung. Einige Empfänger empfinden dies möglicherweise als invasiv. Daher ist es wichtig, diese Funktion verantwortungsbewusst zu nutzen und die Datenschutzeinstellungen zu respektieren.