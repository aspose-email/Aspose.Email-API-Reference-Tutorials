---
date: '2026-02-27'
description: Erfahren Sie, wie Sie MSG-Dateien laden und mit Aspose.Email für Java
  in MHTML konvertieren, einschließlich benutzerdefinierter Zeitzoneneinstellungen
  und Tipps zur Stapelverarbeitung von E-Mails.
keywords:
- Aspose.Email for Java
- load emails in MHTML format
- custom timezone settings
title: Wie man MSG lädt und als MHTML speichert mit Aspose.Email für Java
url: /de/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man MSG lädt und als MHTML speichert mit Aspose.Email für Java

## Einführung

Wenn Sie **wie man msg lädt** Dateien, deren Zeitstempel anpasst und dann **msg zu mhtml konvertiert**, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch das Laden einer `.msg`‑E‑Mail, das Anwenden eines benutzerdefinierten Zeitzonen‑Offsets und das Speichern des Ergebnisses als MHTML‑Archiv – alles mit Aspose.Email für Java. Egal, ob Sie eine einzelne Nachricht oder eine **Batch‑E‑Mail‑Verarbeitung**‑Pipeline bearbeiten, diese Schritte geben Ihnen eine solide Grundlage.

**Was Sie lernen werden**
- Wie man ein `MailMessage` aus einer `.msg`‑Datei lädt.
- Wie man eine benutzerdefinierte Zeitzone und das aktuelle Datum festlegt.
- Wie man die Nachricht als MHTML mit präziser Formatierung speichert.
- Tipps zum Skalieren des Ansatzes für Batch‑Szenarien.

Bereit, Ihren E‑Mail‑Workflow zu optimieren? Richten wir zuerst die Umgebung ein.

## Schnelle Antworten
- **Was ist die primäre Bibliothek?** Aspose.Email für Java.
- **Kann ich MSG laden und in einem Schritt nach MHTML exportieren?** Nein, Sie laden, passen an und speichern dann.
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine gültige Aspose.Email‑Lizenz ist erforderlich.
- **Wird die Zeitzonen‑Verarbeitung unterstützt?** Ja, über `setTimeZoneOffset`.
- **Kann das in der Batch‑Verarbeitung verwendet werden?** Absolut – wickeln Sie die Schritte in einer Schleife ein.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken und Abhängigkeiten
- **Aspose.Email für Java** Bibliothek Version 25.4 (jdk16 classifier)
- Grundlegende Java‑Kenntnisse.
- Eine IDE wie IntelliJ IDEA oder Eclipse.

### Anforderungen an die Umgebung
- JDK 16 oder neuer installiert.
- Maven für das Abhängigkeits‑Management.

## Einrichtung von Aspose.Email für Java

Um die Bibliothek zu einem Maven‑Projekt hinzuzufügen, fügen Sie die folgende Abhängigkeit ein:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Schritte zum Erwerb einer Lizenz

Beginnen Sie mit einer **kostenlosen Testversion** oder erhalten Sie eine **temporäre Lizenz**, um die vollen Funktionen der Bibliothek ohne Einschränkungen zu evaluieren. Für den langfristigen Einsatz sollten Sie den Kauf einer Lizenz in Betracht ziehen:

- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Purchase License](https://purchase.aspose.com/buy)

### Grundlegende Initialisierung

Nachdem Sie die Abhängigkeit hinzugefügt haben, initialisieren Sie die Lizenz in Ihrem Java‑Code:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Implementierungs‑Leitfaden

Wir teilen die Implementierung in drei klare Funktionen auf.

### Funktion 1: Laden einer MailMessage aus einer Datei

#### Überblick
Das Laden einer `.msg`‑Datei gibt Ihnen vollen programmatischen Zugriff auf den Inhalt, die Anhänge und die Metadaten der E‑Mail.

#### Schritt‑für‑Schritt

**Importieren Sie die erforderlichen Klassen**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

**Laden Sie die E‑Mail**

```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` ermöglicht es Ihnen, zu steuern, wie die MSG‑Datei interpretiert wird; die Standardeinstellungen funktionieren in den meisten Szenarien.

### Funktion 2: Festlegen des aktuellen Datums und eines benutzerdefinierten Zeitzonen‑Offsets

#### Überblick
Genauige Zeitstempel sind entscheidend, wenn Sie mit Benutzern in verschiedenen Regionen arbeiten.

**Setzen Sie das aktuelle Datum**

```java
import java.util.Date;

msg.setDate(new Date());
```

**Wenden Sie einen benutzerdefinierten Zeitzonen‑Offset an (z. B. UTC+5)**

```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

Der Offset wird in Millisekunden angegeben, sodass Sie auch negative Werte für westlich von UTC liegende Zonen übergeben können.

### Funktion 3: Speichern einer MailMessage als MHTML‑Datei

#### Überblick
MHTML bündelt HTML‑Inhalte und eingebettete Ressourcen in einer einzigen Datei, ideal für Archivierung oder Weitergabe.

**Konfigurieren Sie die Speicheroptionen**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

**Speichern Sie die E‑Mail**

```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Die resultierende `.mhtml`‑Datei behält die ursprüngliche Formatierung, Bilder und Anhänge bei.

## Warum MSG zu MHTML konvertieren?

Die Konvertierung von MSG‑Dateien zu MHTML liefert Ihnen eine web‑freundliche, ein‑Datei‑Darstellung, die in jedem modernen Browser geöffnet werden kann. Das ist besonders nützlich für:

- **Rechtliche Archivierung**, bei der eine getreue visuelle Kopie erforderlich ist.
- **Plattformübergreifendes Teilen** ohne Outlook.
- **Einbetten von E‑Mails** in Webseiten oder Dokumentationen.

## Tipps zur Batch‑E‑Mail‑Verarbeitung

Wenn Sie **Batch‑E‑Mail‑Verarbeitung** benötigen, wickeln Sie das Laden, die Zeitzonen‑Anpassung und das Speichern in einer Schleife ein, die über ein Verzeichnis von `.msg`‑Dateien iteriert. Denken Sie daran:

1. Verwenden Sie eine einzige `License`‑Instanz, um Overhead zu vermeiden.
2. Geben Sie Ressourcen nach jeder Iteration frei (`msg.dispose()` falls zutreffend).
3. Protokollieren Sie Fehlermeldungen in einer separaten Datei für eine spätere Überprüfung.

## Praktische Anwendungsfälle

1. **E‑Mail‑Archivierung:** Bewahren Sie Kommunikationen in einem portablen Format für Compliance‑Zwecke auf.
2. **Globale Terminplanung:** Passen Sie Zeitstempel an eine einheitliche Zeitzone an, bevor Benachrichtigungen gesendet werden.
3. **CRM‑Integration:** Importieren Sie archivierte E‑Mails automatisch als MHTML‑Anhänge in ein CRM‑System.

## Leistungs‑Überlegungen

- **Speicherverwaltung:** Verarbeiten Sie große Batches in Portionen, um den Speicherverbrauch gering zu halten.
- **I/O‑Optimierung:** Nutzen Sie gepufferte Streams, wenn Sie viele Dateien lesen/schreiben.
- **Parallele Ausführung:** Ziehen Sie Java‑s `ForkJoinPool` für parallele Verarbeitung in Betracht, stellen Sie jedoch die Thread‑Sicherheit der Aspose‑Objekte sicher.

## Fazit

Sie wissen jetzt **wie man msg** Dateien lädt, benutzerdefinierte Zeitzonen‑Offsets anwendet und **msg zu mhtml** konvertiert mit Aspose.Email für Java. Diese Techniken lassen sich skalieren, um **Batch‑E‑Mail‑Verarbeitung**‑Aufgaben zu bewältigen, und bieten Ihnen eine robuste Lösung für E‑Mail‑Archivierung, Migration und Automatisierung.

**Nächste Schritte**  
Entdecken Sie weitere Aspose.Email‑Funktionen wie Anhangs‑Verarbeitung, Kalender‑Item‑Extraktion oder SMTP‑Versand, indem Sie die offizielle [Dokumentation](https://reference.aspose.com/email/java/) besuchen.

## Häufig gestellte Fragen

**F: Kann ich E‑Mails aus anderen Formaten als .msg laden?**  
A: Ja, Aspose.Email unterstützt EML, MSG, MHT und mehrere weitere Formate.

**F: Wie kann ich sehr große E‑Mail‑Dateien effizient handhaben?**  
A: Verwenden Sie die Streaming‑APIs von Aspose.Email, um Daten in Teilen zu lesen/zu schreiben und so den Speicherverbrauch zu reduzieren.

**F: Ist es möglich, Anhänge innerhalb einer MailMessage zu ändern?**  
A: Absolut. Sie können Anhänge über die `MailMessage.getAttachments()`‑Sammlung hinzufügen, entfernen oder ersetzen.

**F: Was, wenn mein Zeitzonen‑Offset negativ ist (hinter UTC)?**  
A: Übergeben Sie einen negativen Millisekundenwert an `setTimeZoneOffset`, z. B. `-3 * 60 * 60 * 1000` für UTC‑3.

**F: Kann ich Aspose.Email in kommerziellen Projekten verwenden?**  
A: Ja, vorausgesetzt, Sie besitzen eine gültige kommerzielle Lizenz.

**F: Wie verarbeite ich tausende MSG‑Dateien, ohne dass der Speicher ausgeht?**  
A: Verarbeiten Sie Dateien in Batches, geben Sie jedes `MailMessage` nach dem Speichern frei und nutzen Sie Java‑s `try‑with‑resources`‑Muster für automatische Bereinigung.

## Ressourcen
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Library](https://releases.aspose.com/email/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-02-27  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}