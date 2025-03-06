---
title: Konvertieren von E-Mails in MHT mit Zeitzone in C#
linktitle: Konvertieren von E-Mails in MHT mit Zeitzone in C#
second_title: Aspose.Email .NET E-Mail-Verarbeitungs-API
description: Konvertieren Sie E-Mails mit Aspose.Email für .NET in das MHT-Format mit genauen Zeitzonen. Schritt-für-Schritt-Anleitung und Codebeispiel bereitgestellt.
weight: 12
url: /de/net/email-conversion-and-export/converting-email-to-mht-with-timezone-in-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren von E-Mails in MHT mit Zeitzone in C#


## Einführung in die E-Mail-Konvertierung von E-Mail zu MHT mit Zeitzone

Das Konvertieren von E-Mail-Nachrichten in verschiedene Formate ist in vielen Anwendungen eine häufige Anforderung. In Szenarien, in denen Zeit- und Zeitzoneninformationen eine entscheidende Rolle spielen, ist es wichtig sicherzustellen, dass diese Informationen während des Konvertierungsprozesses genau beibehalten werden. In diesem Leitfaden konzentrieren wir uns auf die Konvertierung von E-Mails in das MHT-Format und den korrekten Umgang mit Zeitzonendaten.

## Einrichten Ihrer Entwicklungsumgebung

Bevor wir uns mit dem Codierungsprozess befassen, stellen wir sicher, dass Ihre Entwicklungsumgebung einsatzbereit ist. Stellen Sie sicher, dass Sie eine kompatible Version von Visual Studio installiert haben, und erstellen Sie zunächst ein neues C#-Projekt.

## Aspose.Email für .NET installieren

Aspose.Email für .NET ist eine funktionsreiche Bibliothek, die E-Mail-bezogene Aufgaben vereinfacht. Um es zu installieren, gehen Sie folgendermaßen vor:

1. Öffnen Sie Ihr Projekt in Visual Studio.
2. Gehen Sie zu „Extras“ > „NuGet-Paket-Manager“ > „NuGet-Pakete für Lösung verwalten“.
3. Suchen Sie nach „Aspose.Email“ und installieren Sie das Paket.

## E-Mail-Nachrichten laden und analysieren

In diesem Schritt laden und analysieren wir die E-Mail-Nachricht, die wir konvertieren möchten. Verwenden Sie den folgenden Codeausschnitt als Ausgangspunkt:

```csharp
// Fügen Sie die erforderlichen Using-Anweisungen hinzu
using Aspose.Email;

// Laden Sie die E-Mail-Nachricht
var message = MailMessage.Load("path/to/your/email.eml");

// Jetzt haben Sie Zugriff auf die Nachrichteneigenschaften
var subject = message.Subject;
var sender = message.From.Address;
// ... andere Immobilien
```

## Umgang mit Zeitzoneninformationen

Der korrekte Umgang mit Zeitzoneninformationen ist von entscheidender Bedeutung. Der folgende Codeausschnitt zeigt, wie Zeitzonendaten aus einer E-Mail-Nachricht extrahiert und verwaltet werden:

```csharp
var timezone = message.TimezoneOffset;
var timezoneId = Timezone.GetIdFromOffset(timezone);
var timezoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timezoneId);
// Sie können jetzt timezoneInfo verwenden, um Zeitzonenkonvertierungen durchzuführen
```

## Konvertieren von E-Mails in das MHT-Format

Jetzt kommt der Kernkonvertierungsschritt. Wir verwenden Aspose.Email, um die Konvertierung in das MHT-Format durchzuführen:

```csharp
var mhtOptions = MhtSaveOptions.DefaultMhtml;
var mhtStream = new MemoryStream();
message.Save(mhtStream, mhtOptions);
```

## Speichern der MHT-Datei

Nachdem die E-Mail-Nachricht in das MHT-Format konvertiert wurde, ist es an der Zeit, sie als Datei zu speichern:

```csharp
using var fileStream = new FileStream("output.mht", FileMode.Create);
mhtStream.Seek(0, SeekOrigin.Begin);
mhtStream.CopyTo(fileStream);
```

## Weitere Anpassungen erkunden

Aspose.Email für .NET bietet verschiedene Anpassungsmöglichkeiten. Sie können Anhänge hinzufügen, Nachrichteneigenschaften ändern und vieles mehr, um sie an die Anforderungen Ihrer Anwendung anzupassen.

## Vorteile der Verwendung von Aspose.Email für .NET

Aspose.Email für .NET vereinfacht komplexe E-Mail-bezogene Aufgaben und ermöglicht es Entwicklern, sich auf die Kernfunktionen zu konzentrieren. Es bietet zuverlässige Unterstützung für verschiedene E-Mail-Formate und sorgt so für genaue und effiziente Konvertierungen.

## Abschluss

In diesem Leitfaden haben wir erfahren, wie Sie E-Mail-Nachrichten in das MHT-Format konvertieren und dabei Zeitzoneninformationen mit Aspose.Email für .NET verarbeiten. Indem Sie diese Schritte befolgen und weitere Anpassungsoptionen erkunden, können Sie E-Mail-Konvertierungsfunktionen nahtlos in Ihre Anwendungen integrieren.

## FAQs

### Wie gehe ich mit Anhängen bei der E-Mail-Konvertierung um?

 Um Anhänge zu bearbeiten, können Sie die verwenden`Attachments` Eigentum der`MailMessage` Klasse. Gehen Sie die Anhänge durch und speichern Sie sie nach Bedarf während des Konvertierungsprozesses.

### Kann ich E-Mails mit Aspose.Email für .NET in andere Formate konvertieren?

Ja, Aspose.Email für .NET unterstützt verschiedene Formate, darunter MSG, EML, PST und mehr. Sie können die bereitgestellten Codebeispiele an Ihr gewünschtes Ausgabeformat anpassen.

### Werden Zeitzoneninformationen im MHT-Format beibehalten?

 Ja, die Zeitzoneninformationen bleiben während des Konvertierungsvorgangs erhalten. Durch den Umgang mit Zeitzonen-Offsets und die Verwendung der entsprechenden`TimeZoneInfo` Mit diesen Methoden können Sie eine genaue Zeitzonendarstellung in der MHT-Datei sicherstellen.

### Wo finde ich weitere Dokumentation und Updates zu Aspose.Email für .NET?

 Umfassende Informationen und Aktualisierungen finden Sie in der Dokumentation:[Aspose.Email für .NET API-Referenz](https://reference.aspose.com/email/net/)

### Wie kann ich die neueste Version von Aspose.Email für .NET herunterladen?

 Sie können die neueste Version von der Release-Seite herunterladen:[Laden Sie Aspose.Email für .NET herunter](https://releases.aspose.com/email/net/)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
