---
date: '2026-01-04'
description: Leer hoe je een Exchange-agenda maakt in Java met Aspose.Email voor Java.
  Inclusief Maven‑dependency, verbinding maken met Exchange in Java en afspraakbeheer.
keywords:
- Exchange Calendar Management
- Aspose.Email for Java
- Java Exchange Server Integration
title: Exchange‑agenda maken in Java met Aspose.Email – Een volledige gids
url: /nl/java/calendar-appointments/mastering-exchange-calendar-management-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exchange Agenda Java maken met Aspose.Email

## Introductie

E-mails en agenda's beheren in een zakelijke omgeving kan complex zijn, vooral wanneer je **create exchange calendar java** programma's moet maken die werken voor meerdere gebruikers en tijdzones. Gelukkig vereenvoudigt **Aspose.Email for Java** deze taken door robuuste API's te bieden voor Exchange Server agenda‑beheer. In deze uitgebreide gids leer je hoe je verbinding maakt met een Exchange‑server, agenda‑mappen maakt en afspraken afhandelt — allemaal met duidelijke, stap‑voor‑stap Java‑code.

**Wat je zult leren**
- Hoe je **connect to exchange java** gebruikt met Aspose.Email  
- Hoe je de **maven dependency aspose email** aan je project toevoegt  
- Een nieuwe agenda‑map maken en afspraken beheren  
- Afspraken bijwerken, weergeven en annuleren  

Laten we beginnen!

## Snelle antwoorden
- **Wat is de primaire bibliotheek?** Aspose.Email for Java  
- **Hoe voeg ik de bibliotheek toe?** Gebruik de Maven‑dependency hieronder  
- **Kan ik een agenda‑map maken?** Ja, met één API‑aanroep  
- **Heb ik een licentie nodig?** Een proefversie werkt voor ontwikkeling; een volledige licentie is vereist voor productie  
- **Is dit compatibel met Office 365?** Absoluut – dezelfde code werkt met Exchange Online  

## Wat is “create exchange calendar java”?
Een Exchange‑agenda maken in Java betekent programmatisch communiceren met een Exchange‑mailbox om agenda‑items toe te voegen, te wijzigen of te verwijderen. Deze aanpak is ideaal voor geautomatiseerde planning, vergaderbeheer‑tools of enterprise‑brede agenda‑synchronisatie.

## Waarom Aspose.Email voor Java gebruiken?
- **Full‑featured API** – Behandelt Exchange Web Services (EWS) zonder low‑level SOAP‑afhandeling.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS met elke JDK 16+ runtime.  
- **No external dependencies** – De bibliotheek bevat alles wat je nodig hebt om met Exchange te communiceren.  

## Vereisten
- **Aspose.Email for Java** bibliotheek (version 25.4 or later)  
- JDK 16 or higher  
- Toegang tot een Exchange Server (Office 365 or on‑premises)  
- IDE such as IntelliJ IDEA, Eclipse, or NetBeans  

## Maven‑dependency Aspose Email
Voeg het volgende fragment toe aan je `pom.xml`. Dit is de **maven dependency aspose email** die je nodig hebt om de bibliotheek van Maven Central te halen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Stappen voor licentie‑acquisitie
1. **Free Trial:** Download een proefversie van de [Aspose website](https://releases.aspose.com/email/java/) om functies te testen.  
2. **Temporary License:** Verkrijg een tijdelijke licentie voor volledige functionaliteit via [deze link](https://purchase.aspose.com/temporary-license/).  
3. **Purchase:** Als je tevreden bent, overweeg dan een volledige licentie aan te schaffen op de [aankooppagina van Aspose](https://purchase.aspose.com/buy).

## Verbinden met Exchange Java
**Overzicht:** Deze sectie laat zien hoe je **connect to exchange java** gebruikt met de EWS‑client.

### Stap 1: Verbinding tot stand brengen
```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

public class ConnectToExchangeServer {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server with provided URL and credentials
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");
            System.out.println("Connected to Exchange server.");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** Vervang `"username"` en `"password"` door je werkelijke inloggegevens. Deze code maakt een `IEWSClient`‑instantie aan die je opnieuw zult gebruiken voor alle volgende agenda‑bewerkingen.

## Agenda‑map maken
**Overzicht:** Maak een speciale map binnen de agenda van de mailbox om gerelateerde afspraken georganiseerd te houden.

### Stap 2: Nieuwe agenda‑map maken
```java
import com.aspose.email.MailboxInfo;

public class CreateCalendarFolder {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Create a new calendar folder named 'new calendar'
            String calendarUri = client.getMailboxInfo().getCalendarUri();
            client.createFolder(calendarUri, "new calendar", null, "IPF.Appointment");
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** De map `"new calendar"` verschijnt onder de hoofd‑agenda‑hiërarchie, klaar om later gemaakte afspraken op te slaan.

## Afspraak maken in agenda‑map
**Overzicht:** Voeg een vergadering of evenement toe aan de nieuw gemaakte agenda‑map.

### Stap 3: Afspraakdetails instellen
```java
import com.aspose.email.Appointment;
import com.aspose.email.MailAddress;
import java.util.Calendar;
import java.util.Date;
import java.util.UUID;

public class CreateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details
            Calendar calendar = Calendar.getInstance();
            Date startTime = calendar.getTime();
            calendar.add(Calendar.HOUR, 1);
            Date endTime = calendar.getTime();
            String timeZone = "America/New_York";

            Appointment appointment = new Appointment("Room 121", startTime, endTime,
                    MailAddress.to_MailAddress("email1@aspose.com"),
                    MailAddressCollection.to_MailAddressCollection("email2@aspose.com"));
            appointment.setTimeZone(timeZone);
            appointment.setSummary("EMAILNET-35198 - ".concat(UUID.randomUUID().toString()));
            appointment.setDescription("EMAILNET-35198 Ability to add Java event to Secondary Calendar of Office 365");

            // List subfolders and get the URI for the new calendar folder created earlier
            String newCalendarFolderUri = client.listSubFolders(client.getMailboxInfo().getCalendarUri()).get_Item(0).getUri();

            // Create appointment in the specified calendar folder
            client.createAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** Deze code bouwt een `Appointment`‑object, stelt de tijdzone in, voegt deelnemers toe en slaat het op in de aangepaste agenda‑map.

## Afspraak bijwerken
**Overzicht:** Wijzig de eigenschappen van een bestaande afspraak, zoals locatie of onderwerp.

### Stap 4: Bestaande afspraak definiëren
```java
import com.aspose.email.Appointment;

public class UpdateAppointment {
    public static void main(String[] args) {
        IEWSClient client = null;
        try {
            // Connect to Exchange Server (Replace with actual credentials)
            client = EWSClient.getEWSClient("https://outlook.office365.com/exchangeews/exchange.asmx", "username", "password");

            // Setup appointment details for existing appointment
            Appointment appointment = new Appointment();
            appointment.setLocation("Room 122");

            // Specify the URI of the calendar folder where the appointment exists
            String newCalendarFolderUri = "YOUR_DOCUMENT_DIRECTORY";

            // Update the location of the existing appointment
            client.updateAppointment(appointment, newCalendarFolderUri);
        } finally {
            if (client != null)
                client.dispose();
        }
    }
}
```
**Uitleg:** Vervang `"YOUR_DOCUMENT_DIRECTORY"` door de werkelijke map‑URI van de afspraak die je wilt bijwerken. Dit fragment toont hoe je het locatie‑veld wijzigt.

## Veelvoorkomende problemen & tips
- **Authentication errors:** Controleer of het account EWS‑toegang heeft en dat multi‑factor authenticatie is uitgeschakeld of een app‑wachtwoord wordt gebruikt.  
- **Folder URI not found:** Gebruik `client.listSubFolders()` om de juiste agenda‑URI te ontdekken voordat je items maakt of bijwerkt.  
- **Time‑zone mismatches:** Stel altijd de tijdzone in op het `Appointment`‑object om verrassingen door zomertijd te voorkomen.  

## Veelgestelde vragen

**Q: Heb ik een licentie nodig voor ontwikkeling?**  
A: Een gratis proefversie werkt voor ontwikkeling en testen, maar een volledige licentie is vereist voor productie‑implementaties.

**Q: Kan ik dit gebruiken met on‑premises Exchange?**  
A: Ja. Verander gewoon de EWS‑URL zodat deze naar je on‑premises server wijst.

**Q: Wordt Java 8 ondersteund?**  
A: De bibliotheek ondersteunt JDK 16 en nieuwer; oudere JDK's worden niet aanbevolen voor de nieuwste versie.

**Q: Hoe verwijder ik een afspraak?**  
A: Gebruik `client.deleteAppointment(appointmentId, calendarFolderUri);` nadat je de unieke ID van de afspraak hebt opgehaald.

**Q: Wat als ik terugkerende vergaderingen moet afhandelen?**  
A: Aspose.Email biedt een `Recurrence`‑klasse die je aan een `Appointment` kunt koppelen voordat je deze opslaat.

---

**Last Updated:** 2026-01-04  
**Tested With:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}