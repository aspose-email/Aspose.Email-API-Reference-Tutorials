---
date: '2025-12-13'
description: Erfahren Sie, wie Sie MSG/EML mit Aspose.Email für Java konvertieren,
  neue Anhänge hinzufügen, E‑Mail‑Anhänge speichern und TNEF‑Daten verarbeiten.
keywords:
- Aspose.Email Java
- TNEF Handling
- Email Attachments
title: msg und eml mit Aspose.Email Java konvertieren – Leitfaden für TNEF‑Anhänge
url: /de/java/attachments-handling/aspose-email-java-tnef-attachments-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meistern von Aspose.Email Java: Umgang mit TNEF & E-Mail-Anhängen  

In modernen, e‑mail‑zentrierten Anwendungen müssen Sie häufig **convert msg eml** Dateien konvertieren, einem bestehenden Nachricht neue Anhänge hinzufügen und spezielle Formate wie TNEF beibehalten. Egal, ob Sie einen Archivierungsdienst, ein Migrationswerkzeug oder einen clientseitigen Mail‑Viewer erstellen, Aspose.Email für Java bietet Ihnen eine saubere, programmatische Möglichkeit, dies zu tun. In diesem Tutorial sehen Sie genau, wie Sie **convert msg to eml**, einen neuen Anhang hinzufügen, E‑Mail‑Anhänge speichern und mit TNEF‑Daten mithilfe der Aspose.Email‑Java‑Bibliothek arbeiten.

## Quick Answers
- **Wie konvertiere ich MSG zu EML?** Verwenden Sie `MapiMessage` mit `MailConversionOptions` und setzen Sie `convertAsTnef` auf `true`.  
- **Kann ich einem TNEF‑aktivierten EML einen Anhang hinzufügen?** Ja – laden Sie das EML, rufen Sie `getAttachments().addItem(...)` auf und speichern Sie anschließend.  
- **Welche Version von Aspose.Email wird benötigt?** Das Beispiel verwendet Version 25.4 (JDK 16).  
- **Benötige ich eine Lizenz für die Produktion?** Ja – eine Testversion funktioniert für die Evaluierung, aber eine Vollversion entfernt Einschränkungen.  
- **Gibt es eine Möglichkeit, TNEF in einer bestehenden Nachricht zu erkennen?** Rufen Sie nach dem Laden des EML `mail.getOriginalIsTnef()` auf.

## Was ist “convert msg eml”?
Das Konvertieren einer Microsoft Outlook MSG‑Datei in das standardmäßige EML‑Format ermöglicht das Lesen der Nachricht mit jedem RFC‑822‑konformen Mail‑Client. Die Konvertierung bietet Ihnen zudem die Möglichkeit, TNEF‑kodierte Daten während des Vorgangs zu erhalten oder zu manipulieren.

## Warum Aspose.Email Java für diese Aufgabe verwenden?
- **Vollständige Formatunterstützung** – MSG, EML, MHTML und mehr.  
- **Integrierte TNEF‑Verarbeitung** – keine Drittanbieter‑Parser erforderlich.  
- **Einfache API** – Einzeilige Aufrufe zum Laden, Konvertieren und Speichern.  
- **Robuste Lizenzierung** – Testversion zum Testen, Vollversion für die Produktion.

## Voraussetzungen
- **Aspose.Email für Java** (v25.4, JDK 16) – siehe Maven‑Abhängigkeit unten.  
- **Maven** oder ein anderes Build‑Tool, das das Aspose‑Paket auflösen kann.  
- Grundkenntnisse in Java‑I/O und Ausnahmebehandlung.

## Einrichtung von Aspose.Email für Java
Fügen Sie die Bibliothek zu Ihrer Maven `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
Aspose.Email bietet eine kostenlose Testversion an, aber für uneingeschränkte Nutzung ist eine lizenzierte Version erforderlich.

- **Kostenlose Testversion:** Laden Sie eine temporäre Lizenz [hier](https://releases.aspose.com/email/java/) herunter.  
- **Kauf:** Um eine Lizenz zu erwerben, besuchen Sie die [Kaufseite](https://purchase.aspose.com/buy).

Initialisieren Sie die Lizenz in Ihrem Java‑Code:

```java
License license = new License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementierungs‑Leitfaden

### Hinzufügen eines neuen Anhangs zu einer Hauptnachricht mit TNEF
**Wie man einen Anhang hinzufügt:** Laden Sie das EML, fügen Sie die Datei hinzu und speichern Sie anschließend.

#### Schritt 1: Laden der bestehenden E‑Mail‑Nachricht
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage eml = MailMessage.load(dataDir + "MainMessage.eml");
```

#### Schritt 2: Hinzufügen des neuen Anhangs
```java
try (FileInputStream fi = new FileInputStream(dataDir + "barcode.png")) {
    eml.getAttachments().addItem(new Attachment(fi, "barcode.png", "image/png"));
}
```

#### Schritt 3: Speichern der modifizierten E‑Mail‑Nachricht
```java
eml.save(dataDir + "test_out.eml");
```
*Pro‑Tipp:* Verwenden Sie try‑with‑resources, um sicherzustellen, dass Streams geschlossen werden und `FileNotFoundException` vermieden wird.

### Erstellen eines TNEF‑aktivierten EML aus MSG
**Wie man msg zu eml konvertiert:** Setzen Sie `convertAsTnef` auf `true`.

#### Schritt 1: Laden der MSG‑Datei
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MapiMessage msg = MapiMessage.fromFile(dataDir + "Message.msg");
```

#### Schritt 2: Konvertierungsoptionen festlegen
```java
MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);
```

#### Schritt 3: Konvertieren und Speichern
```java
MailMessage mail = msg.toMailMessage(options);
mail.save(dataDir + "converted_message.eml");
```

### TNEF‑Anhänge beim Laden von EML‑Dateien erhalten
**Wie man E‑Mail‑Anhänge speichert und dabei TNEF beibehält:** Verwenden Sie `MsgLoadOptions`.

#### Schritt 1: Ladeoptionen festlegen
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MsgLoadOptions msgLoadOptions = new MsgLoadOptions();
msgLoadOptions.setPreserveTnefAttachments(true);
```

#### Schritt 2: Laden der EML‑Datei mit Optionen
```java
MailMessage eml = MailMessage.load(dataDir + "test.eml", msgLoadOptions);
```

### Erkennen, ob eine Nachricht TNEF ist
**Wie man das Vorhandensein von TNEF prüft:** Rufen Sie `getOriginalIsTnef()` auf.

#### Schritt 1: Laden der EML‑Datei
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage mail = MailMessage.load(dataDir + "test.eml");
```

#### Schritt 2: Erkennen des TNEF‑Vorhandenseins
```java
boolean isTnef = mail.getOriginalIsTnef();
system.out.println("Is TNEF: " + isTnef);
```

## Praktische Anwendungen
1. **E‑Mail‑Archivierung:** Bewahren Sie jeden Anhang – einschließlich TNEF‑kodierter – für Compliance‑Audits auf.  
2. **Unternehmensmigration:** Konvertieren Sie veraltete MSG‑Dateien zu EML, damit sie in moderne Mail‑Server importiert werden können.  
3. **Kundensupport:** Erkennen Sie automatisch TNEF‑Daten, wenn Benutzer Nachrichten zwischen Outlook und Web‑Mail‑Clients weiterleiten.

## Leistungsüberlegungen
- **Ressourcenverwaltung:** Verpacken Sie Dateistreams in try‑with‑resources, um Handles umgehend freizugeben.  
- **Große Anhänge:** Verarbeiten Sie große Dateien in Teilen oder streamen Sie sie direkt, um hohen Speicherverbrauch zu vermeiden.  
- **Überwachung:** Verwenden Sie Java‑Profiling‑Tools, um den Heap‑Verbrauch beim Umgang mit vielen Anhängen zu beobachten.

## Fazit
Wenn Sie die obigen Schritte befolgen, können Sie **convert msg eml**, einen neuen Anhang hinzufügen, E‑Mail‑Anhänge speichern und zuverlässig mit TNEF‑Daten mithilfe von Aspose.Email für Java arbeiten. Die Bibliothek abstrahiert die Low‑Level‑MIME‑Verarbeitung, sodass Sie sich auf die Geschäftslogik konzentrieren können. Für weiterführende Untersuchungen sehen Sie sich die offizielle [Aspose‑Dokumentation](https://reference.aspose.com/email/java/) an oder experimentieren Sie mit anderen Konvertierungsoptionen.

## FAQ‑Abschnitt
**Q1: Was ist eine TNEF‑Datei?**  
A1: TNEF steht für Transport Neutral Encapsulation Format und wird von Microsoft Outlook verwendet, um Rich‑Text‑Formatierung zu erhalten, wenn E‑Mails als Anhänge gesendet werden.

**Q2: Kann ich Aspose.Email ohne Kauf einer Lizenz verwenden?**  
A2: Ja, Sie können mit einer kostenlosen Testversion beginnen. Die Testversion hat jedoch bestimmte Einschränkungen, die die umfassende Nutzung beeinträchtigen können.

**Q3: Ist es möglich, zwischen allen E‑Mail‑Formaten mit Aspose.Email zu konvertieren?**  
A3: Aspose.Email unterstützt die Konvertierung zwischen den meisten gängigen Formaten – einschließlich EML, MSG und MHTML – prüfen Sie jedoch die spezifische Formatunterstützung in der [Dokumentation](https://reference.aspose.com/email/java/).

**Q4: Wie behebe ich Datei‑nicht‑gefunden‑Fehler mit Aspose.Email?**  
A4: Überprüfen Sie, ob die Dateipfade, die Sie an die API übergeben, korrekt sind, ob die Dateien existieren und ob der ausführende Prozess Lese‑/Schreibrechte für diese Verzeichnisse hat.

**Q5: Was ist der beste Weg, große Anhänge mit Aspose.Email zu handhaben?**  
A5: Verarbeiten Sie Anhänge in kleineren Streams oder Teilen und schließen Sie Streams stets umgehend. Das reduziert den Speicherbedarf und verhindert `OutOfMemoryError`.

## Häufig gestellte Fragen (Zusätzlich)

**F: Entfernt Aspose.Email automatisch TNEF beim Konvertieren zu EML?**  
A: Nein. Standardmäßig werden TNEF‑Daten beibehalten. Sie können dieses Verhalten mit `MailConversionOptions.setConvertAsTnef` steuern.

**F: Kann ich programmgesteuert alle Anhänge einer geladenen Nachricht auflisten?**  
A: Ja – verwenden Sie `mail.getAttachments()`, das eine Sammlung zurückgibt, über die Sie iterieren können.

**F: Gibt es eine Möglichkeit, einen Stapel von MSG‑Dateien in einem Durchlauf zu EML zu konvertieren?**  
A: Absolut. Durchlaufen Sie die Dateien, wenden Sie die oben gezeigten Konvertierungsschritte an und speichern Sie jedes Ergebnis.

**Verwandte Ressourcen:** [Aspose Email Java Documentation](https://reference.aspose.com/email/java/) | [Aspose Email Java Releases](https://releases.aspose.com/email/java/) | [Buy Aspose.Email for Java](https://purchase.aspose.com/buy) | Laden Sie eine temporäre Lizenz [hier](https://releases.aspose.com/email/java/).

---

**Letztes Update:** 2025-12-13  
**Getestet mit:** Aspose.Email für Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}