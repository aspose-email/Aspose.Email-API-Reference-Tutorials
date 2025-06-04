---
"date": "2025-05-29"
"description": "Erfahren Sie, wie Sie mit Aspose.Email für Java mehrere Eigenschaften in MAPI-Nachrichten effizient verwalten. Diese Anleitung behandelt die Festlegung von Float-, Double-, Long- und weiteren Typen."
"title": "Festlegen mehrerer MAPI-Eigenschaften in Java mit Aspose.Email – Ein umfassender Leitfaden"
"url": "/de/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Festlegen mehrerer MAPI-Eigenschaften in Java mit Aspose.Email: Ein umfassender Leitfaden

## Einführung

Die effektive Verwaltung von MAPI-Nachrichteneigenschaften ist entscheidend für die Verbesserung Ihrer Java-Anwendungen. Mit Aspose.Email für Java können Sie mehrere Eigenschaften wie Float, Double, Long, Short, Boolean und benutzerdefinierte Eigenschaften nahtlos festlegen. Diese Anleitung führt Sie durch verschiedene Methoden, um dies zu erreichen.

**Was Sie lernen werden:**
- Festlegen mehrerer Eigenschaften in MAPI-Nachrichten mit Aspose.Email Java
- Verschiedene Immobilientypen und ihre Verwendung verstehen
- Praktische Codebeispiele zur Umsetzung

Beginnen wir mit der Klärung der Voraussetzungen.

## Voraussetzungen

Um mitmachen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Java Development Kit (JDK):** JDK 8 oder höher installiert.
- **Aspose.Email-Bibliothek:** Version 25.4 wird empfohlen.
- **Maven-Setup:** Maven sollte in Ihrer IDE für die Abhängigkeitsverwaltung konfiguriert sein.

### Erforderliche Bibliotheken

Fügen Sie Aspose.Email als Abhängigkeit in Ihre `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lizenzerwerb
- **Kostenlose Testversion:** Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.
- **Temporäre Lizenz:** Zum längeren Testen ohne Einschränkungen erhalten.
- **Kaufen:** Erwägen Sie einen Kauf, wenn es Ihren Anforderungen entspricht.

## Einrichten von Aspose.Email für Java

Stellen Sie sicher, dass Aspose.Email in Ihrer Entwicklungsumgebung richtig konfiguriert ist:
1. **Importabhängigkeiten:** Maven-Abhängigkeiten auflösen.
2. **Lizenz festlegen:**
   - Laden Sie eine Lizenzdatei herunter von [Aspose](https://purchase.aspose.com/buy).
   - Wenden Sie es an mit:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Nachdem die Einrichtung abgeschlossen ist, sehen wir uns nun an, wie verschiedene Eigenschaften festgelegt werden.

## Implementierungshandbuch

### Festlegen mehrerer Float-Eigenschaften

Durch das Festlegen von Float-Eigenschaften können numerische Daten effizient gespeichert werden:

#### Überblick
Diese Funktion demonstriert das Hinzufügen mehrerer Float-Werte als MAPI-Nachrichteneigenschaften mit Aspose.Email für Java.

#### Schritte
1. **Erstellen und Initialisieren der Nachricht**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Hinzufügen von Float-Werten zu einer Liste**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Festlegen der Eigenschaft mit einer eindeutigen Kennung**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Erläuterung:* Das Property-Tag `0x23901004` identifiziert diesen Float-Eigenschaftssatz.

### Festlegen mehrerer Double-Eigenschaften

Double-Eigenschaften speichern Gleitkommazahlen mit hoher Genauigkeit:

#### Überblick
In diesem Abschnitt wird das Speichern mehrerer Double-Werte als MAPI-Nachrichteneigenschaften gezeigt.

#### Schritte
1. **Initialisieren der Nachricht**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Doppelte Werte auffüllen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Zu Eigenschaftstag zuweisen**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Festlegen mehrerer APPTIME-Eigenschaften

APPTIME-Eigenschaften speichern Zeitdauern effizient:

#### Überblick
Diese Funktion veranschaulicht die Verwendung von Zahlen mit doppelter Genauigkeit für Zeitdarstellungen.

#### Schritte
1. **Nachrichtenobjekt erstellen**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Zeitwerte hinzufügen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Festlegen der Eigenschaft**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Festlegen mehrerer langer Eigenschaften

Lange Eigenschaften sind ideal für große Ganzzahlen:

#### Überblick
Bei dieser Funktion geht es darum, mehrere lange Ganzzahlwerte in einer Nachricht festzulegen.

#### Schritte
1. **MAPI-Nachricht initialisieren**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lange Werte hinzufügen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Eigenschaftstag definieren**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Festlegen mehrerer kurzer Eigenschaften

Kurze Eigenschaften speichern kleine Ganzzahldaten effizient:

#### Überblick
Diese Anleitung zeigt, wie Sie kurze Ganzzahlen als Nachrichteneigenschaften festlegen.

#### Schritte
1. **Initialisieren der Nachricht**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Kurze Werte hinzufügen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Eigenschafts-Tag zuweisen**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Festlegen mehrerer Boolescher Eigenschaften

Boolesche Eigenschaften speichern Wahr/Falsch-Zustände:

#### Überblick
Erfahren Sie, wie Sie in einer Nachricht mehrere Boolesche Werte festlegen.

#### Schritte
1. **Nachrichtenobjekt erstellen**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Boolesche Werte hinzufügen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Eigenschaft mit Bezeichner festlegen**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Festlegen einer Null-Eigenschaft

Es kann sinnvoll sein, eine Eigenschaft explizit auf null zu setzen:

#### Überblick
In diesem Abschnitt wird die Zuweisung eines Nullwerts zu einer Eigenschaft veranschaulicht.

#### Schritte
1. **Initialisieren der Nachricht**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Null-Eigenschaft zuweisen**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Festlegen einer benannten langen Eigenschaft mit benutzerdefinierter ID und UUID

Legen Sie für komplexe Szenarien benannte Eigenschaften fest:

#### Überblick
Diese Funktion demonstriert das Festlegen einer langen Eigenschaft mit einer benutzerdefinierten Kennung und UUID.

#### Schritte
1. **Initialisieren der Nachricht**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Lange Werte hinzufügen**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Eigenschaft erstellen und zuordnen**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Festlegen einer benutzerdefinierten Eigenschaft mit Namen

Benutzerdefinierte Eigenschaften können zur einfacheren Identifizierung benannt werden:

#### Überblick
In dieser Anleitung wird das Festlegen von Eigenschaften mit benutzerdefinierten Namen gezeigt.

#### Schritte
1. **Nachrichtenobjekt initialisieren**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Benutzerdefinierte Eigenschaft definieren**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Festlegen und Validieren von Eigenschaften

Es ist wichtig sicherzustellen, dass die Eigenschaften richtig eingestellt sind:

#### Überblick
In diesem Abschnitt wird das Festlegen und Validieren mehrerer Eigenschaften in MAPI-Nachrichten behandelt.

#### Schritte
1. **Eigenschaft festlegen**
   Befolgen Sie die vorherigen Beispiele, um eine Eigenschaft festzulegen.
2. **Eigenschaft validieren**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Abschluss

Dieser Leitfaden bietet einen umfassenden Ansatz zur Verwaltung mehrerer Eigenschaften in MAPI-Nachrichten mit Aspose.Email für Java. Mit diesen Schritten können Sie verschiedene Datentypen effizient in Ihren Anwendungen speichern und verwalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}