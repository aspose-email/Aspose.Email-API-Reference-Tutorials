---
date: '2026-06-13'
description: Erfahren Sie, wie Sie MSG-Dateien lesen und MSG-Anhänge mit Aspose.Email
  for Java parsen, um Liefer-/Lesebestätigungen und Abstimmungsergebnisse effizient
  zu extrahieren. Enthält Einrichtung, Code und bewährte Methoden.
keywords:
- how to read msg
- parse msg attachments
- Aspose.Email for Java
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  headline: How to Read MSG Files with Aspose.Email for Java
  type: TechArticle
- description: Learn how to read MSG files and parse MSG attachments using Aspose.Email
    for Java, extracting delivery/read receipts and vote results efficiently. Includes
    setup, code, and best practices.
  name: How to Read MSG Files with Aspose.Email for Java
  steps:
  - name: Load the MSG File
    text: MapiMessage is the Aspose.Email class that represents an Outlook MSG message.
  - name: Iterate Over Recipients
    text: MapiRecipient represents a single recipient (To, CC, or BCC) in the MSG
      file.
  - name: Retrieve and Print Delivery Time
    text: DeliveryTime is a property of MapiRecipient that holds the timestamp when
      the message was delivered to the recipient’s server.
  - name: Retrieve and Print Read Time
    text: ReadTime is a property of MapiRecipient indicating when the recipient opened
      the message, if that information is available.
  - name: Load the MSG File
    text: MapiMessage is used again to access the voting information embedded in the
      MSG file.
  - name: Iterate Over Recipients
    text: MapiRecipient provides access to each participant’s voting choice and response
      time.
  - name: Retrieve and Print Response
    text: The `VotingResponse` property contains the actual vote (e.g., “Accept”,
      “Decline”, or custom options).
  - name: Retrieve and Print Response Time
    text: '`VotingResponseTime` records when the recipient submitted their vote, allowing
      chronological analysis of poll activity.'
  type: HowTo
- questions:
  - answer: Split the file into smaller segments or use the streaming API to read
      portions without full in‑memory loading.
    question: How do I handle MSG files larger than 500 MB?
  - answer: Yes, map the receipt and vote fields to your DB schema and use JDBC or
      an ORM to persist them.
    question: Can I store the extracted data directly into a database?
  - answer: Absolutely; Aspose.Email for Java is platform‑agnostic and runs on any
      OS with a supported JDK.
    question: Does the library work on Linux environments?
  - answer: Use `MailMessage.getAttachments()` after loading the MSG; the method returns
      a collection of all embedded files.
    question: Is there a way to extract attachments while reading receipts?
  - answer: Reach out via the official Aspose Email Forum for community help or open
      a support ticket with a valid license.
    question: What support options are available if I encounter bugs?
  type: FAQPage
title: Wie man MSG-Dateien mit Aspose.Email for Java liest
url: /de/java/email-parsing-analysis/aspose-email-java-msg-receipts-vote-results/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So lesen Sie MSG-Dateien mit Aspose.Email für Java

## Einführung

Das programmgesteuerte Lesen von MSG-Dateien ermöglicht es Ihnen, wertvolle Tracking-Daten—Zustellbestätigungen, Lesebestätigungen und Abstimmungsergebnisse—aus Outlook-Nachrichten zu extrahieren. In diesem Leitfaden zeigen wir **wie man MSG-Dateien** mit Aspose.Email für Java liest, gehen die erforderliche Einrichtung durch und demonstrieren, wie man Empfangs- und Abstimmungsinformationen effizient extrahiert.

## Schnelle Antworten
- **Welche Bibliothek verarbeitet das MSG-Parsing?** Aspose.Email für Java.  
- **Kann ich Lesebestätigungen extrahieren?** Ja, die API gibt Liefer- und Lesezeitstempel zurück.  
- **Sind Abstimmungsdaten zugänglich?** Absolut; Sie können die Abstimmungsantwort jedes Empfängers abrufen.  
- **Brauche ich eine Lizenz?** Eine Testversion funktioniert für Tests; eine kostenpflichtige Lizenz entfernt Bewertungslimits.  
- **Welche Java-Version wird benötigt?** Java 16 oder höher wird empfohlen.

## Was ist Aspose.Email für Java?

Aspose.Email für Java ist eine eigenständige Java-Bibliothek, die das Erstellen, Manipulieren und Konvertieren von E‑Mail‑Formaten ermöglicht, ohne dass Microsoft Outlook erforderlich ist. Sie bietet ein umfangreiches Objektmodell für MSG, EML, PST und viele weitere Formate, sodass Entwickler direkt aus Java‑Code mit E‑Mail‑Daten arbeiten können. (45 Wörter)

## Warum Aspose.Email für Java zum Lesen von MSG-Dateien verwenden?

Aspose.Email für Java unterstützt **über 30 E‑Mail‑Formate** und kann MSG‑Dateien bis zu **500 MB** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Seine Hochleistungs‑Parsing‑Engine reduziert CPU‑ und Speicherverbrauch, was sie ideal für die Verarbeitung großer Mail‑Archive und Echtzeit‑Analyse‑Szenarien macht. (48 Wörter)

## Voraussetzungen

- **Bibliotheken & Abhängigkeiten:** Aspose.Email für Java Version 25.4 oder höher und eine JDK 16+ Runtime.  
- **IDE:** IntelliJ IDEA, Eclipse oder jede Java‑kompatible IDE mit Maven‑Unterstützung.  
- **Grundkenntnisse:** Vertrautheit mit Java‑Syntax und objektorientierten Konzepten.

## Lizenzbeschaffung

Um Aspose.Email für Java zu nutzen, benötigen Sie eine Lizenz:

- **Kostenlose Testversion:** Beginnen Sie mit der kostenlosen Testversion, die auf der [Aspose-Website](https://releases.aspose.com/email/java/) verfügbar ist.  
- **Temporäre Lizenz:** Fordern Sie eine temporäre Lizenz über die [Kaufseite](https://purchase.aspose.com/temporary-license/) an.  
- **Kauf:** Wenn Sie mit der Evaluation zufrieden sind, erwerben Sie eine Lizenz für vollen Zugriff auf alle Funktionen über die Seite [Buy Aspose Products](https://purchase.aspose.com/buy).  

## Wie extrahieren Sie Lese- und Lieferbestätigungsinformationen aus einer MSG-Datei?

Laden Sie die MSG-Datei, durchlaufen Sie deren Empfänger und lesen Sie die Eigenschaften `DeliveryTime` und `ReadTime`. Dieser Ansatz liefert die genauen Zeitstempel, wann der Mail‑Server jedes Empfängers die Nachricht zugestellt hat und wann der Empfänger sie geöffnet hat, und liefert Ihnen präzise Tracking‑Daten für Analysen. (53 Wörter)

### Schritt 1: Laden Sie die MSG-Datei
MapiMessage ist die Aspose.Email‑Klasse, die eine Outlook‑MSG‑Nachricht repräsentiert.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

### Schritt 2: Durchlaufen Sie die Empfänger
MapiRecipient repräsentiert einen einzelnen Empfänger (An, CC oder BCC) in der MSG-Datei.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class RetrieveReceipts {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Schritt 3: Abrufen und Ausgeben der Lieferzeit
DeliveryTime ist eine Eigenschaft von MapiRecipient, die den Zeitstempel enthält, wann die Nachricht an den Server des Empfängers zugestellt wurde.  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Schritt 4: Abrufen und Ausgeben der Lesezeit
ReadTime ist eine Eigenschaft von MapiRecipient, die angibt, wann der Empfänger die Nachricht geöffnet hat, sofern diese Information verfügbar ist.  
```java
            System.out.println("Delivery time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_DELIVERY).getDateTime());
```  

## Wie lesen Sie Abstimmungsergebnisse aus einer MSG-Datei?

Nach dem Laden der Nachricht stellt die API die Abstimmungsantwort jedes Empfängers und den Zeitpunkt seiner Antwort bereit, sodass Sie Umfrageergebnisse programmgesteuert aggregieren können. Diese Daten können verwendet werden, um Zusammenfassungsberichte zu erstellen oder direkt in Business‑Intelligence‑Dashboards für schnelle Entscheidungsfindung einzuspeisen. (53 Wörter)

### Schritt 1: Laden Sie die MSG-Datei
MapiMessage wird erneut verwendet, um auf die in der MSG-Datei eingebetteten Abstimmungsinformationen zuzugreifen.  
```java
            System.out.println("Read time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME_READ).getDateTime());
        }
    }
}
```  

### Schritt 2: Durchlaufen Sie die Empfänger
MapiRecipient bietet Zugriff auf die Abstimmungswahl und die Antwortzeit jedes Teilnehmers.  
```java
import com.aspose.email.MapiMessage;
import com.aspose.email.MapiRecipient;
import com.aspose.email.MapiPropertyTag;

public class ReadVoteResults {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY/outlook/";
        MapiMessage msg = MapiMessage.fromFile(dataDir + "message.msg");
```  

### Schritt 3: Abrufen und Ausgeben der Antwort
Die Eigenschaft `VotingResponse` enthält die tatsächliche Stimme (z. B. „Accept“, „Decline“ oder benutzerdefinierte Optionen).  
```java
        for (MapiRecipient recipient : msg.getRecipients()) {
            System.out.println("Recipient: " + recipient.getDisplayName());
```  

### Schritt 4: Abrufen und Ausgeben der Antwortzeit
`VotingResponseTime` zeichnet auf, wann der Empfänger seine Stimme abgegeben hat, was eine chronologische Analyse der Umfrageaktivität ermöglicht.  
```java
            System.out.println("Response: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_AUTORESPONSE_PROP_RESPONSE).getString());
```  

## Praktische Anwendungen

1. **E‑Mail‑Kampagnen‑Tracking:** Messen Sie Öffnungsraten und Zustellungs‑erfolge, indem Sie Empfangszeitstempel analysieren.  
2. **Umfrage‑Analyse:** Konsolidieren Sie Abstimmungsergebnisse aus Outlook‑Umfragen für schnelle Entscheidungsfindung.  
3. **Kunden‑Feedback‑Management:** Ziehen Sie Antwortdaten in CRM‑ oder Analyseplattformen für tiefere Einblicke.

Die Integration dieser Extrakte mit Datenbanken oder BI‑Tools erhöht den Wert der rohen E‑Mail‑Daten.

## Leistungsüberlegungen

- Verarbeiten Sie große MSG‑Dateien in **Stücken**, um den Speicherverbrauch gering zu halten.  
- Verwenden Sie **Streaming‑APIs**, wenn Sie mit Tausenden von Nachrichten arbeiten.  
- Speichern Sie Empfängerdaten in leichten Sammlungen wie `ArrayList` oder `HashMap` für schnelle Abfragen.

## Häufige Probleme und Lösungen

- **Null‑Zeitstempel:** Ein fehlendes `ReadTime` bedeutet in der Regel, dass der Empfänger die Nachricht noch nicht geöffnet hat.  
- **Große Anhänge:** Enthält eine MSG riesige Anhänge, aktivieren Sie `LoadOptions.setPreserveEmbeddedResources(false)`, um das Laden in den Speicher zu überspringen.  
- **Kodierungsprobleme:** Stellen Sie sicher, dass die richtige Codepage über `MailMessage.setCharset(Charset.forName("UTF-8"))` gesetzt ist, wenn nicht‑ASCII‑Inhalte gelesen werden.

## Häufig gestellte Fragen

**F: Wie gehe ich mit MSG-Dateien größer als 500 MB um?**  
A: Teilen Sie die Datei in kleinere Segmente oder verwenden Sie die Streaming‑API, um Teile zu lesen, ohne die gesamte Datei in den Speicher zu laden.

**F: Kann ich die extrahierten Daten direkt in einer Datenbank speichern?**  
A: Ja, ordnen Sie die Empfangs‑ und Abstimmungsfelder Ihrem DB‑Schema zu und verwenden Sie JDBC oder ein ORM, um sie zu persistieren.

**F: Funktioniert die Bibliothek in Linux‑Umgebungen?**  
A: Absolut; Aspose.Email für Java ist plattformunabhängig und läuft auf jedem Betriebssystem mit einem unterstützten JDK.

**F: Gibt es eine Möglichkeit, Anhänge beim Lesen von Empfangsbestätigungen zu extrahieren?**  
A: Verwenden Sie `MailMessage.getAttachments()` nach dem Laden der MSG; die Methode gibt eine Sammlung aller eingebetteten Dateien zurück.

**F: Welche Support‑Optionen stehen zur Verfügung, wenn ich Bugs finde?**  
A: Wenden Sie sich über das offizielle Aspose Email Forum für Community‑Hilfe an oder öffnen Sie ein Support‑Ticket mit einer gültigen Lizenz.

## Ressourcen
- **Dokumentation:** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **Dokumentation (duplicate):** [Aspose Email Documentation](https://reference.aspose.com/email/java/)  
- **SDK herunterladen:** [Aspose Email Downloads](https://releases.aspose.com/email/java/)  
- **Download‑Bereich:** [Download Section](https://releases.aspose.com/email/java/)  
- **Lizenz kaufen:** [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion:** Beginnen Sie mit einer [Free Trial Version](https://releases.aspose.com/email/java/)  
- **Temporäre Lizenz:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support‑Forum:** [Aspose Email Forum](https://forum.aspose.com/c/email/10)  
- **Support‑Forum (duplicate):** [Aspose Email Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-06-13  
**Getestet mit:** Aspose.Email für Java 25.4  
**Autor:** Aspose

```java
            System.out.println("Response time: " + 
                recipient.getProperties().get_Item(MapiPropertyTag.PR_RECIPIENT_TRACKSTATUS_TIME).getDateTime());
        }
    }
}
```

## Verwandte Tutorials

- [Wie man Outlook‑MSG‑Dateien mit Aspose.Email für Java lädt und analysiert: Ein umfassender Leitfaden](/email/java/mapi-operations/outlook-msg-aspose-email-java-guide/)
- [MSG nach EML konvertieren und Anhänge mit Aspose.Email für Java verwalten](/email/java/attachments-handling/aspose-email-java-master-msg-attachments-parsing/)
- [Inline‑Anhänge in Java extrahieren – MSG‑Dateien mit Aspose.Email](/email/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}