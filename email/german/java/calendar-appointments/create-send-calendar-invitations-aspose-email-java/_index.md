---
date: '2026-09-17'
description: Wie man eine Kalendereinladung mit Aspose.Email for Java erstellt, ermöglicht
  das Teilen von Kalendern, das Festlegen von Delegationsberechtigungen und das programmgesteuerte
  Senden von Freigabe‑E‑Mails.
keywords:
- how to create calendar invitation
- calendar sharing invitation
- Aspose.Email Java
- delegate calendar permissions
lastmod: '2026-09-17'
og_description: Wie man eine Kalendereinladung mit Aspose.Email for Java programmgesteuert
  teilt, Delegationsberechtigungen festlegt und Freigabe‑E‑Mails über Exchange Web
  Services sendet, was die Zusammenarbeit im Team verbessert.
og_image_alt: Guide showing how to create calendar invitation with Aspose.Email for
  Java
og_title: Wie man eine Kalendereinladung mit Aspose.Email for Java erstellt
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  headline: How to create calendar invitation with Aspose.Email for Java
  type: TechArticle
- description: How to create calendar invitation with Aspose.Email for Java lets you
    share calendars, set delegate permissions, and send sharing emails programmatically.
  name: How to create calendar invitation with Aspose.Email for Java
  steps:
  - name: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
    text: Install JDK if you haven't already. You can download it from [Oracle's official
      site](https://www.oracle.com/java/technologies/javase-downloads.html).
  - name: Ensure Maven is installed and configured on your machine.
    text: Ensure Maven is installed and configured on your machine.
  - name: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
    text: Choose an IDE such as IntelliJ IDEA or Eclipse for easier development.
  - name: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
    text: '**Corporate meetings** – Let team members view meeting schedules without
      giving full mailbox rights.'
  - name: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
    text: '**Project management** – Project leads can monitor timelines while developers
      retain control of their own calendars.'
  - name: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
    text: '**Event planning** – Vendors receive a **calendar sharing email** to coordinate
      logistics without exposing internal details.'
  type: HowTo
- questions:
  - answer: It’s a comprehensive library for handling emails, calendars, and contacts
      in Java applications, supporting Outlook, Exchange, and other protocols.
    question: What is Aspose.Email for Java used for?
  - answer: Install JDK 16+, Maven, add the Aspose.Email dependency to `pom.xml`,
      and obtain a license (trial or full).
    question: How do I set up my environment for using Aspose.Email?
  - answer: Yes, but verify the service URL and permission levels match your server’s
      configuration.
    question: Can I use this code with other versions of Exchange Online?
  - answer: Check network connectivity, credentials, and that the delegate user has
      valid permissions. Review exception details for clues.
    question: What should I do if the calendar sharing invitation fails to send?
  - answer: Absolutely – replace `ExchangeDelegateFolderPermissionLevel.Reviewer`
      with `Editor`, `Author`, or `Owner` as needed.
    question: Is it possible to add additional permissions like editing or full access?
  type: FAQPage
tags:
- calendar sharing
- Aspose.Email
- Java email API
- delegate permissions
- EWS client
title: Wie man eine Kalendereinladung mit Aspose.Email for Java erstellt
url: /de/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenderfreigabe verwalten: Aspose.Email für Java Anleitung

## Einführung in die Verwaltung von Kalenderfreigaben
Die Verwaltung von Kalenderfreigabe‑Einladungen kann eine komplexe Aufgabe sein, insbesondere wenn mehrere Benutzer auf verschiedenen Plattformen beteiligt sind. In diesem Tutorial erstellen Sie **Kalenderfreigabe‑Einladungen** mit Aspose.Email für Java und decken alles ab, von der Erstellung von Delegiertenzugriff bis zum Versenden von Kalenderfreigabe‑E‑Mails. Am Ende können Sie Delegiertenberechtigungen festlegen, **Kalenderberechtigungen konfigurieren** und die Zusammenarbeit in Ihrer Organisation optimieren.

**Was Sie lernen werden**
- Wie der EWS‑Client mit Aspose.Email für Java initialisiert wird  
- Einen Delegierten‑Benutzer erstellen und **Delegierten‑Berechtigungen festlegen**  
- **Delegiertenzugriff erstellen** und Kalenderberechtigungen konfigurieren  
- Programmgesteuert eine **Kalenderfreigabe‑E‑Mail** (Einladung) senden  
- Praxisnahe Szenarien, in denen diese Funktionen Mehrwert bieten  

Bevor wir beginnen, stellen Sie sicher, dass Sie alles Notwendige bereit haben.

## Schnellantworten
- **Was ist das Hauptziel dieses Leitfadens?** Zu zeigen, wie man **Kalenderfreigabe‑Einladungen** mit Aspose.Email für Java **erstellt**.  
- **Welche Bibliotheksversion wird benötigt?** Aspose.Email für Java 25.4 (JDK 16 classifier).  
- **Benötige ich eine Lizenz?** Ja – für den Produktionseinsatz ist eine Test‑ oder Voll‑Lizenz erforderlich.  
- **Welche Umgebung wird benötigt?** JDK 16+, Maven und ein Exchange‑Online‑Konto.  
- **Kann ich das mit anderen Exchange‑Servern verwenden?** Ja, eventuell müssen Sie die Service‑URL und die Berechtigungsstufen anpassen.

## Was ist eine Kalenderfreigabe‑Einladung?
Eine Kalenderfreigabe‑Einladung ist eine E‑Mail‑Nachricht, die einem anderen Benutzer Zugriff gewährt, Ihren Kalender anzusehen (oder zu bearbeiten), ohne ihm vollständige Postfachrechte zu geben. Sie ermöglicht Teammitgliedern, Ihren Zeitplan zu sehen, Besprechungen vorzuschlagen oder Ereignisse zu verwalten, während Ihr Postfach geschützt bleibt.

## Warum Kalenderberechtigungen konfigurieren?
Durch das Konfigurieren von Kalenderberechtigungen können Sie genau steuern, was ein Delegierter tun darf – ob er nur Ereignisse lesen, neue vorschlagen oder bestehende Einträge bearbeiten kann. Richtige Berechtigungseinstellungen schützen sensible Informationen und ermöglichen gleichzeitig effektive Zusammenarbeit. Beispielsweise verhindert ein Nur‑Lese‑Zugriff versehentliche Änderungen, während Bearbeitungsrechte dem Delegierten erlauben, im Namen des Besitzers Besprechungen zu planen oder zu ändern.

## Voraussetzungen
- **Java Development Kit (JDK):** Version 16 oder höher.  
- **Maven:** Für das Abhängigkeits‑Management und den Build des Projekts.  
- **Aspose.Email für Java Bibliothek:** Version 25.4 mit JDK 16‑Unterstützung.  

### Anforderungen an die Umgebung
1. Installieren Sie das JDK, falls noch nicht geschehen. Sie können es von der [offiziellen Oracle‑Seite](https://www.oracle.com/java/technologies/javase-downloads.html) herunterladen.  
2. Stellen Sie sicher, dass Maven auf Ihrem Rechner installiert und konfiguriert ist.  
3. Wählen Sie eine IDE wie IntelliJ IDEA oder Eclipse für eine einfachere Entwicklung.

### Fachliche Voraussetzungen
- Grundlegende Java‑Programmierkenntnisse  
- Vertrautheit mit Maven‑Abhängigkeiten  
- Optional: Erfahrung mit Exchange Web Services (EWS)

## Einrichtung von Aspose.Email für Java
### Maven‑Konfiguration
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
Aspose.Email für Java erfordert eine Lizenz für die volle Funktionalität. Sie können:
- **Kostenlose Testversion:** Von der [Aspose‑Release‑Seite](https://releases.aspose.com/email/java/) herunterladen.  
- **Temporäre Lizenz:** Einen temporären Schlüssel auf der Aspose‑Webseite anfordern.  
- **Kauf:** Eine permanente Lizenz für Produktions‑Deployments erwerben.

### Grundlegende Initialisierung und Einrichtung
Nachdem Maven die Abhängigkeit aufgelöst hat, initialisieren Sie den EWS‑Client:

`ExchangeService` ist die Hauptklasse, die zur Kommunikation mit Exchange Web Services verwendet wird.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Wie man eine Kalenderfreigabe‑Einladung erstellt
Um eine Kalenderfreigabe‑Einladung zu erstellen, verbinden Sie sich zunächst mit Exchange über den `ExchangeService`‑Client, definieren dann einen Delegierten mit der gewünschten Berechtigungsstufe und erstellen schließlich eine `MailMessage`, die die Freigabeanforderung enthält. Die folgenden Schritte demonstrieren diesen Workflow in Java.

Im Folgenden behandeln wir zwei Kernfunktionen: das Erstellen und Senden einer Kalenderfreigabe‑Einladung sowie das **Festlegen von Delegierten‑Berechtigungen** für den Kalenderzugriff.

### Feature 1: Kalenderfreigabe‑Einladung erstellen und senden
#### Überblick
Dieses Feature führt Sie durch die Initialisierung des Clients, **Erstellung von Delegiertenzugriff** und das Senden der Einladungs‑E‑Mail.

#### Schritt‑für‑Schritt‑Implementierung
##### 1️⃣ EWS‑Client initialisieren
`ExchangeService` stellt die Verbindung zu einem Exchange‑Server dar und wird zum Senden und Empfangen von Nachrichten verwendet.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  
Damit wird Ihre Java‑Anwendung mit Exchange Online verbunden.

##### 2️⃣ Delegierten‑Benutzer erstellen
`DelegateUser` definiert die E‑Mail‑Adresse des Delegierten und die zugewiesene Berechtigungsstufe.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Hier **erstellen wir Delegiertenzugriff** und weisen die Stufe `Reviewer` zu, die dem Delegierten das Anzeigen von Kalenderelementen erlaubt.

##### 3️⃣ Kalenderfreigabe‑Einladung senden
`MailMessage` erstellt die E‑Mail, die die Kalenderfreigabe‑Einladung enthält.  

```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```  
Der Code baut eine **Kalenderfreigabe‑E‑Mail** (Einladung) und sendet sie über den EWS‑Client.

### Feature 2: Delegierten‑Kalenderzugriffs‑Berechtigung
#### Überblick
Dieser Abschnitt zeigt, wie **Kalenderberechtigungen konfiguriert** werden und der Delegierte die richtigen Rechte erhält.

#### Implementierungsschritte
##### 1️⃣ EWS‑Client initialisieren (Wiederverwendung)
`ExchangeService` kann nach der Erstkonfiguration für mehrere Vorgänge wiederverwendet werden.  

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```  

##### 2️⃣ Delegierten‑Berechtigungen erstellen und festlegen
`ExchangeDelegateFolderPermissionLevel` enumeriert die Zugriffsebenen, die ein Delegierter auf einen Kalenderordner haben kann.  

```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```  
Dieses Snippet **setzt Delegierten‑Berechtigungen**, sodass der Benutzer Kalender‑Einträge sehen kann, ohne vollen Postfachzugriff zu besitzen.

## Wie man Kalenderberechtigungen für Delegierte konfiguriert
Wenn ein Delegierter mehr als nur Lese‑Zugriff benötigt, können Sie `ExchangeDelegateFolderPermissionLevel` anpassen, um Bearbeitungs‑, Autor‑ oder Eigentümer‑Rechte zu gewähren. Wählen Sie die minimale Stufe, die den geschäftlichen Bedarf deckt, um Sicherheit zu wahren und gleichzeitig notwendige Funktionalität bereitzustellen. Beispielsweise erlaubt die Stufe `Editor` dem Delegierten das Erstellen, Ändern und Löschen von Ereignissen, während `Reviewer` nur das Anzeigen gestattet.

- `Reviewer` – Nur‑Lese‑Zugriff.  
- `Editor` – Lese‑/Schreib‑Zugriff.  
- `Author` – Erstellen und Lesen, aber kein Löschen.  
- `Owner` – Vollständige Kontrolle, einschließlich Änderungen der Berechtigungen.  

**Pro‑Tipp:** Verwenden Sie das Prinzip der geringsten Rechte, das den geschäftlichen Anforderungen entspricht, um Ihre Kalenderdaten zu schützen.

## Praktische Anwendungsfälle
Reale Szenarien, in denen **Kalenderfreigabe verwalten** glänzt:
1. **Unternehmens‑Meetings** – Teammitglieder können Meeting‑Pläne einsehen, ohne volle Postfachrechte zu erhalten.  
2. **Projektmanagement** – Projektleiter können Zeitpläne überwachen, während Entwickler ihre eigenen Kalender behalten.  
3. **Event‑Planung** – Anbieter erhalten eine **Kalenderfreigabe‑E‑Mail**, um die Logistik zu koordinieren, ohne interne Details preiszugeben.

## Leistungsaspekte
- **Speicherverwaltung:** Große `MailMessage`‑Objekte in hochvolumigen Anwendungen zeitnah freigeben.  
- **Fehlerbehandlung:** Netzwerkaufrufe in try‑catch‑Blöcken kapseln, um Verbindungsprobleme elegant zu behandeln.  
- **Bibliotheks‑Updates:** Aspose.Email für Java unterstützt über 50 Protokolle und kann Kalender mit bis zu 10.000 Elementen verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Halten Sie die Bibliothek aktuell, um Leistungsverbesserungen und Fehlerbehebungen zu nutzen.

## Häufige Probleme und Lösungen
| Problem | Wahrscheinliche Ursache | Lösung |
|-------|--------------|----------|
| Einladung nicht erhalten | Spam‑Filter oder falsche E‑Mail‑Adresse | Empfängeradresse prüfen und die sendende Domain zur Liste sicherer Absender hinzufügen |
| Berechtigung nicht angewendet | Falsche `ExchangeDelegateFolderPermissionLevel` verwendet | Sicherstellen, dass die Berechtigungsstufe dem gewünschten Zugriff entspricht |
| Laufzeit‑Exception bei `createCalendarSharingInvitationMessage` | Fehlende Lizenz oder veraltete Bibliothek | Gültige Lizenz laden und die neueste Aspose.Email‑Version verwenden |

## Häufig gestellte Fragen
**F: Wofür wird Aspose.Email für Java verwendet?**  
A: Es ist eine umfassende Bibliothek zum Verarbeiten von E‑Mails, Kalendern und Kontakten in Java‑Anwendungen und unterstützt Outlook, Exchange und weitere Protokolle.

**F: Wie richte ich meine Umgebung für die Nutzung von Aspose.Email ein?**  
A: Installieren Sie JDK 16+, Maven, fügen Sie die Aspose.Email‑Abhängigkeit zu `pom.xml` hinzu und beschaffen Sie eine Lizenz (Test‑ oder Voll‑Lizenz).

**F: Kann ich diesen Code mit anderen Versionen von Exchange Online verwenden?**  
A: Ja, prüfen Sie jedoch, ob Service‑URL und Berechtigungsstufen zu Ihrer Server‑Konfiguration passen.

**F: Was tun, wenn das Senden der Kalenderfreigabe‑Einladung fehlschlägt?**  
A: Netzwerkverbindung, Anmeldedaten und die gültigen Berechtigungen des Delegierten prüfen. Ausnahme‑Details für Hinweise analysieren.

**F: Ist es möglich, zusätzliche Berechtigungen wie Bearbeiten oder Vollzugriff hinzuzufügen?**  
A: Absolut – ersetzen Sie `ExchangeDelegateFolderPermissionLevel.Reviewer` durch `Editor`, `Author` oder `Owner` nach Bedarf.

## Fazit
Sie verfügen nun über eine vollständige End‑zu‑End‑Lösung zum **Erstellen von Kalenderfreigabe‑Einladungen** mit Aspose.Email für Java. Durch die Initialisierung des EWS‑Clients, **Erstellung von Delegiertenzugriff**, **Festlegung von Delegierten‑Berechtigungen** und das Senden einer **Kalenderfreigabe‑E‑Mail** können Sie die Zusammenarbeit in Ihrer Organisation automatisieren.

**Nächste Schritte**
- Mit anderen Berechtigungsstufen experimentieren (Editor, Owner).  
- Diese Logik in bestehende Termin‑ oder HR‑Systeme integrieren.  
- Weitere Aspose.Email‑Funktionen wie wiederkehrende Ereignisse oder Besprechungsanfragen erkunden.

---

**Zuletzt aktualisiert:** 2026-09-17  
**Getestet mit:** Aspose.Email für Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Create Calendar Item Java Using Aspose.Email](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose Email Java Filter Exchange Appointments By Date](/email/java/calendar-appointments/aspose-email-java-filter-exchange-appointments-by-date/)
- [Create Exchange Calendar Java with Aspose.Email – A Complete Guide](/email/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}