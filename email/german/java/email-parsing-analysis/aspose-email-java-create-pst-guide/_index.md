---
date: '2026-06-08'
description: Erfahren Sie, wie Sie PST-Dateien mit Aspose.Email für Java erstellen,
  einschließlich des Hinzufügens von Ordnerstrukturen und des effizienten Durchsuchens
  von PST-Inhalten. Schritt‑für‑Schritt‑Anleitung.
keywords:
- how to create pst
- how to add folder
- how to search pst
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  headline: How to Create PST Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to create PST files with Aspose.Email for Java, including
    how to add folder structures and how to search PST content efficiently. Step‑by‑step
    guide.
  name: How to Create PST Files with Aspose.Email for Java
  steps:
  - name: Add Maven Dependency
    text: Add the Aspose.Email Maven dependency to your `pom.xml`. This pulls in all
      required binaries automatically.
  - name: Acquire and Apply a License
    text: A free trial is available, but a permanent license removes evaluation limits
      and enables full‑speed processing.
  - name: Initialize PersonalStorage
    text: The `PersonalStorage` class is Aspose.Email's top‑level object that represents
      a single PST file in memory. After instantiation, all read and write operations
      flow through this object.
  - name: Define Directory Paths
    text: Set source and destination paths for your email files and the PST output
      location.
  - name: Create the PST File
    text: Use `PersonalStorage.create()` with `FileFormatVersion.Unicode` to produce
      a modern Unicode PST that supports large folders and Unicode characters.
  - name: Build Search Query
    text: Construct a query that looks for a keyword in the subject or body, ignoring
      case.
  - name: Execute Query and Retrieve Messages
    text: Run the query on the target folder and iterate over the resulting `MapiMessage`
      collection.
  - name: Initialize PersonalStorage Object
    text: Assume `PersonalStorage` object (`pst`) is already created as shown previously.
  - name: Add to PST Folder
    text: 'Convert `MailMessage` to `MapiMessage` and add it:'
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for full compatibility with Aspose.Email
      for Java.
    question: What is the minimum Java version required?
  - answer: Yes, a trial mode is available but limits PST size to **10 MB** and disables
      certain optimizations.
    question: Can I use Aspose.Email without a license?
  - answer: Process messages in batches, dispose of `MapiMessage` objects promptly,
      and enable lazy loading via `PersonalStorage.setUseUnicode(true)`.
    question: How do I handle large PST files efficiently?
  - answer: Absolutely. When converting `MailMessage` to `MapiMessage`, call `mapiMsg.getAttachments().add(attachment)`
      to embed files.
    question: Is it possible to add attachments to emails in PST files?
  - answer: Aspose offers a dedicated support forum, detailed documentation, and email
      support for licensed customers.
    question: What kind of support is available for troubleshooting issues?
  type: FAQPage
title: Wie man PST-Dateien mit Aspose.Email für Java erstellt
url: /de/java/email-parsing-analysis/aspose-email-java-create-pst-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Beherrschung der E-Mail-Verwaltung mit Aspose.Email für Java

Wenn Sie **how to create pst**-Dateien programmgesteuert erstellen müssen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch jeden Schritt, der erforderlich ist, um eine Unicode‑PST‑Datei zu erzeugen, Standard‑Outlook‑Ordner hinzuzufügen, Nachrichten zu importieren und fall‑unabhängige Suchen durchzuführen – alles mit Aspose.Email für Java. Am Ende verfügen Sie über ein wiederverwendbares Code‑Muster, das von ein paar E‑Mails bis zu Multi‑Gigabyte‑Archiven skaliert.

## Schnelle Antworten
- **Wie fange ich an?** Fügen Sie die Aspose.Email Maven‑Abhängigkeit hinzu, erhalten Sie eine Lizenz und instanziieren Sie `PersonalStorage`.
- **Kann ich einen Posteingangs‑Ordner hinzufügen?** Ja – rufen Sie `pst.getRootFolder().addSubFolder("Inbox")` auf.
- **Werden fall‑unabhängige Suchen unterstützt?** Verwenden Sie `PersonalStorageQueryBuilder` mit `StringComparison.OrdinalIgnoreCase`.
- **Welche Dateigröße kann verarbeitet werden?** Aspose.Email verarbeitet PST‑Dateien bis zu 2 GB, ohne die gesamte Datei in den Speicher zu laden.
- **Benötige ich eine kostenpflichtige Lizenz für die Produktion?** Eine permanente Lizenz entfernt Testbeschränkungen und schaltet alle Leistungs‑Features frei.

## Was ist how to create pst?
**how to create pst** bezeichnet den programmgesteuerten Prozess zur Erstellung einer Outlook Personal Storage Table (PST)‑Datei mittels Code anstelle der Outlook‑Benutzeroberfläche. Aspose.Email für Java bietet eine vollständig verwaltete API, die Unicode‑PST‑Dateien erstellt, Ordner hinzufügt und `MapiMessage`‑Objekte speichert, ohne dass Outlook installiert sein muss.

## Warum Aspose.Email für die PST‑Erstellung verwenden?
Aspose.Email unterstützt **50+** e‑mail‑bezogene Formate (MSG, EML, MBOX, PST usw.) und kann PST‑Dateien mit **bis zu 2 GB** Größe verarbeiten, während der Speicherverbrauch dank der Lazy‑Loading‑Architektur unter **150 MB** bleibt. Diese quantifizierbare Fähigkeit macht es ideal für Unternehmensarchivierung, Migration und Compliance‑Szenarien.

## Voraussetzungen

- **Java Development Kit (JDK)** – Version 16 oder höher.
- **Maven** – für das Abhängigkeits‑Management.
- Grundlegende Kenntnisse der Java‑Syntax; Vorkenntnisse mit PST‑Dateien sind nicht erforderlich.

## Wie erstelle ich eine PST‑Datei?

Die Klasse `PersonalStorage` repräsentiert eine PST‑Datei und bietet Methoden zum Erstellen, Öffnen und Manipulieren ihres Inhalts. Um eine neue Unicode‑PST zu erstellen, rufen Sie `PersonalStorage.create()` mit dem gewünschten Dateipfad und der Formatversion auf. Dieser Vorgang erzeugt eine moderne PST, die große Ordner, Unicode‑Zeichen und effizientes Streaming unterstützt und somit sowohl für kleine als auch für Unternehmens‑Archivierungsaufgaben geeignet ist.

### Schritt 1: Maven‑Abhängigkeit hinzufügen

Fügen Sie die Aspose.Email Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu. Dadurch werden alle erforderlichen Binärdateien automatisch eingebunden.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Schritt 2: Lizenz erwerben und anwenden

Eine kostenlose Testversion ist verfügbar, aber eine permanente Lizenz entfernt Evaluationsbeschränkungen und ermöglicht die Verarbeitung mit voller Geschwindigkeit.

```java
import com.aspose.email.*;

public class AsposeEmailSetup {
    public static void main(String[] args) {
        // Set up license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, proceeding with trial version.");
        }

        System.out.println("Aspose.Email for Java is ready to use!");
    }
}
```

## Wie füge ich einen Ordner zur PST hinzu?

Erstellen Sie die gewünschte Ordnerhierarchie unter dem PST‑Root und referenzieren Sie sie beim Einfügen von Nachrichten. Das Objekt `FolderInfo` repräsentiert jeden Ordner und kann beliebig verschachtelt werden, sodass Sie Strukturen wie Posteingang, Gesendete Elemente oder benutzerdefinierte Projektordner aufbauen können. Das Hinzufügen von Ordnern ist ein leichter Vorgang, der keinen Nachrichteninhalt lädt und die Leistung selbst bei großen PSTs erhält.

### Schritt 1: PersonalStorage initialisieren

Die Klasse `PersonalStorage` ist das Top‑Level‑Objekt von Aspose.Email, das eine einzelne PST‑Datei im Speicher repräsentiert. Nach der Instanziierung laufen alle Lese‑ und Schreibvorgänge über dieses Objekt.

```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.PersonalStorage;
```

### Schritt 2: Verzeichnispfade definieren

Legen Sie Quell‑ und Zielpfade für Ihre E‑Mail‑Dateien sowie den Ausgabepfad der PST fest.

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
String outputDir = "YOUR_OUTPUT_DIRECTORY";
```

### Schritt 3: PST‑Datei erstellen

Verwenden Sie `PersonalStorage.create()` mit `FileFormatVersion.Unicode`, um eine moderne Unicode‑PST zu erzeugen, die große Ordner und Unicode‑Zeichen unterstützt.

```java
try {
    PersonalStorage pst = PersonalStorage.create(outputDir + "NewPSTFile_out.pst", FileFormatVersion.Unicode);

    // Perform operations here.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Wie suche ich in einer PST?

`PersonalStorageQueryBuilder` ist eine Builder‑Klasse, die zum Erstellen von Suchabfragen für PST‑Inhalte verwendet wird. Durch Konfiguration des Builders mit den gewünschten Kriterien und Angabe von `StringComparison.OrdinalIgnoreCase` können Sie schnelle, fall‑unabhängige Suchen über Betreff, Textkörper und benutzerdefinierte Eigenschaften durchführen, ohne die gesamte PST in den Speicher zu laden.

### Schritt 1: Suchabfrage erstellen

Erstellen Sie eine Abfrage, die nach einem Schlüsselwort im Betreff oder Textkörper sucht und dabei die Groß‑/Kleinschreibung ignoriert.

```java
import com.aspose.email.MailQueryBuilder;
import com.aspose.email.MailQuery;
import com.aspose.email.MessageInfoCollection;

MailQueryBuilder builder = new MailQueryBuilder();
builder.getFrom().contains("automated", true);
```

### Schritt 2: Abfrage ausführen und Nachrichten abrufen

Führen Sie die Abfrage im Zielordner aus und iterieren Sie über die resultierende `MapiMessage`‑Sammlung.

```java
try {
    MailQuery query = builder.getQuery();
    MessageInfoCollection coll = fi.getContents(query);

    // Process results as needed.
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Einen vordefinierten Ordner in der PST erstellen

Das Hinzufügen eines vordefinierten Ordners wie **Inbox** hilft, Ihre E‑Mail‑Daten effektiv zu organisieren.

### Schritt 1: PersonalStorage‑Objekt initialisieren
Angenommen, das `PersonalStorage`‑Objekt (`pst`) wurde bereits wie zuvor erstellt.

### Schritt 2: Den Ordner „Inbox“ erstellen

```java
try {
    FolderInfo fi = pst.createPredefinedFolder("Inbox", StandardIpmFolder.Inbox);
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Nachrichten zu einem PST‑Ordner hinzufügen

Füllen Sie Ihren PST‑Ordner mit E‑Mail‑Nachrichten, indem Sie diese aus Dateien laden und konvertieren.

### Schritt 1: E‑Mail‑Nachricht laden

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MapiMessage;

MailMessage mailMessage = MailMessage.load(dataDir + "message.msg");
```

### Schritt 2: Zur PST hinzufügen

Konvertieren Sie `MailMessage` zu `MapiMessage` und fügen Sie sie hinzu:

```java
try {
    fi.addMessage(MapiMessage.fromMailMessage(mailMessage));
} finally {
    if (pst != null)
        pst.dispose();
}
```

## Praktische Anwendungsfälle

Aspose.Email für Java dient nicht nur der Erstellung von PST‑Dateien; es ist ein vielseitiges Werkzeug mit zahlreichen Einsatzmöglichkeiten:
- **E‑Mail‑Archivierung**: Automatisieren Sie die Archivierung von Unternehmens‑E‑Mails in PST‑Dateien und unterstützen Sie Aufbewahrungsrichtlinien von bis zu 10 Jahren.
- **Migrations‑Tools**: Migrieren Sie nahtlos von Legacy‑Mail‑Stores (z. B. MBOX) zu Outlook‑PST mit einem einzigen API‑Aufruf pro Nachricht.
- **Datenanalyse**: Extrahieren Sie Metadaten wie Absender, Empfänger und Zeitstempel für Business‑Intelligence‑Pipelines.
- **Backup‑Lösungen**: Entwickeln Sie robuste Backup‑Utilities, die inkrementelle E‑Mail‑Änderungen speichern, ohne das gesamte Postfach neu zu verarbeiten.

## Leistungs‑Überlegungen

Um optimale Leistung bei der Verwendung von Aspose.Email zu gewährleisten:
- **Ressourcen‑Management**: Rufen Sie stets `pst.dispose()` auf oder verwenden Sie try‑with‑resources, um native Handles sofort freizugeben.
- **Batch‑Verarbeitung**: Verarbeiten Sie E‑Mails in Batches von **500** Elementen, um den Speicherverbrauch vorhersehbar zu halten.
- **Parallelität**: Die Bibliothek ist für reine Lesevorgänge thread‑sicher; für Schreibvorgänge synchronisieren Sie den Zugriff auf die `PersonalStorage`‑Instanz.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **OutOfMemoryError** beim Umgang mit großen PSTs | Gesamte PST wird in den Speicher geladen | Aktivieren Sie `PersonalStorage.setUseUnicode(true)` und verarbeiten Sie Nachrichten in Streams. |
| **Ordner nicht gefunden**‑Fehler | Falsche Groß‑/Kleinschreibung im Ordnerpfad | Verwenden Sie `StringComparison.OrdinalIgnoreCase` in Abfragen oder normalisieren Sie Ordnernamen. |
| **Lizenz nicht angewendet** | Lizenzdatei nicht vor dem ersten API‑Aufruf geladen | Laden Sie die Lizenz beim Anwendungsstart, bevor Sie `PersonalStorage`‑Objekte erstellen. |

## Häufig gestellte Fragen

**F: Welche minimale Java‑Version ist erforderlich?**  
A: JDK 16 oder höher wird für die volle Kompatibilität mit Aspose.Email für Java empfohlen.

**F: Kann ich Aspose.Email ohne Lizenz nutzen?**  
A: Ja, ein Testmodus ist verfügbar, beschränkt jedoch die PST‑Größe auf **10 MB** und deaktiviert bestimmte Optimierungen.

**F: Wie gehe ich effizient mit großen PST‑Dateien um?**  
A: Verarbeiten Sie Nachrichten in Batches, geben Sie `MapiMessage`‑Objekte zügig frei und aktivieren Sie Lazy‑Loading via `PersonalStorage.setUseUnicode(true)`.

**F: Ist es möglich, Anhänge zu E‑Mails in PST‑Dateien hinzuzufügen?**  
A: Absolut. Beim Konvertieren von `MailMessage` zu `MapiMessage` rufen Sie `mapiMsg.getAttachments().add(attachment)` auf, um Dateien einzubetten.

**F: Welche Unterstützung gibt es bei der Fehlersuche?**  
A: Aspose bietet ein dediziertes Support‑Forum, ausführliche Dokumentation und E‑Mail‑Support für lizenzierte Kunden.

## Ressourcen
- [Documentation](https://reference.aspose.com/email/java/)
- [Download](https://releases.aspose.com/email/java/)
- [Purchase](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/email/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-06-08  
**Getestet mit:** Aspose.Email für Java 24.10  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Create and Manage Outlook PST Files Using Aspose.Email for Java](/email/java/outlook-pst-ost-operations/aspose-email-java-manage-pst-files/)
- [Manipulate PST Files Using Aspose.Email for Java: A Comprehensive Guide](/email/java/outlook-pst-ost-operations/manipulate-pst-files-aspose-email-java/)
- [Extract Email Attachments Java - Using Aspose.Email for PST Files – A Step‑by‑Step Guide](/email/java/attachments-handling/extract-email-attachments-pst-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}