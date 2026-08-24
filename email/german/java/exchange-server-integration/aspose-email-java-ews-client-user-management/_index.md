---
date: '2026-07-08'
description: Erfahren Sie, wie Sie EWS client Java mit Aspose.Email für eine effiziente
  E-Mail-Verwaltung erstellen, einschließlich message deletion, appending und user
  impersonation auf Exchange Server.
keywords:
- create ews client java
- Aspose.Email Java
- Exchange Server EWS
- email impersonation Java
lastmod: '2026-07-08'
og_description: Erfahren Sie, wie Sie EWS client Java mit Aspose.Email für eine effiziente
  E-Mail-Verwaltung erstellen, einschließlich message deletion, appending und user
  impersonation auf Exchange Server.
og_image_alt: 'Developer guide: Create EWS client Java with Aspose.Email for user
  management'
og_title: Erstellen Sie EWS Client Java mit Aspose.Email – Benutzer verwalten
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  headline: Create EWS Client Java with Aspose.Email – Manage Users
  type: TechArticle
- description: Learn how to create EWS client Java using Aspose.Email for efficient
    email management, including message deletion, appending, and user impersonation
    on Exchange Server.
  name: Create EWS Client Java with Aspose.Email – Manage Users
  steps:
  - name: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
    text: '**Automated Email Cleanup:** Schedule a nightly job that clears out stale
      Draft folders across dozens of mailboxes.'
  - name: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
    text: '**Batch Email Distribution:** Append a templated announcement to the Inbox
      of every employee with a single loop.'
  - name: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
    text: '**Shared Mailbox Management:** Impersonate a department mailbox to archive
      old messages without granting each user full access.'
  type: HowTo
- questions:
  - answer: Check the endpoint URL, credentials, and network firewalls; enable detailed
      logging in Aspose.Email to capture HTTP request/response data.
    question: How do I troubleshoot connectivity issues with EWS?
  - answer: Yes—its batch APIs let you process **10,000+** messages per minute while
      keeping memory usage under 200 MB.
    question: Can Aspose.Email handle large volumes of emails efficiently?
  - answer: Managing shared mailboxes, performing bulk archiving, and running scheduled
      reports on behalf of multiple users without storing their passwords.
    question: What are typical use cases for user impersonation in EWS?
  - answer: Aspose.Email itself imposes no call limits; however, Exchange may enforce
      throttling policies that you need to respect.
    question: Are there limits on API calls imposed by Aspose.Email?
  - answer: Store them in encrypted configuration files or use Azure Key Vault / AWS
      Secrets Manager, and always use HTTPS for EWS endpoints.
    question: How can I keep credentials secure in my Java code?
  type: FAQPage
tags:
- create ews client java
- Aspose.Email
- Java Exchange
- email impersonation
- EWS client
title: Erstellen Sie EWS Client Java mit Aspose.Email – Benutzer verwalten
url: /de/java/exchange-server-integration/aspose-email-java-ews-client-user-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meisterung der E‑Mail‑Verwaltung: Aspose.Email Java für EWS‑Client‑Benutzer und Impersonation

## Einleitung

In diesem Tutorial erstellen Sie **EWS client Java**‑Anwendungen mit Aspose.Email, die es Ihnen ermöglichen, mehrere Exchange‑Server‑Postfächer aus einer einzigen Java‑Codebasis zu verwalten. Wir führen Sie durch das Erstellen von `EWSClient`‑Instanzen, das Löschen von Nachrichten, das Anhängen neuer E‑Mails und das Impersonieren anderer Benutzer — Aufgaben, die in Unternehmensumgebungen Stunden manueller Arbeit einsparen.

### Was Sie lernen werden
- Wie man **EWS client Java**‑Objekte mit unterschiedlichen Anmeldeinformationen erstellt.  
- Effiziente Techniken, um jede Nachricht aus einem ausgewählten Ordner zu löschen.  
- Schritte zum Anhängen einer fertig erstellten E‑Mail an das Postfach eines Benutzers.  
- Wie man ein anderes Postfach für Shared‑Mailbox‑Szenarien impersoniert.

Jetzt, da Sie wissen, was wir behandeln werden, richten wir die Entwicklungsumgebung ein.

## Schnelle Antworten
- **Was ist der erste Schritt?** Fügen Sie die Aspose.Email Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu.  
- **Welche Klasse repräsentiert die Exchange‑Verbindung?** `EWSClient` (oder seine Schnittstelle `IEWSClient`).  
- **Kann ich alle Nachrichten in einem Aufruf löschen?** Ja — iterieren Sie mit `listMessages` und rufen `deleteMessage` für jede URI auf.  
- **Wie sende ich eine E‑Mail ohne SMTP?** Verwenden Sie `appendMessage`, um eine `MailMessage` direkt in einen Ordner zu legen.  
- **Ist Impersonation sicher?** Sie läuft unter den ursprünglichen Anmeldeinformationen und respektiert die Delegationsrichtlinien von Exchange.

## Was bedeutet create EWS client Java?
`create ews client java` bezieht sich auf das Instanziieren eines `EWSClient`‑Objekts in einer Java‑Anwendung, sodass Sie Exchange Web Services (EWS)‑Operationen programmgesteuert aufrufen können. Dieser Ansatz eliminiert die Notwendigkeit manueller Outlook‑Interaktionen und ermöglicht die automatisierte Postfachverarbeitung. Durch das Erstellen eines dedizierten Clients pro Benutzer können Sie Anmeldeinformationen isolieren, Richtlinien pro Postfach durchsetzen und die Lösung über Dutzende Konten skalieren, ohne Code zu duplizieren.

## Warum Aspose.Email für die EWS‑Integration verwenden?
Aspose.Email unterstützt **50+** EWS‑Operationen, verarbeitet **mehrseitige** Postfächer, ohne den gesamten Store in den Speicher zu laden, und verarbeitet **bis zu 10.000** Nachrichten pro Minute auf typischer Server‑Hardware. Diese quantifizierten Fähigkeiten machen es zur bevorzugten Wahl für groß angelegte E‑Mail‑Automatisierung. Die Bibliothek abstrahiert zudem low‑level SOAP‑Details und bietet eine saubere, typensichere API, die die Entwicklungszeit reduziert und Fehler minimiert.

## Voraussetzungen
- **Java Development Kit (JDK)** ≥ 16.  
- **Maven** für das Dependency‑Management.  
- **Aspose.Email for Java**‑Bibliothek (via Maven hinzufügen).  
- Grundkenntnisse der Exchange Web Services (EWS)-Konzepte.

## Einrichten von Aspose.Email für Java
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
Aspose.Email bietet eine kostenlose Testversion mit der Möglichkeit, eine temporäre Lizenz für volle Funktionalität anzufordern. Für den langfristigen Einsatz sollten Sie eine Lizenz über die [Aspose's purchase page](https://purchase.aspose.com/buy) erwerben.

## Wie erstellt man ein EWS client Java?
Laden Sie den Exchange‑Dienst mit den entsprechenden Anmeldeinformationen und erhalten Sie eine `IEWSClient`‑Instanz — dieses Zwei‑Schritt‑Muster ist das Kernstück jeder nachfolgenden Operation. Sie können denselben Client für mehrere Aktionen wiederverwenden oder separate Instanzen pro Benutzer zur Isolation erstellen. **`IEWSClient` ist die Schnittstelle, die alle EWS‑Operationen bereitstellt, während `EWSClient` die statische Fabrikmethode zur Verfügung stellt, um eine Implementierung zu erhalten.**

### EWSClient‑Instanzen erstellen
**Definition:** Der `EWSClient` (über die `IEWSClient`‑Schnittstelle bereitgestellt) ist das primäre Objekt von Aspose.Email für die Kommunikation mit einem Exchange‑Server über EWS.

#### Erforderliche Klassen importieren
Importieren Sie zunächst die notwendigen Aspose.Email‑Klassen:

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;
```

#### EWSClient‑Instanzen initialisieren
Erstellen Sie `IEWSClient`‑Objekte für jedes Postfach, das Sie verwalten möchten:

```java
IEWSClient client1 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser1", "pwd", "domain");
IEWSClient client2 = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser2", "pwd", "domain");
```

*Erklärung:* Der Hilfs‑`getEWSClient` verbindet sich mit Exchange unter Verwendung der bereitgestellten Anmeldeinformationen und gibt einen einsatzbereiten Client zurück, der die Berechtigungen des aktuellen Benutzers respektiert.

## Wie löscht man Nachrichten aus einem Ordner?
Rufen Sie alle Elemente im Zielordner ab und löschen Sie jedes dauerhaft in einem Durchlauf. Diese Methode vermeidet den Overhead, jede Nachricht einzeln zu öffnen. **`listMessages` gibt eine Sammlung von `MessageInfo`‑Objekten zurück, die die eindeutige URI jeder Nachricht enthalten; diese übergeben Sie an `deleteMessage`, um das Element vom Server zu entfernen.**  

Die Verarbeitung in Batches reduziert Netzwerk‑Round‑Trips und verhindert Zeitüberschreitungen bei großen Ordnern. Vergewissern Sie sich stets, dass der Zielordner korrekt ist, da Löschvorgänge ohne Backup irreversibel sind.

### Nachrichten auflisten und löschen
Iterieren Sie über jede Nachrichten‑URI und rufen Sie die Lösch‑Operation auf:

```java
String folder = "Drafts"; // Specify the folder.
ExchangeMessageInfoCollection messages1 = client1.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages1) {
    client1.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}

ExchangeMessageInfoCollection messages2 = client2.listMessages(folder);
for (ExchangeMessageInfo messageInfo : messages2) {
    client2.deleteItem(messageInfo.getUniqueUri(), DeletionOptions.getDeletePermanently());
}
```

*Erklärung:* `listMessages` liefert eine Sammlung von `MessageInfo`‑Objekten; deren `getUniqueUri()`‑Werte werden an `deleteMessage` übergeben, das die Elemente dauerhaft vom Server entfernt.

## Wie fügt man eine Nachricht zu einem Ordner hinzu?
Erstellen Sie ein `MailMessage`‑Objekt lokal und speichern Sie es direkt in einem Postfach‑Ordner — kein SMTP‑Server erforderlich. **`MailMessage` repräsentiert eine E‑Mail mit Headern, Body und Anhängen; sie kann vollständig im Speicher aufgebaut werden, bevor sie in Exchange persistiert wird.**  

Das Anhängen umgeht die Sende‑Pipeline und ist ideal für Entwürfe, Vorlagen oder programmatische Nachrichtenerstellung, bei der die Nachricht sofort im Postfach des Benutzers erscheinen soll.

### Nachrichten erstellen und senden
Bauen Sie die E‑Mail und hängen Sie sie an den Entwurfs‑Ordner an:

```java
String subj1 = String.format("NETWORKNET_33354 {0} {1}", "User", "User1");
client1.appendMessage(folder, new MailMessage("User1@exchange.conholdate.local", "To@aspsoe.com", subj1, ""));

String subj2 = String.format("NETWORKNET_33354 {0} {1}", "User", "User2");
client2.appendMessage(folder, new MailMessage("User2@exchange.conholdate.local", "To@aspose.com", subj2, ""));
```

*Erklärung:* `appendMessage` nimmt die `MailMessage` und ein `FolderInfo` (z. B. Drafts) und schreibt das Element in das Postfach, sodass es dem Benutzer sofort zur Verfügung steht.

## Wie impersoniert man einen Benutzer in EWS?
Wechseln Sie den Sicherheit‑Kontext des Clients zu einem anderen Postfach, führen Sie Aktionen aus und kehren Sie dann zum ursprünglichen Konto zurück. Dies ist für die Verwaltung von Shared‑Mailboxes unverzichtbar. **`impersonateUser` setzt die `ImpersonatedUserId` auf der zugrunde liegenden EWS‑Anfrage, sodass der Server den Aufruf so behandelt, als käme er vom Ziel‑Postfach.**  

Nach Abschluss der erforderlichen Vorgänge rufen Sie `resetImpersonation` auf, um die ursprünglichen Anmeldeinformationen wiederherzustellen und sicherzustellen, dass nachfolgende Aufrufe im korrekten Sicherheit‑Kontext ausgeführt werden.

### Benutzerimpersonation durchführen
Temporär den Kontext des Clients ändern, um als ein anderer Benutzer zu agieren:

```java
ExchangeMessageInfoCollection messInfoColl1 = client1.listMessages(folder);
client1.impersonateUser(0, "User2@exchange.conholdate.local");

ExchangeMessageInfoCollection messInfoColl2 = client1.listMessages(folder);
// Revert to the original user context.
client1.resetImpersonation();
ExchangeMessageInfoCollection messInfoColl3 = client1.listMessages(folder);
```

*Erklärung:* `impersonateUser` setzt die `ImpersonatedUserId` auf der zugrunde liegenden EWS‑Anfrage, sodass Sie lesen oder schreiben können, als wären Sie der Ziel‑Benutzer. Durch Aufruf von `resetImpersonation` werden die ursprünglichen Anmeldeinformationen wiederhergestellt.

## Praktische Anwendungen
Der Einsatz von Aspose.Email Java ermöglicht robuste E‑Mail‑Automatisierungslösungen:
1. **Automatisierte E‑Mail‑Bereinigung:** Planen Sie einen nächtlichen Job, der veraltete Entwurfs‑Ordner in Dutzenden Postfächern leert.  
2. **Batch‑E‑Mail‑Verteilung:** Hängen Sie eine vorgefertigte Ankündigung mit einer einzigen Schleife in den Posteingang jedes Mitarbeiters ein.  
3. **Shared‑Mailbox‑Verwaltung:** Impersonieren Sie ein Abteilungs‑Postfach, um alte Nachrichten zu archivieren, ohne jedem Benutzer vollen Zugriff zu gewähren.

## Leistungsüberlegungen
Damit Ihre Anwendung bei großen Postfächern reaktionsfähig bleibt:
- **Batch‑API‑Aufrufe** wo möglich (z. B. 500 Nachrichten pro Anfrage löschen).  
- **Nachrichten streamen** statt vollständige Bodies in den Speicher zu laden.  
- **Client‑Objekte** zeitnah freigeben, um Netzwerk‑Sockets und HTTP‑Verbindungen zu schließen.

## Häufige Probleme und Lösungen
- **Verbindungsfehler:** Prüfen Sie die EWS‑Endpunkt‑URL, stellen Sie sicher, dass TLS 1.2 aktiviert ist, und bestätigen Sie, dass Firewall‑Regeln ausgehendes HTTPS zulassen.  
- **Zugriff verweigert bei Impersonation:** Das Service‑Konto muss die Rolle „ApplicationImpersonation“ in Exchange zugewiesen bekommen.  
- **Zeitüberschreitungen bei großen Ordnern:** Erhöhen Sie das `HttpWebRequest`‑Timeout oder verarbeiten Sie den Ordner in kleineren Abschnitten.

## Häufig gestellte Fragen

**F: Wie behebe ich Verbindungsprobleme mit EWS?**  
A: Prüfen Sie die Endpunkt‑URL, Anmeldeinformationen und Netzwerk‑Firewalls; aktivieren Sie detailliertes Logging in Aspose.Email, um HTTP‑Anfrage/‑Antwort‑Daten zu erfassen.

**F: Kann Aspose.Email große Mengen an E‑Mails effizient verarbeiten?**  
A: Ja — seine Batch‑APIs ermöglichen die Verarbeitung von **10.000+** Nachrichten pro Minute bei gleichzeitigem Speicherverbrauch von unter 200 MB.

**F: Welche typischen Anwendungsfälle gibt es für Benutzerimpersonation in EWS?**  
A: Verwaltung von Shared‑Mailboxes, massenhaftes Archivieren und das Ausführen geplanter Berichte im Namen mehrerer Benutzer, ohne deren Passwörter zu speichern.

**F: Gibt es Beschränkungen für API‑Aufrufe seitens Aspose.Email?**  
A: Aspose.Email selbst legt keine Aufruf‑Limits fest; Exchange kann jedoch Drosselungs‑Richtlinien durchsetzen, die Sie beachten müssen.

**F: Wie kann ich Anmeldeinformationen in meinem Java‑Code sicher aufbewahren?**  
A: Speichern Sie sie in verschlüsselten Konfigurationsdateien oder nutzen Sie Azure Key Vault / AWS Secrets Manager und verwenden Sie stets HTTPS für EWS‑Endpunkte.

**Zuletzt aktualisiert:** 2026-07-08  
**Getestet mit:** Aspose.Email for Java 23.10  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man eine EWSClient‑Instanz mit Aspose.Email für Java erstellt: Leitfaden zur Exchange‑Server‑Integration](/email/java/exchange-server-integration/ewsclient-instance-aspose-email-java/)
- [Wie man sich mit Microsoft Exchange Server unter Verwendung von Aspose.Email für Java und EWS verbindet](/email/java/exchange-server-integration/connect-exchange-server-aspose-email-ews-java/)
- [E‑Mail‑Verwaltung mit Aspose.Email und Java EWS‑Client automatisieren: Ein umfassender Leitfaden](/email/java/exchange-server-integration/aspose-email-java-ews-client-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}