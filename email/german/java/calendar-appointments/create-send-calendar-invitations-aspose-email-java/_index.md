---
date: '2026-03-20'
description: Erfahren Sie, wie Sie eine Kalenderfreigabe‑Einladung erstellen, Kalenderberechtigungen
  konfigurieren und Delegiertenzugriff mit Aspose.Email für Java festlegen.
keywords:
- Aspose.Email for Java
- create calendar invitations
- send calendar invitations
title: Kalenderfreigabe‑Einladung mit Aspose.Email für Java erstellen
url: /de/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kalenderfreigabe verwalten: Aspose.Email für Java‑Leitfaden

## Einführung in die Verwaltung von Kalenderfreigaben
Die Verwaltung von Kalenderfreigabe‑Einladungen kann eine komplexe Aufgabe sein, insbesondere wenn mehrere Benutzer über verschiedene Plattformen hinweg beteiligt sind. In diesem Tutorial werden Sie **calendar sharing invitation** mit Aspose.Email für Java **erstellen**, wobei alles von der Erstellung des Delegiertenzugriffs bis zum Senden von Kalenderfreigabe‑E‑Mails abgedeckt wird. Am Ende können Sie Delegiertenberechtigungen festlegen, **configure calendar permissions** und die Zusammenarbeit in Ihrer Organisation optimieren.

**Was Sie lernen werden**
- Wie man den EWS‑Client mit Aspose.Email für Java initialisiert  
- Erstellen eines Delegiertenbenutzers und **set delegate permissions**  
- **Create delegate access** und configure calendar permissions  
- Senden einer **calendar sharing email** (Einladung) programmgesteuert  
- Praxisbeispiele, in denen diese Funktionen Mehrwert bieten  

Bevor wir beginnen, stellen Sie sicher, dass Sie alles haben, was Sie benötigen.

## Schnelle Antworten
- **Was ist der Hauptzweck dieses Leitfadens?** Um zu zeigen, wie man **create calendar sharing invitation** mit Aspose.Email für Java **erstellt**.  
- **Welche Bibliotheksversion ist erforderlich?** Aspose.Email for Java 25.4 (JDK 16 classifier).  
- **Benötige ich eine Lizenz?** Ja – ein Test- oder Volllizenz ist für den Produktionseinsatz erforderlich.  
- **Welche Umgebung wird benötigt?** JDK 16+, Maven und ein Exchange‑Online‑Konto.  
- **Kann ich dies mit anderen Exchange‑Servern verwenden?** Ja, aber Sie müssen möglicherweise die Service‑URL und die Berechtigungsebenen anpassen.

## Was ist eine calendar sharing invitation?
Eine calendar sharing invitation ist eine E‑Mail‑Nachricht, die einem anderen Benutzer Zugriff gewährt, Ihren Kalender anzusehen (oder zu bearbeiten), ohne vollständige Postfachrechte zu vergeben. Sie wird häufig für Teamkoordination, Projektplanung und Veranstaltungsmanagement verwendet.

## Warum calendar permissions konfigurieren?
Durch das Konfigurieren von calendar permissions können Sie genau steuern, was ein Delegierter tun darf – ob er nur Ereignisse lesen, neue vorschlagen oder vorhandene Einträge bearbeiten kann. Richtige Berechtigungseinstellungen schützen sensible Informationen und ermöglichen gleichzeitig eine effektive Zusammenarbeit.

## Voraussetzungen
- **Java Development Kit (JDK):** Version 16 oder höher.  
- **Maven:** Für das Verwalten von Abhängigkeiten und das Erstellen des Projekts.  
- **Aspose.Email for Java Bibliothek:** Version 25.4 mit JDK 16‑Unterstützung.  

### Umgebungs‑Setup‑Anforderungen
1. Installieren Sie das JDK, falls Sie es noch nicht getan haben. Sie können es von [Oracle's official site](https://www.oracle.com/java/technologies/javase-downloads.html) herunterladen.  
2. Stellen Sie sicher, dass Maven auf Ihrem Rechner installiert und konfiguriert ist.  
3. Wählen Sie eine IDE wie IntelliJ IDEA oder Eclipse für eine einfachere Entwicklung.

### Kenntnis‑Voraussetzungen
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
Aspose.Email for Java erfordert eine Lizenz für die volle Funktionalität. Sie können:
- **Kostenlose Testversion:** Download von [Aspose's release page](https://releases.aspose.com/email/java/).  
- **Temporäre Lizenz:** Fordern Sie einen temporären Schlüssel auf der Aspose‑Website an.  
- **Kauf:** Erhalten Sie eine permanente Lizenz für Produktionsbereitstellungen.

### Grundlegende Initialisierung und Einrichtung
Sobald Maven die Abhängigkeit aufgelöst hat, initialisieren Sie den EWS‑Client:

```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

## Wie man eine calendar sharing invitation erstellt
Im Folgenden behandeln wir zwei Kernfunktionen: das Erstellen und Senden einer calendar sharing invitation sowie das **set delegate permissions** für den Kalenderzugriff.

### Funktion 1: calendar sharing invitation erstellen und senden
#### Übersicht
Diese Funktion führt Sie durch die Initialisierung des Clients, **create delegate access**, und das Senden der Einladungs‑E‑Mail.

#### Schritt‑für‑Schritt‑Implementierung
##### 1️⃣ Initialize EWS Client
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```
Dies verbindet Ihre Java‑Anwendung mit Exchange Online.

##### 2️⃣ Create Delegate User
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);
client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Hier **create delegate access** und weisen das `Reviewer`‑Level zu, das dem Delegierten das Anzeigen von Kalendereinträgen ermöglicht.

##### 3️⃣ Send Calendar Sharing Invitation
```java
MapiMessage mapiMessage = client.createCalendarSharingInvitationMessage("sharingfrom@domain.com");

MailConversionOptions options = new MailConversionOptions();
options.setConvertAsTnef(true);

MailMessage mail = mapiMessage.toMailMessage(options);
client.send(mail);
```
Der Code erstellt eine **calendar sharing email** (Einladung) und sendet sie über den EWS‑Client.

### Funktion 2: Delegierten‑Kalenderzugriffs‑Berechtigung
#### Übersicht
Dieser Abschnitt zeigt, wie man **configure calendar permissions** durchführt und sicherstellt, dass der Delegierte die richtigen Rechte hat.

#### Implementierungsschritte
##### 1️⃣ Initialize EWS Client (reuse)
```java
IEWSClient client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "testUser", "pwd", "domain");
```

##### 2️⃣ Create and Set Delegate Permissions
```java
ExchangeDelegateUser delegateUser = new ExchangeDelegateUser("sharingfrom@domain.com", ExchangeDelegateFolderPermissionLevel.NotSpecified);
delegateUser.getFolderPermissions().setCalendarFolderPermissionLevel(ExchangeDelegateFolderPermissionLevel.Reviewer);

client.delegateAccess(delegateUser, "sharingfrom@domain.com");
```
Dieses Snippet **sets delegate permissions**, sodass der Benutzer Kalendereinträge einsehen kann, ohne vollen Postfachzugriff zu haben.

## Wie man calendar permissions für Delegierte konfiguriert
Wenn ein Delegierter mehr als nur Ereignisse anzeigen soll – z. B. bearbeiten oder löschen – können Sie das `ExchangeDelegateFolderPermissionLevel` ändern:

- `Reviewer` – Nur‑Lese‑Zugriff.  
- `Editor` – Lese‑/Schreib‑Zugriff.  
- `Author` – Erstellen und Lesen, aber kein Löschen.  
- `Owner` – Vollständige Kontrolle, einschließlich Änderungen der Berechtigungen.

**Pro‑Tipp:** Verwenden Sie das geringste Privilegien‑Level, das die geschäftlichen Anforderungen erfüllt, um Ihre Kalenderdaten zu sichern.

## Praktische Anwendungen
Praxisbeispiele, bei denen **manage calendar sharing** glänzt:
1. **Corporate Meetings** – Teammitglieder können Meeting‑Pläne einsehen, ohne volle Postfachrechte zu erhalten.  
2. **Project Management** – Projektleiter können Zeitpläne überwachen, während Entwickler die Kontrolle über ihre eigenen Kalender behalten.  
3. **Event Planning** – Anbieter erhalten eine **calendar sharing email**, um die Logistik zu koordinieren, ohne interne Details preiszugeben.

## Leistungsüberlegungen
- **Memory Management:** Entsorgen Sie große `MailMessage`‑Objekte zeitnah in Anwendungen mit hohem Volumen.  
- **Exception Handling:** Umschließen Sie Netzwerkaufrufe in try‑catch‑Blöcken, um Verbindungsprobleme elegant zu behandeln.  
- **Library Updates:** Halten Sie Aspose.Email aktuell, um von Leistungsverbesserungen und Fehlerbehebungen zu profitieren.

## Häufige Probleme und Lösungen
| Issue | Likely Cause | Solution |
|-------|--------------|----------|
| Invitation not received | Spam filters or incorrect email address | Verify recipient address and add the sending domain to safe‑senders list |
| Permission not applied | Using wrong `ExchangeDelegateFolderPermissionLevel` | Double‑check the permission level matches the required access |
| Runtime exception on `createCalendarSharingInvitationMessage` | Missing license or outdated library | Ensure a valid license is loaded and you’re using the latest Aspose.Email version |

| Problem | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Einladung nicht erhalten | Spam‑Filter oder falsche E‑Mail‑Adresse | Empfängeradresse prüfen und die sendende Domain zur Safe‑Senders‑Liste hinzufügen |
| Berechtigung nicht angewendet | Falsches `ExchangeDelegateFolderPermissionLevel` verwendet | Überprüfen Sie, ob das Berechtigungslevel dem erforderlichen Zugriff entspricht |
| Runtime‑Exception bei `createCalendarSharingInvitationMessage` | Fehlende Lizenz oder veraltete Bibliothek | Stellen Sie sicher, dass eine gültige Lizenz geladen ist und Sie die neueste Aspose.Email‑Version verwenden |

## Häufig gestellte Fragen
**Q: Wofür wird Aspose.Email für Java verwendet?**  
A: Es ist eine umfassende Bibliothek zur Verarbeitung von E‑Mails, Kalendern und Kontakten in Java‑Anwendungen und unterstützt Outlook, Exchange und weitere Protokolle.

**Q: Wie richte ich meine Umgebung für die Verwendung von Aspose.Email ein?**  
A: Installieren Sie JDK 16+, Maven, fügen Sie die Aspose.Email‑Abhängigkeit zu `pom.xml` hinzu und erhalten Sie eine Lizenz (Test‑ oder Vollversion).

**Q: Kann ich diesen Code mit anderen Versionen von Exchange Online verwenden?**  
A: Ja, prüfen Sie jedoch, ob die Service‑URL und die Berechtigungsebenen mit der Konfiguration Ihres Servers übereinstimmen.

**Q: Was soll ich tun, wenn die calendar sharing invitation nicht gesendet wird?**  
A: Überprüfen Sie die Netzwerkverbindung, Anmeldeinformationen und ob der Delegierte gültige Berechtigungen hat. Prüfen Sie die Ausnahmedetails für Hinweise.

**Q: Ist es möglich, zusätzliche Berechtigungen wie Bearbeiten oder Vollzugriff hinzuzufügen?**  
A: Absolut – ersetzen Sie `ExchangeDelegateFolderPermissionLevel.Reviewer` durch `Editor`, `Author` oder `Owner`, je nach Bedarf.

## Fazit
Sie haben nun eine vollständige End‑zu‑End‑Lösung für **create calendar sharing invitation** mit Aspose.Email für Java. Durch die Initialisierung des EWS‑Clients, **create delegate access**, **set delegate permissions** und das Senden einer **calendar sharing email** können Sie die Zusammenarbeit in Ihrer Organisation automatisieren.

**Nächste Schritte**
- Experimentieren Sie mit anderen Berechtigungsebenen (Editor, Owner).  
- Integrieren Sie diese Logik in Ihre bestehenden Planungs‑ oder HR‑Systeme.  
- Entdecken Sie weitere Aspose.Email‑Funktionen wie wiederkehrende Ereignisse oder Besprechungsanfragen.

---

**Zuletzt aktualisiert:** 2026-03-20  
**Getestet mit:** Aspose.Email for Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}