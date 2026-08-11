---
date: '2026-08-11'
description: Erfahren Sie, wie Sie PST-Ordner und -Nachrichten mit Aspose.Email für
  Java verschieben – eine Schritt‑für‑Schritt‑Anleitung zum effizienten Verschieben
  von PST.
keywords:
- how to move pst
- Aspose.Email Java
- PST folder manipulation
- email migration Java
lastmod: '2026-08-11'
og_description: Erfahren Sie, wie Sie PST-Ordner und -Nachrichten mit Aspose.Email
  für Java in wenigen Codezeilen verschieben. Dieser Leitfaden behandelt die Einrichtung,
  das Verschieben von Unterordnern, einzelnen Elementen und bewährte Methoden für
  große PST-Dateien.
og_image_alt: Guide showing how to move pst folders and messages using Aspose.Email
  Java SDK
og_title: So verschieben Sie PST-Ordner und -Nachrichten mit Aspose.Email Java
schemas:
- author: Aspose
  dateModified: '2026-08-11'
  description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  headline: How to move pst folders and messages with Aspose.Email Java
  type: TechArticle
- description: Learn how to move pst folders and messages using Aspose.Email for Java
    – a step‑by‑step guide on how to move pst efficiently.
  name: How to move pst folders and messages with Aspose.Email Java
  steps:
  - name: Access predefined folders
    text: '- **Inbox folder**: - **Deleted Items folder**:'
  - name: Move all subfolders
    text: CODE_BLOCK_PLACEHOLDER_15_END
  - name: Access source and destination folders
    text: CODE_BLOCK_PLACEHOLDER_17_END
  - name: Get a specific subfolder from the Inbox
    text: CODE_BLOCK_PLACEHOLDER_18_END
  - name: Move all contents of the subfolder
    text: CODE_BLOCK_PLACEHOLDER_19_END
  type: HowTo
- questions:
  - answer: A PST (Personal Storage Table) file is Outlook’s proprietary format for
      storing email messages, contacts, calendar items, and other mailbox data locally.
    question: What is a PST file?
  - answer: Yes, you can use it commercially provided you have a valid license obtained
      through [Aspose's purchase options](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Email for Java in commercial projects?
  - answer: Wrap your code in `try‑catch` blocks to capture `IOException`, `InvalidOperationException`,
      or Aspose‑specific exceptions, then log the error details or re‑throw as needed.
    question: How do I handle exceptions when working with PST files using Aspose.Email?
  - answer: You need JDK 16 or newer and a compatible IDE such as IntelliJ IDEA or
      Eclipse. The Aspose.Email JAR must be on your project’s classpath.
    question: What are the system requirements for running this code?
  - answer: Visit the official documentation at the [Aspose Email Java Reference](https://reference.aspose.com/email/java/).
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- move pst
- Aspose.Email
- Java email processing
title: So verschieben Sie PST-Ordner und -Nachrichten mit Aspose.Email Java
url: /de/java/email-message-operations/aspose-email-java-move-pst-messages-folders/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man PST-Ordner und -Nachrichten mit Aspose.Email Java verschiebt

Effizientes E-Mail-Management ist entscheidend, wenn Sie große Outlook-PST-Dateien neu organisieren müssen. In diesem Tutorial lernen Sie **wie man PST**-Ordner und -Nachrichten programmgesteuert mit Aspose.Email für Java zu verschieben, wodurch automatisierte Bereinigung, Migration und Archivierung ohne Start von Outlook ermöglicht werden. Für vollständige API-Details siehe die [Aspose Email Java Reference](https://reference.aspose.com/email/java/).

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Email for Java  
- **Kann ich sowohl Ordner als auch einzelne Nachrichten verschieben?** Ja – verwenden Sie `moveItem` für Nachrichten und `moveSubfolders` für ganze Ordner  
- **Benötige ich eine Lizenz für die Produktion?** Eine gültige Aspose-Lizenz ist für kommerzielle Einsätze erforderlich  
- **Welche Java-Version wird empfohlen?** Java 16 oder neuer für optimale Leistung  
- **Wird eine Beispiel-PST-Datei benötigt?** Jede von Outlook erzeugte PST funktioniert; Sie können eine mit Outlook erstellen oder eine Testdatei verwenden  

## Was bedeutet das Verschieben von PST in der Java-Entwicklung?

Das Verschieben von PST bezieht sich auf das programmgesteuerte Verlegen von Ordnern oder E-Mail-Elementen innerhalb einer Personal Storage Table (PST)-Datei. Dadurch können Sie die Massenbereinigung, Archivierung alter E-Mails oder die Migration von Inhalten zwischen Mail-Stores automatisieren, ohne manuell Outlook zu verwenden, was die Effizienz steigert und menschliche Fehler reduziert.

## Warum Aspose.Email für Java zum Verschieben von PST-Daten verwenden?

Sie können PST-Daten mit Aspose.Email verschieben, weil es eine **reine Java-API** bereitstellt, die auf jedem Betriebssystem funktioniert, **PST-Dateien über 100 GB** unterstützt und **bis zu 500 000 Elemente pro Minute** auf Standard-Serverhardware verarbeitet. Die Bibliothek bietet zudem detaillierte Ausnahmen, sodass Sie Probleme schnell identifizieren können.

## Voraussetzungen
- Aspose.Email für Java (neueste Version)  
- JDK 16+ (oder neuer)  
- Maven‑ oder Gradle‑Buildsystem  
- Eine PST-Datei zum Testen (jede von Outlook erzeugte Datei)

## Einrichtung von Aspose.Email für Java
Um Aspose.Email zu verwenden, fügen Sie die Maven-Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Schritte zum Erwerb einer Lizenz
1. **Kostenlose Testversion** – beginnen Sie mit einer kostenlosen Testversion, um die Funktionen von Aspose.Email zu erkunden.  
2. **Temporäre Lizenz** – erhalten Sie eine temporäre Lizenz für erweiterten Gebrauch von [Aspose-Website](https://purchase.aspose.com/temporary-license/).  
3. **Kauf** – erwägen Sie den Kauf einer Voll-Lizenz, wenn die Bibliothek Ihre Produktionsanforderungen erfüllt. Für Preisdetails siehe [Aspose-Kaufoptionen](https://purchase.aspose.com/buy).  

### Grundlegende Initialisierung und Einrichtung
Stellen Sie sicher, dass die Bibliothek korrekt referenziert ist, bevor Sie mit PST-Dateien arbeiten:

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

## Wie man PST-Ordner und -Nachrichten verschiebt
Im Folgenden finden Sie die Kernoperationen, die Sie benötigen, wenn Sie **wie man PST**‑Elemente effizient verschieben möchten.

### PST-Datei initialisieren und zugreifen
`PersonalStorage` ist die Hauptklasse von Aspose.Email zum Öffnen und Manipulieren von PST-Dateien.

```java
PersonalStorage pst = PersonalStorage.fromFile("YOUR_DOCUMENT_DIRECTORY/test.pst");
```

#### Schritt 1: Laden der PST-Datei
```java
    FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
    ```

#### Schritt 2: Zugriff auf vordefinierte Ordner
- **Posteingangs-Ordner**:  
  ```java
    FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
    ```  
- **Gelöschte-Elemente-Ordner**:  
  ```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```  

### Unterordner in einen anderen Ordner in PST verschieben
`FolderInfo` repräsentiert einen Ordner innerhalb einer PST-Datei und bietet Methoden zum Verschieben von Unterordnern.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Schritt 1: Zugriff auf Quell- und Zielordner
```java
pst.moveItem(subfolder, deletedItems);
```

#### Schritt 2: Einen bestimmten Unterordner aus dem Posteingang abrufen
```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
MessageInfoCollection contents = subfolder.getContents();
```

#### Schritt 3: Den gesamten Unterordner verschieben
```java
pst.moveItem(contents.get_Item(0), deletedItems);
```

### Einzelne Nachrichten zwischen Ordnern in PST verschieben
`MessageInfoCollection` enthält eine Sammlung von `MessageInfo`‑Objekten, von denen jedes eine E-Mail-Nachricht darstellt.

```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

#### Schritt 1: Nachrichten aus einem bestimmten Unterordner abrufen
```java
inbox.moveSubfolders(deletedItems);
```

#### Schritt 2: Die erste Nachricht in den Ordner Gelöschte Elemente verschieben
```java
FolderInfo inbox = pst.getPredefinedFolder(StandardIpmFolder.Inbox);
FolderInfo deletedItems = pst.getPredefinedFolder(StandardIpmFolder.DeletedItems);
```

### Alle Unterordner von einem Ordner zu einem anderen in PST verschieben
`moveSubfolders` überträgt jeden Unterordner von einer Quelle zu einem Ziel in einem einzigen Aufruf.

```java
FolderInfo subfolder = inbox.getSubFolder("Subfolder");
```

#### Schritt 1: Zugriff auf Quell- und Zielordner
```java
subfolder.moveContents(deletedItems);
```

#### Schritt 2: Alle Unterordner verschieben
CODE_BLOCK_PLACEHOLDER_15_END

### Den gesamten Inhalt eines Unterordners in einen anderen Ordner in PST verschieben
`moveAllContents` (eine benutzerdefinierte Schleife mit `moveItem`) kann jede Nachricht innerhalb eines Unterordners verlegen.

CODE_BLOCK_PLACEHOLDER_16_END

#### Schritt 1: Zugriff auf Quell- und Zielordner
CODE_BLOCK_PLACEHOLDER_17_END

#### Schritt 2: Einen bestimmten Unterordner aus dem Posteingang abrufen
CODE_BLOCK_PLACEHOLDER_18_END

#### Schritt 3: Den gesamten Inhalt des Unterordners verschieben
CODE_BLOCK_PLACEHOLDER_19_END

## Praktische Anwendungen
Das Verschieben von PST-Ordnern und -Nachrichten ist nützlich für:
- **Datenmigration** – Mailboxen von Outlook zu einem anderen Mailsystem verschieben.  
- **E-Mail-Archivierung** – alte Mails automatisch in Archivordner organisieren.  
- **Bereinigungs-Operationen** – Posteingänge aufräumen, indem veraltete Elemente in Archiv- oder Löschordner verschoben werden.

## Leistungsüberlegungen
Beim Umgang mit großen PST-Dateien mit Aspose.Email für Java beachten Sie folgende Tipps:

- **Ressourcennutzung optimieren** – schließen Sie `PersonalStorage`‑Objekte umgehend mit try‑with‑resources oder explizitem `dispose`.  
- **Speicherverwaltung** – verarbeiten Sie Elemente stapelweise statt einen gesamten Ordner in den Speicher zu laden; dies reduziert den Heap‑Druck auf JVMs.  

### Beste Praktiken
- Geben Sie PST‑Ressourcen nach Vorgängen immer frei.  
- Validieren Sie die Existenz von Ordnern, bevor Sie Verschiebungen versuchen, um `InvalidOperationException` zu vermeiden.  

## Häufig gestellte Fragen

**Q: Was ist eine PST‑Datei?**  
A: Eine PST (Personal Storage Table)-Datei ist das proprietäre Format von Outlook zum lokalen Speichern von E‑Mail‑Nachrichten, Kontakten, Kalendereinträgen und anderen Mailbox‑Daten.

**Q: Kann ich Aspose.Email für Java in kommerziellen Projekten verwenden?**  
A: Ja, Sie können es kommerziell nutzen, vorausgesetzt Sie besitzen eine gültige Lizenz, die Sie über [Aspose-Kaufoptionen](https://purchase.aspose.com/buy) erhalten.

**Q: Wie gehe ich mit Ausnahmen um, wenn ich mit PST‑Dateien unter Verwendung von Aspose.Email arbeite?**  
A: Umgeben Sie Ihren Code mit `try‑catch`‑Blöcken, um `IOException`, `InvalidOperationException` oder Aspose‑spezifische Ausnahmen abzufangen, dann protokollieren Sie die Fehlermeldungen oder werfen Sie sie bei Bedarf erneut.

**Q: Was sind die Systemanforderungen für die Ausführung dieses Codes?**  
A: Sie benötigen JDK 16 oder neuer und eine kompatible IDE wie IntelliJ IDEA oder Eclipse. Das Aspose.Email‑JAR muss im Klassenpfad Ihres Projekts liegen.

**Q: Wo finde ich weitere Ressourcen zu Aspose.Email für Java?**  
A: Besuchen Sie die offizielle Dokumentation unter der [Aspose Email Java Referenz](https://reference.aspose.com/email/java/).

**Q: Unterstützt Aspose.Email passwortgeschützte PST‑Dateien?**  
A: Ja, Sie können verschlüsselte PSTs öffnen, indem Sie das Passwort beim Aufruf von `PersonalStorage.fromFile` übergeben.

**Q: Wie kann ich überprüfen, ob ein Verschiebevorgang erfolgreich war?**  
A: Nachdem Sie `moveItem` oder `moveSubfolders` aufgerufen haben, fragen Sie den Zielordner mit `getContents()` oder `getSubFolders()` ab, um das Vorhandensein der verschobenen Elemente zu bestätigen.

## Ressourcen
- **Dokumentation**: [Aspose Email Java Referenz](https://reference.aspose.com/email/java/)  
- **API-Details**: [Aspose Email Java Referenz](https://reference.aspose.com/email/java/)  
- **Download**: [Aspose Email Java Releases](https://releases.aspose.com/email/java/)  
- **Kauf**: [Aspose-Produkte kaufen](https://purchase.aspose.com/buy)  
- **Kostenlose Testversionen**: [Aspose Free Trials](https://releases.aspose.com/email/java/)  
- **Temporäre Lizenz**: [Temporäre Lizenz erhalten](https://purchase.aspose.com/temporary-license/)

---

**Letzte Aktualisierung:** 2026-08-11  
**Getestet mit:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Massenaktualisierung von PST-Nachrichten mit Aspose.Email für Java: Ein umfassender Leitfaden](/email/java/outlook-pst-ost-operations/aspose-email-java-bulk-update-pst-messages/)
- [Wie man Outlook PST-Nachrichten mit Aspose.Email für Java extrahiert: Ein vollständiger Leitfaden](/email/java/outlook-pst-ost-operations/extract-outlook-pst-messages-aspose-email-java/)
- [Nachrichten zwischen PST-Dateien mit Aspose.Email für Java übertragen: Ein umfassender Leitfaden](/email/java/outlook-pst-ost-operations/transfer-messages-between-pst-files-using-aspose-email-for-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}