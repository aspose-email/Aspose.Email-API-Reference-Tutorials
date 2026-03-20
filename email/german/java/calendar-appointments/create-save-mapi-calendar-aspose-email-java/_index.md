---
date: '2026-03-20'
description: Erfahren Sie, wie Sie Outlook‑Kalender‑PST mit Aspose.Email für Java
  exportieren – MAPI‑Kalenderobjekte erstellen, Wiederholungen festlegen, Teilnehmer
  hinzufügen und in PST speichern.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Outlook‑Kalender‑PST mit Aspose.Email exportieren – Java
url: /de/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Outlook calendar PST with Aspose.Email – Java

## Einführung

Möchten Sie die Kalenderautomatisierung in Ihren Java‑Anwendungen optimieren und **Outlook‑Kalender‑PST**‑Dateien exportieren? Mit **Aspose.Email for Java** können Sie **MAPI calendar Java**‑Elemente erstellen, Wiederholungsmuster definieren, Teilnehmer hinzufügen und **den Kalender in PST speichern** – und das mit nur wenigen Codezeilen. Dieses Tutorial führt Sie durch den gesamten Prozess – von der Einrichtung der Bibliothek bis zur Erstellung eines voll funktionsfähigen Kalendereintrags, der bereit zur Verteilung ist.

### Was Sie lernen werden
- Wie man **MAPI calendar Java**‑Ereignisse mit Aspose.Email erstellt.  
- Konfiguration von täglichen, wöchentlichen oder benutzerdefinierten Wiederholungsmustern.  
- Hinzufügen von Empfängern (Organisatoren, Teilnehmer) zu Ihren Kalendereinladungen.  
- Persistieren des Kalenderelements durch **Speichern des Kalenders in PST** für Outlook‑Kompatibilität.  
- Wie man **die Terminplanung automatisiert** mit wiederverwendbarem Code.

## Schnellantworten
- **Welche Bibliothek?** Aspose.Email for Java  
- **Hauptziel?** Export Outlook calendar PST und **Speichern des Kalenders in PST**  
- **Voraussetzungen?** Java 8+, Maven, Aspose.Email‑Lizenz  
- **Typische Implementierungsdauer?** 10‑15 Minuten für ein Basis‑Ereignis  
- **Kann ich Wiederholungen hinzufügen?** Ja – täglich, wöchentlich, monatlich usw.

## Export Outlook calendar PST

In diesem Abschnitt konzentrieren wir uns auf den End‑zu‑End‑Ablauf, der es Ihnen ermöglicht, **Outlook calendar PST**‑Dateien zu **exportieren**. Nachdem das MAPI‑Kalenderobjekt erstellt wurde, besteht der letzte Schritt darin, es in einer PST‑Datei zu speichern, die Outlook direkt lesen kann.

## Warum Aspose.Email für die Kalenderautomatisierung verwenden?

- **Vollständige Outlook‑Kompatibilität** – erzeugte Elemente funktionieren in Outlook, OWA und mobilen Clients.  
- **Umfangreiche Wiederholungsunterstützung** – tägliche, wöchentliche, monatliche und benutzerdefinierte Muster out of the box.  
- **Keine externen Abhängigkeiten** – reine Java‑Bibliothek, kein COM‑Interop erforderlich.  
- **Hohe Leistung** – effiziente Verarbeitung großer PST‑Dateien und Batch‑Operationen.  
- **Automatisierte Terminplanung** – betten Sie diese Logik in Batch‑Jobs oder Web‑Services ein, um Hunderte von Einladungen automatisch zu erstellen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken
- **Aspose.Email for Java**: Version 25.4 oder neuer.

### Anforderungen an die Umgebung
- Eine Java‑IDE wie IntelliJ IDEA oder Eclipse.  
- Maven installiert zur Verwaltung der Abhängigkeiten.

### Fachliche Voraussetzungen
- Grundlegende Java‑Programmierkenntnisse.  
- Vertrautheit mit objektorientierten Konzepten.

## Aspose.Email for Java einrichten

Fügen Sie die Aspose.Email‑Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung

Aspose.Email bietet eine kostenlose Testversion, aber eine Lizenz schaltet alle Funktionen frei:

- **Kostenlose Testversion**: Testen Sie ohne Einschränkungen für 30 Tage.  
- **Temporäre Lizenz**: Anfordern über die [Aspose‑Website](https://purchase.aspose.com/temporary-license/), falls Sie mehr Zeit benötigen.  
- **Kauf**: Erwerben Sie eine permanente Lizenz über die [Kaufseite](https://purchase.aspose.com/buy).

### Grundlegende Initialisierung

Nach dem Hinzufügen der Abhängigkeit initialisieren Sie die Bibliothek mit Ihrer Lizenzdatei:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## Implementierungsleitfaden

Jetzt, wo Sie eingerichtet sind, lassen Sie uns **MAPI calendar Java** erstellen und **den Kalender in PST speichern**.

### MAPI‑Kalender mit Wiederholung erstellen

#### Überblick

Wir bauen ein Kalenderevent, wenden eine tägliche Wiederholung an, fügen Teilnehmer hinzu und speichern das Ganze schließlich in einer PST‑Datei.

#### Schritt‑für‑Schritt‑Implementierung

1. **Datum und Wiederholungsmuster initialisieren**  

   Definieren Sie zunächst die Startzeit und setzen Sie eine tägliche Wiederholung:

   ```java
   import java.util.Date;

   // Add hours to current date to get the start time
   Date startDate = addHours(new Date(), 12);

   MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
   recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
   ```

   *Erklärung*: `MapiCalendarEventRecurrence` enthält die Wiederholungsdetails; wir wählen ein tägliches Muster über `MapiCalendarDailyRecurrencePattern`.

2. **Empfänger einrichten**  

   Fügen Sie die Personen hinzu, die die Besprechungseinladung erhalten sollen:

   ```java
   import com.aspose.email.MapiRecipientCollection;
   import com.aspose.email.MapiRecipientType;

   MapiRecipientCollection recColl = new MapiRecipientCollection();
   recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
   ```

   *Erklärung*: `MapiRecipientCollection` speichert jeden Teilnehmer; `MAPI_TO` kennzeichnet sie als primäre Empfänger.

3. **MAPI‑Kalenderelement erstellen**  

   Erzeugen Sie das Kalenderobjekt mit allen erforderlichen Details:

   ```java
   import com.aspose.email.MapiCalendar;

   MapiCalendar calendar = new MapiCalendar(
       "Organizer Name", 
       "Meeting Subject", 
       "Meeting Location", 
       startDate, 
       addHours(startDate, 1), // End time is one hour after start
       "Event Description",
       recColl,
       recurrence
   );
   ```

   *Erklärung*: Der Konstruktor erwartet Organisator, Betreff, Ort, Start‑/Endzeit, Beschreibung, Empfängerliste und Wiederholung.

4. **In PST‑Datei speichern**  

   Schließlich persistieren Sie den Kalender durch **Speichern des Kalenders in PST**:

   ```java
   import com.aspose.email.PersonalStorage;
   import com.aspose.email.FolderInfo;
   import com.aspose.email.StandardIpmFolder;

   PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
   FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

   // Save the MAPI Calendar item
   calendarFolder.addMapiMessageItem(calendar);
   ```

   *Erklärung*: `PersonalStorage.create` erzeugt eine neue PST‑Datei, und `addMapiMessageItem` fügt den Kalendereintrag in den Ordner „Calendar“ ein.

### Fehlerbehebungstipps
- Überprüfen Sie den Lizenzpfad; eine ungültige Lizenz schränkt die Funktionalität ein.  
- Stellen Sie sicher, dass die E‑Mail‑Adressen der Empfänger korrekt formatiert sind, um Einladungsfehler zu vermeiden.  
- Schließen Sie die PST (`pst.dispose()`) nach den Vorgängen, um Dateihandles freizugeben.

## Praktische Anwendungsfälle

Hier einige gängige Szenarien, in denen **MAPI calendar Java** zu erstellen und **den Kalender in PST zu speichern** besonders nützlich ist:

1. **Automatisierte Terminplanung** – Generieren Sie wiederkehrende Besprechungseinladungen für Projektteams ohne manuellen Aufwand.  
2. **Event‑Management‑Plattformen** – Exportieren Sie Konferenzsessions als Outlook‑kompatible Kalendereinträge.  
3. **CRM‑Integration** – Synchronisieren Sie Kundentermine aus einem CRM‑System direkt in Outlook via PST‑Dateien.

## Leistungsüberlegungen

- **Ressourcenverwaltung**: Entsorgen Sie `PersonalStorage`‑Objekte nach Gebrauch, um Dateisperren zu vermeiden.  
- **Batch‑Verarbeitung**: Bei großen Mengen verarbeiten Sie Kalenderelemente asynchron oder in Chargen, um den Speicherverbrauch gering zu halten.  

## Fazit

Sie haben nun gelernt, wie Sie **Outlook calendar PST** exportieren, indem Sie MAPI calendar Java‑Objekte erstellen, Wiederholungen konfigurieren, Teilnehmer hinzufügen und **den Kalender in PST speichern** mit Aspose.Email. Dieser Ansatz befähigt Ihre Java‑Anwendungen, anspruchsvolle Terminplanungs‑Workflows mit Outlook‑Kompatibilität zu automatisieren.

Für weiterführende Informationen besuchen Sie die offizielle [Dokumentation](https://reference.aspose.com/email/java/).

## FAQ‑Abschnitt

### Q: Kann ich wöchentliche Wiederholungsmuster erstellen?
- **A**: Ja! Verwenden Sie `MapiCalendarWeeklyRecurrencePattern`, um wöchentliche Wiederholungen zu definieren.

### Q: Wie gehe ich mit Ausnahmen bei der Ereigniswiederholung um?
- **A**: Rufen Sie `setExceptions()` am Wiederholungsobjekt auf, um Daten anzugeben, die vom Muster abweichen.

### Q: Ist es möglich, ein bestehendes Kalenderelement zu aktualisieren?
- **A**: Absolut. Laden Sie das Element aus der PST, ändern Sie dessen Eigenschaften und speichern Sie es erneut.

### Q: Kann ich die PST‑Datei verschlüsseln?
- **A**: Ja, Aspose.Email ermöglicht das Setzen eines Passworts für `PersonalStorage` beim Erstellen der PST.

### Q: Was, wenn ich Anhänge zum Kalenderevent hinzufügen muss?
- **A**: Verwenden Sie `calendar.getAttachments().addFileAttachment("path/to/file")` vor dem Speichern.

## Ressourcen

- [Aspose.Email Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/email/java/)
- [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

---

**Zuletzt aktualisiert:** 2026-03-20  
**Getestet mit:** Aspose.Email for Java 25.4 (JDK 16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}