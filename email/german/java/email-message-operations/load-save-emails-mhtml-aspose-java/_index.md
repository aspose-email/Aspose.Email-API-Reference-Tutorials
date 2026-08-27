---
date: '2026-08-27'
description: Erfahren Sie, wie Sie MSG-Dateien mit Aspose.Email für Java laden und
  in MHTML konvertieren, einschließlich benutzerdefinierter Zeitzoneneinstellungen
  und Tipps zur Stapelverarbeitung von E-Mails.
keywords:
- how to load msg
- Aspose.Email Java
- convert MSG to MHTML
- email timezone offset
lastmod: '2026-08-27'
og_description: Erfahren Sie, wie Sie MSG-Dateien mit Aspose.Email für Java laden
  und als MHTML exportieren. Enthält Zeitzonenverwaltung und Tipps zur Stapelverarbeitung.
og_image_alt: Guide to loading MSG files and saving as MHTML with Aspose.Email for
  Java
og_title: Wie man MSG lädt und als MHTML speichert mit Aspose.Email für Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  headline: How to load msg and save as MHTML using Aspose.Email for Java
  type: TechArticle
- description: Learn how to load MSG files and convert them to MHTML with Aspose.Email
    for Java, including custom timezone settings and batch email processing tips.
  name: How to load msg and save as MHTML using Aspose.Email for Java
  steps:
  - name: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
    text: '**Reuse the license** – call `new License().setLicense(...)` once at application
      startup.'
  - name: '**Use try‑with‑resources** for automatic cleanup of streams.'
    text: '**Use try‑with‑resources** for automatic cleanup of streams.'
  - name: '**Log failures** to a separate file so you can retry problematic messages
      later.'
    text: '**Log failures** to a separate file so you can retry problematic messages
      later.'
  - name: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
    text: '**Consider parallelism** with `ForkJoinPool` for large batches, but ensure
      each thread uses its own `MailMessage` instance.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Email supports EML, MHT, EMLX, and several other formats,
      totaling over 30 input types.
    question: Can I load emails from formats other than .msg?
  - answer: Use the streaming APIs (`MailMessage.load(InputStream, ...)`) to read
      and write data in chunks, which keeps memory consumption under 50 MB even for
      500‑page messages.
    question: How can I handle very large email files efficiently?
  - answer: Absolutely. You can add, remove, or replace attachments via the `msg.getAttachments()`
      collection, then call `save` to persist changes.
    question: Is it possible to modify attachments within a MailMessage?
  - answer: Pass a negative millisecond value to `setTimeZoneOffset`, e.g., `-3 *
      60 * 60 * 1000` for UTC‑3.
    question: What if my timezone offset is negative (behind UTC)?
  - answer: Yes, provided you have a valid commercial license. The free trial is limited
      to 20 MB per document.
    question: Can I use Aspose.Email in commercial projects?
  type: FAQPage
tags:
- email processing
- Aspose.Email
- Java email conversion
title: Wie man MSG-Dateien lädt und als MHTML speichert mit Aspose.Email für Java
url: /de/java/email-message-operations/load-save-emails-mhtml-aspose-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man MSG lädt und als MHTML speichert mit Aspose.Email für Java

## Einleitung

Wenn Sie **how to load msg** Dateien benötigen, deren Zeitstempel anpassen und dann **convert msg to mhtml** durchführen möchten, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch das Laden einer `.msg`‑E‑Mail, das Anwenden eines benutzerdefinierten Zeitzonen‑Offsets und das Speichern des Ergebnisses als MHTML‑Archiv – alles mit Aspose.Email für Java. Egal, ob Sie eine einzelne Nachricht oder eine **batch email processing**‑Pipeline verarbeiten, diese Schritte geben Ihnen eine solide Grundlage für zuverlässige Archivierung und Migration.

**Was Sie lernen werden**
- Wie man ein `MailMessage` aus einer `.msg`‑Datei lädt.
- Wie man eine benutzerdefinierte Zeitzone und das aktuelle Datum festlegt.
- Wie man die Nachricht als MHTML mit präziser Formatierung speichert.
- Tipps zum Skalieren des Ansatzes für Batch‑Szenarien.

Bereit, Ihren E‑Mail‑Workflow zu optimieren? Lassen Sie uns zuerst die Umgebung einrichten.

## Schnelle Antworten
- **Was ist die primäre Bibliothek?** Aspose.Email for Java.
- **Kann ich MSG laden und in einem Schritt nach MHTML exportieren?** No, you load, adjust, then save.
- **Benötige ich eine Lizenz für die Produktion?** Yes, a valid Aspose.Email license is required.
- **Wird die Zeitzonen‑Verarbeitung unterstützt?** Yes, via `setTimeZoneOffset`.
- **Kann dies in der Batch‑Verarbeitung verwendet werden?** Absolutely – wrap the steps in a loop.

## Was ist Aspose.Email für Java?

Aspose.Email for Java ist eine umfassende API, die es Ihnen ermöglicht, E‑Mail‑Nachrichten zu erstellen, zu lesen, zu konvertieren und zu manipulieren, ohne Microsoft Outlook zu benötigen. Sie unterstützt mehr als 30 E‑Mail‑Formate und kann mehrseitige Nachrichten verarbeiten, während der Speicherverbrauch gering bleibt.

## Warum MSG nach MHTML konvertieren?

Die Konvertierung von MSG‑Dateien zu MHTML liefert Ihnen eine web‑freundliche, ein‑Datei‑Darstellung, die in jedem modernen Browser geöffnet werden kann. Dieses Format bewahrt das ursprüngliche Styling, eingebettete Bilder und Anhänge, wodurch es ideal für **legal archiving**, **cross‑platform sharing** und **embedding emails into web pages or documentation** ist.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken und Abhängigkeiten
- **Aspose.Email for Java** Bibliothek Version 25.4 (jdk16 classifier) – die Bibliothek unterstützt **50+** Eingabe‑ und Ausgabe‑E‑Mail‑Formate.
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
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Schritte zum Erwerb einer Lizenz

Beginnen Sie mit einer **free trial** oder erhalten Sie eine **temporary license**, um die vollen Fähigkeiten der Bibliothek ohne Einschränkungen zu evaluieren. Für den langfristigen Einsatz sollten Sie den Kauf einer Lizenz in Betracht ziehen:

- [Kostenlose Testversion](https://releases.aspose.com/email/java/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Lizenz kaufen](https://purchase.aspose.com/buy)

### Grundlegende Initialisierung

Die Klasse `License` registriert Ihre Aspose.Email‑Lizenz, um alle Funktionen freizuschalten.  
Nachdem Sie die Abhängigkeit hinzugefügt haben, initialisieren Sie die Lizenz in Ihrem Java‑Code:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("Aspose.Email.lic");
```
```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path_to_your_license_file.lic");
```

## Wie man MSG lädt und als MHTML speichert?

Laden Sie die MSG‑Datei, passen Sie den Zeitstempel an und speichern Sie sie in drei einfachen Schritten als MHTML. Zuerst instanziieren Sie ein `MailMessage` aus der MSG‑Datei mit `MsgLoadOptions`. Als Nächstes setzen Sie den gewünschten Zeitzonen‑Offset mit `setTimeZoneOffset`. Schließlich konfigurieren Sie `MhtSaveOptions` und rufen `save` auf, um das MHTML‑Archiv zu erzeugen.

### Feature 1: Laden eines MailMessage aus einer Datei

Die Klasse `MailMessage` repräsentiert eine E‑Mail‑Nachricht mit Headern, Body und Anhängen.

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```
```java
import com.aspose.email.MailMessage;
import com.aspose.email.MsgLoadOptions;
```

```java
MsgLoadOptions loadOptions = new MsgLoadOptions();
MailMessage msg = MailMessage.load("sample.msg", loadOptions);
```
```java
String filename = "YOUR_DOCUMENT_DIRECTORY/MSG file with RTF Formatting.msg";
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
```

`MsgLoadOptions` ermöglicht es Ihnen zu steuern, wie die MSG‑Datei geparst wird; die Standardeinstellungen funktionieren für die meisten Szenarien.

### Feature 2: Festlegen des aktuellen Datums und eines benutzerdefinierten Zeitzonen‑Offsets

Das Objekt `Date` enthält den Zeitstempel, der in den **Date**‑Header der E‑Mail geschrieben wird.

```java
java.util.Date now = new java.util.Date();
msg.setDate(now);
```
```java
import java.util.Date;

msg.setDate(new Date());
```

Der Offset wird in Millisekunden angegeben; für UTC+5 übergeben Sie `5 * 60 * 60 * 1000`.

```java
int utcPlusFive = 5 * 60 * 60 * 1000;
msg.setTimeZoneOffset(utcPlusFive);
```
```java
msg.setTimeZoneOffset(5 * 60 * 60 * 1000); // 5 hours ahead of UTC in milliseconds.
```

### Feature 3: Speichern eines MailMessage als MHTML‑Datei

`MhtSaveOptions` definiert, wie die E‑Mail in ein MHTML‑Archiv verpackt wird, wobei Inline‑Bilder und Anhänge erhalten bleiben.

```java
import com.aspose.email.MhtSaveOptions;
MhtSaveOptions saveOptions = new MhtSaveOptions();
saveOptions.setWriteHeader(true);
```
```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
```

```java
msg.save("output.mhtml", saveOptions);
```
```java
msg.save("YOUR_OUTPUT_DIRECTORY/ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
```

Die resultierende `.mhtml`‑Datei behält das ursprüngliche Layout, Bilder und Anhänge bei und stellt somit eine getreue visuelle Kopie des ursprünglichen MSG dar.

## Wie man einen benutzerdefinierten Zeitzonen‑Offset setzt?

Sie können die Zeitzone ändern, indem Sie `setTimeZoneOffset` auf der `MailMessage`‑Instanz aufrufen. Die Methode erwartet einen Offset in Millisekunden und erlaubt sowohl positive (östlich von UTC) als auch negative (westlich von UTC) Werte. Zum Beispiel ist UTC‑3 `-3 * 60 * 60 * 1000`.

## Wie man MSG‑Dateien stapelweise verarbeitet?

Verpacken Sie den dreischrittigen Workflow in eine Schleife, die über ein Verzeichnis von `.msg`‑Dateien iteriert. Verwenden Sie eine einzelne `License`‑Instanz erneut, um wiederholte I/O zu vermeiden, und geben Sie jedes `MailMessage` nach dem Speichern frei, um den Speicherverbrauch gering zu halten.

```java
File folder = new File("msg_folder");
for (File file : folder.listFiles((dir, name) -> name.toLowerCase().endsWith(".msg"))) {
    MailMessage msg = MailMessage.load(file.getAbsolutePath(), new MsgLoadOptions());
    // set date & timezone as shown earlier
    msg.save(file.getName().replace(".msg", ".mhtml"), new MhtSaveOptions());
    msg.dispose(); // releases native resources
}
```

### Tipps zur Batch‑Verarbeitung
1. **Lizenz wiederverwenden** – rufen Sie `new License().setLicense(...)` einmal beim Anwendungsstart auf.
2. **try‑with‑resources verwenden** für die automatische Bereinigung von Streams.
3. **Fehler protokollieren** in einer separaten Datei, damit Sie problematische Nachrichten später erneut versuchen können.
4. **Parallelität in Betracht ziehen** mit `ForkJoinPool` für große Stapel, aber stellen Sie sicher, dass jeder Thread seine eigene `MailMessage`‑Instanz verwendet.

## Häufige Probleme und Lösungen

- **Speicherspitzen bei riesigen MSG‑Dateien** – aktivieren Sie Streaming, indem Sie `MailMessage.load(InputStream, MsgLoadOptions)` verwenden und den Stream in Teilen verarbeiten.
- **Falsche Zeitstempel** – prüfen Sie, ob die Systemuhr auf UTC eingestellt ist, bevor Sie Offsets anwenden, oder übergeben Sie explizit eine `java.util.Calendar`‑Instanz.
- **Fehlende Anhänge in MHTML** – stellen Sie sicher, dass `MhtSaveOptions.setWriteHeader(true)` gesetzt ist; dies bettet Anhänge als `cid:`‑Ressourcen ein.

## Häufig gestellte Fragen

**Q: Kann ich E‑Mails aus anderen Formaten als .msg laden?**  
A: Ja, Aspose.Email unterstützt EML, MHT, EMLX und mehrere andere Formate, insgesamt über 30 Eingabetypen.

**Q: Wie kann ich sehr große E‑Mail‑Dateien effizient verarbeiten?**  
A: Verwenden Sie die Streaming‑APIs (`MailMessage.load(InputStream, ...)`), um Daten in Teilen zu lesen und zu schreiben, wodurch der Speicherverbrauch selbst bei 500‑Seiten‑Nachrichten unter 50 MB bleibt.

**Q: Ist es möglich, Anhänge innerhalb eines MailMessage zu ändern?**  
A: Absolut. Sie können Anhänge über die Sammlung `msg.getAttachments()` hinzufügen, entfernen oder ersetzen und anschließend `save` aufrufen, um die Änderungen zu speichern.

**Q: Was ist, wenn mein Zeitzonen‑Offset negativ ist (hinter UTC)?**  
A: Übergeben Sie einen negativen Millisekundenwert an `setTimeZoneOffset`, z. B. `-3 * 60 * 60 * 1000` für UTC‑3.

**Q: Kann ich Aspose.Email in kommerziellen Projekten verwenden?**  
A: Ja, vorausgesetzt, Sie besitzen eine gültige kommerzielle Lizenz. Die kostenlose Testversion ist auf 20 MB pro Dokument begrenzt.

**Q: Wie verarbeite ich Tausende von MSG‑Dateien, ohne den Speicher zu erschöpfen?**  
A: Verarbeiten Sie Dateien in Batches, geben Sie jedes `MailMessage` nach dem Speichern frei und nutzen Sie das Java‑Muster `try‑with‑resources` für die automatische Bereinigung.

## Ressourcen
- [Dokumentation](https://reference.aspose.com/email/java/)
- [Dokumentation](https://reference.aspose.com/email/java/)
- [Bibliothek herunterladen](https://releases.aspose.com/email/java/)
- [Lizenz kaufen](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/email/java/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Support‑Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-08-27  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Outlook‑MSG‑Dateien mit Aspose.Email für Java lädt und analysiert: Ein umfassender Leitfaden](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [Maven Aspose.Email für Java: E‑Mails als MHT‑Dateien speichern](/email/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/)
- [Wie man Anhänge aus MSG‑Dateien mit Aspose.Email für Java extrahiert](/email/java/advanced-email-attachments/extracting-attachments-from-email-messages/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}