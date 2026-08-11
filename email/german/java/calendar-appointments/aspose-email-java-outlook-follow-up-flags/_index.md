---
date: '2026-07-27'
description: Erfahren Sie, wie Sie mit Aspose.Email für Java Outlook-Flag setzen,
  einschließlich Flag-Erstellung, Empfänger‑Flags, Abschluss, Entfernung und Leseoptionen.
keywords:
- set outlook flag java
- outlook follow up flag java
- aspose email java
lastmod: '2026-07-27'
og_description: Setzen Sie Outlook-Flag in Java mit Aspose.Email für Java. Dieser
  Leitfaden zeigt, wie man Outlook-Follow‑up‑Flags effizient erstellt, liest, abschließt
  und entfernt.
og_image_alt: 'Developer guide: Set Outlook flag Java using Aspose.Email'
og_title: Outlook-Flag in Java setzen – Vollständiger Aspose.Email-Programmierleitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  headline: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  type: TechArticle
- description: Learn how to set outlook flag java using Aspose.Email for Java, covering
    flag creation, recipient flags, completion, removal, and reading options.
  name: Set Outlook Flag Java – Complete Aspose.Email Programming Guide
  steps:
  - name: Create and Initialize the Message
    text: '`MailMessage` is Aspose.Email’s high‑level class that represents an email.
      After you build the message, you convert it to a `MapiMessage` for flag manipulation.
      *We first build a `MailMessage`, set sender/recipient, then convert it to a
      `MapiMessage` for flag manipulation.*'
  - name: Define Follow‑Up Dates (Outlook Flag Reminder)
    text: '`FollowUpOptions` holds the start, reminder, and due dates. Use Java’s
      `Calendar` to set precise timestamps. *Here we set the start, reminder (the
      **outlook flag reminder**), and due dates using the `Calendar` class.*'
  - name: Apply Follow‑Up Options
    text: The `FollowUpManager.setOptions` method attaches the flag to the `MapiMessage`.
      *The `FollowUpOptions` object holds all flag details, which we apply with `FollowUpManager.setOptions`.*
  - name: Save the Message
    text: Save the flagged message as a `.msg` file so Outlook can display the flag.
      *The message is saved as a `.msg` file with the flag attached.*
  - name: Mark as Draft
    text: '`MessageFlags` is a MAPI enumeration that controls the state of the message.
      Setting `MSGFLAG_UNSENT` tells Outlook the item is a draft. *Marking the message
      as unsent ensures Outlook treats it as a draft.*'
  - name: Set Recipient Flag
    text: '`FollowUpManager.setFlagForRecipients` attaches the flag exclusively to
      the recipient’s copy. *The flag is now visible only to the recipients – a classic
      **flag for recipients** scenario.*'
  - name: Load the Message
    text: '`MapiMessage` can read a saved `.msg` file, giving you full access to its
      MAPI properties.'
  - name: Mark as Completed and Save
    text: '`FollowUpManager.completeFlag` updates the flag status, after which you
      persist the changes. *The flag status changes to “Completed” and the updated
      file is saved.*'
  - name: Load and Clear Flag
    text: '`FollowUpManager.clearFlag` removes all flag‑related properties from the
      message. *The message is saved without any follow‑up flag.*'
  - name: Retrieve Options
    text: The returned `options` object gives you full visibility into the flag’s
      configuration. *The `options` object now contains start, due, and reminder dates,
      plus the flag subject – useful when you need to **read flag options** for reporting.*
  type: HowTo
- questions:
  - answer: It’s a pure‑Java API that lets you create, read, and manipulate email
      files (MSG, EML, etc.) without needing Outlook installed.
    question: What is Aspose.Email for Java?
  - answer: Visit the [Aspose website](https://releases.aspose.com/email/java/) to
      download a 30‑day trial.
    question: How do I obtain a free trial license?
  - answer: Outlook supports only one flag per message, but you can store additional
      task data in custom MAPI properties.
    question: Can I set multiple follow‑up flags on a single message?
  - answer: Confirm the `outputDir` path is valid and that the application has permission
      to write to that location.
    question: My message isn’t saved after setting a flag. What should I check?
  - answer: Loop through your message collection and call `FollowUpManager.clearFlag`
      on each `MapiMessage`.
    question: How can I remove flags from many messages at once?
  type: FAQPage
tags:
- outlook flag
- aspose.email
- java email automation
title: Outlook-Flag in Java setzen – Vollständiger Aspose.Email-Programmierleitfaden
url: /de/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook-Flag in Java setzen mit Aspose.Email für Java

## Einführung
Wenn Sie **Outlook-Flag in Java** programmgesteuert setzen müssen, sind Sie hier genau richtig. Das Follow‑Up‑Flag von Outlook verwandelt eine normale E‑Mail in eine nachverfolgbare Aufgabe, und Aspose.Email für Java ermöglicht Ihnen die Verwaltung dieser Flags, ohne dass Outlook installiert sein muss. In diesem Tutorial führen wir Sie durch das Erstellen, Lesen, Abschließen und schließlich Entfernen von Flags sowie das Anwenden von Flags für bestimmte Empfänger. Am Ende haben Sie ein wiederverwendbares Java‑Snippet, das die Aufgabenverfolgung direkt aus Ihren Backend‑Services automatisiert.

## Schnelle Antworten
- **Was bedeutet „set outlook flag java“?** Ein Flag mit Start‑, Erinnerungs‑ und Fälligkeitsdaten zu einem Outlook‑Element per Java‑Code hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Email für Java (v25.4 oder neuer).  
- **Benötige ich eine Lizenz?** Ja – eine Testversion funktioniert für die Evaluierung, aber für den Produktionseinsatz ist eine gekaufte Lizenz erforderlich.  
- **Kann ich Flags nur für Empfänger setzen?** Absolut – verwenden Sie `FollowUpManager.setFlagForRecipients`.  
- **Ist es möglich, ein Flag später zu entfernen?** Ja – rufen Sie `FollowUpManager.clearFlag` auf.

## Was ist ein Outlook‑Follow‑Up‑Flag?
Das Outlook‑Follow‑Up‑Flag ist ein integrierter Aufgabenmarker, dem ein Startdatum, eine Erinnerung und ein Fälligkeitsdatum an jede Mail‑Nachricht angehängt werden können. Es verwandelt eine E‑Mail in ein nachverfolgtes Aktionselement und hilft Ihnen und Ihrem Team, ausstehende Arbeiten im Blick zu behalten.

## Warum Aspose.Email für Java verwenden?
Aspose.Email für Java unterstützt **über 70 E‑Mail‑Formate** (einschließlich MSG, EML, MHTML und TNEF) und kann **mehr als 100.000 Nachrichten pro Minute** auf einem typischen 8‑Kern‑Server verarbeiten, ganz ohne Outlook auf dem Host‑Rechner. Das macht es ideal für Backend‑Automatisierung, Compliance‑Reporting und die Integration mit Projekt‑Management‑Tools.

## Voraussetzungen
- **Aspose.Email für Java** Version 25.4 oder höher.  
- **JDK 16+** installiert.  
- Maven‑kompatible IDE (IntelliJ IDEA, Eclipse usw.).  
- Grundkenntnisse in Java und Vertrautheit mit E‑Mail‑Konzepten.

## Einrichtung von Aspose.Email für Java
### Maven-Konfiguration
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

## Outlook-Flag in Java setzen (Feature 1)
### Direkte Antwort
Laden Sie ein `MailMessage`, konvertieren Sie es zu einem `MapiMessage`, konfigurieren Sie `FollowUpOptions` und rufen Sie `FollowUpManager.setOptions` auf. Diese Sequenz erstellt ein vollständig geflaggtes Outlook‑Element in nur wenigen Zeilen Java‑Code.

### Schritt 1: Nachricht erstellen und initialisieren
`MailMessage` ist Aspose.Email’s High‑Level‑Klasse, die eine E‑Mail repräsentiert. Nachdem Sie die Nachricht gebaut haben, konvertieren Sie sie zu einem `MapiMessage` für die Flag‑Manipulation.

```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*Wir erstellen zunächst ein `MailMessage`, setzen Absender/Empfänger und konvertieren es anschließend zu einem `MapiMessage` für die Flag‑Manipulation.*

### Schritt 2: Follow‑Up‑Daten definieren (Outlook‑Flag‑Erinnerung)
`FollowUpOptions` enthält die Start‑, Erinnerungs‑ und Fälligkeitsdaten. Verwenden Sie Java’s `Calendar`, um präzise Zeitstempel zu setzen.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*Hier setzen wir das Start‑, Erinnerungs‑(**outlook flag reminder**)‑ und Fälligkeitsdatum mithilfe der `Calendar`‑Klasse.*

### Schritt 3: Follow‑Up‑Optionen anwenden
Die Methode `FollowUpManager.setOptions` fügt das Flag dem `MapiMessage` hinzu.  

```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*Das `FollowUpOptions`‑Objekt enthält alle Flag‑Details, die wir mit `FollowUpManager.setOptions` anwenden.*

### Schritt 4: Nachricht speichern
Speichern Sie die geflaggte Nachricht als `.msg`‑Datei, damit Outlook das Flag anzeigen kann.

```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*Die Nachricht wird als `.msg`‑Datei mit angehängtem Flag gespeichert.*

## Wie man ein Flag für Empfänger setzt (Feature 2)?
Verwenden Sie `FollowUpManager.setFlagForRecipients`, nachdem Sie die Nachricht als Entwurf markiert haben. Diese Methode fügt das Follow‑Up‑Flag nur der Kopie des Empfängers hinzu, sodass die Ansicht des Absenders unverändert bleibt. Sie müssen `MessageFlags.MSGFLAG_UNSENT` setzen, bevor Sie das Flag anwenden. Sie können zudem Start‑, Erinnerungs‑ und Fälligkeitsdaten über ein `FollowUpOptions`‑Objekt anpassen, bevor Sie die Methode aufrufen.

### Direkte Antwort
Markieren Sie die Nachricht als Entwurf mit `MessageFlags.MSGFLAG_UNSENT` und rufen Sie dann `FollowUpManager.setFlagForRecipients` auf. Outlook zeigt das Flag nur den Empfängern, nicht dem Absender, an.

### Übersicht
Manchmal muss das Flag **nur für Empfänger** sichtbar sein. Dieses Beispiel markiert die Nachricht zuerst als Entwurf und fügt dann das Flag hinzu.

#### Schritt 1: Als Entwurf markieren
`MessageFlags` ist eine MAPI‑Aufzählung, die den Zustand der Nachricht steuert. Das Setzen von `MSGFLAG_UNSENT` signalisiert Outlook, dass das Element ein Entwurf ist.

```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*Das Markieren der Nachricht als nicht gesendet stellt sicher, dass Outlook sie als Entwurf behandelt.*

#### Schritt 2: Empfänger‑Flag setzen
`FollowUpManager.setFlagForRecipients` fügt das Flag ausschließlich der Kopie des Empfängers hinzu.

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*Das Flag ist nun nur für die Empfänger sichtbar – ein klassisches **flag for recipients**‑Szenario.*

## Wie man ein Outlook‑Follow‑Up‑Flag als erledigt markiert (Feature 3)?
Laden Sie die .msg‑Datei in ein `MapiMessage` und rufen Sie `FollowUpManager.completeFlag` auf. Dadurch wird der Flag‑Status auf „Completed“ gesetzt und in Outlook ein Häkchen angezeigt. Nach dem Abschließen speichern Sie die Nachricht, um die Änderung zu persistieren. Optional können Sie die Abschlusszeit über die Eigenschaft `FlagCompleteTime` anpassen, falls dies für Auditzwecke erforderlich ist.

### Direkte Antwort
Laden Sie die vorhandene `.msg`‑Datei in ein `MapiMessage`, rufen Sie `FollowUpManager.completeFlag` auf und speichern Sie die Datei. Der Flag‑Status ändert sich zu „Completed“ und erscheint mit einem Häkchen in Outlook.

### Schritt 1: Nachricht laden
`MapiMessage` kann eine gespeicherte `.msg`‑Datei lesen und bietet vollen Zugriff auf deren MAPI‑Eigenschaften.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### Schritt 2: Als erledigt markieren und speichern
`FollowUpManager.completeFlag` aktualisiert den Flag‑Status, danach persistieren Sie die Änderungen.

```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*Der Flag‑Status ändert sich zu „Completed“ und die aktualisierte Datei wird gespeichert.*

## Wie man ein Outlook‑Follow‑Up‑Flag entfernt (Feature 4)?
Öffnen Sie die .msg‑Datei mit `MapiMessage`, rufen Sie `FollowUpManager.clearFlag` auf und speichern Sie die Nachricht anschließend. Dadurch werden alle flag‑bezogenen MAPI‑Eigenschaften entfernt, sodass Outlook keinen Follow‑Up‑Indikator mehr anzeigt. Nutzen Sie dies, wenn eine Aufgabe storniert oder nicht mehr relevant ist. Stellen Sie sicher, dass Sie auch etwaige benutzerdefinierte Erinnerungs‑Eigenschaften löschen, um Restbenachrichtigungen zu vermeiden.

### Direkte Antwort
Öffnen Sie die `.msg`‑Datei mit `MapiMessage`, rufen Sie `FollowUpManager.clearFlag` auf und speichern Sie die Datei. Die Nachricht zeigt keinen Follow‑Up‑Indikator mehr in Outlook an.

### Schritt 1: Laden und Flag entfernen
`FollowUpManager.clearFlag` entfernt alle flag‑bezogenen Eigenschaften aus der Nachricht.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*Die Nachricht wird ohne irgendein Follow‑Up‑Flag gespeichert.*

## Wie man Flag‑Optionen liest (Feature 5)?
Rufen Sie `FollowUpManager.getOptions` auf einem geladenen `MapiMessage` auf, um ein `FollowUpOptions`‑Objekt zu erhalten. Dieses Objekt liefert Start‑, Fälligkeits‑ und Erinnerungsdaten sowie den Flag‑Betreff, sodass Sie die Flag‑Details anzeigen oder protokollieren können. Es ist nützlich für Reporting und Compliance‑Audits.

### Direkte Antwort
Verwenden Sie `FollowUpManager.getOptions` auf einem geladenen `MapiMessage`, um ein `FollowUpOptions`‑Objekt zu erhalten, das Start‑, Fälligkeits‑ und Erinnerungsdaten sowie den Flag‑Betreff enthält. Das ist praktisch für Reporting‑ oder Compliance‑Audits.

### Schritt 1: Optionen abrufen
Das zurückgegebene `options`‑Objekt liefert vollständige Einblicke in die Konfiguration des Flags.

```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*Das `options`‑Objekt enthält nun Start‑, Fälligkeits‑ und Erinnerungsdaten sowie den Flag‑Betreff – nützlich, wenn Sie **read flag options** für Berichte benötigen.*

## Praktische Anwendungen
- **Integration in Aufgaben‑Management‑Tools:** Geflaggte E‑Mails mit Jira, Trello oder Azure Boards synchronisieren.  
- **Automatisierte Erinnerungen:** Tägliche Erinnerungs‑E‑Mails für ausstehende Follow‑Ups generieren.  
- **Compliance‑Audits:** Flag‑Daten für regulatorische Berichte exportieren, wobei die Möglichkeit genutzt wird, Flag‑Optionen programmgesteuert zu lesen.

## Leistungsüberlegungen
- **Datumsberechnungen:** Daten einmal pro Batch berechnen statt in Schleifen.  
- **Ressourcenverwaltung:** Streams oder Dateihandles nach dem Speichern von Nachrichten schließen.  
- **Speicherverbrauch:** Große Postfächer in Teilen verarbeiten, um Heap‑Druck zu vermeiden; Aspose.Email kann mehrere hundertseitige Postfächer verarbeiten, ohne die gesamte Datei in den Speicher zu laden.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| Flag wird in Outlook nicht angezeigt | Nachricht ohne korrekte `MessageFlags` gespeichert | Stellen Sie sicher, dass `setMessageFlags` auf `MSGFLAG_UNSENT` gesetzt ist, bevor Empfänger‑Flags angewendet werden. |
| Save wirft `AccessDeniedException` | Falscher Dateipfad oder fehlende Schreibrechte | Vergewissern Sie sich, dass das Ausgabeverzeichnis existiert und die Anwendung Schreibrechte hat. |
| Daten liegen einen Tag zurück | Zeitzonen‑Diskrepanz | Verwenden Sie konsequent `TimeZone.getTimeZone("GMT")` oder Ihre lokale Zone. |

## Häufig gestellte Fragen
**F: Was ist Aspose.Email für Java?**  
A: Es ist eine reine Java‑API, mit der Sie E‑Mail‑Dateien (MSG, EML usw.) erstellen, lesen und manipulieren können, ohne dass Outlook installiert sein muss.

**F: Wie erhalte ich eine kostenlose Testlizenz?**  
A: Besuchen Sie die [Aspose-Website](https://releases.aspose.com/email/java/), um eine 30‑tägige Testversion herunterzuladen.

**F: Kann ich mehrere Follow‑Up‑Flags auf einer einzigen Nachricht setzen?**  
A: Outlook unterstützt nur ein Flag pro Nachricht, aber Sie können zusätzliche Aufgabendaten in benutzerdefinierten MAPI‑Eigenschaften speichern.

**F: Meine Nachricht wird nach dem Setzen eines Flags nicht gespeichert. Was sollte ich prüfen?**  
A: Vergewissern Sie sich, dass der Pfad `outputDir` gültig ist und die Anwendung Schreibrechte für diesen Ort hat.

**F: Wie kann ich Flags von vielen Nachrichten gleichzeitig entfernen?**  
A: Durchlaufen Sie Ihre Nachrichten‑Sammlung und rufen Sie `FollowUpManager.clearFlag` für jedes `MapiMessage` auf.

## Ressourcen
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Manage Outlook Categories with Aspose.Email for Java - A Comprehensive Guide](/email/java/calendar-appointments/manage-outlook-categories-aspose-email-java/)
- [Create outlook notes java with Aspose.Email – Full Guide](/email/java/calendar-appointments/create-customize-outlook-notes-aspose-email-java/)
- [Create Tasks in Microsoft Exchange Using Aspose.Email for Java: A Complete Guide](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}