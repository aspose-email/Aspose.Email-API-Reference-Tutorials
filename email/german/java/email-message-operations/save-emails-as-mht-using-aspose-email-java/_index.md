---
date: '2026-03-02'
description: Erfahren Sie, wie Sie Maven Aspose.Email für Java verwenden, um E-Mails
  als MHT-Dateien zu speichern. Diese Schritt‑für‑Schritt‑Anleitung behandelt die
  Einrichtung, benutzerdefinierte Vorlagen und die Konvertierung von E-Mails zu MHT.
keywords:
- save emails as MHT files
- Aspose.Email for Java
- convert emails to MHTML
title: 'Maven Aspose.Email für Java: E-Mails als MHT-Dateien speichern'
url: /de/java/email-message-operations/save-emails-as-mht-using-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maven Aspose.Email für Java: Wie man E-Mails als MHT-Dateien speichert

## Einführung

Die effiziente Verwaltung von E‑Mail‑Daten kann eine Herausforderung sein, insbesondere wenn es um das Teilen und Archivieren geht. In diesem Leitfaden zeigen wir Ihnen **wie man MHT**‑Dateien mit **Maven Aspose.Email für Java** speichert, sodass Sie E‑Mails mit benutzerdefinierten Vorlagen in MHT konvertieren und Kalenderereignisse unverändert behalten können. Am Ende verfügen Sie über eine sofort einsatzbereite Lösung, die in jeder Java 16+‑Umgebung funktioniert.

## Schnellantworten
- **Welche Bibliothek benötige ich?** Maven Aspose.Email für Java (v25.4+).  
- **Welches Format wird erzeugt?** Eine MHT (MHTML)‑Datei, die HTML, Bilder und Kalenderdaten bündelt.  
- **Kann ich den Header anpassen?** Ja – verwenden Sie `MhtFormatOptions` und Vorlagen‑Strings.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine permanente Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** JDK 16 oder höher.

## Was ist Maven Aspose.Email für Java?
Maven Aspose.Email für Java ist eine leistungsstarke API, mit der Sie E‑Mail‑Nachrichten direkt aus Java‑Code erstellen, lesen, konvertieren und manipulieren können. Sie unterstützt eine Vielzahl von Formaten – darunter MSG, EML und MHT – und eignet sich damit ideal für **java email conversion**‑Aufgaben.

## Warum E‑Mails in MHT konvertieren?
- **Web‑freundlich**: MHT‑Dateien werden in Browsern ohne externe Ressourcen angezeigt.  
- **Archiv‑Stabilität**: Alle Ressourcen sind eingebettet, wodurch das ursprüngliche Aussehen erhalten bleibt.  
- **Kalender‑Unterstützung**: Wiederkehrende Ereignisse können mit benutzerdefinierten Vorlagen gerendert werden.  

## Voraussetzungen
- **Aspose.Email für Java** (Maven‑Artefakt `com.aspose:aspose-email:25.4` mit `jdk16`‑Classifier).  
- **Maven** installiert und auf Ihrem Rechner konfiguriert.  
- **JDK 16+** (die Bibliothek zielt auf Java 16).  
- Grundkenntnisse in Java (Dateiverarbeitung, Maven‑Abhängigkeiten).

## Einrichtung von Aspose.Email für Java

### Maven‑Abhängigkeit

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

Aspose bietet eine kostenlose Testversion an, um die Funktionen zu erkunden, sowie Optionen zum Kauf einer Lizenz oder zum Erhalt einer temporären Lizenz.

1. **Kostenlose Testversion**: Laden Sie sie von [Releases](https://releases.aspose.com/email/java/) herunter und testen Sie die Funktionen ohne Einschränkungen.  
2. **Temporäre Lizenz**: Fordern Sie eine voll funktionsfähige Version über die [Temporary License Page](https://purchase.aspose.com/temporary-license/) an.  
3. **Kauf**: Ziehen Sie einen Kauf in Betracht, wenn Aspose.Email Ihren langfristigen Projektanforderungen entspricht.

### Grundlegende Initialisierung

Nach der Installation initialisieren Sie die Bibliothek in Ihrer Java‑Anwendung:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license/file");
```

Mit diesen Schritten sind Sie bereit, die Funktionen von Aspose.Email für eine effiziente E‑Mail‑Verarbeitung zu nutzen.

## Implementierungs‑Leitfaden

### Feature 1: Load MailMessage

#### Überblick
Das Laden einer E‑Mail‑Nachricht ist der erste Schritt, um sie zu verarbeiten und als MHT‑Datei zu speichern. Im Folgenden zeigen wir, wie Sie eine `.msg`‑Datei mit `MailMessage` laden.

#### Schritt‑für‑Schritt

**Erforderliche Klassen importieren**

```java
import com.aspose.email.MailMessage;
```

**E‑Mail aus Datei laden**

```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY" + "/email/";
MailMessage msg = MailMessage.load(dataDir + "Meeting with Recurring Occurrences.msg");
```

Dieses Snippet lädt eine E‑Mail‑Nachricht aus dem von Ihnen angegebenen Verzeichnis.

### Feature 2: Configure MhtSaveOptions

#### Überblick
Die Konfiguration von `MhtSaveOptions` ist entscheidend, um festzulegen, wie Ihre E‑Mail als MHT‑Datei gespeichert wird, einschließlich benutzerdefinierter Formatierung für Kalenderereignisse.

#### Schritt‑für‑Schritt

**Erforderliche Klassen importieren**

```java
import com.aspose.email.MhtSaveOptions;
import com.aspose.email.MhtFormatOptions;
import com.aspose.email.MhtTemplateName;
```

**Speicheroptionen und Vorlagen festlegen**

```java
MhtSaveOptions options = new MhtSaveOptions();
options.setMhtFormatOptions(MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent);

// Customize templates for email properties
for (Map.Entry<MhtTemplateName, String> entry : options.getFormatTemplates().entrySet()) {
    switch (entry.getKey()) {
        case START:
            options.getFormatTemplates().set_Item(MhtTemplateName.START,
                    "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
            break;
        // Add other cases similarly...
    }
}

// Ensure entries are added if absent
options.getFormatTemplates().addIfAbsent(MhtTemplateName.START,
            "<span class='headerLineTitle'>Start:</span><span class='headerLineText'>{0}</span><br/>");
```

Diese Konfiguration richtet Header und das Rendern von Kalenderereignissen in der MHT‑Ausgabe ein.

### Feature 3: Save MailMessage as MHT

#### Überblick
Der letzte Schritt besteht darin, Ihre konfigurierte `MailMessage` mit den angegebenen Optionen als MHT‑Datei zu speichern.

#### Schritt‑für‑Schritt

**Erforderliche Klassen importieren**

```java
import com.aspose.email.MailMessage;
import com.aspose.email.MhtSaveOptions;
```

**E‑Mail‑Nachricht speichern**

```java
msg.save("YOUR_OUTPUT_DIRECTORY" + "Meeting with Recurring Occurrences_out.mhtml", options);
```

Dieser Befehl schreibt die E‑Mail in eine MHT‑Datei, bereit zum Teilen oder Archivieren.

## Praktische Anwendungsfälle
- **E‑Mail‑Archivierung**: Konvertieren und speichern Sie wichtige E‑Mails in einem web‑freundlichen Format.  
- **Rechtliche Dokumentation**: Verwenden Sie MHT‑Dateien als Teil von Beweismaterial, bei dem E‑Mail‑Details erhalten bleiben müssen.  
- **Plattformübergreifendes Teilen**: Teilen Sie E‑Mails ohne Kompatibilitätsprobleme zwischen verschiedenen Systemen.  

Die Integration mit anderen Systemen, wie CRM‑ oder Projekt‑Management‑Tools, kann die Zusammenarbeit verbessern, indem wichtige E‑Mail‑Daten direkt in Workflows eingebettet werden.

## Leistungs‑Überlegungen
Um optimale Leistung zu gewährleisten:
- Verwalten Sie den Speicherverbrauch effizient, wenn Sie große Mengen an E‑Mails verarbeiten.  
- Optimieren Sie Datei‑I/O‑Operationen, um Engpässe beim Speichervorgang zu vermeiden.  

Die Befolgung bewährter Java‑Speicher‑Management‑Praktiken hält Ihre Anwendung reaktionsfähig.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| **NullPointerException bei `msg.save`** | Falscher Ausgabepfad | Stellen Sie sicher, dass `YOUR_OUTPUT_DIRECTORY` existiert und beschreibbar ist. |
| **Bilder fehlen im MHT** | `MhtFormatOptions` nicht auf Einbetten von Ressourcen gesetzt | Fügen Sie `MhtFormatOptions.EmbedResources` zum Options‑Flag hinzu. |
| **Kalenderereignisse werden nicht gerendert** | `RenderCalendarEvent`‑Flag fehlt | Stellen Sie sicher, dass `options.setMhtFormatOptions(MhtFormatOptions.WriteHeader \| MhtFormatOptions.RenderCalendarEvent);` verwendet wird. |

## Häufig gestellte Fragen

**F: Wie gehe ich mit Anhängen um, wenn ich E‑Mails als MHT speichere?**  
A: Stellen Sie sicher, dass `MhtSaveOptions` so konfiguriert ist, dass die Anhangs‑Verarbeitung einbezogen wird. Die Bibliothek unterstützt das Einbetten von Anhängen in die MHT‑Datei.

**F: Kann ich E‑Mail‑Header im ausgegebenen MHT‑File anpassen?**  
A: Ja, verwenden Sie `MhtFormatOptions.WriteHeader` und definieren Sie benutzerdefinierte Vorlagen für verschiedene Header‑Felder, wie im Tutorial gezeigt.

**F: Was sind die Systemanforderungen für die Verwendung von Aspose.Email Java?**  
A: Ein JDK 16 oder höher ist erforderlich. Die Bibliothek funktioniert nahtlos mit den meisten modernen IDEs, die Maven‑Projekte unterstützen.

**F: Ist es möglich, nur bestimmte Teile einer E‑Mail‑Nachricht zu speichern?**  
A: Während das MHT‑Format typischerweise vollständige Nachrichten enthält, können Sie die Eigenschaften von `MailMessage` nutzen, um Inhalte selektiv zu verarbeiten und einzuschließen.

**F: Wie kann ich Probleme beim Laden oder Speichern von E‑Mails diagnostizieren?**  
A: Prüfen Sie die Dateipfade auf Korrektheit, stellen Sie sicher, dass die Bibliothek korrekt im Projekt eingerichtet ist, und konsultieren Sie das [Support‑Forum von Aspose.Email](https://forum.aspose.com/c/email/10) für weitere Hilfe.

**F: Unterstützt die Bibliothek die Konvertierung anderer Formate (EML, MSG) nach MHT?**  
A: Absolut. `MailMessage.load` kann EML, MSG und weitere Formate lesen; anschließend können Sie sie mit denselben Optionen als MHT speichern.

## Ressourcen
- **Dokumentation**: Für einen tieferen Einblick in alle Funktionen besuchen Sie die [Aspose Email Java Documentation](https://reference.aspose.com/email/java/).  
- **Download**: Starten Sie Ihre kostenlose Testversion, indem Sie von [Releases](https://releases.aspose.com/email/java/) herunterladen.  
- **Kauf**: Erkunden Sie Kaufoptionen auf der [Official Purchase Page](https://purchase.aspose.com/buy) für den langfristigen Einsatz.  
- **Kostenlose Testversion und temporäre Lizenz**: Nutzen Sie umfassende Funktionen während einer Testphase oder erhalten Sie eine temporäre Lizenz über diese Links:  
  - [Free Trial](https://releases.aspose.com/email/java/)  
  - [Temporary License](https://purchase.aspose.com/temporary-license/)

Entdecken, implementieren und transformieren Sie Ihre E‑Mail‑Verarbeitung noch heute mit Aspose.Email für Java!

---

**Zuletzt aktualisiert:** 2026-03-02  
**Getestet mit:** Aspose.Email für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
