---
date: '2025-12-19'
description: Erfahren Sie, wie Sie Follow‑Up‑Markierungen in Outlook mit Aspose.Email
  für Java setzen, einschließlich wie Sie Outlook‑Follow‑Up‑Markierung setzen und
  effizient entfernen.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Wie man Follow-up‑Markierungen in Outlook mit Aspose.Email für Java setzt
url: /de/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Follow‑Up‑Markierungen in Outlook mit Aspose.Email für Java setzt

## Einführung
Wenn Sie jemals Schwierigkeiten hatten, wichtige E‑Mails im Blick zu behalten, wissen Sie, wie wertvoll die Follow‑Up‑Markierungen von Outlook sein können. In diesem Leitfaden zeigen wir **wie man Follow‑Up‑Markierungen** programmgesteuert mit Aspose.Email für Java setzt und behandeln außerdem, wie man **Outlook‑Follow‑Up‑Markierungen für Empfänger** setzt sowie **Outlook‑Follow‑Up‑Markierungen entfernt**, wenn eine Aufgabe abgeschlossen ist. Am Ende können Sie die Aufgabenverfolgung, Erinnerungen und Audit‑Logs direkt aus Ihrem Java‑Code automatisieren.

**Was Sie lernen werden**
- Erstellen und Anwenden einer Follow‑Up‑Markierung auf einer Outlook‑Nachricht.  
- Follow‑Up‑Markierungen für bestimmte Empfänger setzen.  
- Eine Markierung als erledigt markieren und später entfernen.  
- Markierungsoptionen auslesen für Berichte oder Compliance.  

Bereiten wir die Umgebung vor, bevor wir in den Code eintauchen.

## Schnellantworten
- **Was bedeutet „how to set follow‑up“?** Das Hinzufügen einer Markierung mit Start‑, Erinnerungs‑ und Fälligkeitsdaten zu einem Outlook‑Element.  
- **Welche Bibliothek wird benötigt?** Aspose.Email für Java (v25.4 oder neuer).  
- **Benötige ich eine Lizenz?** Ja, für die volle Funktionalität ist eine Test‑ oder Kauf‑Lizenz erforderlich.  
- **Kann ich Markierungen nur für Empfänger setzen?** Absolut – verwenden Sie `FollowUpManager.setFlagForRecipients`.  
- **Ist es möglich, eine Markierung später zu entfernen?** Ja, rufen Sie `FollowUpManager.clearFlag` auf.

## Was ist eine Follow‑Up‑Markierung?
Eine Follow‑Up‑Markierung ist ein Outlook‑Feature, das eine E‑Mail als Aufgabe kennzeichnet und optional Start‑, Erinnerungs‑ und Fälligkeitsdaten anhängt. Sie hilft Ihnen und Ihrem Team, ausstehende Aktionen im Blick zu behalten.

## Warum Aspose.Email für Java verwenden?
Aspose.Email bietet eine reine Java‑API, die ohne installierte Outlook‑Instanz funktioniert und Ihnen ermöglicht, .msg‑Dateien zu manipulieren, Markierungen zu setzen und Aufgaben auf jeder Plattform zu verwalten – ideal für Backend‑Dienste, automatisierte Workflows oder die Integration mit Projekt‑Management‑Tools.

## Voraussetzungen
- **Aspose.Email für Java** Version 25.4 oder höher.  
- **JDK 16+** installiert.  
- Maven‑kompatible IDE (IntelliJ IDEA, Eclipse usw.).  
- Grundkenntnisse in Java und Vertrautheit mit E‑Mail‑Konzepten.

## Aspose.Email für Java einrichten
### Maven‑Konfiguration
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung
Aspose.Email erfordert für den Produktionseinsatz eine Lizenz:

- **Kostenlose Testversion** – 30‑tägige Evaluierung.  
- **Temporäre Lizenz** – erweiterte Tests.  
- **Vollständige Lizenz** – unbefristetes Abonnement.

Initialisieren Sie die Lizenz vor jeder E‑Mail‑Operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementierungs‑Leitfaden

### Wie man Follow‑Up‑Markierungen setzt (Feature 1)
#### Überblick
Dieser Abschnitt führt Sie durch das Erstellen einer Outlook‑Nachricht, das Definieren von Start‑/Erinnerungs‑/Fälligkeitsdaten und das Anwenden einer Follow‑Up‑Markierung.

#### Schritt 1: Nachricht erstellen und initialisieren
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Zunächst bauen wir ein `MailMessage`, setzen Absender/Empfänger und konvertieren es anschließend zu einem `MapiMessage` für die Markierungs‑Manipulation.*

#### Schritt 2: Follow‑Up‑Daten festlegen
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier setzen wir Start‑, Erinnerungs‑ und Fälligkeitsdaten mithilfe der `Calendar`‑Klasse.*

#### Schritt 3: Follow‑Up‑Optionen anwenden
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Das `FollowUpOptions`‑Objekt enthält alle Markierungsdetails, die wir mit `FollowUpManager.setOptions` anwenden.*

#### Schritt 4: Nachricht speichern
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Die Nachricht wird als `.msg`‑Datei mit angehängter Markierung gespeichert.*

### Wie man Outlook‑Follow‑Up‑Markierung für Empfänger setzt (Feature 2)
#### Überblick
Manchmal muss eine Nachricht nur für die Empfänger markiert werden. Dieses Beispiel markiert die Nachricht zunächst als Entwurf und fügt dann die Markierung hinzu.

#### Schritt 1: Als Entwurf markieren
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Durch das Markieren der Nachricht als nicht gesendet stellt Outlook sicher, dass sie als Entwurf behandelt wird.*

#### Schritt 2: Empfänger‑Markierung setzen
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Die Markierung ist nun nur für die Empfänger sichtbar.*

### Wie man eine Outlook‑Follow‑Up‑Markierung als erledigt markiert (Feature 3)
#### Überblick
Wenn eine Aufgabe erledigt ist, können Sie die Markierung programmgesteuert als abgeschlossen markieren.

#### Schritt 1: Nachricht laden
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Schritt 2: Als erledigt markieren und speichern
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Der Markierungsstatus ändert sich zu „Completed“ und die aktualisierte Datei wird gespeichert.*

### Wie man Outlook‑Follow‑Up‑Markierung entfernt (Feature 4)
#### Überblick
Falls eine Markierung nicht mehr benötigt wird, können Sie sie vollständig löschen.

#### Schritt 1: Laden und Markierung löschen
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Die Nachricht wird ohne jegliche Follow‑Up‑Markierung gespeichert.*

### Wie man Follow‑Up‑Markierungsoptionen ausliest (Feature 5)
#### Überblick
Für Audits oder Berichte müssen Sie möglicherweise die bestehenden Markierungseinstellungen auslesen.

#### Schritt 1: Optionen abrufen
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Das `options`‑Objekt enthält nun Start‑, Fälligkeits‑ und Erinnerungsdaten sowie den Markierungs‑Betreff.*

## Praktische Anwendungsfälle
- **Task‑Management‑Integration:** Flagged‑E‑Mails mit Jira, Trello oder Azure Boards synchronisieren.  
- **Automatisierte Erinnerungen:** Tägliche Erinnerungs‑E‑Mails für ausstehende Follow‑Ups generieren.  
- **Compliance‑Audits:** Markierungsdaten für regulatorische Berichte exportieren.

## Leistungs‑Überlegungen
- **Datumsberechnungen:** Daten einmal pro Batch berechnen statt innerhalb von Schleifen.  
- **Ressourcen‑Management:** Streams oder Dateihandles nach dem Speichern von Nachrichten schließen.  
- **Speicherverbrauch:** Große Postfächer in Chunks verarbeiten, um Heap‑Druck zu vermeiden.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| Markierung erscheint nicht in Outlook | Nachricht ohne korrekte `MessageFlags` gespeichert | Stellen Sie sicher, dass `setMessageFlags` auf `MSGFLAG_UNSENT` gesetzt ist, bevor Empfänger‑Markierungen angewendet werden. |
| Beim Speichern wird `AccessDeniedException` geworfen | Falscher Dateipfad oder fehlende Schreibrechte | Überprüfen Sie, ob das Ausgabeverzeichnis existiert und die Anwendung Schreibrechte hat. |
| Daten sind um einen Tag verschoben | Zeitzonen‑Mismatch | Verwenden Sie konsistent `TimeZone.getTimeZone("GMT")` oder Ihre lokale Zone. |

## Häufig gestellte Fragen
**F: Was ist Aspose.Email für Java?**  
A: Es ist eine reine Java‑API, mit der Sie E‑Mail‑Dateien (MSG, EML usw.) erstellen, lesen und manipulieren können, ohne Outlook zu benötigen.

**F: Wie erhalte ich eine kostenlose Testlizenz?**  
A: Besuchen Sie die [Aspose‑Website](https://releases.aspose.com/email/java/), um eine 30‑tägige Testversion herunterzuladen.

**F: Kann ich mehrere Follow‑Up‑Markierungen auf einer Nachricht setzen?**  
A: Outlook unterstützt nur eine Markierung pro Nachricht, aber Sie können zusätzliche Aufgabendaten in benutzerdefinierten MAPI‑Eigenschaften speichern.

**F: Meine Nachricht wird nach dem Setzen einer Markierung nicht gespeichert. Was sollte ich prüfen?**  
A: Vergewissern Sie sich, dass der Pfad `outputDir` gültig ist und die Anwendung Schreibrechte für diesen Ort hat.

**F: Wie kann ich Markierungen aus vielen Nachrichten gleichzeitig entfernen?**  
A: Durchlaufen Sie Ihre Nachrichten‑Sammlung und rufen Sie `FollowUpManager.clearFlag` für jedes `MapiMessage` auf.

## Ressourcen
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Zuletzt aktualisiert:** 2025-12-19  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}