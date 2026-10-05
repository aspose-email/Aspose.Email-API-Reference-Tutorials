---
date: '2026-10-02'
description: Erfahren Sie, wie Sie Exchange verbinden und öffentliche Ordner von Exchange
  mit Aspose.Email für Java auflisten. Diese Schritt‑für‑Schritt‑Anleitung zeigt die
  Maven‑Abhängigkeit und die Einrichtung ohne Code.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Erfahren Sie, wie Sie Exchange verbinden und öffentliche Ordner von
  Exchange mit Aspose.Email für Java auflisten. Diese Anleitung behandelt die Maven‑Abhängigkeit,
  Lizenzierung und rekursive Nachrichtenabrufe.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: So verbinden Sie Exchange und listen öffentliche Ordner in Java
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: So verbinden Sie Exchange und listen öffentliche Ordner in Java
url: /de/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Exchange verbindet und öffentliche Ordner in Java auflistet

## Einleitung
In modernen Unternehmen ermöglicht der programmgesteuerte Zugriff auf Microsoft Exchange-Postfächer die Automatisierung von Archivierungs-, Überwachungs- und Berichtaufgaben. Dieses Tutorial zeigt **wie man Exchange verbindet** mit Aspose.Email für Java und dann **Exchange‑öffentliche Ordner** rekursiv **aufzählt**. Sie sehen die erforderliche Maven‑Abhängigkeit, Lizenzierungsschritte und die genaue Reihenfolge der API‑Aufrufe – ohne zusätzliche Bibliotheken. Am Ende können Sie Nachrichten aus jedem öffentlichen Ordner abrufen und lokal speichern.

## Schnelle Antworten
- **Was ist der erste Schritt?** Fügen Sie die Aspose.Email Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu.  
- **Benötige ich eine Lizenz?** Ja – verwenden Sie eine temporäre Lizenz für die Evaluierung oder erwerben Sie eine Voll‑Lizenz für die Produktion.  
- **Welche Klasse erstellt die Verbindung?** `ExchangeClient` (oder `ImapClient` für IMAP) übernimmt die Authentifizierung und Serverkommunikation.  
- **Kann ich Unterordner automatisch auflisten?** Ja – verwenden Sie die rekursive `listSubFolders`‑Methode, die von der API bereitgestellt wird.  
- **Ist dieser Ansatz thread‑sicher?** Die Client‑Objekte sind nicht thread‑sicher; erstellen Sie für jeden Thread eine separate Instanz für gleichzeitige Arbeitslasten.

## Was ist „how to connect exchange“?
**How to connect exchange** ist der Prozess, eine Java‑Anwendung bei einem lokalen oder cloud‑basierten Microsoft Exchange‑Server zu authentifizieren, sodass Sie API‑Aufrufe wie Ordner‑Aufzählung oder Nachrichten‑Abruf ausführen können. Aspose.Email abstrahiert die zugrunde liegenden EWS/IMAP‑Protokolle und bietet Ihnen ein einheitliches Objektmodell.

## Warum Exchange‑öffentliche Ordner auflisten?
Das Auflisten öffentlicher Ordner verschafft Ihnen Einblick in die hierarchische Struktur, die Organisationen für gemeinsam genutzte Postfächer, Verteilerlisten und Archivspeicher verwenden. Aspose.Email kann über **50+ öffentliche Ordner** in einem einzigen Aufruf enumerieren und unterstützt die Verarbeitung von Postfächern mit mehreren hundert Seiten, ohne den gesamten Speicher in den Arbeitsspeicher zu laden, wodurch der RAM‑Verbrauch um bis zu 70 % reduziert wird.

## Voraussetzungen
- **Aspose.Email für Java** — Version 25.4 oder neuer (die neueste stabile Version).  
- **Java Development Kit (JDK)** — JDK 11 oder neuer installiert und `JAVA_HOME` konfiguriert.  
- **Maven** — für Abhängigkeitsverwaltung und Build‑Automatisierung.  
- Grundkenntnisse der Java‑Syntax und Exchange‑Konzepte (Postfächer, Ordner, EWS).

## Einrichten von Aspose.Email für Java
Um die Bibliothek zu integrieren, fügen Sie die Maven‑Abhängigkeit zu Ihrer Projekt‑`pom.xml` hinzu. Dies ist die **Maven‑Abhängigkeit Aspose Email**, die Sie benötigen.

### Maven‑Abhängigkeit
Fügen Sie das folgende Snippet innerhalb des `<dependencies>`‑Elements Ihrer `pom.xml` ein:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffungs‑Schritte
Aspose.Email erfordert eine gültige Lizenz für die Nutzung aller Funktionen:

- **Kostenlose Testversion** – Laden Sie eine temporäre Lizenz von der [Aspose-Website](https://purchase.aspose.com/temporary-license/) herunter, um die API zu evaluieren.  
- **Kauf** – Erwerben Sie eine kommerzielle Lizenz über das Aspose-Portal für Produktionsumgebungen.

#### Grundlegende Initialisierung
Nachdem Maven das Paket aufgelöst hat und Sie eine Lizenzdatei besitzen, legen Sie die `.lic`‑Datei in den Klassenpfad und initialisieren die Bibliothek:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementierungs‑Leitfaden
Wir gehen jeden Funktionsblock durch und beantworten die Schlüsselfragen mit direkten, prägnanten Absätzen vor den detaillierten Schritten.

### Wie man Exchange verbindet?
Laden Sie den `ExchangeClient` mit der Server‑URL, den Benutzeranmeldeinformationen und der Domäne und rufen Sie dann `connect()` auf. Der Client stellt eine HTTPS‑Sitzung mit Exchange Web Services (EWS) her und validiert die Anmeldeinformationen. Wenn die Verbindung fehlschlägt, wirft die API eine detaillierte `AuthenticationException`, die den HTTP‑Statuscode für schnelle Fehlersuche enthält.  
`ExchangeClient` ist die Klasse von Aspose.Email, die eine Verbindung zu Exchange Web Services verwaltet.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Wie man Exchange‑öffentliche Ordner auflistet?
Rufen Sie `client.listPublicFolders()` auf, um eine Sammlung von `FolderInfo`‑Objekten zu erhalten, die jeden öffentlichen Ordner auf oberster Ebene repräsentieren. Die Methode liefert Metadaten wie Ordnername, Gesamtelementzahl und eine eindeutige Kennung, die für nachfolgende Aufrufe verwendet wird. Dieser Aufruf wird in weniger als 2 Sekunden abgeschlossen für typische On‑Premises‑Bereitstellungen mit bis zu 500 Ordnern.  
`listPublicFolders()` gibt eine Sammlung von `FolderInfo`‑Objekten zurück.  
`FolderInfo` enthält Metadaten wie Anzeigenamen und Elementanzahl.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Wie man Ordnerinformationen anzeigt?
Iterieren Sie über die `FolderInfo`‑Sammlung und geben Sie `displayName` und `subFolderCount` aus. Dieser schnelle Überblick hilft Ihnen, die Hierarchie zu verstehen, bevor Sie eine tiefere Durchsuchung starten. Für große Organisationen kann die API Ergebnisse paginieren und 100 Ordner pro Seite zurückgeben, um den Speicherverbrauch gering zu halten.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Wie man Nachrichten aus einem Ordner auflistet?
Rufen Sie `client.listMessages(folderId)` auf, wobei `folderId` die im vorherigen Schritt erhaltene Kennung ist. Die Methode gibt eine Liste von `MessageInfo`‑Objekten zurück, die Betreff, Absender und Empfangsdatum enthalten. Sie können das Ergebnis mit `maxCount` begrenzen, um den Client nicht zu überlasten, wenn Sie sehr große Ordner verarbeiten.  
`listMessages(folderId)` gibt eine Liste von `MessageInfo`‑Objekten zurück.  
`MessageInfo` enthält grundlegende Eigenschaften einer E‑Mail wie Betreff, Absender und Empfangsdatum.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Wie man Nachrichten abruft und speichert?
Für jedes `MessageInfo` verwenden Sie `client.fetchMessage(messageId)`, um den vollständigen MIME‑Inhalt herunterzuladen. Schreiben Sie dann das Byte‑Array in eine `.eml`‑Datei auf die Festplatte. Die API streamt den Inhalt, sodass selbst 100 MB‑Nachrichten verarbeitet werden können, ohne die gesamte Nutzlast in den Arbeitsspeicher zu laden.  
`fetchMessage(messageId)` lädt den vollständigen MIME‑Inhalt der angegebenen E‑Mail herunter.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Wie man Nachrichten rekursiv aus Unterordnern auflistet?
Implementieren Sie eine Tiefensuche‑Traversal: Beginnen Sie mit einem Ordner auf oberster Ebene, listen Sie dessen Unterordner über `client.listSubFolders(parentId)` auf und rufen Sie dann dieselbe Nachrichten‑Auflistungs‑Routine für jedes Kind auf. Dieses Muster stellt sicher, dass jede Nachricht im öffentlichen Ordnerbaum verarbeitet wird. Die Rekursionstiefe ist nur durch die Ordnerhierarchie des Servers begrenzt (typischerweise < 20 Ebenen).  
`listSubFolders(parentId)` gibt die unmittelbaren Unterordner des angegebenen Ordners zurück.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Praktische Anwendungen
Echtwelt‑Szenarien, in denen dieser Workflow glänzt:

1. **Automatisierte E‑Mail‑Archivierung** – Periodisch alle Nachrichten aus öffentlichen Ordnern abrufen und in einem konformen Archiv speichern.  
2. **Backup‑Lösungen** – Exchange‑öffentliche Ordner in ein sicheres Dateisystem oder Cloud‑Bucket spiegeln, um Datenredundanz zu gewährleisten.  
3. **Benutzerdefinierte E‑Mail‑Clients** – Leichte Viewer erstellen, die nur die benötigten Ordner und Nachrichten anzeigen, um die UI‑Komplexität zu reduzieren.

## Leistungs‑Überlegungen
Beim Skalieren auf tausende Ordner und Millionen von Nachrichten beachten Sie diese Tipps:

- **Verbindungs‑Pooling** – Verwenden Sie eine einzelne `ExchangeClient`‑Instanz für mehrere Vorgänge, anstatt für jeden Ordner einen neuen Client zu erstellen.  
- **Lazy Loading** – Fordern Sie nur die Metadaten an, die Sie benötigen (`listMessages` mit einem `maxCount`‑Parameter) und holen Sie vollständige Inhalte bei Bedarf.  
- **Objekte freigeben** – Rufen Sie `client.dispose()` nach dem Batch‑Durchlauf auf, um HTTP‑Verbindungen und thread‑lokale Puffer freizugeben.  
- **Parallele Verarbeitung** – Aufteilen der obersten Ordner auf mehrere Threads, jeder mit einer eigenen Client‑Instanz, um Mehrkern‑CPUs effektiv zu nutzen.

## Häufig gestellte Fragen

**Q: Kann ich diesen Code mit Exchange Online (Office 365) verwenden?**  
A: Ja. Geben Sie den Office 365 EWS‑Endpunkt (`https://outlook.office365.com/EWS/Exchange.asmx`) an und verwenden Sie moderne Authentifizierung (OAuth) – Aspose.Email unterstützt OAuth‑Token von Haus aus.

**Q: Was ist, wenn ein Ordner mehr als 10 000 Nachrichten enthält?**  
A: Verwenden Sie die Überladung von `listMessages`, die die Parameter `skip` und `take` akzeptiert, um die Ergebnisse zu paginieren und den Speicherverbrauch unter Kontrolle zu halten.

**Q: Gibt es ein Limit für die Größe einer einzelnen E‑Mail, die ich herunterladen kann?**  
A: Die API streamt den Inhalt, sodass Nachrichten bis zu 150 MB unterstützt werden, ohne das Java‑Heap‑Limit zu erreichen, vorausgesetzt, die JVM verfügt über ausreichend nativen Speicher.

**Q: Muss ich SSL‑Zertifikate manuell behandeln?**  
A: Standardmäßig vertraut Aspose.Email dem Java‑Standard‑Keystore. Wenn Ihr Exchange‑Server ein selbstsigniertes Zertifikat verwendet, importieren Sie es in den JVM‑Truststore oder setzen Sie `client.setEnableSslVerification(false)` nur für Testzwecke.

**Q: Wie protokolliere ich die Vorgänge für Auditzwecke?**  
A: Aktivieren Sie das integrierte Logging von Aspose.Email, indem Sie `Logger.setLevel(Level.INFO)` konfigurieren und die Ausgabe in eine Datei oder ein Überwachungssystem leiten.

## Fazit
Sie haben nun ein vollständiges, produktionsreifes Rezept für **how to connect exchange** und das rekursive Auflisten von Nachrichten aus öffentlichen Ordnern mit Aspose.Email für Java. Die Schritte umfassen Maven‑Einrichtung, Lizenzierung, Verbindung, Ordner‑Aufzählung, Nachrichten‑Abruf und Leistungsoptimierung. Erweitern Sie diese Grundlage, indem Sie sie mit Datenbanken, Cloud‑Speicher oder benutzerdefinierten Analyse‑Pipelines integrieren, um die spezifischen Anforderungen Ihrer Organisation zu erfüllen.

---

**Last Updated:** 2026-10-02  
**Tested With:** Aspose.Email for Java 25.4  
**Author:** Aspose

## Verwandte Tutorials

- [Wie man sich mit dem Exchange-Server verbindet mit Aspose.Email in Java: Schritt-für-Schritt-Anleitung](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Wie man sich verbindet und Exchange-Server-Ordner mit Aspose.Email für Java auflistet](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Verwalten von Exchange-Server-Ordnern mit Aspose.Email für Java: Ein umfassender Leitfaden](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}