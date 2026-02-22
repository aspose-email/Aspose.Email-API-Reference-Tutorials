---
date: '2026-02-22'
description: Erfahren Sie, wie Sie in Outlook mithilfe von Aspose.Email für Java ein
  Follow‑Up‑Flag setzen, einschließlich des Setzens, Lesens und Entfernens von Flags
  für Empfänger.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Wie man das Outlook‑Folgevermerk‑Flag mit Aspose.Email für Java setzt
url: /de/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Outlook Follow‑Up‑Flag mit Aspose.Email für Java setzt

## Einführung
Wenn Sie jemals Schwierigkeiten hatten, wichtige E‑Mails im Auge zu behalten, wissen Sie, wie wertvoll das **Outlook Follow‑Up‑Flag** ist. In diesem Leitfaden zeigen wir, **wie man ein Outlook Follow‑Up‑Flag** programmgesteuert mit Aspose.Email für Java setzt, und behandeln außerdem, wie man **ein Outlook Follow‑Up‑Flag für Empfänger setzt**, sowie wie man **ein Outlook Follow‑Up‑Flag entfernt**, wenn eine Aufgabe abgeschlossen ist. Am Ende können Sie die Aufgabenverfolgung, Erinnerungen und Prüfpfade direkt aus Ihrem Java‑Code automatisieren.

**Was Sie lernen werden**
- Ein Follow‑Up‑Flag auf einer Outlook‑Nachricht erstellen und anwenden.  
- Follow‑Up‑Flags für bestimmte Empfänger setzen.  
- Ein Flag als erledigt markieren und später entfernen.  
- Flag‑Optionen für Berichte oder Compliance auslesen.  

Lassen Sie uns die Umgebung vorbereiten, bevor wir in den Code eintauchen.

## Schnelle Antworten
- **Was bedeutet „how to set follow‑up“?** Ein Flag mit Start‑, Erinnerungs‑ und Fälligkeitsdatum zu einem Outlook‑Element hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Email für Java (v25.4 oder neuer).  
- **Benötige ich eine Lizenz?** Ja, für die volle Funktionalität ist eine Test‑ oder Kauf‑Lizenz erforderlich.  
- **Kann ich Flags nur für Empfänger setzen?** Absolut – verwenden Sie `FollowUpManager.setFlagForRecipients`.  
- **Ist es möglich, ein Flag später zu entfernen?** Ja, rufen Sie `FollowUpManager.clearFlag` auf.

## Was ist ein Outlook Follow‑Up‑Flag?
Ein Outlook Follow‑Up‑Flag ist ein integrierter Aufgabenmarker, der einem Mail‑Element ein Startdatum, eine Erinnerung und ein Fälligkeitsdatum zuweisen kann. Es verwandelt eine reguläre E‑Mail in ein nachverfolgtes Aktionselement und hilft Ihnen und Ihrem Team, ausstehende Arbeiten im Blick zu behalten.

## Warum Aspose.Email für Java verwenden?
Aspose.Email bietet eine reine Java‑API, die ohne installierte Outlook‑Installation funktioniert und Ihnen ermöglicht, .msg‑Dateien zu manipulieren, Flags zu setzen und Aufgaben auf jeder Plattform zu verwalten – ideal zum **automatisieren von Outlook‑Aufgaben**, für Backend‑Dienste oder die Integration in Projekt‑Management‑Tools.

## Voraussetzungen
- **Aspose.Email für Java** Version 25.4 oder höher (auch bekannt als **aspose email java**).  
- **JDK 16+** installiert.  
- Maven‑kompatible IDE (IntelliJ IDEA, Eclipse usw.).  
- Grundkenntnisse in Java und Vertrautheit mit E‑Mail‑Konzepten.

## Einrichtung von Aspose.Email für Java
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
Aspose.Email erfordert eine Lizenz für die Produktion:

- **Kostenlose Testversion** – 30‑Tage‑Bewertung.  
- **Temporäre Lizenz** – erweiterte Tests.  
- **Vollständige Lizenz** – unbefristetes Abonnement.

Initialisieren Sie die Lizenz vor jeder E‑Mail‑Operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook Follow‑Up‑Flag setzen (Feature 1)
### Schritt 1: Nachricht erstellen und initialisieren
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Zuerst erstellen wir ein `MailMessage`, setzen Absender/Empfänger und konvertieren es dann zu einem `MapiMessage` für die Flag‑Manipulation.*

### Schritt 2: Follow‑Up‑Daten festlegen (Outlook‑Flag‑Erinnerung)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier setzen wir das Start‑, Erinnerungs‑ (die **Outlook‑Flag‑Erinnerung**) und Fälligkeitsdatum mit der `Calendar`‑Klasse.*

### Schritt 3: Follow‑Up‑Optionen anwenden
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Das Objekt `FollowUpOptions` enthält alle Flag‑Details, die wir mit `FollowUpManager.setOptions` anwenden.*

### Schritt 4: Nachricht speichern
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Die Nachricht wird als `.msg`‑Datei mit angehängtem Flag gespeichert.*

## Flag für Empfänger setzen (Feature 2)
### Überblick
Manchmal muss das Flag **nur für Empfänger** sichtbar sein. Dieses Beispiel markiert die Nachricht zuerst als Entwurf und fügt dann das Flag hinzu.

#### Schritt 1: Als Entwurf markieren
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Durch das Markieren der Nachricht als nicht gesendet behandelt Outlook sie als Entwurf.*

#### Schritt 2: Empfänger‑Flag setzen
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Das Flag ist jetzt nur für die Empfänger sichtbar – ein klassisches **Flag‑für‑Empfänger**‑Szenario.*

## Outlook Follow‑Up‑Flag als erledigt markieren (Feature 3)
### Schritt 1: Nachricht laden
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Schritt 2: Als erledigt markieren und speichern
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Der Flag‑Status ändert sich zu „Completed“ und die aktualisierte Datei wird gespeichert.*

## Outlook Follow‑Up‑Flag entfernen (Feature 4)
### Schritt 1: Laden und Flag löschen
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Die Nachricht wird ohne ein Follow‑Up‑Flag gespeichert.*

## Flag‑Optionen auslesen (Feature 5)
### Schritt 1: Optionen abrufen
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Das Objekt `options` enthält nun Start‑, Fälligkeits‑ und Erinnerungsdaten sowie den Flag‑Betreff – nützlich, wenn Sie **Flag‑Optionen auslesen** für Berichte benötigen.*

## Praktische Anwendungen
- **Task‑Management‑Integration:** Markierte E‑Mails mit Jira, Trello oder Azure Boards synchronisieren.  
- **Automatisierte Erinnerungen:** Tägliche Erinnerungs‑E‑Mails für ausstehende Follow‑Ups generieren.  
- **Compliance‑Audits:** Flag‑Daten für regulatorische Berichte exportieren.

## Leistungsüberlegungen
- **Datumsberechnungen:** Daten einmal pro Stapel berechnen statt in Schleifen.  
- **Ressourcenverwaltung:** Nach dem Speichern von Nachrichten alle Streams oder Dateihandles schließen.  
- **Speichernutzung:** Große Postfächer in Teilen verarbeiten, um Heap‑Druck zu vermeiden.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| Flag wird in Outlook nicht angezeigt | Nachricht ohne korrekte `MessageFlags` gespeichert | Stellen Sie sicher, dass `setMessageFlags` vor dem Anwenden von Empfänger‑Flags auf `MSGFLAG_UNSENT` gesetzt ist. |
| Speichern wirft `AccessDeniedException` | Falscher Dateipfad oder fehlende Schreibberechtigungen | Überprüfen Sie, ob das Ausgabeverzeichnis existiert und die Anwendung Schreibrechte hat. |
| Daten sind um einen Tag verschoben | Zeitzonen‑Fehlanpassung | Verwenden Sie konsequent `TimeZone.getTimeZone("GMT")` oder Ihre lokale Zone. |

## Häufig gestellte Fragen
**F: Was ist Aspose.Email für Java?**  
A: Es ist eine reine Java‑API, mit der Sie E‑Mail‑Dateien (MSG, EML usw.) erstellen, lesen und manipulieren können, ohne Outlook zu installieren.

**F: Wie erhalte ich eine kostenlose Testlizenz?**  
A: Besuchen Sie die [Aspose-Website](https://releases.aspose.com/email/java/), um eine 30‑Tage‑Testversion herunterzuladen.

**F: Kann ich mehrere Follow‑Up‑Flags auf einer einzelnen Nachricht setzen?**  
A: Outlook unterstützt nur ein Flag pro Nachricht, aber Sie können zusätzliche Aufgabendaten in benutzerdefinierten MAPI‑Eigenschaften speichern.

**F: Meine Nachricht wird nach dem Setzen eines Flags nicht gespeichert. Was sollte ich prüfen?**  
A: Stellen Sie sicher, dass der Pfad `outputDir` gültig ist und die Anwendung Schreibrechte für diesen Ort hat.

**F: Wie kann ich Flags aus vielen Nachrichten gleichzeitig entfernen?**  
A: Durchlaufen Sie Ihre Nachrichtensammlung und rufen Sie `FollowUpManager.clearFlag` für jedes `MapiMessage` auf.

## Ressourcen
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Zuletzt aktualisiert:** 2026-02-22  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}