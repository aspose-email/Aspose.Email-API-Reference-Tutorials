---
"date": "2025-05-30"
"description": "Erfahren Sie, wie Sie die Kontaktverwaltung mit Exchange-Servern mithilfe von Aspose.Email für .NET über EWS integrieren. Diese Anleitung beschreibt die effiziente Einrichtung, Verbindung und den Abruf von Kontakten."
"title": "Abrufen von Kontakten mit Aspose.Email und EWS in .NET – Ein umfassender Leitfaden"
"url": "/de/net/exchange-server-integration/retrieve-contacts-aspose-email-net-exchange-ews/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Abrufen von Kontakten mit Aspose.Email und EWS in .NET: Ein umfassender Leitfaden

## Einführung

Die Kontaktverwaltung über einen Exchange-Server integriert sich nahtlos in Ihre .NET-Anwendungen, optimiert Kommunikationsabläufe, spart Zeit und steigert die Produktivität. Dieses Tutorial führt Sie durch die Nutzung der leistungsstarken **Aspose.Email für .NET** API zum Herstellen einer Verbindung mit einem Exchange-Server über den Webdienst (EWS) und zum Abrufen einer Kontaktliste.

### Was Sie lernen werden:
- Einrichten von Aspose.Email für .NET in Ihrem Projekt
- Herstellen einer Verbindung mit einem Exchange-Server über EWS
- Programmgesteuertes Abrufen und Anzeigen von Kontaktinformationen

Mit diesen Fähigkeiten können Sie die E-Mail-Kommunikation problemlos verwalten. Beginnen wir mit den Voraussetzungen.

## Voraussetzungen

Bevor Sie mit der Codeimplementierung beginnen, stellen Sie sicher, dass Ihre Entwicklungsumgebung einsatzbereit ist:

- **Bibliotheken und Versionen**: Stellen Sie sicher, dass Sie Aspose.Email für .NET installiert haben.
- **Umgebungs-Setup**: Sie benötigen eine .NET-Entwicklungsumgebung, z. B. Visual Studio 2019 oder höher.
- **Voraussetzungen**: Grundkenntnisse in C# und der Arbeit mit APIs sind hilfreich.

## Einrichten von Aspose.Email für .NET

Zunächst müssen Sie die Bibliothek Aspose.Email zu Ihrem Projekt hinzufügen. So geht's:

### Installation

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Email
```

**Verwenden der Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Email
```

**Über die NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Email“ und installieren Sie die neueste Version.

### Lizenzerwerb

Sie können beginnen mit einem **kostenlose Testversion** um Funktionen zu erkunden. Für längere Projekte sollten Sie eine Lizenz erwerben oder eine temporäre Lizenz anfordern:
- [Kostenlose Testversion](https://releases.aspose.com/email/net/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)

Initialisieren Sie Ihr Projekt, indem Sie die erforderlichen using-Direktiven hinzufügen und eine Instanz von `IEWSClient` für den Verbindungsaufbau.

## Implementierungshandbuch

In diesem Abschnitt werden Sie durch jeden Schritt geführt, der zum Abrufen von Kontakten von einem Exchange-Server erforderlich ist.

### Schritt 1: Erstellen einer Instanz von IEWSClient

**Überblick**Stellen Sie mit dem EWS-Client von Aspose.Email eine sichere Verbindung zu Ihrem Exchange-Server her.

```csharp
IEWSClient client = EWSClient.GetEWSClient(
    "https://outlook.office365.com/ews/exchange.asmx", 
    "testUser",    
    "pwd",         
    "domain"       
);
```

**Erläuterung**: Ersetzen `"testUser"`, `"pwd"`, Und `"domain"` mit Ihren tatsächlichen Exchange-Server-Anmeldeinformationen. Dieser Schritt authentifiziert und initialisiert die Verbindung.

### Schritt 2: Alle Kontakte auflisten

**Überblick**: Rufen Sie mit EWS Kontakte aus Ihrem Postfach ab.

```csharp
Contact[] contacts = client.GetContacts(client.MailboxInfo.ContactsUri);
```

**Erläuterung**: `client.GetContacts` ruft alle verfügbaren Kontakte ab. Die Methode gibt ein Array von Kontaktobjekten zurück, die anschließend verarbeitet werden können.

### Schritt 3: Kontaktinformationen anzeigen

**Überblick**: Durchlaufen Sie die abgerufenen Kontakte, um deren Namen und E-Mail-Adressen anzuzeigen.

```csharp
foreach (MapiContact contact in contacts)
{
    Console.WriteLine(
        "Name: " + contact.NameInfo.DisplayName + ", Email Address: " +
        contact.ElectronicAddresses.Email1
    );
}
```

**Erläuterung**: Durchlaufen Sie jede `MapiContact` um auf wichtige Informationen wie Name und E-Mail-Adresse zuzugreifen und diese anzuzeigen.

### Tipps zur Fehlerbehebung

- Stellen Sie sicher, dass Server-URL, Benutzername, Passwort und Domäne richtig konfiguriert sind.
- Überprüfen Sie die Netzwerkkonnektivität, wenn keine Verbindung zum Exchange-Server hergestellt werden kann.
- Stellen Sie sicher, dass Ihre API-Version mit Ihrer .NET Framework-Version kompatibel ist.

## Praktische Anwendungen

Hier sind einige Szenarien aus der Praxis, in denen das Abrufen von Kontakten über Aspose.Email von Vorteil sein kann:
1. **Automatisierte E-Mail-Kampagnen**: Automatisches Sammeln und Aktualisieren von Kontaktlisten für Marketingzwecke.
2. **CRM-Integration**: Synchronisieren Sie Kontaktinformationen zwischen Exchange-Server und CRM-Systemen wie Salesforce oder Dynamics 365.
3. **Datensicherungslösungen**: Erstellen Sie Backups der Kontaktdaten, um die Geschäftskontinuität sicherzustellen.

## Überlegungen zur Leistung

Beim Arbeiten mit Aspose.Email in .NET-Anwendungen:
- **Netzwerkanrufe optimieren**: Minimieren Sie die Anzahl der API-Aufrufe, indem Sie nur erforderliche Felder abrufen.
- **Effizientes Speichermanagement**: Entsorgen Sie nicht mehr benötigte Objekte, um Speicherressourcen freizugeben.
- **Stapelverarbeitung**: Wenn Sie mit großen Datensätzen arbeiten, sollten Sie die Kontaktverarbeitung in Stapeln in Betracht ziehen.

## Abschluss

Sie haben nun gelernt, wie Sie mit Aspose.Email für .NET eine Verbindung zu einem Exchange-Server herstellen und Kontakte abrufen. Dieses leistungsstarke Tool kann die E-Mail-Verwaltung Ihrer Anwendung erheblich verbessern. Für weitere Informationen können Sie sich mit erweiterten Funktionen der API wie dem Senden von E-Mails oder der Kalenderverwaltung befassen.

Werden Sie noch heute aktiv und probieren Sie diese Implementierung in Ihren Projekten aus!

## FAQ-Bereich

1. **Was ist Aspose.Email für .NET?**
   - Es handelt sich um eine Bibliothek, die die Interaktion mit E-Mail-Servern wie Exchange über verschiedene Protokolle, einschließlich EWS, erleichtert.
2. **Wie gehe ich mit Authentifizierungsfehlern bei der Verbindung mit einem Exchange-Server um?**
   - Überprüfen Sie Ihre Anmeldeinformationen noch einmal und stellen Sie sicher, dass die Server-URL korrekt ist.
3. **Kann Aspose.Email offline funktionieren?**
   - Während es hauptsächlich mit Onlinediensten interagiert, können Sie lokale Dateien wie PST- oder MSG-Formate offline bearbeiten.
4. **Gibt es eine Begrenzung für die Anzahl der Kontakte, die ich gleichzeitig abrufen kann?**
   - Die Kontaktbeschränkungen hängen von der Konfiguration Ihres Exchange-Servers ab. Wenden Sie sich bei Bedarf an Ihren Systemadministrator.
5. **Wie aktualisiere ich die Informationen eines Kontakts mit Aspose.Email?**
   - Nutzen Sie die `UpdateContact` Methode nach dem Ändern der Eigenschaften eines `MapiContact`.

## Ressourcen

- [Aspose.Email Dokumentation](https://reference.aspose.com/email/net/)
- [Laden Sie Aspose.Email herunter](https://releases.aspose.com/email/net/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/email/net/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Support-Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}