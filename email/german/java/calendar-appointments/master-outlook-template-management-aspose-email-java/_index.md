---
date: '2026-01-06'
description: Erfahren Sie, wie Sie OFT in MSG konvertieren, die Verarbeitung von Outlook‑Vorlagen
  automatisieren und Outlook‑Vorlagen‑MSG‑Dateien mit Aspose.Email für Java speichern.
keywords:
- Outlook template management
- Aspose.Email for Java
- email automation with Java
title: Wie man OFT in MSG konvertiert und Outlook‑Vorlagen mit Aspose.Email für Java
  verwaltet
url: /de/java/calendar-appointments/master-outlook-template-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# convert oft to msg – Beherrschung der Outlook-Vorlagenverwaltung mit Aspose.Email für Java

In diesem umfassenden Leitfaden erfahren Sie **wie man OFT in MSG konvertiert**, Outlook-Vorlageneigenschaften aktualisiert und Outlook-Vorlagen‑MSG‑Dateien speichert – alles mit der leistungsstarken Aspose.Email‑Bibliothek für Java. Egal, ob Sie automatisierte E‑Mail‑Kampagnen erstellen oder Besprechungseinladungen generieren, diese Schritte helfen Ihnen, Ihren Arbeitsablauf zu optimieren.

## Schnelle Antworten
- **Was bedeutet „convert oft to msg“?** Es wandelt eine Outlook‑Vorlage (OFT) in eine vollständig konfigurierte Outlook‑Nachricht (MSG) um.  
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.Email für Java.  
- **Benötige ich eine Lizenz?** Eine Testversion funktioniert zum Testen; eine Voll‑Lizenz schaltet alle Funktionen frei.  
- **Kann ich Maven für Abhängigkeiten verwenden?** Ja, fügen Sie das Aspose.Email Maven‑Artefakt hinzu.  
- **Ist Java 16 erforderlich?** Empfohlen, aber spätere JDKs werden ebenfalls unterstützt.

## Einführung

Die Automatisierung von Outlook‑Vorlagen ist eine gängige Aufgabe für Entwickler, die E‑Mail‑Workflows optimieren möchten. Mit Aspose.Email für Java wird **convert OFT to MSG** sowohl einfach als auch effizient. Dieses Tutorial behandelt:

- Laden vorhandener Outlook‑Vorlagen
- Aktualisieren von E‑Mail‑Eigenschaften wie Absender‑ und Empfängerdetails
- Speichern von Nachrichten im MSG‑Format
- Erstellen und Speichern neuer Outlook‑Vorlagen

Am Ende dieses Leitfadens sind Sie sicher im Umgang mit Outlook‑Vorlagendateien, beim Konvertieren von OFT zu MSG und beim Speichern von Outlook‑Vorlagen‑MSG‑Dateien zur Wiederverwendung.

### Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:
- **Aspose.Email für Java Bibliothek**: Version 25.4 oder neuer  
- **Java Development Kit (JDK)**: JDK 16 oder höher wird empfohlen  
- **Maven** (optional) für die Verwaltung von Abhängigkeiten  
- Grundkenntnisse in Java‑Programmierung und E‑Mail‑Konzepten

## Einrichtung von Aspose.Email für Java

Um Aspose.Email in Ihrem Java‑Projekt zu verwenden, binden Sie es als Abhängigkeit ein. So können Sie es mit Maven einrichten:

### Maven‑Einrichtung

Fügen Sie das Folgende zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzbeschaffung

Aspose.Email erfordert eine Lizenz für die volle Funktionalität, aber Sie können mit einer kostenlosen Testversion beginnen oder eine temporäre Lizenz anfordern, um das Produkt zu evaluieren:
- **Kostenlose Testversion**: Laden Sie sie von der [Aspose‑Release‑Seite](https://releases.aspose.com/email/java/) herunter.  
- **Temporäre Lizenz**: Fordern Sie eine [hier](https://purchase.aspose.com/temporary-license/) an, falls nötig.  
- **Kauf**: Für den langfristigen Einsatz erwerben Sie eine Lizenz über das [Kauf‑Portal](https://purchase.aspose.com/buy).

Initialisieren Sie Ihre Umgebung mit Aspose.Email, indem Sie die Lizenz wie unten gezeigt einrichten:

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_license.lic");
```

## Implementierungs‑Leitfaden

### Laden und Aktualisieren einer Outlook‑Vorlagendatei

Dieser Abschnitt führt Sie durch das Laden einer vorhandenen OFT‑Datei, das Aktualisieren ihres Inhalts und das Speichern als MSG‑Datei – genau der **convert OFT to MSG**‑Prozess, den Sie benötigen.

#### Überblick

Erfahren Sie, wie Sie den Inhalt einer OFT‑(Outlook‑Vorlage)‑Datei manipulieren und in eine vollständig konfigurierte MSG‑E‑Mail‑Nachricht konvertieren.

#### Implementierungsschritte

**1. Laden der Outlook‑Vorlage**

Beginnen Sie damit, Ihre OFT‑Vorlage mit `MailMessage` zu laden:

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
MailMessage message = MailMessage.load(dataDir + "sample.oft");
```

**2. Absender‑ und Empfängerdetails festlegen**

Aktualisieren Sie die Absender‑ und Empfängerinformationen in der geladenen E‑Mail.

```java
message.setSender(new MailAddress("john@abc.com", "John"));
message.getTo().addMailAddress(new MailAddress("william@xzy.com", "William"));
```

**3. HTML‑Body‑Inhalt aktualisieren**

Ändern Sie den HTML‑Body, um Ihre E‑Mail‑Vorlage mit Empfängerdetails und Besprechungsinformationen zu personalisieren.

```java
String htmlBody = message.getHtmlBody();
htmlBody = htmlBody.replace("DisplayName", "<b>William</b>");
htmlBody = htmlBody.replace("MeetingPlace", "<u>Hall 1, Convention Center, New York, USA</u>");
htmlBody = htmlBody.replace("MeetingTime", "<u>Monday, June 28, 2010</u>");
message.setHtmlBody(htmlBody);
```

**4. Als MSG‑Datei speichern**

Speichern Sie schließlich die aktualisierte Nachricht im MSG‑Format – das ist der Kern von **convert OFT to MSG**.

```java
MapiMessage mapimessage = MapiMessage.fromMailMessage(message);
mapimessage.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
mapimessage.save(dataDir + "Invitation.msg");
```

### Outlook‑Nachricht als Vorlagendatei speichern

Erfahren Sie, wie Sie eine neue E‑Mail‑Nachricht erstellen und als OFT‑Datei für die zukünftige Wiederverwendung speichern – ideal für **outlook template automation**.

#### Überblick

Wir führen Sie durch das Erstellen einer einfachen E‑Mail‑Nachricht und das Speichern als Outlook‑Vorlagendatei, die Sie später bei Bedarf laden und in MSG konvertieren können.

#### Implementierungsschritte

**1. Neue E‑Mail‑Nachricht erstellen**

Initialisieren Sie ein `MapiMessage` mit den erforderlichen Details.

```java
MapiMessage mapi = new MapiMessage("test@from.to", "test@to.to", "template subject", "Template body");
```

**2. Als Vorlagendatei speichern**

Speichern Sie die Nachricht im OFT‑Format für die zukünftige Verwendung.

```java
try {
    mapi.saveAsTemplate(dataDir + "mapiToOft.oft");
} finally {
    if (mapi != null) ((IDisposable)mapi).dispose();
}
```

## Praktische Anwendungen

Hier sind einige Praxisbeispiele, in denen diese Funktionen glänzen:
1. **Automatisierte E‑Mail‑Kampagnen** – Verwenden Sie Vorlagen, um personalisierte Massenmailings zu optimieren.  
2. **Besprechungseinladungen** – Füllen Sie Empfängerdetails dynamisch aus und konvertieren Sie die Vorlage vor dem Versand in MSG.  
3. **Dokumentenverteilung** – Speichern Sie häufig genutzte Nachrichten als OFT‑Vorlagen und konvertieren Sie sie bei Bedarf.

## Leistungsüberlegungen

- **Ressourcennutzung optimieren** – Verwalten Sie Streams und Objekte sorgfältig, insbesondere bei großen HTML‑Bodies oder Anhängen.  
- **Speichermanagement** – Entsorgen Sie `IDisposable`‑Objekte (wie gezeigt), um den Speicher sofort freizugeben.  
- **Batch‑Verarbeitung** – Bei der Verarbeitung vieler Vorlagen verarbeiten Sie sie in Stapeln, um den Speicherverbrauch gering zu halten.

## Fazit

In diesem Tutorial haben Sie gelernt, wie man **convert OFT to MSG** durchführt, Outlook‑Vorlageneigenschaften aktualisiert und Outlook‑Vorlagen‑MSG‑Dateien mit Aspose.Email für Java speichert. Mit diesen Fähigkeiten können Sie die E‑Mail‑Erstellung automatisieren, Besprechungseinladungen personalisieren und wiederverwendbare Outlook‑Vorlagen pflegen.

Um Ihr Verständnis der Möglichkeiten von Aspose.Email zu vertiefen, erkunden Sie die [Dokumentation](https://reference.aspose.com/email/java/) und experimentieren Sie mit verschiedenen Funktionen.

## Häufig gestellte Fragen

**Q1: Kann ich Aspose.Email Java ohne Lizenz verwenden?**  
A1: Ja, Sie können mit einer kostenlosen Testversion beginnen, aber einige Funktionen sind eingeschränkt, bis Sie eine Voll‑Lizenz erwerben.

**Q2: Was sind die Vorteile von Aspose.Email für die E‑Mail‑Automatisierung?**  
A2: Es bietet robuste APIs zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von E‑Mail‑Formaten, wodurch groß angelegte Automatisierung zuverlässig wird.

**Q3: Wie gehe ich mit Anhängen in Aspose.Email Java um?**  
A3: Verwenden Sie `MapiMessage`‑Methoden wie `addAttachment` oder `removeAttachment`, um an Ihre Nachrichten angehängte Dateien zu verwalten.

**Q4: Kann ich MSG‑Dateien mit Aspose.Email Java zurück in OFT‑Vorlagen konvertieren?**  
A4: Direkte Konvertierung wird nicht unterstützt, aber Sie können ein MSG laden, dessen Inhalt ändern und es dann als OFT‑Vorlage speichern, indem Sie die Struktur neu erstellen.

**Q5: Eignet sich Aspose.Email Java für die Verarbeitung von großen E‑Mail‑Mengen?**  
A5: Ja, vorausgesetzt, Sie implementieren ein effizientes Ressourcenmanagement und berücksichtigen die Stapelverarbeitung für optimale Leistung.

---

**Zuletzt aktualisiert:** 2026-01-06  
**Getestet mit:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

**Ressourcen**
- **Dokumentation**: [Aspose Email Java Reference](https://reference.aspose.com/email/java/)  
- **Bibliothek herunterladen**: [Aspose Email Releases](https://releases.aspose.com/email/java/)  
- **Lizenz erwerben**: [Buy Aspose Products](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion**: [Try Aspose Email](https://releases.aspose.com/email/java/)  
- **Temporäre Lizenz**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support‑Forum**: [Aspose Community Support](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}