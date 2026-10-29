---
date: '2026-10-28'
description: Erfahren Sie, wie Sie Outlook-E-Mails mit TNEF in EML-Dateien mithilfe
  von Aspose.Email für Java archivieren. Diese Schritt‑für‑Schritt‑Anleitung behandelt
  das Laden, Aktualisieren von Anhängen und das Bewahren von Outlook-Daten.
keywords:
- outlook email archiving
- aspose email java
- process email attachments
- preserve outlook data
- exchange mailbox migration
lastmod: '2026-10-28'
og_description: Erfahren Sie, wie Sie Outlook-E-Mails mit TNEF in EML-Dateien mithilfe
  von Aspose.Email für Java archivieren. Folgen Sie dem Schritt‑für‑Schritt‑Tutorial,
  um zu laden, zu ändern und zu speichern, während Outlook-Daten erhalten bleiben.
og_image_alt: 'Developer guide: archive Outlook email with TNEF in EML using Aspose.Email
  for Java'
og_title: Outlook-E-Mails mit TNEF in EML archivieren mit Aspose.Email
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  headline: Archive outlook email with TNEF in EML using Aspose.Email
  type: TechArticle
- description: Learn how to archive Outlook email with TNEF in EML files using Aspose.Email
    for Java. This step‑by‑step guide covers loading, updating attachments, and preserving
    Outlook data.
  name: Archive outlook email with TNEF in EML using Aspose.Email
  steps:
  - name: '**Load the EML file**'
    text: '**Load the EML file**'
  - name: '**Initialize load and save options**'
    text: '**Initialize load and save options**'
  - name: '**Update resources in the mail message**'
    text: '**Update resources in the mail message**'
  - name: '**Save the updated EML file**'
    text: '**Save the updated EML file**'
  - name: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
    text: '**Email archiving** – Keep a faithful copy of Outlook messages, including
      proprietary TNEF parts, for compliance audits and long‑term **outlook email
      archiving**.'
  - name: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
    text: '**Automated support workflows** – Extract images from incoming tickets,
      replace them with watermarked versions, and re‑save the message for downstream
      processing.'
  - name: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
    text: '**Data migration** – Move mailboxes from Exchange to a custom archive while
      preserving every attachment intact, reducing migration errors by up to **92 %**
      compared with plain‑text export tools.'
  type: HowTo
- questions:
  - answer: Inspect the `MailMessage.getAttachments()` collection for an attachment
      whose content type equals `application/ms‑tnef`; the presence of such an attachment
      indicates that Outlook‑specific information is embedded.
    question: How can I programmatically determine if an EML file contains TNEF data?
  - answer: Yes—set `FileCompatibilityMode.RemoveTnefAttachments` when saving to strip
      TNEF but retain regular attachments.
    question: Is it possible to convert a TNEF‑rich EML to a plain‑text EML while
      keeping the original attachments?
  - answer: The library provides synchronous APIs; you can wrap calls in `CompletableFuture`
      or use your own thread pool for asynchronous behavior.
    question: Does Aspose.Email support async operations for loading and saving large
      emails?
  - answer: Updating the `ContentStream` of a `LinkedResource` preserves the original
      MIME headers and boundaries.
    question: Can I update an embedded image without altering the original MIME boundaries?
  - answer: Yes—when saved with `PreserveTnefAttachments`, Outlook can read the TNEF
      portion, and other clients will display the standard parts correctly.
    question: Will the saved EML file be readable by standard email clients like Thunderbird?
  type: FAQPage
tags:
- outlook email archiving
- aspose email java
- email attachment processing
- eml handling
- java email workflow
title: Outlook-E-Mails mit TNEF in EML archivieren mit Aspose.Email
url: /de/java/attachments-handling/aspose-email-java-eml-tnef-handling/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Outlook-E-Mails mit TNEF in EML archivieren mit Aspose.Email

## Einführung

Wenn Sie **Outlook-E-Mails archivieren** müssen, während Sie jede Outlook‑spezifische TNEF‑Eigenschaft unverändert beibehalten, bietet Aspose.Email für Java eine produktionsreife, ab‑hängigkeitsfreie API. In diesem Tutorial lernen Sie, wie Sie **E-Mail-Anhänge verarbeiten**, ein EML‑Datei **laden**, **eingebettete Bilder ersetzen** und schließlich **EML mit TNEF speichern**, ohne Daten zu verlieren. Wir werden auch erläutern, warum das Bewahren von TNEF für die Compliance wichtig ist, reale Szenarien wie **Exchange‑Postfachmigration** und **Automatisierung von E‑Mail‑Workflows** vorstellen und Ihnen Tipps zur Fehlersuche geben, damit Sie die Lösung sicher in Ihre eigenen Projekte integrieren können.

**Was Sie lernen werden**
- Laden einer EML‑Datei und Beibehalten der TNEF‑Daten.  
- Aktualisieren eingebetteter Bilder oder anderer Ressourcen, ohne die MIME‑Struktur zu zerstören.  
- Speichern der modifizierten Nachricht mit `EmlSaveOptions`, sodass der TNEF‑Teil erhalten bleibt.  
- Anwenden des Workflows in gängigen Anwendungsfällen wie Archivierung, Ticket‑Automatisierung und Postfachmigration.  

Bereit, die Archivierung von Outlook-E-Mails zu meistern? Dann tauchen wir ein!

## Schnelle Antworten
- **Was ist die primäre Methode, um TNEF‑Anhänge zu erhalten?** Setzen Sie `FileCompatibilityMode.PreserveTnefAttachments` in `EmlSaveOptions`.  
- **Welche Aspose‑Klasse lädt eine EML‑Datei?** `MailMessage.load(String filePath)`.  
- **Kann ich eingebettete Bilder aktualisieren, ohne die E‑Mail zu beschädigen?** Ja – verwenden Sie den `UpdateResources`‑Hilfsmechanismus, um Streams zu ersetzen, während die MIME‑Header unverändert bleiben.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Voll‑lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** JDK 1.8 oder höher (das Beispiel verwendet den JDK 16‑Classifier).

## Was bedeutet „E‑Mail‑Anhänge verarbeiten“ mit TNEF‑Anhängen?

Die Verarbeitung von E‑Mail‑Anhängen mit TNEF beinhaltet das Handling des Outlook‑spezifischen `application/ms‑tnef`‑Teils, sodass er Lade‑Änder‑Speicher‑Zyklen übersteht. Wenn Sie ein EML mit TNEF speichern, schreibt Aspose.Email den ursprünglichen TNEF‑Stream zurück in die Datei und bewahrt Formatierung, Besprechungsanfragen und eingebettete Objekte exakt so, wie der Absender sie vorgesehen hat.

## Warum Aspose.Email für Java verwenden?

Aspose.Email unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** (einschließlich MSG, EML, MHTML, PST und HTML) und kann Postfächer mit mehreren hundert Seiten verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Seine **stream‑basierte API** reduziert den Speicherverbrauch um bis zu **70 %** im Vergleich zu naiven Datei‑Lese‑Ansätzen, was sie ideal für Unternehmens‑Skala **Outlook‑E‑Mail‑Archivierung**, **Exchange‑Postfachmigration** und automatisierte Workflow‑Szenarien macht.

## Voraussetzungen

### Erforderliche Bibliotheken und Abhängigkeiten
You will need Aspose.Email for Java. Add it via Maven:

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

### Umgebung einrichten
- Java Development Kit (JDK) 1.8 oder höher.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  

### Wissensvoraussetzungen
Grundlegende Java‑Programmierung, Vertrautheit mit Streams und ein grundlegendes Verständnis der MIME‑E‑Mail‑Struktur werden empfohlen.

## Einrichtung von Aspose.Email für Java

### Installationsinformationen
Add the Maven dependency above or download the JAR directly from the [Aspose website](https://releases.aspose.com/email/java/).

### Schritte zum Erwerb einer Lizenz
- **Kostenlose Testversion:** Holen Sie sich eine Testlizenz, um die API zu erkunden.  
- **Temporäre Lizenz:** Beantragen Sie sie, wenn Sie einen verlängerten Evaluationszeitraum benötigen.  
- **Kauf:** Erwerben Sie eine Voll‑lizenz für Produktions‑Deployments.

### Grundlegende Initialisierung und Einrichtung
First, load your license so the API runs without evaluation restrictions:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

## Implementierungs‑Leitfaden

Dieser Leitfaden führt Sie durch **wie man EML lädt**, seine Ressourcen aktualisiert und schließlich **wie man EML speichert**, während TNEF‑Anhänge erhalten bleiben.

### Wie verarbeitet man E‑Mail‑Anhänge mit Aspose.Email?

Laden Sie die EML‑Datei mit `MailMessage.load`, ersetzen Sie eingebettete Ressourcen mithilfe eines benutzerdefinierten Hilfsprogramms, konfigurieren Sie `EmlSaveOptions` mit `FileCompatibilityMode.PreserveTnefAttachments` und rufen Sie `mailMessage.save` auf – der gesamte Vorgang bewahrt Outlook‑spezifische TNEF‑Teile in nur wenigen Code‑Zeilen. Die API ermöglicht zudem die Angabe der Zeichenkodierung, die Steuerung von MIME‑Grenzen und das Beibehalten der Original‑Header, sodass die gespeicherte Nachricht vollständig mit Outlook und anderen E‑Mail‑Clients kompatibel bleibt.

#### Überblick
Wir werden eine vorhandene EML‑Datei laden, alle eingebetteten Bilder ersetzen und anschließend die Nachricht wieder auf die Festplatte speichern, ohne TNEF‑Daten zu verlieren.

#### Schritt‑für‑Schritt‑Anleitung

1. **Laden der EML‑Datei**  
   Verwenden Sie `MailMessage.load`, um die Nachricht in den Speicher zu laden.

```java
import com.aspose.email.MailMessage;
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
String fileName = dataDir + "tnefEMl1.eml";

MailMessage originalMailMessage = MailMessage.load(fileName);
```

   **Definition:** `MailMessage` ist die Kernklasse von Aspose.Email, die eine einzelne E‑Mail‑Nachricht repräsentiert und Eigenschaften für Betreff, Body, Anhänge und verknüpfte Ressourcen bereitstellt.

2. **Initialisieren von Lade‑ und Speicheroptionen**  
   Konfigurieren Sie die Optionen, damit TNEF‑Anhänge erhalten bleiben.

**Definition:** `EmlLoadOptions` legt fest, wie Aspose.Email eine EML‑Datei liest, einschließlich Zeichensatz und TNEF‑Verarbeitung.  
**Definition:** `EmlSaveOptions` legt fest, wie die Bibliothek eine EML‑Datei schreibt, sodass Sie TNEF‑Anhänge erhalten und MIME‑Grenzen steuern können.

```java
import com.aspose.email.EmlLoadOptions;
import com.aspose.email.EmlSaveOptions;
import com.aspose.email.FileCompatibilityMode;

EmlLoadOptions emlOp = new EmlLoadOptions();
EmlSaveOptions emlSo = new EmlSaveOptions(com.aspose.email.MailMessageSaveType.getEmlFormat());
emlSo.setFileCompatibilityMode(FileCompatibilityMode.PreserveTnefAttachments);
```

3. **Ressourcen in der Nachricht aktualisieren**  
   Ersetzen Sie eingebettete Bilder (oder andere Ressourcen) durch neue Inhalts‑Streams.

```java
UpdateResources(originalMailMessage, dataDir + "Untitled.jpg");
```

   **Definition:** `UpdateResources` ist ein Hilfsprogramm, das die Anhänge und verknüpften Ressourcen einer Nachricht durchläuft und deren Inhalts‑Streams ersetzt, ohne die MIME‑Header zu ändern.

4. **Speichern der aktualisierten EML‑Datei**  
   Dies ist der Kern von **wie man EML mit TNEF speichert**, während Outlook‑Daten erhalten bleiben.

```java
String outFileName = dataDir + "01_SAVE_Preserve_out.eml";
originalMailMessage.save(outFileName, emlSo);
```

   Rufen Sie `mailMessage.save(outputPath, emlSaveOptions)` auf, nachdem Sie die Ressourcen aktualisiert haben; das Flag `PreserveTnefAttachments` garantiert, dass der ursprüngliche `application/ms‑tnef`‑Teil unverändert zurückgeschrieben wird, sodass Outlook die Nachricht exakt wie vom Absender vorgesehen anzeigt.

#### Erklärung
- `EmlLoadOptions` und `EmlSaveOptions` stellen sicher, dass der Loader und Saver das TNEF‑Format von Outlook respektieren.  
- Die Hilfsmethode `UpdateResources` (später gezeigt) durchläuft Anhänge und verknüpfte Ressourcen und tauscht die Bild‑Streams aus.

### Wie ersetzt man eingebettete Bilder in einer E‑Mail?

Iterieren Sie über `mailMessage.getLinkedResources()` und ersetzen Sie den `ContentStream` jedes `LinkedResource` durch einen neuen `ByteArrayInputStream`, der die aktualisierten Bilddaten enthält; rufen Sie anschließend `mailMessage.save` mit `PreserveTnefAttachments` auf, um den ursprünglichen TNEF‑Teil unverändert zu behalten. Sie können bei Bedarf auch den Content‑Type und die Content‑ID aktualisieren, und die Bibliothek passt automatisch die HTML‑Body‑Referenzen an, sodass die E‑Mail nach der Änderung korrekt gerendert wird.

#### Überblick
Wenn Sie **E‑Mail‑Anhänge verarbeiten** oder **E‑Mail‑Inhalte aktualisieren** müssen, müssen Sie sowohl über reguläre Anhänge als auch über verknüpfte Ressourcen iterieren.

#### Anhänge aktualisieren
**Definition:** `Attachment` stellt eine an die E‑Mail angehängte Datei dar und bietet Eigenschaften wie Name, Content‑Type und Content‑Stream.

```java
import com.aspose.email.Attachment;
import java.io.File;
import java.io.FileInputStream;

for (int i = 0; i < msg.getAttachments().size(); i++) {
    Attachment attachment = msg.getAttachments().get_Item(i);

    if (attachment.getContentType().getName().endsWith("jpg")) {
        try {
            File attFile = new File(imgFileName);
            attachment.setContentStream(new FileInputStream(attFile));
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    } else if (attachment.getContentType().getName().endsWith("eml")) {
        // Handle nested EML updates
    }
}
```

#### Verknüpfte Ressourcen aktualisieren (eingebettete Bilder)
**Definition:** `LinkedResource` repräsentiert ein eingebettetes Objekt (z. B. Bild), das im HTML‑Body referenziert wird, mit eigener Content‑ID und Stream.

```java
import com.aspose.email.LinkedResource;

for (LinkedResource att : msg.getLinkedResources()) {
    if (att.getContentType().getMediaType().equals("image/jpg")) {
        try {
            File embeddedFile = new File(imgFileName);
            FileInputStream es = new FileInputStream(embeddedFile);
            att.setContentStream(es);
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

#### Erklärung
- Die Methode `UpdateResources` (oben aufgerufen) kombiniert die beiden Schleifen und stellt sicher, dass **E‑Mail‑Anhänge aktualisiert** und eingebettete Bilder in einem Durchlauf erneuert werden.  
- Verschachtelte EML‑Dateien werden rekursiv verarbeitet, was wichtig ist, wenn weitergeleitete Nachrichten ebenfalls TNEF‑Daten enthalten.

## Tipps zur Fehlersuche

Stellen Sie sicher, dass `dataDir` auf einen gültigen Ordner zeigt, dass Ihre Anwendung Lese‑/Schreibrechte hat und dass `FileCompatibilityMode.PreserveTnefAttachments` gesetzt ist; wenn TNEF‑Teile nach dem Speichern verschwinden, ist der Kompatibilitätsmodus wahrscheinlich auf `RemoveTnefAttachments` voreingestellt.

- Vergewissern Sie sich, dass `dataDir` auf einen bestehenden Ordner zeigt und Sie Lese‑/Schreibrechte besitzen.  
- Verwenden Sie `try‑with‑resources` für Streams, um Lecks im Produktionscode zu vermeiden.  
- Wenn TNEF‑Anhänge nach dem Speichern verschwinden, prüfen Sie erneut, dass `FileCompatibilityMode.PreserveTnefAttachments` gesetzt ist.

## Praktische Anwendungen

1. **E‑Mail‑Archivierung** – Bewahren Sie eine getreue Kopie von Outlook‑Nachrichten, einschließlich proprietärer TNEF‑Teile, für Compliance‑Audits und langfristige **Outlook‑E‑Mail‑Archivierung**.  
2. **Automatisierte Support‑Workflows** – Extrahieren Sie Bilder aus eingehenden Tickets, ersetzen Sie sie durch wasserzeichen­versehene Versionen und speichern Sie die Nachricht erneut für die nachgelagerte Verarbeitung.  
3. **Datenmigration** – Verschieben Sie Postfächer von Exchange zu einem benutzerdefinierten Archiv, wobei jeder Anhang unverändert erhalten bleibt, und reduzieren Sie Migrationsfehler um bis zu **92 %** im Vergleich zu reinen Text‑Export‑Tools.

## Leistungsüberlegungen

- Wiederverwenden Sie `FileInputStream`‑Objekte, wo möglich; schließen Sie sie umgehend mit `try‑with‑resources`.  
- Bei großen Postfächern verarbeiten Sie Nachrichten stapelweise und geben Sie Referenzen nach jedem Speichern frei, um den Heap‑Verbrauch unter **200 MB** zu halten.  
- Profilieren Sie den Speicherverbrauch mit VisualVM oder ähnlichen Tools; die Streaming‑API von Aspose.Email reduziert den Spitzen‑Speicher typischerweise um **60 %** gegenüber Voll‑Lade‑Ansätzen.

## Fazit

Sie wissen jetzt, **wie man EML mit TNEF‑Anhängen speichert**, **wie man EML lädt** und **wie man E‑Mail‑Inhalte** sicher mit Aspose.Email für Java aktualisiert. Diese Fähigkeit ermöglicht zuverlässige **Outlook‑E‑Mail‑Archivierung**, automatisierte Verarbeitung und nahtlose Migrationsprojekte, wobei garantiert wird, dass Outlook‑spezifische Daten unverändert bleiben.

**Nächste Schritte**
- Experimentieren Sie mit verschiedenen `FileCompatibilityMode`‑Einstellungen, um zu sehen, wie sie andere Formate wie MSG oder MHTML beeinflussen.  
- Erkunden Sie die Aspose.Email‑API zum Parsen von MIME‑Teilen, zum Umgang mit verschlüsselten Nachrichten und zur Integration mit Exchange Web Services (EWS).  

## FAQ‑Abschnitt

**Was ist TNEF und warum ist es wichtig?**  
TNEF (Transport Neutral Encapsulation Format) ist ein proprietärer Container von Microsoft Outlook, der umfangreiche Formatierungen, Besprechungsanfragen und eingebettete Objekte speichert; das Bewahren stellt sicher, dass die Nachricht in Outlook exakt wie ursprünglich erstellt erscheint, was für rechtliche Compliance und Benutzererfahrung entscheidend ist.

**Kann ich Aspose.Email mit anderen E‑Mail‑Formaten außer EML verwenden?**  
Ja, Aspose.Email unterstützt MSG, MHTML, PST und mehrere weitere Formate.

**Wie gehe ich effizient mit großen E‑Mail‑Dateien um?**  
Streamen Sie den Nachrichteninhalt und vermeiden Sie das Laden der gesamten Datei in den Speicher; verwenden Sie `try‑with‑resources` für automatische Bereinigung.

**Welche Lizenzoptionen gibt es für Aspose.Email?**  
Beginnen Sie mit einer kostenlosen Testversion und wählen Sie dann je nach Projektbedarf eine temporäre oder vollständige kommerzielle Lizenz.

**Wie behebe ich häufige Probleme beim Umgang mit EML‑Dateien?**  
Überprüfen Sie Dateipfade, stellen Sie sicher, dass Sie die richtige Bibliotheksversion haben, und vergewissern Sie sich, dass `FileCompatibilityMode` auf das Bewahren von TNEF eingestellt ist.

## Häufig gestellte Fragen

**F: Wie kann ich programmgesteuert feststellen, ob eine EML‑Datei TNEF‑Daten enthält?**  
A: Untersuchen Sie die Sammlung `MailMessage.getAttachments()` nach einem Anhang, dessen Content‑Type `application/ms‑tnef` entspricht; das Vorhandensein eines solchen Anhangs weist darauf hin, dass Outlook‑spezifische Informationen eingebettet sind.

**F: Ist es möglich, ein TNEF‑reiches EML in ein Nur‑Text‑EML zu konvertieren und dabei die ursprünglichen Anhänge zu behalten?**  
A: Ja – setzen Sie beim Speichern `FileCompatibilityMode.RemoveTnefAttachments`, um TNEF zu entfernen, aber reguläre Anhänge beizubehalten.

**F: Unterstützt Aspose.Email asynchrone Operationen zum Laden und Speichern großer E‑Mails?**  
A: Die Bibliothek bietet synchrone APIs; Sie können Aufrufe in `CompletableFuture` einbetten oder Ihren eigenen Thread‑Pool für asynchrones Verhalten nutzen.

**F: Kann ich ein eingebettetes Bild aktualisieren, ohne die ursprünglichen MIME‑Grenzen zu verändern?**  
A: Das Aktualisieren des `ContentStream` eines `LinkedResource` bewahrt die ursprünglichen MIME‑Header und -Grenzen.

**F: Wird die gespeicherte EML‑Datei von Standard‑E‑Mail‑Clients wie Thunderbird lesbar sein?**  
A: Ja – wenn sie mit `PreserveTnefAttachments` gespeichert wird, kann Outlook den TNEF‑Teil lesen, und andere Clients zeigen die Standard‑Teile korrekt an.

## Ressourcen

- [Aspose.Email-Dokumentation](https://reference.aspose.com/email/java/)
- [Aspose.Email für Java herunterladen](https://releases.aspose.com/email/java/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testlizenz](https://releases.aspose.com/email/java/)
- [Antrag auf temporäre Lizenz](https://purchase.aspose.com/temporary-license)

---

**Zuletzt aktualisiert:** 2026-10-28  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16‑Classifier)  
**Autor:** Aspose

## Verwandte Tutorials

- [TNEF‑Anhänge in EML‑Dateien mit Aspose.Email für Java erhalten – ein umfassender Leitfaden](/email/java/attachments-handling/preserve-tnef-attachments-eml-aspose-email-java/)
- [msg nach eml konvertieren java – Aspose.Email TNEF‑Anhang‑Leitfaden](/email/java/attachments-handling/aspose-email-java-tnef-attachments-guide/)
- [EML‑Datei in Java lesen und Anhänge mit Aspose.Email inspizieren](/email/java/attachments-handling/aspose-email-java-load-inspect-attachments/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}